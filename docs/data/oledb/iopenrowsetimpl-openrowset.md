---
title: "IOpenRowsetImpl::OpenRowset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OpenRowset"
  - "IOpenRowsetImpl::OpenRowset"
  - "IOpenRowsetImpl.OpenRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenRowset 메서드"
ms.assetid: 2ece8d6c-d165-4f1d-b155-8609bbb60eb6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IOpenRowsetImpl::OpenRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Opens and returns a rowset that includes all rows from a single base table or index.  
  
## 구문  
  
```  
  
      HRESULT OpenRowset(  
   IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset   
);  
```  
  
#### 매개 변수  
 See [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) in the *OLE DB Programmer's Reference*.  
  
## 설명  
 This method is not found in ATLDB.H.  It is created by the ATL Object Wizard when you create a provider.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IOpenRowsetImpl 클래스](../../data/oledb/iopenrowsetimpl-class.md)