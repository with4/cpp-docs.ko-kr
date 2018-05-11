---
title: 전용 가상 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, private
- derived classes, virtual functions
- access modifiers [C++], for class members
- member access [C++], virtual members
ms.assetid: 04448086-bf72-44be-9c1f-dfda1744949e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 97b4d7d9f47901fa69aa50bfc6f405355cf378b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="private-virtual-functions"></a>전용 가상 함수
개인 가상 함수가 파생된 클래스에서 처리 되는 방법은 Visual c + + Managed Extensions for c + + 변경 되었습니다.  
  
 Managed extensions에서 액세스 수준에는 가상 함수는 파생된 클래스에서 재정의 해야 하는 기능을 제한 하지 않습니다. 새 구문에서 가상 함수에 액세스할 수 없는 기본 클래스 가상 함수를 재정의할 수 없습니다. 예를 들어:  
  
```  
__gc class MyBaseClass {  
   // inaccessible to a derived class   
   virtual void g();  
};  
  
__gc class MyDerivedClass : public MyBaseClass {  
public:  
   // okay in Managed Extensions; g() overrides MyBaseClass::g()  
   // error in new syntax; cannot override: MyBaseClass::g() is inaccessible  
   void g();  
};  
```  
  
 새 구문에 대 한 디자인의 이러한 종류의 실제 매핑이 지원 되지 않습니다. 하나는 기본 클래스 멤버에 액세스할 수 있도록-즉, private이 아닌 단순히에 있습니다. 상속 된 메서드는 동일한 액세스 권한을 할 필요가 없습니다. 이 예제에서는 최소 침투 적으로 변경 되는 MyBaseClass 회원 `protected`합니다. 이러한 방식으로 MyBaseClass 통해 방법에 대 한 일반 프로그램의 액세스는 여전히 금지 됩니다.  
  
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
  
 명시적 없으면 `virtual` 키워드 새 구문에서 기본 클래스에는 경고 메시지를 생성 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언(C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 