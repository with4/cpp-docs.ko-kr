---
title: "인터페이스 멤버 명시적 재정의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, explicit overrides
- overriding functions
- interface members, explicit overrides
- functions [C++], overriding
- explicit override of virtual function
ms.assetid: 46f1f536-bf43-4311-9a17-ff2282e528a9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 85681b2e2aeeb6dbeb6ffdf511827fb1fc1cb029
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="explicit-override-of-an-interface-member"></a>인터페이스 멤버 명시적 재정의
선언 클래스 내에서 인터페이스 멤버 명시적 재정의 구문은 Visual c + + Managed Extensions for c + + 변경 되었습니다.  
  
 -클래스 개체 인터페이스 핸들을 통해 조작 때 사용 되는 클래스 인터페이스를 통해 클래스 개체를 사용 하는 경우 사용 되는 인터페이스를 구현 하는 클래스 내에서 인터페이스 멤버의 두 인스턴스를 제공 하고자 합니다. 예:  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 Managed extensions에서이를 위해 인터페이스 메서드의 명시적 선언을 인터페이스의 이름으로 한정 되는 메서드의 이름을 제공 합니다. 클래스 관련 인스턴스 정규화 하지 않습니다. 이렇게 하지 않아도 다운 캐스트의 반환 값 `Clone`,이 예제에서는 인스턴스를 통해 명시적으로 호출할 때 `R`합니다.  
  
 새 구문에서 일반적인 재정의 메커니즘을 도입 했습니다 Managed Extensions 구문을 대체 하는. 예제는 다음과 같이 작성할 수 합니다.  
  
```  
public ref class R : public ICloneable {  
public:  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R  
   virtual R^ Clone();  
};  
```  
  
 이 수정 해야 하는 인터페이스 멤버를 명시적으로 재정의 되는 클래스 내에서 고유한 이름을 지정 합니다. 여기서 이라는 이름을 제공한 `InterfaceClone`합니다. 동작은 동일한-호출을 통해는 `ICloneable` 인터페이스를 호출 하며 이름이 바뀐 `InterfaceClone`, 형식의 개체를 통해 호출 하는 동안 `R` 두 `Clone` 인스턴스.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언 (C + + /cli CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [명시적 재정](../windows/explicit-overrides-cpp-component-extensions.md)