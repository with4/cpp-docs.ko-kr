---
title: 컴파일러 경고 (수준 1) C4293 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4293
dev_langs:
- C++
helpviewer_keywords:
- C4293
ms.assetid: babecd96-eb51-41a5-9835-462c7a46dbad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ad588b69db1a0b46efa708b472bfc2218d17c0c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4293"></a>컴파일러 경고(수준 1) C4293
'operator': 시프트 횟수가 음수 이거나 너무 큽니다., 정의 되지 않은 동작  
  
 시프트 횟수가 음수 이거나 너무 큰 경우에 결과 이미지의 동작이 정의 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4293 오류가 생성 됩니다.  
  
```  
// C4293.cpp  
// compile with: /c /W1  
unsigned __int64 combine (unsigned lo, unsigned hi) {  
  
   return (hi << 32) | lo;   // C4293  
  
   // try the following line instead  
   // return ( (unsigned __int64)hi << 32) | lo;  
}  
```