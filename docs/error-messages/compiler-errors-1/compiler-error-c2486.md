---
title: 컴파일러 오류 C2486 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2486
dev_langs:
- C++
helpviewer_keywords:
- C2486
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 856d17d9ec816c8216553eca5bb273349ca0040e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33197288"
---
# <a name="compiler-error-c2486"></a>컴파일러 오류 C2486
' __LOCAL_SIZE' 'naked' 특성이 있는 함수에만 사용할 수  
  
 인라인 어셈블리 함수 이름에서에서 `__LOCAL_SIZE` 으로 선언 된 함수의 예약 되는 [naked](../../cpp/naked-cpp.md) 특성입니다.  
  
 다음 샘플에서는 C2486 오류가 생성 됩니다.  
  
```  
// C2486.cpp  
// processor: x86  
void __declspec(naked) f1() {  
   __asm {  
      mov   eax,   __LOCAL_SIZE  
   }  
}  
void f2() {  
   __asm {  
      mov   eax,   __LOCAL_SIZE   // C2486  
   }  
}  
```