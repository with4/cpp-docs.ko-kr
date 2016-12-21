---
title: "IDBPropertiesImpl::SetProperties | Microsoft Docs"
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
  - "IDBPropertiesImpl.SetProperties"
  - "SetProperties"
  - "IDBPropertiesImpl::SetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetProperties 메서드"
ms.assetid: 2f9fc1de-7f35-4bca-bab3-7b427bf92c26
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBPropertiesImpl::SetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sets properties in the Data Source and Initialization property groups, for data source objects, or the Initialization property group, for enumerators.  
  
## 구문  
  
```  
  
      STDMETHOD(SetProperties)(   
   ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]    
);  
```  
  
#### 매개 변수  
 See [IDBProperties::SetProperties](https://msdn.microsoft.com/en-us/library/ms723049.aspx) in the *OLE DB Programmer's Reference*.  
  
## 설명  
 If the provider is initialized, this method sets the values of properties in the **DBPROPSET\_DATASOURCE**, **DBPROPSET\_DATASOURCEINFO**, **DBPROPSET\_DBINIT** property groups for the data source object.  If the provider is not initialized, it sets **DBPROPSET\_DBINIT** group properties only.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IDBPropertiesImpl 클래스](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)