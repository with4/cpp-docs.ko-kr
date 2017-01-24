---
title: "컴파일러 오류 C3861 | Microsoft Docs"
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
  - "C3861"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3861"
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3861
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 식별자를 찾을 수 없습니다.  
  
 컴파일러가 인수 종속 조회를 사용하는 경우에도 식별자에 대한 참조를 확인할 수 없습니다.  
  
 이 오류를 해결하려면 식별자 선언에서 대\/소문자 및 철자를 확인합니다.  [범위 확인 연산자](../../cpp/scope-resolution-operator.md) 및 네임스페이스 [using 지시문](../../misc/using-directive-cpp.md)이 올바르게 사용되는지 확인합니다.  식별자가 헤더 파일에 선언된 경우 헤더가 참조되기 전에 포함되었는지 확인합니다.  또한 식별자가 [조건부 컴파일 지시문](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)으로 제외되지 않는지 확인합니다.  
  
## 예제  
 다음 샘플에서는 C3861을 생성합니다.  
  
```  
// C3861.cpp  
void f2(){}  
int main() {  
   f();   // C3861  
   f2();   // OK  
}  
```  
  
## 예제  
 이제 C\+\+ 표준 라이브러리의 예외 클래스는 `std` 네임스페이스에 있습니다.  
  
```  
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