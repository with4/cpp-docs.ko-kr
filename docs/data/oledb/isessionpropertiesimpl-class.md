---
title: "ISessionPropertiesImpl 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ISessionPropertiesImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISessionPropertiesImpl 클래스"
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ISessionPropertiesImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Provides an implementation of the [ISessionProperties](https://msdn.microsoft.com/en-us/library/ms713721.aspx) interface.  
  
## 구문  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
#### 매개 변수  
 `T`  
 Your class, derived from `ISessionPropertiesImpl`.  
  
 `PropClass`  
 A user\-definable property class that defaults to `T`.  
  
## 멤버  
  
### Interface Methods  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/isessionpropertiesimpl-getproperties.md)|Returns the list of properties in the Session property group that are currently set on the session.|  
|[SetProperties](../../data/oledb/isessionpropertiesimpl-setproperties.md)|Sets properties in the Session property group.|  
  
## 설명  
 A mandatory interface on sessions.  This class implements session properties by calling a static function defined by the [property set map](../../data/oledb/begin-propset-map.md).  The property set map should be specified in your session class.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)