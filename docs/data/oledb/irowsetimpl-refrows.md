---
title: "IRowsetImpl::RefRows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IRowsetImpl::RefRows"
  - "ATL.IRowsetImpl.RefRows"
  - "IRowsetImpl.RefRows"
  - "RefRows"
  - "IRowsetImpl::RefRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RefRows 메서드"
ms.assetid: 1c048a2a-65dc-4bba-9c81-a23c0dc249c8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::RefRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) 와 [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md) 이 호출됨으로써 기존 행 핸들에 대해 참조 횟수를 증가시키거나 해제합니다.  
  
## 구문  
  
```  
  
      HRESULT RefRows(  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[],  
   BOOL bAdd   
);  
```  
  
#### 매개 변수  
 *OLE DB Programmer's Reference* 에서 [OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms719619.aspx)를 참조하십시오.  
  
## 반환 값  
 표준 `HRESULT` 값입니다.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)   
 [CSimpleRow 클래스](../../data/oledb/csimplerow-class.md)