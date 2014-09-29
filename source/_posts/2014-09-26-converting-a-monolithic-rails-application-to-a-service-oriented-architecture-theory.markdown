---
layout: post
title: "Converting a Monolithic Rails Application to a Service Oriented Architecture - Theory"
date: 2014-09-26 21:02
comments: false
categories: Architecture SOA
---

Over the past year at AMA we've done some amazing things. One of them is convert over a huge Rails (3.0+)
application into multiple sites which are all linked together with OAuth2. This was a huge undertaking that took over a year,
and there's still some cleanup we have to do.

There's a few reasons that we wanted to get this in place:

- Technical debt was at an all time high, we needed better test coverage
- As the team grew, working on 1 app was painful
- We needed a common API to communicate in and out with external services
- 1 login for every site, including mobile

For the purpose of this blog post I'm going to pretend we're google. I'm also only going to cover the general theory of how to break
everything apart. I'll be creating more technical blog posts to supplement this one.





