---
title: "원격 자동화가 필요한 경우 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "원격 자동화, DCOM"
ms.assetid: 4c4c8176-cfc0-44f7-bc87-b690f069ad2f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 원격 자동화가 필요한 경우
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DCOM was released in 1996 and is available with 32\-bit and 64\-bit platforms only.  The Visual Basic team at Microsoft has always seen Visual Basic as using Automation to allow its components to communicate.  The lack of a distributed version severely limited the use of these capabilities in enterprise environments, so the team developing Visual Basic 4.0 Enterprise Edition decided to investigate the creation of its own set of remoting components for the Automation parts of OLE and COM.  Clearly, a major goal was to ensure that the result would be compatible with and could be replaced by DCOM when it became available.  They then proceeded to implement Remote Automation \(RA\) for both 16\-bit and 32\-bit Windows platforms.  
  
 Remote Automation is not tied to any specific language, but until the release of Visual C\+\+ 4.2 Enterprise Edition, it was shipped only with Visual Basic 4.0.  Be aware that Remote Automation is wholly subsumed by DCOM.  If you have the opportunity to use DCOM instead of Remote Automation in your applications, you should do so.  Nevertheless, there are scenarios where Remote Automation is more appropriate:  
  
-   Wherever you have 16\-bit clients.  
  
-   If your organization has not rolled out a DCOM\-enabled version of Windows NT or Windows 95 yet.  
  
-   If you are upgrading an existing application suite that uses Remote Automation to use C\+\+ components in place of one or more Visual Basic components.  
  
 There need be no difference between programs created to use Remote Automation and those created to use Automation over DCOM, and the configuration utilities make it very simple to switch operation between Remote Automation and DCOM.  Consequently, it is not difficult to upgrade an application from Remote Automation to DCOM once the infrastructure is in place.  
  
## 참고 항목  
 [원격 자동화의 기능은 무엇입니까?](../mfc/what-does-remote-automation-provide-q.md)   
 [DCOM의 역사](../mfc/history-of-dcom.md)