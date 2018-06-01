---
title: 혼합형된 어셈블리에 대 한 라이브러리 지원 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d4b584e0bacb1cb93cad33efdff807bb5fa9c8e2
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704113"
---
# <a name="library-support-for-mixed-assemblies"></a>혼합형 어셈블리에 대한 라이브러리 지원

Visual c + +는 c + + 표준 라이브러리는 C 런타임 라이브러리 (CRT)의 사용을 지 원하는 ATL 및 MFC를 사용 하 여 컴파일된 응용 프로그램에 대 한 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)합니다. 따라서 이러한 라이브러리를 사용 하 여.NET Framework 기능을 사용 하는 기존 응용 프로그램 수 있습니다.

> [!IMPORTANT]
> **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

이 지원은 다음 DLL 및 가져오기 라이브러리가 포함 되어 있습니다.

- 사용 하 여 컴파일하면 Msvcmrt [d].lib **/clr**합니다. 혼합형된 어셈블리 링크가 가져오기 라이브러리입니다.

이 지원을 여러 관련 이점을 제공 합니다.

- CRT 및 c + + 표준 라이브러리는 혼합된 코드에서 사용할 수 있습니다. CRT 및 제공 하는 c + + 표준 라이브러리는 확인할 수 있습니다. 궁극적으로, 네이티브 코드에서 사용 하 여 통화는 여전히 동일한 CRT 및 c + + 표준 라이브러리에 라우팅됩니다 됩니다.

- 통합 된 예외 처리 혼합된 이미지를 수정 합니다.

- 혼합된 이미지의 c + + 변수 정적 초기화 합니다.

- 관리 되는 코드에서 프로세스별 및 AppDomain 별 변수를 지원 합니다.

- 이 하 버전 Visual Studio 2003에서 컴파일된 혼합된 Dll에 적용 하는 로더 잠금 문제를 해결 합니다.

또한이 지원을 다음과 같은 제한 사항을 제공합니다.

- 로 컴파일된 코드는 CRT DLL 모델에만 사용할 수 **/clr**합니다. 지 원하는 정적 CRT 라이브러리가 **/clr** 빌드합니다.

이전 버전에서 실행 되도록 보장 되지는 대로 현재 버전을 공용 언어 런타임 (CLR)를 업데이트 해야 합니다. 이러한 변경 내용으로 작성 된 코드는 CLR 버전에서 실행 되지 것입니다 1.x 합니다.

## <a name="see-also"></a>참고자료

- [혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)
