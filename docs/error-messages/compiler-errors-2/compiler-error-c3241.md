---
title: 컴파일러 오류 C3241 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3241
dev_langs:
- C++
helpviewer_keywords:
- C3241
ms.assetid: 2ca14879-bba0-4a23-b22a-72cfff92d6a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1a3849dd404c82811eee9176fe87861cfd4a435
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250312"
---
# <a name="compiler-error-c3241"></a>컴파일러 오류 C3241
'method':이 메서드는 'interface' 의해 정의 되지 않았습니다  
  
 명시적으로 함수를 재정의할 때 함수 시그니처 재정의 하는 함수에 대 한 선언이 일치 해야 합니다.  
  
 다음 샘플에서는 C3241 오류가 생성 됩니다.  
  
```  
// C3241.cpp  
#pragma warning(disable:4199)  
  
__interface IX12A {  
   void mf();  
};  
  
__interface IX12B {  
   void mf(int);  
};  
  
class CX12 : public IX12A, public IX12B { // C3241  
   void IX12A::mf(int);  
};  
```