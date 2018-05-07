---
title: 순수형 및 안정형 코드 (C + + /cli CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c4f4b9bd590ad873d0b241d2c095be53ad1dacb4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="pure-and-verifiable-code-ccli"></a>순수형 및 안정형 코드(C++/CLI)
.NET 프로그래밍에 대 한 Visual Studio 2017에 Visual c + +를 사용 하 여 혼합된 어셈블리의 생성을 지원는 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션입니다. **/clr: pure** 및 **: safe** 옵션에는 Visual Studio 2015를 기준으로 사용 되지 않으며 이후 버전의 컴파일러에서 제거 됩니다. 코드를 확인할 수 있으려면 하는 경우 C#로 포팅하 하도록 권장 합니다.
  
## <a name="mixed-clr"></a>혼합 (/ clr)  
 혼합형 어셈블리 (컴파일된 **/clr**) 부분과 관리 되지 않는 모두 포함 하 여.NET 기능을 사용할 수 있도록 하는 관리 되는 부분이 하지만 여전히 네이티브 코드를 포함 합니다. 이렇게 하면 전체 프로젝트 다시 작성 하지 않고도.NET 기능을 사용 하도록 업데이트할 응용 프로그램 및 구성 합니다. Visual c + +를 사용 하 여 이러한 방식으로 관리 코드와 네이티브 코드를 혼합 하는 c + + Interop 호출 됩니다. 자세한 내용은 참조 [혼합 (네이티브 / 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md) 및 [네이티브 및.NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)합니다.  
  
  
P/Invoke를 통해 네이티브 Dll로 관리 되는 어셈블리에서 호출은 컴파일되지만 보안 설정에 따라 런타임에 실패할 수 있습니다.  
  
코드 작성 시나리오 컴파일러 성공 하지만 확인할 수 없는 어셈블리에 발생 하는: 범위 확인 연산자를 사용 하 여 개체 인스턴스를 통해 가상 함수를 호출 합니다.  예: `MyObj -> A::VirtualFunction();`  
  
## <a name="see-also"></a>참고 항목  
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
