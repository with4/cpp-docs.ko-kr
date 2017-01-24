---
title: "컴파일러 오류 C2140 | Microsoft Docs"
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
  - "C2140"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2140"
ms.assetid: d44a0500-002c-4632-9e5e-c71c3a473ec4
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2140
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 제네릭 형식 매개 변수에 종속된 형식은 컴파일러 내장 형식 특성 'trait'에 대한 인수로 사용할 수 없습니다.  
  
 잘못된 형식 지정자를 형식 특성에 전달했습니다.  
  
 자세한 내용은 [Compiler Support for Type Traits](../../windows/compiler-support-for-type-traits-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C2140 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2140.cpp  
// compile with: /clr /c  
template <class T>  
  
struct is_polymorphic {  
   static const bool value = __is_polymorphic(T);  
};  
  
class x {};  
  
generic <class T>  
ref class C {  
   void f() {  
      System::Console::WriteLine(__is_polymorphic(T));   // C2140  
      System::Console::WriteLine(is_polymorphic<T>::value);   // C2140  
  
      System::Console::WriteLine(__is_polymorphic(x));   // OK  
      System::Console::WriteLine(is_polymorphic<x>::value);   // OK  
   }  
};  
```