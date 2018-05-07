---
title: 컴파일러 오류 C2671 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2671
dev_langs:
- C++
helpviewer_keywords:
- C2671
ms.assetid: fc0ee40f-c8f3-408f-b89d-745d149c4169
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22812808ce6e159c0f35d9dc2de8e269ecc23cac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2671"></a>컴파일러 오류 C2671
'function': 정적 멤버 함수에는 'this' 포인터가 없는 합니다.  
  
 A `static` 멤버 함수에 액세스 하려고 했습니다. `this`합니다.  
  
 다음 샘플에서는 C2671 오류가 생성 됩니다.  
  
```  
// C2671.cpp  
struct S {  
   static S* const func() { return this; }  // C2671  
};  
```