---
title: "continue 문 (C++) | Microsoft Docs"
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
  - "continue"
  - "continue_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "continue 키워드[C++]"
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# continue 문 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제어를 가장 작은 바깥쪽 [do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md) 또는 [while](../cpp/while-statement-cpp.md) 루프의 제어 식으로 강제로 전송합니다.  
  
## 구문  
  
```  
continue;  
```  
  
## 설명  
 현재 반복에서 나머지 모든 문은 실행되지 않습니다.  루프의 다음 반복은 다음과 같이 결정됩니다.  
  
-   `do` 또는 `while` 루프 내에서 다음 반복은 `do` 또는 `while` 문의 제어 식의 다시 계산에 의해 시작됩니다.  
  
-   `for` 루프\(`for`\(`init-expr`; `cond-expr`; `loop-expr`\) 구문 사용\)에서 `loop-expr` 절이 실행됩니다.  그런 다음 `cond-expr` 절이 다시 계산되고 해당 결과에 따라 루프가 종료되거나 다른 반복이 발생합니다.  
  
 다음 예제에서는 `continue` 문을 사용하여 코드 섹션을 건너뛰고 루프의 다음 반복을 시작하는 방법을 보여 줍니다.  
  
## 예제  
  
```  
// continue_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        i++;  
        printf_s("before the continue\n");  
        continue;  
        printf("after the continue, should never print\n");  
     } while (i < 3);  
  
     printf_s("after the do loop\n");  
}  
```  
  
  **before the continue**  
**before the continue**  
**before the continue**  
**after the do loop**   
## 참고 항목  
 [점프 문](../cpp/jump-statements-cpp.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)