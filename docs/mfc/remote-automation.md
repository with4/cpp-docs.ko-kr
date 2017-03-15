---
title: "원격 자동화 | Microsoft Docs"
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
  - "자동화 컨트롤러"
  - "자동화 개체"
  - "자동화 개체, 만들기"
  - "COM, 원격 자동화"
  - "DCOM, 원격 자동화"
  - "MFC COM, 원격 자동화"
  - "MFC, COM 지원"
  - "원격 자동화"
ms.assetid: 363f87fb-08fa-4458-b089-b46365a6d4f2
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 원격 자동화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  It is recommended that Visual C\+\+ .NET developers use DCOM rather than Remote Automation for new applications.  Visual C\+\+ .NET does not support Windows 95.  Cases in which you would need to support Remote Automation are described in [Where Does Remote Automation Fit In?](../mfc/where-does-remote-automation-fit-in-q.md).  
  
 Remote Automation is a type of [Automation](../mfc/automation.md) that allows an interface consumer to execute an interface provider that resides on another machine, for example, on a network.  
  
 This article explains how to create Automation objects that can be invoked and executed remotely, and how to create Automation controllers that can use these Remote Automation objects.  It also examines configuration options and points out the major differences between Remote Automation and DCOM \(the distributed version of COM and OLE that allows interfaces other than those related to automation to be invoked and executed remotely\).  
  
## 단원 내용  
 [History of DCOM \(Distributed Component Object Model\)](../mfc/history-of-dcom.md)  
  
 [Where Does Remote Automation Fit In?](../mfc/where-does-remote-automation-fit-in-q.md)  
  
 [What Does Remote Automation Provide?](../mfc/what-does-remote-automation-provide-q.md)  
  
 [Remote Automation Security](../mfc/security-in-remote-automation.md)  
  
 [Threading Models](../mfc/remote-automation-threading-models.md)  
  
 [설치](../mfc/remote-automation-installation.md)  
  
 [The Automation Manager](../mfc/automation-manager-mfc.md)  
  
-   [The Remote Automation Connection Manager](../mfc/remote-automation-connection-manager.md)  
  
-   [Remote Automation User Components](../mfc/remote-automation-user-components.md)  
  
 [Creating Programs That Use Remote Automation](../mfc/creating-programs-that-use-remote-automation.md)  
  
 [Running Remote Automation Using AUTOCLIK and AUTODRIV](../mfc/running-remote-automation-using-autoclik-and-autodriv.md)  
  
## 참고 항목  
 [MFC COM](../mfc/mfc-com.md)   
 [자동화](../mfc/automation.md)