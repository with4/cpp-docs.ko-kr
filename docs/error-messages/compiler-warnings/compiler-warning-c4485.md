---
title: "컴파일러 경고 C4485 | Microsoft Docs"
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
  - "C4485"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4485"
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 C4485
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'override\_function' : 기본 ref 클래스 메서드 'base\_class\_function'과\(와\) 일치하지만 'new' 또는 'override'로 표시되어 있지 않습니다. 'new'\(및 'virtual'\)로 가정합니다.  
  
 `virtual` 키워드 사용에 관계없이 접근자는 기본 클래스 접근자 함수를 재정의하지만 `override` 또는 `new` 지정자는 재정의 함수 시그니처의 일부가 아닙니다.  이 경고를 해결하려면 `new` 또는 `override` 지정자를 추가하십시오.  
  
 자세한 내용은 [override](../../windows/override-cpp-component-extensions.md) 및 [new \(new slot in vtable\)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)를 참조하십시오.  
  
 C4485는 항상 오류로서 발생합니다.  C4485가 표시되지 않도록 하려면 [경고](../../preprocessor/warning.md) pragma를 사용합니다.  
  
## 예제  
 다음 샘플에서는 C4485 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4485.cpp  
// compile with: /clr  
delegate void Del();  
  
ref struct A {  
   virtual event Del ^E;  
};  
  
ref struct B : A {  
   virtual event Del ^E;   // C4485  
};  
  
ref struct C : B {  
   virtual event Del ^E {  
      void raise() override {}  
      void add(Del ^) override {}  
      void remove(Del^) override {}  
   }  
};  
```