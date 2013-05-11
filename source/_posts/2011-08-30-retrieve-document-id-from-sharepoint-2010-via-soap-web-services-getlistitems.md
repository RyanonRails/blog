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
{% codeblock lang:csharp %}
// Build the CAML Query
System.Text.StringBuilder oSb = new System.Text.StringBuilder();
oSb.Append("     <Query>");
oSb.Append("         <Where>");
oSb.Append("             <Eq>");
oSb.Append("                  <FieldRef Name=\"FileLeafRef\" />");
oSb.Append("                  <Value Type=\"Text\">" + fileName +"</Value>");
oSb.Append("             </Eq>");
oSb.Append("        </Where>");
oSb.Append("    </Query>");
 
string sResult = oSb.ToString();
XmlDocument CAMLqueryXML = new XmlDocument();
CAMLqueryXML.LoadXml(sResult);
 
//Build the CAML Query Options
oSb.Clear(); // Clear the string builder
oSb.Append("    <QueryOptions>");
oSb.Append("         <Folder>" + libraryName + "/</Folder> />");
oSb.Append("    </QueryOptions>");
string CAMLqueryOptions = oSb.ToString();
 
XmlDocument CAMLqueryOptionsXML = new XmlDocument();
CAMLqueryOptionsXML.LoadXml(CAMLqueryOptions);
 
// Execute GetListItems
XmlNode queryResults = lists.GetListItems(libraryName, null, CAMLqueryXML, null, null, CAMLqueryOptionsXML, null);
{% endcodeblock %}