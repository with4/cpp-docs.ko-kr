---
title: "혼합형 (네이티브 및 관리) 어셈블리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interop [C++], mixed assemblies
- /clr compiler option [C++], mixed assemblies
- managed code [C++], interoperability
- interoperability [C++], mixed assemblies
- mixed DLL loading [C++]
- mixed assemblies [C++], about mixed assemblies
- assemblies [C++], mixed
- mixed assemblies [C++]
- native code [C++], .NET interoperatibility
ms.assetid: 4299dfce-392f-4933-8bf0-5da2f0d1c282
caps.latest.revision: "35"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: aeb0a4f21487d9d230c72bfbfc6a06928455dfe2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mixed-native-and-managed-assemblies"></a>혼합형(네이티브 및 관리) 어셈블리
혼합형된 어셈블리는 관리 되지 않는 컴퓨터 명령과 MSIL 명령이 포함 될 수 있습니다. 따라서 호출 하 고 완전히 관리 되지 않는 구성 요소와의 호환성을 유지 하는 동안에.NET 구성 요소에서 호출할 수 있습니다. 혼합형된 어셈블리를 사용 하 여 작성 하는 스레드와 관리 되지 않는 기능이 함께 사용 하 여 응용 프로그램입니다. 이렇게 하면 혼합형된 어셈블리를 기존 Visual c + + 응용 프로그램을.NET 플랫폼으로 마이그레이션하는 데 적합 합니다.  
  
 예를 들어 관리 되지 않는 함수 공백으로 구성 된 기존 응용 프로그램 기울일 수 있도록.NET 플랫폼 사용 하 여 하나의 모듈을 다시 컴파일하여는 **/clr** 컴파일러 스위치입니다. 이 모듈.NET 기능을 사용할 수 있지만 응용 프로그램의 나머지 부분에서는 호환성이 유지 됩니다. 이러한 방식으로 응용 프로그램 점진적이 고 하나씩 방식으로.NET 플랫폼으로 변환할 수 있습니다. 동일한 파일 내에서 각 함수에서 함수 별로 스레드와 관리 되지 않는 컴파일을 선택할 수도 (참조 [관리, 관리 되지 않는](../preprocessor/managed-unmanaged.md)).  
  
 Visual c + + 라는 세 가지 형식의 관리 되는 어셈블리의 생성을 지원: 혼합형, 순수형 및 안정형 합니다. 후자 두에 대해서는 설명 [순수형 및 안정형 코드 (C + + /cli CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: /clr으로 마이그레이션](../dotnet/how-to-migrate-to-clr.md)  
 도입 하거나 응용 프로그램에서.NET 기능 업그레이드에 대 한 권장 되는 단계를 설명 합니다.  
  
 [방법: MFC 및 ATL 코드 사용 하 여 /clr 컴파일](../dotnet/how-to-compile-mfc-and-atl-code-by-using-clr.md)  
 기존 MFC 및 ATL 프로그램을 공용 언어 런타임을 대상으로 컴파일하는 방법을 설명 합니다.  
  
 [혼합형 어셈블리 초기화](../dotnet/initialization-of-mixed-assemblies.md)  
 "로더 잠금" 문제 및 해결 방법에 설명합니다.  
  
 [혼합형 어셈블리에 대한 라이브러리 지원](../dotnet/library-support-for-mixed-assemblies.md)  
 네이티브 라이브러리를 사용 하는 방법을 설명 **/clr** 컴파일 수입니다.  
  
 [성능 고려 사항](../dotnet/performance-considerations-for-interop-cpp.md)  
 혼합형된 어셈블리와 데이터 마샬링을의 성능에 미치는 영향에 설명합니다.  
  
 [응용 프로그램 도메인 및 Visual C++](../dotnet/application-domains-and-visual-cpp.md)  
 응용 프로그램 도메인에 대 한 Visual c + + 지원에 설명 합니다.  
  
 [이중 썽킹](../dotnet/double-thunking-cpp.md)  
 관리 되는 함수에 대 한 네이티브 진입점의 성능에 미치는 영향에 설명 합니다.  
  
 [/Clr을 사용한 CLR 종료를 사용해 COM 개체 작성 시 예외 방지](../dotnet/avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr.md)  
 로 컴파일된 COM 개체를 사용 하는 관리 되는 응용 프로그램의 올바르게 종료 하는 방법에 설명 **/clr**합니다.  
  
 [방법: CRT 라이브러리 DLL에 대한 종속성을 제거하여 부분적으로 신뢰할 수 있는 응용 프로그램 만들기](../dotnet/create-a-partially-trusted-application.md)  
 Visual c + +를 사용 하 여 msvcm90.dll에 대 한 종속성을 제거 하 여 부분적으로 신뢰할 수 있는 공용 언어 런타임 응용 프로그램을 만드는 방법을 설명 합니다.  
  
 혼합형된 어셈블리에 대 한 지침을 코딩 하는 방법에 대 한 자세한 내용은 MSDN 문서 "는 개요의 관리 되 는/관리 되지 않는 코드 상호 운용성"에서 참조 [http://msdn.microsoft.com/netframework/default.aspx?pull=/library/dndotnet/html/manunmancode.asp](http://msdn.microsoft.com/netframework/default.aspx?pull=/library/dndotnet/html/manunmancode.asp)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)