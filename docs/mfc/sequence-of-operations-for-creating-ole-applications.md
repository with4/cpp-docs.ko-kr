---
title: "OLE 응용 프로그램을 만드는 작업 시퀀스 | Microsoft Docs"
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
  - "응용 프로그램[OLE]"
  - "응용 프로그램[OLE], 만들기"
  - "OLE 응용 프로그램[C++]"
  - "OLE 응용 프로그램[C++], 만들기"
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE 응용 프로그램을 만드는 작업 시퀀스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The following table shows your role and the framework's role in creating OLE linking and embedding applications.  These represent options available rather than a sequence of steps to perform.  
  
### Creating OLE Applications  
  
|Task|You do|The framework does|  
|----------|------------|------------------------|  
|Create a COM component.|Run the MFC Application Wizard.  Choose **Full\-server** or **Mini\-server** in the **Compound Document Support** tab.|The framework generates a skeleton application with COM component capability enabled.  All of the COM capability can be transferred to your existing application with only slight modification.|  
|Create a container application from scratch.|Run the MFC Application Wizard.  Choose **Container** in the **Compound Document Support** tab.  Using Class View, go to the source code editor.  Fill in code for your COM handler functions.|The framework generates a skeleton application that can insert COM objects created by COM component \(server\) applications.|  
|Create an application that supports Automation from scratch.|Run the MFC Application Wizard.  Choose **Automation** from the **Advanced Features** tab.  Use Class View to expose methods and properties in your application for automation.|The framework generates a skeleton application that can be activated and automated by other applications.|  
  
## 참고 항목  
 [프레임워크를 기반으로 구축](../mfc/building-on-the-framework.md)   
 [MFC 응용 프로그램을 빌드하는 작업 시퀀스](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [ActiveX 컨트롤을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-activex-controls.md)   
 [데이터베이스 응용 프로그램을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-database-applications.md)