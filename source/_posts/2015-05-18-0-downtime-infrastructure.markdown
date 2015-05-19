---
layout: post
title: "0 Downtime Infrastructure"
date: 2015-05-18 19:01
comments: false
categories: [Devops, Uptime, 0 Downtime]
description: No one should ever try and visit a web page and find that it's down for maintenance. This is how we keep AMA websites up 100% of the time.
---

At AMA we strive for is a high quality user experience. Part of that user experience is making
 sure that our services are available to our members. If a service/site is down, we've failed the member. Imagine trying
 to book a road side assistance call and the site was down. That wouldn't be good.

Here's what we do to make sure that the sites are running 24/7.

Servers
---------------------

We use Amazon for our server hosting to make sure that we have servers available and can be spun up whenever we need them.
 In the winter time we can spike up to 3000+ concurrent users on our [AMA road reports](http://amaroadreports.ca/) site, so
 the ability to flex our server load is very important.

We use EC2 for the application boxes themselves. Elasticache for our in memory storage again and
 RDS for our data storage. All of the boxes/services are hosted on multiple [availability zones](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html) so
 if we suffer an outage in 1 data center we will automatically be flipped over to the other data center. We also leverage geo-redundant S3 for backups.

Application Deploys
---------------------

[Unicorn](http://unicorn.bogomips.org/) is our server of choice for our 0 downtime application deploys. This allows us to deploy the website without
 having to take down the website for a short period of time. We never want the member to see a downtime page. This also
 allows us to deploy at all hours of the day, so we don't have to do night time deploys.

Unicorn does a dance where it keeps the original version of the application in memory while you're deploying the new version
 of the application. Then it slowly phases out the original version for the new version. The experience is 100% seamless
 to the member.

Server Patching
---------------------

It's extremely critical that we stay on top of security patches. In both the Ruby/Rails world, but also on the infrastructure server side.
 Generally server patching needs to take down the server for a short period of time, however due to the technologies we use
 (RDS/Elasticache) our database and in memory storage is covered for us (by Amazon). For the application servers we pull 1 server out
 of the load balancer, apply the patches and then bring the server back into the load balancer once it's been rebooted (if it needs to).

This is a fully automated process using Ansible. We're also able to do this in paralell, so we can patch all of our sites at the same time.

Notifications
---------------------

We run a 24/7 on call crew that allows us to address any issues that might happen at night (you'd be surprised at how many people are
 renewing their memberships in the middle of the night!). The tough part of monitoring is that you need it at a few levels.

The first is the server level. Is the RAM/CPU/HD/Network performing correctly? No? Send a page! Then at the next level is the application,
 we need to make sure that the application itself is working correctly. If the web page isn't loading but the server is up
 something is wrong and someone needs to be paged. And the next level is the 3rd party integration. We're hooked into
 multiple webservices and they might go down. So we'll get an alert and follow up with the 3rd party.

We're able to cover off these scenarios with [New Relic](http://newrelic.com) and Rollbar(http://rollbar.com).

Armageddon
---------------------

What happens if your Amazon zones get wiped off the face of the earth? Luckily we store offsite backups of our data. Our
 server build and deploys are all fully automated so we can bring up our server environments extremely fast. It would probably
 take longer for DNS to propagate than it would for us to rebuild our infrastructure in a new Amazon Region.

We have had the odd outage here and there with Amazon (which is to be expected with cloud providers) and we've
 failed over without problems.


Summary
---------------------

If you're a member of AMA, you should expect the services to be available at all times. And we'll make sure that happens.


Ryan