---
title: "알고리즘 (최신 c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 6f758d3c-a7c7-4a50-92bb-97b2f6d4ab27
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d89f6b5116459018cb50eb58b976f6f853ed088
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="algorithms-modern-c"></a>알고리즘(최신 C++)
최신 c + + 프로그래밍에 대 한 알고리즘에 사용 하는 권장는 [c + + 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)합니다. 다음은 몇 가지 중요 한 예입니다.  
  
-   `for_each`은 기본 탐색 알고리즘입니다. (또한 `transform` not 내부 의미 체계에 대 한 합니다.)  
  
-   `find_if`기본 검색 알고리즘은입니다.  
  
-   `sort``lower_bound`, 및 기타 기본 정렬 및 알고리즘을 검색 합니다.  
  
 경우 비교 연산자를 작성 하려면 사용 하 여 엄격한 `<` 사용 하 여 *람다 식은 명명 된* 할 수 있습니다.  
  
```cpp  
auto comp = [](const widget& w1, const widget& w2)  
      { return w1.weight() < w2.weight(); }  
  
sort( v.begin(), v.end(), comp );  
  
auto i = lower_bound( v.begin(), v.end(), comp );  
```  
  
## <a name="loops"></a>루프  
 가능한 경우 사용 하 여 범위 기반 `for` 루프 또는 알고리즘 호출 또는 직접 작성 된 루프. 대신 둘 다`copy`, `transform`, `count_if`, `remove_if`, 필기 루프 보다 훨씬 효율적으로 같은 나머지는 때문에 의도 분명 한 것은 쉽게 버그 없이 코드를 작성 하 고 있습니다. 또한 많은 c + + 표준 라이브러리 알고리즘 구현 최적화에 보다 효율적으로 만들를 두 개.  
  
 대신 다음과 같이 이전 c + +:  
  
```cpp  
for ( auto i = strings.begin(); i != strings.end(); ++i ) {  
   /* ... */  
}  
  
auto i = v.begin();  
  
for ( ; i != v.end(); ++i ) {  
  if (*i > x && *i < y) break;  
}  
```  
  
 다음과 같은 최신 c + +를 사용 합니다.  
  
```cpp  
for_each( begin(strings), end(strings), [](string& s) {  
   // ...  
} );  
  
auto i = find_if( begin(v), end(v),  [=](int i) { return i > x && i < y; } );  
```  
  
### <a name="range-based-for-loops"></a>범위 기반 for 루프  
 범위 기반 `for` 루프는 C + + 11 언어 기능을 c + + 표준 라이브러리 알고리즘 없습니다. 하지만이 설명에서 루프에 대 한 내용을 기울이게 합니다. 범위 기반 `for` 루프의 확장 되는 `for` 키워드 고 값의 범위에 대해 반복 하는 루프를 작성 하는 편리 하 고 효율적인 방법을 제공 합니다. C + + 표준 라이브러리 컨테이너, 문자열 및 배열에 대 한 기본으로 제공 되는 범위 기반 `for` 루프입니다. 사용자 정의 유형에 대 한 새 반복 구문의 사용 하려면 다음과 같은 지원 추가:  
  
-   A `begin` 구조의 시작 부분에는 반복기를 반환 하는 메서드 및 `end` 구조체의 끝 반복기를 반환 하는 메서드입니다.  
  
-   이러한 방법에 대 한 반복기에 대 한 지원: `operator*`, `operator!=`, 및 `operator++` (접두사 버전).  
  
 이러한 메서드는 멤버 또는 독립 실행형 함수 일 수 있습니다.  
  
## <a name="random-numbers"></a>난수  
 하는 이전 CRT `rand()` 함수에는 많은 결함을 c + + 커뮤니티에서 길게 논의해 왔습니다. 최신 c + +에서 이러한 단점을 다룰 필요가 없습니다-나 사용자 고유의 균등된 난수 생성기를 만들 않아도- 와같이빠르고쉽게만드는도구를c++표준라이브러리를사용할수있으므로[ \<임의 >](../standard-library/random.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + +의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C + + 언어 참조](../cpp/cpp-language-reference.md)   
 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)