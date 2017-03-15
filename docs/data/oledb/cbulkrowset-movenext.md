---
title: "CBulkRowset::MoveNext | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CBulkRowset<TAccessor>.MoveNext"
  - "ATL::CBulkRowset::MoveNext"
  - "CBulkRowset::MoveNext"
  - "ATL.CBulkRowset.MoveNext"
  - "CBulkRowset.MoveNext"
  - "ATL::CBulkRowset<TAccessor>::MoveNext"
  - "CBulkRowset<TAccessor>.MoveNext"
  - "CBulkRowset<TAccessor>::MoveNext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveNext 메서드"
ms.assetid: 788f3344-cf60-4af1-8f5f-0098c8d1a3f0
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CBulkRowset::MoveNext
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves the next row of data.  
  
## 구문  
  
```  
  
HRESULT MoveNext( ) throw( );  
  
```  
  
## 반환 값  
 A standard `HRESULT`.  When the end of the rowset has been reached, returns **DB\_S\_ENDOFROWSET**.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CBulkRowset 클래스](../../data/oledb/cbulkrowset-class.md)