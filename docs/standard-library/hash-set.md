---
title: "&lt;hash_set&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<hash_set>"
  - "std.<hash_set>"
  - "std::<hash_set>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_set 헤더"
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# &lt;hash_set&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  이 헤더는 사용되지 않습니다. 다른 방법은 [\<unordered\_set\>](../standard-library/unordered-set.md)입니다.  
  
 컨테이너 템플릿 클래스 hash\_set 및 hash\_multiset와 각 클래스의 지원 템플릿을 정의합니다.  
  
## 구문  
  
```  
  
#include <hash_set>  
  
```  
  
## 설명  
 Visual C\+\+ .NET 2003에서 [\<hash\_map\>](../standard-library/hash-map.md) 및 [\<hash\_set\>](#vclrfhash_set_header_file) 헤더 파일의 멤버는 더 이상 std 네임스페이스에 없으며, 대신 stdext 네임스페이스로 이동되었습니다. 자세한 내용은 [stdext 네임스페이스](../standard-library/stdext-namespace.md)를 참조하십시오.  
  
### 연산자  
  
|Hash\_set 버전|Hash\_multiset 버전|설명|  
|------------------|-----------------------|--------|  
|[operator\!\=\(hash\_set\)](../Topic/operator!=%20\(hash_set\).md)|[operator\!\=\(hash\_multiset\)](../Topic/operator!=%20\(hash_multiset\).md)|연산자의 좌변에 있는 hash\_set 또는 hash\_multiset 개체가 우변에 있는 hash\_set 또는 hash\_multiset 개체와 같지 않은지 테스트합니다.|  
|[operator\=\=\(hash\_set\)](http://msdn.microsoft.com/ko-kr/791b95bd-f917-4716-aea6-add50badbfac)|[operator\=\=\(hash\_multiset\)](http://msdn.microsoft.com/ko-kr/cfa9aa0c-d5f6-403a-9441-35c2a4cee0fb)|연산자의 좌변에 있는 hash\_set 또는 hash\_multiset 개체가 우변에 있는 hash\_set 또는 hash\_multiset 개체와 같은지 테스트합니다.|  
  
### 특별 템플릿 함수  
  
|Hash\_set 버전|Hash\_multiset 버전|설명|  
|------------------|-----------------------|--------|  
|[swap\(hash\_set\)](../Topic/swap%20\(hash_set\).md)|[swap\(hash\_multiset\)](../Topic/swap%20\(hash_multiset\).md)|두 hash\_set 또는 hash\_multiset의 요소를 교환합니다.|  
  
### 클래스  
  
|||  
|-|-|  
|[hash\_compare 클래스](../standard-library/hash-compare-class.md)|해시 연관 컨테이너\(hash\_map, hash\_multimap, hash\_set 또는 hash\_multiset\) 중 하나에서 기본 **Traits** 매개 변수 개체로 사용하여 포함된 요소의 순서를 지정하고 해시할 수 있는 개체를 설명합니다.|  
|[hash\_set 클래스](../standard-library/hash-set-class.md)|포함된 요소의 값이 고유하고 키 값으로 사용된 컬렉션의 데이터를 빠르게 검색하고 저장하는 데 사용됩니다.|  
|[hash\_multiset 클래스](../standard-library/hash-multiset-class.md)|포함된 요소의 값이 고유하고 키 값으로 사용된 컬렉션의 데이터를 빠르게 검색하고 저장하는 데 사용됩니다.|  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)