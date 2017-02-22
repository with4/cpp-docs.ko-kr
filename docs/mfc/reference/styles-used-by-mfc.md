---
title: "MFC에서 사용하는 스타일 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.styles"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "단추, MFC 도구 모음"
  - "콤보 상자, 스타일"
  - "스타일 편집[MFC]"
  - "확장 창 스타일"
  - "프레임 창, 스타일"
  - "목록 상자, 스타일"
  - "메시지 상자 스타일"
  - "스크롤 막대 스타일[MFC]"
  - "정적 스타일"
  - "스타일"
  - "스타일, MFC"
  - "창 스타일, MFC"
ms.assetid: d3b9af37-31b5-4c97-a8ad-189fd724b04c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# MFC에서 사용하는 스타일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Use the following styles when you create the corresponding MFC object.  In most cases, these styles are set in the `dwStyle` parameter of the class **Create** function.  
  
### MFC Styles  
  
|스타일|설명|  
|---------|--------|  
|[Button styles](../../mfc/reference/button-styles.md)|Applies to [CButton Class](../../mfc/reference/cbutton-class.md) objects, such as radio buttons, check boxes and pushbuttons.  Specify a combination of styles in the `dwStyle` parameter of [CButton::Create](../Topic/CButton::Create.md).|  
|[Combo\-box styles](../../mfc/reference/combo-box-styles.md)|Applies to [CComboBox Class](../../mfc/reference/ccombobox-class.md) objects.  Specify a combination of styles in the `dwStyle` parameter of [CComboBox::Create](../Topic/CComboBox::Create.md).|  
|[Edit styles](../../mfc/reference/edit-styles.md)|Applies to [CEdit Class](../../mfc/reference/cedit-class.md) objects.  Specify a combination of styles in the `dwStyle` parameter of [CEdit::Create](../Topic/CEdit::Create.md).|  
|[Frame\-window styles](../../mfc/reference/frame-window-styles-mfc.md)|Applies to [CFrameWnd Class](../../mfc/reference/cframewnd-class.md) objects.  Specify a combination of styles in the `dwStyle` parameter of [CFrameWnd::Create](../Topic/CFrameWnd::Create.md).|  
|[List\-box styles](../../mfc/reference/list-box-styles.md)|Applies to [CListBox Class](../../mfc/reference/clistbox-class.md) objects.  Specify a combination of styles in the `dwStyle` parameter of [CListBox::Create](../Topic/CListBox::Create.md).|  
|[Message\-box styles](../../mfc/reference/message-box-styles.md)|Applies to [AfxMessageBox](../Topic/AfxMessageBox.md) items.  Specify a combination of styles in the `nType` parameter of `AfxMessageBox`.|  
|[Scroll\-bar styles](../../mfc/reference/scroll-bar-styles.md)|Applies to [CScrollBar Class](../../mfc/reference/cscrollbar-class.md) objects.  Specify a combination of styles in the `dwStyle` parameter of [CScrollBar::Create](../Topic/CScrollBar::Create.md).|  
|[Static styles](../../mfc/reference/static-styles.md)|Applies to [CStatic Class](../../mfc/reference/cstatic-class.md) objects.  Specify a combination of styles in the `dwStyle` parameter of [CStatic::Create](../Topic/CStatic::Create.md).|  
|[창 스타일](../../mfc/reference/window-styles.md)|Applies to [CWnd Class](../../mfc/reference/cwnd-class.md) objects.  Specify a combination of styles in the `dwStyle` parameter of [CWnd::Create](../Topic/CWnd::Create.md) or [CWnd::CreateEx](../Topic/CWnd::CreateEx.md).|  
|[Extended window styles](../../mfc/reference/extended-window-styles.md)|Applies to [CWnd Class](../../mfc/reference/cwnd-class.md) objects.  Specify a combination of styles in the `dwExStyle` parameter of [CWnd::CreateEx](../Topic/CWnd::CreateEx.md).|  
  
## 참고 항목  
 [클래스 개요](../../mfc/class-library-overview.md)