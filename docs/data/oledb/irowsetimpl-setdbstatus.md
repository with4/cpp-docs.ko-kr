---
title: "IRowsetImpl::SetDBStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetImpl.SetDBStatus"
  - "IRowsetImpl::SetDBStatus"
  - "SetDBStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetDBStatus 메서드"
ms.assetid: b73f526a-4fc6-4adb-9611-c3cca2cddb23
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::SetDBStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sets the `DBSTATUS` status flags for the specified field.  
  
## 구문  
  
```  
  
      virtual HRESULT SetDBStatus(  
   DBSTATUS* statusFlags,  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnInfo   
);  
```  
  
#### 매개 변수  
 `statusFlags`  
 The [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) flags to set for the column.  
  
 `currentRow`  
 The current row.  
  
 *columnInfo*  
 The column for which status is being set.  
  
## 반환 값  
 A standard `HRESULT` value.  
  
## 설명  
 The provider overrides this function to provide special processing for **DBSTATUS\_S\_ISNULL** and **DBSTATUS\_S\_DEFAULT**.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)