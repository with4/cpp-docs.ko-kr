---
title: 컴파일러 오류 C2884 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2884
dev_langs:
- C++
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41bacfc53f8b1f14a9b7409a43db39fd943739e5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2884"></a>컴파일러 오류 C2884
'name': 'function' 지역 함수와 충돌 using 선언으로 인해  
  
 함수를 두 번 이상 정의 하려고 했습니다. 첫 번째 정의 로컬 정의입니다. 포함 된 네임 스페이스에서 두 번째는는 `using` 선언 합니다.  
  
 다음 샘플에서는 C2884 오류가 생성 됩니다.  
  
```  
// C2884.cpp  
namespace A {  
   void z(int);  
}  
  
void f() {  
   void z(int);  
   using A::z;   // C2884 z is already defined  
}  
```