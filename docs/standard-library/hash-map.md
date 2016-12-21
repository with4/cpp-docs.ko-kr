---
title: "&lt;hash_map&gt; | Microsoft Docs"
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
  - "std.<hash_map>"
  - "<hash_map>"
  - "std::<hash_map>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_map 헤더"
ms.assetid: 0765708a-a668-42a2-9800-654c857bdcc2
caps.latest.revision: 27
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;hash_map&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  이 헤더는 사용되지 않습니다. 다른 방법은 [\<unordered\_map\>](../standard-library/unordered-map.md)입니다.  
  
 컨테이너 템플릿 클래스 hash\_map 및 hash\_multimap과 지원 템플릿을 정의합니다.  
  
 Visual C\+\+ .NET 2003에서 [\<hash\_map\>](#vclrfhash_map_header_file) 및 [\<hash\_set\>](../standard-library/hash-set.md) 헤더 파일의 멤버는 더 이상 std 네임스페이스에 없으며, 대신 stdext 네임스페이스로 이동되었습니다. 자세한 내용은 [stdext 네임스페이스](../standard-library/stdext-namespace.md)를 참조하세요.  
  
## 구문  
  
```  
  
#include <hash_map>  
  
```  
  
### 연산자  
  
|Hash\_map 버전|Hash\_multimap 버전|설명|  
|------------------|-----------------------|--------|  
|[operator\!\=\(hash\_map\)](../Topic/operator!=%20\(hash_map\).md)|[operator\!\=\(hash\_multimap\)](../Topic/operator!=%20\(hash_multimap\).md)|연산자의 좌변에 있는 hash\_map 또는 hash\_multimap 개체가 우변에 있는 hash\_map 또는 hash\_multimap 개체와 같지 않은지 테스트합니다.|  
|[operator\=\=\(hash\_map\)](http://msdn.microsoft.com/ko-kr/f933cb1c-934d-43f5-aa9e-0b325eb95b85)|[operator\=\=\(hash\_multimap\)](http://msdn.microsoft.com/ko-kr/3fa378b1-0250-4e3f-a130-dc14103fc5e9)|연산자의 좌변에 있는 hash\_map 또는 hash\_multimap 개체가 우변에 있는 hash\_map 또는 hash\_multimap 개체와 같은지 테스트합니다.|  
  
### 특별 템플릿 함수  
  
|Hash\_map 버전|Hash\_multimap 버전|설명|  
|------------------|-----------------------|--------|  
|[swap\(hash\_map\)](../Topic/hash_map::swap.md)|[swap\(hash\_multimap\)](../Topic/hash_multimap::swap.md)|두 hash\_map 또는 hash\_multimap의 요소를 교환합니다.|  
  
### 클래스  
  
|||  
|-|-|  
|[hash\_compare 클래스](../standard-library/hash-compare-class.md)|해시 연관 컨테이너\(hash\_map, hash\_multimap, hash\_set 또는 hash\_multiset\) 중 하나에서 기본 **Traits** 매개 변수 개체로 사용하여 포함된 요소의 순서를 지정하고 해시할 수 있는 개체를 설명합니다.|  
|[value\_compare 클래스](../standard-library/value-compare-class.md)|키 값 비교를 통해 hash\_map의 요소를 비교하여 hash\_map 내의 상대 순서를 확인할 수 있는 함수 개체를 제공합니다.|  
|[hash\_map 클래스](../standard-library/hash-map-class.md)|각 요소가 값이 고유하고 연결된 데이터 값인 정렬 키가 있는 쌍인 컬렉션에서 데이터를 신속하게 저장하고 검색하는 데 사용됩니다.|  
|[hash\_multimap 클래스](../standard-library/hash-multimap-class.md)|각 요소가 값이 고유하고 연결된 데이터 값이 아니어도 되는 정렬 키가 있는 쌍인 컬렉션에서 데이터를 신속하게 저장하고 검색합니다.|  
  
## 요구 사항  
 **헤더:** \<hash\_map\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)