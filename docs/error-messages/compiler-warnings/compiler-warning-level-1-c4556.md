---
title: 컴파일러 경고 (수준 1) C4556 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- xml
- C4556
dev_langs:
- C++
helpviewer_keywords:
- C4556
ms.assetid: e4c0e296-b747-4db1-9608-30b8b74feac2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22d10f7dc73e0d5e39fcad8975114f7cb176b24d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4556"></a>컴파일러 경고(수준 1) C4556
직접 실행 내장 인수 'value'의 값은 'lowerbound-upperbound' 범위를 벗어났습니다.  
  
 하드웨어 명령 내장 일치합니다. 하드웨어 명령에는 상수를 인코딩하는 비트의 고정 된 수 있습니다. 경우 ***값*** 가 범위를 벗어난 경우 인코딩할 수 없으므로 제대로 합니다. 컴파일러는 추가 된 비트를 자릅니다.  
  
 다음 샘플에서는 C4556 오류가 생성 됩니다.  
  
```  
// C4556.cpp  
// compile with: /W1  
// processor: x86 IPF  
#include <xmmintrin.h>  
void test()  
{  
   __m64 m;  
   _m_pextrw(m, 5);   // C4556  
}  
int main()  
{  
}  
```