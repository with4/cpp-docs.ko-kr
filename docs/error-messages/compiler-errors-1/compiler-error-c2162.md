---
title: 컴파일러 오류 C2162 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2162
dev_langs:
- C++
helpviewer_keywords:
- C2162
ms.assetid: 34923628-d35e-48ab-9072-b95e3b5f6b45
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc7cfebd4563e4d41f6ca50e2cdec667e82fb5f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2162"></a>컴파일러 오류 C2162
예상된 매크로 정식 매개 변수  
  
 문자열 화 연산자 (#) 뒤의 토큰이 정식 매개 변수 이름이 아닙니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2162 오류가 생성 됩니다.  
  
```  
// C2162.cpp  
// compile with: /c  
#include <stdio.h>  
  
#define print(a) printf_s(b)   // OK  
#define print(a) printf_s(#b)    // C2162  
```