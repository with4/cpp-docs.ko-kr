---
title: "표준 대화 상자 데이터 유효성 검사 루틴 | Microsoft Docs"
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
  - "표준 대화 상자, 데이터 유효성 검사 루틴"
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# 표준 대화 상자 데이터 유효성 검사 루틴
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

This topic lists the standard dialog data validation \(DDV\) routines used for common MFC dialog controls.  
  
> [!NOTE]
>  The standard dialog data exchange routines are defined in the header file afxdd\_.h.  However, applications should include afxwin.h.  
  
### DDV 함수  
  
|||  
|-|-|  
|[DDV\_MaxChars](../Topic/DDV_MaxChars.md)|Verifies the number of characters in a given control value does not exceed a given maximum.|  
|[DDV\_MinMaxByte](../Topic/DDV_MinMaxByte.md)|Verifies a given control value does not exceed a given **BYTE** range.|  
|[DDV\_MinMaxDateTime](../Topic/DDV_MinMaxDateTime.md)|Verifies a given control value does not exceed a given time range.|  
|[DDV\_MinMaxDouble](../Topic/DDV_MinMaxDouble.md)|Verifies a given control value does not exceed a given **double** range.|  
|[DDV\_MinMaxDWord](../Topic/DDV_MinMaxDWord.md)|Verifies a given control value does not exceed a given **DWORD** range.|  
|[DDV\_MinMaxFloat](../Topic/DDV_MinMaxFloat.md)|Verifies a given control value does not exceed a given **float** range.|  
|[DDV\_MinMaxInt](../Topic/DDV_MinMaxInt.md)|Verifies a given control value does not exceed a given **int** range.|  
|[DDV\_MinMaxLong](../Topic/DDV_MinMaxLong.md)|Verifies a given control value does not exceed a given **long** range.|  
|[DDV\_MinMaxLongLong](../Topic/DDV_MinMaxLongLong.md)|Verifies a given control value does not exceed a given **LONGLONG** range.|  
|[DDV\_MinMaxMonth](../Topic/DDV_MinMaxMonth.md)|Verifies a given control value does not exceed a given date range.|  
|[DDV\_MinMaxShort](../Topic/DDV_MinMaxShort.md)|Verifies a given control value does not exceed a given **short** range.|  
|[DDV\_MinMaxSlider](../Topic/DDV_MinMaxSlider.md)|Verifies a given slider control value falls within the given range.|  
|[DDV\_MinMaxUInt](../Topic/DDV_MinMaxUInt.md)|Verifies a given control value does not exceed a given **UINT** range.|  
|[DDV\_MinMaxULongLong](../Topic/DDV_MinMaxULongLong.md)|Verifies a given control value does not exceed a given **ULONGLONG** range.|  
  
## 참고 항목  
 [Standard Dialog Data Exchange Routines](../../mfc/reference/standard-dialog-data-exchange-routines.md)   
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)