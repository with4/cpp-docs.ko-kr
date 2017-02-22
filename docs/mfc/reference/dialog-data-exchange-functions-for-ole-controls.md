---
title: "OLE 컨트롤에 대한 대화 상자 데이터 교환 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DDX(대화 상자 데이터 교환), OLE 지원"
  - "OLE 컨트롤, DDX 함수"
ms.assetid: 7ef1f288-ff65-40d4-aad2-5497bc00bb27
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# OLE 컨트롤에 대한 대화 상자 데이터 교환 함수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

This topic lists the DDX\_OC functions used to exchange data between a property of an OLE control in a dialog box, form view, or control view object and a data member of the dialog box, form view, or control view object.  
  
### DDX\_OC Functions  
  
|||  
|-|-|  
|[DDX\_OCBool](../Topic/DDX_OCBool.md)|Manages the transfer of **BOOL** data between a property of an OLE control and a **BOOL** data member.|  
|[DDX\_OCBoolRO](../Topic/DDX_OCBoolRO.md)|Manages the transfer of **BOOL** data between a read\-only property of an OLE control and a **BOOL** data member.|  
|[DDX\_OCColor](../Topic/DDX_OCColor.md)|Manages the transfer of **OLE\_COLOR** data between a property of an OLE control and an **OLE\_COLOR** data member.|  
|[DDX\_OCColorRO](../Topic/DDX_OCColorRO.md)|Manages the transfer of **OLE\_COLOR** data between a read\-only property of an OLE control and an **OLE\_COLOR** data member.|  
|[DDX\_OCFloat](../Topic/DDX_OCFloat.md)|Manages the transfer of **float** \(or **double**\) data between a property of an OLE control and a **float** \(or **double**\) data member.|  
|[DDX\_OCFloatRO](../Topic/DDX_OCFloatRO.md)|Manages the transfer of **float** \(or **double**\) data between a read\-only property of an OLE control and a **float** \(or **double**\) data member.|  
|[DDX\_OCInt](../Topic/DDX_OCInt.md)|Manages the transfer of `int` \(or **long**\) data between a property of an OLE control and an `int` \(or **long**\) data member.|  
|[DDX\_OCIntRO](../Topic/DDX_OCIntRO.md)|Manages the transfer of `int` \(or **long**\) data between a read\-only property of an OLE control and an `int` \(or **long**\) data member.|  
|[DDX\_OCShort](../Topic/DDX_OCShort.md)|Manages the transfer of **short** data between a property of an OLE control and a **short** data member.|  
|[DDX\_OCShortRO](../Topic/DDX_OCShortRO.md)|Manages the transfer of **short** data between a read\-only property of an OLE control and a **short** data member.|  
|[DDX\_OCText](../Topic/DDX_OCText.md)|Manages the transfer of **CString** data between a property of an OLE control and a **CString** data member.|  
|[DDX\_OCTextRO](../Topic/DDX_OCTextRO.md)|Manages the transfer of **CString** data between a read\-only property of an OLE control and a **CString** data member.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)