---
title: "컴파일러 경고 (수준 1) C4730 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4730
dev_langs: C++
helpviewer_keywords: C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 334c53b030097dc822451b0e555a51c90e70d904
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4730"></a>컴파일러 경고 (수준 1) C4730
'main': _m64 혼합 및 부동 소수점에 잘못 된 코드 식으로 인해 수  
  
 함수를 사용 하 여 [__m64](../../cpp/m64.md) 및 **float**/**double** 형식입니다. 같은 실제 MMX와 부동 소수점 레지스터 공유 하기 때문에 레지스터 공간 (사용할 수 없음 동시에)를 사용 하 여 `__m64` 및 **float**/**double** 동일한 형식 함수는 데이터가 손상 되어 예외가 발생할 수 있습니다.  
  
 안전 하 게 사용 하려면 `__m64` 형식 중 하나를 사용 하는 각 명령으로 구분 해야 형식과 같은 함수에 부동 소수점 형식에는 **_m_empty** (mmx 용)에 대 한 또는 **_m_femms** (3DNow! 용) 내장 함수입니다.  
  
 다음 샘플에서는 C4730 오류가 생성 됩니다.  
  
```  
// C4730.cpp  
// compile with: /W1  
// processor: x86  
#include "mmintrin.h"  
  
void func(double)  
{  
}  
  
int main(__m64 a, __m64 b)  
{  
   __m64 m;  
   double f;  
   f = 1.0;  
   m = _m_paddb(a, b);  
   // uncomment the next line to resolve C4730  
   // _m_empty();  
   func(f * 3.0);   // C4730  
}  
```