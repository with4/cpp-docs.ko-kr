---
title: "BEGIN_PROPERTY_SET | Microsoft Docs"
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
  - "BEGIN_PROPERTY_SET"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_PROPERTY_SET 매크로"
ms.assetid: 5995f21a-5161-4ecf-b9da-e2ff6754d40e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BEGIN_PROPERTY_SET
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marks the beginning of a property set in a property set map.  
  
## 구문  
  
```  
  
BEGIN_PROPERTY_SET(  
guid   
)  
  
```  
  
#### 매개 변수  
 `guid`  
 \[in\] The property GUID.  
  
## 예제  
 See [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md).  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿에 대한 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)