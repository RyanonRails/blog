---
title: Download a document from Sharepoint 2010 via WebClient
author: admin
layout: post
permalink: /2011/10/11/download-a-document-from-sharepoint-2010-via-webclient/
categories:
  - Microsoft / CRM / SharePoint / SSRS
---


Here’s how I use the WebClient object to download a pdf from Sharepoint 2010:
{% codeblock lang:csharp %}
string uri = "wwww.google.ca";
string filepath = "waffles.pdf";
 
WebClient wc = new WebClient();
wc.Credentials = loginCredentials;
byte[] generatedPdf = wc.DownloadData(uri + "/" + filePath);
{% endcodeblock %}