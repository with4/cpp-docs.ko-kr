---
title: "컴파일러 오류 C2015 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2015"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2015"
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2015
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

상수에 문자가 너무 많습니다.  
  
 문자 상수에 문자가 세 개 이상 포함되어 있습니다.  표준 문자 상수의 경우 문자 하나, 긴 문자 상수의 경우에는 문자 두 개로 제한됩니다.  
  
 이스케이프 시퀀스\(예: \\t\)는 단일 문자로 변환됩니다.  
  
## 예제  
 다음 샘플에서는 C2015 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2015.cpp  
// compile with: /c  
  
char test1 = 'error';   // C2015  
char test2 = 'e';   // OK  
```  
  
## 예제  
 Microsoft 확장을 사용하는 경우에도 C2015가 발생할 수 있으며, 문자 상수가 정수로 변환됩니다.  다음 샘플에서는 C2015 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2015b.cpp  
#include <stdio.h>  
  
int main()   
{  
    int a = 'abcde';   // C2015  
  
    int b = 'a';   // 'a' = ascii 0x61  
    printf_s("%x\n", b);  
}  
```