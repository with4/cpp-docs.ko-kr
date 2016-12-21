---
title: "BEGIN_COLUMN_MAP | Microsoft Docs"
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
  - "BEGIN_COLUMN_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_COLUMN_MAP 매크로"
ms.assetid: d6ffe633-e0da-4e33-8faa-f7f259d05420
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BEGIN_COLUMN_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

열 맵 항목의 시작을 표시합니다.  
  
## 구문  
  
```  
  
BEGIN_COLUMN_MAP(  
x  
 )  
  
```  
  
#### 매개 변수  
 *x*  
 \[in\] `CAccessor`에서 파생된 사용자 레코드 클래스의 이름입니다.  
  
## 설명  
 이 매크로는 행 집합에 단일 접근자가 있는 경우에 사용됩니다. 행 집합에 여러 접근자가 있는 경우 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)을 사용합니다.  
  
 `BEGIN_COLUMN_MAP` 매크로는 `END_COLUMN_MAP` 매크로로 완료됩니다. 이 매크로는 사용자 레코드에 하나의 접근자만 필요한 경우에 사용됩니다.  
  
 열은 바인딩하려면 행 집합의 필드에 해당합니다.  
  
## 예제  
 다음은 열 및 매개 변수 맵의 샘플입니다.  
  
 [!CODE [NVC_OLEDB_Consumer#16](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#16)]  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)