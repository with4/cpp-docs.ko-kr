---
title: "컴파일러 경고 (수준 1) C4488 | Microsoft Docs"
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
  - "C4488"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4488"
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4488
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 인터페이스 메서드 'interface\_method'을\(를\) 구현하려면 'keyword' 키워드가 있어야 합니다.  
  
 클래스에서는 이 클래스가 직접 파생된 대상 인터페이스의 모든 멤버를 구현해야 합니다.  구현된 멤버는 공용으로 액세스할 수 있어야 하고 가상 멤버로 표시되어야 합니다.  
  
## 예제  
 C4488은 구현된 멤버가 공용이 아닌 경우 발생할 수 있습니다.  다음 샘플에서는 C4488 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4488.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
// implemented member not public  
ref class B : MyI { virtual void f1() {} };  // C4488  
  
// OK  
ref class C : MyI {  
public:  
   virtual void f1() {}  
};  
```  
  
## 예제  
 C4488은 구현된 멤버가 가상 멤버로 표시되지 않은 경우 발생할 수 있습니다.  다음 샘플에서는 C4488 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4488_b.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
ref struct B : MyI { void f1() {} };   // C4488  
ref struct C : MyI { virtual void f1() {} };   // OK  
```