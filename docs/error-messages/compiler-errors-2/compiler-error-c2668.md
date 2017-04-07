---
title: "컴파일러 오류 c 2668 | Microsoft Docs"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2668
dev_langs:
- C++
helpviewer_keywords:
- C2668
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
caps.latest.revision: 13
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
translationtype: Machine Translation
ms.sourcegitcommit: b790beb88de009e1c7161f3c9af6b3e21c22fd8e
ms.openlocfilehash: 6bb1dc7c1dbf26a4ff8ec25a46fe7128e0fb6aa8
ms.lasthandoff: 03/29/2017

---
# <a name="compiler-error-c2668"></a>컴파일러 오류 c 2668
'function': 오버 로드 된 함수에 대 한 호출이 모호 합니다  
  
 지정 된 오버 로드 된 함수 호출을 확인할 수 없습니다. 실제 매개 변수 중 하나 이상을 명시적으로 캐스팅할 수도 있습니다.  
  
 또한 서식 파일 사용을 통해이 오류를 가져올 수 있습니다. 같은 클래스에는 일반 멤버 함수와 같은 서명 사용 하는 템플릿 멤버 함수는 것이 있다면, 템플릿 기반 하나 먼저와 야 합니다. Visual c + +의 현재 구현에서의 제한 사항입니다.  
  
 함수 템플릿의 부분 순서 지정에 자세한 내용은 기술 자료 문서 Q240869를 참조 합니다.  
  
 지 원하는 COM 개체를 포함 하는 ATL 프로젝트를 빌드하는 경우 `ISupportErrorInfo`, 기술 자료 문서 q 243298 참조 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 c 2668 오류가 생성 됩니다.  
  
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
  
## <a name="example"></a>예제  
 이 오류를 해결 하려면 또 다른 방법은 한 [선언을 사용 하 여](../../cpp/using-declaration.md):  
  
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
  
## <a name="example"></a>예제  
 이 오류는 Visual Studio.NET 2003에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 있습니다: 상수 0의 캐스트에 대 한 모호한 변환 합니다.  
  
 상수 0을 사용 하 여 캐스트에 대 한 변환 int long과 void *에 대 한 변환이 모두 필요 하므로 모호 합니다. 이 오류를 해결 하려면 0을 하 여 변환이 수행 (이 코드는 Visual c + +의 Visual Studio.NET 2003 및 Visual Studio.NET 버전에서 사용할 수 있습니다) 필요가에 사용 되는 함수 매개 변수의 정확한 형식으로 캐스팅 합니다.  
  
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
  
## <a name="example"></a>예제  
 Float 및 double 형식의 모든 수학 함수에 이제 CRT에 있기 때문에이 오류가 발생할 수 있습니다.  
  
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
  
## <a name="example"></a>예제  
 Pow (int, int) CRT의 math.h에서 제거 되었기 때문에이 오류가 발생할 수 있습니다.  
  
```  
// C2668e.cpp  
#include <math.h>  
int main() {  
   pow(9,9);   // C2668  
   pow((double)9,9);   // OK  
}  
```

## <a name="example"></a>예제  
이 코드는 Visual Studio 2015에서 성공 하지만 Visual Studio 2017과 C2668를 사용 하 여 나중에 실패 합니다. Visual Studio 2015에서 컴파일러는 일반 copy-initialization과 같은 방식으로 copy-list-initialization을 잘못 처리했고 오버로드 확인을 위해 생성자 변환만 고려했습니다. 

```
C++
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```
