---
title: 컴파일러 경고 (수준 1) C4033 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4033
dev_langs:
- C++
helpviewer_keywords:
- C4033
ms.assetid: 189a9ec3-ff6d-49dd-b9b2-530b28bbb7c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c5df24b6b86bfc07c36b84cd6094515f9aa31f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4033"></a>컴파일러 경고(수준 1) C4033
'function'은 값을 반환해야 합니다.  
  
 함수가 값을 반환하지 않습니다. 정의되지 않은 값이 반환됩니다.  
  
 반환 값 없이 `return` 을 사용하는 함수를 `void`형식으로 선언해야 합니다.  
  
 이 오류는 C 언어 코드용입니다.  
  
 다음 샘플에서는 C4033을 생성합니다.  
  
```  
// C4033.c  
// compile with: /W1 /LD  
int test_1(int x)   // C4033 expected  
{  
   if (x)  
   {  
      return;   // C4033  
   }  
}  
```