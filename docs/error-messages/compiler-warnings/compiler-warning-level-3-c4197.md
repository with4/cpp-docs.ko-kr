---
title: 컴파일러 경고 (수준 3) C4197 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4197
dev_langs:
- C++
helpviewer_keywords:
- C4197
ms.assetid: f766feef-82b0-4d81-8a65-33628c7db196
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa119e0b1afd3f660dd04040965006f1b52cad01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290428"
---
# <a name="compiler-warning-level-3-c4197"></a>컴파일러 경고 (수준 3) C4197
'type': 캐스트의 최상위 volatile은 무시 됩니다.  
  
 컴파일러 검색으로 정규화는 r-value 형식으로 캐스팅할 [휘발성](../../cpp/volatile-cpp.md), 또는 r-value 형식으로 volatile 한정 않았습니다. 일부 형식으로 캐스트 합니다. C 표준 (6.5.3)에 따라 한정 된 형식과 연관 된 속성 l-value 식에 대해서만 의미가 있습니다.  
  
 다음 샘플에서는 C4197 오류가 생성 됩니다.  
  
```  
// C4197.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <signal.h>  
#include <stdlib.h>  
  
void sigproc(int);  
struct S  
{  
   int i;  
} s;  
  
int main()  
{  
   signal(SIGINT, sigproc);  
   s.i = 1;  
   S *pS = &s;  
   for ( ; (volatile int)pS->i ; )   // C4197  
      break;  
   // for ( ; *(volatile int *)&pS->i ; )   // OK  
   //    break;  
}  
  
void sigproc(int) // ctrl-C  
{  
   signal(SIGINT, sigproc);  
   s.i = 0;  
}  
  
```