---
title: Upload a document to Sharepoint 2010 via WebClient
author: admin
layout: post
permalink: /2011/09/17/upload-a-document-to-sharepoint-2010-via-webclient/
categories:
  - Microsoft / CRM / SharePoint / SSRS
---
# 

Here’s some code on how to upload a document into Sharepoint 2010. This works accross domains:

    WebClient wc = new WebClient();
    wc.Credentials = loginCredentials;
    wc.UploadData(destinationUrl, "PUT", fileData);

A big FYI. The Copy.asmx web service will **NOT** work across domains. Using the above method will work for all occasions (of course the only issue is that you need to update the columns in a separate call.