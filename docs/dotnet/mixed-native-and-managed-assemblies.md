---
title: "혼합형(네이티브 및 관리) 어셈블리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "/clr 컴파일러 옵션[C++], 혼합형 어셈블리"
  - "어셈블리[C++], 혼합형"
  - "interop[C++], 혼합형 어셈블리"
  - "상호 운용성[C++], 혼합형 어셈블리"
  - "관리 코드[C++], 상호 운용성"
  - "혼합형 어셈블리[C++]"
  - "혼합형 어셈블리[C++], 혼합형 어셈블리 정보"
  - "혼합 DLL 로드[C++]"
  - "네이티브 코드[C++], .NET 상호 운용성"
ms.assetid: 4299dfce-392f-4933-8bf0-5da2f0d1c282
caps.latest.revision: 35
caps.handback.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 혼합형(네이티브 및 관리) 어셈블리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

혼합형 어셈블리에는 관리되지 않는 기계어 명령과 MSIL 명령이 모두 포함될 수 있습니다.  이렇게 하면 전혀 관리되지 않는 구성 요소와의 호환성을 유지한 채 이 어셈블리에서 .NET 구성 요소를 호출하거나 .NET 구성 요소에서 이 어셈블리를 호출할 수 있습니다.  혼합형 어셈블리를 사용하면 관리되는 기능과 관리되지 않는 기능이 함께 사용되는 응용 프로그램을 작성할 수 있습니다.  이러한 점에서 혼합형 어셈블리는 기존 Visual C\+\+ 응용 프로그램을 .NET 플랫폼으로 마이그레이션하는 데 적합합니다.  
  
 예를 들어, **\/clr** 컴파일러 스위치를 사용하여 모듈 하나를 컴파일하는 것만으로도 관리되지 않는 함수로만 구성된 기존 응용 프로그램을 .NET 플랫폼에서 사용할 수 있습니다.  이 모듈은 응용 프로그램의 나머지 부분과 계속 호환 상태를 유지하면서 .NET 기능을 사용할 수 있습니다.  이와 같이 점진적이고 단위적인 방식으로 응용 프로그램을 .NET 플랫폼에 맞도록 변환할 수 있습니다.  동일한 파일 내에서 각 함수별로 관리되는 컴파일 또는 관리되지 않는 컴파일을 선택할 수도 있습니다. [관리되는, 관리되지 않는](../preprocessor/managed-unmanaged.md)를 참조하십시오.  
  
 Visual C\+\+에서는 세 가지 형식의 관리되는 어셈블리\(혼합형, 순수 및 확인 가능\) 생성을 지원합니다.  마지막 두 가지 형식의 어셈블리에 대한 내용은 [순수형 및 안정형 코드](../dotnet/pure-and-verifiable-code-cpp-cli.md)을 참조하십시오.  
  
## 단원 내용  
 [방법: \/clr로 마이그레이션](../dotnet/how-to-migrate-to-clr.md)  
 응용 프로그램에서 .NET 기능을 도입하거나 업그레이드하는 데 필요한 권장 단계에 대해 설명합니다.  
  
 [방법: \/clr을 사용하여 MFC 및 ATL 코드 컴파일](../dotnet/how-to-compile-mfc-and-atl-code-by-using-clr.md)  
 공용 언어 런타임을 대상으로 기존 MFC 및 ATL 프로그램을 컴파일하는 방법에 대해 설명합니다.  
  
 [혼합형 어셈블리 초기화](../dotnet/initialization-of-mixed-assemblies.md)  
 "로더 잠금" 문제와 해결책에 대해 설명합니다.  
  
 [혼합형 어셈블리에 대한 라이브러리 지원](../dotnet/library-support-for-mixed-assemblies.md)  
 **\/clr** 컴파일에 네이티브 라이브러리를 사용하는 방법에 대해 설명합니다.  
  
 [성능 고려 사항](../dotnet/performance-considerations-for-interop-cpp.md)  
 혼합형 어셈블리 및 데이터 마샬링이 성능에 미치는 영향에 대해 설명합니다.  
  
 [응용 프로그램 도메인 및 Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md)  
 응용 프로그램 도메인과 관련된 Visual C\+\+ 지원에 대해 설명합니다.  
  
 [이중 썽킹](../dotnet/double-thunking-cpp.md)  
 관리되지 않는 함수에 대한 네이티브 진입점이 성능에 미치는 영향에 대해 설명합니다.  
  
 [\/clr로 빌드한 COM 개체를 사용할 때 CLR 종료 시 예외 방지](../dotnet/avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr.md)  
 **\/clr**을 사용하여 컴파일한 COM 개체를 사용하는 관리되는 응용 프로그램을 올바르게 종료하는 방법에 대해 설명합니다.  
  
 [방법: CRT 라이브러리 DLL에 대한 종속성을 제거하여 부분적으로 신뢰할 수 있는 응용 프로그램 만들기](../dotnet/create-a-partially-trusted-application.md)  
 msvcm90.dll에 대한 종속성을 제거하고 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]를 사용하여 부분적으로 신뢰할 수 있는 공용 언어 런타임 응용 프로그램을 만드는 방법에 대해 설명합니다.  
  
 혼합된 어셈블리에 대한 코딩 지침에 대한 자세한 내용은 MSDN의 "관리되는\/관리되지 않는 코드 상호 운용성의 개요" 문서를 [http:\/\/msdn.microsoft.com\/netframework\/default.aspx?pull\=\/ library\/dndotnet\/html\/manunmancode.asp](http://msdn.microsoft.com/netframework/default.aspx?pull=/library/dndotnet/html/manunmancode.asp)에서 확인하세요.  
  
## 참고 항목  
 [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)