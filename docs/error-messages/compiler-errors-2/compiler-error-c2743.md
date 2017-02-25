---
title: "컴파일러 오류 C2743 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2743"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2743"
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2743
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : \_\_clrcall 소멸자 또는 복사 생성자를 사용하여 네이티브 형식을 Catch할 수 없습니다.  
  
 **\/clr:pure**가 아닌 **\/clr**를 사용하여 컴파일한 모듈에서 네이티브 형식의 예외를 catch하려고 했습니다. 이때 형식의 소멸자나 복사 소멸자에 \_`_clrcall` 호출 규칙이 사용되고 있습니다.  
  
 **\/clr:pure**가 아닌 **\/clr**로 컴파일하는 경우 예외 처리에 필요한 네이티브 형식의 멤버 함수는 [\_\_clrcall](../../cpp/clrcall.md)이 아닌 [\_\_cdecl](../../cpp/cdecl.md)입니다.  `__clrcall` 호출 규칙을 사용하는 멤버 함수의 네이티브 형식은 **\/clr**로 컴파일한 모듈에서 catch할 수 없습니다.  
  
 자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C2743 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2743.cpp  
// compile with: /clr  
public struct S {  
   __clrcall ~S() {}  
};  
  
public struct T {  
   ~T() {}  
};  
  
int main() {  
   try {}  
   catch(S) {}   // C2743  
   // try the following line instead  
   // catch(T) {}  
  
   try {}  
   catch(S*) {}   // OK  
}  
```