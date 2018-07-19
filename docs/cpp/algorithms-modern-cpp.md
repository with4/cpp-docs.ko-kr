---
title: 알고리즘 (최신 c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6f758d3c-a7c7-4a50-92bb-97b2f6d4ab27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ce233b4ffa33873b752ebc409fb8570856acbff
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940201"
---
# <a name="algorithms-modern-c"></a>알고리즘(최신 C++)
최신 c + + 프로그래밍에 대 한 것이 좋습니다에 알고리즘을 사용 하 여 [c + + 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)합니다. 몇 가지 중요 한 예는 다음과 같습니다.  
  
-   **for_each**은 기본 통과 알고리즘입니다. (또한 **변환** not-전체 의미 체계에 대 한 합니다.)  
  
-   **find_if**은 기본 검색 알고리즘입니다.  
  
-   **정렬**하십시오 **lower_bound**, 및 기타 기본 정렬 및 검색 알고리즘.  
  
 비교 연산자를 작성, 사용 하 여 엄격한 **<** 사용 하 여 *명명 된 람다* 수 있습니다.  
  
```cpp  
auto comp = [](const widget& w1, const widget& w2)  
      { return w1.weight() < w2.weight(); }  
  
sort( v.begin(), v.end(), comp );  
  
auto i = lower_bound( v.begin(), v.end(), comp );  
```  
  
## <a name="loops"></a>루프  
 범위를 기준으로 사용 가능한 경우 **에 대 한** 루프 또는 알고리즘 호출 또는 둘 다를 직접 작성 한 루프 대신 합니다. **복사본**, **변환**를 **count_if**를 **remove_if**, 하는 의도 분명 때문에 손으로 작성 한 루프 보다 우수 하 고 있으며 쉽게 버그 없는 코드를 작성할 수 있도록 합니다. 또한 대부분의 c + + 표준 라이브러리 알고리즘 보다 효율적으로 만드는 구현 최적화가.  
  
 대신 다음과 같은 이전 c + +:  
  
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
 범위 기반 **에 대 한** 루프는 C + + 언어 기능, c + + 표준 라이브러리 알고리즘을 하지 않습니다. 하지만 루프에 대 한이 설명에서 언급할 가치가 있습니다. 범위 기반 **에 대 한** 루프의 확장은 합니다 **에 대 한** 키워드 및 값의 범위를 반복 하는 루프를 작성할 수 있는 편리 하 고 효율적인 방법을 제공 합니다. C + + 표준 라이브러리 컨테이너, 문자열 및 배열에 대 한 기본으로 제공 되는 범위 기반 **에 대 한** 루프입니다. 사용자 정의 형식에 대 한이 새로운 반복 구문의 사용 하려면 다음 지원을 추가 합니다.  
  
-   A **시작** 구조의 시작 부분에 반복기를 반환 하는 메서드 및 **끝** 구조의 끝에 반복기를 반환 하는 메서드입니다.  
  
-   이러한 메서드에 대 한 반복기에 대 한 지원: * * 연산자 * **연산자! =**, 및 **operator + +** (접두사 버전).  
  
 이러한 메서드는 멤버 또는 독립 실행형 함수 일 수 있습니다.  
  
## <a name="random-numbers"></a>임의의 숫자  
 더는 이전 CRT **rand ()** 함수에 많은 결함을 c + + 커뮤니티에서 다루어 논의해 왔습니다. 최신 c + +에서는 이러한 단점을 다룰 필요가-없으며 고유한 균일 하 게 분산된 된 난수 생성기를 — 에서처럼빠르고쉽게만드는도구c++표준라이브러리에서사용할수있으므로[ \<임의 >](../standard-library/random.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + +의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 언어 참조](../cpp/cpp-language-reference.md)   
 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)