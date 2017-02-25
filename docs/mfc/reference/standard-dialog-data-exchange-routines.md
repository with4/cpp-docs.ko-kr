---
title: "표준 대화 상자 데이터 교환 루틴 | Microsoft Docs"
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
  - "표준 대화 상자, 데이터 교환 루틴"
ms.assetid: c6adb7f3-f9af-4cc5-a9ea-315c5b60ad1a
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# 표준 대화 상자 데이터 교환 루틴
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

This topic lists the standard dialog data exchange \(DDX\) routines used for common MFC dialog controls.  
  
> [!NOTE]
>  The standard dialog data exchange routines are defined in the header file afxdd\_.h.  However, applications should include afxwin.h.  
  
### DDX 함수  
  
|||  
|-|-|  
|[DDX\_CBIndex](../Topic/DDX_CBIndex.md)|Initializes or retrieves the index of the current selection of a combo box control.|  
|[DDX\_CBString](../Topic/DDX_CBString.md)|Initializes or retrieves the current contents of the edit field of a combo box control.|  
|[DDX\_CBStringExact](../Topic/DDX_CBStringExact.md)|Initializes or retrieves the current contents of the edit field of a combo box control.|  
|[DDX\_Check](../Topic/DDX_Check.md)|Initializes or retrieves the current state of a check box control.|  
|[DDX\_Control](../Topic/DDX_Control.md)|Subclasses a given control within a dialog box.|  
|[DDX\_DateTimeCtrl](../Topic/DDX_DateTimeCtrl.md)|Initializes or retrieves date and\/or time data of a date and time picker control.|  
|[DDX\_IPAddress](../Topic/DDX_IPAddress.md)|Initializes or retrieves the current value of an IP address control.|  
|[DDX\_LBIndex](../Topic/DDX_LBIndex.md)|Initializes or retrieves the index of the current selection of a list box control.|  
|[DDX\_LBString](../Topic/DDX_LBString.md)|Initializes or retrieves the current selection within a list box control.|  
|[DDX\_LBStringExact](../Topic/DDX_LBStringExact.md)|Initializes or retrieves the current selection within a list box control.|  
|[DDX\_MonthCalCtrl](../Topic/DDX_MonthCalCtrl.md)|Initializes or retrieves the current value of a month calendar control.|  
|[DDX\_Radio](../Topic/DDX_Radio.md)|Initializes or retrieves the 0\-based index of the radio control that is currently checked within a radio control group.|  
|[DDX\_Scroll](../Topic/DDX_Scroll.md)|Initializes or retrieves the current position of a scroll control's thumb.|  
|[DDX\_Slider](../Topic/DDX_Slider.md)|Initializes or retrieves the current position of a slider control's thumb.|  
|[DDX\_Text](../Topic/DDX_Text.md)|Initializes or retrieves the current value of an edit control.|  
  
## 참고 항목  
 [Standard Dialog Data Validation Routines](../../mfc/reference/standard-dialog-data-validation-routines.md)   
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)