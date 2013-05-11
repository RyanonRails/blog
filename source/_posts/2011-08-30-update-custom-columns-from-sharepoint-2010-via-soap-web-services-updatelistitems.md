---
title: 'Update Custom Columns from SharePoint 2010 via SOAP Web Services  - UpdateListItems'
author: admin
layout: post
permalink: 
  /2011/08/30/update-custom-columns-from-sharepoint-2010-via-soap-web-services-updatelistitems/
categories:
  - Microsoft / CRM / SharePoint / SSRS
---


Here’s a query to update a file’s custom columns in SharePoint 2010.

    // Build the CAML Query
    System.Text.StringBuilder oSb = new System.Text.StringBuilder();
    oSb.Append("     ");
    oSb.Append("         ");
    oSb.Append("             "   fileID   " ");
    oSb.Append("             "   customColumnText   " ");
    oSb.Append("             "   test123Text  " ");
    oSb.Append("        ");
    oSb.Append("    ");
    
    string sResult = oSb.ToString();
    XmlDocument CAMLqueryXML = new XmlDocument();
    CAMLqueryXML.LoadXml(sResult);
    
    // Execute UpdateListItems
    System.Xml.XmlNode result = lists.UpdateListItems(libraryName, CAMLqueryXML);