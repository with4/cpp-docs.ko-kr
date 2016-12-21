---
title: "TN062: Windows 컨트롤에 대한 메시지 리플렉션 | Microsoft Docs"
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
  - "vc.controls.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메시지 리플렉션"
  - "알림 메시지"
  - "ON_CONTROL_REFLECT 매크로"
  - "ON_CONTROL_REFLECT_EX 매크로"
  - "ON_NOTIFY 메시지"
  - "ON_NOTIFY_REFLECT 메시지"
  - "ON_NOTIFY_REFLECT_EX 메시지"
  - "ON_UPDATE_COMMAND_UI_REFLECT 매크로"
  - "ON_WM_CHARTOITEM_REFLECT 매크로"
  - "ON_WM_COMPAREITEM_REFLECT 매크로"
  - "ON_WM_CTLCOLOR_REFLECT 매크로"
  - "ON_WM_DELETEITEM_REFLECT 매크로"
  - "ON_WM_DRAWITEM_REFLECT 매크로"
  - "ON_WM_HSCROLL_REFLECT 매크로"
  - "ON_WM_MEASUREITEM_REFLECT 매크로"
  - "ON_WM_PARENTNOTIFY_REFLECT 매크로"
  - "ON_WM_VKEYTOITEM_REFLECT 매크로"
  - "ON_WM_VSCROLL_REFLECT 매크로"
  - "TN062"
  - "WM_COMMAND"
  - "WM_CTLCOLOR 메시지"
  - "WM_NOTIFY 메시지"
ms.assetid: 53efb0ba-fcda-4fa0-a3c7-14e0b78fb494
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN062: Windows 컨트롤에 대한 메시지 리플렉션
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다.  따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다.  최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 This technical note describes message reflection, a new feature in MFC 4.0.  It also contains directions for creating a simple reusable control that uses message reflection.  
  
 This technical note does not discuss message reflection as it applies to ActiveX controls \(formerly called OLE controls\).  Please see the article [ActiveX Controls: Subclassing a Windows Control](../mfc/mfc-activex-controls-subclassing-a-windows-control.md).  
  
 **What Is Message Reflection?**  
  
 Windows controls frequently send notification messages to their parent windows.  For instance, many controls send a control color notification message \(`WM_CTLCOLOR` or one of its variants\) to their parent to allow the parent to supply a brush for painting the background of the control.  
  
 In Windows and in MFC before version 4.0, the parent window, often a dialog box, is responsible for handling these messages.  This means that the code for handling the message needs to be in the parent window's class and that it has to be duplicated in every class that needs to handle that message.  In the case above, every dialog box that wanted controls with custom backgrounds would have to handle the control color notification message.  It would be much easier to reuse code if a control class could be written that would handle its own background color.  
  
 In MFC 4.0, the old mechanism still works — parent windows can handle notification messages.  In addition, however, MFC 4.0 facilitates reuse by providing a feature called "message reflection" that allows these notification messages to be handled in either the child control window or the parent window, or in both.  In the control background color example, you can now write a control class that sets its own background color by handling the reflected `WM_CTLCOLOR` message — all without relying on the parent. \(Note that since message reflection is implemented by MFC, not by Windows, the parent window class must be derived from `CWnd` for message reflection to work.\)  
  
 Older versions of MFC did something similar to message reflection by providing virtual functions for a few messages, such as messages for owner\-drawn list boxes \(`WM_DRAWITEM`, and so on\).  The new message reflection mechanism is generalized and consistent.  
  
 Message reflection is backward compatible with code written for versions of MFC before 4.0.  
  
 If you have supplied a handler for a specific message, or for a range of messages, in your parent window's class, it will override reflected message handlers for the same message provided you don't call the base class handler function in your own handler.  For example, if you handle `WM_CTLCOLOR` in your dialog box class, your handling will override any reflected message handlers.  
  
 If, in your parent window class, you supply a handler for a specific **WM\_NOTIFY** message or a range of **WM\_NOTIFY** messages, your handler will be called only if the child control sending those messages does not have a reflected message handler through **ON\_NOTIFY\_REFLECT\(\)**.  If you use **ON\_NOTIFY\_REFLECT\_EX\(\)** in your message map, your message handler may or may not allow the parent window to handle the message.  If the handler returns **FALSE**, the message will be handled by the parent as well, while a call that returns **TRUE** does not allow the parent to handle it.  Note that the reflected message is handled before the notification message.  
  
 When a **WM\_NOTIFY** message is sent, the control is offered the first chance to handle it.  If any other reflected message is sent, the parent window has the first chance to handle it and the control will receive the reflected message.  To do so, it will need a handler function and an appropriate entry in the control's class message map.  
  
 The message\-map macro for reflected messages is slightly different than for regular notifications: it has **\_REFLECT** appended to its usual name.  For instance, to handle a **WM\_NOTIFY** message in the parent, you use the macro `ON_NOTIFY` in the parent's message map.  To handle the reflected message in the child control, use the **ON\_NOTIFY\_REFLECT** macro in the child control's message map.  In some cases, the parameters are different, as well.  Note that ClassWizard can usually add the message\-map entries for you and provide skeleton function implementations with correct parameters.  
  
 See [TN061: ON\_NOTIFY and WM\_NOTIFY Messages](../mfc/tn061-on-notify-and-wm-notify-messages.md) for information on the new **WM\_NOTIFY** message.  
  
 **Message\-Map Entries and Handler Function Prototypes for Reflected Messages**  
  
 To handle a reflected control notification message, use the message\-map macros and function prototypes listed in the table below.  
  
 ClassWizard can usually add these message\-map entries for you and provide skeleton function implementations.  See [Defining a Message Handler for a Reflected Message](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md) for information about how to define handlers for reflected messages.  
  
 To convert from the message name to the reflected macro name, prepend **ON\_** and append **\_REFLECT**.  For example, `WM_CTLCOLOR` becomes **ON\_WM\_CTLCOLOR\_REFLECT**. \(To see which messages can be reflected, do the opposite conversion on the macro entries in the table below.\)  
  
 The three exceptions to the rule above are as follows:  
  
