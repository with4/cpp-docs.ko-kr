---
title: "IRowsetInfoImpl::GetReferencedRowset | Microsoft Docs"
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
  - "ATL::IRowsetInfoImpl::GetReferencedRowset"
  - "GetReferencedRowset"
  - "ATL.IRowsetInfoImpl.GetReferencedRowset"
  - "IRowsetInfoImpl.GetReferencedRowset"
  - "IRowsetInfoImpl::GetReferencedRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetReferencedRowset 메서드"
ms.assetid: 94d2155c-9da0-4c19-a37c-bc35716359fd
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetInfoImpl::GetReferencedRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns an interface pointer to the rowset to which a bookmark applies.  
  
## 구문  
  
```  
  
      STDMETHOD ( GetReferencedRowset )(  
   DBORDINAL iOrdinal,  
   REFIID riid,  
   IUnknown** ppReferencedRowset   
);  
```  
  
#### 매개 변수  
 See [IRowsetInfo::GetReferencedRowset](https://msdn.microsoft.com/en-us/library/ms721145.aspx) in the *OLE DB Programmer's Reference*.  The *iOrdinal* parameter must be a bookmark column.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetInfoImpl 클래스](../../data/oledb/irowsetinfoimpl-class.md)   
 [IRowsetInfoImpl::GetSpecification](../../data/oledb/irowsetinfoimpl-getspecification.md)   
 [IRowsetInfoImpl::GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)