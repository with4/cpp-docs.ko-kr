---
title: "컴파일러 오류 C2490 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2490
dev_langs:
- C++
helpviewer_keywords:
- C2490
ms.assetid: 9de6bddd-b2e2-4ce6-b33b-201a8c2c8c54
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3c71f65364923af09e259cc722b5472f3603ba8f
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

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
