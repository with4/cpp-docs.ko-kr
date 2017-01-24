---
title: "컴파일러 오류 C2694 | Microsoft Docs"
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
  - "C2694"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2694"
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2694
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'override': 재정의 가상 함수에 지정된 예외가 기본 클래스 가상 멤버 함수 'base'보다 덜 제한적입니다.  
  
 가상 함수가 재정의되었지만 [\/Za](../../build/reference/za-ze-disable-language-extensions.md) 옵션이 지정된 경우에는 재정의 함수의 [예외 사양](../../cpp/exception-specifications-throw-cpp.md)이 제약을 덜 받습니다.  
  
 다음 샘플에서는 C2694 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2694.cpp  
// compile with: /Za /c  
class MyBase {  
public:  
   virtual void f(void) throw(int) {  
   }  
};  
  
class Derived : public MyBase {  
public:  
   void f(void) throw(...) {}   // C2694  
   void f2(void) throw(int) {}   // OK  
};  
```