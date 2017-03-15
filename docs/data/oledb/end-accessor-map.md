---
title: "END_ACCESSOR_MAP | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "END_ACCESSOR_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "END_ACCESSOR_MAP 매크로"
ms.assetid: ede813c7-46c9-48a6-aa1a-8ebf38e92023
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# END_ACCESSOR_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marks the end of the accessor map entries.  
  
## 구문  
  
```  
  
END_ACCESSOR_MAP( )  
  
```  
  
## 설명  
 For multiple accessors on a rowset, you need to specify `BEGIN_ACCESSOR_MAP` and use the `BEGIN_ACCESSOR` macro for each individual accessor.  The `BEGIN_ACCESSOR` macro is completed with the `END_ACCESSOR` macro.  The `BEGIN_ACCESSOR_MAP` macro is completed with the `END_ACCESSOR_MAP` macro.  
  
## 예제  
 See [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)