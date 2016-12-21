---
title: "AFX 메시지 | Microsoft Docs"
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
  - "SB_LINELEFT"
  - "SB_THUMBTRACK"
  - "AFX_TOOLTIP_TYPE_EDIT"
  - "AFX_WM_ON_HSCROLL"
  - "SB_PAGERIGHT"
  - "AFX_WM_RESETPROMPT"
  - "AFX_WM_CHANGE_RIBBON_CATEGORY"
  - "AFX_TOOLTIP_TYPE_MINIFRAME"
  - "AFX_WM_CUSTOMIZETOOLBAR"
  - "AFX_WM_CHANGE_ACTIVE_TAB"
  - "AFX_WM_ACCGETOBJECT"
  - "AFX_WM_TOOLBARMENU"
  - "AFX_TOOLTIP_TYPE_DOCKBAR"
  - "AFX_WM_CUSTOMIZEHELP"
  - "AFX_WM_ON_GET_TAB_TOOLTIP"
  - "AFX_WM_ON_RIBBON_CUSTOMIZE"
  - "AFX_WM_ON_DRAGCOMPLETE"
  - "AFX_WM_RESETTOOLBAR"
  - "AFX_WM_ON_MOVETOTABGROUP"
  - "AFX_WM_CHECKEMPTYMINIFRAME"
  - "AFX_WM_GETDOCUMENTCOLORS"
  - "SB_RIGHT"
  - "AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU"
  - "AFX_WM_ACCGETSTATE"
  - "SB_PAGELEFT"
  - "SB_ENDSCROLL"
  - "AFX_WM_ON_CANCELTABMOVE"
  - "AFX_TOOLTIP_TYPE_TAB"
  - "AFX_WM_WINDOW_HELP"
  - "AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM"
  - "AFX_WM_SHOWREGULARMENU"
  - "AFX_TOOLTIP_TYPE_TOOLBAR"
  - "AFX_WM_CHANGE_CURRENT_FOLDER"
  - "AFX_WM_UPDATETOOLTIPS"
  - "AFX_WM_ON_MOVE_TAB"
  - "AFX_WM_CHANGING_ACTIVE_TAB"
  - "AFX_WM_RESETMENU"
  - "AFX_WM_GETDRAGBOUNDS"
  - "AFX_WM_RESETCONTEXTMENU"
  - "AFX_TOOLTIP_TYPE_BUTTON"
  - "AFX_WM_ON_CLOSEPOPUPWINDOW"
  - "AFX_TOOLTIP_TYPE_TOOLBOX"
  - "AFX_WM_CHANGEVISUALMANAGER"
  - "SB_LINERIGHT"
  - "AFX_WM_ON_RENAME_TAB"
  - "AFX_TOOLTIP_TYPE_DEFAULT"
  - "AFX_WM_ON_TABGROUPMOUSEMOVE"
  - "SB_LEFT"
  - "AFX_WM_DELETETOOLBAR"
  - "AFX_WM_PROPERTY_CHANGED"
  - "AFX_TOOLTIP_TYPE_ALL"
  - "AFX_WM_ACCHITTEST"
  - "AFX_WM_ON_AFTER_SHELL_COMMAND"
  - "AFX_WM_ON_PRESS_CLOSE_BUTTON"
  - "AFX_WM_RESETKEYBOARD"
  - "AFX_WM_ON_MOVETABCOMPLETE"
  - "AFX_WM_CREATETOOLBAR"
  - "SB_THUMBPOSITION"
  - "AFX_WM_POSTSETPREVIEWFRAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX 메시지"
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
caps.latest.revision: 24
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AFX 메시지
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

These messages are used in MFC.  
  
## 메시지  
 The following table lists messages that are used in the MFC library:  
  
