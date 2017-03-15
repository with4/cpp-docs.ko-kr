---
title: "알고리즘(최신 C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 6f758d3c-a7c7-4a50-92bb-97b2f6d4ab27
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 알고리즘(최신 C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

최신 C\+\+ 프로그래밍의 경우 STL\([표준 템플릿 라이브러리](../standard-library/cpp-standard-library-reference.md)\)의 알고리즘을 사용하는 것이 좋습니다.  다음은 몇 가지 중요한 예입니다.  
  
-   `for_each`은 기본 통과 알고리즘입니다. \(또한 내부가 아닌 의미 체계용 `transform`입니다.  
  
-   `find_if`은 검색 알고리즘 기본값입니다.  
  
-   `sort`, `lower_bound` 및 기타 기본 정렬 및 검색 알고리즘.  
  
 비교 연산자를 작성하려면 가능한 경우 엄격한 `<`를 사용하고  *명명된 람다*를 사용합니다.  
  
```cpp  
  
auto comp = [](const widget& w1, const widget& w2)  
      { return w1.weight() < w2.weight(); }  
  
sort( v.begin(), v.end(), comp );  
  
auto i = lower_bound( v.begin(), v.end(), comp );  
  
```  
  
## 루프  
 가능하면 직접 작성한 루프 대신 범위 기반 `for` 루프 또는 알고리즘 호출 중 하나 또는 모두를 사용합니다.  `copy`, `transform`, `count_if`, `remove_if` 등은 의도가 명백하고 버그 없는 코드를 작성하기 쉽기 때문에 손으로 작성한 루프보다 훨씬 효과적입니다.  또한 많은 STL 알고리즘에는 이 알고리즘을 보다 효율적으로 만드는 구현 최적화가 있습니다.  
  
 다음과 같은 이전 C\+\+ 대신:  
  
```cpp  
  
for( auto i = strings.begin(); i != strings.end(); ++i ) {  
  :::  
  :::  
}  
  
auto i = v.begin();  
  
for( ; i != v.end(); ++i ) {  
  if (*i > x && *i < y) break;  
}  
  
```  
  
 다음과 같은 최신 C\+\+를 사용합니다.  
  
```cpp  
  
for_each( begin(strings), end(strings), [](string& s) {  
  :::  
  :::  
} );  
auto i = find_if( begin(v), end(v),  [=](int i) { return i > x && i < y; }  );  
  
```  
  
### 범위 기반 for 루프  
 범위 기반 `for` 루프는 STL 알고리즘이 아닌 C\+\+11 언어 기능입니다.  하지만 루프에 대한 이 설명에서 언급할 가치가 있습니다.  범위 기반의 `for` 루프는 `for` 키워드의 확장이며 값의 범위에서 반복하는 루프를 작성하는 편리하고 효율적인 방법을 제공합니다.  STL 컨테이너, 문자열 및 배열은 범위 기반의 `for` 루프를 위해 기본적으로 제공됩니다.  사용자 정의 형식에 대해 이 새로운 반복 구문을 사용하려면 다음 지원을 추가합니다.  
  
-   `begin` 메서드는 구조의 시작으로 반복기를 반환하고 `end` 메서드는 구조의 끝에 반복기를 반환합니다.  
  
-   이러한 방법에 대한 반복기에 대한 지원: `operator*`, `operator!=`, 및 `operator++`\(접두사 버전\).  
  
 이러한 메서드는 멤버 함수 또는 독립 실행형 함수일 수 있습니다.  
  
## 임의의 숫자  
 C\+\+ 커뮤니티에서 오랫동안 토론해 왔던 오래된 CRT `rand()` 함수에 많은 결함이 있다는 것은 비밀이 아닙니다.  최신 C\+\+에서는 이러한 단점을 처리할 필요가 없으며 신속하고 쉽게 만드는 도구는 [\<random\>](../standard-library/random.md)에 표시된 대로 STL에서 사용할 수 있으므로 자신의 균일하게 분산된 난수 생성기를 만들 필요가 없습니다.  
  
## 참고 항목  
 [C\+\+의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C\+\+ 언어 참조](../cpp/cpp-language-reference.md)   
 [C\+\+ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)