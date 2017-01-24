---
title: "if-else 문 (C++) | Microsoft Docs"
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
  - "else_cpp"
  - "else"
  - "if_cpp"
  - "if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "else 키워드[C++]"
  - "if 키워드[C++]"
  - "if 키워드[C++], if-else"
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# if-else 문 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

조건부 분기를 제어합니다.  
  
## 구문  
  
```  
  
      if ( expression )  
   statement1  
[else  
   statement2]  
```  
  
## 설명  
 *expression*의 값이 0이 아니면 *statement1*이 실행됩니다.  선택적인 **else**가 있을 경우 *expression*의 식이 0이면 *statement2*가 실행됩니다.  *식*은 산술 또는 포인터 형식이거나, 산술 또는 포인터 형식으로의 명확한 변환을 정의하는 클래스 형식 중 하나를 기반으로 해야 합니다. \(변환에 대한 자세한 내용은 [표준 변환](../cpp/standard-conversions.md)을 참조하십시오.\)  
  
 **if** 문의 두 형식에서, 구조체를 제외한 모든 값을 저장할 수 있는 *식*과 모든 파생 작업이 계산됩니다.  제어는 *문* 중 하나에 [break](../cpp/break-statement-cpp.md), [continue](../cpp/continue-statement-cpp.md) 또는 [goto](../cpp/goto-statement-cpp.md)가 포함되지 않은 경우 **if** 문에서 프로그램의 다음 문으로 전달됩니다.  
  
 `if...else` 문의 **else** 절은 해당 **else** 문이 없는 같은 범위의 가장 가까운 이전 **if** 문에 연결됩니다.  
  
 이 샘플을 `if...else` 쌍에 대해 명확하게 하도록 중괄호의 주석 처리를 제거합니다.  
  
## 예제  
  
```  
// if_else_statement.cpp  
#include <stdio.h>  
  
int main()   
{  
   int x = 0;  
   if (x == 0)  
   {  
      printf_s("x is 0!\n");  
   }  
   else  
   {  
      printf_s("x is not 0!\n"); // this statement will not be executed  
   }  
  
   x = 1;  
   if (x == 0)  
   {  
      printf_s("x is 0!\n"); // this statement will not be executed  
   }  
   else  
   {  
      printf_s("x is not 0!\n");  
   }  
  
   return 0;  
}  
```  
  
  **x는 0입니다\!**  
**x가 0\!가 아닌 경우**   
## 참고 항목  
 [선택문](../cpp/selection-statements-cpp.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [switch 문 \(C\+\+\)](../cpp/switch-statement-cpp.md)