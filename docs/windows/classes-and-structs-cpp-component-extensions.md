---
title: 클래스 및 구조체 (c + + 구성 요소 확장) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ref class keyword [C++]
- value class keyword [C++]
- value struct keyword [C++]
- ref struct keyword [C++]
ms.assetid: 5c360764-b229-49c6-9357-66213afbc372
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 22f8dc4dfc3268930c80caece85b06b9a1a25d58
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461025"
---
# <a name="classes-and-structs--c-component-extensions"></a>클래스 및 구조체(C++ 구성 요소 확장)
클래스 또는 구조체 선언입니다 *개체 수명* 자동으로 관리 됩니다. 개체가 더 이상 액세스 불가능하게 되거나 범위를 벗어나면 Visual C++가 개체에 할당된 메모리를 자동 삭제합니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 **구문**  
  
```  
      class_access  
      ref class  
      name  
      modifier :  inherit_accessbase_type {};  
class_accessref structnamemodifier :  inherit_accessbase_type {};  
class_accessvalue classnamemodifier :  inherit_accessbase_type {};  
class_accessvalue structnamemodifier :  inherit_accessbase_type {};  
  
```  
  
 **매개 변수**  
  
 *class_access* (선택 사항)  
 어셈블리 외부 클래스 또는 구조체의 접근성입니다. 가능한 값은 **공개** 하 고 **개인** (**개인** 기본값). 중첩 된 클래스 또는 구조체를 사용할 수 없습니다는 *class_access* 지정자입니다.  
  
 *name*  
 클래스 또는 구조체의 이름입니다.  
  
 *한정자* (선택 사항)  
 [추상](../windows/abstract-cpp-component-extensions.md) 하 고 [sealed](../windows/sealed-cpp-component-extensions.md) 가 유효한 한정자입니다.  
  
 *inherit_access* (선택 사항)  
 `base_type`의 접근성입니다. 유일한 허용 된 액세스 가능성은 **공개** (**공용** 기본값).  
  
 *base_type* (선택 사항)  
 기본 형식입니다. 그러나 값 형식은 기본 형식으로 작동할 수 없습니다.  
  
 자세한 내용은 특정 언어에 대 한 설명은 Windows 런타임 및 공용 언어 Runtimesections에서이 매개 변수를 참조 하세요.  
  
 **주의**  
  
 사용 하 여 선언 된 개체의 기본 멤버 접근성 **ref 클래스** 하거나 **값 클래스** 됩니다 **개인**합니다. 로 선언 된 개체의 기본 멤버 접근성 **ref 구조체** 또는 **값 구조체** 됩니다 **공개**합니다.  
  
 참조 형식이 다른 참조 형식에서 상속 하는 경우 기본 클래스의 가상 함수 명시적으로 재정의 해야 합니다 (사용 하 여 [재정의](../windows/override-cpp-component-extensions.md)) 숨겨지는 (사용 하 여 [new (의 new 슬롯 vtable)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)). 파생된 클래스 함수 또한 명시적으로 표시 되어야 합니다 **가상**합니다.  
  
 형식 인지 여부를 컴파일 타임에 검색 하는 **ref 클래스** 또는 **ref 구조체**, 또는 **값 클래스** 또는 **값 구조체**를 사용 하 여 `__is_ref_class (type)`, `__is_value_class (type)`, 또는 `__is_simple_value_class (type)`합니다. 자세한 내용은 [형식 특성에 대 한 컴파일러 지원](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)합니다.  
  
 클래스 및 구조체에 대한 자세한 내용은 다음을 참조하세요.  
  
-   [클래스 및 구조체 인스턴스화](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)  
  
-   [참조 형식에 대한 C++ 스택 의미 체계](../dotnet/cpp-stack-semantics-for-reference-types.md)  
  
-   [클래스, 구조체 및 공용 구조체](../cpp/classes-and-structs-cpp.md)  
  
-   [소멸자 및 종료자에서 방법: 클래스 및 구조체 정의 및 사용 (C + + /cli CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)  
  
-   [사용자 정의 연산자(C++/CLI)](../dotnet/user-defined-operators-cpp-cli.md)  
  
-   [사용자 정의 변환(C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md)  
  
-   [방법: C#에서 사용하기 위해 네이티브 클래스 래핑](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)  
  
-   [제네릭 클래스(C++/CLI)](../windows/generic-classes-cpp-cli.md)  
  
## <a name="windows-runtime"></a>Windows 런타임  
 **주의**  
  
 참조 [Ref 클래스 및 구조체](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx) 하 고 [값 클래스 및 구조체](http://msdn.microsoft.com/library/windows/apps/hh699861.aspx)합니다.  
  
 **매개 변수**  
  
 *base_type* (선택 사항)  
 기본 형식입니다. A **ref 클래스** 하거나 **ref 구조체** 0 개 이상의 인터페이스 및 0 개 또는 1에서 상속할 수 있습니다 `ref` 형식입니다. A **값 클래스** 하거나 **값 구조체** 0 개 이상의 인터페이스 에서만 상속할 수 있습니다.  
  
 사용 하 여 개체를 선언 하는 **ref 클래스** 또는 **ref 구조체** 키워드는 액세스 한 개체가 개체에 대 한 핸들, 즉 개체에 대 한 참조 카운터 포인터입니다. 선언된 변수가 범위를 벗어나면 컴파일러가 자동으로 내부 개체를 삭제합니다. 개체가 호출에서 매개 변수로 사용되거나 변수에 저장되면 개체 핸들이 실제로 전달되거나 저장됩니다.  
  
 사용 하 여 개체를 선언 하면 합니다 **값 클래스** 또는 **값 구조체** 키워드를 선언 된 개체의 개체 수명이 감독 되지 않습니다. 개체는 다른 표준 C++ 클래스 또는 구조체와 같습니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 **주의**  
  
 다음 표에 나오는 구문의 차이점이 합니다 **모든 런타임** 섹션 관련이 있는 C + + /cli CLI입니다.  
  
 **매개 변수**  
  
 *base_type* (선택 사항)  
 기본 형식입니다. A **ref 클래스** 하거나 **ref 구조체** 이상의 관리 인터페이스 및 0 개 또는 한 명의 ref 형식 또는 0에서 상속할 수 있습니다. A **값 클래스** 하거나 **값 구조체** 0 개 이상의 관리 되는 인터페이스 에서만 상속할 수 있습니다.  
  
 합니다 **ref 클래스** 하 고 **ref 구조체** 키워드는 컴파일러가 힙에 할당 되는 클래스 또는 구조체입니다. 개체가 호출에서 매개 변수로 사용되거나 변수에 저장되면 개체 참조가 실제로 전달되거나 저장됩니다.  
  
 합니다 **값 클래스** 하 고 **값 구조체** 키워드는 컴파일러가 할당 된 클래스 또는 구조체의 값 함수에 전달 되었거나 멤버에 저장 합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)