---
title: "&lt; 맵 &gt; | Microsoft Docs"
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
  - "std::<map>"
  - "std.<map>"
  - "<map>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "map 헤더"
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; 맵 &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컨테이너 템플릿 클래스 map 및 multimap과 지원 템플릿을 정의합니다.  
  
## 구문  
  
```  
  
#include <map>  
  
```  
  
## 멤버  
  
### 연산자  
  
|map 버전|multimap 버전|설명|  
|------------|-----------------|--------|  
|[operator\!\= \(map\)](../Topic/operator!=%20\(map\).md)|[operator\!\= \(multimap\)](../Topic/operator!=%20\(multimap\).md)|연산자의 좌변에 있는 map 또는 multimap 개체가 우변에 있는 map 또는 multimap 개체와 같지 않은지 테스트합니다.|  
|[operator\< \(map\)](../Topic/operator==%20\(map\).md)|[operator\< \(multimap\)](../Topic/operator==%20\(multimap\).md)|연산자의 좌변에 있는 map 또는 multimap 개체가 우변에 있는 map 또는 multimap 개체보다 작은지 테스트합니다.|  
|[operator\<\= \(map\)](../Topic/operator%3C%20\(map\).md)|[operator\<\= \(multimap\)](../Topic/operator%3C%20\(multimap\).md)|연산자의 좌변에 있는 map 또는 multimap 개체가 우변에 있는 map 또는 multimap 개체보다 작거나 같은지 테스트합니다.|  
|[operator\=\= \(map\)](../Topic/operator%3C=%20\(map\).md)|[operator\=\= \(multimap\)](../Topic/operator%3C=%20\(multimap\).md)|연산자의 좌변에 있는 map 또는 multimap 개체가 우변에 있는 map 또는 multimap 개체와 같은지 테스트합니다.|  
|[operator\> \(map\)](../Topic/operator%3E%20\(map\).md)|[operator\> \(multimap\)](../Topic/operator%3E%20\(multimap\).md)|연산자의 좌변에 있는 map 또는 multimap 개체가 우변에 있는 map 또는 multimap 개체보다 큰지 테스트합니다.|  
|[operator\>\= \(map\)](../Topic/operator%3E=%20\(map\).md)|[operator\>\= \(multimap\)](../Topic/operator%3E=%20\(multimap\).md)|연산자의 좌변에 있는 map 또는 multimap 개체가 우변에 있는 map 또는 multimap 개체보다 크거나 같은지 테스트합니다.|  
  
### 특별 템플릿 함수  
  
|map 버전|multimap 버전|설명|  
|------------|-----------------|--------|  
|[swap\(map\)](../Topic/swap%20\(map\).md)|[swap\(multimap\)](../Topic/swap%20\(multimap\).md)|두 map 또는 multimap의 요소를 교환합니다.|  
  
### 클래스  
  
|||  
|-|-|  
|[value\_compare 클래스](../standard-library/value-compare-class-map.md)|키 값 비교를 통해 맵의 요소를 비교하여 map 내의 상대 순서를 확인할 수 있는 함수 개체를 제공합니다.|  
|[map 클래스](../standard-library/map-class.md)|각 요소에 데이터가 자동 정렬되는 기준인 고유한 키가 있는 컬렉션에서 데이터를 저장 및 검색하는 데 사용됩니다.|  
|[multimap 클래스](../standard-library/multimap-class.md)|각 요소에 데이터가 자동 정렬되는 기준인 키가 있고 키 값이 고유하지 않아도 되는 컬렉션에서 데이터를 저장 및 검색하는 데 사용됩니다.|  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)