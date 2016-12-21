---
title: "범위 기반 for 문(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 5750ba1d-ba48-4236-a923-e32de8345c2d
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 범위 기반 for 문(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`statement` 반복적 및 순차적으로 `expression` 에서 각 요소를 실행합니다.  
  
## 구문  
  
```  
  
      for ( for-range-declaration : expression )  
   statement   
```  
  
## 설명  
 범위 기반이며 "범위"를 통해 실행 해야 하는 구조체 루프에 대한 `for` 문, 반복할 수 있는 어떤 것으로 정의 통해 실행 해야 하는 루프를 생성 하는 문\-예를 들어, `std::vector`, 또는 해당 범위에서 정의 된 STL 시퀀스 `begin()` 및 `end()`.  `for-range-declaration` 부분에서 정의된 이름은 `for` 문에서 지역적이고 `expression` 또는 `statement`에서 재정의될 수 없습니다.  [자동](../cpp/auto-cpp.md) 키워드가 `for-range-declaration` 문의 부분에 선호되는 것에 주목하십시오.  
  
 이 코드 영역된 `for` 배열과 벡터를 반복 하는 루프를 어떻게 사용하는지 보여줍니다:  
  
```cpp  
  
// range-based-for.cpp  
// compile by using: cl /EHsc /nologo /W4  
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main()   
{  
    // Basic 10-element integer array.  
    int x[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };  
  
    // Range-based for loop to iterate through the array.  
    for( int y : x ) { // Access by value using a copy declared as a specific type.   
                       // Not preferred.  
        cout << y << " ";  
    }  
    cout << endl;  
  
    // The auto keyword causes type inference to be used. Preferred.  
  
    for( auto y : x ) { // Copy of 'x', almost always undesirable  
        cout << y << " ";  
    }  
    cout << endl;  
  
    for( auto &y : x ) { // Type inference by reference.  
        // Observes and/or modifies in-place. Preferred when modify is needed.  
        cout << y << " ";  
    }  
    cout << endl;  
  
    for( const auto &y : x ) { // Type inference by reference.  
        // Observes in-place. Preferred when no modify is needed.  
        cout << y << " ";  
    }  
    cout << endl;  
    cout << "end of integer array test" << endl;  
    cout << endl;  
  
    // Create a vector object that contains 10 elements.  
    vector<double> v;  
    for (int i = 0; i < 10; ++i) {  
        v.push_back(i + 0.14159);  
    }  
  
    // Range-based for loop to iterate through the vector, observing in-place.  
    for( const auto &j : v ) {  
        cout << j << " ";  
    }  
    cout << endl;  
    cout << "end of vector test" << endl;  
}  
  
```  
  
 출력은 다음과 같습니다.  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `end of integer array test`  
  
 `0.14159 1.14159 2.14159 3.14159 4.14159 5.14159 6.14159 7.14159 8.14159 9.14159`  
  
 `end of vector test`  
  
 범위 기반  `for`  루프가 이러한 `statement`에서 실행될 때: [브레이크](../cpp/break-statement-cpp.md), [반환](../cpp/return-statement-cpp.md), 또는  [goto](../cpp/goto-statement-cpp.md) 범위 기반 외부를 레이블 문으로 **에** 루프.  [계속](../cpp/continue-statement-cpp.md) 범위 기반에서 명세서 `for` 루프는 현재 반복에만 종료 합니다.  
  
 범위 기반 `for` 에 대한 이러한 사실을 명심하십시오:  
  
-   배열을 자동으로 인식 합니다.  
  
-   `.begin()` 및 `.end()` 을 가진 컨테이너를 인식하십시오.  
  
-   기타 항목을 위해 `begin()` 및 `end()` 인수 종속성 조회 사용하기.  
  
## 참고 항목  
 [auto](../cpp/auto-cpp.md)   
 [반복 문](../cpp/iteration-statements-cpp.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [while 문 \(C\+\+\)](../cpp/while-statement-cpp.md)   
 [do\-while 문\(C\+\+\)](../cpp/do-while-statement-cpp.md)   
 [for 문 \(C\+\+\)](../cpp/for-statement-cpp.md)