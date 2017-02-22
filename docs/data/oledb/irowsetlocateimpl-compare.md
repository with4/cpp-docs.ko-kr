---
title: "IRowsetLocateImpl::Compare | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetLocateImpl.Compare"
  - "IRowsetLocateImpl::Compare"
  - "IRowsetLocateImpl.Compare"
  - "ATL::IRowsetLocateImpl::Compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Compare 메서드"
ms.assetid: 6f84052c-c68c-480a-982f-03748faa7d5d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetLocateImpl::Compare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compares two bookmarks.  
  
## 구문  
  
```  
  
      STDMETHOD ( Compare )(  
   HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmark1,  
   const BYTE* pBookmark1,  
   DBBKMARK cbBookmark2,  
   const BYTE* pBookmark2,  
   DBCOMPARE* pComparison   
);  
```  
  
#### 매개 변수  
 See [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx) in the *OLE DB Programmer's Reference*.  
  
## 설명  
 Either of the bookmarks can be a standard OLE DB\-defined [standard bookmark](https://msdn.microsoft.com/en-us/library/ms712954.aspx) \(**DBBMK\_FIRST**, **DBBMK\_LAST**, or **DBBMK\_INVALID**\).  The value returned in `pComparison` indicates the relationship between the two bookmarks:  
  
-   **DBCOMPARE\_LT** \(`cbBookmark1` is before `cbBookmark2`.\)  
  
-   **DBCOMPARE\_EQ** \(`cbBookmark1` is equal to `cbBookmark2`.\)  
  
-   **DBCOMPARE\_GT** \(`cbBookmark1` is after `cbBookmark2`.\)  
  
-   **DBCOMPARE\_NE** \(The bookmarks are equal and not ordered.\)  
  
-   **DBCOMPARE\_NOTCOMPARABLE** \(The bookmarks cannot be compared.\)  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetLocateImpl 클래스](../../data/oledb/irowsetlocateimpl-class.md)