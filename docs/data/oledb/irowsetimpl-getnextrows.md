---
title: "IRowsetImpl::GetNextRows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetNextRows"
  - "ATL.IRowsetImpl.GetNextRows"
  - "ATL::IRowsetImpl::GetNextRows"
  - "IRowsetImpl::GetNextRows"
  - "IRowsetImpl.GetNextRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetNextRows 메서드"
ms.assetid: 1c0975d6-d770-4884-830b-6986c6fa8e65
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::GetNextRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이전 위치를 기억하여 행을 순서대로 페치합니다.  
  
## 구문  
  
```  
  
      STDMETHOD( GetNextRows )(  
   HCHAPTER hReserved,  
   DBROWOFFSET lRowsOffset,  
   DBROWCOUNT cRows,  
   DBCOUNTITEM* pcRowsObtained,  
   HROW** prghRows   
);  
```  
  
#### 매개 변수  
 *OLE DB Programmer's Reference* 에 있는 [IRowset::GetNextRows](https://msdn.microsoft.com/en-us/library/ms709827.aspx)를 참고하세요.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)   
 [IRowsetImpl::AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)   
 [IRowsetImpl::ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)