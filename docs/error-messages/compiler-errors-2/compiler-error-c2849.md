---
title: 컴파일러 오류 C2849 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2849
dev_langs:
- C++
helpviewer_keywords:
- C2849
ms.assetid: e28f6b3e-e0e7-4f92-b006-ebaa81d368e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af882bdd40440cb03a42ae5a7683c02917da83e0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2849"></a>컴파일러 오류 C2849
'소멸자': 인터페이스는 소멸자를 사용할 수 없습니다  
  
 Visual c + + [인터페이스](../../cpp/interface.md) 소멸자를 가질 수 없습니다.  
  
 다음 샘플에서는 C2849 오류가 생성 됩니다.  
  
```  
// C2849.cpp  
// compile with: /c  
__interface C {  
   ~C();   // C2849 destructor not allowed in an interface  
};  
```