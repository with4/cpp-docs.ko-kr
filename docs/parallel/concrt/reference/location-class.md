---
title: "위치 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::location"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "location 클래스"
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
caps.latest.revision: 10
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 위치 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

하드웨어의 물리적 위치를 추상화 합니다.  
  
## 구문  
  
```  
class location;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[location::location 생성자](../Topic/location::location%20Constructor.md)|오버로드됨.  `location` 개체를 생성합니다.|  
|[location::~location 소멸자](../Topic/location::~location%20Destructor.md)|`location` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[location::current 메서드](../Topic/location::current%20Method.md)|호출한 스레드에서 실행 되는 구체적인 장소를 나타내는  `location` 개체를 반환합니다.|  
|[location::from\_numa\_node 메서드](../Topic/location::from_numa_node%20Method.md)|주어진 NUMA 노드를 나타내는  `location` 개체가 반환됩니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[location::operator\!\= 연산자](../Topic/location::operator!=%20Operator.md)|두 `location` 개체가 서로 다른 위치를 나타내는지 여부를 확인합니다.|  
|[location::operator\= 연산자](../Topic/location::operator=%20Operator.md)|다른 `location` 개체의 내용을 여기에 할당합니다.|  
|[location::operator\=\= 연산자](../Topic/location::operator==%20Operator.md)|두 `location` 개체가 동일한 위치를 나타내는지 여부를 나타냅니다.|  
  
## 상속 계층  
 `location`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)