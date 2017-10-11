---
title: "컴파일러 오류 C3241 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3241
dev_langs:
- C++
helpviewer_keywords:
- C3241
ms.assetid: 2ca14879-bba0-4a23-b22a-72cfff92d6a4
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f704b466edc30fe3960ef0e2cedebad692015531
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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
