---
title: "컴파일러 오류 C3764 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3764"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3764"
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3764
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'override\_function': 기본 클래스 메서드 'base\_class\_function'을\(를\) 재정의할 수 없습니다.  
  
 컴파일러에서 잘못된 형식의 재정의를 발견했습니다.  예를 들어, 기본 클래스 함수가 `virtual`이 아닙니다.  자세한 내용은 [override](../../windows/override-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3764 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3764.cpp  
// compile with: /clr /c  
public ref struct A {  
   void g(int);  
   virtual void h(int);  
};  
  
public ref struct B : A {  
   virtual void g(int) override {}   // C3764  
   virtual void h(int) override {}   // OK  
};  
```  
  
## 예제  
 C3764는 기본 클래스 메서드가 명시적 재정의인 동시에 명명된 재정의인 경우에도 발생할 수 있습니다.  다음 샘플에서는 C3764 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3764_b.cpp  
// compile with: /clr /c  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : public A {  
   virtual void Test() override {}  
   virtual void Test2() = A::Test {}   // C3764  
};  
```