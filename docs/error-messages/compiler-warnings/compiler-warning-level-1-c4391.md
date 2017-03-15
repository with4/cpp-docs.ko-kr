---
title: "컴파일러 경고 (수준 1) C4391 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4391"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4391"
ms.assetid: 95c6182c-fae9-4174-8f7b-98aa352e68ca
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4391
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'signature' : 내장 함수의 반환 형식이 잘못되었습니다. 'type'이\(가\) 필요합니다.  
  
 컴파일러 내장 함수 선언에 잘못된 반환 형식이 있으므로  결과 이미지가 올바로 실행되지 않을 수 있습니다.  
  
 이 경고를 해결하려면 선언을 올바르게 수정하거나 선언을 삭제한 다음 \#include를 사용하여 적합한 헤더 파일을 포함하십시오.  
  
 다음 샘플에서는 C4391 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4391.cpp  
// compile with: /W1  
// processor: x86  
// uncomment the following line and delete the line that  
// generated the warning to resolve  
// #include "xmmintrin.h"  
  
#ifdef  __cplusplus  
extern "C" {  
#endif  
  
extern void _mm_load_ss(float *p);   // C4391  
  
#ifdef  __cplusplus  
}  
#endif  
  
int main()  
{  
}  
```