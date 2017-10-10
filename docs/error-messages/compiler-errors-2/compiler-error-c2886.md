---
title: "컴파일러 오류 C2886 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2886
dev_langs:
- C++
helpviewer_keywords:
- C2886
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cbb4ab1d50a4a6c5bb9ea3c392febf786197e0fa
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2886"></a>컴파일러 오류 C2886
'class::identifier': 멤버 using 선언에서 기호를 사용할 수 없습니다  
  
 A `using` 선언에는 네임 스페이스 이름이 같은 기호를 사용 합니다. A `using` 선언이 기본 클래스 멤버를 선언 합니다.  
  
 다음 샘플에서는 C2886 오류가 생성 됩니다.  
  
```  
// C2886.cpp  
// compile with: /c  
namespace Z {  
    int i;  
}  
  
class B {  
protected:  
    int i;  
};  
  
class D : public B {  
    // Error: Z is a namespace  
    using Z::i;   // C2886  
  
    // OK: B is a base class  
    using B::i;  
};  
```
