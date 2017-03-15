---
title: "전용 가상 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "액세스 한정자[C++], 클래스 멤버"
  - "파생 클래스, 가상 함수"
  - "멤버 액세스[C++], 가상 멤버"
  - "가상 함수, private"
ms.assetid: 04448086-bf72-44be-9c1f-dfda1744949e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 전용 가상 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 파생 클래스에서 전용 가상 함수를 처리하는 방식이 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 Managed Extensions에서는 해당 액세스 수준에 제한을 받지 않고 파생 클래스 내에서 가상 함수를 재정의할 수 있었지만,  변경된 새 구문에서는 가상 함수가 자신이 액세스할 수 없는 기본 클래스 가상 함수는 재정의할 수 없습니다.  예를 들면 다음과 같습니다.  
  
```  
__gc class MyBaseClass {  
   // inaccessible to a derived class   
   virtual void g();  
};  
  
__gc class MyDerivedClass : public MyBaseClass {  
public:  
   // okay in Managed Extensions; g() overrides MyBaseClass::g()  
   // error in new syntax; cannot override: MyBaseClass::g() is inaccessible …  
   void g();  
};  
```  
  
 새 구문에서는 위와 같은 방식에 상응하는 기능이 없습니다.  가능한 방법은 기본 클래스 멤버를 액세스 가능하게, 즉 비전용 멤버로 만드는 것 뿐입니다.  상속된 메서드는 동일한 액세스 수준을 가질 필요가 없습니다.  이 예제에서 변화를 최소화하는 방법은 MyBaseClass 멤버를 `protected`로 만드는 것입니다.  이 경우 프로그램에서 MyBaseClass를 통한 메서드에의 일반적인 액세스는 여전히 금지됩니다.  
  
```  
ref class MyBaseClass {  
protected:  
   virtual void g();  
};  
  
ref class MyDerivedClass : MyBaseClass {  
public:  
   virtual void g() override;  
};  
```  
  
 새 구문에서는 기본 클래스에 명시적 `virtual` 키워드가 없으면 경고 메시지가 생성됩니다.  
  
## 참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언\(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [멤버 표시 유형](../misc/member-visibility.md)