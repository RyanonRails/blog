---
title: 'Retrieve document ID from SharePoint 2010 via SOAP Web Services  - GetListItems'
author: admin
layout: post
permalink: 
  /2011/08/30/retrieve-document-id-from-sharepoint-2010-via-soap-web-services-getlistitems/
categories:
  - Microsoft / CRM / SharePoint / SSRS
---


Get a specific item from a SharePoint 2010 library using GetListItems.

    // Build the CAML Query
    System.Text.StringBuilder oSb = new System.Text.StringBuilder();
    oSb.Append("     ");
    oSb.Append("         ");
    oSb.Append("             ");
    oSb.Append("                  ");
    oSb.Append("                  "   fileName  "");
    oSb.Append("             ");
    oSb.Append("        ");
    oSb.Append("    ");
    
    string sResult = oSb.ToString();
    XmlDocument CAMLqueryXML = new XmlDocument();
    CAMLqueryXML.LoadXml(sResult);
    
    //Build the CAML Query Options
    oSb.Clear(); // Clear the string builder
    oSb.Append("    ");
    oSb.Append("         "   libraryName   "/ />");
    oSb.Append("    ");
    string CAMLqueryOptions = oSb.ToString();
    
    XmlDocument CAMLqueryOptionsXML = new XmlDocument();
    CAMLqueryOptionsXML.LoadXml(CAMLqueryOptions);
    
    // Execute GetListItems
    XmlNode queryResults = lists.GetListItems(libraryName, null, CAMLqueryXML, null, null, CAMLqueryOptionsXML, null);