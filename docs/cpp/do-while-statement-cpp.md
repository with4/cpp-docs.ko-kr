---
title: "do-while 문(C++) | Microsoft Docs"
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
  - "do-while_cpp"
  - "do-while"
  - "do"
  - "while_cpp"
  - "do_cpp"
  - "while"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "do 키워드[C++]"
  - "do 키워드[C++], do-while"
  - "do-while 키워드[C++]"
  - "while 키워드[C++], do-while"
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# do-while 문(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 종료 조건\(*expression*\)이 0으로 평가될 때까지 *statement*를 반복해서 실행합니다.  
  
## 구문  
  
```  
  
      do  
   statement  
   while ( expression ) ;  
```  
  
## 설명  
 종료 조건은 각 루프를 실행한 후 테스트되므로 `do-while` 루프는 종료 식의 값에 따라 한 번 이상 실행됩니다.  `do-while` 문은 문 본문 내에서 [break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md) 또는 [return](../cpp/return-statement-cpp.md) 문이 실행되는 경우에도 종료될 수 있습니다.  
  
 *expression*은 산술 형식이나 포인터 형식이어야 합니다.  다음과 같이 실행됩니다.  
  
1.  문 본문이 실행됩니다.  
  
2.  다음으로, *expression*이 평가됩니다.  *expression*이 false인 경우 `do-while` 문이 종료되고 프로그램의 다음 문으로 제어가 전달됩니다.  *expression*이 true\(0이 아님\)인 경우에는 프로세스가 1단계부터 반복됩니다.  
  
## 예제  
 다음 샘플에서는 `do-while` 문을 보여 줍니다.  
  
```  
// do_while_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        printf_s("\n%d",i++);  
    } while (i < 3);  
}  
```  
  
## 참고 항목  
 [반복 문](../cpp/iteration-statements-cpp.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [while 문 \(C\+\+\)](../cpp/while-statement-cpp.md)   
 [for 문 \(C\+\+\)](../cpp/for-statement-cpp.md)   
 [범위 기반 for 문\(C\+\+\)](../cpp/range-based-for-statement-cpp.md)