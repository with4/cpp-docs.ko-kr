---
title: "CBulkRowset::MoveToBookmark | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBulkRowset<TAccessor>::MoveToBookmark"
  - "CBulkRowset.MoveToBookmark"
  - "MoveToBookmark"
  - "ATL.CBulkRowset.MoveToBookmark"
  - "CBulkRowset::MoveToBookmark"
  - "ATL::CBulkRowset<TAccessor>::MoveToBookmark"
  - "ATL::CBulkRowset::MoveToBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToBookmark 메서드"
ms.assetid: 76aab025-819e-4ecd-ae0a-d8d3fb2d2099
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CBulkRowset::MoveToBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fetches the row marked by a bookmark or the row at a specified offset \(`lSkip`\) from that bookmark.  
  
## 구문  
  
```  
  
      HRESULT MoveToBookmark(  
   const CBookmarkBase& bookmark,  
   DBCOUNTITEM lSkip = 0   
) throw( );  
```  
  
#### 매개 변수  
 `bookmark`  
 \[in\] A bookmark marking the location from which you want to fetch data.  
  
 `lSkip`  
 \[in\] The number count of rows from the bookmark to the target row.  If `lSkip` is zero, the first row fetched is the bookmarked row.  If `lSkip` is 1, the first row fetched is the row after the bookmarked row.  If `lSkip` is –1, the first row fetched is the row before the bookmarked row.  
  
## 반환 값  
 See [IRowset::GetData](https://msdn.microsoft.com/en-us/library/ms716988.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CBulkRowset 클래스](../../data/oledb/cbulkrowset-class.md)