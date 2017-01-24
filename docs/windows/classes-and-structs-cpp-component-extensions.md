---
title: "Classes and Structs  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "public"
  - "ref struct"
  - "value_CPP"
  - "ref class"
  - "value struct"
  - "ref struct_cpp"
  - "ref class_cpp"
  - "value class_cpp"
  - "value struct_cpp"
  - "value class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ref class keyword [C++]"
  - "value class keyword [C++]"
  - "value struct keyword [C++]"
  - "ref struct keyword [C++]"
ms.assetid: 5c360764-b229-49c6-9357-66213afbc372
caps.latest.revision: 32
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes and Structs  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*개체 수명*이 자동 관리되는 클래스나 구조체를 선언합니다.  개체가 더 이상 액세스 불가능하게 되거나 범위를 벗어나면 Visual C\+\+가 개체에 할당된 메모리를 자동 삭제합니다.  
  
## 모든 런타임  
 **구문**  
  
```  
  
          class_access ref class    name modifier :  inherit_access base_type {};  
class_access ref struct   name modifier :  inherit_access base_type {};  
class_access value class  name modifier :  inherit_access base_type {};  
class_access value struct name modifier :  inherit_access base_type {};  
  
```  
  
 **매개 변수**  
  
 *class\_access*\(선택 사항\)  
 어셈블리 외부 클래스 또는 구조체의 접근성입니다.  가능한 값은 **public** 및 `private`입니다\(기본값은 `private`\).  중첩된 클래스 또는 구조체에는 *class\_access* 지정자가 있을 수 없습니다.  
  
 *name*  
 클래스 또는 구조체의 이름입니다.  
  
 *modifier*\(선택 사항\)  
 [abstract](../windows/abstract-cpp-component-extensions.md) 및 [sealed](../windows/sealed-cpp-component-extensions.md)가 유효한 한정자입니다.  
  
 *inherit\_access*\(선택 사항\)  
 `base_type`의 접근성입니다.  허용되는 접근성은 `public`뿐입니다\(기본값은 `public`\).  
  
 *base\_type*\(선택 사항\)  
 기본 형식입니다.  그러나 값 형식은 기본 형식으로 작동할 수 없습니다.  
  
 자세한 내용은 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 및 [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)] 섹션에서 이 매개 변수에 대한 언어별 설명을 참조하세요.  
  
 **설명**  
  
 **ref 클래스** 또는 **값 클래스**를 사용하여 선언된 개체의 기본 멤버 접근성은 `private`입니다.  또한 **ref 구조체** 또는 **값 구조체**를 사용하여 선언된 개체의 기본 멤버 접근성은 `public`입니다.  
  
 참조 형식이 다른 참조 형식에서 상속되는 경우 기본 클래스의 가상 함수는 [override](../windows/override-cpp-component-extensions.md)를 사용하여 명시적으로 재정의하거나 [new \(new slot in vtable\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)를 사용하여 숨겨야 합니다.  파생 클래스 함수 또한 `virtual` 명시적으로 표시해야 합니다.  
  
 형식이 `ref class` 또는 `ref struct`인지, 아니면 `value class` 또는 `value struct`인지 여부를 컴파일 타임에 감지하려면 `__is_ref_class (``type``)`, `__is_value_class (``type``)` 또는 `__is_simple_value_class (``type``)`를 사용합니다.  자세한 내용은 [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)을 참조하세요.  
  
 클래스 및 구조체에 대한 자세한 내용은 다음을 참조하세요.  
  
-   [클래스 및 구조체 인스턴스화](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)  
  
-   [값 형식 및 참조 형식에서 this 포인터의 의미](../misc/semantics-of-the-this-pointer-in-value-and-reference-types.md)  
  
-   [참조 형식에 대한 C\+\+ 스택 의미 체계](../dotnet/cpp-stack-semantics-for-reference-types.md)  
  
-   [클래스, 구조체 및 공용 구조체](../cpp/classes-and-structs-cpp.md)  
  
-   [네이티브 클래스의 public 및 private](../misc/how-to-declare-public-and-private-on-native-classes.md)  
  
-   [암시적 추상 클래스](../misc/implicitly-abstract-classes.md)  
  
-   [클래스 또는 구조체에서 정적 생성자 정의](../misc/how-to-define-static-constructors-in-a-class-or-struct.md)  
  
-   [복사 생성자를 생성하지 못할 수 있습니다.](../misc/copy-constructor-may-not-be-generated.md)  
  
-   [참조 형식의 Hide\-by\-Signature 함수](../misc/hide-by-signature-functions-in-reference-types.md)  
  
-   [Visual C\+\+의 소멸자 및 종료자](../misc/destructors-and-finalizers-in-visual-cpp.md)  
  
-   [형식 멤버 표시 유형](../misc/type-and-member-visibility.md)  
  
-   [사용자 정의 연산자](../dotnet/user-defined-operators-cpp-cli.md)  
  
-   [사용자 정의 변환](../dotnet/user-defined-conversions-cpp-cli.md)  
  
-   [방법: C\#에서 사용하기 위해 네이티브 클래스 래핑](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)  
  
-   [Generic Classes \(C\+\+\/CLI\)](../windows/generic-classes-cpp-cli.md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **설명**  
  
 [Ref 클래스 및 구조체](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx) 및 [값 클래스 및 구조체](http://msdn.microsoft.com/library/windows/apps/hh699861.aspx)를 참조하세요.  
  
 **매개 변수**  
  
 *base\_type*\(선택 사항\)  
 기본 형식입니다.  `ref class` 또는 `ref struct`는 0개 이상의 인터페이스 및 0개 또는 한 개의 `ref` 형식에서 상속할 수 있습니다.  `value class` 또는 `value struct`는 0개 이상의 인터페이스에서만 상속할 수 있습니다.  
  
 `ref class` 또는 `ref struct` 키워드를 사용하여 개체를 선언하면 개체 핸들, 즉 개체에 대한 참조 카운터 포인터가 이 개체에 액세스합니다.  선언된 변수가 범위를 벗어나면 컴파일러가 자동으로 내부 개체를 삭제합니다.  개체가 호출에서 매개 변수로 사용되거나 변수에 저장되면 개체 핸들이 실제로 전달되거나 저장됩니다.  
  
 `value class` 또는 `value struct` 키워드를 사용하여 개체를 선언하면 선언된 개체의 개체 수명이 감독되지 않습니다.  개체는 다른 표준 C\+\+ 클래스 또는 구조체와 같습니다.  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **설명**  
  
 다음 표에는 C\+\+\/CLI에 특정한 **모든 런타임** 섹션에 표시되는 구문의 차이점이 나와 있습니다.  
  
 **매개 변수**  
  
 *base\_type*\(선택 사항\)  
 기본 형식입니다.  `ref class` 또는 `ref struct`는 0개 이상의 관리되는 인터페이스 및 0개 또는 한 개의 ref 형식에서 상속할 수 있습니다.  `value class` 또는 `value struct`는 0개 이상의 관리되는 인터페이스에서만 상속할 수 있습니다.  
  
 `ref class` 및 `ref struct` 키워드는 클래스 또는 구조체를 힙에 할당하도록 컴파일러에 지시합니다.  개체가 호출에서 매개 변수로 사용되거나 변수에 저장되면 개체 참조가 실제로 전달되거나 저장됩니다.  
  
 `value class` 및 `value struct` 키워드는 컴파일러에게 할당된 클래스 또는 구조체의 값이 함수에 전달되거나 멤버에 저장됨을 알려줍니다.  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)