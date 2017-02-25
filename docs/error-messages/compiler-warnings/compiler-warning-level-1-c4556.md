---
title: "컴파일러 경고 (수준 1) C4556 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "xml"
  - "C4556"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4556"
ms.assetid: e4c0e296-b747-4db1-9608-30b8b74feac2
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4556
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

직접 실행 내장 함수 인수의 값 'value'이\(가\) 'lowerbound \- upperbound' 범위를 벗어났습니다.  
  
 내장 함수가 하드웨어 명령과 일치하고  이 하드웨어 명령에는 상수를 인코딩하는 고정된 비트 수가 있습니다.  ***value***가 범위를 벗어나는 값이면 제대로 인코딩할 수 없으므로  컴파일러에서 추가 비트를 자릅니다.  
  
 다음 샘플에서는 C4556 오류가 발생하는 경우를 보여 줍니다.  
  
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