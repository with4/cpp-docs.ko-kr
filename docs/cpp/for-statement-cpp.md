---
title: "for 문 (C++) | Microsoft Docs"
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
helpviewer_keywords: 
  - "for 키워드[C++]"
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# for 문 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

조건이 false가 될 때까지 문을 반복적으로 실행합니다.  범위 기반 문장에 대한 자세한 내용은 [범위 기반 for 문\(C\+\+\)](../cpp/range-based-for-statement-cpp.md)를 참조하십시오.  
  
## 구문  
  
```  
for ( init-expression ; cond-expression ; loop-expression )   
    statement;  
```  
  
## 설명  
 `for` 문을 사용하여 지정된 횟수만큼 실행해야 하는 루프를 생성합니다.  
  
 `for` 문은 다음 표와 같이 세 가지 선택적 부분으로 구성됩니다.  
  
### 루프 요소에 대해  
  
|구문 이름|실행 시기|설명|  
|-----------|-----------|--------|  
|`init-expression`|**for** 문의 다른 요소 앞에서는 `init-expression`이 한 번만 실행됩니다.  그런 다음 `cond-expression`으로 제어가 전달됩니다.|루프 인덱스를 초기화하는 데 자주 사용됩니다.  식 또는 선언을 포함할 수 있습니다.|  
|`cond-expression`|첫 번째 반복을 포함한 `statement`의 각 반복을 실행하기 전에  `statement`는 `cond-expression`이 true\(0이 아님\)로 평가될 때만 실행됩니다.|정수 형식으로 명확한 변환을 하는 정수 형식 또는 클래스 형식으로 평가되는 식입니다.  일반적으로 루프 종료 기준을 테스트하는 데 사용됩니다.|  
|`loop-expression`|`statement`의 각 반복 끝에서  `loop-expression`이 실행된 후, `cond-expression`이 평가됩니다.|일반적으로 루프 인덱스 증가에 사용됩니다.|  
  
 다음 예제에서는 `for` 문을 사용하는 여러 가지 방법을 보여 줍니다.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main() {  
    // The counter variable can be declared in the init-expression.  
    for (int i = 0; i < 2; i++ ){   
       cout << i;  
    }  
    // Output: 01  
    // The counter variable can be declared outside the for loop.  
    int i;  
    for (i = 0; i < 2; i++){  
        cout << i;  
    }  
    // Output: 01  
    // These for loops are the equivalent of a while loop.  
    i = 0;  
    while (i < 2){  
        cout << i++;  
    }  
}  
    // Output: 012  
```  
  
 `init-expression` 및 `loop-expression`은 쉼표로 구분된 여러 개의 문을 포함할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main(){  
    int i, j;  
    for ( i = 5, j = 10 ; i + j < 20; i++, j++ ) {  
        cout << "i + j = " << (i + j) << '\n';  
    }  
}  
    // Output:  
    i + j = 15  
    i + j = 17  
    i + j = 19  
```  
  
 `loop-expression`은 증가 또는 감소하거나 다른 방식으로 수정될 수 있습니다.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main(){  
for (int i = 10; i > 0; i--) {  
        cout << i << ' ';  
    }  
    // Output: 10 9 8 7 6 5 4 3 2 1  
    for (int i = 10; i < 20; i = i+2) {  
        cout << i << ' ';  
    }  
    // Output: 10 12 14 16 18  
```  
  
 `for` 루프는 `statement` 내의 [브레이크](../cpp/break-statement-cpp.md), [반환](../cpp/return-statement-cpp.md) 또는 [goto](../cpp/goto-statement-cpp.md)\(**for** 루프 외부에 있는 레이블 문\)가 실행될 때 종료합니다.  `for` 루프의 [continue](../cpp/continue-statement-cpp.md) 문은 현재 반복만 종료합니다.  
  
 `cond-expression`이 생략된 경우 true 및 **for** 루프가 `statement` 내의 `break`, `return` 또는 `goto` 없이는 종료되지 않는 것으로 간주됩니다.  
  
 `for` 문의 세 필드는 일반적으로 초기화, 종료 테스트, 증가에 사용되지만 이러한 용도에 제한된 것은 아닙니다.  예를 들어, 다음 코드는 0부터 4까지의 숫자를 인쇄합니다.  이 경우 `statement`은 null 문입니다.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    int i;  
    for( i = 0; i < 5; cout << i << '\n', i++){  
        ;  
    }  
}  
```  
  
## 루프와 C\+\+ 표준에 대해  
 C\+\+ 표준에 따르면 `for` 루프에서 선언된 변수는 `for` 루프가 종료된 후 범위를 벗어납니다.  예를 들면 다음과 같습니다.  
  
```cpp  
for (int i = 0 ; i < 5 ; i++) {  
   // do something  
}  
// i is now out of scope under /Za or /Zc:forScope  
```  
  
 기본적으로 [\/Ze](../build/reference/za-ze-disable-language-extensions.md)에서 `for` 루프에서 선언된 변수는 `for` 루프의 바깥쪽 범위가 종료될 때까지 범위에 남아 있습니다.  
  
 [\/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)에서는 \/Za를 지정하지 않아도 루프에 대해 선언된 표준 변수 동작을 사용할 수 있습니다.  
  
 `for` 루프의 범위 차이를 사용하여 \/Ze에서 다음과 같이 변수를 다시 선언하는 것도 가능합니다.  
  
```cpp  
// for_statement5.cpp  
int main(){  
   int i = 0;   // hidden by var with same name declared in for loop  
   for ( int i = 0 ; i < 3; i++ ) {}  
  
   for ( int i = 0 ; i < 3; i++ ) {}  
}  
```  
  
 이것은 `for` 루프에서 선언된 변수의 표준 동작을 더 가깝게 모방합니다. 이 동작은 `for` 루프에서 필요한 변수가 루프가 모두 수행되면 범위를 벗어나야 합니다.  변수가 `for` 루프에서 선언되는 경우 컴파일러는 같은 이름인 지역 변수가 있다고 하더라도 내부적으로 `for` 루프의 안에 있는 바깥쪽 범위에서 내부적으로 승격합니다.  
  
## 참고 항목  
 [반복 문](../cpp/iteration-statements-cpp.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [while 문 \(C\+\+\)](../cpp/while-statement-cpp.md)   
 [do\-while 문\(C\+\+\)](../cpp/do-while-statement-cpp.md)   
 [범위 기반 for 문\(C\+\+\)](../cpp/range-based-for-statement-cpp.md)