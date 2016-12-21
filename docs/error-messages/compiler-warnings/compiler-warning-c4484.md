---
title: "컴파일러 경고 C4484 | Microsoft Docs"
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
  - "C4484"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4484"
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 C4484
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'override\_function' : 기본 ref 클래스 메서드 'base\_class\_function'과\(와\) 일치하지만 'virtual', 'new' 또는 'override'로 표시되어 있지 않습니다. 'new'\('virtual' 아님\)로 가정합니다.  
  
 **\/clr**를 사용하여 컴파일하는 경우에는 컴파일러가 기본 클래스 함수를 암시적으로 재정의하지 않습니다. 즉, vtable에 함수의 새 슬롯이 할당됩니다.  이 문제를 해결하려면 함수가 재정의인지 여부를 명시적으로 지정합니다.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [override](../../windows/override-cpp-component-extensions.md)  
  
-   [new \(new slot in vtable\)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
 C4484는 항상 오류로서 발생합니다.  C4484를 비활성화하려면 [경고](../../preprocessor/warning.md) pragma를 사용하십시오.  
  
## 예제  
 다음 샘플에서는 C4484 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4484.cpp  
// compile with: /clr  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : A {  
   void Test() {}   // C4484  
};  
  
// OK  
ref struct C {  
   virtual void Test() {}  
   virtual void Test2() {}  
};  
  
ref struct D : C {  
   virtual void Test() new {}  
   virtual void Test2() override {}  
};  
```