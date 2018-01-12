---
title: "방법:-clr로 마이그레이션: 순수 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /clr compiler option [C++], migrating to /clr:pure
- migration [C++], pure MSIL
- pure MSIL [C++], porting to
ms.assetid: 5ffb1184-2095-4ade-84aa-4fa6324bc764
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b8d49ee233167c02570408ba091c2a99b78487d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-migrate-to-clrpure-ccli"></a>방법: /clr:pure로 마이그레이션(C++/CLI)
이 항목에서는 사용 하 여 순수 MSIL로 마이그레이션할 때 발생할 수 있는 문제를 설명 **/clr: pure** (참조 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md) 자세한 정보에 대 한). 이 항목 가정 마이그레이션하려는 현재 사용 하 여 혼합 된 어셈블리는 **/clr** 으로 순수 MSIL에 비관리 코드에서의 마이그레이션 경로 직접 옵션입니다. 비관리 코드에 대 한 참조 [하는 방법: /clr으로 마이그레이션](../dotnet/how-to-migrate-to-clr.md) 순수 MSIL로 마이그레이션을 시작 하기 전에.  
  
## <a name="basic-changes"></a>기본 변경 사항  
 MSIL에 표현할 수 없는 함수를 포함 하는 코드는 컴파일되지 것입니다 되므로 순수 MSIL MSIL 명령을 구성 됩니다. 이외의 다른 호출 규칙을 사용 하 여 정의 된 함수가 여기에 [__clrcall](../cpp/clrcall.md)합니다. (__Clrcall 이외의 함수 수 순수 MSIL 구성 요소에서 호출 되는 있지만 정의 되지 않았습니다.)  
  
 런타임 오류 C4412 경고를 활성화 해야 합니다. C4412 추가 하 여 활성화할 `#pragma warning (default : 4412)` 를 사용 하 여 컴파일할 각 컴파일 대상 **/clr: 순수** IJW에서 c + + 형식을 전달 하 고 (**/clr)** 또는 네이티브 코드입니다. 참조 [컴파일러 경고 (수준 2) C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) 자세한 정보에 대 한 합니다.  
  
## <a name="architectural-considerations"></a>아키텍처 고려 사항  
 에 나열 된 순수 MSIL 어셈블리의 제한 사항 중 일부 [순수형 및 안정형 코드 (C + + /cli CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md) 는 응용 프로그램 설계 및 마이그레이션 전략에 대 한 높은 수준의 영향을 줍니다. 가장 주목할 만한 혼합형된 어셈블리와 달리 완벽 한 호환성 관리 되는 모듈을 순수 MSIL 어셈블리에 이용할 수 없습니다.  
  
 순수 MSIL 어셈블리는 관리 되지 않는 함수를 호출할 수 있지만 관리 되지 않는 함수를 호출할 수 없습니다. 결과적으로, 순수 MSIL은 관리 되지 않는 함수에서 사용 되는 서버 코드에 비해 관리 되지 않는 함수를 사용 하는 클라이언트 코드에 더 적합 합니다. 순수 MSIL 어셈블리에 포함 된 기능이 관리 되지 않는 함수에서 사용할 경우 인터페이스 계층으로 혼합 된 어셈블리를 사용 합니다.  
  
 ATL 또는 MFC를 사용 하는 응용 프로그램은 이러한 라이브러리는이 릴리스에서 지원 되지 않기 때문 순수 MSIL로의 마이그레이션 위한 적합 하지 않습니다. 마찬가지로,는 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)] 컴파일되지 않는 헤더 파일이 포함 되어 **/clr: pure**합니다.  
  
 순수 MSIL 어셈블리에서 관리 되지 않는 함수를 호출할 수는이 기능은 단순 C 스타일 함수에 제한 됩니다. 더 복잡 한 관리 되지 않는 Api 사용 해야 하는 COM 인터페이스 또는 순수 MSIL와 관리 되지 않는 구성 요소 간의 인터페이스로으로 사용할 수 있는 혼합된 어셈블리의 형식으로 노출 해야 하는 관리 되지 않는 기능입니다. 혼합형된 어셈블리 레이어를 사용 하는 유일한 방법은 예를 들어, 콜백 함수를 사용 하는 관리 되지 않는 함수를 순수 어셈블리는 콜백으로 사용 하기 위해 네이티브 호출 가능 함수를 제공할 수 있는 그대로 사용 하 합니다.  
  
## <a name="application-domains-and-calling-conventions"></a>응용 프로그램 도메인 및 호출 규칙  
 이 가능 하지만 순수 msil 어셈블리 사용 하 여 관리 되지 않는 기능, 함수 및 정적 데이터를 다르게 처리 됩니다. 순수형 어셈블리 함수 사용 하 여 구현 되는 [__clrcall](../cpp/clrcall.md) 저장된 응용 프로그램 도메인은 호출 규칙 및 정적 데이터입니다. 이 사용 하 여 관리 되지 않는 혼합 어셈블리에 대 한 기본값과에서 다른는 [__cdecl](../cpp/cdecl.md) 함수에 대 한 호출 규칙 및 각 프로세스 별로 정적 데이터를 저장 합니다.  
  
 순수 MSIL (및 /clr: safe로 컴파일된 안정형 코드)의 컨텍스트 내에서 이러한 기본값은 투명으로 [__clrcall](../cpp/clrcall.md) 는 CLR의 기본 호출 규칙 및 응용 프로그램 도메인은 정적 네이티브 범위 및 .NET 응용 프로그램의 글로벌 데이터입니다. 그러나 혼합 또는 관리 되지 않는 구성 요소와 상호 작용, 함수 및 글로벌 데이터의 서로 다른 처리 문제가 발생할 수 있습니다.  
  
 예를 들어 순수 MSIL 구성 관리 되지 않는 또는 혼합 DLL에서 함수를 호출 하는 것을 DLL에 대 한 헤더 파일 순수 어셈블리를 컴파일하는 데 사용 됩니다. 그러나 헤더에서 각 함수에 대 한 호출 규칙으로 명시적으로 지정 하지 않으면 이러한 모든 간주 되도록 [__clrcall](../cpp/clrcall.md)합니다. 이 나중에 런타임 오류를 일으킬 이러한 함수는 사용 하 여 구현 가능성이 [__cdecl](../cpp/cdecl.md) 규칙입니다. 로 관리 되지 않는 헤더 파일에서 함수를 명시적으로 표시할 수 있습니다 [__cdecl](../cpp/cdecl.md), 아래 전체 DLL 소스 코드를 컴파일해야 또는 **/clr: pure**합니다.  
  
 마찬가지로 함수 포인터는 가리키는 것으로 간주 됩니다 [__clrcall](../cpp/clrcall.md) 아래 함수 **/clr: pure** 컴파일입니다. 이러한 너무 명시적으로 주석을 달아야 올바른 호출 규칙입니다.  
  
 자세한 내용은 참조 [응용 프로그램 도메인 및 Visual c + +](../dotnet/application-domains-and-visual-cpp.md)합니다.  
  
## <a name="linking-limitations"></a>링크 제한  
 Visual c + + 링커 저장소 범위와 호출 규칙이 다르면 혼합형 및 순수형 OBJ 파일을 연결 하려면 시도 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [순수형 및 안정형 코드(C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)