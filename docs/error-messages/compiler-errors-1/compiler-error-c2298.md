---
title: 컴파일러 오류 C2298 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2298
dev_langs:
- C++
helpviewer_keywords:
- C2298
ms.assetid: eb0120ad-c850-4bdd-911d-0361229cc859
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d469c00998d849c21db652f1f5033c5a9b46c8a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171884"
---
# <a name="compiler-error-c2298"></a>컴파일러 오류 C2298
'operation': 멤버 함수 식에 대 한 포인터에서 잘못 된 작업  
  
 멤버 함수 식에 대 한 포인터는 멤버 함수를 호출 해야 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2298 오류가 발생 합니다.  
  
```  
// C2298.cpp  
#include <stdio.h>  
  
struct X {  
   void mf() {  
      puts("in X::mf");  
   }  
  
   void mf2() {  
      puts("in X::mf2");  
   }  
};  
  
X x;  
// pointer to member functions with no params and void return in X  
typedef void (X::*pmf_t)();   
  
// a pointer to member function X::mf  
void (X::*pmf)() = &X::mf;  
  
int main() {  
   int (*pf)();  
   pf = x.*pmf;   // C2298  
   +(x.*pmf);     // C2298  
  
   pmf_t pf2 = &X::mf2;  
   (x.*pf2)();   // uses X::mf2  
   (x.*pmf)();   // uses X::mf  
}  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2298 오류가 발생 합니다.  
  
```  
// C2298_b.cpp  
// compile with: /c  
void F() {}  
  
class Measure {  
public:  
   void SetTrackingFunction(void (Measure::*fnc)()) {  
      TrackingFunction = this->*fnc;   // C2298  
      TrackingFunction = fnc;   // OK  
      GlobalTracker = F;   // OK  
   }  
private:  
   void (Measure::*TrackingFunction)(void);  
   void (*GlobalTracker)(void);  
};  
```