---
title: "InitInstance 멤버 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "InitInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램[MFC], 초기화"
  - "MFC 응용 프로그램 초기화"
  - "InitInstance 메서드"
  - "MFC[C++], 초기화"
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# InitInstance 멤버 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The Windows operating system allows you to run more than one copy, or "instance," of the same application.  `WinMain` calls [InitInstance](../Topic/CWinApp::InitInstance.md) every time a new instance of the application starts.  
  
 The standard `InitInstance` implementation created by the MFC Application Wizard performs the following tasks:  
  
-   As its central action, creates the document templates that in turn create documents, views, and frame windows.  For a description of this process, see [Document Template Creation](../mfc/document-template-creation.md).  
  
-   Loads standard file options from an .ini file or the Windows registry, including the names of the most recently used files.  
  
-   Registers one or more document templates.  
  
-   For an MDI application, creates a main frame window.  
  
-   Processes the command line to open a document specified on the command line or to open a new, empty document.  
  
 You can add your own initialization code or modify the code written by the wizard.  
  
> [!NOTE]
>  MFC 응용 프로그램은 단일 스레드 아파트먼트 \(STA\)로 초기화 되어야 합니다.  `InitInstance`를 재정의하여 [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279)를 호출하는 경우, `COINIT_APARTMENTTHREADED` \(`COINIT_MULTITHREADED` 보다는\) 를 지정하십시오.  자세한 내용은 PRB: 다중 스레드 아파트먼트로 응용 프로그램을 초기화할 때 MFC 응용 프로그램이 멈춤 \(828643\) [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;828643](http://support.microsoft.com/default.aspx?scid=kb;en-us;828643)를 참조하십시오.  
  
## 참고 항목  
 [CWinApp: 응용 프로그램 클래스](../mfc/cwinapp-the-application-class.md)