---
title: 'Create a Folder with SharePoint 2010 via SOAP Web Services - UpdateListItems'
author: admin
layout: post
permalink: 
  /2011/10/11/create-a-folder-with-sharepoint-2010-via-soap-web-services-updatelistitems/
categories:
  - Microsoft / CRM / SharePoint / SSRS
---
# 

Here’s a call to SharePoint 2010 for creating a folder. Note the RootFolder.

    // Build the CAML Query
    System.Text.StringBuilder oSb = new System.Text.StringBuilder();
    oSb.Append("     ");
    oSb.Append("         ");
    oSb.Append("             New ");
    oSb.Append("             1 "); // 1 = folder, 0 = document
    oSb.Append("             "   folderName   " ");
    oSb.Append("        ");
    oSb.Append("    ");
    
    string sResult = oSb.ToString();
    XmlDocument CAMLqueryXML = new XmlDocument();
    CAMLqueryXML.LoadXml(sResult);
    
    // Execute UpdateListItems
    System.Xml.XmlNode result = lists.UpdateListItems(SPLibraryName, CAMLqueryXML);