---
title: "MFC 인터넷 프로그래밍 작업 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "인터넷 응용 프로그램, 시작하기 전에"
  - "인터넷 응용 프로그램, 시작"
ms.assetid: 6377e9b8-07c4-4380-b63b-05f5a9061313
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# MFC 인터넷 프로그래밍 작업
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This section contains detailed steps for adding Internet support to your applications.  Topics include how to use the MFC classes to Internet\-enable your existing applications, and how to add Active document support to your existing COM component.  Do you want to create a document with up\-to\-the\-minute stock quotes, Pittsburgh's football scores, and the latest temperature in Antarctica?  Microsoft provides a number of technologies to help you do that over the Internet.  
  
 Active technologies include ActiveX controls \(formerly OLE controls\) and Active documents; WinInet for easily retrieving and saving files across the Internet; and asynchronous monikers for efficient data downloading.  Visual C\+\+ provides wizards to help you get started quickly with a starter application.  For an introduction to these technologies, see [MFC Internet Programming Basics](../mfc/mfc-internet-programming-basics.md) and [MFC COM](../mfc/mfc-com.md).  
  
 Have you always wanted to FTP a file but haven't learned WinSock and network programming protocols?  WinInet classes encapsulate these protocols, providing you with a simple set of functions you can use to write a client application on the Internet to download files using HTTP, FTP, and gopher.  You can use WinInet to search directories on your hard drive or around the world.  You can transparently collect data of several different types, and present it to the user in an integrated interface.  
  
 Do you have large amounts of data to download?  Asynchronous monikers provide a COM \(Component Object Model\) solution for progressive rendering of large objects.  WinInet can also be used asynchronously.  
  
 The following table describes a few of the things you can do with these technologies.  
  
|You have|You want to|You should|  
|--------------|-----------------|----------------|  
|A Web server.|Track logons and detailed information about URL requests.|Write a filter, request notifications for logon events and URL mapping.|  
|A Web browser.|Provide dynamic content.|Create ActiveX controls and Active documents.|  
|A document\-based application.|Add support to FTP a file.|Use WinInet or asynchronous monikers.|  
  
 See the following topics for details to get you started:  
  
-   [Application Design Choices](../mfc/application-design-choices.md)  
  
-   [Writing MFC Applications](../mfc/writing-mfc-applications.md)  
  
-   [ActiveX Controls on the Internet](../mfc/activex-controls-on-the-internet.md)  
  
-   [Upgrading an Existing ActiveX Control](../mfc/upgrading-an-existing-activex-control.md)  
  
-   [Active Documents on the Internet](../mfc/active-documents-on-the-internet.md)  
  
-   [Asynchronous Monikers on the Internet](../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [Testing Internet Applications](../mfc/testing-internet-applications.md)  
  
-   [Internet Security](../mfc/internet-security-cpp.md)  
  
## 참고 항목  
 [MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)   
 [작업별 인터넷 정보](../mfc/internet-information-by-task.md)