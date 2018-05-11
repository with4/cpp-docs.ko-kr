---
title: 클래스 및 구조체 (c + + 구성 요소 확장명) | Microsoft Docs
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
ms.openlocfilehash: 9863786e5e017b69217f984e3aa6d1db597e74d3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="classes-and-structs--c-component-extensions"></a>클래스 및 구조체(C++ 구성 요소 확장)
클래스 또는 구조체 선언 인 *개체 수명* 자동으로 관리 됩니다. 개체가 더 이상 액세스 불가능하게 되거나 범위를 벗어나면 Visual C++가 개체에 할당된 메모리를 자동 삭제합니다.  
  
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
 어셈블리 외부 클래스 또는 구조체의 접근성입니다. 가능한 값은 **공용** 및 `private` (`private` 기본값임). 중첩 된 클래스 또는 구조체를 사용할 수 없습니다는 *class_access* 지정자입니다.  
  
 *name*  
 클래스 또는 구조체의 이름입니다.  
  
 *한정자* (선택 사항)  
 [추상](../windows/abstract-cpp-component-extensions.md) 및 [봉인](../windows/sealed-cpp-component-extensions.md) 가 유효한 한정자입니다.  
  
 *inherit_access* (선택 사항)  
 `base_type`의 접근성입니다. 허용되는 접근성은 `public`뿐입니다(기본값은 `public`).  
  
 *base_type* (선택 사항)  
 기본 형식입니다. 그러나 값 형식은 기본 형식으로 작동할 수 없습니다.  
  
 자세한 내용은 Windows 런타임 및 공용 언어 Runtimesections에이 매개 변수의 언어별 설명을 참조 하십시오.  
  
 **주의**  
  
 으로 선언 된 개체의 기본 멤버 접근성 **ref 클래스** 또는 **값 클래스** 은 `private`합니다. 사용 하 여 선언 된 개체의 기본 멤버 접근성 **ref 구조체** 또는 **값 구조체** 은 `public`합니다.  
  
 참조 형식이 다른 참조 형식에서 상속 하는 경우 기본 클래스의 가상 함수 명시적 재정의 해야 합니다 (으로 [재정의](../windows/override-cpp-component-extensions.md)) 또는 숨겨진 (으로 [new (의 new 슬롯 vtable)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)) 합니다. 파생 클래스 함수 또한 `virtual` 명시적으로 표시해야 합니다.  
  
 형식이 있는지 여부를 컴파일 타임에 감지 하려면는 `ref class` 또는 `ref struct`, 또는 `value class` 또는 `value struct`를 사용 하 여 `__is_ref_class (type)`, `__is_value_class (type)`, 또는 `__is_simple_value_class (type)`합니다. 자세한 내용은 참조 [형식 특성에 대 한 컴파일러 지원](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)합니다.  
  
 클래스 및 구조체에 대한 자세한 내용은 다음을 참조하세요.  
  
-   [클래스 및 구조체 인스턴스화](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)  
  
 
  
-   [참조 형식에 대한 C++ 스택 의미 체계](../dotnet/cpp-stack-semantics-for-reference-types.md)  
  
-   [클래스, 구조체 및 공용 구조체](../cpp/classes-and-structs-cpp.md)  
  
-   [소멸자 및 종료자에서 하는 방법: 클래스 및 구조체 정의 및 사용 (C + + /cli CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)  
  
-   [사용자 정의 연산자(C++/CLI)](../dotnet/user-defined-operators-cpp-cli.md)  
  
-   [사용자 정의 변환(C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md)  
  
-   [방법: C#에서 사용하기 위해 네이티브 클래스 래핑](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)  
  
-   [제네릭 클래스(C++/CLI)](../windows/generic-classes-cpp-cli.md)  
  
## <a name="windows-runtime"></a>Windows 런타임  
 **주의**  
  
 참조 [Ref 클래스 및 구조체](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx) 및 [값 클래스 및 구조체](http://msdn.microsoft.com/library/windows/apps/hh699861.aspx)합니다.  
  
 **매개 변수**  
  
 *base_type* (선택 사항)  
 기본 형식입니다. `ref class` 또는 `ref struct`는 0개 이상의 인터페이스 및 0개 또는 한 개의 `ref` 형식에서 상속할 수 있습니다. `value class` 또는 `value struct`는 0개 이상의 인터페이스에서만 상속할 수 있습니다.  
  
 `ref class` 또는 `ref struct` 키워드를 사용하여 개체를 선언하면 개체 핸들, 즉 개체에 대한 참조 카운터 포인터가 이 개체에 액세스합니다. 선언된 변수가 범위를 벗어나면 컴파일러가 자동으로 내부 개체를 삭제합니다. 개체가 호출에서 매개 변수로 사용되거나 변수에 저장되면 개체 핸들이 실제로 전달되거나 저장됩니다.  
  
 `value class` 또는 `value struct` 키워드를 사용하여 개체를 선언하면 선언된 개체의 개체 수명이 감독되지 않습니다. 개체는 다른 표준 C++ 클래스 또는 구조체와 같습니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 **주의**  
  
 에 표시 된 구문에서 이러한 차이점을 나열 하는 다음 표에 **모든 런타임** 섹션 관련이 있는 C + + /cli CLI 합니다.  
  
 **매개 변수**  
  
 *base_type* (선택 사항)  
 기본 형식입니다. `ref class` 또는 `ref struct`는 0개 이상의 관리되는 인터페이스 및 0개 또는 한 개의 ref 형식에서 상속할 수 있습니다. `value class` 또는 `value struct`는 0개 이상의 관리되는 인터페이스에서만 상속할 수 있습니다.  
  
 `ref class` 및 `ref struct` 키워드는 클래스 또는 구조체를 힙에 할당하도록 컴파일러에 지시합니다. 개체가 호출에서 매개 변수로 사용되거나 변수에 저장되면 개체 참조가 실제로 전달되거나 저장됩니다.  
  
 `value class` 및 `value struct` 키워드는 컴파일러가 할당 된 클래스 또는 구조체의 값 함수에 전달 되었거나 멤버에 저장 합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)