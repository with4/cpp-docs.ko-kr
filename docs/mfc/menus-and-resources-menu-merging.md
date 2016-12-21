---
title: "메뉴 및 리소스: 메뉴 병합 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "메뉴 레이아웃 조정"
  - "메뉴[C++], OLE 문서 응용 프로그램"
  - "도구 모음 및 상태 표시줄 병합"
  - "OLE 컨테이너, 메뉴 및 리소스"
  - "상태 표시줄, OLE 문서 응용 프로그램"
  - "도구 모음[C++], OLE 문서 응용 프로그램"
  - "비주얼 편집, 응용 프로그램 메뉴 및 리소스"
ms.assetid: 80b6bb17-d830-4122-83f0-651fc112d4d1
caps.latest.revision: 9
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 메뉴 및 리소스: 메뉴 병합
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article details the steps necessary for OLE document applications to handle visual editing and in\-place activation properly.  In\-place activation poses a challenge for both container and server \(component\) applications.  The user remains in the same frame window \(within the context of the container document\) but is actually running another application \(the server\).  This requires coordination between the resources of the container and server applications.  
  
 Topics covered in this article include:  
  
-   [Menu Layouts](#_core_menu_layouts)  
  
-   [Toolbars and Status Bars](#_core_toolbars_and_status_bars)  
  
##  <a name="_core_menu_layouts"></a> Menu Layouts  
 The first step is to coordinate menu layouts.  For more information, see the **Menu Creation** section in [Menu Programming Considerations](https://msdn.microsoft.com/en-us/library/ms647557.aspx) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Container applications should create a new menu to be used only when embedded items are activated in place.  At the minimum, this menu should consist of the following, in the order listed:  
  
1.  File menu identical to the one used when files are open. \(Usually no other menu items are placed before the next item.\)  
  
2.  Two consecutive separators.  
  
3.  Window menu identical to the one used when files are open \(only if the container application in an MDI application\).  Some applications may have other menus, such as an Options menu, that belong in this group, which remains on the menu when an embedded item is activated in place.  
  
    > [!NOTE]
    >  There may be other menus that affect the view of the container document, such as Zoom.  These container menus appear between the two separators in this menu resource.  
  
 Server \(component\) applications should also create a new menu specifically for in\-place activation.  It should be like the menu used when files are open, but without menu items, such as File and Window that manipulate the server document instead of the data.  Typically, this menu consists of the following:  
  
1.  Edit menu identical to the one used when files are open.  
  
2.  Separator.  
  
3.  Object editing menus, such as the Pen menu in the Scribble sample application.  
  
4.  Separator.  
  
5.  Help menu.  
  
 For an example, look at the layout of some sample in\-place menus for a container and a server.  The details of each menu item have been removed to make the example clearer.  The container's in\-place menu has the following entries:  
  
```  
IDR_CONTAINERTYPE_CNTR_IP MENU PRELOAD DISCARDABLE   
BEGIN  
    POPUP "&File C1"  
    MENUITEM SEPARATOR  
    POPUP "&Zoom C2"  
    MENUITEM SEPARATOR  
    POPUP "&Options C3"  
    POPUP "&Window C3"  
END  
```  
  
 The consecutive separators indicate where the first part of the server's menu should go.  Now look at the server's in\-place menu:  
  
```  
IDR_SERVERTYPE_SRVR_IP MENU PRELOAD DISCARDABLE   
BEGIN  
    POPUP "&Edit S1"  
    MENUITEM SEPARATOR  
    POPUP "&Format S2"  
    MENUITEM SEPARATOR  
    POPUP "&Help S3"  
END  
```  
  
 The separators here indicate where the second group of container menu items should go.  The resulting menu structure when an object from this server is activated in place inside this container looks like this:  
  
```  
BEGIN  
    POPUP "&File C1"  
    POPUP "&Edit S1"  
    POPUP "&Zoom C2"  
    POPUP "&Format S2"  
    POPUP "&Options C3  
    POPUP "&Window C3"  
    POPUP "&Help S3"  
END  
```  
  
 As you can see, the separators have been replaced with the different groups of each application's menu.  
  
 Accelerator tables associated with the in\-place menu should also be supplied by the server application.  The container will incorporate them into its own accelerator tables.  
  
 When an embedded item is activated in place, the framework loads the in\-place menu.  It then asks the server application for its menu for in\-place activation and inserts it where the separators are.  This is how the menus combine.  You get menus from the container for operating on the file and window placement, and you get menus from the server for operating on the item.  
  
##  <a name="_core_toolbars_and_status_bars"></a> Toolbars and Status Bars  
 Server applications should create a new toolbar and store its bitmap in a separate file.  The application wizard–generated applications store this bitmap in a file called ITOOLBAR.BMP.  The new toolbar replaces the container application's toolbar when your server's item is activated in place, and should contain the same items as your normal toolbar, but remove icons representing items on the File and Window menus.  
  
 This toolbar is loaded in your `COleIPFrameWnd`\-derived class, created for you by the application wizard.  The status bar is handled by the container application.  For more information on the implementation of in\-place frame windows, see [Servers: Implementing a Server](../mfc/servers-implementing-a-server.md).  
  
## 참고 항목  
 [메뉴 및 리소스\(OLE\)](../mfc/menus-and-resources-ole.md)   
 [활성화](../mfc/activation-cpp.md)   
 [서버](../mfc/servers.md)   
 [컨테이너](../mfc/containers.md)