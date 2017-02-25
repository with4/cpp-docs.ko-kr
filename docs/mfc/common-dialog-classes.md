---
title: "일반 대화 상자 클래스 | Microsoft Docs"
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
  - "일반 대화 상자[C++]"
  - "일반 대화 상자[C++], 일반 대화 상자 클래스"
  - "일반 대화 상자 클래스[C++]"
  - "대화 상자[C++], Windows 일반 대화 상자"
  - "대화 상자 클래스[C++]"
  - "대화 상자 클래스[C++], 일반"
  - "MFC 대화 상자, Windows 일반 대화 상자"
  - "Windows 일반 대화 상자[C++]"
ms.assetid: 5c4f6443-896c-4b05-a7df-8169fdadc71d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 일반 대화 상자 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In addition to class [CDialog](../mfc/reference/cdialog-class.md), MFC supplies several classes derived from `CDialog` that encapsulate commonly used dialog boxes, as shown in the following table.  The dialog boxes encapsulated are called the "common dialog boxes" and are part of the Windows common dialog library \(COMMDLG.DLL\).  The dialog\-template resources and code for these classes are provided in the Windows common dialog boxes that are part of Windows versions 3.1 and later.  
  
### Common Dialog Classes  
  
|Derived dialog class|용도|  
|--------------------------|--------|  
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|Lets user select colors.|  
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|Lets user select a filename to open or to save.|  
|[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|Lets user initiate a find or replace operation in a text file.|  
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|Lets user specify a font.|  
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|Lets user specify information for a print job.|  
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Windows 2000 print property sheet.|  
  
 For more information about the common dialog classes, see the individual class names in the *MFC Reference*.  MFC also supplies a number of standard dialog classes used for OLE.  For information about these classes, see the base class, [COleDialog](../mfc/reference/coledialog-class.md), in the *MFC Reference*.  
  
 Three other classes in MFC have dialog\-like characteristics.  For information about classes [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), and [CDaoRecordView](../mfc/reference/cdaorecordview-class.md), see the classes in the *MFC Reference*.  For information about class [CDialogBar](../mfc/reference/cdialogbar-class.md), see [Dialog Bars](../mfc/dialog-bars.md).  
  
## 참고 항목  
 [대화 상자](../mfc/dialog-boxes.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)   
 [OLE의 대화 상자](../mfc/dialog-boxes-in-ole.md)