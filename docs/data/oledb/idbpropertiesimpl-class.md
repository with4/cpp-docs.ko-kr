---
title: "IDBPropertiesImpl 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBPropertiesImpl"
  - "ATL.IDBPropertiesImpl"
  - "ATL.IDBPropertiesImpl<T>"
  - "ATL::IDBPropertiesImpl<T>"
  - "ATL::IDBPropertiesImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDBPropertiesImpl 클래스"
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBPropertiesImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Provides an implementation for the `IDBProperties` interface.  
  
## 구문  
  
```  
template <class T>   
class ATL_NO_VTABLE IDBPropertiesImpl   
   : public IDBProperties, public CUtlProps<T>  
```  
  
#### 매개 변수  
 `T`  
 Your class, derived from `IDBPropertiesImpl`.  
  
## 멤버  
  
### Interface Methods  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)|Returns the values of properties in the Data Source, Data Source Information, and Initialization property groups that are currently set on the data source object or the values of properties in the Initialization property group that are currently set on the enumerator.|  
|[GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)|Returns information about all properties supported by the provider.|  
|[SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)|Sets properties in the Data Source and Initialization property groups, for data source objects, or the Initialization property group, for enumerators.|  
  
## 설명  
 [IDBProperties](https://msdn.microsoft.com/en-us/library/ms719607.aspx) is a mandatory interface for data source objects and an optional interface for enumerators.  However, if an enumerator exposes [IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx), it must expose `IDBProperties`.  `IDBPropertiesImpl` implements `IDBProperties` by using a static function defined by [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md).  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)