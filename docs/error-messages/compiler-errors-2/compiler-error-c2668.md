---
title: "컴파일러 오류 C2668 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2668"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2668"
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 컴파일러 오류 C2668
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 오버로드된 함수에 대한 호출이 모호합니다.  
  
 지정한 오버로드된 함수 호출을 해결하지 못했습니다.  하나 이상의 실제 매개 변수를 명시적으로 캐스팅해야 할 수도 있습니다.  
  
 템플릿 사용을 통해 이 오류가 발생할 수도 있습니다.  동일 클래스에서 정규 멤버 함수와 템플릿 기반 멤버 함수가 동일한 시그니처를 가지는 경우 템플릿 기반 함수가 먼저 와야 합니다.  이는 Visual C\+\+의 현재 구현에 대한 제한 사항입니다.  
  
 함수 템플릿의 부분 순서 지정에 대한 자세한 내용은 기술 자료 문서 Q240869를 참조하십시오.  
  
 `ISupportErrorInfo`를 지원하는 COM 개체를 포함하는 ATL 프로젝트를 빌드하는 경우에는 기술 자료 문서 Q243298을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C2668 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2668.cpp  
struct A {};  
struct B : A {};  
struct X {};  
struct D : B, X {};  
  
void func( X, X ){}  
void func( A, B ){}  
D d;  
int main() {  
   func( d, d );   // C2668 D has an A, B, and X   
   func( (X)d, (X)d );   // OK, uses func( X, X )  
}  
```  
  
## 예제  
 다음과 같이 [using 선언](../../cpp/using-declaration.md)을 사용하여 이 오류를 해결할 수도 있습니다.  
  
```  
// C2668b.cpp  
// compile with: /EHsc /c  
// C2668 expected  
#include <iostream>  
class TypeA {  
public:  
   TypeA(int value) {}  
};  
  
class TypeB {  
   TypeB(int intValue);  
   TypeB(double dbValue);  
};  
  
class TestCase {  
public:  
   void AssertEqual(long expected, long actual, std::string  
                    conditionExpression = "");  
};  
  
class AppTestCase : public TestCase {  
public:  
   // Uncomment the following line to resolve.  
   // using TestCase::AssertEqual;  
   void AssertEqual(const TypeA expected, const TypeA actual,  
                    std::string conditionExpression = "");  
   void AssertEqual(const TypeB expected, const TypeB actual,  
                    std::string conditionExpression = "");  
};  
  
class MyTestCase : public AppTestCase {  
   void TestSomething() {  
      int actual = 0;  
      AssertEqual(0, actual, "Value");  
   }  
};  
```  
  
## 예제  
 Visual Studio .NET 2003에서는 컴파일러 규칙에 따라 이제 상수 0의 캐스팅에 대한 변환에 모호성이 있기 때문에 이 오류가 발생할 수도 있습니다.  
  
 상수 0을 사용한 캐스팅에 대한 변환의 경우 int를 long과 void\* 모두로 변환해야 하기 때문에 모호성이 발생합니다.  이 오류를 해결하려면 사용할 함수 매개 변수의 정확한 형식으로 0을 캐스팅하여 변환이 일어날 필요가 없게 만드십시오. 이렇게 하면 Visual Studio .NET 2003과 Visual Studio .NET 버전의 Visual C\+\+ 모두에서 올바른 코드가 됩니다.  
  
```  
// C2668c.cpp  
#include "stdio.h"  
void f(long) {  
   printf_s("in f(long)\n");  
}  
void f(void*) {  
   printf_s("in f(void*)\n");  
}  
int main() {  
   f((int)0);   // C2668  
  
   // OK  
   f((long)0);  
   f((void*)0);  
}  
```  
  
## 예제  
 이제 CRT가 모든 산술 함수에 float 및 double 형식을 사용하기 때문에 이 오류가 발생할 수도 있습니다.  
  
```  
// C2668d.cpp  
#include <math.h>  
int main() {  
   int i = 0;  
   float f;  
   f = cos(i);   // C2668  
   f = cos((float)i);   // OK  
}  
```  
  
## 예제  
 CRT의 math.h에서 pow\(int, int\)를 제거한 경우에 이 오류가 발생할 수 있습니다.  
  
```  
// C2668e.cpp  
#include <math.h>  
int main() {  
   pow(9,9);   // C2668  
   pow((double)9,9);   // OK  
}  
```