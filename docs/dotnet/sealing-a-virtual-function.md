---
title: "가상 함수 봉인 | Microsoft Docs"
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
  - "__sealed 키워드"
  - "파생 클래스, 가상 함수"
  - "sealed 키워드[C++]"
  - "가상 함수, 봉인"
ms.assetid: 0e9fae03-6425-4512-9a24-8ccb6dc8a0d4
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 가상 함수 봉인
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 가상 함수를 봉인하는 구문이 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 Managed Extensions의 경우 참조 형식을 수정하고 여기서 더는 파생되지 않도록 하거나\([관리되는 클래스 형식 선언](../dotnet/declaration-of-a-managed-class-type.md) 참조\) 가상 함수를 수정하여 파생 클래스에서 메서드가 더는 재정의되지 않도록 하는 데 `__sealed` 키워드를 사용합니다.  예를 들면 다음과 같습니다.  
  
```  
__gc class base { public: virtual void f(); };  
__gc class derived : public base {  
public:  
   __sealed void f();  
};  
```  
  
 이 예제에서 `derived::f()`는 함수 프로토타입의 정확한 일치 항목을 기반으로 `base::f()` 인스턴스를 재정의합니다.  `__sealed` 키워드는 이후에 파생 클래스에서 상속되는 클래스로 `derived::f()`를 재정의할 수 없도록 지정합니다.  
  
 이전에는 실제 함수 프로토타입 앞의 아무 위치에나 사용할 수 있던 `sealed`가 새 구문에서는 시그니처 뒤에 배치됩니다.  또한 `sealed`를 사용하려면 `virtual` 키워드도 명시적으로 사용해야 합니다.  즉, 위 예제의 `derived`를 올바르게 변환하면 다음과 같습니다.  
  
```  
ref class derived: public base {  
public:  
   virtual void f() override sealed;  
};  
```  
  
 이 경우 `virtual` 키워드를 생략하면 오류가 발생합니다.  새 구문에서는 컨텍스트 키워드 `abstract`를 `=0` 대신 사용하여 순수 가상 함수를 지정할 수 있습니다.  Managed Extensions에서는 이러한 방식이 지원되지 않습니다.  예를 들면 다음과 같습니다.  
  
```  
__gc class base { public: virtual void f()=0; };  
```  
  
 이 코드는 다음과 같이 수정할 수 있습니다.  
  
```  
ref class base { public: virtual void f() abstract; };  
```  
  
## 참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언\(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)