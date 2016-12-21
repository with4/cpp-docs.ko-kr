---
title: "TN024: MFC에서 정의한 메시지 및 리소스 | Microsoft Docs"
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
  - "vc.mfc.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메시지[C++], MFC"
  - "리소스[MFC]"
  - "TN024"
  - "Windows 메시지[C++], MFC에서 정의한"
ms.assetid: c65353ce-8096-454b-ad22-1a7a1dd9a788
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN024: MFC에서 정의한 메시지 및 리소스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다.  따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다.  최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 This note describes the internal Windows messages and resource formats used by MFC.  This information explains the implementation of the framework, and will assist you in debugging your application.  For the adventurous, even though all this information is officially unsupported, you may use some of this information for advanced implementations.  
  
 This note contains MFC private implementation details; all the contents are subject to change in the future.  MFC private Windows messages have meaning in the scope of one application only but will change in the future to contain system\-wide messages.  
  
 The range of MFC private Windows messages and resource types are in the reserved "system" range set aside by Microsoft Windows.  Currently not all numbers in the ranges are used and, in the future, new numbers in the range may be used.  The currently used numbers may be changed.  
  
 MFC private Windows messages are in the range 0x360\-\>0x37F.  
  
 MFC private resource types are in the range 0xF0\-\>0xFF.  
  
 **MFC Private Windows Messages**  
  
 These Windows messages are used in place of C\+\+ virtual functions where relatively loose coupling is required between window objects and where a C\+\+ virtual function would not be appropriate.  
  
 These private Windows messages and associated parameter structures are declared in the MFC private header 'AFXPRIV.H'.  Be warned that any of your code that includes this header may be relying on undocumented behavior and will likely break in future versions of MFC.  
  
 In the rare case of needing to handle one of these messages, you should use the `ON_MESSAGE` message map macro and handle the message in the generic LRESULT\/WPARAM\/LPARAM format.  
  
 **WM\_QUERYAFXWNDPROC**  
  
 This message is sent to a window that is being created.  This is sent very early in the creation process as a method of determining if the WndProc is **AfxWndProc. AfxWndProc** returns 1.  
  
|||  
|-|-|  
|wParam|사용되지 않습니다.|  
|lParam|사용되지 않습니다.|  
|returns|1 if processed by **AfxWndProc**|  
  
 **WM\_SIZEPARENT**  
  
 This message is sent by a frame window to its immediate children during resizing \(**CFrameWnd::OnSize** calls `CFrameWnd::RecalcLayout` which calls `CWnd::RepositionBars`\) to reposition the control bars around the side of the frame.  The **AFX\_SIZEPARENTPARAMS** structure contains the current available client rectangle of the parent and a HDWP \(which may be NULL\) with which to call `DeferWindowPos` to minimize repainting.  
  
|||  
|-|-|  
|wParam|사용되지 않습니다.|  
|lParam|Address of an **AFX\_SIZEPARENTPARAMS** structure|  
|returns|Not used \(0\)|  
  
 Ignoring the message indicates that the window doesn't take part in the layout.  
  
 **WM\_SETMESSAGESTRING**  
  
 This message is sent to a frame window to ask it to update the message line in the status bar.  Either a string ID or a LPCSTR can be specified \(but not both\).  
  
|||  
|-|-|  
|wParam|String ID \(or zero\)|  
|lParam|LPCSTR for the string \(or NULL\)|  
|returns|Not used \(0\)|  
  
 **WM\_IDLEUPDATECMDUI**  
  
 This message is sent in idle time to implement the idle\-time update of update\-command UI handlers.  If the window \(usually a control bar\) handles the message, it creates a `CCmdUI` object \(or an object of a derived class\) and call **CCmdUI::DoUpdate** for each of the "items" in the window.  This will in turn check for an `ON_UPDATE_COMMAND_UI` handler for the objects in the command\-handler chain.  
  
|||  
|-|-|  
|wParam|BOOL bDisableIfNoHandler|  
|lParam|Not used \(0\)|  
|returns|Not used \(0\)|  
  
 *bDisableIfNoHandler* is nonzero to disable the UI object if there is neither an `ON_UPDATE_COMMAND_UI` nor an `ON_COMMAND` handler.  
  
 **WM\_EXITHELPMODE**  
  
 This message is posted to a `CFrameWnd` that to exit context sensitive help mode.  The receipt of this message terminates the modal loop started by **CFrameWnd::OnContextHelp.**  
  
|||  
|-|-|  
|wParam|Not used \(0\)|  
|lParam|Not used \(0\)|  
|returns|사용되지 않습니다.|  
  
 **WM\_INITIALUPDATE**  
  
 This message is sent by the document template to all descendants of a frame window when it is safe for them to do their initial update.  It maps to a call to `CView::OnInitialUpdate` but can be used in other `CWnd`\-derived classes for other one\-shot updating.  
  
|||  
|-|-|  
|wParam|Not used \(0\)|  
|lParam|Not used \(0\)|  
|returns|Not used \(0\)|  
  
 **WM\_RECALCPARENT**  
  
 This message is sent by a view to its parent window \(obtained via `GetParent`\) to force a layout recalculation \(usually, the parent will call `RecalcLayout`\).  This is used in OLE server applications where it is necessary for the frame to grow in size as the view's total size grows.  
  
 If the parent window processes this message it should return TRUE and fill the RECT passed in lParam with the new size of the client area.  This is used in `CScrollView` to properly handle scrollbars \(place then on the outside of the window when they are added\) when a server object is in\-place activated.  
  
