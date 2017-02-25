---
title: "IRowsetLocateImpl::Hash | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetLocateImpl::Hash"
  - "IRowsetLocateImpl.Hash"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Hash 메서드"
ms.assetid: 7df4386d-80fb-4332-a85f-baae98cdc6e0
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetLocateImpl::Hash
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns hash values for the specified bookmarks.  
  
## 구문  
  
```  
  
      STDMETHOD ( Hash )(  
   HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmarks,  
   const DBBKMARK* rgcbBookmarks[],  
   const BYTE* rgpBookmarks[],  
   DBHASHVALUE rgHashValues[],  
   DBROWSTATUS rgBookmarkStatus[]   
);  
```  
  
#### 매개 변수  
 `hReserved`  
 \[in\] Corresponds to `hChapter` parameter to [IRowsetLocate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx).  
  
 For other parameters, see [IRowsetLocate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetLocateImpl 클래스](../../data/oledb/irowsetlocateimpl-class.md)