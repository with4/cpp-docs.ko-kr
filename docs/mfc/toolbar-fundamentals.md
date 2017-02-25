---
title: "도구 모음 기본 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RT_TOOLBAR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램 마법사[C++], 기본 응용 프로그램 도구 모음 설치"
  - "명령 ID, 도구 모음 단추"
  - "CToolBar 클래스, 응용 프로그램 마법사의 기본 도구 모음"
  - "프레임 창 클래스에 도구 모음 포함"
  - "프레임 창 클래스, 도구 모음 포함됨"
  - "LoadBitmap 메서드, 도구 모음"
  - "LoadToolBar 메서드"
  - "리소스[MFC], 도구 모음"
  - "RT_TOOLBAR 리소스"
  - "SetButtons 메서드"
  - "도구 모음 컨트롤[MFC], 명령 ID"
  - "도구 모음 컨트롤[MFC], 응용 프로그램 마법사를 사용하여 만든 도구 모음"
  - "도구 모음 편집기, 응용 프로그램 마법사"
  - "도구 모음[C++], 응용 프로그램 마법사를 사용하여 기본 추가"
  - "도구 모음[C++], 만들기"
ms.assetid: cc00aaff-8a56-433b-b0c0-b857d76b4ffd
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 도구 모음 기본 사항
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article describes the fundamental MFC implementation that lets you add a default toolbar to your application by selecting an option in the Application Wizard.  다음 내용에 대해 다룹니다.  
  
-   [The Application Wizard toolbar option](#_core_the_appwizard_toolbar_option)  
  
-   [The toolbar in code](#_core_the_toolbar_in_code)  
  
-   [Editing the toolbar resource](#_core_editing_the_toolbar_resource)  
  
-   [Multiple toolbars](#_core_multiple_toolbars)  
  
##  <a name="_core_the_appwizard_toolbar_option"></a> The Application Wizard Toolbar Option  
 To get a single toolbar with default buttons, select the Standard Docking toolbar option on the page labeled User Interface Features.  This adds code to your application that:  
  
-   Creates the toolbar object.  
  
-   Manages the toolbar, including its ability to dock or to float.  
  
##  <a name="_core_the_toolbar_in_code"></a> The Toolbar in Code  
 The toolbar is a [CToolBar](../mfc/reference/ctoolbar-class.md) object declared as a data member of your application's **CMainFrame** class.  In other words, the toolbar object is embedded in the main frame window object.  This means that MFC creates the toolbar when it creates the frame window and destroys the toolbar when it destroys the frame window.  The following partial class declaration, for a multiple document interface \(MDI\) application, shows data members for an embedded toolbar and an embedded status bar.  It also shows the override of the `OnCreate` member function.  
  
 [!code-cpp[NVC_MFCListView#6](../mfc/codesnippet/CPP/toolbar-fundamentals_1.h)]  
  
 Toolbar creation occurs in **CMainFrame::OnCreate**.  MFC calls [OnCreate](../Topic/CWnd::OnCreate.md) after creating the window for the frame but before it becomes visible.  The default `OnCreate` that the Application Wizard generates does the following toolbar tasks:  
  
1.  Calls the `CToolBar` object's [Create](../Topic/CToolBar::Create.md) member function to create the underlying [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) object.  
  
2.  Calls [LoadToolBar](../Topic/CToolBar::LoadToolBar.md) to load the toolbar resource information.  
  
3.  Calls functions to enable docking, floating, and tool tips.  For details about these calls, see the article [Docking and Floating Toolbars](../mfc/docking-and-floating-toolbars.md).  
  
> [!NOTE]
>  The MFC General sample [DOCKTOOL](../top/visual-cpp-samples.md) includes illustrations of both old and new MFC toolbars.  The toolbars that use **COldToolbar** require calls in step 2 to `LoadBitmap` \(rather than `LoadToolBar`\) and to `SetButtons`.  The new toolbars require calls to `LoadToolBar`.  
  
 The docking, floating, and tool tips calls are optional.  You can remove those lines from `OnCreate` if you prefer.  The result is a toolbar that remains fixed, unable to float or redock and unable to display tool tips.  
  
##  <a name="_core_editing_the_toolbar_resource"></a> Editing the Toolbar Resource  
 The default toolbar you get with the Application Wizard is based on an **RT\_TOOLBAR** custom resource, introduced in MFC version 4.0.  You can edit this resource with the [toolbar editor](../mfc/toolbar-editor.md).  The editor lets you easily add, delete, and rearrange buttons.  It contains a graphical editor for the buttons that is very similar to the general graphics editor in Visual C\+\+.  If you edited toolbars in previous versions of Visual C\+\+, you'll find the task much easier now.  
  
 To connect a toolbar button to a command, you give the button a command ID, such as `ID_MYCOMMAND`.  Specify the command ID in the button's property page in the toolbar editor.  Then create a handler function for the command \(see [Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md) for more information\).  
  
 New [CToolBar](../mfc/reference/ctoolbar-class.md) member functions work with the **RT\_TOOLBAR** resource.  [LoadToolBar](../Topic/CToolBar::LoadToolBar.md) now takes the place of [LoadBitmap](../Topic/CToolBar::LoadBitmap.md) to load the bitmap of the toolbar button images, and [SetButtons](../Topic/CToolBar::SetButtons.md) to set the button styles and connect buttons with bitmap images.  
  
 For details about using the toolbar editor, see [Toolbar Editor](../mfc/toolbar-editor.md).  
  
##  <a name="_core_multiple_toolbars"></a> Multiple Toolbars  
 The Application Wizard provides you with one default toolbar.  If you need more than one toolbar in your application, you can model your code for additional toolbars based on the wizard\-generated code for the default toolbar.  
  
 If you want to display a toolbar as the result of a command, you'll need to:  
  
-   Create a new toolbar resource with the toolbar editor and load it in `OnCreate` with the [LoadToolbar](../Topic/CToolBar::LoadToolBar.md) member function.  
  
-   Embed a new [CToolBar](../mfc/reference/ctoolbar-class.md) object in your main frame window class.  
  
-   Make the appropriate function calls in `OnCreate` to dock or float the toolbar, set its styles, and so on.  
  
### 추가 정보  
  
-   [MFC Toolbar Implementation \(overview information on toolbars\)](../mfc/mfc-toolbar-implementation.md)  
  
-   [도구 모음 고정 및 고정 해제](../mfc/docking-and-floating-toolbars.md)  
  
-   [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) 및 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 클래스  
  
-   [Working with the toolbar control](../mfc/working-with-the-toolbar-control.md)  
  
-   [Using your old toolbars](../mfc/using-your-old-toolbars.md)  
  
## 참고 항목  
 [MFC 도구 모음 구현](../mfc/mfc-toolbar-implementation.md)