|||  
|-|-|  
|wParam|Not used \(0\)|  
|lParam|LPRECT rectClient, may be NULL|  
|returns|TRUE if new client rectangle returned, FALSE otherwise|  
  
 **WM\_SIZECHILD**  
  
 This message is sent by `COleResizeBar` to its owner window \(via `GetOwner`\) when the user resizes the resize bar with the resize handles.  `COleIPFrameWnd` responds to this message by attempting to reposition the frame window as the user has requested.  
  
 The new rectangle, given in client coordinates relative to the frame window which contains the resize bar, is pointed at by lParam.  
  
|||  
|-|-|  
|wParam|Not used \(0\)|  
|lParam|LPRECT rectNew|  
|returns|Not used \(0\)|  
  
 **WM\_DISABLEMODAL**  
  
 This message is sent to all pop\-up windows owned by a frame window that is being deactivated.  The frame window uses the result to determine whether or not to disable the pop\-up window.  
  
 You can use this to perform special processing in your pop\-up window when the frame enters a modal state or to keep certain pop\-up windows from getting disabled.  Tooltips use this message to destroy themselves when the frame window goes into a modal state, for example.  
  
|||  
|-|-|  
|wParam|Not used \(0\)|  
|lParam|Not used \(0\)|  
|returns|Non\-zero to **NOT** disable the window, 0 indicates the window will be disabled|  
  
 **WM\_FLOATSTATUS**  
  
 This message is sent to all pop\-up windows owned by a frame window when the frame is either activated or deactivated by another top\-level frame window.  This is used by the implementation of **MFS\_SYNCACTIVE** in `CMiniFrameWnd`, to keep the activation of these pop\-up windows in sync with the activation of the top level frame window.  
  
|||  
|-|-|  
|wParam|Is one of the following values:<br /><br /> **FS\_SHOW**<br /><br /> **FS\_HIDE**<br /><br /> **FS\_ACTIVATE**<br /><br /> **FS\_DEACTIVATE**<br /><br /> **FS\_ENABLEFS\_DISABLE**<br /><br /> **FS\_SYNCACTIVE**|  
|lParam|Not used \(0\)|  
  
 The return value should be non\-zero if **FS\_SYNCACTIVE** is set and the window syncronizes its activation with the parent frame.  `CMiniFrameWnd` returns non\-zero when the style is set to **MFS\_SYNCACTIVE.**  
  
 For more information, see the implementation of `CMiniFrameWnd`.  
  
## WM\_ACTIVATETOPLEVEL  
 This message is sent to a top\-level window when a window in its "top\-level group" is either activated or deactivated.  A window is part of a top\-level group if it is a top\-level window \(no parent or owner\), or it is owned by such a window.  This message is similar in use to **WM\_ACTIVATEAPP,** but works in situations where windows belonging to different processes are mixed in a single window hierarchy \(common in OLE applications\).  
  
## WM\_COMMANDHELP, WM\_HELPHITTEST, WM\_EXITHELPMODE  
 These messages are used in the implementation of context\-sensitive Help.  Please refer to [Technical Note 28](../mfc/tn028-context-sensitive-help-support.md) for more information.  
  
## MFC Private Resource Formats  
 Currently, MFC defines two private resource formats: **RT\_TOOLBAR** and **RT\_DLGINIT**.  
  
## RT\_TOOLBAR Resource Format  
 The default toolbar supplied by AppWizard is based on an **RT\_TOOLBAR** custom resource, which was introduced in MFC 4.0.  You can edit this resource using the Toolbar editor.  
  
## RT\_DLGINIT Resource Format  
 One MFC private resource format is used to store extra dialog initialization information.  This includes the initial strings stored in a combo box.  The format of this resource is not designed to be manually edited, but is handled by Visual C\+\+.  
  
 Visual C\+\+ and this **RT\_DLGINIT** resource are not required to use the related features of MFC since there are API alternative to using the information in the resource.  Using Visual C\+\+ makes it much easier to write, maintain, and translate your application in the long run.  
  
 The basic structure of a **RT\_DLGINIT** resource is as follows:  
  
```  
+---------------+                    \  
| Control ID    |   UINT             |  
+---------------+                    |  
| Message #     |   UINT             |  
+---------------+                    |  
|length of data |   DWORD            |  
+---------------+                    |   Repeated  
|   Data        |   Variable Length  |   for each control  
|   ...         |   and Format       |   and message  
+---------------+                    /  
|     0         |   BYTE  
+---------------+  
```  
  
 A repeated section contains the control ID to send the message to, the Message \# to send \(a normal Windows message\) and a variable length of data.  The Windows message is sent in a form:  
  
```  
SendDlgItemMessage(<Control ID>, <Message #>, 0, &<Data>);  
```  
  
 This is a very general format, allowing any Windows messages and data content.  The Visual C\+\+ resource editor and MFC only support a limited subset of Windows messages: CB\_ADDSTRING for the initial list\-choices for combo boxes \(the data is a text string\).  
  
## 참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)