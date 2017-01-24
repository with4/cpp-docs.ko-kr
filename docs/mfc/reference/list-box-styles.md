---
title: "목록 상자 스타일 | Microsoft Docs"
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
  - "LBS_STANDARD"
  - "LBS_NODATA"
  - "LBS_OWNERDRAWVARIABLE"
  - "LBS_EXTENDEDSEL"
  - "LBS_USETABSTOPS"
  - "LBS_WANTKEYBOARDINPUT"
  - "LBS_NOTIFY"
  - "LBS_DISABLENOSCROLL"
  - "LBS_HASSTRINGS"
  - "LBS_NOREDRAW"
  - "LBS_NOSEL"
  - "LBS_NOINTEGRALHEIGHT"
  - "LBS_MULTICOLUMN"
  - "LBS_SORT"
  - "LBS_MULTIPLESEL"
  - "LBS_OWNERDRAWFIXED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LBS_DISABLENOSCROLL 상수"
  - "LBS_EXTENDEDSEL 상수"
  - "LBS_HASSTRINGS 상수"
  - "LBS_MULTICOLUMN 상수"
  - "LBS_MULTIPLESEL 상수"
  - "LBS_NODATA 상수"
  - "LBS_NOINTEGRALHEIGHT 상수"
  - "LBS_NOREDRAW 상수"
  - "LBS_NOSEL 상수"
  - "LBS_NOTIFY 상수"
  - "LBS_OWNERDRAWFIXED 상수"
  - "LBS_OWNERDRAWVARIABLE 상수"
  - "LBS_SORT 상수"
  - "LBS_STANDARD 상수"
  - "LBS_USETABSTOPS 상수"
  - "LBS_WANTKEYBOARDINPUT 상수"
  - "목록 상자, 스타일"
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 목록 상자 스타일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **LBS\_DISABLENOSCROLL** The list box shows a disabled vertical scroll bar when the list box does not contain enough items to scroll.  Without this style, the scroll bar is hidden when the list box does not contain enough items.  
  
-   **LBS\_EXTENDEDSEL** The user can select multiple items using the SHIFT key and the mouse or special key combinations.  
  
-   **LBS\_HASSTRINGS** Specifies an owner\-draw list box that contains items consisting of strings.  The list box maintains the memory and pointers for the strings so the application can use the `GetText` member function to retrieve the text for a particular item.  
  
-   **LBS\_MULTICOLUMN** Specifies a multicolumn list box that is scrolled horizontally.  The `SetColumnWidth` member function sets the width of the columns.  
  
-   **LBS\_MULTIPLESEL** String selection is toggled each time the user clicks or double\-clicks the string.  Any number of strings can be selected.  
  
-   **LBS\_NODATA** Specifies a no\-data list box.  Specify this style when the count of items in the list box will exceed one thousand.  A no\-data list box must also have the **LBS\_OWNERDRAWFIXED** style, but must not have the **LBS\_SORT** or **LBS\_HASSTRINGS** style.  
  
     A no\-data list box resembles an owner\-drawn list box except that it contains no string or bitmap data for an item.  Commands to add, insert, or delete an item always ignore any given item data; requests to find a string within the list box always fail.  The system sends the `WM_DRAWITEM` message to the owner window when an item must be drawn.  The itemID member of the `DRAWITEMSTRUCT` structure passed with the `WM_DRAWITEM` message specifies the line number of the item to be drawn.  A no\-data list box does not send a `WM_DELETEITEM` message.  
  
-   **LBS\_NOINTEGRALHEIGHT** The size of the list box is exactly the size specified by the application when it created the list box.  Usually, Windows sizes a list box so that the list box does not display partial items.  
  
-   **LBS\_NOREDRAW** List\-box display is not updated when changes are made.  This style can be changed at any time by sending a **WM\_SETREDRAW** message.  
  
-   **LBS\_NOSEL** Specifies that the list box contains items that can be viewed but not selected.  
  
-   **LBS\_NOTIFY** Parent window receives an input message whenever the user clicks or double\-clicks a string.  
  
-   **LBS\_OWNERDRAWFIXED** The owner of the list box is responsible for drawing its contents; the items in the list box are the same height.  
  
-   **LBS\_OWNERDRAWVARIABLE** The owner of the list box is responsible for drawing its contents; the items in the list box are variable in height.  
  
-   **LBS\_SORT** Strings in the list box are sorted alphabetically.  
  
-   **LBS\_STANDARD** Strings in the list box are sorted alphabetically, and the parent window receives an input message whenever the user clicks or double\-clicks a string.  The list box contains borders on all sides.  
  
-   **LBS\_USETABSTOPS** Allows a list box to recognize and expand tab characters when drawing its strings.  The default tab positions are 32 dialog units. \(A dialog unit is a horizontal or vertical distance.  One horizontal dialog unit is equal to one\-fourth of the current dialog base width unit.  The dialog base units are computed based on the height and width of the current system font.  The **GetDialogBaseUnits** Windows function returns the current dialog base units in pixels.\) This style should not be used with **LBS\_OWNERDRAWFIXED**.  
  
-   **LBS\_WANTKEYBOARDINPUT** The owner of the list box receives `WM_VKEYTOITEM` or `WM_CHARTOITEM` messages whenever the user presses a key while the list box has input focus.  This allows an application to perform special processing on the keyboard input.  
  
## 참고 항목  
 [MFC에서 사용하는 스타일](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../Topic/CListBox::Create.md)   
 [List Box Styles](http://msdn.microsoft.com/library/windows/desktop/bb775149)