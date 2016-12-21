---
title: "Component Extensions for Runtime Platforms | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "what's new [C++], keywords"
  - "what's new [C++], language features"
  - "Visual C++, keywords"
  - "keywords [C++]"
  - "Managed Extensions for C++, replacement syntax"
ms.assetid: 1e400ee6-3ac9-4910-a608-9d3d5993e423
caps.latest.revision: 77
caps.handback.revision: 77
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Component Extensions for Runtime Platforms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+에서는 런타임 플랫폼을 대상으로 프로그래밍할 수 있도록 언어 확장을 제공합니다.  [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)]\([!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)]\)을 사용하여 네이티브 코드로 컴파일되는 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱 및 구성 요소를 프로그래밍할 수 있습니다.  [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] COM 인터페이스를 대상으로 직접 프로그래밍하거나 [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)]를 사용하여 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱을 만들 수 있지만 생성자, 예외 및 기타 최신 C\+\+ 프로그래밍 관용구를 사용하여 작업할 수 있습니다.  .NET 플랫폼의 관리되는 실행 환경에서 C\+\+ 프로그래밍을 사용하도록 설정하려면 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)]를 사용할 수 있습니다.  
  
 **두 개의 런타임, 하나의 확장 집합**  
  
 [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)]는 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)]의 하위 집합입니다.  [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] 및 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)]에 공통으로 적용되는 확장의 경우 의미 체계가 CLR\(공용 언어 런타임\)을 대상으로 하는지 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]를 대상으로 하는지에 따라 달라집니다.  [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]에서 실행되려면 앱을 컴파일하려면 **\/ZW** 컴파일러 옵션을 지정합니다.  CLR에서 실행되도록 컴파일하려면 **\/clr** 컴파일러 옵션을 지정합니다.  이러한 스위치는 Visual Studio를 사용하여 프로젝트를 만들 때 자동으로 설정됩니다.  
  
 C\+\+에서 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱을 만드는 방법에 대한 자세한 내용은 [C\+\+로 작성한 Windows 런타임 앱용 로드맵](http://msdn.microsoft.com/library/windows/apps/hh700360.aspx)을 참조하세요.  
  
 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)]는  ISO\/ANSI C\+\+ 표준을 확장하며, Ecma [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] 표준에 따라 정의됩니다.  자세한 내용은 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)을 참조하세요.  
  
## 데이터 형식 키워드  
 언어 확장에는 *집계 키워드*가 포함됩니다. 이 키워드는 공백으로 구분되는 두 개의 토큰으로 구성됩니다.  토큰은 별도로 사용될 때의 의미와 함께 사용될 때의 의미가 있을 수 있습니다.  예를 들어 "ref"라는 단어는 일반 식별자이고 "class"라는 단어는 네이티브 클래스를 선언하는 키워드입니다.  그러나 이러한 단어가 결합되어 `ref class`를 구성하는 경우 결과 집계 키워드는 *런타임 클래스*라는 엔터티를 선언합니다.  
  
 확장에도 *상황에 맞는* 키워드입가 있습니다.  키워드는 해당 키워드를 포함하는 문의 종류 및 해당 문에서의 배치에 따라 상황에 맞는 것으로 처리됩니다.  예를 들어 토큰 "property"는 식별자이거나 특별한 종류의 public 클래스 멤버를 선언할 수 있습니다.  
  
 다음 표에는 C\+\+ 언어 확장의 키워드가 나열되어 있습니다.  
  
