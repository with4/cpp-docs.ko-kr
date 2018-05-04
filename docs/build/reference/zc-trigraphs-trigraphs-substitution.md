---
title: '/Zc: trigraphs (삼중 자 대체) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e465b62944b360d6fdb09da1230f3353658437b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs(삼중자 대체)

때 **/zc: trigraphs** 지정, 컴파일러가 해당 문장 부호 문자를 사용 하 여 삼중 자는 문자 시퀀스를 바꿉니다.

## <a name="syntax"></a>구문

> **/Zc:trigraphs**[**-**]  

## <a name="remarks"></a>설명

A *삼중 자* 두 개의 연속 된 물음표로 시작 구성 됩니다 ("??") 뒤에 고유한 세 번째 문자입니다. C 언어 표준 일부 문장 부호 문자에 대 한 편리한 그래픽 표현을 포함 하지 않는 문자 집합을 사용 하는 소스 파일에 대 한 삼중 자를 지원 합니다. 예를 들어 삼중 자 설정 되 면 컴파일러 대체는 "?? = "'#' 문자를 사용 하 여 삼중 자입니다. C + + 14를 통해 삼중 자는 3. 에서처럼 지원 C + + 언어에서 삼중 자 제거 하는 표준 C + + 17 합니다. C + + 코드에서는 **/zc: trigraphs** 컴파일러 옵션을 사용 하면 대체 삼중 자 시퀀스의 해당 문장 부호 문자입니다. **/Zc:trigraphs-** 삼중 자 대체를 사용 하지 않도록 설정 합니다.

**/zc: trigraphs** 옵션은 기본적으로 해제 되어 및 옵션이 않는 때 영향을 받는 [관대 한 /-](permissive-standards-conformance.md) 옵션을 지정 합니다.

C/c + + 삼중 자 및 삼중 자를 사용 하는 방법을 보여 주는 예제 목록 참조 [삼중 자](../../c-language/trigraphs.md)합니다.

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 수정 된 **추가 옵션** 포함할 속성을 **/zc: trigraphs** 또는 **/Zc:trigraphs-** 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](../../build/reference/zc-conformance.md)<br/>
[삼중자](../../c-language/trigraphs.md)<br/>
