---
title: 컴파일러 경고 (수준 3) C4645 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4645
dev_langs:
- C++
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 718afb6b8336e36e0c0244cbdccd8af16ac4167f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4645"></a>컴파일러 경고(수준 3) C4645
__declspec(noreturn)으로 선언된 함수에 return 문이 있습니다.  
  
 A [return](../../cpp/return-statement-in-program-termination-cpp.md) 문이 [noreturn](../../cpp/noreturn.md) `__declspec` 한정자로 표시된 함수에 있습니다. `return` 문이 무시되었습니다.  
  
 다음 샘플에서는 C4645를 생성합니다.  
  
```  
// C4645.cpp  
// compile with:  /W3  
void __declspec(noreturn) func() {  
   return;   // C4645, delete this line to resolve  
}  
  
int main() {  
}  
```