-   The macro for **WM\_COMMAND** notifications is **ON\_CONTROL\_REFLECT**.  
  
-   The macro for **WM\_NOTIFY** reflections is **ON\_NOTIFY\_REFLECT**.  
  
-   The macro for `ON_UPDATE_COMMAND_UI` reflections is **ON\_UPDATE\_COMMAND\_UI\_REFLECT**.  
  
 In each of the above special cases, you must specify the name of the handler member function.  In the other cases, you must use the standard name for your handler function.  
  
 The meanings of the parameters and return values of the functions are documented under either the function name or the function name with **On** prepended.  For instance, **CtlColor** is documented in `OnCtlColor`.  Several reflected message handlers need fewer parameters than the similar handlers in a parent window.  Just match the names in the table below with the names of the formal parameters in the documentation.  
  
|Map entry|함수 프로토타입|  
|---------------|--------------|  
|**ON\_CONTROL\_REFLECT\(**  `wNotifyCode` **,**  `memberFxn`  **\)**|**afx\_msg void**  `memberFxn`  **\( \);**|  
|**ON\_NOTIFY\_REFLECT\(**  `wNotifyCode` **,**  `memberFxn`  **\)**|**afx\_msg void**  `memberFxn`  **\( NMHDR \***  `pNotifyStruct` **, LRESULT\***  *result*  **\);**|  
|**ON\_UPDATE\_COMMAND\_UI\_REFLECT\(**  `memberFxn`  **\)**|**afx\_msg void**  `memberFxn`  **\( CCmdUI\***  `pCmdUI`  **\);**|  
|**ON\_WM\_CTLCOLOR\_REFLECT\( \)**|**afx\_msg HBRUSH CtlColor \( CDC\***  `pDC` **, UINT**  `nCtlColor`  **\);**|  
|**ON\_WM\_DRAWITEM\_REFLECT\( \)**|**afx\_msg void DrawItem \( LPDRAWITEMSTRUCT**  `lpDrawItemStruct`  **\);**|  
|**ON\_WM\_MEASUREITEM\_REFLECT\( \)**|**afx\_msg void MeasureItem \( LPMEASUREITEMSTRUCT**  `lpMeasureItemStruct`  **\);**|  
|**ON\_WM\_DELETEITEM\_REFLECT\( \)**|**afx\_msg void DeleteItem \( LPDELETEITEMSTRUCT**  `lpDeleteItemStruct`  **\);**|  
|**ON\_WM\_COMPAREITEM\_REFLECT\( \)**|**afx\_msg int CompareItem \( LPCOMPAREITEMSTRUCT**  `lpCompareItemStruct`  **\);**|  
|**ON\_WM\_CHARTOITEM\_REFLECT\( \)**|**afx\_msg int CharToItem \( UINT**  `nKey` **, UINT**  `nIndex`  **\);**|  
|**ON\_WM\_VKEYTOITEM\_REFLECT\( \)**|**afx\_msg int VKeyToItem \( UINT**  `nKey` **, UINT**  `nIndex`  **\);**|  
|**ON\_WM\_HSCROLL\_REFLECT\( \)**|**afx\_msg void HScroll \( UINT**  `nSBCode` **, UINT**  `nPos`  **\);**|  
|**ON\_WM\_VSCROLL\_REFLECT\( \)**|**afx\_msg void VScroll \( UINT**  `nSBCode` **, UINT**  `nPos`  **\);**|  
|**ON\_WM\_PARENTNOTIFY\_REFLECT\( \)**|**afx\_msg void ParentNotify \( UINT**  `message` **, LPARAM**  `lParam`  **\);**|  
  
 The **ON\_NOTIFY\_REFLECT** and **ON\_CONTROL\_REFLECT** macros have variations that allow more than one object \(such as the control and its parent\) to handle a given message.  
  
