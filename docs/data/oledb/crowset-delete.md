---
title: "CRowset::Delete | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CRowset::Delete"
  - "CRowset.Delete"
  - "CRowset::Delete"
  - "ATL.CRowset.Delete"
  - "ATL::CRowset<TAccessor>::Delete"
  - "CRowset<TAccessor>.Delete"
  - "CRowset<TAccessor>::Delete"
  - "ATL.CRowset<TAccessor>.Delete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Delete 메서드"
ms.assetid: 4feb4f7e-139f-489a-b7d5-ea6ec0058e0f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::Delete
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calls [IRowsetChange::DeleteRows](https://msdn.microsoft.com/en-us/library/ms724362.aspx) to delete the current row from the rowset.  
  
## 구문  
  
```  
  
HRESULT Delete( ) const throw( );  
  
```  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)