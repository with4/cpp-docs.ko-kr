---
title: "컴파일러 오류 C2065 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2065
dev_langs:
- C++
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 5a3a0d4389a958f421f23a4dc96a395eaf3e22ab
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-error-c2065"></a>컴파일러 오류 C2065
'identifier' : 선언되지 않은 식별자입니다.  
  
컴파일러는 식별자에 대 한 선언을 찾을 수 없습니다. 식별자가 변수를 사용 하려면 먼저 변수의 형식을 선언에 지정 해야 합니다. 식별자가 함수 이름, 함수를 사용 하려면 먼저이 함수를 사용 하는 매개 변수 선언에 지정 되어야 합니다. 식별자가 사용자 정의 형식에 대 한 태그 예를 들어 한 `class` 또는 `struct`, 태그의 형식을 사용 하려면 먼저 선언 해야 합니다. 식별자가 형식 별칭을 사용 하 여 형식을 선언 해야는 `using` 선언 또는 `typedef` 형식을 사용할 수 있습니다.  
  
이 오류에 대 한 다양 한 원인 있습니다. 다음은 몇 가지 가장 일반적인 문제입니다.
  
## <a name="example-misspelled-identifier"></a>예: 철자가 잘못 된 식별자  
  
이 오류는 흔히 식별자 이름의 철자가, 또는 식별자 잘못 된 사용 대문자 및 소문자 때 발생 합니다. 선언에서 이름에 사용 하는 이름이 일치 해야 합니다.  
  
```cpp  
// C2065_spell.cpp  
// compile with: cl /EHsc C2065_spell.cpp 
#include <iostream> 
using namespace std; 
int main() { 
    int someIdentifier = 42; 
    cout << "Some Identifier: " << SomeIdentifier << endl;   
    // C2065: 'SomeIdentifier': undeclared identifier 
    // To fix, correct the spelling:  
    // cout << "Some Identifier: " << someIdentifier << endl;   
}  
```
  
## <a name="example-missing-header-file"></a>예: 헤더 파일이 없습니다.  
  
식별자를 선언 하는 헤더 파일을 포함 되지 않습니다. 식별자에 대 한 선언이 포함 된 파일이 사용 하는 모든 소스 파일에 포함 되어 있는지 확인 합니다.  
  
```cpp  
// C2065_header.cpp  
// compile with: cl /EHsc C2065_spell.cpp 

//#include <stdio.h> 
int main() { 
    fpos_t file_position = 42; // C2065: 'fpos_t': undeclared identifier 
    // To fix, uncomment the #include <stdio.h> line
    // to include the header where fpos_t is defined  
} 
```  
  
정의 하는 경우 Windows 데스크톱 응용 프로그램 소스 파일에서이 오류가 표시 될 수 있습니다 `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN`, 또는 `WIN32_EXTRA_LEAN`합니다. 이러한 전처리기 매크로 windows.h 및 afxv에서 일부 헤더 파일을 제외\_w32.h 속도를 컴파일합니다. Windows.h 및 afxv_w32.h에 대 한 최신 설명 제외 되는를 찾습니다.  
  
## <a name="eample-missing-closing-quote"></a>Eample: 닫는 따옴표가 없습니다.  
  
이 오류는 문자열 상수 뒤 닫는 따옴표가 누락 된 경우에 발생할 수 있습니다. 이것이 쉽게 컴파일러 혼동을 줄 수입니다. 
  
```cpp  
// C2065_quote.cpp  
// compile with: cl /EHsc C2065_quote.cpp 
#include <iostream>  

int main() { 
    // Fix this issue by adding the closing quote to "Aaaa"
    char * first = "Aaaa, * last = "Zeee"; 
    std::cout << "Name: " << first 
        << " " << last << std::endl; // C2065: 'last': undeclared identifier 
} 
```  
  
## <a name="example-use-iterator-outside-for-loop-scope"></a>예: for 루프 범위 외부의 반복기를 사용 합니다.  
  
