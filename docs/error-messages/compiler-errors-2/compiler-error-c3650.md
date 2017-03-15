---
title: "컴파일러 오류 C3650 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3650"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3650"
ms.assetid: ca4d8de4-b027-4d13-9b9f-03ca62905c33
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3650
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface\_method' : 명시적 재정의로 사용할 수 없습니다. 기본 클래스의 가상 멤버 함수여야 합니다.  
  
 가상이 아닌 멤버에 대한 명시적 재정의를 수행하려고 했습니다.  
  
 자세한 내용은 [명시적으로 재정의](../../windows/explicit-overrides-cpp-component-extensions.md)를 참조하십시오.  
  
 다음 샘플에서는 C3650 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3650.cpp  
// compile with: /clr  
public interface struct I {  
   void a();  
};  
  
public ref class S {  
public:  
   static int f() { return 0; }  
   static int g() { return 0; }  
};  
  
public ref struct T1 : public S, I {  
   virtual int f() new sealed = S::f;   // C3650  
   virtual int g() { return 0; }   // OK does not override S::g  
   virtual void a() new sealed = I::a {}   // OK  
};  
```