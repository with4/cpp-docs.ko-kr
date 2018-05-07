---
title: 컴파일러 경고 (수준 1) C4392 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4392
dev_langs:
- C++
helpviewer_keywords:
- C4392
ms.assetid: 817806ad-06a6-4b9e-8355-e25687c782dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b64159737b9423f3d9ea55489eb28c20a2162d14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4392"></a>컴파일러 경고(수준 1) C4392
'서명': 내장 함수의 인수 개수가 잘못 되었습니다 'number' 인수를 필요 합니다.  
  
 함수 선언에는 컴파일러 내장 함수에 인수 수가 잘못 되었습니다. 결과 이미지가 올바르게 실행 되지 않을 수 있습니다.  
  
 이 경고를 해결 하려면 수정 선언 하거나 선언을 삭제 하 고 간단 #include 적절 한 헤더 파일입니다.  
  
 다음 샘플에서는 C4392 오류가 생성 됩니다.  
  
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