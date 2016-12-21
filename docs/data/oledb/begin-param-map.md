---
title: "BEGIN_PARAM_MAP | Microsoft Docs"
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
  - "BEGIN_PARAM_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_PARAM_MAP 매크로"
ms.assetid: 32f3f70e-c7c6-4b80-ab98-e02c8eb3a894
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BEGIN_PARAM_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marks the beginning of the parameter map entries.  
  
## 구문  
  
```  
  
BEGIN_PARAM_MAP(  
x  
 )  
  
```  
  
#### 매개 변수  
 *x*  
 \[in\] The name of the user record class.  
  
## 설명  
 Parameters are used by [commands](https://msdn.microsoft.com/en-us/library/ms724608.aspx).  
  
## 예제  
 See the example for the [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md) macro.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [END\_PARAM\_MAP](../../data/oledb/end-param-map.md)   
 [SET\_PARAM\_TYPE](../../data/oledb/set-param-type.md)