---
title: "형식 시스템(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b67bee8a-b526-4872-969e-ef22724e88fe
caps.latest.revision: 28
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 28
---
# 형식 시스템(C++/CX)
[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 아키텍처를 사용하면 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)], Visual Basic, Visual C\# 및 JavaScript를 사용하여 Windows API에 직접 액세스하고 다른 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 앱 및 구성 요소와 상호 운용되는 앱 및 구성 요소를 작성할 수 있습니다. C\+\+로 작성된 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 앱은 CPU에서 직접 실행되는 네이티브 코드로 컴파일됩니다. C\# 또는 Visual Basic으로 작성된 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 앱은 MSIL\(Microsoft Intermediate Language\)로 컴파일되고 CLR\(공용 언어 런타임\)로 실행됩니다. JavaScript로 작성된 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 앱은 런타임 환경에서 실행됩니다.[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 운영 체제 구성 요소 자체는 C\+\+로 작성되고 네이티브 코드로 실행됩니다. 이 모든 구성 요소 및 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 앱은 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] ABI\(응용 프로그램 이진 인터페이스\)를 통해 직접 통신합니다.  
  
 최신 C\+\+ 관용구에서 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]에 대한 지원을 제공하기 위해 Microsoft는 [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]\([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\)를 만들었습니다.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]는 C\+\+ 앱 및 구성 요소가 ABI에서 다른 언어로 작성된 앱과 통신하도록 지원하는 기본 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식의 구현 및 기본 제공 기본 형식을 제공합니다. 모든 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식을 사용하거나, 다른 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 앱 및 구성 요소에서 사용할 수 있는 클래스, 구조체, 인터페이스 및 기타 사용자 정의 형식을 만들 수 있습니다. 또한 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]로 작성된[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 앱은 공용으로 액세스할 수 없는 경우 일반 C\+\+ 클래스 및 구조체를 사용할 수 있습니다.  
  
 C\+\+\/CX 언어 프로젝션 및 작동 방법에 대한 자세한 내용은 다음 블로그 게시물을 참조하세요.  
  
1.  [C \+ \+ \/CX 파트 0 \/ \[n\]: 소개](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
2.  [C \+ \+ \/CX 파트 0 \/ \[n\]: 소개](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
3.  [C \+ \+ \/CX 파트 2 \/ \[n\]: 모자를 쓰는 유형](http://blogs.msdn.com/b/vcblog/archive/2012/09/17/cxxcxpart02typesthatwearhats.aspx)  
  
4.  [C \+ \+ \/CX 파트 3 \/ \[n\]: 작성 중](http://blogs.msdn.com/b/vcblog/archive/2012/10/05/cxxcxpart03underconstruction.aspx)  
  
5.  [C \+ \+ \/CX 파트 4 \/ \[n\]: 정적 멤버 함수](http://blogs.msdn.com/b/vcblog/archive/2012/10/19/cxxcxpart04staticmemberfunctions.aspx)  
  
## Windows 메타데이터\(.winmd\) 파일  
 C\+\+로 작성된 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 앱을 컴파일할 경우 컴파일러는 네이티브 컴퓨터 코드에서 실행 파일을 생성하고 클래스, 구조체, 열거형, 인터페이스, 매개 변수화된 인터페이스 및 대리자를 포함하는 공용 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식에 대한 설명이 포함된 별도의 Windows 메타데이터\(.winmd\) 파일을 생성합니다. 메타데이터의 형식은 .NET Framework 어셈블리에 사용된 형식과 유사합니다.  C\+\+ 구성 요소에서 .winmd 파일은 메타데이터만 포함합니다. 실행 코드는 별도의 파일에 상주합니다. 이는 Windows에 포함된 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소에 적용됩니다. WinMD 파일 이름은 소스 코드의 루트 네임스페이스의 접두사와 일치하거나 그 접두사여야 합니다. .NET Framework 언어의 경우 .winmd 파일에는 .NET Framework 어셈블리와 마찬가지로 코드와 메타데이터가 둘 다 포함됩니다.  
  
 .winmd 파일의 메타데이터는 코드의 게시된 표면을 나타냅니다. 게시된 형식은 해당 앱이 작성된 언어에 관계없이 다른 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]에 표시됩니다. 따라서 메타데이터 또는 게시된 코드는 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식 시스템에 의해 지정된 형식만 포함할 수 있습니다. 일반 클래스, 배열, 템플릿 또는 STL 컨테이너와 같은 C\+\+에 특정한 언어 구문은 메타데이터에 게시할 수 없습니다. Javascript 또는 C\# 클라이언트 앱은 이러한 언어 구문으로 수행할 작업을 인식하지 못하기 때문입니다.  
  
 메타데이터에 형식이 표시되는지, 메서드가 표시되는지는 적용된 액세스 가능성 한정자에 따라 결정됩니다. 표시하려면 네임스페이스에 public으로 형식을 선언해야 합니다. public이 아닌 ref 클래스는 코드의 내부 도우미 형식으로 허용되고, 메타데이터에 표시되지는 않습니다. public ref 클래스의 경우에도 일부 멤버만 표시하면 됩니다. 다음 표에는 public ref 클래스의 C\+\+ 액세스 지정자와 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 메타데이터 표시 유형 간의 관계가 나와 있습니다.  
  
|||  
|-|-|  
|**메타데이터에 게시됨**|**메타데이터에 게시되지 않음**|  
|public|private|  
|protected|internal|  
|public protected|private protected|  
  
 **개체 브라우저**를 사용하여 .winmd 파일의 내용을 볼 수 있습니다. Windows에 포함된 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소는 Windows.winmd 파일에 있습니다. default.winmd 파일은 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]에 사용되는 기본 형식을 포함하고, platform.winmd는 Platform 네임스페이스의 추가 형식을 포함합니다. 기본적으로 이 세 .winmd 파일은 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 앱의 모든 C\+\+ 프로젝트에 포함됩니다.  
  
> [!TIP]
>  [Platform::Collections 네임스페이스](../cppcx/platform-collections-namespace.md)의 형식은 public이 아니므로 .winmd 파일에 표시되지 않습니다. 이는 `Windows::Foundation::Collections`에 정의된 인터페이스의 private C\+\+ 관련 구현입니다. JavaScript 또는 C\#으로 작성된 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 앱은 [Platform::Collections::Vector 클래스](../cppcx/platform-collections-vector-class.md)가 무엇인지 인식하지 못하지만 `Windows::Foundation::Collections::IVector`를 사용할 수는 있습니다.`Platform::Collections` 형식은 collection.h에 정의됩니다.  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]의 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 형식 시스템  
 다음 섹션에서는 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식 시스템의 주요 기능 및 이러한 기능이 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]에서 지원되는 방식에 대해 설명합니다.  
  
### 네임스페이스  
 모든 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식은 네임스페이스 내에 선언되어야 합니다. Windows API 자체는 네임스페이스로 구성됩니다. .winmd 파일은 루트 네임스페이스와 이름이 같아야 합니다. 예를 들어 이름이 A.B.C.MyClass인 클래스는 이름이 A.winmd, A.B.winmd 또는 A.B.C.winmd인 메타데이터 파일에 정의된 경우에만 인스턴스화될 수 있습니다. DLL의 이름은 .winmd 파일 이름과 일치하지 않아도 됩니다.  
  
 Windows API 자체는 네임스페이스로 구성된 효율적인 클래스 라이브러리로 다시 만들어졌습니다.  모든 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소는 Windows.\* 네임스페이스에 선언됩니다.  
  
 자세한 내용은 [네임스페이스 및 형식 표시 유형](../cppcx/namespaces-and-type-visibility-c-cx.md)을 참조하십시오.  
  
### 기본 형식  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]에서는 UInt8, Int16, UInt16, Int32, UInt32, Int64, UInt64, Single, Double, Char16, Boolean 및 String과 같은 기본 형식을 정의합니다.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]는 기본 네임스페이스에서 uint16, uint32, uint64, int16, int32, int64, float32, float64 및 char16의 기본 숫자 형식을 지원합니다. Boolean과 String은 둘 다 Platform 네임스페이스에 정의됩니다.  
  
 또한 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]는 `unsigned char`에서 지원되지 않고 공용 API에서 사용할 수 없는 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]과 동일한 uint8을 정의합니다.  
  
 기본 형식을 [Platform::IBox Interface](../cppcx/platform-ibox-interface.md) 인터페이스에서 래핑하여 nullable로 만들 수 있습니다. 자세한 내용은 [값 클래스 및 구조체](../cppcx/value-classes-and-structs-c-cx.md)을 참조하십시오.  
  
 기본 형식에 대한 자세한 내용은 [기본 형식](../cppcx/fundamental-types-c-cx.md)을 참조하십시오.  
  
### 문자열  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 문자열은 변경할 수 없는 16비트 유니코드 문자의 시퀀스입니다.[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 문자열은 `Platform::String^`으로 프로젝션됩니다. 이 클래스는 문자열 작성, 조작 및 `wchar_t` 간의 변환을 위한 메서드를 제공합니다.  
  
 자세한 내용은 [문자열](../cppcx/strings-c-cx.md)을 참조하십시오.  
  
### 배열  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]은 모든 형식의 1차원 배열을 지원합니다. 배열의 배열은 지원되지 않습니다.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]에서 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 배열은 [Platform::Array 클래스](../cppcx/platform-array-class.md)로 프로젝션됩니다.  
  
 자세한 내용은 [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)을 참조하십시오.  
  
### Ref 클래스 및 구조체  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 클래스는 참조에 의해 복사되므로 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]에서 ref 클래스 또는 ref 구조체로 프로젝션됩니다. ref 클래스 및 ref 구조체의 메모리 관리는 참조 횟수에 따라 투명하게 처리됩니다. 개체에 대한 마지막 참조가 범위를 벗어나면 해당 개체가 삭제됩니다. ref 클래스 또는 ref 구조체는 다음을 지원합니다.  
  
-   멤버 생성자, 메서드, 속성 및 이벤트를 포함할 수 있습니다. 이러한 멤버는 액세스 가능성이 public, private, protected 또는 internal일 수 있습니다.  
  
-   private 중첩 열거형, 구조체 또는 클래스 정의를 포함할 수 있습니다.  
  
-   기본 클래스에서 직접 상속될 수 있으며 원하는 수의 인터페이스를 구현할 수 있습니다. 모든 ref 클래스는 암시적으로 [Platform::Object 클래스](../cppcx/platform-object-class.md)로 변환될 수 있으며, [Object::ToString](../cppcx/object-tostring-method-c-cx.md)과 같은 가상 메서드를 재정의할 수 있습니다.  
  
 public 생성자가 있는 ref 클래스는 추가 파생을 방지하기 위해 sealed로 선언해야 합니다.  
  
 자세한 내용은 [Ref 클래스 및 구조체](../cppcx/ref-classes-and-structs-c-cx.md)을 참조하십시오.  
  
### 값 클래스 및 구조체  
 값 클래스 또는 값 구조체는 기본 데이터 구조를 나타내며 값 클래스, 값 구조체 또는 `Platform::String^` 형식일 수 있는 필드만 포함합니다.  값 구조체 및 값 클래스는 값으로 복사됩니다.  
  
 값 구조체를 IBox 인터페이스에서 래핑하여 nullable로 만들 수 있습니다.  
  
 자세한 내용은 [값 클래스 및 구조체](../cppcx/value-classes-and-structs-c-cx.md)을 참조하십시오.  
  
### partial 클래스  
 partial 클래스 기능을 사용하면 여러 파일에 대해 하나의 클래스를 정의할 수 있습니다. 이 클래스는 XAML 편집기와 같은 코드 생성 도구에서 사용자가 편집하는 파일을 건드리지 않고 하나의 파일을 수정할 수 있게 하는 데 주로 사용됩니다.  
  
 자세한 내용은 [partial 클래스](../cppcx/partial-classes-c-cx.md)을 참조하십시오.  
  
### 속성  
 속성은 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식의 public 데이터 멤버이며, get\/set 메서드 쌍으로 구현됩니다. 클라이언트 코드는 공용 필드인 것처럼 속성에 액세스합니다. 사용자 지정 get 또는 set 코드가 필요 없는 속성을 *trivial 속성*이라고 하며, 명시적인 get 또는 set 메서드 없이 선언할 수 있습니다.  
  
 자세한 내용은 [속성](../cppcx/properties-c-cx.md)을 참조하십시오.  
  
### [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]의 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 컬렉션  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]은 각 언어에서 자체적으로 구현하는 컬렉션 형식에 대한 인터페이스 집합을 정의합니다.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]는 [Platform::Collections::Vector 클래스](../cppcx/platform-collections-vector-class.md), [Platform::Collections::Map 클래스](../cppcx/platform-collections-map-class.md) 및 해당 STL\(표준 템플릿 라이브러리\)과 호환되는 그 밖의 관련 구체적 컬렉션 형식의 구현을 제공합니다.  
  
 자세한 내용은 [컬렉션](../cppcx/collections-c-cx.md)을 참조하십시오.  
  
### 템플릿 ref 클래스  
 private 및 internal ref 클래스는 템플릿으로 만들고 특수화할 수 있습니다.  
  
 자세한 내용은 [템플릿 ref 클래스](../cppcx/template-ref-classes-c-cx.md)을 참조하십시오.  
  
### 인터페이스  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 인터페이스는 ref 클래스 또는 ref 구조체가 인터페이스에서 상속된 경우에 구현해야 하는 공용 속성, 메서드 및 이벤트 집합을 정의합니다.  
  
 자세한 내용은 [인터페이스](../cppcx/interfaces-c-cx.md)을 참조하십시오.  
  
### 열거형  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]의 열거형 클래스는 C\+\+의 범위가 지정된 열거형과 유사합니다. 기본 형식은 int32입니다. 단, \[Flags\] 특성이 지정된 경우에는 기본 형식이 uint32입니다.  
  
 자세한 내용은 [열거형](../cppcx/enums-c-cx.md)을 참조하십시오.  
  
### 대리자  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]의 대리자는 C\+\+의 std::function 개체와 유사합니다. 호환되는 시그니처가 있는 클라이언트 제공 함수를 호출하는 데 사용되는 특별한 종류의 ref 클래스입니다.  대리자는 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]에서 주로 이벤트 형식으로 사용됩니다.  
  
 자세한 내용은 [대리자](../cppcx/delegates-c-cx.md)을 참조하십시오.  
  
### 예외  
 C\+\+\/CX에서는 사용자 지정 예외 형식, [std::exception](~/standard-library/exception-class.md) 형식 및 [Platform::Exception](../cppcx/platform-exception-class.md) 형식을 catch할 수 있습니다.  
  
 자세한 내용은 [예외](../cppcx/exceptions-c-cx.md)을 참조하십시오.  
  
### 이벤트  
 이벤트는 형식이 대리자 형식인 ref 클래스 또는 ref 구조체의 public 멤버입니다. 이벤트는 호출될 수만 있습니다. 즉, 소유 클래스에 의해서만 발생합니다. 그러나 클라이언트 코드는 소유 클래스가 이벤트를 발생시킨 경우에 호출되는 이벤트 처리기라는 고유 함수를 제공할 수 있습니다.  
  
 자세한 내용은 [이벤트](../cppcx/events-c-cx.md)을 참조하십시오.  
  
### 캐스팅  
 C\+\+\/CX에서는 표준 C\+\+ 캐스트 연산자인 [static\_cast](../cpp/static-cast-operator.md), [dynamic\_cast](../cpp/dynamic-cast-operator.md) 및 [reinterpret\_cast](../cpp/reinterpret-cast-operator.md)와 C\+\+\/CX에서만 사용되는 [safe\_cast](~/windows/safe-cast-cpp-component-extensions.md) 연산자도 지원됩니다.  
  
 자세한 내용은 [캐스팅](../cppcx/casting-c-cx.md)을 참조하십시오.  
  
### boxing  
 boxed 변수는 참조 의미 체계가 필요한 경우 참조 형식에 래핑되는 값 형식입니다.  
  
 자세한 내용은 [boxing](../cppcx/boxing-c-cx.md)을 참조하십시오.  
  
### 특성  
 특성은 모든 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식 또는 형식 멤버에 적용되고 런타임에 검사할 수 있는 메타데이터 값입니다.[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]은 `Windows::Foundation::Metadata` 네임스페이스의 공용 특성 집합을 정의합니다. 공용 인터페이스의 사용자 정의 특성은 이 릴리스의 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]에서 지원되지 않습니다.  
  
## API 사용 중단  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 시스템 형식에 사용되는 특성과 동일한 특성을 사용하여 공용 API를 사용하지 않도록 표시하는 방법을 설명합니다.  
  
 자세한 내용은 [형식 및 멤버가 사용되지 않도록 지정](../cppcx/deprecating-types-and-members-c-cx.md)을 참조하십시오.  
  
## 참고 항목  
 [Visual C\+\+ 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)