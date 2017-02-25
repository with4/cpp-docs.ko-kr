---
title: "IRowsetImpl::CreateRow | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetImpl.CreateRow"
  - "ATL.IRowsetImpl.CreateRow"
  - "ATL::IRowsetImpl::CreateRow"
  - "CreateRow"
  - "IRowsetImpl::CreateRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateRow 메서드"
ms.assetid: b01c430c-9484-4fef-a6cf-a2e8d9d99130
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::CreateRow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

A helper method called by [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) to allocate a new **HROW**.  
  
## 구문  
  
```  
  
      HRESULT CreateRow(  
   DBROWOFFSET lRowsOffset,  
   DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows   
);  
```  
  
#### 매개 변수  
 *lRowsOffset*  
 Cursor position of the row being created.  
  
 *cRowsObtained*  
 A reference passed back to the user indicating the number of rows created.  
  
 *rgRows*  
 An array of **HROW**s returned to the caller with the newly created row handles.  
  
## 설명  
 If the row exists, this method calls [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) and returns.  Otherwise, it allocates a new instance of the RowClass template variable and adds it to [m\_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md).  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)