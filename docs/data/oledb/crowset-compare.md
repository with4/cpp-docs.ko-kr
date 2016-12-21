---
title: "CRowset::Compare | Microsoft Docs"
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
  - "CRowset<TAccessor>.Compare"
  - "CRowset<TAccessor>::Compare"
  - "ATL.CRowset<TAccessor>.Compare"
  - "ATL::CRowset<TAccessor>::Compare"
  - "CRowset.Compare"
  - "ATL::CRowset::Compare"
  - "ATL.CRowset.Compare"
  - "CRowset::Compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Compare 메서드"
ms.assetid: a8117b40-7abd-4867-b0ba-eb9e9808204e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::Compare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compares two bookmarks using [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx).  
  
## 구문  
  
```  
  
      HRESULT Compare(   
   const CBookmarkBase& bookmark1,   
   const CBookmarkBase& bookmark2,   
   DBCOMPARE* pComparison    
) const throw( );  
```  
  
#### 매개 변수  
 *Bookmark1*  
 \[in\] The first bookmark to compare.  
  
 *Bookmark2*  
 \[in\] The second bookmark to compare.  
  
 `pComparison`  
 \[out\] A pointer to the result of the comparison.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 This method requires the optional interface `IRowsetLocate`, which might not be supported on all providers; if this is the case, the method returns **E\_NOINTERFACE**.  You must also set **DBPROP\_IRowsetLocate** to `VARIANT_TRUE` before calling **Open** on the table or command containing the rowset.  
  
 For information about using bookmarks in consumers, see [Using Bookmarks](../../data/oledb/using-bookmarks.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)