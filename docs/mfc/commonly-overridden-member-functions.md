---
title: "일반적으로 재정의되는 멤버 함수 | Microsoft Docs"
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
  - "CDialog 클래스, 멤버"
  - "대화 상자 클래스, 일반적으로 재정의되는 멤버 함수"
  - "MFC 대화 상자, 멤버 함수 재정의"
  - "OnCancel 함수"
  - "OnInitDialog 함수"
  - "OnOK 함수"
  - "재정의, 대화 상자 클래스 멤버"
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 일반적으로 재정의되는 멤버 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The following table lists the most likely member functions to override in your `CDialog`\-derived class.  
  
### Commonly Overridden Member Functions of Class CDialog  
  
|멤버 함수|Message it responds to|Purpose of the override|  
|-----------|----------------------------|-----------------------------|  
|`OnInitDialog`|**WM\_INITDIALOG**|Initialize the dialog box's controls.|  
|`OnOK`|**BN\_CLICKED** for button **IDOK**|Respond when the user clicks the OK button.|  
|`OnCancel`|**BN\_CLICKED** for button **IDCANCEL**|Respond when the user clicks the Cancel button.|  
  
 `OnInitDialog`, `OnOK`, and `OnCancel` are virtual functions.  To override them, you declare an overriding function in your derived dialog class using the [Properties window](../Topic/Properties%20Window.md).  
  
 `OnInitDialog` is called just before the dialog box is displayed.  You must call the default `OnInitDialog` handler from your override — usually as the first action in the handler.  By default, `OnInitDialog` returns **TRUE** to indicate that the focus should be set to the first control in the dialog box.  
  
 `OnOK` is typically overridden for modeless but not modal dialog boxes.  If you override this handler for a modal dialog box, call the base class version from your override — to ensure that `EndDialog` is called — or call `EndDialog` yourself.  
  
 `OnCancel` is usually overridden for modeless dialog boxes.  
  
 For more information about these member functions, see class [CDialog](../mfc/reference/cdialog-class.md) in the *MFC Reference* and the discussion on [Life Cycle of a Dialog Box](../mfc/life-cycle-of-a-dialog-box.md).  
  
## 참고 항목  
 [대화 상자](../mfc/dialog-boxes.md)   
 [일반적으로 추가되는 멤버 함수](../mfc/commonly-added-member-functions.md)