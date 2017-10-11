---
title: "컴파일러 오류 c 2784 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2784
dev_langs:
- C++
helpviewer_keywords:
- C2784
ms.assetid: 3d761fe2-881c-48bd-afae-e2e714e20473
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c65b03e098b1e0917e554052ee3c8ebfa7181193
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2784"></a>컴파일러 오류 c 2784
'declaration': 'type'의 템플릿 인수를 'type'에서 추론할 수 없습니다.  
  
 컴파일러가 제공된 함수 인수에서 템플릿 인수를 확인할 수 없습니다.  
  
 다음 샘플에서는 C2784를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2784.cpp  
template<class T> class X {};  
template<class T> void f(X<T>) {}  
  
int main() {  
   X<int> x;  
   f(1);   // C2784  
  
   // To fix it, try the following line instead  
   f(x);  
}  
```
