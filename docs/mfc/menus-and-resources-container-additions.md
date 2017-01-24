---
title: "메뉴 및 리소스: 컨테이너 추가 | Microsoft Docs"
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
  - "IDP_OLE_INIT_FAILED"
  - "IDP_FAILED_TO_CREATE"
  - "VK_ESCAPE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "액셀러레이터 키 테이블[C++], 컨테이너 응용 프로그램"
  - "응용 프로그램 엑셀러레이터 키 테이블[C++]"
  - "자습서 포함"
  - "IDP_FAILED_TO_CREATE 매크로"
  - "IDP_OLE_INIT_FAILED 매크로"
  - "링크 메뉴 항목"
  - "OLE 컨테이너, 메뉴 및 리소스"
  - "비주얼 편집, 응용 프로그램 메뉴 및 리소스"
  - "VK_ESCAPE 키"
ms.assetid: 425448be-8ca0-412e-909a-a3a9ce845288
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 메뉴 및 리소스: 컨테이너 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article explains the changes that need to be made to the menus and other resources in a visual editing container application.  
  
 In container applications, two types of changes need to be made: modifications to existing resources to support OLE visual editing and addition of new resources used for in\-place activation.  If you use the application wizard to create your container application, these steps will be done for you, but they may require some customization.  
  
 If you do not use the application wizard, you may want to look at OCLIENT.RC, the resource script for the OCLIENT sample application, to see how these changes are implemented.  See the MFC OLE sample [OCLIENT](../top/visual-cpp-samples.md).  
  
 Topics covered in this article include:  
  
-   [Container Menu Additions](#_core_container_menu_additions)  
  
-   [Accelerator Table Additions](#_core_container_application_accelerator_table_additions)  
  
-   [String Table Additions](#_core_string_table_additions_for_container_applications)  
  
##  <a name="_core_container_menu_additions"></a> Container Menu Additions  
 You must add the following items to the Edit menu:  
  
|항목|용도|  
|--------|--------|  
|**Insert New Object**|Opens the OLE Insert Object dialog box to insert a linked or embedded item into the document.|  
|**Paste Link**|Pastes a link to the item on the Clipboard into the document.|  
|**OLE Verb**|Calls the selected item's primary verb.  The text of this menu item changes to reflect the primary verb of the selected item.|  
|**링크**|Opens the OLE Edit Links dialog box to change existing linked items.|  
  
 In addition to the changes listed in this article, your source file must include AFXOLECL.RC, which is required for the Microsoft Foundation Class Library implementation.  Insert New Object is the only required menu addition.  Other items can be added, but those listed here are the most common.  
  
 You must create a new menu for your container application if you want to support in\-place activation of contained items.  This menu consists of the same File menu and Window pop\-up menus used when files are open, but it has two separators placed between them.  These separators are used to indicate where the server \(component\) item \(application\) should place its menus when activated in place.  For more information on this menu\-merging technique, see [Menus and Resources: Menu Merging](../mfc/menus-and-resources-menu-merging.md).  
  
##  <a name="_core_container_application_accelerator_table_additions"></a> Container Application Accelerator Table Additions  
 Small changes to a container application's accelerator table resources are necessary if you are supporting in\-place activation.  The first change allows the user to press the escape key \(ESC\) to cancel the in\-place editing mode.  Add the following entry to the main accelerator table:  
  
|ID|Key|형식|  
|--------|---------|--------|  
|**ID\_CANCEL\_EDIT\_CNTR**|VK\_ESCAPE|**VIRTKEY**|  
  
 The second change is to create a new accelerator table that corresponds to the new menu resource created for in\-place activation.  This table has entries for the File and Window menus in addition to the **VK\_ESCAPE** entry above.  The following example is the accelerator table created for in\-place activation in the MFC sample [CONTAINER](../top/visual-cpp-samples.md):  
  
|ID|Key|형식|  
|--------|---------|--------|  
|`ID_FILE_NEW`|Ctrl\+N|**VIRTKEY**|  
|`ID_FILE_OPEN`|Ctrl\+O|**VIRTKEY**|  
|**ID\_FILE\_SAVE**|Ctrl\+S|**VIRTKEY**|  
|**ID\_FILE\_PRINT**|Ctrl\+P|**VIRTKEY**|  
|**ID\_NEXT\_PANE**|VK\_F6|**VIRTKEY**|  
|**ID\_PREV\_PANE**|SHIFT\+VK\_F6|**VIRTKEY**|  
|**ID\_CANCEL\_EDIT\_CNTR**|VK\_ESCAPE|**VIRTKEY**|  
  
##  <a name="_core_string_table_additions_for_container_applications"></a> String Table Additions for Container Applications  
 Most of the changes to string tables for container applications correspond to the additional menu items mentioned in [Container Menu Additions](#_core_container_menu_additions).  They supply the text displayed in the status bar when each menu item is displayed.  As an example, here are the string\-table entries the application wizard generates:  
  
|ID|String|  
|--------|------------|  
|**IDP\_OLE\_INIT\_FAILED**|OLE를 초기화할 수 없습니다.  OLE 라이브러리 버전이 올바른지 확인하십시오.|  
|**IDP\_FAILED\_TO\_CREATE**|개체를 만들지 못했습니다.  Make sure that the object is entered in the system registry.|  
  
## 참고 항목  
 [메뉴 및 리소스\(OLE\)](../mfc/menus-and-resources-ole.md)   
 [메뉴 및 리소스: 서버 추가](../mfc/menus-and-resources-server-additions.md)