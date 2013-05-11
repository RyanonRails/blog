---
title: Check in a file into SharePoint 2010 via SOAP Web Services – CheckInFile
author: admin
layout: post
permalink: 
  /2011/08/30/check-in-a-file-into-sharepoint-2010-via-soap-web-services-checkinfile/
categories:
  - Microsoft / CRM / SharePoint / SSRS
---


Checking in a a file into Sharepoint using Lists.asmx.
{% codeblock lang:csharp %}
// Check the file in to sharepoint
lists.CheckInFile(destinationUrl, "Text for the checkin", "1");
{% endcodeblock %}
A string representation of the values 0, 1 or 2, where 0 = MinorCheckIn, 1 = MajorCheckIn, and 2 = OverwriteCheckIn.