---
title: /Zc:__cplusplus (업데이트 된 __cplusplus 매크로 사용)
ms.custom: ''
ms.date: 05/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:__cplusplus
dev_langs:
- C++
helpviewer_keywords:
- -Zc:__cplusplus compiler option (C++)
- __cplusplus macro (C++)
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a796794c0086b09c15ee88442e0fea4d1b114d98
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705720"
---
# <a name="zccplusplus-enable-updated-cplusplus-macro"></a>/Zc:__cplusplus (업데이트 된 __cplusplus 매크로 사용)

**/Zc:__cplusplus** 컴파일러 옵션 사용은  **\_ \_cplusplus** 최신 c + + 언어 표준 지원에 대 한 업데이트 된 값을 보고 하기 위해 전처리기 매크로입니다. 기본적으로 Visual Studio 항상 반환 값에 "199711 L"에 대 한는  **\_ \_cplusplus** 전처리기 매크로입니다.

## <a name="syntax"></a>구문

> **/Zc:__cplusplus**[**-**]

## <a name="remarks"></a>설명

**\_ \_cplusplus** 전처리기 매크로 일반적으로 c + + 표준의 특정 버전에 대 한 지원 되는 보고서에 사용 됩니다. 명시적으로 옵트인를 사용 하 여 하지 않으면 컴파일러 매크로의 값에 바뀌지 않으면 기존 코드의 많은 "199711 L"와 일치 하는이 매크로의 값에 따라 달라 지도록 나타나므로 **/Zc:__cplusplus** 컴파일러 옵션입니다. **/Zc:__cplusplus** 옵션은 Visual Studio 2017 15.7, 버전부터 사용할 수 및 기본적으로 해제 되어 있습니다. 이전 버전의 Visual Studio 및 기본적으로 또는 **/Zc:__cplusplus-** 지정, "199711 L" 값을 반환 하는 Visual Studio에 대 한는  **\_ \_cplusplus** 전처리기 매크로입니다. [관대 한 /-](permissive-standards-conformance.md) 옵션을 사용 하지 않는 **/Zc:__cplusplus**합니다.

경우는 **/Zc:__cplusplus** 옵션을 사용 하 여 보고 된 값의  **\_ \_cplusplus** 매크로에 따라 달라 집니다는 [/std](std-specify-language-standard-version.md) 버전 스위치 설정입니다. 이 표에서 매크로 대 한 가능한 값을 보여 줍니다.

|/Zc:__cplusplus 스위치|/std:c++ 스위치|__cplusplus 값|
|-|-|-|
Zc:__cplusplus|/std:c + + 14 (기본값)|201402 L
Zc:__cplusplus|/std:c + + 17|201703 L
Zc:__cplusplus|/std:c + + 최신|201704 L
Zc:__cplusplus-(사용 안 함)|모든 값|199711 L
지정 안 됨|모든 값|199711 L

컴파일러는 C + + 98, C + + 03에서는 또는 C + + 11에 대 한 표준 스위치를 지원 하지 않습니다.

컴파일러 도구 집합에 대 한 변경의 세부적인 탐지에 사용 된 [_MSC_VER](../../preprocessor/predefined-macros.md) 미리 정의 된 매크로입니다. 이 기본 제공 매크로의 값은 Visual Studio 2017 이상 버전에서 모든 도구 집합 업데이트에 대해 증가 됩니다. [_MSVC_LANG](../../preprocessor/predefined-macros.md) 미리 정의 된 매크로 보고 표준 버전 여부는 **/Zc:__cplusplus** 옵션 사용 하거나 사용 하지 않도록 설정 합니다. 때 **/Zc:__cplusplus** 를 사용 하는 `__cplusplus == _MSVC_LANG`합니다.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)을 참조하세요.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 추가 **/Zc:__cplusplus** 또는 **/Zc:__cplusplus-** 에 **추가 옵션:** 창.

## <a name="see-also"></a>참고자료

- [/Zc(규칙)](zc-conformance.md)
- [/std (지정 언어 표준 버전)](std-specify-language-standard-version.md)
- [미리 정의 된 매크로](../../preprocessor/predefined-macros.md)
