---
title: "__super | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__super_cpp"
  - "__super"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__super 키워드[C++]"
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __super
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 재정의하는 함수에 대한 기본 클래스 구현을 호출하고 있음을 명시적으로 나타낼 수 있도록 합니다.  
  
## 구문  
  
```  
  
__super::  
member_function  
();  
  
```  
  
## 설명  
 액세스할 수 있는 모든 기본 클래스 메서드가 오버로드 확인 단계에서 고려되고 가장 일치하는 함수가 호출되는 함수입니다.  
  
 `__super`는 멤버 함수의 본문 내에서만 나타날 수 있습니다.  
  
 `__super`는 using 선언과 함께 사용할 수 없습니다.  자세한 내용은 [선언 사용](../cpp/using-declaration.md)을 참조하십시오.  
  
 코드를 삽입하는 [특성](../windows/cpp-attributes-reference.md)이 도입되면서 이름을 모를 수도 있지만 호출하려는 메서드를 포함하는 하나 이상의 기본 클래스가 코드에 포함될 수도 있습니다.  
  
## 예제  
  
```  
// deriv_super.cpp  
// compile with: /c  
struct B1 {  
   void mf(int) {}  
};  
  
struct B2 {  
   void mf(short) {}  
  
   void mf(char) {}  
};  
  
struct D : B1, B2 {  
   void mf(short) {  
      __super::mf(1);   // Calls B1::mf(int)  
      __super::mf('s');   // Calls B2::mf(char)  
   }  
};  
```  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)