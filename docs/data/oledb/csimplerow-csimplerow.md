---
title: "CSimpleRow::CSimpleRow | Microsoft Docs"
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
  - "CSimpleRow"
  - "ATL::CSimpleRow::CSimpleRow"
  - "CSimpleRow.CSimpleRow"
  - "ATL.CSimpleRow.CSimpleRow"
  - "CSimpleRow::CSimpleRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleRow 클래스, 생성자"
ms.assetid: 3968a36c-b8bb-48df-bd06-3956e64b0842
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleRow::CSimpleRow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

생성자입니다.  
  
## 구문  
  
```  
  
      CSimpleRow(  
   DBCOUNTITEM iRowsetCur   
);  
```  
  
#### 매개 변수  
 `iRowsetCur`  
 \[in\] Index to the current rowset.  
  
## 설명  
 Sets [m\_iRowset](../../data/oledb/csimplerow-m-irowset.md) to `iRowsetCur`.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [CSimpleRow 클래스](../../data/oledb/csimplerow-class.md)