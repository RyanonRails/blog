---
title: 'batman.js - Data not being submitted to server on create (POST)'
author: admin
layout: post
permalink: /2012/05/29/batman-js-data-not-being-submitted-to-server-on-create/
categories:
  - Javascript
---
# 

I couldn’t figure out why my data wasn’t being submitted up to the server on a POST (create). Turns out that the data-bind are case sensitive. IE:

    class EST.Section extends Batman.Model
      @resourceName: 'section'
    
      @set 'primaryKey', 'SectionId'
      @persist Batman.RestStorage
      @encode 'SectionId', 'Name'

They need to match up with @encode ‘SectionId’, ‘Name’

    
      

The POST parameters came across once I specified them as case sensitive.

Batman 0.9