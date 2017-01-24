---
title: "프레임워크(MFC) | Microsoft Docs"
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
  - "API[C++], MFC Win32에서 캡슐화"
  - "응용 프로그램 프레임워크[C++], MFC 응용 프로그램 프레임워크 정보"
  - "캡슐화된 Win32 API"
  - "캡슐화[C++]"
  - "캡슐화[C++], Win32 API"
  - "MFC[C++], 응용 프로그램 프레임워크"
  - "Win32[C++], MFC에서 API 캡슐화"
  - "Windows API[C++], MFC에서 캡슐화"
  - "래퍼 클래스, 설명됨"
ms.assetid: 3be0fec8-9843-4119-ae42-ece993ef500b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 프레임워크(MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Your work with the Microsoft Foundation Class \(MFC\) Library framework is based largely on a few major classes and several Visual C\+\+ tools.  Some classes encapsulate a large portion of the Win32 application programming interface \(API\).  Other classes encapsulate application concepts such as documents, views, and the application itself.  Still others encapsulate OLE features and ODBC and DAO data\-access functionality.  
  
 For example, Win32's concept of window is encapsulated by MFC class `CWnd`.  That is, a C\+\+ class called `CWnd` encapsulates or "wraps" the `HWND` handle that represents a Windows window.  Likewise, class `CDialog` encapsulates Win32 dialog boxes.  
  
 Encapsulation means that the C\+\+ class `CWnd`, for example, contains a member variable of type `HWND`, and the class's member functions encapsulate calls to Win32 functions that take an `HWND` as a parameter.  The class member functions typically have the same name as the Win32 function they encapsulate.  
  
## 단원 내용  
 [SDI 및 MDI](../mfc/sdi-and-mdi.md)  
  
 [Documents, Views, and the Framework](../mfc/documents-views-and-the-framework.md)  
  
 [Wizards and Resource Editors](../mfc/wizards-and-the-resource-editors.md)  
  
## In Related Sections  
 [Building on the Framework](../mfc/building-on-the-framework.md)  
  
 [How the Framework Calls Your Code](../mfc/how-the-framework-calls-your-code.md)  
  
 [CWinApp: The Application Class](../mfc/cwinapp-the-application-class.md)  
  
 [Document Templates and the Document\/View Creation Process](../mfc/document-templates-and-the-document-view-creation-process.md)  
  
 [메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)  
  
 [Window Objects](../mfc/window-objects.md)  
  
## 참고 항목  
 [클래스를 사용하여 Windows 응용 프로그램 작성](../mfc/using-the-classes-to-write-applications-for-windows.md)