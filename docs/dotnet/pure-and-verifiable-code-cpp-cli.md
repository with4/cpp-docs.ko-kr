---
title: "순수형 및 안정형 코드 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /clr compiler option [C++], verifiable assemblies
- /clr compiler option [C++], mixed assemblies
- pure MSIL [C++]
- verifiable assemblies [C++]
- verifiably type-safe code [C++]
- /clr compiler option [C++], pure assemblies
- .NET Framework [C++], pure and verifiable code
- assemblies [C++], mixed code
- verifiable assemblies [C++], about verifiable assemblies
- mixed assemblies [C++], about mixed assemblies
- pure MSIL [C++], about pure code
- assemblies [C++], verifiable code
- mixed assemblies [C++]
- assemblies [C++], pure code
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
caps.latest.revision: "31"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7bcaabb9f0a696a5eb7b01c4bd78757681e4e6a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="pure-and-verifiable-code-ccli"></a>순수형 및 안정형 코드(C++/CLI)
Visual c + +.NET 프로그래밍에 대 한 세 가지 유형의 구성 요소 및 응용 프로그램 만들기를 지원: 혼합형, 순수형 및 안정형 합니다. 세 개는 모두를 통해 사용할 수는 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션입니다.  
  
## <a name="remarks"></a>설명  
 안정형 어셈블리에 대 한 자세한 내용은 다음을 참조 하세요.  
  
-   [혼합형, 순수형 및 안정형 기능 비교(C++/CLI)](../dotnet/mixed-pure-and-verifiable-feature-comparison-cpp-cli.md)  
  
