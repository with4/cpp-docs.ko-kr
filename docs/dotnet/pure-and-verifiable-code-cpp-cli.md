---
title: "순수형 및 안정형 코드(C++/CLI) | Microsoft Docs"
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
  - ".NET Framework[C++], 순수형 및 안정형 코드"
  - "/clr 컴파일러 옵션[C++], 혼합형 어셈블리"
  - "/clr 컴파일러 옵션[C++], 순수형 어셈블리"
  - "/clr 컴파일러 옵션[C++], 안정형 어셈블리"
  - "어셈블리[C++], 혼합 코드"
  - "어셈블리[C++], 순수형 코드"
  - "어셈블리[C++], 안정형 코드"
  - "혼합형 어셈블리[C++]"
  - "혼합형 어셈블리[C++], 혼합형 어셈블리 정보"
  - "순수형 MSIL[C++]"
  - "순수형 MSIL[C++], about pure code"
  - "안정형 어셈블리[C++]"
  - "안정형 어셈블리[C++], about verifiable assemblies"
  - "안정형 형식 안전 코드[C++]"
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
caps.latest.revision: 31
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 순수형 및 안정형 코드(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.NET 프로그래밍과 관련하여 Visual C\+\+에서는 순수형, 혼합형 및 안정형이라는 세 가지 형식의 구성 요소 및 응용 프로그램 작성을 지원합니다.  이러한 세 가지 형식은 모두 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 통해 사용할 수 있습니다.  
  
## 설명  
 안정형 어셈블리에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [혼합형, 순수형 및 안정형 기능 비교](../dotnet/mixed-pure-and-verifiable-feature-comparison-cpp-cli.md)  
  
-   [방법: \/clr:pure로 마이그레이션](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [방법: 안정형 C\+\+ 프로젝트 만들기](../dotnet/how-to-create-verifiable-cpp-projects-cpp-cli.md)  
  
-   [방법: \/clr:safe로 마이그레이션](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)  
  
-   [SQL Server에 안정형 어셈블리 사용](../dotnet/using-verifiable-assemblies-with-sql-server-cpp-cli.md)  
  
-   [최선의 보안 구현 방법](../top/security-best-practices-for-cpp.md)  
  
-   [프로젝트를 혼합 모드에서 순수 IL로 변환](../dotnet/converting-projects-from-mixed-mode-to-pure-intermediate-language.md)  
  
## 혼합형\(\/clr\)  
 **\/clr**을 사용하여 컴파일되는 혼합형 어셈블리에는 관리되지 않는 부분과 관리되는 부분이 모두 포함되므로 .NET 기능을 사용할 수 있지만 여기에는 비관리 코드가 포함됩니다.  이 경우 전체 프로젝트를 다시 작성하지 않고도 .NET 기능을 사용하도록 응용 프로그램과 구성 요소를 업데이트할 수 있습니다.  이러한 방식으로 관리 코드와 비관리 코드를 혼합하도록 C\+\+를 사용하는 것을 Visual C\+\+ Interop이라고 합니다.  자세한 내용은 [혼합형\(네이티브 및 관리\) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md) 및 [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)를 참조하십시오.  
  
## 순수형\(\/clr:pure\)  
 **\/clr:pure**를 사용하여 컴파일되는 순수형 어셈블리에는 네이티브 데이터 형식과 관리되는 데이터 형식이 모두 포함될 수 있지만 함수는 관리되는 함수만 포함될 수 있습니다.  혼합형 어셈블리와 마찬가지로 순수형 어셈블리를 사용하면 P\/Invoke를 통해 네이티브 DLL과 상호 작용할 수 있지만\([C\+\+에서 명시적 PInvoke 사용\(DllImport 특성\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md) 참조\) C\+\+ Interop 기능은 사용할 수 없습니다.  또한 순수형 어셈블리의 진입점에서는 [\_\_clrcall](../cpp/clrcall.md) 호출 규칙을 사용하므로 네이티브 함수에서 호출할 수 있는 함수는 순수형 어셈블리에서 내보낼 수 없습니다.  
  
### \/clr:pure의 이점  
  
-   성능이 향상됩니다. 순수형 어셈블리에는 MSIL만 포함되고 네이티브 함수가 없으므로 관리\/비관리 전환이 필요하지 않습니다. P\/Invoke를 통한 함수 호출은 이 규칙의 예외입니다.  
  
-   AppDomain을 인식할 수 있습니다. 관리되는 함수와 CLR 데이터 형식은 그 표시 여부와 액세스 가능성에 영향을 주는 `Application Domains` 안에 저장됩니다.  순수형 어셈블리는 도메인을 인식합니다. 즉, 각 형식에 대해 \_\_declspec\([appdomain](../cpp/appdomain.md)\)이 암시적으로 적용됩니다. 따라서 다른 .NET 구성 요소에서 더 쉽고 더 안전하게 이러한 어셈블리의 형식과 기능에 액세스할 수 있습니다.  따라서 순수형 어셈블리를 사용하면 혼합형 어셈블리보다 더 쉽게 다른 .NET 구성 요소와 상호 작용할 수 있습니다.  
  
-   디스크를 사용하여 로드하지 않습니다. 순수형 어셈블리는 메모리에 로드할 수 있고 스트림할 수도 있습니다.  이는 .NET 어셈블리를 저장 프로시저로 사용하는 근본적인 이유입니다.  이는 Windows 로드 메커니즘에 종속되어 있기 때문에 실행을 위해서는 반드시 디스크에 있어야 하는 혼합형 어셈블리와 다른 점입니다.  
  
-   리플렉션이 가능합니다. 혼합 실행 파일에 대해서는 리플렉션할 수 없지만 순수형 어셈블리의 경우 전체 리플렉션이 지원됩니다.  자세한 내용은 [리플렉션](../dotnet/reflection-cpp-cli.md)을 참조하십시오.  
  
-   호스트를 제어할 수 있습니다. 순수형 어셈블리에는 MSIL만 포함되므로 CLR을 호스팅하고 그 기본 동작을 수정하는 응용 프로그램에서 사용하는 경우 혼합형 어셈블리보다 더 정확하게 예측 가능하고 융통성 있게 작동합니다.  
  
### \/clr:pure의 제한 사항  
 이 단원에서는 **\/clr:pure**가 현재 지원하지 않는 기능에 대해 설명합니다.  
  
-   순수형 어셈블리는 관리되지 않는 함수를 통해 호출할 수 없습니다.  따라서 순수형 어셈블리는 COM 인터페이스를 구현하거나 네이티브 콜백을 노출할 수 없습니다.  순수형 어셈블리는 \_\_declspec\(dllexport\) 또는 .DEF 파일을 통해 함수를 내보낼 수 없습니다.  또한 \_\_clrcall 규칙을 사용하여 선언한 함수는 \_\_declspec\(dllimport\)을 통해 가져올 수 없습니다.  네이티브 모듈의 함수는 순수형 어셈블리에서 호출할 수 있지만 순수형 어셈블리는 호출 가능한 네이티브 함수를 노출할 수 없으므로 순수형 어셈블리의 기능을 노출하려면 혼합형 어셈블리의 관리되는 함수를 사용해야 합니다.  자세한 내용은 [방법: \/clr:pure로 마이그레이션](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)를 참조하십시오.  
  
-   Visual C\+\+의 순수 모드 컴파일에서는 ATL 및 MFC 라이브러리를 지원하지 않습니다.  
  
-   순수한 .netmodule은 Visual C\+\+ 링커의 입력으로 사용할 수 없습니다.  그러나 순수 .obj 파일은 링커에 사용할 수 있으며 .obj 파일에는 netmodule에 들어 있는 정보의 상위 집합이 포함됩니다.  자세한 내용은 [링커 입력 파일로 사용하는 .netmodule 파일](../build/reference/netmodule-files-as-linker-input.md)를 참조하십시오.  
  
-   관리되지 않는 명령을 순수형 어셈블리에 가져오는 결과가 되므로 컴파일러 COM 지원\(\#import\)을 사용할 수 없습니다.  
  
-   순수형 어셈블리에 대해서는 할당 및 예외 처리를 위한 부동 소수점 옵션을 조정할 수 없습니다.  따라서 \_\_declspec\(align\)을 사용할 수 없습니다.  이를 사용하면 \/clr:pure와 함께 사용할 수 없는 fpieee.h 같은 일부 헤더 파일이 렌더링됩니다.  
  
-   **\/clr:pure**를 사용하여 컴파일하는 경우 PSDK의 GetLastError 함수 동작이 정의되지 않습니다.  
  
## 안정형\(\/clr:safe\)  
 **\/clr:safe** 컴파일러 옵션을 사용하면 CLR\(공용 언어 런타임\)에서 코드가 현재 보안 설정을 위반하지 않도록 하는데 필요한 요구 사항을 충족하면서 Visual Basic 및 C\#에서 작성한 것과 같은 안정형 어셈블리를 생성할 수 있습니다.  예를 들어, 보안 설정에서 구성 요소가 디스크에 쓰지 못하도록 금지하고 있는 경우 CLR은 코드를 실행하기 전에 안정형 구성 요소가 이 조건을 충족하는지 확인할 수 있습니다.  안정형 어셈블리에 대해서는 CRT가 지원되지 않습니다. CRT는 C 런타임 라이브러리의 순수 MSIL 버전을 통해 순수형 어셈블리에 사용할 수 있습니다.  
  
 안정형 어셈블리를 사용하면 순수형 어셈블리나 혼합형 어셈블리에 비해 다음과 같은 이점이 있습니다.  
  
-   보안이 강화됩니다.  
  
-   SQL 구성 요소 같은 일부 상황에서는 이를 반드시 필요로 합니다.  
  
-   Windows의 이후 버전에서는 안정형 구성 요소와 응용 프로그램을 더 많이 요구하게 될 것입니다.  
  
 안정형 어셈블리의 한 가지 단점은 C\+\+ Interop 기능을 사용할 수 없다는 데 있습니다.  안정형 어셈블리에는 관리 코드에서 참조하지 않는 경우라 해도 관리되지 않는 함수나 네이티브 데이터 형식이 전혀 포함될 수 없습니다.  
  
 "안정"이라는 표현을 사용하고는 있지만 **\/clr:safe**를 사용하여 응용 프로그램을 컴파일한다고 해서 버그가 전혀 발생하지 않는다는 의미는 아닙니다. 이 표현은 단지 CLR이 런타임에 보안 설정을 확인할 수 있음을 뜻합니다.  
  
 어셈블리 형식과 상관없이 관리되는 어셈블리에서 P\/Invoke를 통해 네이티브 DLL로 호출하면 컴파일은 가능하지만 보안 설정에 따라서는 런타임에 오류가 발생할 수 있습니다.  
  
> [!NOTE]
>  범위 확인 연산자를 사용하여 개체 인스턴스를 통해 가상 함수를 호출하는 코드 작성 시나리오에서는 컴파일러 작업이 성공하지만 이 경우 비안정형 어셈블리가 생성됩니다.  예: `MyObj -> A::VirtualFunction();`  
  
## 참고 항목  
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)