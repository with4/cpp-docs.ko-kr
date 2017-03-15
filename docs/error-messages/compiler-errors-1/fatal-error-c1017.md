---
title: "심각한 오류 C1017 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1017"
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 심각한 오류 C1017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정수 계열 상수 식이 잘못되었습니다.  
  
 `#if` 지시문의 식이 없거나 식이 상수가 아닙니다.  
  
 `#define`을 사용하여 정의한 상수가 `#if`, `#elif` 또는 `#else` 지시문에 사용되는 경우 정수 계열 상수인 값을 사용해야 합니다.  
  
 다음 샘플에서는 C1017 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C1017.cpp  
#define CONSTANT_NAME "YES"  
#if CONSTANT_NAME   // C1017  
#endif  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C1017b.cpp  
// compile with: /c  
#define CONSTANT_NAME 1  
#if CONSTANT_NAME  
#endif  
```  
  
 `CONSTANT_NAME`이 정수가 아니라 문자열이므로 `#if` 지시문은 심각한 오류인 C1017을 발생시킵니다.  
  
 다른 경우에 전처리기는 정의되지 않은 상수를 0으로 계산하므로,  다음 샘플에 나타난 것처럼 의도하지 않은 결과가 생성됩니다.  `YES`는 정의되지 않았으므로 0으로 계산됩니다.  `#if` `CONSTANT_NAME` 식은 false가 되며 `YES`에 사용되는 코드는 전처리기에 의해 제거됩니다.  `NO`도 정의되지 않았으므로 0으로 계산되고, `#elif` `CONSTANT_NAME==NO`는 true\(`0 == 0`\)가 되며, 의도한 동작의 정반대로 전처리기가 문의 `#elif` 부분에 있는 코드는 그대로 둡니다.  
  
```  
// C1017c.cpp  
// compile with: /c  
#define CONSTANT_NAME YES  
#if CONSTANT_NAME  
   // Code to use on YES...  
#elif CONSTANT_NAME==NO  
   // Code to use on NO...  
#endif  
```  
  
 컴파일러가 전처리기 지시문을 처리하는 방법을 정확하게 알아보려면 [\/P](../../build/reference/p-preprocess-to-a-file.md), [\/E](../../build/reference/e-preprocess-to-stdout.md) 또는 [\/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)를 사용하십시오.