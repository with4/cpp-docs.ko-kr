---
title: "인터페이스 멤버 명시적 재정의 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "가상 함수 명시적 재정의"
  - "함수[C++], 재정의"
  - "인터페이스 멤버, 명시적 재정의"
  - "함수 재정의"
  - "가상 함수, 명시적 재정의"
ms.assetid: 46f1f536-bf43-4311-9a17-ff2282e528a9
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 인터페이스 멤버 명시적 재정의
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 클래스 내의 인터페이스 멤버에 대한 명시적 재정의를 선언하는 구문이 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 인터페이스를 구현하는 클래스 내에서 인터페이스 멤버의 인스턴스를 두 개 제공해야 하는 경우가 많습니다. 그 중 하나는 인터페이스 핸들을 통해 클래스 개체를 조작할 때 사용되고, 다른 하나는 클래스 인터페이스를 통해 클래스 개체를 사용할 때 사용됩니다.  예를 들면 다음과 같습니다.  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 Managed Extensions의 경우 인터페이스 이름을 사용하여 정규화된 메서드 이름으로 인터페이스 메서드를 명시적으로 선언하여 이를 수행합니다.  클래스 고유 인스턴스는 정규화되지 않습니다.  이렇게 하면 이 예제의 경우 `R`의 인스턴스를 통해 명시적으로 호출할 때 `Clone`의 반환 값을 다운캐스팅할 필요가 없습니다.  
  
 새 구문에는 Managed Extensions 구문을 대신하여 일반적인 재정의 메커니즘이 도입되었습니다.  새 구문에서는 위 예제를 다음과 같이 작성할 수 있습니다.  
  
```  
public ref class R : public ICloneable {  
public:  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R  
   virtual R^ Clone();  
};  
```  
  
 이 경우 명시적으로 재정의되는 인터페이스 멤버는 클래스 내에서 고유한 이름을 가져야 합니다.  이 예제에서는 `InterfaceClone`이라는 이름을 지정했습니다.  두 경우 모두 동작은 동일합니다. `ICloneable` 인터페이스를 통한 호출에서는 `InterfaceClone`으로 이름이 바뀐 멤버가 호출되고 `R` 형식의 개체를 통한 호출에서는 두 번째 `Clone` 인스턴스가 호출됩니다.  
  
## 참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언\(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Explicit Overrides](../windows/explicit-overrides-cpp-component-extensions.md)