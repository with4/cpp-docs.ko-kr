---
title: "IRowsetLocateImpl::GetRowsByBookmark | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetLocateImpl::GetRowsByBookmark"
  - "IRowsetLocateImpl.GetRowsByBookmark"
  - "GetRowsByBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRowsByBookmark 메서드"
ms.assetid: 07906e42-3582-427e-812a-aa19791e3c56
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetLocateImpl::GetRowsByBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정 된 책갈피와 일치 하는 하나 이상의 행을 반입 합니다.  
  
## 구문  
  
```  
  
      STDMETHOD ( GetRowsByBookmark )(  
   HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const DBBKMARK rgcbBookmarks[],  
   const BYTE* rgpBookmarks,  
   HROW rghRows[],  
   DBROWSTATUS* rgRowStatus[]   
);  
```  
  
#### 매개 변수  
 `hReserved`  
 \[in\] `hChapter` 매개 변수는 [IRowsetLocate::GetRowsByBookmark](https://msdn.microsoft.com/en-us/library/ms725420.aspx) 에 해당합니다.  
  
 다른 매개 변수에 대해 *OLE DB Programmer's Reference* 에서 [IRowsetLocate::GetRowsByBookmark](https://msdn.microsoft.com/en-us/library/ms725420.aspx) 를 참조하십시오.  
  
## 설명  
 책갈피는 사용자가 지정한 OLE DB [standard bookmarks](https://msdn.microsoft.com/en-us/library/ms712954.aspx) 또는 값일 수 있습니다. \(**DBBMK\_FIRST** 또는 **DBBMK\_LAST**\)  커서 위치를 변경 하지 않습니다.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetLocateImpl 클래스](../../data/oledb/irowsetlocateimpl-class.md)   
 [IRowsetLocateImpl::GetRowsAt](../../data/oledb/irowsetlocateimpl-getrowsat.md)