---
title: "메뉴 및 리소스(OLE) | Microsoft Docs"
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
  - "응용 프로그램[OLE], 메뉴 및 리소스"
  - "컨테이너[C++], OLE 컨테이너 응용 프로그램"
  - "내부 활성화, OLE 메뉴 및 리소스"
  - "메뉴[C++], OLE 문서 응용 프로그램"
  - "OLE 응용 프로그램[C++], 메뉴 및 리소스"
  - "OLE 컨테이너, 메뉴 및 리소스"
  - "OLE 메뉴 및 리소스"
  - "OLE 서버 응용 프로그램, 메뉴 및 리소스"
  - "OLE 비주얼 편집 서버"
  - "서버 응용 프로그램, OLE 메뉴 및 리소스"
  - "상태 표시줄, OLE 문서 응용 프로그램"
  - "문자열 편집, 비주얼 편집 응용 프로그램"
  - "문자열 테이블, 비주얼 편집 응용 프로그램"
  - "도구 모음[C++], OLE 문서 응용 프로그램"
  - "비주얼 편집, 응용 프로그램 메뉴 및 리소스"
ms.assetid: 52bfa086-7d3d-466f-94c7-c7061f3bdb3a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 메뉴 및 리소스(OLE)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This group of articles explains the use of menus and resources in MFC OLE document applications.  
  
 OLE visual editing places additional requirements on the menu and other resources provided by OLE document applications because there are a number of modes in which both container and server \(component\) applications can be started and used.  For example, a full\-server application can run in any of these three modes:  
  
-   Stand alone.  
  
-   In place, for editing an item within the context of a container.  
  
-   Open, for editing an item outside the context of its container, often in a separate window.  
  
 This requires three separate menu layouts, one for each possible mode of the application.  Accelerator tables are also necessary for each new mode.  A container application may or may not support in\-place activation; if it does, it needs a new menu structure and associated accelerator tables.  
  
 In\-place activation requires that the container and server applications must negotiate for menu, toolbar, and status bar space.  All resources must be designed with this in mind.  The article [Menus and Resources: Menu Merging](../mfc/menus-and-resources-menu-merging.md) covers this topic in detail.  
  
 Because of these issues, OLE document applications created with the application wizard can have up to four separate menus and accelerator table resources.  These are used for the following reasons:  
  
|리소스 이름|기능|  
|------------|--------|  
|**IDR\_MAINFRAME**|Used in an MDI application if no file is open, or in an SDI application regardless of open files.  This is the standard menu used in non\-OLE applications.|  
|**IDR\_\<project\>TYPE**|Used in an MDI application if files are open.  Used when an application is running stand\-alone.  This is the standard menu used in non\-OLE applications.|  
|**IDR\_\<project\>TYPE\_SRVR\_IP**|Used by the server or container when an object is open in place.|  
|**IDR\_\<project\>TYPE\_SRVR\_EMB**|Used by a server application if an object is opened without using in\-place activation.|  
  
 Each of these resource names represents a menu and, usually, an accelerator table.  A similar scheme should be used in MFC applications that are not created with the application wizard.  
  
 The following articles discuss topics related to containers, servers, and the menu merging necessary to implement in\-place activation:  
  
-   [Menus and Resources: Container Additions](../mfc/menus-and-resources-container-additions.md)  
  
-   [Menus and Resources: Server Additions](../mfc/menus-and-resources-server-additions.md)  
  
-   [Menus and Resources: Menu Merging](../mfc/menus-and-resources-menu-merging.md)  
  
## 참고 항목  
 [OLE](../mfc/ole-in-mfc.md)