---
title: '-Zc: auto (변수 형식 추론) | Microsoft Docs'
ms.custom: ''
ms.date: 02/28/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:auto
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: caa64f64b75145c850c6f6393570dc3f9ba0b0d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="zcauto-deduce-variable-type"></a>/Zc:auto(변수 형식 추론)

**/zc: auto [-]** 컴파일러 옵션 컴파일러를 사용 하는 방법을 지시는 [auto 키워드](../../cpp/auto-keyword.md) 변수를 선언 합니다. 기본 옵션을 지정 하는 경우 **/zc: auto**, 컴파일러는 초기화 식에서 선언 된 변수의 형식을 추론 합니다. 지정 하는 경우 **/zc: auto-**, 컴파일러가 자동 저장소 클래스에 변수를 할당 합니다.

## <a name="syntax"></a>구문

> **/Zc:auto**[**-**]  

## <a name="remarks"></a>설명

C++ 표준에는 `auto` 키워드의 원래 의미와 수정된 의미가 정의되어 있습니다. 하기 전에 [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], 즉, 변수 있는 지역 변수; 키워드는 자동 저장소 클래스에는 변수를 선언 합니다. 부터는 [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], 키워드 선언의 초기화 식에서 변수의 형식을 추론 합니다. 사용 하 여는 **/zc: auto [-]** 컴파일러 옵션의 원래 이나 수정 된 의미를 사용 하도록 컴파일러에 지시 하는 `auto` 키워드입니다. **/zc: auto** 옵션은 기본적으로 합니다. [관대 한 /-](permissive-standards-conformance.md) 옵션의 기본 설정은 변경 되지 않습니다 **/zc: auto**합니다.

경우 컴파일러는 적절 한 진단 메시지를 발생 사용자의 사용은 `auto` 키워드 모순 현재 **/zc: auto** 컴파일러 옵션입니다. 자세한 내용은 참조 [auto 키워드](../../cpp/auto-keyword.md)합니다. Visual c + + 규칙과 관련 된 문제에 대 한 자세한 내용은 참조 [비표준 동작](../../cpp/nonstandard-behavior.md)합니다.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 추가 **/zc: auto** 또는 **/zc: auto-** 에 **추가 옵션:** 창.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](../../build/reference/zc-conformance.md)<br/>
[auto 키워드](../../cpp/auto-keyword.md)
