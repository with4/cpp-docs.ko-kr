---
title: "IDBPropertiesImpl::GetProperties | Microsoft Docs"
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
  - "IDBPropertiesImpl::GetProperties"
  - "IDBPropertiesImpl.GetProperties"
  - "GetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProperties 메서드"
ms.assetid: ab24aebd-366d-49a1-b49b-bb46c6d90f05
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBPropertiesImpl::GetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns the values of properties in the Data Source, Data Source Information, and Initialization property groups that are currently set on the data source object or the values of properties in the Initialization property group that are currently set on the enumerator.  
  
## 구문  
  
```  
  
      STDMETHOD(GetProperties)(   
   ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcProperties,   
   DBPROPSET ** prgProperties    
);  
```  
  
#### 매개 변수  
 See [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) in the *OLE DB Programmer's Reference*.  
  
 Some parameters correspond to *OLE DB Programmer's Reference* parameters of different names, which are described in **IDBProperties::GetProperties**:  
  
|OLE DB Template parameters|*OLE DB Programmer's Reference* parameters|  
|--------------------------------|------------------------------------------------|  
|`cPropertySets`|`cPropertyIDSets`|  
|`rgPropertySets`|`rgPropertyIDSets`|  
|*pcProperties*|*pcPropertySets*|  
|*prgProperties*|*prgPropertySets*|  
  
## 설명  
 If the provider is initialized, this method returns the values of properties in the **DBPROPSET\_DATASOURCE**, **DBPROPSET\_DATASOURCEINFO**, **DBPROPSET\_DBINIT** property groups that are currently set on the data source object.  If the provider is not initialized, it returns **DBPROPSET\_DBINIT** group properties only.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IDBPropertiesImpl 클래스](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)   
 [IDBPropertiesImpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)