||||||  
|-|-|-|-|-|  
|메시지|설명|\[in\] `wParam`|`lParam` \(All parameters are \[in\] unless otherwise stated.\)|반환 값|  
|AFX\_WM\_ACCGETOBJECT|사용되지 않습니다.|사용되지 않습니다.|해당 사항 없음.|해당 사항 없음.|  
|AFX\_WM\_ACCGETSTATE|Used for accessibility support.  Send this message to `CMFCPopupMenu` or `CMFCRibbonPanelMenu` to retrieve the state of the current element.|Index of element, which could be a menu button or separator.|사용되지 않습니다.|The element’s state.  It is \-1 if the index is invalid, 0 if the menu button has no special attributes.  Otherwise it is a combination of the following flags:<br /><br /> TBBS\_DISABLED –item is disabled<br /><br /> TBBS\_CHECKED – item is checked<br /><br /> TBBS\_BUTTON – the item is a standard pushbutton<br /><br /> TBBS\_PRESSED –button is pressed<br /><br /> TBBS\_INDETERMINATE – undefined state<br /><br /> TBBS\_SEPARATOR \- rather than a menu button, this element forms a separation between other menu items|  
|AFX\_WM\_CHANGE\_ACTIVE\_TAB|The framework sends this message to the resizable control bar control.  Process this message to receive notifications from `CMFCTabCtrl` objects when a user changes an active tab.|The index of a tab.|사용되지 않습니다.|Nonzero.|  
|AFX\_WM\_CHANGE\_CURRENT\_FOLDER|The framework sends this message to the parent of `CMFCShellListCtrl` when the user has changed the current folder.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|  
|AFX\_WM\_CHANGEVISUALMANAGER|The framework sends this message to all frame windows when the user changes the current Visual Manager.  In response to this message, a frame window recalculates its region and adjusts other parameters as needed.  You can process the AFX\_WM\_CHANGEVISUALMANAGER message in your application if you need to be notified about this event.  You must call the base class handler \(`OnChangeVisualManager`\) to ensure that the framework's internal processing of this event takes place.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|  
|AFX\_WM\_CHANGING\_ACTIVE\_TAB|Sent to the parent of `CMFCTabCtrl` object.  Process this message if you want to receive notifications from `CMFCTabCtrl` objects when a user resets a tab.|The index of the tab that is being activated.|사용되지 않습니다.|Nonzero.|  
|AFX\_WM\_CHECKEMPTYMINIFRAME|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.|해당 사항 없음.|  
|AFX\_WM\_CREATETOOLBAR|Sent from `CMFCToolBarsListPropertyPage` when a user creates a new toolbar during customization process.  You can process this message to instantiate a custom CMFCToolBar\-derived object.  If you handle this message and create your own toolbar, omit the call to the default handler.|사용되지 않습니다.|A pointer to a string that contains the name of the toolbar.|A pointer to the newly created toolbar.  NULL indicates that the toolbar creation was canceled.|  
|AFX\_WM\_CUSTOMIZEHELP|Sent to the main frame window from the customization property sheet `CMFCToolbarCustomize``Dialog` when the user presses the **Help** button or the F1 key.|Specifies the active page of the customization property sheet.|A pointer to a `CMFCToolbarCustomize``Dialog` object.|0입니다.|  
|AFX\_WM\_CUSTOMIZETOOLBAR|The `CMFCToolbarCustomize``Dialog` sends this message to notify the parent frame that the user is creating a new toolbar.|`TRUE` when customization is started, `FALSE` when customization is finished.|사용되지 않습니다.|0입니다.|  
|AFX\_WM\_DELETETOOLBAR|Sent to the main frame window when the user is about to delete a toolbar in the customization mode.<br /><br /> Process this message to take additional actions when a user deletes a toolbar in customization mode.  You should also call the default handler \(`OnToolbarDelete`\), which deletes the toolbar.  The default handler returns a value that indicates whether it is possible to delete the toolbar.|사용되지 않습니다.|Pointer to a `CMFCToolBar` object to be deleted.|Nonzero if a toolbar cannot be deleted; otherwise 0.|  
|AFX\_WM\_GETDOCUMENTCOLORS|`CMFCColorMenuButton` sends this message to the main frame window to retrieve the document colors.|사용되지 않습니다.|\[in, out\] Pointer to a `CList<COLORREF, COLORREF>` object.|0입니다.|  
|AFX\_WM\_GETDRAGBOUNDS|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.|해당 사항 없음.|  
|AFX\_WM\_HIGHLIGHT\_RIBBON\_LIST\_ITEM|Sent to the main frame window when a user highlights a ribbon list item.|Index of the highlighted item|A pointer to `CMFCBaseRibbonElement`|사용되지 않습니다.|  
|AFX\_WM\_ON\_AFTER\_SHELL\_COMMAND|Sent to a parent of `CMFCShellListCtrl` or `CMFCShellTreeCtrl` controls when a user finishes executing a shell command.|The ID of the command that the user executed|사용되지 않습니다.|If the application processes this message, it should return zero.|  
|AFX\_WM\_ON\_BEFORE\_SHOW\_RIBBON\_ITEM\_MENU|The framework sends this message to the ribbon's parent before it displays the pop\-up menu.  You can process this message and modify pop\-up menus at any time.|사용되지 않습니다.|A pointer to `CMFCBaseRibbonElement`|사용되지 않습니다.|  
|AFX\_WM\_ON\_CANCELTABMOVE|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.||  
|AFX\_WM\_ON\_CHANGE\_RIBBON\_CATEGORY|The framework sends this message to the main frame when the user changes the active Ribbon Control category.|사용되지 않습니다.|A pointer to the `CMFCRibbonBar` whose category has changed.|사용되지 않습니다.|  
|AFX\_WM\_ON\_CLOSEPOPUPWINDOW|The framework sends this message to notify the owner of `CMFCDesktopAlertWnd` that the window is about to be closed.|사용되지 않습니다.|A pointer to `CMFCDesktopAlertWnd` object.|사용되지 않습니다.|  
|AFX\_WM\_ON\_DRAGCOMPLETE|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.|해당 사항 없음.|  
|AFX\_WM\_ON\_GET\_TAB\_TOOLTIP|Sent to the main frame window when a tab window is about to display a tooltip for a tab, if custom tooltips are enabled.|사용되지 않습니다.|A pointer to a `CMFCTabToolTipInfo` structure.|사용되지 않습니다.|  
|AFX\_WM\_ON\_HSCROLL|Sent to the resizable control bar control.  Process this message to receive notifications from `CMFCTabCtrl` objects when a scroll event occurs in the tabbed widget horizontal scroll bar.|The low\-order word specifies a scroll bar value that indicates the user's scrolling request.  자세한 내용은 이 항목 뒷부분에 나오는 표를 참조하십시오.|사용되지 않습니다.|Nonzero.|  
|AFX\_WM\_ON\_MOVE\_TAB|Sent to the parent of a tabbed window when a user drags a tab to a new position.|The zero\-based index of the tab in its original position.|\[out\] The zero\-based index of the tab in its new position.|0입니다.|  
|AFX\_WM\_ON\_MOVETABCOMPLETE|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.|해당 사항 없음.|  
|AFX\_WM\_ON\_MOVETOTABGROUP|Sent to the main frame window when a user moves an MDI child window from one tabbed group to another.|A handle to tabbed window \(`CMFCTabCtrl`\) from which the MDI child window has been removed.|\[out\] A handle to tabbed window \(`CMFCTabCtrl`\) to which the MDI child window has been inserted.|무시합니다.|  
|AFX\_WM\_ON\_PRESS\_CLOSE\_BUTTON|Sent to a parent of `CDockablePane` when user clicks the **Close** button on the caption of the control bar.|사용되지 않습니다.|A pointer to a dockable pane on which the user clicked the **Close** button.|`TRUE` if a pane cannot be closed; otherwise FALSE.|  
|AFX\_WM\_ON\_RENAME\_TAB|Sent to the parent of tabbed window after the user renamed an editable tab.|The zero\-based index of the renamed tab.|\[out\] A pointer to a string that contains the new tab name.|Nonzero if the application processes this message; the framework will suppress the call to `CMFCBaseTabCtrl::SetTabLabel`.  If zero is returned, then `CMFCBaseTabCtrl::SetTabLabel` is called by the framework.|  
|AFX\_WM\_ON\_RIBBON\_CUSTOMIZE|Sent to the parent frame when user starts customization.  Process this message if you want to display your own customization dialog box.|사용되지 않습니다.|A pointer to the ribbon control to be customized.|Nonzero if the application processes this message and displays its own customization dialog box.  If the application returns zero, the framework will display the built\-in customization dialog box.|  
|AFX\_WM\_ON\_TABGROUPMOUSEMOVE|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.|해당 사항 없음.|  
|AFX\_WM\_POSTSETPREVIEWFRAME|Sent to notify the main frame that the user changed the print preview mode|`TRUE` indicates that the print preview mode is set.  `FALSE` indicates that print preview mode is turned off.|사용되지 않습니다.|사용되지 않습니다.|  
|AFX\_WM\_PROPERTY\_CHANGED|Sent to the owner of the property grid control \(`CMFCPropertyGridCtrl`\) when the user changes the value of the selected property.|The control ID of the property list.|A pointer to the property \(`CMFCProp``ertyGridProperty`\) that changed.|사용되지 않습니다.|  
|AFX\_WM\_RESETCONTEXTMENU|Sent to the main frame window when the user resets the context menu during customization.|The resource ID of the context menu.|A pointer to the current context menu, `CMFCPopupMenu`.|사용되지 않습니다.|  
|AFX\_WM\_RESETKEYBOARD|The framework sends this message to the main frame window when the user resets all keyboard accelerators during customization.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|  
|AFX\_WM\_RESETMENU|The framework sends this message to the menu owner \(a frame window\) when the user resets an application frame menu during customization|The menu resource ID.|사용되지 않습니다.|사용되지 않습니다.|  
|AFX\_WM\_RESETPROMPT|The framework sends this message when the user resets a toolbar from the toolbar customize dialog box.  The default handler displays a message box that asks whether the user wants to reset the toolbar.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|  
|AFX\_WM\_RESETTOOLBAR|A `CMFCToolBar` object sends this message when a toolbar is restored to its original state, that is, loaded from the resources.  Process this message to reinsert toolbar buttons whose classes are derived from `CMFCToolbarButton`.  자세한 내용은 `CMFCToolbarComboBoxButton`을 참조하십시오.|The resource ID of a toolbar whose state was restored.|사용되지 않습니다.|0입니다.|  
|AFX\_WM\_SHOWREGULARMENU|`CMFCToolbarMenuButton` object sends this message to its owner when the user clicks a regular menu button.  Process this message every time that you use `CMFCToolbarMenuButton` to display a pop\-up menu when the user clicks a button.|The command ID of a button that sends the message.|Screen coordinates of the cursor.  The low\-order word specifies the x\-coordinate.  The high\-order word specifies the y\-coordinate.|사용되지 않습니다.|  
|AFX\_WM\_TOOLBARMENU|Sent to the main frame window when the user releases the right button of a mouse while the mouse pointer is in the client or non\-client area of a pane.|사용되지 않습니다.|Screen coordinates of the mouse pointer.  The low\-order word specifies the x\-coordinate.  The high\-order word specifies the y\-coordinate.|Zero if the application processes this message; otherwise, nonzero.|  
|AFX\_WM\_UPDATETOOLTIPS|Sent to all tooltip owners to indicate that their tooltip controls should be recreated.|The type of control that should process this message.  See the table later in this topic for a list of possible values.|사용되지 않습니다.|사용되지 않습니다.|  
|AFX\_WM\_WINDOW\_HELP|`CMFCWindowsManagerDialog` sends this message to the parent frame when the user clicks the **Help** button, or enters the help mode by clicking the **Help** caption button or the F1 key.|사용되지 않습니다.|A pointer to the instance of `CMFCWindowsManagerDialog`.|사용되지 않습니다.|  
  
 The following table shows the values for the low word of the `lParam` parameter of the AFX\_WM\_HSCROLL method:  
  
