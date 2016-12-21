---
title: "IRowsetInfoImpl::GetProperties | Microsoft Docs"
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
  - "ATL.IRowsetInfoImpl.GetProperties"
  - "IRowsetInfoImpl.GetProperties"
  - "ATL::IRowsetInfoImpl::GetProperties"
  - "IRowsetInfoImpl::GetProperties"
  - "GetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProperties 메서드"
ms.assetid: 62c12063-28e0-4a06-ad4d-21c5c1e9ccea
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetInfoImpl::GetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns the current settings for properties in the **DBPROPSET\_ROWSET** group.  
  
## 구문  
  
```  
  
      STDMETHOD ( GetProperties )(  
   const ULONG cPropertyIDSets,  
   const DBPROPIDSET rgPropertyIDSets[],  
   ULONG* pcPropertySets,  
   DBPROPSET** prgPropertySets   
);  
```  
  
#### 매개 변수  
 See [IRowsetInfo::GetProperties](https://msdn.microsoft.com/en-us/library/ms719611.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetInfoImpl 클래스](../../data/oledb/irowsetinfoimpl-class.md)   
 [IRowsetInfoImpl::GetReferencedRowset](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)   
 [IRowsetInfoImpl::GetSpecification](../../data/oledb/irowsetinfoimpl-getspecification.md)