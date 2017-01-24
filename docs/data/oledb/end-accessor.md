---
title: "END_ACCESSOR | Microsoft Docs"
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
  - "END_ACCESSOR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "END_ACCESSOR 매크로"
ms.assetid: 26f74167-68c4-4909-a474-73dc7ebc9542
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# END_ACCESSOR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

접근자 항목의 끝을 표시합니다.  
  
## 구문  
  
```  
  
END_ACCESSOR( )  
  
```  
  
## 설명  
 행 집합에서 여러 접근자에 대하여  `BEGIN_ACCESSOR_MAP` 을 지정하고 각 개별 접근자에 대해 `BEGIN_ACCESSOR`  매크로를 사용해야합니다.   `BEGIN_ACCESSOR`  매크로는  `END_ACCESSOR`  매크로를 사용하여 완료됩니다.   `BEGIN_ACCESSOR_MAP`  매크로는  `END_ACCESSOR_MAP`  매크로를 사용하여 완료됩니다.  
  
## 예제  
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)을 참고하십시오.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)