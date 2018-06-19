---
title: 컴파일러 오류 C3671 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3671
dev_langs:
- C++
helpviewer_keywords:
- C3671
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50b52bb30b24204e810dc350cdb7fef502a93852
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33263637"
---
# <a name="compiler-error-c3671"></a>컴파일러 오류 C3671
'function_1': 함수가 'function_2'를 재정의 하지 않습니다  
  
 명시적 재정의 구문은 사용할 경우 컴파일러는 함수를 재정의 하지 않은 경우 오류를 생성 합니다.  참조 [명시적으로 재정의](../../windows/explicit-overrides-cpp-component-extensions.md) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3671 오류가 발생 합니다.  
  
```  
// C3671.cpp  
// compile with: /clr /c  
ref struct S {  
   virtual void f();  
};  
  
ref struct S1 : S {  
   virtual void f(int) new sealed = S::f;   // C3671  
   virtual void f() new sealed = S::f;  
};  
```