---
title: "사용되지 않음 (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.deprecated"
  - "deprecated_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "deprecated pragma"
  - "pragma, deprecated"
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 사용되지 않음 (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**deprecated** pragma를 사용하면 함수, 형식 또는 다른 식별자가 향후 릴리스에서 더 이상 지원되지 않거나 더 이상 사용되지 않음을 나타낼 수 있습니다.  
  
## 구문  
  
```  
  
#pragma deprecated( identifier1 [,identifier2, ...] )  
```  
  
## 설명  
 컴파일러가 사용되지 않는 기호를 발견하면 [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)가 발생합니다.  
  
 매크로 이름을 사용하지 않을 수 있습니다.  매크로 이름을 따옴표로 묶지 않으면 매크로 확장이 발생합니다.  
  
 [deprecated](../cpp/deprecated-cpp.md) `__declspec` 한정자를 사용하면 특정 형식의 오버로드된 함수에 사용되지 않음 상태를 지정할 수 있습니다.  
  
## 예제  
  
```  
// pragma_directive_deprecated.cpp  
// compile with: /W3  
#include <stdio.h>  
void func1(void) {  
}  
  
void func2(void) {  
}  
  
int main() {  
   func1();  
   func2();  
   #pragma deprecated(func1, func2)  
   func1();   // C4995  
   func2();   // C4995  
}  
```  
  
 다음 샘플에서는 클래스를 사용하지 않는 방법을 보여 줍니다.  
  
```  
// pragma_directive_deprecated2.cpp  
// compile with: /W3  
#pragma deprecated(X)  
class X {  // C4995  
public:  
   void f(){}  
};  
  
int main() {  
   X x;   // C4995  
}  
```  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)