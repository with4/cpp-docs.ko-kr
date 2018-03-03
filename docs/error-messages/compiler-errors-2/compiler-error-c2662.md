---
title: "컴파일러 오류 C2662 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2662
dev_langs:
- C++
helpviewer_keywords:
- C2662
ms.assetid: e172c2a4-f29e-4034-8232-e7dc6f83689f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4370754983b71e842b172eade8da6058a8d1dbc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2662"></a>컴파일러 오류 C2662
'function': 'type1'에서 'this'이 포인터를 'type2' (으)로 변환할 수 없습니다  
  
 컴파일러가 변환 하지 못했습니다 된 `this` 에서 포인터 `type1` 를 `type2`합니다.  
  
 비-를 호출 하 여이 오류가 발생할 수 있습니다`const` 에 멤버 함수는 `const` 개체입니다.  가능한 해결 방법:  
  
-   제거는 `const` 개체 선언에서 합니다.  
  
-   추가 `const` 멤버 함수에 있습니다.  
  
 다음 샘플에서는 C2662 오류가 생성 됩니다.  
  
```  
// C2662.cpp  
class C {  
public:  
   void func1();  
   void func2() const{}  
} const c;  
  
int main() {  
   c.func1();   // C2662  
   c.func2();   // OK  
}  
```  
  
 로 컴파일할 때 **/clr**에 함수를 호출할 수는 `const` 또는 `volatile` 관리 되는 형식을 한정 합니다. Const 관리 개체에서 메서드를 호출할 수 없습니다의 관리 되는 클래스는 const 멤버 함수를 선언할 수 없습니다.  
  
```  
// C2662_b.cpp  
// compile with: /c /clr  
ref struct M {  
   property M^ Type {  
      M^ get() { return this; }  
   }  
  
   void operator=(const M %m) {  
      M ^ prop = m.Type;   // C2662  
   }  
};  
  
ref struct N {  
   property N^ Type {  
      N^ get() { return this; }  
   }  
  
   void operator=(N % n) {  
      N ^ prop = n.Type;   // OK  
   }  
};  
```  
  
 다음 샘플에서는 C2662 오류가 생성 됩니다.  
  
```  
// C2662_c.cpp  
// compile with: /c  
// C2662 expected  
typedef int ISXVD;  
typedef unsigned char BYTE;  
  
class LXBASE {  
protected:  
    BYTE *m_rgb;  
};  
  
class LXISXVD:LXBASE {  
public:  
   // Delete the following line to resolve.  
   ISXVD *PMin() { return (ISXVD *)m_rgb; }  
  
   ISXVD *PMin2() const { return (ISXVD *)m_rgb; };   // OK  
};  
  
void F(const LXISXVD *plxisxvd, int iDim) {  
   ISXVD isxvd;  
   // Delete the following line to resolve.  
   isxvd = plxisxvd->PMin()[iDim];  
  
   isxvd = plxisxvd->PMin2()[iDim];    
}  
```