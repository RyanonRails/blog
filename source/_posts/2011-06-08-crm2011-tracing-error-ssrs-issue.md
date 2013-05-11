---
title: 'CRM2011 Tracing Error - SSRS Issue'
author: admin
layout: post
permalink: /2011/06/08/crm2011-tracing-error-ssrs-issue/
categories:
  - Microsoft / CRM / SharePoint / SSRS
---


I was getting this System.Security.SecurityException because my SSRS datasource settings were incorrect:

    Unhandled Exception: System.ServiceModel.FaultException`1[[Microsoft.Xrm.Sdk.OrganizationServiceFault, 
    Microsoft.Xrm.Sdk, Version=5.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]: 
    System.Security.SecurityException: Microsoft Dynamics CRM has experienced an error. Reference number for 
    administrators or support: #84ED43B9Detail: 
    
      -2147220970
      
      System.Security.SecurityException: Microsoft Dynamics CRM has experienced an error. Reference number for administrators or support: #84ED43B9
      2011-05-16T16:55:39.4637893Z
      
      
    
    [: Plugins.]
    [d6afc2c3-717a-e011-9afc-00155d036888: Plugins.: Update of ]
    
    
    
    

Hope this helps,  
Ry