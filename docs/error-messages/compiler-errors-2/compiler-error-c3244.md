---
title: "컴파일러 오류 C3244 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3244
dev_langs:
- C++
helpviewer_keywords:
- C3244
ms.assetid: dae6c49b-5212-4206-8f61-d4010c0b9969
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 08758b22847e07442aafdfa2c7d9d5cf1381c5e2
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3244"></a>컴파일러 오류 C3244
'method': 이 메서드는 'interface'에 의해 정의되었습니다('interface'에 의해 정의되지 않음).  
  
 하려고 [명시적으로 재정의](../../cpp/explicit-overrides-cpp.md) 지정된 된 인터페이스에는 없지만 다른 기본 클래스에 있는 멤버입니다.  
  
 다음 샘플에서는 C3244를 생성합니다.  
  
```  
// C3244.cpp  
#pragma warning(disable:4199)  
  
__interface IX15A {  
   void f();  
};  
  
__interface IX15B {  
   void g();  
};  
  
class CX15 : public IX15A, public IX15B {  
public:        
   void IX15A::f();  
   void IX15B::g();  
};  
  
void CX15::IX15A::g()   // C3244 occurs here  
{  
}  
```
