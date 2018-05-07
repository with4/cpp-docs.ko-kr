---
title: 컴파일러 오류 C2490 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2490
dev_langs:
- C++
helpviewer_keywords:
- C2490
ms.assetid: 9de6bddd-b2e2-4ce6-b33b-201a8c2c8c54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc366178c31f900b031aacca278e39cc0c2eb493
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2490"></a>컴파일러 오류 C2490
' keyword' 'naked' 특성이 있는 함수에 사용할 수 없습니다  
  
 으로 정의 된 함수 [naked](../../cpp/naked-cpp.md) 구조적된 예외 처리를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2490 오류가 생성 됩니다.  
  
```  
// C2490.cpp  
// processor: x86  
__declspec( naked ) int func() {  
   __try{}   // C2490, structured exception handling  
}  
```