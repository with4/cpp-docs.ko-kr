---
title: "IRowsetImpl::GetDBStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetDBStatus"
  - "IRowsetImpl.GetDBStatus"
  - "IRowsetImpl::GetDBStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetDBStatus 메서드"
ms.assetid: e51d8ee2-fc0c-4909-861c-026c94fb0dfc
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::GetDBStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns the `DBSTATUS` status flags for the specified field.  
  
## 구문  
  
```  
  
      virtual DBSTATUS GetDBStatus(  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnNames   
);  
```  
  
#### 매개 변수  
 \[in\] `currentRow`  
 The current row.  
  
 \[in\] `columnNames`  
 The column for which status is being requested.  
  
## 반환 값  
 The [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) flags for the column.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)