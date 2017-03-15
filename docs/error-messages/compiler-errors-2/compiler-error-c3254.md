---
title: "컴파일러 오류 C3254 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3254"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3254"
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3254
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'explicit override' : 클래스에 명시적 재정의 'override'이\(가\) 포함되어 있지만 함수 선언을 포함하는 인터페이스에서 파생되지 않습니다.  
  
 메서드에 대한 [명시적으로 재정의](../../cpp/explicit-overrides-cpp.md)를 수행할 때, 재정의를 포함하는 클래스는 오버로드하고 있는 함수를 포함하는 형식으로부터 직접 또는 간접적으로 파생되어야 합니다.  
  
 다음 샘플에서는 C3254 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3254.cpp  
__interface I  
{  
   void f();  
};  
  
__interface I1 : I  
{  
};  
  
struct A /* : I1 */  
{  
   void I1::f()  
   {   // C3254, uncomment : I1 to resolve this C3254  
   }  
};  
  
int main()  
{  
}  
```