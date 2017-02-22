---
title: "CRowset::GetApproximatePosition | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CRowset::GetApproximatePosition"
  - "ATL::CRowset<TAccessor>::GetApproximatePosition"
  - "CRowset.GetApproximatePosition"
  - "CRowset::GetApproximatePosition"
  - "GetApproximatePosition"
  - "ATL.CRowset.GetApproximatePosition"
  - "CRowset<TAccessor>::GetApproximatePosition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetApproximatePosition 메서드"
ms.assetid: 8f9ccd41-0590-468e-b202-6731d0f99d21
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::GetApproximatePosition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns the approximate position of a row corresponding to a bookmark.  
  
## 구문  
  
```  
  
      HRESULT GetApproximatePosition(   
   const CBookmarkBase* pBookmark,   
   DBCOUNTITEM* pPosition,   
   DBCOUNTITEM* pcRows    
) throw( );  
```  
  
#### 매개 변수  
 `pBookmark`  
 \[in\] A pointer to a bookmark that identifies the row whose position is to be found.  **NULL** if only the row count is required.  
  
 *pPosition*  
 \[out\] A pointer to the location where `GetApproximatePosition` returns the position of the row.  **NULL** if the position is not required.  
  
 `pcRows`  
 \[out\] A pointer to the location where `GetApproximatePosition` returns the total number of rows.  **NULL** if the row count is not required.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 This method requires the optional interface `IRowsetScroll`, which might not be supported on all providers; if this is the case, the method returns **E\_NOINTERFACE**.  You must also set **DBPROP\_IRowsetScroll** to `VARIANT_TRUE` before calling **Open** on the table or command containing the rowset.  
  
 For information about using bookmarks in consumers, see [Using Bookmarks](../../data/oledb/using-bookmarks.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [IRowsetScroll::GetApproximatePosition](https://msdn.microsoft.com/en-us/library/ms712901.aspx)