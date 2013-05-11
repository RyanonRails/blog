---
title: 'Delete document from SharePoint 2010 via SOAP Web Services  - UpdateListItems'
author: admin
layout: post
permalink: 
  /2011/08/30/delete-document-from-sharepoint-2010-via-soap-web-services-updatelistitems/
categories:
  - Microsoft / CRM / SharePoint / SSRS
---


Delete a document from SharePoint 2010. You NEED both the ID and the FileRef.

    // Delete the sharepoint document
    System.Text.StringBuilder oSb = new System.Text.StringBuilder();
    oSb.Append("      ");
    oSb.Append("          ");
    oSb.Append("             "   fileID   " ");
    oSb.Append("             "   URLofFile   " ");
    oSb.Append("        ");
    oSb.Append("    ");
    
    string sResult = oSb.ToString();
    XmlDocument CAMLqueryXML = new XmlDocument();
    CAMLqueryXML.LoadXml(sResult);
    
    // Execute GetListItems
    XmlNode queryResults = lists.UpdateListItems(SPLibraryName, CAMLqueryXML);