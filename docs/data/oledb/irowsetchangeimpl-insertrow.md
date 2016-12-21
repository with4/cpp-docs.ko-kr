---
title: "IRowsetChangeImpl::InsertRow | Microsoft Docs"
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
  - "ATL.IRowsetChangeImpl.InsertRow"
  - "InsertRow"
  - "IRowsetChangeImpl.InsertRow"
  - "ATL::IRowsetChangeImpl::InsertRow"
  - "IRowsetChangeImpl::InsertRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InsertRow 메서드"
ms.assetid: 93027be3-921e-438e-a19a-6e5aadb813eb
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetChangeImpl::InsertRow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Creates and initializes a new row in the rowset.  
  
## 구문  
  
```  
  
      STDMETHOD ( InsertRow )(  
   HCHAPTER /* hReserved */,  
   HACCESSOR hAccessor,  
   void* pData,  
   HROW* phRow   
);  
```  
  
#### 매개 변수  
 See [IRowsetChange::InsertRow](https://msdn.microsoft.com/en-us/library/ms716921.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetChangeImpl 클래스](../../data/oledb/irowsetchangeimpl-class.md)