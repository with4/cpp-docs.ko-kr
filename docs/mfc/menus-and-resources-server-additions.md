---
title: "메뉴 및 리소스: 서버 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDP_OLE_INIT_FAILED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "액셀러레이터 키 테이블[C++], 서버 응용 프로그램"
  - "IDP_OLE_INIT_FAILED 매크로"
  - "OLE 초기화 오류"
  - "OLE 서버 응용 프로그램, 메뉴 및 리소스"
  - "OLE 비주얼 편집 서버"
  - "리소스[MFC], 서버 응용 프로그램"
  - "서버 응용 프로그램, 액셀러레이터 키 테이블"
  - "서버 응용 프로그램, OLE 메뉴 및 리소스"
  - "서버, 메뉴 추가"
  - "문자열 편집, 비주얼 편집 응용 프로그램"
  - "문자열 테이블, 비주얼 편집 응용 프로그램"
  - "비주얼 편집, 응용 프로그램 메뉴 및 리소스"
ms.assetid: 56ce9e8d-8f41-4db8-8dee-e8b0702d057c
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 메뉴 및 리소스: 서버 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article explains the changes that need to be made to the menus and other resources in a visual editing server \(component\) application.  A server application requires many additions to the menu structure and other resources because it can be started in one of three modes: stand alone, embedded, or in place.  As described in the [Menus and Resources \(OLE\)](../mfc/menus-and-resources-ole.md) article, there are a maximum of four sets of menus.  All four are used for an MDI full\-server application, while only three are used for a miniserver.  The application wizard will create the menu layout necessary for the type of server you want.  Some customization may be necessary.  
  
 If you do not use the application wizard, you may want to look at HIERSVR.RC, the resource script for the MFC sample application [HIERSVR](../top/visual-cpp-samples.md), to see how these changes are implemented.  
  
 Topics covered in this article include:  
  
-   [Server Menu Additions](#_core_server_menu_additions)  
  
-   [Accelerator Table Additions](#_core_server_application_accelerator_table_additions)  
  
-   [String Table Additions](../mfc/menus-and-resources-container-additions.md)  
  
-   [Miniserver Additions](#_core_mini.2d.server_additions)  
  
##  <a name="_core_server_menu_additions"></a> Server Menu Additions  
 Server \(component\) applications must have menu resources added to support OLE visual editing.  The menus used when the application is run in stand\-alone mode do not have to be changed, but you must add two new menu resources before building the application: one to support in\-place activation and one to support the server being fully open.  Both menu resources are used by full\- and miniserver applications.  
  
-   To support in\-place activation, you must create a menu resource that is very similar to the menu resource used when run in stand\-alone mode.  The difference in this menu is that the File and Window items \(and any other menu items that deal with the application, and not the data\) are missing.  The container application will supply these menu items.  For more information on, and an example of, this menu\-merging technique, see the article [Menus and Resources: Menu Merging](../mfc/menus-and-resources-menu-merging.md).  
  
-   To support fully open activation, you must create a menu resource nearly identical to the menu resource used when run in stand\-alone mode.  The only modification to this menu resource is that some items are reworded to reflect the fact that the server is operating on an item embedded in a compound document.  
  
 In addition to the changes listed in this article, your resource file needs to include AFXOLESV.RC, which is required for the Microsoft Foundation Class Library implementation.  This file is in the MFC\\Include subdirectory.  
  
##  <a name="_core_server_application_accelerator_table_additions"></a> Server Application Accelerator Table Additions  
 Two new accelerator table resources must be added to server applications; they correspond directly to the new menu resources previously described.  The first accelerator table is used when the server application is activated in place.  It consists of all the entries in the view's accelerator table except those tied to the File and Window menus.  
  
 The second table is nearly an exact copy of the view's accelerator table.  Any differences parallel changes made in the fully open menu mentioned in [Server Menu Additions](#_core_server_menu_additions).  
  
 For an example of these accelerator table changes, compare the **IDR\_HIERSVRTYPE\_SRVR\_IP** and **IDR\_HIERSVRTYPE\_SRVR\_EMB** accelerator tables with **IDR\_MAINFRAME** in the HIERSVR.RC file included in the MFC OLE sample [HIERSVR](../top/visual-cpp-samples.md).  The File and Window accelerators are missing from the in\-place table and exact copies of them are in the embedded table.  
  
##  <a name="_core_string_table_additions_for_server_applications"></a> String Table Additions for Server Applications  
 Only one string table addition is necessary in a server application — a string to signify that the OLE initialization failed.  As an example, here is the string\-table entry that the application wizard generates:  
  
|ID|String|  
|--------|------------|  
|**IDP\_OLE\_INIT\_FAILED**|OLE를 초기화할 수 없습니다.  OLE 라이브러리 버전이 올바른지 확인하십시오.|  
  
##  <a name="_core_mini.2d.server_additions"></a> Miniserver Additions  
 The same additions apply for miniservers as those listed above for full\-servers.  Because a miniserver cannot be run in stand\-alone mode, its main menu is much smaller.  The main menu created by the application wizard has only a File menu, containing only the items Exit and About.  Embedded and in\-place menus and accelerators for miniservers are the same as those for full\-servers.  
  
## 참고 항목  
 [메뉴 및 리소스\(OLE\)](../mfc/menus-and-resources-ole.md)   
 [메뉴 및 리소스: 메뉴 병합](../mfc/menus-and-resources-menu-merging.md)