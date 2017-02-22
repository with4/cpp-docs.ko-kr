---
title: "MEASUREITEMSTRUCT 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MEASUREITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MEASUREITEMSTRUCT 구조체"
ms.assetid: d141ace4-47cb-46b5-a81c-ad2c5e5a8501
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# MEASUREITEMSTRUCT 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `MEASUREITEMSTRUCT` structure informs Windows of the dimensions of an owner\-drawn control or menu item.  
  
## 구문  
  
```  
  
      typedef struct tagMEASUREITEMSTRUCT {  
   UINT CtlType;  
   UINT CtlID;  
   UINT itemID;  
   UINT itemWidth;  
   UINT itemHeight;  
   DWORD itemData  
} MEASUREITEMSTRUCT;  
```  
  
#### 매개 변수  
 `CtlType`  
 Contains the control type.  The values for control types are as follows:  
  
-   **ODT\_COMBOBOX** Owner\-draw combo box  
  
-   **ODT\_LISTBOX** Owner\-draw list box  
  
-   **ODT\_MENU** Owner\-draw menu  
  
 `CtlID`  
 Contains the control ID for a combo box, list box, or button.  This member is not used for a menu.  
  
 `itemID`  
 Contains the menu\-item ID for a menu or the list\-box\-item ID for a variable\-height combo box or list box.  This member is not used for a fixed\-height combo box or list box, or for a button.  
  
 *itemWidth*  
 Specifies the width of a menu item.  The owner of the owner\-draw menu item must fill this member before it returns from the message.  
  
 *itemHeight*  
 Specifies the height of an individual item in a list box or a menu.  Before it returns from the message, the owner of the owner\-draw combo box, list box, or menu item must fill out this member.  The maximum height of a list box item is 255.  
  
 `itemData`  
 For a combo box or list box, this member contains the value that was passed to the list box by one of the following:  
  
-   [CComboBox::AddString](../Topic/CComboBox::AddString.md)  
  
-   [CComboBox::InsertString](../Topic/CComboBox::InsertString.md)  
  
-   [CListBox::AddString](../Topic/CListBox::AddString.md)  
  
-   [CListBox::InsertString](../Topic/CListBox::InsertString.md)  
  
 For a menu, this member contains the value that was passed to the menu by one of the following:  
  
-   [CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md)  
  
-   [CMenu::InsertMenu](../Topic/CMenu::InsertMenu.md)  
  
-   [CMenu::ModifyMenu](../Topic/CMenu::ModifyMenu.md)  
  
 This allows Windows to process user interaction with the control correctly.  Failure to fill out the proper members in the `MEASUREITEMSTRUCT` structure will cause improper operation of the control.  
  
## 요구 사항  
 **Header:** winuser.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnMeasureItem](../Topic/CWnd::OnMeasureItem.md)