---
title: "BEGIN_PROPERTY_SET_EX | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BEGIN_PROPERTY_SET_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_PROPERTY_SET_EX 매크로"
ms.assetid: c95e7fab-edce-47b8-b282-200e53a2ea8a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# BEGIN_PROPERTY_SET_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marks the beginning of a property set in a property set map.  
  
## 구문  
  
```  
  
BEGIN_PROPERTY_SET_EX(  
guid  
, flags )  
```  
  
#### 매개 변수  
 `guid`  
 \[in\] The property GUID.  
  
 `flags`  
 \[in\] **UPROPSET\_HIDDEN** for any property sets you do not wish to expose, or **UPROPSET\_PASSTHROUGH** for a provider exposing properties defined outside the scope of the provider.  
  
## 예제  
 See [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md).  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿에 대한 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)