---
title: 'batman.js - Uncaught RangeError: Maximum call stack size exceeded'
author: admin
layout: post
permalink: /2012/05/29/batman-js-uncaught-rangeerror-maximum-call-stack-size-exceeded/
categories:
  - Javascript
---
# 

> Error:  
>   
> Uncaught RangeError: Maximum call stack size exceeded  
>  

I ran into this issue when I had data-route=”routeHere” defined incorrectly (it seems to cause an infinite loop). This was with a version of batman < 0.9. It seems to be handled since batman.js 0.9.