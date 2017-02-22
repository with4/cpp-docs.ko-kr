---
title: "CBulkRowset 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CBulkRowset"
  - "ATL.CBulkRowset"
  - "ATL::CBulkRowset<TAccessor>"
  - "CBulkRowset"
  - "ATL.CBulkRowset<TAccessor>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBulkRowset 클래스"
ms.assetid: c6bde426-c543-4022-a98a-9519d9e2ae59
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CBulkRowset 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fetches and manipulates rows to work on data in bulk by retrieving multiple row handles with a single call.  
  
## 구문  
  
```  
template <class TAccessor>  
class CBulkRowset : public CRowset<TAccessor>  
```  
  
#### 매개 변수  
 `TAccessor`  
 An accessor class.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/cbulkrowset-addrefrows.md)|Increments the reference count.|  
|[CBulkRowset](../../data/oledb/cbulkrowset-cbulkrowset.md)|생성자입니다.|  
|[MoveFirst](../../data/oledb/cbulkrowset-movefirst.md)|Retrieves the first row of data, performing a new bulk fetch if necessary.|  
|[MoveLast](../../data/oledb/cbulkrowset-movelast.md)|Moves to the last row.|  
|[MoveNext](../../data/oledb/cbulkrowset-movenext.md)|Retrieves the next row of data.|  
|[MovePrev](../../data/oledb/cbulkrowset-moveprev.md)|Moves to the previous row.|  
|[MoveToBookmark](../../data/oledb/cbulkrowset-movetobookmark.md)|Fetches the row marked by a bookmark or the row at a specified offset from that bookmark.|  
|[MoveToRatio](../../data/oledb/cbulkrowset-movetoratio.md)|Fetches rows starting from a fractional position in the rowset.|  
|[ReleaseRows](../../data/oledb/cbulkrowset-releaserows.md)|Sets the current row \(**m\_nCurrentRow**\) to zero and releases all rows.|  
|[SetRows](../../data/oledb/cbulkrowset-setrows.md)|Sets the number of row handles to be retrieved by one call.|  
  
## 예제  
 The following example demonstrates use of the `CBulkRowset` class.  
  
 [!code-cpp[NVC_OLEDB_Consumer#1](../../data/oledb/codesnippet/CPP/cbulkrowset-class_1.cpp)]  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)