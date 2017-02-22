---
title: "함수 인라이닝 문제 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Ob1 C++ 컴파일러 옵션"
  - "/Ob2 C++ 컴파일러 옵션"
  - "함수 인라이닝 문제"
  - "인라인 함수, 문제점"
  - "-Ob1 C++ 컴파일러 옵션"
  - "-Ob2 C++ 컴파일러 옵션"
ms.assetid: 65d59943-4b3c-4a43-aeb6-dccbf7686740
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 함수 인라이닝 문제
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

함수 인라이닝을 사용하는 경우에는 다음을 준수해야 합니다.  
  
-   인라인 함수를 포함된 헤더 파일에서 구현해야 합니다.  
  
-   헤더 파일에서 인라이닝을 ON으로 설정해야 합니다. 첫 번째 코드 파일:  
  
```  
// LNK2019_function_inline.cpp  
// compile with: /c   
// post-build command: lib LNK2019_function_inline.obj  
#include <stdio.h>  
struct _load_config_used {  
   void Test();  
   void Test2() { printf("in Test2\n"); }  
};  
  
void _load_config_used::Test() { printf("in Test\n"); }  
```  
  
 두 번째 코드 파일:  
  
```  
// LNK2019_function_inline_2.cpp  
// compile with: LNK2019_function_inline.lib  
struct _load_config_used {  
   void Test();  
   void Test2();  
};  
  
int main() {  
   _load_config_used x;  
   x.Test();  
   x.Test2();   // LNK2019  
}  
```  
  
 `#pragma inline_depth` 컴파일러 지시문을 사용하는 경우에는 2 이상의 값 집합을 사용해야 합니다.  0 값은 인라이닝을 해제시킵니다.  또한 **\/Ob1** 또는 **\/Ob2** 컴파일러 옵션을 사용해야 합니다.  
  
 서로 다른 모듈에서 인라인과 비인라인 컴파일 옵션을 혼합 사용하면 문제가 발생할 수도 있습니다.  함수 인라이닝이 설정\([\/Ob1](../../build/reference/ob-inline-function-expansion.md) 또는 [\/Ob2](../../build/reference/ob-inline-function-expansion.md)\)된 상태로 C\+\+ 라이브러리를 만들지만 함수를 설명하는 해당 헤더 파일에서 인라이닝의 설정을 해제할\(옵션 없음\) 경우 오류 LNK2001이 발생합니다.  함수는 헤더 파일의 코드에 인라인되지 않지만, 라이브러리 파일에 위치하지 않으므로 참조를 확인할 주소가 없습니다.  
  
 마찬가지로, 함수 인라이닝을 사용하는 프로젝트가 헤더 파일 대신에 .cpp 파일에 함수를 정의하면 LNK2019가 발생합니다.  헤더 파일은 적절한 위치에 포함되지만 .cpp 파일이 컴파일러를 통해 전달할 때 함수만 인라인되므로, 함수가 다른 모듈에서 사용될 때 링커는 이 함수를 확인할 수 없는 외부 참조로 인식합니다.  
  
```  
// LNK2019_FIP.h  
struct testclass {  
   void PublicStatMemFunc1(void);  
};  
```  
  
 두 번째 코드 파일:  
  
```  
// LNK2019_FIP.cpp  
// compile with: /c  
#include "LNK2019_FIP.h"  
inline void testclass::PublicStatMemFunc1(void) {}  
```  
  
 두 번째 코드 파일:  
  
```  
// LNK2019_FIP_2.cpp  
// compile with: LNK2019_FIP.cpp  
// LNK2019 expected  
#include "LNK2019_FIP.h"  
int main() {  
   testclass testclsObject;  
  
   // module cannot see the implementation of PublicStatMemFunc1  
   testclsObject.PublicStatMemFunc1();  
}  
```  
  
## 참고 항목  
 [링커 도구 오류 LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)