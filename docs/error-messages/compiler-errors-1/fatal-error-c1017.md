---
title: "심각한 오류 C1017 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1017
dev_langs:
- C++
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e28a4b09ef4d62edd97d734e4a3ad64b8a0c2f86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1017"></a>심각한 오류 C1017
정수 계열 상수 식이 잘못되었습니다.  
  
 식에는 `#if` 지시문 존재 하지 않는 또는 상수 식이 아닙니다.  
  
 사용 하 여 정의 된 상수 `#define` 에 사용 되는 경우 정수 상수를 평가 하는 값을 가져야 합니다는 `#if`, `#elif`, 또는 `#else` 지시문입니다.  
  
 다음 샘플에서는 C1017 오류가 생성 됩니다.  
  
```  
// C1017.cpp  
#define CONSTANT_NAME "YES"  
#if CONSTANT_NAME   // C1017  
#endif  
```  
  
 해결 방법:  
  
```  
// C1017b.cpp  
// compile with: /c  
#define CONSTANT_NAME 1  
#if CONSTANT_NAME  
#endif  
```  
  
 때문에 `CONSTANT_NAME` 정수가 아닌 문자열로로 평가 되는 `#if` 지시어 심각한 오류 C1017를 생성 합니다.  
  
 다른 경우 전처리기는 정의 되지 않은 상수 0으로 계산 됩니다. 다음 샘플에 표시 된 대로 의도 하지 않은 결과가 발생할 수 있습니다. `YES`이 정의 되지 않습니다 않았으므로 0으로 계산 합니다. 식 `#if` `CONSTANT_NAME` 사용 되는 코드를 false로 평가 되 `YES` 전처리기에 의해 제거 됩니다. `NO`또한 정의 되지 않은 (영) 이므로 `#elif` `CONSTANT_NAME==NO` true로 평가 (`0 == 0`), 전처리기에서 코드는 `#elif` 보고서의 부분-정확히 반대는 의도 된 동작입니다.  
  
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
  
 컴파일러 전처리기 지시문을 처리 하는 방식을 정확 하 게를 보려면 사용 [/P](../../build/reference/p-preprocess-to-a-file.md), [/E](../../build/reference/e-preprocess-to-stdout.md), 또는 [/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)합니다.