---
title: "컴파일러 경고 (수준 1) C4730 | Microsoft Docs"
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
  - "C4730"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4730"
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4730
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'main' : \_m64 및 부동 소수점 식을 혼합하면 코드가 잘못될 수 있습니다.  
  
 함수에서 [\_\_m64](../../cpp/m64.md) 및 **float**\/**double** 형식을 사용하고 있습니다.  MMX와 부동 소수점 레지스터는 같은 실제 레지스터 공간을 공유하여 동시에 사용할 수 없으므로 같은 함수에 `__m64` 및 **float**\/**double** 형식을 사용하면 데이터가 손상되어 예외가 발생할 수 있습니다.  
  
 같은 함수에 `__m64` 형식과 부동 소수점 형식을 안전하게 사용하려면 한 형식을 사용하는 각 명령을 **\_m\_empty\(\)**\(MMX용\) 또는 **\_m\_femms\(\)**\(3DNow\!용\) 내장 함수를 통해 분리해야 합니다.  
  
 다음 샘플에서는 C4730 오류가 발생하는 경우를 보여 줍니다.  
  
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