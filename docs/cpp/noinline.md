---
title: "noinline | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "noinline"
  - "noinline_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec 키워드[C++], noinline"
  - "noinline __declspec 키워드"
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# noinline
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 **\_\_declspec\(noinline\)**은 특정 멤버 함수\(클래스의 함수\)를 인라인 처리하지 않도록 컴파일러에 지시합니다.  
  
 함수가 작고 코드 성능에 심각한 영향을 주지 않는 경우 함수를 인라인 처리하지 않는 것이 적합할 수 있습니다.  즉, 오류 조건을 처리하는 함수처럼 함수가 작고 자주 호출될 가능성이 적은 경우가 여기에 해당합니다.  
  
 함수가 `noinline`으로 표시된 경우 호출하는 함수는 더 작기 때문에 그 자체가 컴파일러 인라인 처리의 후보가 됩니다.  
  
```  
class X {  
   __declspec(noinline) int mbrfunc() {  
      return 0;   
   }   // will not inline  
};  
```  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [inline, \_\_inline, \_\_forceinline](../misc/inline-inline-forceinline.md)