---
title: "컴파일러 오류 C2059 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2059"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2059"
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2059
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구문 오류 : 'token'  
  
 토큰으로 인해 구문 오류가 발생했습니다.  
  
 다음 예제에서는 `j`를 선언하는 줄에 대한 오류 메시지를 생성합니다.  
  
```  
// C2059e.cpp  
// compile with: /c  
// C2143 expected  
// Error caused by the incorrect use of '*'.  
   int j*; // C2059   
```  
  
 오류의 원인을 알아보려면 오류 메시지에 기록된 줄뿐 아니라 위에 있는 줄들도 검사하십시오.  해당 줄을 검사해도 문제에 대한 아무런 단서를 얻지 못하면 오류 메시지에 표시된 줄과 위에 있는 줄 중 예상되는 몇 줄을 주석 처리하십시오.  
  
 오류 메시지가 `typedef` 변수 바로 다음에 오는 기호에 대해 발생하는 경우에는 이 변수가 소스 코드 내에서 정의되었는지 확인합니다.  
  
 **\/D** `symbol` **\=**을 사용하여 컴파일할 때와 같이 기호가 어떤 값으로도 계산되지 않으면 C2059 오류가 발생할 수 있습니다.  
  
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
  
 함수의 기본 인수에 구조체를 지정하는 응용 프로그램을 컴파일할 때에도 C2059 오류가 발생할 수 있습니다.  인수의 기본값은 반드시 식이어야 합니다.  구조체를 초기화하는데 사용되는 예를 들어 이니셜라이저 목록은 식이 아닙니다.  이 문제를 해결하기 위해서는 생성자가 필수 초기화를 수행하도록 정의하십시오.  
  
 다음 예제는 C2059를 발생시킵니다.  
  
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
  
 클래스 외부에 멤버 템플릿 클래스나 함수를 정의할 경우에도 C2059 오류가 발생할 수 있습니다.  자세한 내용은 [기술 자료 문서 241949](http://support.microsoft.com/kb/241949) 를 참조하십시오.  
  
 C2059는 형식이 잘못된 캐스트에 대해 발생할 수 있습니다.  
  
 다음 샘플에서는 C2059 오류가 발생하는 경우를 보여 줍니다.  
  
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
  
 C2059는 마침표가 포함된 네임스페이스 이름을 만들려는 경우에도 발생할 수 있습니다.  
  
 다음 샘플에서는 C2059 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2059d.cpp  
// compile with: /c  
namespace A.B {}   // C2059  
  
// OK  
namespace A  {  
   namespace B {}  
}  
```  
  
 C2059 운영자 이름을 정규화 할 수 있는 경우에 발생할 수 있습니다 \(`::`,  `->` , 및  `.` \) 키워드 다음에 야  `template` , 같이 있습니다.  
  
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
  
 기본적으로 c \+ \+는 가정  `AY::Rebind`  이고. 따라서 다음  `<`  으로 해석\-보다 작습니다.  알려야 컴파일러는 명시적으로  `Rebind`  는 꺾쇠 괄호 올바르게 구문 분석할 수 있도록 서식 파일입니다.  이 오류를 해결 하려면 사용 하는  `template`  종속 형식 이름을 다음과 같이 키워드입니다.  
  
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