---
title: "CRowset::GetRowStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowset.GetRowStatus"
  - "ATL.CRowset<TAccessor>.GetRowStatus"
  - "ATL::CRowset<TAccessor>::GetRowStatus"
  - "CRowset::GetRowStatus"
  - "ATL::CRowset::GetRowStatus"
  - "CRowset<TAccessor>::GetRowStatus"
  - "ATL.CRowset.GetRowStatus"
  - "CRowset<TAccessor>.GetRowStatus"
  - "GetRowStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRowStatus 메서드"
ms.assetid: 7a29a235-cb7e-40c1-92ce-5441751febee
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::GetRowStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns the status of all rows.  
  
## 구문  
  
```  
  
      HRESULT GetRowStatus(   
   DBPENDINGSTATUS* pStatus    
) const throw( );  
```  
  
#### 매개 변수  
 `pStatus`  
 \[out\] A pointer to a location where `GetRowStatus` returns the status value.  See DBPENDINGSTATUS in the OLE DB Programmer's Reference.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 This method requires the optional interface `IRowsetUpdate`, which might not be supported on all providers; if this is the case, the method returns **E\_NOINTERFACE**.  You must also set **DBPROP\_IRowsetUpdate** to `VARIANT_TRUE` before calling **Open** on the table or command containing the rowset.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/en-us/library/ms724377.aspx)