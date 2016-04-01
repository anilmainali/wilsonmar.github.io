---
layout: post
title: "Build load-balanced servers in AWS EC2"
excerpt: "This is where computers are"
tags: [AWS, EC2, cloud]
image:
  feature: pic data center slice 1900x500.jpg
  credit: 
  creditlink: 
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}

Building a server within AWS for enterprise use requires several services:

* <a href="#AWSConsole">AWS Management Console</a>
* <a href="#CLI">Command Line Interface</a>
* <a href="#CF">Cloud Formation</a>
* <a href="#AMI">AMI</a>
* <a href="#ELB">ELB</a>
* <a href="#VPC">VPC</a> defines subnets
* <a href="#VPN">VPN</a> 
* <a href="#NAT">NAT</a>
* <a href="#AutoScale">Auto-Scale</a>

And dozens more.

<a name="AWSConsole"></a>

## AWS Management Console

The AWS Management Console 
is now used for <strong>manual review</strong> of one 
Availability Zone at a time.

In enterprises today, servers are built by 
scripts and configuration files 
generated from templates. 
This is so the build process can be debugged
and changed slightly through the lifecycle from test to prod.

Instead of clicking and typing, server administrators work with
template files in JSON format for Cloud Formation to process.

The next step up is to use Atlas 
which generates  
JSON files based on information typed into their web Consoles.

The <a href="#CLI">command line interface</a>
is used by programs rather than the manual Console.

These inputs to generators (and the generator code)
are saved in version control systems like Git.

However, tutorials in Amazon's Qwiklabs use the manual approach,
so it's presented here to provide notes.

0. There are several ways to select a service.
  One is clicking the icon in the gallery.

