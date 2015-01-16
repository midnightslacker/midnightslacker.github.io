---
layout:post
title:Google discloses 3rd Microsoft "Zero Day" 
date:2015-01-16
categories: infosec
---

<img src="/pix/GvsM.png" align="center" width="500" height="300">

Google has discovered yet another bug in Microsoft's Windows Operating System. If you haven't been paying attention, get caught up [here.][zdnet]
This time, the bug was found in CryptProtectMemory function found in Windows 7 and Windows 8.1.

The bug was found by James Forshaw, the same security researcher who discovered a privilege escalation flaw in Windows 8.1 that was disclosed a few days prior to Microsoft's 'Patch Tuesday'.

Here is a description of the bug by Forshaw

*When using the logon session option (CRYPTPROTECTMEMORY_SAME_LOGON flag), the encryption key is generated based on the logon session identifier, this is for sharing memory between processes running within the same logon. As this might also be used for sending data from one process to another, it supports extracting the logon session ID from the impersonation token." The issue is the implementation in CNG.sys doesn't check the impersonation level of the token when capturing the logon sessionID (using SeQueryAuthenticationIdToken) so a normal user can impersonate at Identification level and decrypt or encrypt data for that logon session.*

Microsoft is less then pleased, [to say the least][msoft]
Wonder if the folks over in Redmond will buy a few Chromebooks to "return the favor."

[msoft]: http://blogs.technet.com/b/msrc/archive/2015/01/11/a-call-for-better-coordinated-vulnerability-disclosure.aspx
[zdnet]: http://www.zdnet.com/article/microsoft-slams-google-for-spilling-the-beans-on-windows-8-1-security-flaw/
