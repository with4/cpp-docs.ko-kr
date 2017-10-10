---
title: "컴파일러 오류 C2059 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2059
dev_langs:
- C++
helpviewer_keywords:
- C2059
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: dbf80ab803eaaacc29ac82657af130194417f1c7
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2059"></a>컴파일러 오류 C2059
구문 오류: 'token'  
  
 토큰 구문 오류가 발생 했습니다.  
  
 다음 예제에서는 선언 하는 줄에 대 한 오류 메시지를 생성 `j`합니다.  
  
```  
// C2059e.cpp  
// compile with: /c  
// C2143 expected  
// Error caused by the incorrect use of '*'.  
   int j*; // C2059   
```  
  
 오류의 원인을 확인 하려면 오류 메시지에 나열 된 줄 뿐만 아니라 위에 있는 줄을 검사 합니다. 해당 줄을 검사 문제에 대해 아무런 단서를, 오류 메시지에 나열 된 선과 상위 아마도 여러 줄 주석 보십시오.  
  
 오류 메시지는 바로 뒤에 기호에 대해 발생 하는 경우는 `typedef` 변수, 변수 소스 코드에 정의 되어 있는지 확인 합니다.  
  
 C2059 오류가 발생할 수 있으므로, nothing으로 계산 되는 기호 때 **/D** `symbol`  **=**  컴파일하는 데 사용 됩니다.  
  
```  
// C2059a.cpp  
// compile with: /DTEST=  
#include <stdio.h>  
  
int main() {  
   #ifdef TEST  
      printf_s("\nTEST defined %d", TEST);   // C2059  
   #else  
      printf_s("\nTEST not defined");  
   #endif  
}  
```  
  
 C2059 발생할 수 있는 경우 구조를 함수에 대 한 기본 인수에 지정 하는 응용 프로그램을 컴파일하는 경우에 합니다. 인수에 대 한 기본값 식 이어야 합니다. 이니셜라이저 목록-구조를 초기화 하는 데 사용 하는 예를 들어 하나-식이 아닙니다.  이 문제를 해결 하려면 필요한 초기화를 수행 하는 생성자를 정의 합니다.  
  
 다음 예제에서는 C2059 오류가 생성 됩니다.  
  
```  
// C2059b.cpp  
// compile with: /c  
struct ag_type {  
   int a;  
   float b;  
   // Uncomment the following line to resolve.  
   // ag_type(int aa, float bb) : a(aa), b(bb) {}   
};  
  
void func(ag_type arg = {5, 7.0});   // C2059  
void func(ag_type arg = ag_type(5, 7.0));   // OK  
```  
  
 멤버 템플릿 클래스나 클래스 밖의 함수를 정의 하는 경우에 C2059을 얻을 수 있습니다. 자세한 내용은 참조 [기술 자료 문서 241949](http://support.microsoft.com/kb/241949)합니다.  
  
 잘못 된 형식의 캐스트에 대 한 C2059 발생할 수 있습니다.  
  
 다음 샘플에서는 C2059 오류가 생성 됩니다.  
  
```  
// C2059c.cpp  
// compile with: /clr  
using namespace System;  
ref class From {};  
ref class To : public From {};  
  
int main() {  
   From^ refbase = gcnew To();  
   To^ refTo = safe_cast<To^>(From^);   // C2059  
   To^ refTo2 = safe_cast<To^>(refbase);   // OK  
}  
```  
  
 C2059는 마침표가 포함 된 네임 스페이스 이름을 만들기 위해 사용 하려는 경우에 발생할 수 있습니다.  
  
 다음 샘플에서는 C2059 오류가 생성 됩니다.  
  
```  
// C2059d.cpp  
// compile with: /c  
namespace A.B {}   // C2059  
  
// OK  
namespace A  {  
   namespace B {}  
}  
```  
  
 이름을 정규화 할 수 있는 연산자 C2059 발생할 수 있습니다 (`::`, `->`, 및 `.`) 키워드 뒤에 야 `template`이 예제에 나온 것 처럼:  
  
```cpp  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    typedef typename AY::Rebind<X>::Other AX; // error C2059  
};  
  
```  
  
 기본적으로 C++는 `AY::Rebind`이 템플릿이 아니라고 가정하기 때문에 다음 `<`는 보다 작음 기호로 해석됩니다.  꺾쇠 괄호로 올바르게 구문 분석될 수 있도록 `Rebind`이 템플릿임을 컴파일러에 명시적으로 알려야 합니다. 이 오류를 해결하려면 다음과 같이 종속 형식의 이름에서 `template` 키워드를 사용합니다.  
  
```cpp  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    typedef typename AY::template Rebind<X>::Other AX; // correct  
};  
  
```
