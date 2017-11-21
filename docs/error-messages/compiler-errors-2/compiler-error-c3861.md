---
title: "컴파일러 오류 C3861 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3861
dev_langs: C++
helpviewer_keywords: C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d515c112c94024f123ee712b674b668b0c62287d
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="compiler-error-c3861"></a>컴파일러 오류 C3861

> '*식별자*': 식별자를 찾을 수 없습니다  
  
컴파일러가 인수 종속 조회를 사용하는 경우에도 식별자에 대한 참조를 확인할 수 없습니다.  
  
이 오류를 해결 하려면 사용을 비교 *식별자* 대/소문자 및 철자 식별자 선언에 있습니다. 확인 [범위 확인 연산자](../../cpp/scope-resolution-operator.md) 및 네임 스페이스 [지시문을 사용 하 여](../../cpp/namespaces-cpp.md#using_directives) 이 올바르게 사용 합니다. 식별자가 헤더 파일에 선언 된 경우 식별자가 참조 하기 전에 헤더 포함 되어 있는지 확인 합니다. 식별자 외부에서 표시 하려는 경우이 사용 하는 모든 소스 파일에 선언 되어 있는지 확인 합니다. 식별자 선언 또는 정의에서 제외 되지 않은 확인 [조건부 컴파일 지시문](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)합니다. 

Visual Studio 2015에서 C 런타임 라이브러리에서 사용 되지 않는 함수를 제거 하려면 변경 내용을 C3861 발생할 수 있습니다. 이 오류를 해결 하려면 이러한 함수에 대 한 참조를 제거 하거나 있는 경우 해당 안전한 대안으로 바꾸세요. 자세한 내용은 참조 [사용 되지 않는 함수가](../../c-runtime-library/obsolete-functions.md)합니다.  

이전 버전의 컴파일러에서 오류 C3861 나타나면 프로젝트 마이그레이션 후에 지원 되는 Windows 버전에 관련 된 문제를 할 수 있습니다. Visual C++에서는 더 이상 Windows 95, Windows 98, Windows ME, Windows NT 또는 Windows 2000을 대상으로 지정할 수 없습니다. WINVER 또는 _WIN32_WINNT 매크로가 이러한 Windows 버전 중 하나에 할당 된 경우에 매크로 수정 해야 합니다. 자세한 내용은 참조 [수정 WINVER 및 _WIN32_WINNT](../../porting/modifying-winver-and-win32-winnt.md)합니다.
  
## <a name="example"></a>예제  

다음 샘플에서는 식별자가 정의 되지 않았으므로 C3861 오류가 발생 합니다.  
  
```cpp  
// C3861.cpp  
void f2(){}  
int main() {  
   f();    // C3861  
   f2();   // OK  
}  
```  
  
## <a name="example"></a>예제  

다음 샘플을 사용 하는 다른 소스 파일에서 선언 되지 않은 식별자는 해당 정의의 파일 범위에서 볼 수만 이므로 C3861를 생성 합니다.  
  
```cpp  
// C3861_a1.cpp
// Compile with: cl /EHsc /W4 C3861_a1.cpp C3861_a2.cpp  
#include <iostream>
// Uncomment the following line to fix:
// int f();  // declaration makes external function visible
int main() {  
   std::cout << f() << std::endl;    // C3861
}  
```  
  
```cpp  
// C3861_a2.cpp  
int f() {  // declared and defined here
   return 42;  
}
```  
  
## <a name="example"></a>예제  

C + + 표준 라이브러리의 예외 클래스에 필요한는 `std` 네임 스페이스입니다.  
  
```cpp  
// C3861_b.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   try {  
      throw exception("Exception");   // C3861  
      // try the following line instead  
      // throw std::exception("Exception");  
   }  
   catch (...) {  
      std::cout << "caught an exception" << std::endl;  
   }  
}  
```  
## <a name="example"></a>예제  

CRT 라이브러리에서 사용 되지 않는 함수가 제거 되었습니다.  
  
```cpp  
// C3861_c.cpp  
#include <stdio.h>  
int main() {  
   char line[21]; // room for 20 chars + '\0'  
   gets( line );  // C3861  
   // Use gets_s instead.  
   printf( "The line entered was: %s\n", line );  
}  
```
다음 샘플에서는 컴파일러가 FriendFunc에 대 한 인수 종속 조회를 사용할 수 없으므로 C3767를 생성 합니다.  
  
```  
namespace N {  
   class C {  
      friend void FriendFunc() {}  
      friend void AnotherFriendFunc(C* c) {}  
   };  
}  
  
int main() {  
   using namespace N;  
   FriendFunc();   // C3861 error  
   C* pC = new C();  
   AnotherFriendFunc(pC);   // found via argument-dependent lookup  
}  
```  
  
이 오류를 해결 하려면 클래스 범위에서 friend를 선언 하 고 네임 스페이스 범위에서 정의:  
  

MyClass {클래스  
   int m_private;  
   friend void 되;  
};  
  
void 되 {  
   MyClass s입니다.  
   s.m_private = 0;  
}  
  
int main () {  
   되;  
}  