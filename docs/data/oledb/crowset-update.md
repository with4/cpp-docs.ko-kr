---
title: "CRowset::Update | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowset.Update"
  - "ATL.CRowset.Update"
  - "ATL.CRowset<TAccessor>.Update"
  - "ATL::CRowset<TAccessor>::Update"
  - "CRowset<TAccessor>::Update"
  - "CRowset::Update"
  - "CRowset<TAccessor>.Update"
  - "ATL::CRowset::Update"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Update 메서드"
ms.assetid: cd5fedc8-2b85-4cb8-8c40-c79576316903
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::Update
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Transmits any pending changes made to the current row since the last fetch or **Update** call on it.  
  
## 구문  
  
```  
  
      HRESULT Update(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL    
) throw( );  
```  
  
#### 매개 변수  
 `pcRows`  
 \[out\] A pointer to the location where **Update** returns the number of rows it attempted to update, if required.  
  
 `phRow`  
 \[out\] A pointer to the location where **Update** returns the handle of the row it attempted to update.  No handle is returned if `phRow` is null.  
  
 `pStatus`  
 \[out\] A pointer to the location where **Update** returns the row status value.  No status is returned if `pStatus` is null.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 Transmits any pending changes made to the current row since that row was last fetched or updated \(using **Update** or [UpdateAll](../../data/oledb/crowset-updateall.md)\).  You typically call [SetData](../../data/oledb/crowset-setdata.md) to set data values in columns in a row, and then call **Update** to transmit those changes.  
  
 This method requires the optional interface `IRowsetUpdate`, which might not be supported on all providers; if this is the case, the method returns **E\_NOINTERFACE**.  You must also set **DBPROP\_IRowsetUpdate** to `VARIANT_TRUE` before calling **Open** on the table or command containing the rowset.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::UpdateAll](../../data/oledb/crowset-updateall.md)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)