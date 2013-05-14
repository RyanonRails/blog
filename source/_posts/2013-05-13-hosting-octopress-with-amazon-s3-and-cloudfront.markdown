---
layout: post
title: "Hosting Octopress with Amazon S3 and Cloudfront"
date: 2013-05-13 20:29
comments: false
categories:
 categories:
   - Amazon S3
   - Amazon CloudFront
   - Octopress
---

I recently set up this blog and I figured as my first "real" post I could go through the steps it took to set this up.
I gleaned quite a bit of information from quite a few sites, but overall I didn't find a guide that explained everything thouroughly.
I've made sure to include all of my references in the bottom of the post.

Generate Site

Upload to S3 (static site)

Update DNS

Configure Cloudfront


References:
* http://www.snikt.net/blog/2012/11/03/moving-octopress-to-amazon-s3-and-cloudfront/ (general information on the setup, speedtest chart)
* http://stackoverflow.com/questions/15309113/amazon-cloudfront-doesnt-respect-my-s3-website-buckets-index-html-rules (specify custom origin in cloudfront)
* http://stackoverflow.com/questions/1268158/force-cloudfront-distribution-file-update (CloudFront invalidation)
* http://stackoverflow.com/questions/8312162/static-hosting-on-amazon-s3-dns-configuration (A record for DNS, naked domain to www)

