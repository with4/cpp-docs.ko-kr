---
title: "DELETEITEMSTRUCT 구조체 | Microsoft Docs"
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
  - "DELETEITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DELETEITEMSTRUCT 구조체"
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
caps.latest.revision: 13
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DELETEITEMSTRUCT 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `DELETEITEMSTRUCT` structure describes a deleted owner\-drawn list\-box or combo\-box item.  
  
## 구문  
  
```  
  
      typedef struct tagDELETEITEMSTRUCT { /* ditms */  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    HWND hwndItem;  
    UINT itemData;  
} DELETEITEMSTRUCT;  
```  
  
#### 매개 변수  
 `CtlType`  
 Specifies **ODT\_LISTBOX** \(an owner\-drawn list box\) or **ODT\_COMBOBOX** \(an owner\-drawn combo box\).  
  
 `CtlID`  
 Specifies the identifier of the list box or combo box.  
  
 `itemID`  
 Specifies index of the item in the list box or combo box being removed.  
  
 `hwndItem`  
 컨트롤을 식별합니다.  
  
 `itemData`  
 Specifies application\-defined data for the item.  This value is passed to the control in the **lParam** parameter of the message that adds the item to the list box or combo box.  
  
## 설명  
 When an item is removed from the list box or combo box or when the list box or combo box is destroyed, Windows sends the `WM_DELETEITEM` message to the owner for each deleted item.  The **lParam** parameter of the message contains a pointer to this structure.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../Topic/CWnd::OnDeleteItem.md)