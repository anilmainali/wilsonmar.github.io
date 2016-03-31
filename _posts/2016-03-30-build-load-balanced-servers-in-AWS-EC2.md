---
layout: post
title: "Build load-balanced servers in AWS EC2"
excerpt: "How high is your availability?"
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

* <a href="#AMI">AMI</a>
* <a href="#AWSConsole">AWS Management Console</a>
* <a href="#CLI">Command Line Interface</a>
* <a href="#ELB">ELB</a>
* <a href="#VPC">VPC</a>
* <a href="#NAT">NAT</a>
* <a href="#AutoScale">Auto-Scale</a>
* <a href="#CF">Cloud Formation</a>

<a name="AMI"></a>

## AMI



<a name="AWSConsole"></a>

## AWS Management Console

The AWS Management Console is now used
for manual review, not to do the work
because scripts and configuration files are used to provide
repeatability.

Tutorials in Amazon's Qwiklabs use this, so it's presented here
to provide notes.

Create AMI instances.


<a name="CLI"></a>

## Command line interface

## Availability zone

We want "high" availability.

What is it again?

    ```
    ec2-metadata -z
    ```

<a name="ELB"></a>

## ELB (Elastic Load Balancer)

<a name="VPC"></a>

## VPC (Virtual Private Cloud)

<a name="NAT"></a>

## NAT (Network Address Translation)

A NAT allows servers in private subnets to communicate with the Internet.

<a name="AutoScale"></a>

## Auto-Scale

### Create Auto-Scaling Group

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

### Create Auto Scaling Policies

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


<a name="CF"></a>

## Cloud Formation

CF is used to span two or more Availability Zones 
in a four-subnet Amazon VPC

PROTIP: With such complexity, better use a JSON file
which contains all the specifications to ensure repeatability.
