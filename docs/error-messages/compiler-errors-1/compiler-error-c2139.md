---
title: "컴파일러 오류 C2139 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2139"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2139"
ms.assetid: 31e047c0-5bf9-46c2-b6de-b627ea6a5768
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2139
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 정의되지 않은 클래스는 컴파일러 내장 형식 특성 'trait'에 대한 인수로 사용할 수 없습니다.  
  
 잘못된 인수를 형식 특성에 전달했습니다.  
  
 자세한 내용은 [Compiler Support for Type Traits](../../windows/compiler-support-for-type-traits-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C2139 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2139.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
template <class T>  
struct is_polymorphic {  
   static const bool value = __is_polymorphic(T);  
};  
  
class C;  
class D {};  
  
class E {  
public:  
   virtual void Test() {}  
};  
  
int main() {  
   cout << is_polymorphic<C>::value << endl;   // C2139  
   cout << is_polymorphic<D>::value << endl;   // OK  
   cout << is_polymorphic<E>::value << endl;   // OK  
}  
```