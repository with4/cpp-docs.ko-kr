---
title: "방법: /clr:pure로 마이그레이션(C++/CLI) | Microsoft Docs"
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
  - "/clr 컴파일러 옵션[C++], /clr:pure로 마이그레이션"
  - "마이그레이션[C++], 순수형 MSIL"
  - "순수형 MSIL[C++], 포팅"
ms.assetid: 5ffb1184-2095-4ade-84aa-4fa6324bc764
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: /clr:pure로 마이그레이션(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 **\/clr:pure**를 사용하여 순수 MSIL로 마이그레이션할 때 발생할 수 있는 문제에 대해 설명합니다. 자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)를 참조하십시오.  이 항목에서는 마이그레이션하려는 코드가 현재 **\/clr** 옵션을 사용하여 혼합형 어셈블리로 컴파일되어 있는 것으로 가정합니다. 비관리 코드에서 순수 MSIL로 마이그레이션하는 과정은 중간 단계를 거쳐야 하기 때문입니다.  비관리 코드의 경우에는 순수 MSIL로 마이그레이션을 시작하기 전에 [방법: \/clr로 마이그레이션](../dotnet/how-to-migrate-to-clr.md)을 참조하십시오.  
  
## 기본 변경 사항  
 순수 MSIL은 MSIL 명령으로 이루어져 있으므로 MSIL로 표현할 수 없는 함수가 들어 있는 코드는 컴파일되지 않습니다.  여기에는 [\_\_clrcall](../cpp/clrcall.md) 이외의 호출 규칙을 사용하여 정의된 함수가 포함됩니다. 순수 MSIL 구성 요소에서는 \_\_clrcall 이외의 함수를 호출할 수 있지만 이를 정의할 수는 없습니다.  
  
 런타임 오류를 방지하기 위해서는 C4412 경고를 활성화해야 합니다.  C4412를 활성화하려면 **\/clr:pure**를 사용하여 컴파일하는 각 컴파일 대상과 IJW \(**\/clr\)** 또는 네이티브 코드 사이에 C\+\+ 형식을 전달하는 각 컴파일 대상에 `#pragma warning (default : 4412)`을 추가합니다.  자세한 내용은 [컴파일러 경고 \(수준 2\) C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md)를 참조하십시오.  
  
## 아키텍처 고려 사항  
 [순수형 및 안정형 코드](../dotnet/pure-and-verifiable-code-cpp-cli.md)에 나열되어 있는 순수 MSIL 어셈블리의 제한 사항 중 일부는 응용 프로그램 디자인 및 마이그레이션 전략에 있어 매우 중요한 의미를 갖습니다.  예를 들어, 혼합형 어셈블리와 달리 순수 MSIL 어셈블리는 관리되지 않는 모듈과 완벽하게 호환되지 않습니다.  
  
 순수 MSIL 어셈블리가 관리되지 않는 함수를 호출할 수는 있지만, 관리되지 않는 함수에서 순수 MSIL 어셈블리를 호출할 수는 없습니다.  따라서 순수 MSIL은 관리되지 않는 함수에 사용되는 서버 코드보다는 관리되지 않는 함수를 사용하는 클라이언트 코드에 더 적합합니다.  순수 MSIL 어셈블리에 포함된 기능이 관리되지 않는 함수에 사용하기 위한 것이라면 혼합형 어셈블리를 인터페이스 레이어로 사용해야 합니다.  
  
 ATL 또는 MFC를 사용하는 응용 프로그램은 순수 MSIL로 마이그레이션하기에 적합하지 않습니다. 이러한 라이브러리는 이 릴리스에서 지원되지 않기 때문입니다.  마찬가지로, [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]에는 **\/clr:pure**로 컴파일되지 않는 헤더 파일이 포함되어 있습니다.  
  
 순수 MSIL 어셈블리에서 관리되지 않는 함수를 호출할 수는 있지만 이 기능은 간단한 C 스타일 함수로만 제한됩니다.  관리되지 않는 더 복잡한 API를 사용하려면 COM 인터페이스의 형태로 노출되는 관리되지 않는 기능을 사용해야 하거나 순수 MSIL과 관리되지 않는 구성 요소 사이에 인터페이스로 작용할 수 있는 혼합형 어셈블리를 사용해야 합니다.  예를 들어, 콜백 함수가 필요한 관리되지 않는 함수를 사용하려면 혼합형 어셈블리 레이어를 사용해야만 합니다. 순수형 어셈블리에서는 콜백으로 사용하기 위한 호출 가능한 네이티브 함수를 제공할 수 없기 때문입니다.  
  
## 응용 프로그램 도메인 및 호출 규칙  
 순수 MSIL 어셈블리에서 관리되지 않는 기능을 사용할 수는 있지만 함수와 정적 데이터는 서로 다른 방식으로 처리됩니다.  순수형 어셈블리에서 함수는 [\_\_clrcall](../cpp/clrcall.md) 호출 규칙을 사용하여 구현되고 정적 데이터는 응용 프로그램별 도메인에 저장됩니다.  이는 함수에 대해 [\_\_cdecl](../cpp/cdecl.md) 호출 규칙을 사용하고 정적 데이터를 프로세스별로 저장하는 관리되지 않는 어셈블리 및 혼합형 어셈블리의 기본 동작과 다릅니다.  
  
 [\_\_clrcall](../cpp/clrcall.md)은 CLR의 기본 호출 규칙이고 응용 프로그램 도메인은 .NET 응용 프로그램의 정적 및 전역 데이터에 대한 네이티브 범위이므로 순수 MSIL 및 \/clr:safe로 컴파일된 안정형 코드의 컨텍스트 내에서 이러한 기본 동작은 명확하게 수행됩니다.  그러나 관리되지 않는 구성 요소나 혼합 구성 요소가 중간에 끼어들면 함수와 전역 데이터가 다른 방식으로 처리되어 문제가 발생할 수 있습니다.  
  
 예를 들어, 순수 MSIL 구성 요소가 관리되지 않는 DLL이나 혼합 DLL의 함수를 호출해야 하는 경우 순수형 어셈블리를 컴파일하는 데는 DLL의 헤더 파일이 사용됩니다.  그러나 헤더에서 각 함수에 대한 호출 규칙을 명시적으로 지정하지 않으면 모든 호출에 [\_\_clrcall](../cpp/clrcall.md)을 사용하는 것으로 간주됩니다.  이러한 함수를 [\_\_cdecl](../cpp/cdecl.md) 규칙으로 구현해야 할 수도 있으므로 이는 나중에 런타임 오류를 일으킬 수 있습니다.  관리되지 않는 헤더 파일의 함수가 [\_\_cdecl](../cpp/cdecl.md)로 명시적으로 표시될 수 있습니다. 또는 전체 DLL 소스 코드를 **\/clr:pure**를 사용하여 다시 컴파일해야 합니다.  
  
 마찬가지로, **\/clr:pure** 컴파일의 경우 함수 포인터는 [\_\_clrcall](../cpp/clrcall.md) 함수를 가리키는 것으로 간주됩니다.  이러한 함수 포인터도 마찬가지로 올바른 호출 규칙을 사용하여 명시적으로 지정해야 합니다.  
  
 자세한 내용은 [응용 프로그램 도메인 및 Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md)을 참조하십시오.  
  
## 링크 제한  
 저장소 범위와 호출 규칙이 서로 다르기 때문에 Visual C\+\+ 링커는 혼합형 및 순수형 OBJ 파일을 링크하지 않습니다.  
  
## 참고 항목  
 [순수형 및 안정형 코드](../dotnet/pure-and-verifiable-code-cpp-cli.md)