---
title: "BEGIN_ACCESSOR_MAP | Microsoft Docs"
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
  - "BEGIN_ACCESSOR_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_ACCESSOR_MAP 매크로"
ms.assetid: e6d6e3a4-62fa-4e49-8c53-caf8c9d20091
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BEGIN_ACCESSOR_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

접근자 맵 항목의 시작을 표시합니다.  
  
## 구문  
  
```  
  
BEGIN_ACCESSOR_MAP(  
x  
,   
num  
 )  
  
```  
  
#### 매개 변수  
 *x*  
 \[in\] 사용자 레코드 클래스의 이름입니다.  
  
 *num*  
 \[in\] 이 접근자 맵에 있는 접근자 수입니다.  
  
## 설명  
 행 집합에 여러 접근자가 있는 경우 시작 부분에 `BEGIN_ACCESSOR_MAP`을 지정하고 각 접근자에 `BEGIN_ACCESSOR` 매크로를 사용해야 합니다.`BEGIN_ACCESSOR` 매크로는 `END_ACCESSOR` 매크로로 완료됩니다. 접근자 맵은 `END_ACCESSOR_MAP` 매크로로 완료됩니다.  
  
 사용자 레코드에 접근자가 하나만 있는 경우 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md) 매크로를 사용합니다.  
  
## 예제  
 [!CODE [NVC_OLEDB_Consumer#15](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#15)]  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)