-   [방법: /clr으로 마이그레이션: 순수 (C + + /cli CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [방법: 안정형 C++ 프로젝트 만들기(C++/CLI)](../dotnet/how-to-create-verifiable-cpp-projects-cpp-cli.md)  
  
-   [방법: /clr: safe로 마이그레이션 (C + + /cli CLI)](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)  
  
-   [SQL Server에 안정형 어셈블리 사용(C++/CLI)](../dotnet/using-verifiable-assemblies-with-sql-server-cpp-cli.md)  
  
-   [보안 모범 사례](../security/security-best-practices-for-cpp.md)  
  
-   [프로젝트를 혼합 모드에서 순수 IL로 변환](../dotnet/converting-projects-from-mixed-mode-to-pure-intermediate-language.md)  
  
## <a name="mixed-clr"></a>혼합 (/ clr)  
 혼합형 어셈블리 (컴파일된 **/clr**) 부분과 관리 되지 않는 모두 포함 하 여.NET 기능을 사용할 수 있도록 하는 관리 되는 부분이 하지만 여전히 관리 되지 않는 코드를 포함 합니다. 이렇게 하면 전체 프로젝트 다시 작성 하지 않고도.NET 기능을 사용 하도록 업데이트할 응용 프로그램 및 구성 합니다. Visual c + +를 사용 하 여 이러한 방식으로 관리 및 비관리 코드를 혼합 하는 c + + Interop 호출 됩니다. 자세한 내용은 참조 [혼합 (네이티브 / 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md) 및 [네이티브 및.NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)합니다.  
  
## <a name="pure-clrpure"></a>순수 (/ clr: pure)  
 순수형 어셈블리 (사용 하 여 컴파일된 **/clr: pure**) 네이티브 및 관리 되는 데이터 형식이 모두 포함 될 수 있지만 관리 되는 함수만 합니다. 순수형 어셈블리 혼합형된 어셈블리와 마찬가지로 P/Invoke를 통해 네이티브 Dll과 상호 허용 (참조 [(DllImport 특성)를 c + +에서 명시적 PInvoke를 사용 하 여](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md))을 하지만 c + + Interop 기능을 사용할 수 없는 합니다. 또한 순수 내보낼 수 없습니다 진입점 순수 어셈블리 사용에서 하기 때문에 네이티브 함수에서 호출할 수 있는 함수는 [__clrcall](../cpp/clrcall.md) 호출 규칙입니다.  
  
### <a name="advantages-of-clrpure"></a>/Clr의 장점: 순수  
  
-   향상 된 성능: 네이티브 함수를 순수 어셈블리만 MSIL에 포함 되어 있으므로 및 따라서 관리 되 는/관리 하는 전환이 없는 해야 합니다. (P/Invoke를 통해 만든 함수 호출이이 규칙의 예외입니다.)  
  
-   : AppDomain 인식 내부 존재 관리 되는 함수 및 CLR 데이터 형식 `Application Domains`의 표시 여부와 내게 필요한 옵션에 영향을 주는 합니다. 순수형 어셈블리는 도메인을 인식 (__declspec ([appdomain](../cpp/appdomain.md)) 인 각 형식에 대 한 것으로 간주) 쉽고 안전 하 게는 다른.NET 구성 요소에서 해당 형식 및 기능에 액세스 합니다. 결과적으로, 혼합 된 어셈블리 보다 다른.NET 구성 요소와 순수형 어셈블리 보다 쉽게 운용 합니다.  
  
-   비 디스크 로드: 메모리 내 모드와 스트리밍된 순수형 어셈블리를 로드할 수 있습니다. .NET 어셈블리를 사용 하 여 저장 프로시저로 필수적입니다. Windows에 대 한 종속성으로 인해 실행 하기 위해 디스크에 있어야 메커니즘을 로드 하는 혼합 된 어셈블리를이 점에서 차이가 있습니다.  
  
-   리플렉션: 수 없으면 혼합 된 실행 파일에 대 한 리플렉션을 순수형 어셈블리 전체 리플렉션 지원을 제공 합니다. 자세한 내용은 참조 [리플렉션 (C + + /cli CLI)](../dotnet/reflection-cpp-cli.md)합니다.  
  
-   호스트 Controllability: 순수 어셈블리만 MSIL에 포함 되어 있으므로 동작 하므로 더 예측 가능 하 고 CLR 응용 프로그램에서 해당 호스트를 사용할 경우에 어셈블리를 혼합 하 고 해당 기본 동작을 수정 하는 보다 유연 하 게 합니다.  
  
### <a name="limitations-of-clrpure"></a>/Clr 제한 사항: 순수  
 이 섹션에서는 현재 지원 하지 않는 기능 **/clr: pure**합니다.  
  
-   순수형 어셈블리는 관리 되지 않는 함수에서 호출할 수 없습니다. 따라서 순수형 어셈블리는 COM 인터페이스를 구현 하거나 네이티브 콜백을 노출할 수 없습니다. 순수형 어셈블리 __declspec (dllexport) 통해 함수를 내보낼 수 없습니다 또는 합니다. DEF 파일입니다. 또한으로 선언 된 함수는 \__clrcall 규칙을 통해 가져올 수 없는 \__declspec(dllimport) 합니다. 순수형 어셈블리에서 네이티브 모듈의 함수를 호출할 수 있지만 순수형 어셈블리 호출 가능한 네이티브 함수를 노출할 수 없으므로 순수 어셈블리의 기능을 노출 혼합된 어셈블리의 관리 되는 함수를 통해 수행 해야 합니다. 참조 [하는 방법: /clr으로 마이그레이션: 순수 (C + + /cli CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md) 자세한 정보에 대 한 합니다.  
  
-   ATL 및 MFC 라이브러리는 Visual c + +에서 컴파일 pure 모드에서 지원 되지 않습니다.  
  
-   순수한 .netmodule을 Visual C++ 링커에 대한 입력으로 수락하지 않습니다. 그러나 순수.obj 파일을 링커에 의해 허용 되 고.obj 파일 netmodule에 포함 된 정보의 상위 집합에 포함. 참조 [링커 입력 파일로.netmodule 파일](../build/reference/netmodule-files-as-linker-input.md) 자세한 정보에 대 한 합니다.  
  
-   컴파일러 COM 지원 (#import)을 순수형 어셈블리에 관리 되지 않는 지침을 도입한 것이 지원 되지 않습니다.  
  
-   부동 소수점 맞춤 및 예외 처리에 대 한 옵션은 순수 어셈블리에 대 한 조정할 수 없습니다. 결과적으로, __declspec (align)는 사용할 수 없습니다. 그러면 렌더링 fpieee.h, 같은 일부 헤더 파일 /clr와 호환 되지 않는: 순수 합니다.  
  
-   로 컴파일할 때 PSDK에 GetLastError 함수 정의 되지 않은 동작을 제공할 수 **/clr: pure**합니다.  
  
## <a name="verifiable-clrsafe"></a>안정형 (/: safe)  
 **/clr: safe** Visual Basic 및 C#의 경우 공용 언어 런타임 (CLR) 코드 위반 하지 않도록을 현재 사용할 수 있는 요구 사항을 충족 하면서로 작성 된 것과 같은 안정형 어셈블리를 생성 하는 컴파일러 옵션 보안 설정입니다. 예를 들어 디스크에 쓰이지 않도록에서 구성 요소를 금지 하는 보안 설정, CLR 확인할 수 있는 구성 요소는 코드를 실행 하기 전에이 조건을 충족 하는지 확인할 수 있습니다. 안정형 어셈블리에 대 한 CRT 지원은 없습니다. (CRT 지원은 C 런타임 라이브러리의 순수 MSIL 버전을 통해 순수 어셈블리에 사용할 수 있습니다.)  
  
 안정형 어셈블리 순수 및 혼합 어셈블리 비해 이러한 이점을 제공합니다.  
  
-   보안이 강화 됩니다.  
  
-   일부 경우 것 (SQL 구성 요소, 예:) 필요합니다.  
  
-   이후 버전의 Windows 구성 요소 및 응용 프로그램을 확인할 수 있으려면 점점 더 걸립니다.  
  
 한 가지 단점은 c + + interop 기능은 지원 되지 않습니다. 안정형 어셈블리는 관리 코드에서 참조 되지 않는 경우에 관리 되지 않는 함수 또는 네이티브 데이터 형식을 포함할 수 없습니다.  
  
 단어 "안전한"이 사용 되지만 응용 프로그램을 컴파일하 **/clr: safe** 의미 하지는 않습니다 버그가 없습니다; 단지 CLR 런타임 시 보안 설정을 확인할 수 있음을 뜻합니다.  
  
 어셈블리 종류에 관계 없이 P/Invoke를 통해 네이티브 Dll로 관리 되는 어셈블리에서 호출은 컴파일되지만 보안 설정에 따라 런타임에 실패할 수 있습니다.  
  
> [!NOTE]
>  코드 작성 시나리오 컴파일러 성공 하지만 확인할 수 없는 어셈블리에 발생 하는: 범위 확인 연산자를 사용 하 여 개체 인스턴스를 통해 가상 함수를 호출 합니다.  예: `MyObj -> A::VirtualFunction();`  
  
## <a name="see-also"></a>참고 항목  
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)