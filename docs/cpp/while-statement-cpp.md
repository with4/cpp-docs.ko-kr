---
title: "while 문 (C++) | Microsoft Docs"
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
  - "while_cpp"
  - "while"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "while 키워드[C++]"
  - "while 키워드[C++], 구문"
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# while 문 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*expression*이 0으로 평가될 때까지 *statement*을 반복적으로 실행합니다.  
  
## 구문  
  
```  
  
      while ( expression )  
   statement  
```  
  
## 설명  
 각 루프를 실행하기 전에  식을 테스트하기 때문에 `while` 루프는 0번 이상 실행됩니다.  *식*은 정수 계열 형식, 포인터 형식 또는 정수 계열이거나 포인터 형식으로의 명확한 변환을 통한 클래스 형식 중 하나를 기반으로 해야 합니다.  
  
 `while` 루프는 문 본문 내에서 [break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md) 또는 [return](../cpp/return-statement-cpp.md)이 실행될 때도 종료할 수 있습니다.  [계속](../cpp/continue-statement-cpp.md)을 사용하여 `while` 루프를 종료하지 않고 현재 반복을 종료합니다.  **continue**는 `while` 루프의 다음 반복으로 제어를 전달합니다.  
  
 다음 코드는 문자열의 후행 밑줄을 트리밍하기 위해 `while` 루프를 사용합니다.  
  
```  
// while_statement.cpp  
  
#include <string.h>  
#include <stdio.h>  
char *trim( char *szSource )  
{  
    char *pszEOS = 0;  
  
    //  Set pointer to character before terminating NULL  
    pszEOS = szSource + strlen( szSource ) - 1;  
  
    //  iterate backwards until non '_' is found   
    while( (pszEOS >= szSource) && (*pszEOS == '_') )  
        *pszEOS-- = '\0';  
  
    return szSource;  
}  
int main()  
{  
    char szbuf[] = "12345_____";  
  
    printf_s("\nBefore trim: %s", szbuf);  
    printf_s("\nAfter trim: %s\n", trim(szbuf));  
}  
```  
  
 종료 조건이 루프의 맨 위에서 계산됩니다.  후행 밑줄이 없을 경우 루프가 실행되지 않습니다.  
  
## 참고 항목  
 [반복 문](../cpp/iteration-statements-cpp.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [do\-while 문\(C\+\+\)](../cpp/do-while-statement-cpp.md)   
 [for 문 \(C\+\+\)](../cpp/for-statement-cpp.md)   
 [범위 기반 for 문\(C\+\+\)](../cpp/range-based-for-statement-cpp.md)