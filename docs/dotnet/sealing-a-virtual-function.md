---
title: "가상 함수 봉인 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- sealed keyword [C++]
- derived classes, virtual functions
- virtual functions, sealing
- __sealed keyword
ms.assetid: 0e9fae03-6425-4512-9a24-8ccb6dc8a0d4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 500e5b5e6014b7141c000a4e453341ceb5e822d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="sealing-a-virtual-function"></a>가상 함수 봉인
가상 함수 봉인 하는 구문은 Visual c + + Managed Extensions for c + + 변경 되었습니다.  
  
 `__sealed` 키워드 중 하나는 참조 형식에서 파생 되지 않도록 수정 하는 Managed extensions에서 사용 됩니다 (참조 [관리 되는 클래스 형식 선언의](../dotnet/declaration-of-a-managed-class-type.md)), 또는 가상 함수를 수정 하려면 허용 안 함 이후의 메서드의 파생된 클래스에서 재정의 합니다. 예:  
  
```  
__gc class base { public: virtual void f(); };  
__gc class derived : public base {  
public:  
   __sealed void f();  
};  
```  
  
 이 예제에서는 `derived::f()` 재정의 `base::f()` 인스턴스는 정확히 일치 하는 함수 프로토타입 기반으로 합니다. `__sealed` 키워드는 파생된 클래스에서 상속 되며, 후속 클래스의 재정의 제공할 수 없는 나타냅니다 `derived::f()`합니다.  
  
 새 구문에서 `sealed` 아무 위치에 실제 함수 프로토타입 전에 허용 되었던을 허용 하기 보다는 서명을 뒤에 배치 됩니다. 또한 사용 `sealed` 을 명시적으로 사용 해야는 `virtual` 키워드에도 합니다. 즉, 올바르게 변환 하면 `derived`, 위는 다음과 같습니다.  
  
```  
ref class derived: public base {  
public:  
   virtual void f() override sealed;  
};  
```  
  
 없는 경우는 `virtual` 키워드가이 인스턴스를 실행 하면 오류가 발생 합니다. 새 구문 컨텍스트 키워드 `abstract` 대신 사용할 수는 `=0` 순수 가상 함수를 지정할 수 있습니다. Managed Extensions 내에서 지원 되지 않았습니다. 예:  
  
```  
__gc class base { public: virtual void f()=0; };  
```  
  
 으로 다시 작성할 수 있습니다.  
  
```  
ref class base { public: virtual void f() abstract; };  
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언 (C + + /cli CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)