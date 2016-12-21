---
title: "CBulkRowset::ReleaseRows | Microsoft Docs"
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
  - "ReleaseRows"
  - "ATL.CBulkRowset<TAccessor>.ReleaseRows"
  - "ATL::CBulkRowset<TAccessor>::ReleaseRows"
  - "ATL.CBulkRowset.ReleaseRows"
  - "CBulkRowset<TAccessor>::ReleaseRows"
  - "ATL::CBulkRowset::ReleaseRows"
  - "CBulkRowset::ReleaseRows"
  - "CBulkRowset.ReleaseRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseRows 메서드"
ms.assetid: ba48aff3-0887-47ba-aed7-7ff28fa1c4a8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBulkRowset::ReleaseRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calls [IRowset::ReleaseRows](https://msdn.microsoft.com/en-us/library/ms719771.aspx) to decrement the reference count for all rows currently retrieved from the bulk rowset.  
  
## 구문  
  
```  
  
HRESULT ReleaseRows( ) throw( );  
  
```  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CBulkRowset 클래스](../../data/oledb/cbulkrowset-class.md)   
 [CBulkRowset::AddRefRows](../../data/oledb/cbulkrowset-addrefrows.md)