---
title: "ICommandPropertiesImpl 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandPropertiesImpl"
  - "ATL.ICommandPropertiesImpl"
  - "ATL::ICommandPropertiesImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandPropertiesImpl 클래스"
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ICommandPropertiesImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Provides an implementation of the [ICommandProperties](https://msdn.microsoft.com/en-us/library/ms723044.aspx) interface.  
  
## 구문  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ICommandPropertiesImpl   
   : public ICommandProperties, public CUtlProps<PropClass>  
```  
  
#### 매개 변수  
 `T`  
 Your class, derived from  
  
 `PropClass`  
 Your properties class.  
  
## 멤버  
  
### Interface Methods  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/icommandpropertiesimpl-getproperties.md)|Returns the list of properties in the Rowset property group that are currently requested for the rowset.|  
|[SetProperties](../../data/oledb/icommandpropertiesimpl-setproperties.md)|Sets properties in the Rowset property group.|  
  
## 설명  
 This is mandatory on commands.  The implementation is provided by a static function defined by the [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md) macro.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)