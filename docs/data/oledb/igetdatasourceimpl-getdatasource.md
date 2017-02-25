---
title: "IGetDataSourceImpl::GetDataSource | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetDataSource"
  - "IGetDataSourceImpl.GetDataSource"
  - "IGetDataSourceImpl::GetDataSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetDataSource 메서드"
ms.assetid: b70995d2-b951-452e-a2d4-fb3eb085886e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IGetDataSourceImpl::GetDataSource
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns an interface pointer on the data source object that created the session.  
  
## 구문  
  
```  
  
      STDMETHOD(GetDataSource)(   
   REFIID riid,   
   IUnknown ** ppDataSource    
);  
```  
  
#### 매개 변수  
 See [IGetDataSource::GetDataSource](https://msdn.microsoft.com/en-us/library/ms725443.aspx) in the *OLE DB Programmer's Reference*.  
  
## 설명  
 Useful if you need to access properties in the data source object.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IGetDataSourceImpl 클래스](../../data/oledb/igetdatasourceimpl-class.md)