---
title: 컴파일러 오류 C2184 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2184
dev_langs:
- C++
helpviewer_keywords:
- C2184
ms.assetid: 80fc8bff-7d76-4bde-94d2-01d84bb6824a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 068850ea37811cc68c070a968cc2ddc5aa0ce8a5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171756"
---
# <a name="compiler-error-c2184"></a>컴파일러 오류 C2184
'type': __except 식의 형식이 잘못되었습니다. 정수여야 합니다.  
  
 형식이 [__except](../../c-language/try-except-statement-c.md) 문에서 사용되었지만 형식이 허용되지 않습니다.  
  
 다음 샘플에서는 C2184를 생성합니다.  
  
```  
// C2184.cpp  
void f() {  
   int * p;  
   __try{}  
   __except(p){};   // C2184  
}  
```  
  
 해결 방법:  
  
```  
// C2184b.cpp  
// compile with: /c  
void f() {  
   int i = 0;  
   __try{}  
   __except(i){};  
}  
```