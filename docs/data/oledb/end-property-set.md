---
title: "END_PROPERTY_SET | Microsoft Docs"
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
  - "END_PROPERTY_SET"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "END_PROPERTY_SET 매크로"
ms.assetid: c20a5c97-1d6e-41c5-be2f-244e008e87af
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# END_PROPERTY_SET
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marks the end of a property set.  
  
## 구문  
  
```  
  
END_PROPERTY_SET(  
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