---
title: "컴파일러 경고 (수준 1) C4382 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4382"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4382"
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4382
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' throw : \_\_clrcall 소멸자 또는 복사 생성자가 있는 형식은 \/clr:pure 모듈에서만 catch할 수 있습니다.  
  
 **\/clr:pure**가 아닌 **\/clr**로 컴파일하는 경우 예외 처리에 필요한 네이티브 형식의 멤버 함수는 [\_\_clrcall](../../cpp/clrcall.md)이 아닌 [\_\_cdecl](../../cpp/cdecl.md)입니다.  `__clrcall` 호출 규칙을 사용하는 멤버 함수의 네이티브 형식은 **\/clr**로 컴파일한 모듈에서 catch할 수 없습니다.  
  
 예외를 **\/clr:pure**를 사용하여 컴파일한 모듈에서 catch하는 경우에는 이 경고를 무시할 수 있습니다.  
  
 자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4382 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4382.cpp  
// compile with: /clr /W1 /c  
struct S {  
   __clrcall ~S() {}  
};  
  
struct T {  
   ~T() {}  
};  
  
int main() {  
   S s;  
   throw s;   // C4382  
  
   S * ps = &s;  
   throw ps;   // OK  
  
   T t;  
   throw t;   // OK  
}  
```