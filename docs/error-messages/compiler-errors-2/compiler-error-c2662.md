---
title: "컴파일러 오류 C2662 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2662"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2662"
ms.assetid: e172c2a4-f29e-4034-8232-e7dc6f83689f
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C2662
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 'this' 포인터를 'type1'에서 'type2'\(으\)로 변환할 수 없습니다.  
  
 컴파일러가 `this` 포인터를 `type1`에서 `type2`로 변환할 수 없습니다.  
  
 이 오류는 `const`가 아닌 멤버 함수를 `const` 개체에 대해 호출하는 경우에 발생할 수 있습니다.  다음과 같이 해결할 수 있습니다.  
  
-   개체 선언에서 `const`를 제거합니다.  
  
-   멤버 함수에 `const`를 추가합니다.  
  
 다음 샘플에서는 C2662 오류가 발생하는 경우를 보여 줍니다.  
  
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
  
 **\/clr**를 사용하여 컴파일하는 경우 정규화하여 관리되는 `const` 또는 `volatile` 형식에 대해 함수를 호출할 수 없습니다.  관리되는 클래스의 const 멤버 함수를 선언할 수 없으므로 관리되는 const 개체에 대해 메서드를 호출할 수 없습니다.  
  
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
  
 다음 샘플에서는 C2662 오류가 발생하는 경우를 보여 줍니다.  
  
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