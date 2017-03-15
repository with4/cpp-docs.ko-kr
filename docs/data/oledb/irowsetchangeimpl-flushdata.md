---
title: "IRowsetChangeImpl::FlushData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetChangeImpl::FlushData"
  - "IRowsetChangeImpl.FlushData"
  - "FlushData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FlushData 메서드"
ms.assetid: fd4bc73b-bc25-4aab-90d5-0bed92670c88
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetChangeImpl::FlushData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Overidden by provider to commit data to its store.  
  
## 구문  
  
```  
  
      HRESULT FlushData(  
   HROW hRowToFlush,  
   HACCESSOR hAccessorToFlush   
);  
```  
  
#### 매개 변수  
 *hRowToFlush*  
 \[in\] Handle to the rows for the data.  The type of this row is determined from the *RowClass* template argument of the `IRowsetImpl` class \(`CSimpleRow` by default\).  
  
 *hAccessorToFlush*  
 \[in\] Handle to the accessor, which contains binding information and type information in its **PROVIDER\_MAP** \(see [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)\).  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetChangeImpl 클래스](../../data/oledb/irowsetchangeimpl-class.md)