0. Copy the public DNS to clipboard (like 

    ec2-11-22-33-444-compute-1.amazonaws.com

0. Download the PEM/PPK.


<a name="CLI"></a>

## Command Line Interface


<a name="CF"></a>

## Cloud Formation

CF can span two or more Availability Zones 
in a multi-subnet Amazon <a href="#VPC">VPC</a>.

PROTIP: With such complexity, better use a JSON file
which contains all the resource specifications.

0. In the AWS Management Console Services gallery, click
   Cloud Formation.
0. Click Create New Stack.
0. In the Stack Name box, type "Lab" or other name.
0. Select Specify an Amazon S3 template URL.
0. Paste the URL. An example is provided at:

    http://us-east-1-aws-training.s3.amazonaws.com/self-paced-lab-15/VPC1.json

    This one has additional security groups and output parameters:

    http://us-east-1-aws-training.s3.amazonaws.com/self-paced-lab-15/VPC2.json

0. Click Next.
0. On the Specify Parameters page, leave the default settings.
0. Click Next in the Options page (no Tags).
0. Click Create after reviewing.
0. Click Events tab.
0. Click Refresh occassionally.
0. On the Services menu, click VPC to see results.

To Delete the stack, first turn off Termination Protection:

0. Select EC2 from the Services gallery.
0. Click Instances.
0. <strong>Right-click</strong> on the running instance
   to Change Termination Protection.
0. Click Yes, Disable.
0. Now back on Cloud Formation service.
0. Select the box for the stack to be deleted.
0. Click Delete Stack.
0. Click Yes, Delete.

### CF Front Matter
An example template:

{% highlight text %}
{
  "AWSTemplateFormatVersion" : "2010-09-09",

  "Description" : "VPC with 4 subnets across 2 Availability Zones.",
{% endhighlight %}

PROTIP: Use #tags as  metadata in the Description to 
automate search among multiple files.

<a name="AZ"></a>

## Availability zone
Unlike the Console web page,
which shows the current Availability Zone in the upper right corner,
within CLI you use a command:

    ```
    ec2-metadata -z
    ```

<a name="AMI"></a>

## AMI (Amazon Machine Image)

Images of what is in a server containing all the software.

Each AMI is created by taking a snapshot 
of what has been configured on a server.

In CF Mapping, each AMI is specific to a Availability Zone.

{% highlight text %}
    "AWSRegionArch2AMI" : {
      "us-east-1"      : {"64" : "ami-f619c29f"},
      "us-west-2"      : {"64" : "ami-52ff7262"},
      "us-west-1"      : {"64" : "ami-3bcc9e7e"},
      "eu-west-1"      : {"64" : "ami-e5e2d991"},
      "ap-southeast-1" : {"64" : "ami-02eb9350"},
      "ap-southeast-2" : {"64" : "ami-ab990e91"},
      "ap-northeast-1" : {"64" : "ami-14d86d15"},
      "sa-east-1"      : {"64" : "ami-0039e61d"}
    }
{% endhighlight %}

<a name="Mappings"></a>

## Mappings of Instance Types
Within the Console, the type of machine are Instance Types.

In a CF JSON file, instance types are defined in Mappings:

{% highlight text %}
  "Mappings" : {
    "AWSInstanceType2Arch" : {
      "m1.small"   : { "Arch" : "64" },
      "m1.medium"  : { "Arch" : "64" },
      "m1.large"   : { "Arch" : "64" },
      "m1.xlarge"  : { "Arch" : "64" },
      "m2.xlarge"  : { "Arch" : "64" },
      "m2.2xlarge" : { "Arch" : "64" },
      "m2.4xlarge" : { "Arch" : "64" },
      "m3.xlarge"  : { "Arch" : "64" },
      "m3.2xlarge" : { "Arch" : "64" },
      "c1.medium"  : { "Arch" : "64" },
      "c1.xlarge"  : { "Arch" : "64" }
    },
{% endhighlight %}

Nowdays, 64-bit servers are all that is being made.

<a name="VPC"></a>

## VPC (Virtual Private Cloud)

For security, some servers can only make outbound calls to the internet (through the <a href="#NAT">NAT server</a>)

There is one VPC per Availability Zone.

A single Gateway serves all VPCs because that is the address
the public DNS resolves corporate host names to.

In each VPC is a public subnet and a private subnet.

In the CF JSON to define a VPC, CF automatically populates the
"VpcId" : { "Ref" : "VPC" },

{% highlight text %}
  "Resources" : {
     "VPC" : {
      "Type" : "AWS::EC2::VPC",
      "Properties" : {
        "CidrBlock" : "10.0.0.0/16"
      }
    },

    "InternetGateway" : {
      "Type" : "AWS::EC2::InternetGateway",
      "Properties" : { 
      }
    },

    "AttachGateway" : {
       "Type" : "AWS::EC2::VPCGatewayAttachment",
       "Properties" : {
         "VpcId" : { "Ref" : "VPC" },
         "InternetGatewayId" : { "Ref" : "InternetGateway" }
       }
    },
{% endhighlight %}


NOTE: One annoyance of EC2 at the moment is the use of 
static IP addresses in configurations. 

An alternative cloud (Skytap) enables servers to be configured
and saved with a static IP address which Skytap internally 
changes to real ones. This allows many servers to be configured
and run with the same IP addresses.


<a name="SecGroups"></a>

## Security Groups

SGs define which ports are open.

By default, no ports are open.

This template has additional output parameters:



<a name="ACL"></a>

## ACL

Access Control Lists can provide more fine-grained control.

There is a spearate ACL for ingress in and egress out.

ACL use degrades performance because every packet
is inspected.


<a name="NAT"></a>

## NAT 
Network Address Translation enables servers in private subnets to communicate with the public Internet outside the farm.

An example of how NAT is configured in a CF JSON file:

{% highlight text %}
  "Parameters" : {
    
    "NATInstanceType" : {
      "Description" : "NAT EC2 instance type",
      "Type" : "String",
      "Default" : "m1.small",
      "AllowedValues" : [ "m1.small","m1.medium" ]
    },
{% endhighlight %}

The "m1.small" is defined in <a href="#Mappings">Mappings</a>.

In the CF JSON Resources section:

{% highlight text %}
    "NAT" : {
      "Type" : "AWS::EC2::Instance",
      "Properties" : { 
        "InstanceType" : { "Ref" : "NATInstanceType" },
        "ImageId" : { "Fn::FindInMap" : [ "AWSRegionArch2AMI", { "Ref" : "AWS::Region" },
                      { "Fn::FindInMap" : [ "AWSInstanceType2Arch", { "Ref" : "NATInstanceType" }, "Arch" ] } ] },
        "SubnetId" : { "Ref" : "PublicSubnet1" },
        "SourceDestCheck" : "false",
        "DisableApiTermination" : "true",
        "SecurityGroupIds" : [ { "Ref" : "NATSecurityGroup" } ],
        "Tags" : [ 
          { "Key" : "Name", "Value" : { "Fn::Join" : ["", [
              "NAT-", { "Ref" : "VPC"} ]] } }
        ]
      }
    },
  
    "NATIP" : {
      "Type" : "AWS::EC2::EIP",
      "Properties" : {
        "Domain" : "vpc",
        "InstanceId" : { "Ref" : "NAT" }
      }
    },
    
   "NATSecurityGroup" : {
      "Type" : "AWS::EC2::SecurityGroup",
      "Properties" : {
        "GroupDescription" : "NAT Security Group",
        "VpcId" : {"Ref" : "VPC"},
        "SecurityGroupIngress" : [ 
          { "IpProtocol" : "-1", "FromPort" : "1", "ToPort" : "65535", "SourceSecurityGroupId" : { "Ref" : "PrivateSG" } },
          { "IpProtocol" : "icmp", "FromPort" : "-1", "ToPort" : "-1", "SourceSecurityGroupId" : { "Ref" : "PrivateSG" } }
        ]
      }
    },
{% endhighlight %}

The "EIP" is an Elastic IP to the public.

NOTE: NAT servers are physical appliances, so no SSH key pairs are
used to log into the instance.

NAT instances are a Single Point of Failure (SPOF),
so monitoring and automated replacement is needed.

<a name="VPN"></a>

## VPN (Virtual Private Network)
VPN is not an Amazon invention.

VPN secures the network between data centers.
So VPN are said to extend data centers.

The CorporateCidrIP parameter in the CF JSON Parameters section
(at the top)
is the IP address VPC allowed 
inbound access.

{% highlight text %}
    "CorporateCidrIp" : {
      "Description" : "Your Company's CidrIp (to restrict traffic to be authorized ONLY from corporate office)",
      "Type" : "String",
      "Default" :  "0.0.0.0/0"
    } 
{% endhighlight %}

Cidr (Classless Inter-Domain Routing) is also called "supernetting"
becuase it allows more flexible allocation of Internet Protocol (IP) addresses. Whatever.

<a name="Bastion"></a>

## Bastion Hosts

Bastion hosts are the only servers allowed access from SSH
via the public internet.

Windows users use Putty program from:

    http://the.earth.li/~sgtatham/putty/latest/x86/putty.exe

Public and private keys:

    * Windows users download the PPK.
    * Linux/Mac users download the PEM.


<a name="ELB"></a>

## ELB (Elastic Load Balancer)



<a name="AutoScale"></a>

## Auto-Scale

Amazon charges by the hour, even if the server was used only a few minutes.

The cooldown period to remove servers is 5 minutes 
(x60 = 300 seconds).

### Auto-Scaling Config

Auto scaling launches specific AMI instances.

{% highlight html %}
as-create-launch-config 
--image-id  (an Amazon Linux AMI)
--instance-type t1.micro 
--key <YourKeyName> 
--group <YourSecurityGroup> 
--user-data-file as-bootstrap.sh 
--launch-config lab-lc
{% endhighlight %}

### Create Auto Scaling Group

{% highlight html %}
as-create-auto-scaling-group 
lab-as-group 
--availability-zones <YourAvailabilityZone> 
--launch-configuration lab-lc 
--load-balancers <YourElasticLoadBalancer> 
--max-size 5 
--min-size 1
{% endhighlight %}

PROTIP: There is a maximum of 5 in a group being scaled.

The response is:

    ```
    OK-Created AutoScalingGroup
    ```

### Verify Auto Scaling

0. In the AWS Management Console | Services | EC2 | Instances.
0. Select instance without a name. Refresh.
0. Status Checks should say "2/2".
0. Copy the Public DNS and paste it in a browser.

   It should say CPU Load: 0%.

0. Click <strong>Generate Load</strong>.

> The condition for auto-scaling is to terminate one of the instances.

> Identify the amount of time between when the condition occurs
to when the new instance can accept and process requests.

Consider the time sequence:

   * CloudWatch aggregation makes data available (60 seconds)
   * Auto Scaling Trigger is invoked (polling every 60 seconds)
   * New instance is populated (several minutes)
   * New instance is placed in Load Balancer.


<a name="TagAutoScale"></a>

### Tag Auto Scaling Resources

0. Click the gear icon to Show/Hide columns.

<pre>
as-create-or-update-tags 
--tag "id=lab-as-group, t=auto-scaling-group, k=Name, v=AS-Web-Server, p=true"
</pre>

### Create Auto Scaling Notifications

0. This uses Amazon's Simple Notification Service (SNS).
   Go to that among AWS Management Console.
0. Click Get Started.
0. Click Create Topic.
0. For Topic Name, type "lab-as-topic".

    PROTIP: Define a naming convention for topics.

0. Click Create Topic.
0. Click Create Subscription.
0. Click Email for Protocol.
0. Type an email address in the Enpoint box.

    PROTIP: Specify a <strong>group</strong> email.

0. Click Create Subscription.
0. Specify the Topic ARN.

{% highlight html %}
as-put-notification-configuration <lab-as-group>
--topic-arn <TopicARN> 
--notification-types autoscaling:EC2_INSTANCE_LAUNCH, autoscaling:EC2_INSTANCE_TERMINATE
{% endhighlight %}

### Auto Scaling Policies

{% highlight html %}
as-put-scaling-policy lab-scale-up-policy 
--auto-scaling-group <lab-as-group>
--adjustment=1 
--type ChangeInCapacity 
--cooldown 300
{% endhighlight %}

To scale down:

{% highlight html %}
as-put-scaling-policy lab-scale-down-policy 
--auto-scaling-group lab-as-group "--adjustment=-1" 
--type ChangeInCapacity 
--cooldown 300
{% endhighlight %}



<pre>
as-describe-scaling-activities --show-long
</pre>

<a name="CloudWatch"></a>

## CloudWatch

CloudWatch is necessary to detect when instances need to be 
added or removed.

The conditions can be CPU utilization percentage 
over a period of time, 
or something more elaborate.

0. In AWS Services, select CloudWatch.
0. Click Alarms.
0. Create Alarm.
0. Search for By Auto Scaling Group on the CloudWatch Metrics by Category page.
0. Select AutoScalingGroupName "lab-as-group".
0. Select Metric Name "CPUUtilization". Next.
0. Type High CPU Alarm in Name box. Description.
0. In Whenever drop-down list, select exceeds or equals >=50
(50%) for one consecutive period.
0. CLick + AutoScaling Action.

PROTIP: A full set of triggers need to include all the components,
which include memory, disk space, file handles, available ports, etc.

<a name="CloudFront"></a>

## CloudFront

CloudFront is Amazon's CDN (Content Delivery Network)
where files in S3 (Simple Storage Service) 
are spread around the world.

Compared with Akamai, CloudFront has no minimum usage costs.

CloudFront is among green icons for
Management Tools in the Services gallery.

CloudFront has one Resource Type: Distribution.




