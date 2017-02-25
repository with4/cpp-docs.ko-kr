---
title: "도구 모음 도구 설명 | Microsoft Docs"
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
  - "CBRS_FLYBY 상수"
  - "CBRS_TOOLTIPS 상수"
  - "flyby 상태 표시줄 업데이트"
  - "상태 표시줄, 도구 설명"
  - "도구 설명[C++]"
  - "도구 설명[C++], 활성화"
  - "도구 설명[C++], 텍스트 추가"
  - "업데이트"
  - "업데이트, 상태 표시줄 메시지"
  - "상태 표시줄 메시지 업데이트"
ms.assetid: d1696305-b604-4fad-9f09-638878371412
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 도구 모음 도구 설명
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Tool tips are the tiny popup windows that present short descriptions of a toolbar button's purpose when you position the mouse over a button for a period of time.  When you create an application with the Application Wizard that has a toolbar, tool tip support is provided for you.  This article explains both the tool tip support created by the Application Wizard and how to add tool tip support to your application.  
  
 This article covers:  
  
-   [Activating tool tips](#_core_activating_tool_tips)  
  
-   [Flyby status bar updates](#_core_fly_by_status_bar_updates)  
  
##  <a name="_core_activating_tool_tips"></a> Activating Tool Tips  
 To activate tool tips in your application, you must do two things:  
  
-   Add the `CBRS_TOOLTIPS` style to the other styles \(such as **WS\_CHILD**, **WS\_VISIBLE**, and other **CBRS\_** styles\) passed as the `dwStyle` parameter to the [CToolBar::Create](../Topic/CToolBar::Create.md) function or in [SetBarStyle](../Topic/CControlBar::SetBarStyle.md).  
  
-   As described in the procedure below, append the toolbar tip text, separated by a newline character \('\\n'\), to the string resource containing the command\-line prompt for the toolbar command.  The string resource shares the ID of the toolbar button.  
  
#### To add the tool tip text  
  
1.  While you are editing the toolbar in the toolbar editor, open the **Toolbar Button Properties** window for a given button.  
  
2.  In the **Prompt** box, specify the text you want to appear in the tool tip for that button.  
  
> [!NOTE]
>  Setting the text as a button property in the toolbar editor replaces the former procedure, in which you had to open and edit the string resource.  
  
 If a control bar with tool tips enabled has child controls placed on it, the control bar will display a tool tip for every child control on the control bar as long as it meets the following criteria:  
  
-   The ID of the control is not – 1.  
  
-   The string\-table entry with the same ID as the child control in the resource file has a tool tip string.  
  
##  <a name="_core_fly_by_status_bar_updates"></a> Flyby Status Bar Updates  
 A feature related to tool tips is "flyby" status bar updating.  By default, the message on the status bar describes only a particular toolbar button when the button is activated.  By including `CBRS_FLYBY` in your list of styles passed to `CToolBar::Create`, you can have these messages updated when the mouse cursor passes over the toolbar without actually activating the button.  
  
### 추가 정보  
  
-   [MFC Toolbar Implementation \(overview information on toolbars\)](../mfc/mfc-toolbar-implementation.md)  
  
-   [도구 모음 고정 및 고정 해제](../mfc/docking-and-floating-toolbars.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) 및 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 클래스  
  
-   [Working with the toolbar control](../mfc/working-with-the-toolbar-control.md)  
  
-   [Using your old toolbars](../mfc/using-your-old-toolbars.md)  
  
## 참고 항목  
 [MFC 도구 모음 구현](../mfc/mfc-toolbar-implementation.md)