|Map entry|함수 프로토타입|  
|---------------|--------------|  
|**ON\_NOTIFY\_REFLECT\_EX\(**  `wNotifyCode` **,**  `memberFxn`  **\)**|**afx\_msg BOOL**  `memberFxn`  **\( NMHDR \***  `pNotifyStruct` **, LRESULT\***  *result*  **\);**|  
|**ON\_CONTROL\_REFLECT\_EX\(**  `wNotifyCode` **,**  `memberFxn`  **\)**|**afx\_msg BOOL**  `memberFxn`  **\( \);**|  
  
## Handling Reflected Messages: An Example of a Reusable control  
 This simple example creates a reusable control called `CYellowEdit`.  The control works the same as a regular edit control except that it displays black text on a yellow background.  It would be easy to add member functions that would allow the `CYellowEdit` control to display different colors.  
  
#### To try the example that creates a reusable control  
  
1.  Create a new dialog box in an existing application.  For more information, see the [dialog editor](../mfc/dialog-editor.md) topic.  
  
     You must have an application in which to develop the reusable control.  If you don't have an existing application to use, create a dialog\-based application using AppWizard.  
  
2.  With your project loaded into Visual C\+\+, use ClassWizard to create a new class called `CYellowEdit` based on `CEdit`.  
  
3.  Add three member variables to your `CYellowEdit` class.  The first two will be **COLORREF** variables to hold the text color and the background color.  The third will be a `CBrush` object that will hold the brush for painting the background.  The `CBrush` object allows you to create the brush once, merely referencing it after that, and to destroy the brush automatically when the `CYellowEdit` control is destroyed.  
  
4.  Initialize the member variables by writing the constructor as follows:  
  
    ```  
    CYellowEdit::CYellowEdit()  
    {  
       m_clrText = RGB( 0, 0, 0 );  
       m_clrBkgnd = RGB( 255, 255, 0 );  
       m_brBkgnd.CreateSolidBrush( m_clrBkgnd );  
    }  
    ```  
  
5.  Using ClassWizard, add a handler for the reflected `WM_CTLCOLOR` message to your `CYellowEdit` class.  Note that the equal sign in front of the message name in the list of messages you can handle indicates that the message is reflected.  This is described in [Defining a Message Handler for a Reflected Message](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md).  
  
     ClassWizard adds the following message\-map macro and skeleton function for you:  
  
    ```  
    ON_WM_CTLCOLOR_REFLECT()  
  
    // Note: other code will be in between....  
  
    HBRUSH CYellowEdit::CtlColor(CDC* pDC, UINT nCtlColor)   
    {  
       // TODO: Change any attributes of the DC here  
  
       // TODO: Return a non-NULL brush if the  
       //   parent's handler should not be called  
       return NULL;  
    }  
    ```  
  
6.  Replace the body of the function with the following code.  The code specifies the text color, the text background color, and the background color for rest of the control.  
  
    ```  
    pDC->SetTextColor( m_clrText );   // text  
    pDC->SetBkColor( m_clrBkgnd );   // text bkgnd  
    return m_brBkgnd;            // ctl bkgnd  
    ```  
  
7.  Create an edit control in your dialog box, then attach it to a member variable by double\-clicking the edit control while holding a control key down.  In the Add Member Variable dialog box, finish the variable name and choose "Control" for the category, then "CYellowEdit" for the variable type.  Don't forget to set the tab order in the dialog box.  Also, be sure to include the header file for the `CYellowEdit` control in your dialog box's header file.  
  
8.  응용 프로그램을 빌드하고 실행합니다.  The edit control will have a yellow background.  
  
## 참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)