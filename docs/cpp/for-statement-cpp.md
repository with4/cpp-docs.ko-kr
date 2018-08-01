---
title: for 문 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: feb14056e3054cdf0e802b16ce9ff20f67da43fe
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401576"
---
# <a name="for-statement-c"></a>for 문 (C++)
조건이 false가 될 때까지 문을 반복적으로 실행합니다. 에 범위 기반의 for 문에 대 한 내용은 참조 하세요 [범위에 대 한 문 (c + +)를 기준으로](../cpp/range-based-for-statement-cpp.md)입니다.  
  
## <a name="syntax"></a>구문  
  
```  
for ( init-expression ; cond-expression ; loop-expression )   
    statement;  
```  
  
## <a name="remarks"></a>설명  
 사용 된 **에 대 한** 문이 지정한 횟수 만큼 실행 해야 하는 루프를 생성 합니다.  
  
 합니다 **에 대 한** 다음 표에 나와 있는 것 처럼 문은 세 가지 선택적 부분으로 구성 됩니다.  
  
### <a name="for-loop-elements"></a>루프 요소에 대해  
  
|구문 이름|실행 시기|설명|  
|-----------------|-------------------|-----------------|  
|`init-expression`|다른 요소 앞의 **에 대 한** 문을 `init-expression` 한 번만 실행 됩니다. 그런 다음 `cond-expression`으로 제어가 전달됩니다.|루프 인덱스를 초기화하는 데 자주 사용됩니다. 식 또는 선언을 포함할 수 있습니다.|  
|`cond-expression`|첫 번째 반복을 포함한 `statement`의 각 반복을 실행하기 전에 `statement`는 `cond-expression`이 true(0이 아님)로 평가될 때만 실행됩니다.|정수 형식으로 명확한 변환을 하는 정수 형식 또는 클래스 형식으로 평가되는 식입니다. 일반적으로 루프 종료 기준을 테스트하는 데 사용됩니다.|  
|`loop-expression`|`statement`의 각 반복 끝에서 `loop-expression`이 실행된 후, `cond-expression`이 평가됩니다.|일반적으로 루프 인덱스 증가에 사용됩니다.|  
  
 다음 예제에서는 사용 하는 다양 한 방법 표시 합니다 **에 대 한** 문입니다.  
  
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
  
 `init-expression` 및 `loop-expression`은 쉼표로 구분된 여러 개의 문을 포함할 수 있습니다. 예를 들어:  
  
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
  
 **에 대 한** 루프를 종료 하는 경우를 [중단](../cpp/break-statement-cpp.md)를 [반환](../cpp/return-statement-cpp.md), 또는 [goto](../cpp/goto-statement-cpp.md) (외부에 있는 레이블 문으로 **에대한**루프) 내에서 `statement` 실행 됩니다. A [계속](../cpp/continue-statement-cpp.md) 문에서 **에 대 한** 루프 현재 반복만 종료 합니다.  
  
 하는 경우 `cond-expression` 는 생략 하면는 것이 true 및 **에 대 한** 없이 루프는 종료 되지 않는 **중단**를 **반환**, 또는 **goto** 내 `statement`합니다.  
  
 하지만의 세 필드를 **에 대 한** 문에 초기화, 종료 테스트, 일반적으로 사용 되며 들어오더라도 없는 이러한 용도에 제한 합니다. 예를 들어, 다음 코드는 0부터 4까지의 숫자를 인쇄합니다. 이 경우 `statement`은 null 문입니다.  
  
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
  
## <a name="for-loops-and-the-c-standard"></a>루프와 C++ 표준에 대해  
 c + + 표준에 따르면에서 선언 된 변수를 **에 대 한** 루프 후 범위 벗어납니다 합니다 **에 대 한** 루프가 종료 합니다. 예를 들어:  
  
```cpp  
for (int i = 0 ; i < 5 ; i++) {  
   // do something  
}  
// i is now out of scope under /Za or /Zc:forScope  
```  
  
 기본적으로 아래 [/Ze](../build/reference/za-ze-disable-language-extensions.md)에서 선언 된 변수를 **에 대 한** 루프까지 범위 내에 남아 합니다 **에 대 한** 루프의 바깥쪽 범위가 종료 합니다.  
  
 [/Zc: forscope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 지정 하지 않고도 for 루프에서 선언 된 변수의 표준 동작을 활성화 `/Za`합니다.  
  
 것도 가능의 범위 차이 사용 하는 **에 대 한** 루프에서 변수를 다시 선언 `/Ze` 다음과 같습니다.  
  
```cpp  
// for_statement5.cpp  
int main(){  
   int i = 0;   // hidden by var with same name declared in for loop  
   for ( int i = 0 ; i < 3; i++ ) {}  
  
   for ( int i = 0 ; i < 3; i++ ) {}  
}  
```  
  
 에 선언 된 변수의 표준 동작을 더 가깝게 모방이 **에 대 한** 루프에서 선언 된 변수를 필요로 하는 **에 대 한** 루프가 완료 되 면 범위를 벗어나는 루프입니다. 변수가 선언 된 경우는 **에 대 한** 루프 컴파일러 내부적으로 승격에서 지역 변수를 **에 대 한** 루프의 안에 있는 바깥쪽 범위 변수가 이미 같은 이름의 지역 변수인 경우에 합니다.  
  
## <a name="see-also"></a>참고자료  
 [반복 문](../cpp/iteration-statements-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)   
 [while 문(C++)](../cpp/while-statement-cpp.md)   
 [do-while 문(C++)](../cpp/do-while-statement-cpp.md)   
 [범위 기반 for 문(C++)](../cpp/range-based-for-statement-cpp.md)