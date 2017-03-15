---
title: "컴파일러 경고 (수준 1) C4392 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4392"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4392"
ms.assetid: 817806ad-06a6-4b9e-8355-e25687c782dc
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4392
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'signature' : 내장 함수의 인수 개수가 잘못되었습니다. 'number'개의 인수가 필요합니다.  
  
 컴파일러 내장 함수 선언에 인수 개수가 잘못되었으므로  결과 이미지가 올바로 실행되지 않을 수 있습니다.  
  
 이 경고를 해결하려면 선언을 올바르게 수정하거나 선언을 삭제한 다음 \#include를 사용하여 적합한 헤더 파일을 포함하십시오.  
  
 다음 샘플에서는 C4392 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4392.cpp  
// compile with: /W1  
// processor: x86  
// uncomment the following line and delete the line that  
// generated the warning to resolve  
// #include "xmmintrin.h"  
  
#ifdef  __cplusplus  
extern "C" {  
#endif  
  
extern void _mm_stream_pd(double *dp);   // C4392  
  
#ifdef  __cplusplus  
}  
#endif  
  
int main()  
{  
}  
```