---
title: "컴파일러 오류 C3243 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3243
dev_langs:
- C++
helpviewer_keywords:
- C3243
ms.assetid: 35d8ad1a-377d-47df-be9d-c55eea23340f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: edd1b0ee0625acf97ed5c8d1513ff6f5a03838bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3243"></a>컴파일러 오류 C3243
오버로드 함수가 'interface'에 의해 하나도 정의되지 않았습니다.  
  
 지정된 인터페이스에 없는 멤버를 [명시적으로 재정의](../../cpp/explicit-overrides-cpp.md) 하려고 했습니다.  
  
 다음 샘플에서는 C3243을 생성합니다.  
  
```  
// C3243.cpp  
#pragma warning(disable:4199)  
__interface IX14A {  
   void g();  
};  
  
__interface IX14B {  
   void f();  
   void f(int);  
};  
  
class CX14 : public IX14A, public IX14B {  
public:  
   void IX14A::g();  
   void IX14B::f();  
   void IX14B::f(int);  
};  
  
void CX14::IX14A::f()   // C3243 occurs here  
{  
}  
```