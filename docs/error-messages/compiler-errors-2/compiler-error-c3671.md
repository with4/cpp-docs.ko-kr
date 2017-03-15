---
title: "컴파일러 오류 C3671 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3671"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3671"
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3671
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function\_1' : 함수가 'function\_2'을\(를\) 재정의하지 않습니다.  
  
 명시적 재정의 구문을 사용할 때 함수가 재정의되지 않으면 컴파일러에서 오류가 발생합니다.  자세한 내용은 [Explicit Overrides](../../windows/explicit-overrides-cpp-component-extensions.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3671 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3671.cpp  
// compile with: /clr /c  
ref struct S {  
   virtual void f();  
};  
  
ref struct S1 : S {  
   virtual void f(int) new sealed = S::f;   // C3671  
   virtual void f() new sealed = S::f;  
};  
```