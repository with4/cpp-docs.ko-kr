---
title: "IRowsetUpdateImpl::Update | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IRowsetUpdateImpl::Update"
  - "IRowsetUpdateImpl::Update"
  - "IRowsetUpdateImpl.Update"
  - "ATL.IRowsetUpdateImpl.Update"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Update 메서드"
ms.assetid: 9ec6884d-aa9c-4871-a803-c048f162403c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetUpdateImpl::Update
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Transmits any changes made to the row since the last fetch or update.  
  
## 구문  
  
```  
  
      STDMETHOD ( Update )(  
   HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBCOUNTITEM* pcRows,  
   HROW** prgRows,  
   DBROWSTATUS** prgRowStatus   
);  
```  
  
#### 매개 변수  
 `hReserved`  
 \[in\] Corresponds to the `hChapter` parameter in [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx).  
  
 For other parameters, see [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx) in the *OLE DB Programmer's Reference*.  
  
## 설명  
 Changes are transmitted by calling [IRowsetChangeImpl::FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md).  The consumer must call [CRowset::Update](../../data/oledb/crowset-update.md) for the changes to take effect.  Set *prgRowstatus* to an appropriate value as described in [Row States](https://msdn.microsoft.com/en-us/library/ms722752.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetUpdateImpl 클래스](../../data/oledb/irowsetupdateimpl-class.md)