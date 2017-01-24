---
title: "COMPAREITEMSTRUCT 구조체 | Microsoft Docs"
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
  - "COMPAREITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COMPAREITEMSTRUCT 구조체"
ms.assetid: 4b7131a5-5c7d-4e98-aac7-e85650262b52
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COMPAREITEMSTRUCT 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `COMPAREITEMSTRUCT` structure supplies the identifiers and application\-supplied data for two items in a sorted, owner\-drawn list box or combo box.  
  
## 구문  
  
```  
  
      typedef struct tagCOMPAREITEMSTRUCT {  
    UINT   CtlType;  
    UINT   CtlID;  
    HWND   hwndItem;  
    UINT   itemID1;  
    DWORD  itemData1;  
    UINT   itemID2;  
    DWORD  itemData2;  
} COMPAREITEMSTRUCT;  
```  
  
#### 매개 변수  
 `CtlType`  
 **ODT\_LISTBOX** \(which specifies an owner\-draw list box\) or **ODT\_COMBOBOX** \(which specifies an owner\-draw combo box\).  
  
 `CtlID`  
 The control ID for the list box or combo box.  
  
 `hwndItem`  
 The window handle of the control.  
  
 *itemID1*  
 The index of the first item in the list box or combo box being compared.  
  
 *itemData1*  
 Application\-supplied data for the first item being compared.  This value was passed in the call that added the item to the combo or list box.  
  
 *itemID2*  
 Index of the second item in the list box or combo box being compared.  
  
 *itemData2*  
 Application\-supplied data for the second item being compared.  This value was passed in the call that added the item to the combo or list box.  
  
## 설명  
 Whenever an application adds a new item to an owner\-drawn list box or combo box created with the **CBS\_SORT** or **LBS\_SORT** style, Windows sends the owner a `WM_COMPAREITEM` message.  The `lParam` parameter of the message contains a long pointer to a `COMPAREITEMSTRUCT` structure.  Upon receiving the message, the owner compares the two items and returns a value indicating which item sorts before the other.  
  
## 요구 사항  
 **Header:** winuser.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCompareItem](../Topic/CWnd::OnCompareItem.md)