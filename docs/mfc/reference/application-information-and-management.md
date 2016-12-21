---
title: "응용 프로그램 정보 및 관리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램[MFC], 관리"
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
caps.latest.revision: 17
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 응용 프로그램 정보 및 관리
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

When you write an application, you create a single [CWinApp](../../mfc/reference/cwinapp-class.md)\-derived object.  At times, you may want to get information about this object from outside the `CWinApp`\-derived object.  
  
 The Microsoft Foundation Class Library provides the following global functions to help you accomplish these tasks:  
  
### Application Information and Management Functions  
  
|||  
|-|-|  
|[AfxBeginThread](../Topic/AfxBeginThread.md)|Creates a new thread.|  
|[AfxEndThread](../Topic/AfxEndThread.md)|Terminates the current thread.|  
|[AfxFreeLibrary](../Topic/AfxFreeLibrary.md)|Decrements the reference count of the loaded dynamic\-link library \(DLL\) module; when the reference count reaches zero, the module is unmapped.|  
|[AfxGetApp](../Topic/AfxGetApp.md)|Returns a pointer to the application's single `CWinApp` object.|  
|[AfxGetAppName](../Topic/AfxGetAppName.md)|Returns a string that contains the application's name.|  
|[AfxGetInstanceHandle](../Topic/AfxGetInstanceHandle.md)|Returns an `HINSTANCE` representing this instance of the application.|  
|[AfxGetMainWnd](../Topic/AfxGetMainWnd.md)|Returns a pointer to the current "main" window of a non\-OLE application, or the in\-place frame window of a server application.|  
|[AfxGetPerUserRegistration](../Topic/AfxGetPerUserRegistration.md)|Use this function to determine whether the application redirects registry access to the **HKEY\_CURRENT\_USER** \(**HKCU**\) node.|  
|[AfxGetResourceHandle](../Topic/AfxGetResourceHandle.md)|Returns an `HINSTANCE` to the source of the application's default resources.  Use this to access the application's resources directly.|  
|[AfxGetThread](../Topic/AfxGetThread.md)|Retrieves a pointer to the current [CWinThread](../../mfc/reference/cwinthread-class.md) object.|  
|[AfxInitRichEdit](../Topic/AfxInitRichEdit.md)|Initializes the version 1.0 rich edit control for the application.|  
|[AfxInitRichEdit2](../Topic/AfxInitRichEdit2.md)|Initializes the version 2.0 and later rich edit control for the application.|  
|[AfxLoadLibrary](../Topic/AfxLoadLibrary.md)|Maps a DLL module and returns a handle that can be used to obtain the address of a DLL function.|  
|[AfxRegisterClass](../Topic/AfxRegisterClass.md)|Registers a window class in a DLL that uses MFC.|  
|[AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md)|Registers a Windows window class to supplement those registered automatically by MFC.|  
|[AfxSetPerUserRegistration](../Topic/AfxSetPerUserRegistration.md)|Sets whether the application redirects registry access to the **HKEY\_CURRENT\_USER** \(**HKCU**\) node.|  
|[AfxSetResourceHandle](../Topic/AfxSetResourceHandle.md)|Sets the `HINSTANCE` handle where the default resources of the application are loaded.|  
|[AfxSocketInit](../Topic/AfxSocketInit.md)|Called in a `CWinApp::InitInstance` override to initialize Windows Sockets.|  
|[AfxWinInit](../Topic/AfxWinInit.md)|Called by the MFC\-supplied `WinMain` function, as part of the [CWinApp](../../mfc/reference/cwinapp-class.md) initialization of a GUI\-based application, to initialize MFC.  Must be called directly for console applications that use MFC.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)