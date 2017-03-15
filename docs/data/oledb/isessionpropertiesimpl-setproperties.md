---
title: "ISessionPropertiesImpl::SetProperties | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ISessionPropertiesImpl.SetProperties"
  - "SetProperties"
  - "ISessionPropertiesImpl::SetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetProperties 메서드"
ms.assetid: 2e1219ed-0e1e-460e-84d6-031acfbfd3d2
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ISessionPropertiesImpl::SetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sets properties in the **DBPROPSET\_SESSION** property group.  
  
## 구문  
  
```  
  
      STDMETHOD(SetProperties)(   
   ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]    
);  
```  
  
#### 매개 변수  
 See [ISessionProperties::SetProperties](https://msdn.microsoft.com/en-us/library/ms714405.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [ISessionPropertiesImpl 클래스](../../data/oledb/isessionpropertiesimpl-class.md)   
 [ISessionPropertiesImpl::GetProperties](../../data/oledb/isessionpropertiesimpl-getproperties.md)