|키워드|상황에 맞는지 여부|용도|참조|  
|---------|----------------|--------|--------|  
|`ref class`<br /><br /> `ref struct`|아니요|클래스를 선언합니다.|[Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`value class`<br /><br /> `value struct`|아니요|값 클래스를 선언합니다.|[Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`interface class`<br /><br /> `interface struct`|아니요|인터페이스를 선언합니다.|[interface class](../windows/interface-class-cpp-component-extensions.md)|  
|`enum class`<br /><br /> `enum struct`|아니요|열거형을 선언합니다.|[enum class](../windows/enum-class-cpp-component-extensions.md)|  
|`property`|예|속성을 선언합니다.|[property](../windows/property-cpp-component-extensions.md)|  
|`delegate`|예|대리자를 선언합니다.|[delegate](../windows/delegate-cpp-component-extensions.md)|  
|`event`|예|이벤트를 선언합니다.|[event](../windows/event-cpp-component-extensions.md)|  
  
## Override 지정자  
 다음 키워드를 사용하여 파생의 재정의 동작을 정규화할 수 있습니다.  `new` 키워드는 C\+\+의 확장이 아니지만 추가 컨텍스트에서 사용할 수 있으므로 여기에 나열됩니다.  일부 지정자는 네이티브 프로그래밍에도 사용할 수 있습니다.  자세한 내용은 [방법: 네이티브 컴파일에 override 지정자 선언](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)을 참조하세요.  
  
|키워드|상황에 맞는지 여부|용도|참조|  
|---------|----------------|--------|--------|  
|`abstract`|예|함수 또는 클래스가 추상임을 나타냅니다.|[abstract](../windows/abstract-cpp-component-extensions.md)|  
|`new`|아니요|함수가 기본 클래스 버전의 재정의가 아님을 나타냅니다.|[new \(new slot in vtable\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)|  
|`override`|예|메서드가 기본 클래스 버전의 재정의이어야 함을 나타냅니다.|[override](../windows/override-cpp-component-extensions.md)|  
|`sealed`|예|클래스를 기본 클래스로 사용할 수 없도록 합니다.|[sealed](../windows/sealed-cpp-component-extensions.md)|  
  
## 제네릭에 대한 키워드  
 다음은 제네릭 형식을 지원하도록 추가된 키워드입니다.  자세한 내용은 [Generics](../windows/generics-cpp-component-extensions.md)을 참조하세요.  
  
|키워드|상황에 맞는지 여부|용도|  
|---------|----------------|--------|  
|`generic`|아니요|제네릭 형식을 선언합니다.|  
|`where`|예|제네릭 형식 매개 변수에 적용되는 제약 조건을 지정합니다.|  
  
## 기타 키워드  
 다음은 C\+\+ 확장에 추가된 키워드입니다.  
  
|키워드|상황에 맞는지 여부|용도|참조|  
|---------|----------------|--------|--------|  
|`finally`|예|기본 예외 처리 동작을 나타냅니다.|[Exception Handling](../windows/exception-handling-cpp-component-extensions.md)|  
|`for each, in`|아니요|컬렉션의 요소를 열거합니다.|[for each, in](../dotnet/for-each-in.md)|  
|`gcnew`|아니요|가비지 수집 힙에 형식을 할당합니다.  `new` 및 `delete` 대신 사용합니다.|[ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`ref new`|예|[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 형식을 할당합니다.  `new` 및 `delete` 대신 사용합니다.|[ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`initonly`|예|선언 또는 정적 생성자에서만 멤버를 초기화할 수 있음을 나타냅니다.|[initonly](../dotnet/initonly-cpp-cli.md)|  
|`literal`|예|리터럴 변수를 만듭니다.|[literal](../windows/literal-cpp-component-extensions.md)|  
|`nullptr`|아니요|핸들 또는 포인터가 개체를 가리키지 않음을 나타냅니다.|[nullptr](../windows/nullptr-cpp-component-extensions.md)|  
  
## 템플릿 구문  
 다음 언어 구문은 키워드 대신 템플릿으로 구현됩니다.  **\/ZW** 컴파일러 옵션을 지정하는 경우 `lang` 네임스페이스에 정의됩니다.  **\/clr** 컴파일러 옵션을 지정하는 경우 `cli` 네임스페이스에 정의됩니다.  
  
|키워드|용도|참조|  
|---------|--------|--------|  
|`array`|배열을 선언합니다.|[Arrays](../windows/arrays-cpp-component-extensions.md)|  
|`interior_ptr`|\(CLR에만 해당\) 참조 형식의 데이터를 가리킵니다.|[interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)|  
|`pin_ptr`|\(CLR에만 해당\) 가비지 수집 시스템을 일시적으로 표시하지 않도록 CLR 참조 형식을 가리킵니다.|[pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)|  
|`safe_cast`|런타임 형식에 대한 최적의 캐스팅 메서드를 확인하고 실행합니다.|[safe\_cast](../windows/safe-cast-cpp-component-extensions.md)|  
|`typeid`|\(CLR에만 해당\) 지정된 형식 또는 개체를 설명하는 <xref:System.Type?displayProperty=fullName>개체를 검색합니다.|[typeid](../windows/typeid-cpp-component-extensions.md)|  
  
## 선언자  
 다음 형식 선언자는 할당된 개체의 수명 및 삭제를 자동으로 관리하도록 런타임에 지시합니다.  
  
|연산자|용도|참조|  
|---------|--------|--------|  
|`^`|개체에 대한 핸들을 선언합니다. 즉, 더 이상 사용할 수 없는 경우 자동으로 삭제되는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 또는 CLR 개체에 대한 포인터를 선언합니다.|[개체 연산자에 대한 핸들\(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)|  
|`%`|추적 참조를 선언합니다. 즉, 더 이상 사용할 수 없는 경우 자동으로 삭제되는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 또는 CLR 개체에 대한 참조를 선언합니다.|[Tracking Reference Operator](../windows/tracking-reference-operator-cpp-component-extensions.md)|  
  
## 추가 구문 및 관련 항목  
 이 섹션에서는 추가 프로그래밍 구문 및 CLR과 관련된 항목을 나열합니다.  
  
|항목|설명|  
|--------|--------|  
|[\_\_identifier \(C\+\+\/CLI\)](../windows/identifier-cpp-cli.md)|\([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 및 CLR\) 키워드를 식별자로 사용할 수 있습니다.|  
|[Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)|\([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 및 CLR\) 함수에서 가변 개수의 인수를 사용하도록 합니다.|  
|[C\+\+ 네이티브 형식에 해당하는 .NET Framework](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)|C\+\+ 정수 계열 형식 대신 사용되는 CLR 유형을 나열합니다.|  
|[appdomain](../cpp/appdomain.md) `__declspec` 한정자|정적 및 전역 변수가 appdomain별로 존재하도록 지정하는 `__declspec` 한정자입니다.|  
|[C\-Style Casts with \/clr \(C\+\+\/CLI\)](../windows/c-style-casts-with-clr-cpp-cli.md)|C 스타일 캐스트가 해석되는 방법을 설명합니다.|  
|[\_\_clrcall](../cpp/clrcall.md) 호출 규칙|CLR 규격 호출 규칙을 나타냅니다.|  
|`__cplusplus_cli`|[미리 정의된 매크로](../preprocessor/predefined-macros.md)|  
|[Custom Attributes](../windows/custom-attributes-cpp.md)|사용자 고유의 CLR 특성을 정의하는 방법을 설명합니다.|  
|[Exception Handling](../windows/exception-handling-cpp-component-extensions.md)|예외 처리에 대한 개요를 제공합니다.|  
|[Explicit Overrides](../windows/explicit-overrides-cpp-component-extensions.md)|멤버 함수에서 임의 멤버를 재정의하는 방법을 보여 줍니다.|  
|[Friend 어셈블리\(C\+\+\)](../dotnet/friend-assemblies-cpp.md)|클라이언트 어셈블리에서 어셈블리 구성 요소의 모든 형식에 액세스할 수 있는 방법을 설명합니다.|  
|[Boxing](../windows/boxing-cpp-component-extensions.md)|값 형식이 boxing되는 조건을 보여 줍니다.|  
|[Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)|컴파일 시간에 형식의 특성을 검색하는 방법을 설명합니다.|  
|[관리되는, 관리되지 않는](../preprocessor/managed-unmanaged.md) pragma|관리되는 함수와 관리되지 않는 함수가 동일한 모듈에 공존하는 방법을 보여 줍니다.|  
|[프로세스](../cpp/process.md) `__declspec` 한정자|정적 및 전역 변수가 process별로 존재하도록 지정하는 `__declspec` 한정자입니다.|  
|[리플렉션](../dotnet/reflection-cpp-cli.md)|런타임 형식 정보의 CLR 버전을 보여 줍니다.|  
|[String](../windows/string-cpp-component-extensions.md)|<xref:System.String>로 문자열 리터럴의 컴파일러 변환을 설명합니다.|  
|[Type Forwarding \(C\+\+\/CLI\)](../windows/type-forwarding-cpp-cli.md)|클라이언트 코드를 다시 컴파일할 필요가 없도록 전달 어셈블리의 형식을 다른 어셈블리로 이동할 수 있습니다.|  
|[User\-Defined Attributes](../windows/user-defined-attributes-cpp-component-extensions.md)|사용자 정의 특성을 보여 줍니다.|  
|[\#using 지시문](../preprocessor/hash-using-directive-cpp.md)|외부 어셈블리를 가져옵니다.|  
|[XML 문서](../ide/xml-documentation-visual-cpp.md)|[\/doc\(문서 주석 처리\)](../build/reference/doc-process-documentation-comments-c-cpp.md)를 사용하여 XML 기반 코드 문서를 설명합니다.|  
  
## 참고 항목  
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)