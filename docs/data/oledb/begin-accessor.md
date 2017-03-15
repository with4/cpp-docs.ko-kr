---
title: "BEGIN_ACCESSOR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BEGIN_ACCESSOR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_ACCESSOR 매크로"
  - "BEGIN_ACCESSOR 매크로, 구문"
ms.assetid: 59d0ff3e-7cfd-4ce8-9a1c-d664c0892a52
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# BEGIN_ACCESSOR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marks the beginning of an accessor entry.  
  
## 구문  
  
```  
  
BEGIN_ACCESSOR(  
num  
,   
bAuto  
 )  
  
```  
  
#### 매개 변수  
 *num*  
 \[in\] The zero\-offset number for the accessor in this accessor map.  
  
 *bAuto*  
 \[in\] Specifies if this accessor is an auto accessor or a manual accessor.  If **true**, the accessor is auto; if **false**, the accessor is manual.  An auto accessor means data is fetched for you on move operations.  
  
## 설명  
 In the case of multiple accessors on a rowset, you need to specify `BEGIN_ACCESSOR_MAP` and use the `BEGIN_ACCESSOR` macro for each individual accessor.  The `BEGIN_ACCESSOR` macro is completed with the `END_ACCESSOR` macro.  The `BEGIN_ACCESSOR_MAP` macro is completed with the `END_ACCESSOR_MAP` macro.  
  
## 예제  
 See [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)