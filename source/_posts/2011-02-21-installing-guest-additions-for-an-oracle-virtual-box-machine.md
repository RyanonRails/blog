---
title: Installing Guest Additions for an Oracle Virtual Box Machine
author: admin
layout: post
permalink: /2011/02/21/installing-guest-additions-for-an-oracle-virtual-box-machine/
categories:
  - Microsoft / CRM / SharePoint / SSRS
---


One of the more annoying things is that you constantly have to hit “CTRL” to exit your mouse out of the virtual machine. We can fix that by installing the Guest Additions provided by Virtual Box. The Additions are built directly into the image.

Click Devices -> Install Guest Additions

![][2]

 [2]: /images/old/VB_Guest_Menu.png

![][3]

 [3]: /images/old/VB_Guest_Run.png

Click Run VBoxWindowsAdditions.exe

Once the Oracle VM VirtualBox Guest Additions Setup Wizard opens, click Next all the way through, and click install when it asks you to. Then Reboot.