|||  
|-|-|  
|값|의미|  
|SB\_ENDSCROLL|The user ends the scroll.|  
|SB\_LEFT|The user scrolls to the upper\-left.|  
|SB\_RIGHT|The user scrolls to the lower\-right.|  
|SB\_LINELEFT|The user scrolls left by one unit.|  
|SB\_LINERIGHT|The user scrolls right by one unit.|  
|SB\_PAGELEFT|The user scrolls left by the width of the window.|  
|SB\_PAGERIGHT|The user scrolls right by the width of the window.|  
|SB\_THUMBPOSITION|The user has dragged the scroll box \(thumb\) and released the mouse button.  The high\-order word indicates the position of the scroll box at the end of the drag operation.|  
|SB\_THUMBTRACK|The user is dragging the scroll box.  The AFX\_WM\_ON\_HSCROLL message is sent repeatedly with this value until the user releases the mouse button.  The high\-order word indicates the position to which the scroll box has been dragged.|  
  
> [!NOTE]
>  The high\-order word of the `lParam` parameter specifies the current position of the scroll box if the low\-order word is SB\_THUMBPOSITION or SB\_THUMBTRACK; otherwise, this word is not used.  
  
 The following table lists the flag values for the `lParam` parameter of the AFX\_WM\_UPDATETOOLTIPS message:  
  
|||  
|-|-|  
|플래그|값|  
|AFX\_TOOLTIP\_TYPE\_DEFAULT|0x0001|  
|AFX\_TOOLTIP\_TYPE\_TOOLBAR|0x0002|  
|AFX\_TOOLTIP\_TYPE\_TAB|0x0004|  
|AFX\_TOOLTIP\_TYPE\_MINIFRAME|0x0008|  
|AFX\_TOOLTIP\_TYPE\_DOCKBAR|0x0010|  
|AFX\_TOOLTIP\_TYPE\_EDIT|0x0020|  
|AFX\_TOOLTIP\_TYPE\_BUTTON|0x0040|  
|AFX\_TOOLTIP\_TYPE\_TOOLBOX|0x0080|  
|AFX\_TOOLTIP\_TYPE\_ALL|0xFFFF|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)