반복기 변수를 선언 하는 경우이 오류가 발생할 수 있습니다는 `for` 루프 및 다음의 범위를 벗어나는 반복기 변수를 사용 하려고는 `for` 루프입니다. 사용 하면 컴파일러는 [/zc: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 기본적으로 컴파일러 옵션입니다. 참조 [디버그 반복기 지원](../../standard-library/debug-iterator-support.md) 자세한 정보에 대 한 합니다.  
  
```cpp  
// C2065_iter.cpp  
// compile with: cl /EHsc C2065_iter.cpp 
#include <iostream> 
#include <string> 

int main() {
    // char last = '!'; 
    std::string letters{ "ABCDEFGHIJKLMNOPQRSTUVWXYZ" }; 
    for (const char& c : letters) {
        if ('Q' == c) {
            std::cout << "Found Q!" << std::endl;
        }
        // last = c;
    }
    std::cout << "Last letter was " << c << std::endl; // C2065
    // Fix by using a variable declared in an outer scope.
    // Uncomment the lines that declare and use 'last' for an example.
    // std::cout << "Last letter was " << last << std::endl; // C2065
} 
```  
  
## <a name="example-preprocessor-removed-declaration"></a>예: 전처리기 제거 선언  
  
이 오류는 현재 구성에 대 한 컴파일되지 않은 조건부로 컴파일된 코드에 된 변수 또는 함수를 참조 하는 경우에 발생할 수 있습니다. 빌드 환경에서 현재 지원 되지 않는 헤더 파일에는 함수를 호출 하는 경우 발생할 수도 있습니다. 특정 변수 또는 함수 인만 사용할 수 있는 특정 전처리기 매크로 정의 된 경우 동일한 전처리기 매크로 정의 된 경우에 이러한 함수를 호출 하는 코드를 컴파일할 수 있는지 확인 합니다. 이 문제는 필요한 전처리기 매크로 현재 빌드 구성에 대해 정의 되어 있지 않은 경우 함수에 대 한 선언을 회색 하기 때문에를 쉽게 IDE에 파악할 수 있습니다.  
  
이것이 디버그를 작성 하지만 소매 하지 하는 경우에 작동 하는 코드의 예:  
  
```cpp  
// C2065_defined.cpp
// Compile with: cl /EHsc /W4 /MT C2065_defined.cpp
#include <iostream>
#include <crtdbg.h>
#ifdef _DEBUG
    _CrtMemState oldstate;
#endif
int main() {
    _CrtMemDumpStatistics(&oldstate); 
    std::cout << "Total count " << oldstate.lTotalCount; // C2065
    // Fix by guarding references the same way as the declaration:
    // #ifdef _DEBUG
    //    std::cout << "Total count " << oldstate.lTotalCount;
    // #endif
}
```
  
## <a name="example-use-an-unscoped-identifier"></a>예: 범위가 지정 되지 않은 식별자를 사용 합니다.  
  
식별자를 제대로 범위로 지정 되지 않은 경우이 오류가 발생할 수 있습니다. 예를 들어 c + + 표준 라이브러리 함수 및 연산자 정규화 되지 않은 네임 스페이스로 시기나 하지 놓은 `std` 네임 스페이스를 사용 하 여 현재 범위에는 `using` 지시문, 컴파일러 찾을 수 없습니다 해당 합니다. 이 문제를 해결 하려면 완전히 식별자 이름을 한정 하거나 포함 된 네임 스페이스를 지정 된 `using` 지시문입니다.  
  
이 예제는 있기 때문에 컴파일하지 실패 `cout` 및 `endl` 에 정의 된는 `std` 네임 스페이스:  
  
```cpp  
// C2065_scope.cpp  
// compile with: cl /EHsc C2065_scope.cpp 
// using namespace std;   // Uncomment this line to fix  
#include <iostream>  
int main() {  
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier 
                               // C2065 'endl': undeclared identifier
    // Or try the following line instead  
    std::cout << "Hello" << std::endl;  
}
```  
  
내에 선언 된 식별자 `class`, `struct`, 또는 `enum class` 형식, 바깥쪽 범위의 이름으로도 정규화 해야 합니다.
  
## <a name="example-ccli-type-deduction-failure"></a>예: C + + /cli CLI 형식 추론이 실패  
  
사용 된 매개 변수에서 원하는 형식 인수를 추론할 수 없는 경우 일반 함수를 호출할 때이 오류가 발생할 수 있습니다. 자세한 내용은 참조 [제네릭 함수 (C + + /cli CLI)](../../windows/generic-functions-cpp-cli.md)합니다.  
  
```cpp  
// C2065_b.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
int main() {  
   // global generic function call  
   G<T>(10);   // C2065  
   G<int>(10);   // OK - fix with a specific type argument  
}  
```  
  
## <a name="example-ccli-attribute-parameters"></a>예: C + + /cli CLI 특성 매개 변수  
  
이 오류는 Visual C++ 2005에 대해 수행한 컴파일러 규칙 작업의 결과로 생성될 수도 있습니다. 매개 변수에 Visual C++ 특성이 있는지 확인합니다.  
  
```cpp  
// C2065_attributes.cpp  
// compile with: cl /c /clr C2065_attributes.cpp  
[module(DLL, name=MyLibrary)];   // C2065  
// try the following line instead  
// [module(dll, name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```  

