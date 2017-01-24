---
title: "__noop | Microsoft Docs"
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
  - "__noop_cpp"
  - "__noop"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__noop 키워드[C++]"
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __noop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `__noop` 내장 함수를 무시 하도록 지정 하 고 인수 목록을 구문 분석할 수 있지만 인수에 대 한 코드를 생성할 수 있습니다.  가변 개수의 인수를 사용 하는 전역 디버그 함수에서 사용 하기 위해 만들어졌습니다.  
  
 변환 컴파일러는 `__noop` 0 컴파일 타임에 내장.  
  
## 예제  
 다음 코드를 사용할 수 있습니다 보여 줍니다. `__noop`.  
  
```  
// compiler_intrinsics__noop.cpp  
// compile with or without /DDEBUG  
#include <stdio.h>  
  
#if DEBUG  
   #define PRINT   printf_s  
#else  
   #define PRINT   __noop  
#endif  
  
int main() {  
   PRINT("\nhello\n");  
}  
```  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)