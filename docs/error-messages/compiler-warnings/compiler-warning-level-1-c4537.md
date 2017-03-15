---
title: "컴파일러 경고 (수준 1) C4537 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4537"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4537"
ms.assetid: 9454493c-d419-475e-8f35-9c00233c9329
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4537
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'object' : 'operator'을\(를\) UDT가 아닌 형식에 적용했습니다.  
  
 사용자 정의 형식의 개체가 필요한 곳에 참조를 전달했습니다.  참조는 개체가 아니지만 인라인 어셈블리 코드에서는 둘의 차이를 구별할 수 없습니다.  컴파일러에서 ***object***가 인스턴스인 것처럼 코드를 생성합니다.  
  
 다음 샘플에서는 C4537 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4537.cpp  
// compile with: /W1 /c  
// processor: x86  
struct S {  
   int member;  
};  
  
void f1(S &s) {  
   __asm mov eax, s.member;   // C4537  
   // try the following code instead  
   // or, make the declaration "void f1(S s)"  
   /*  
   mov eax, s  
   mov eax, [eax]s.member  
   */  
}  
```