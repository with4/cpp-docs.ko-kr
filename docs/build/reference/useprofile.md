---
title: /USEPROFILE (LTCG 사용 하 여 사용 하 여 PGO 데이터) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- USEPROFILE
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b12c2e63d5e65d2528f77852d9466d4161d7cc6a
ms.sourcegitcommit: ee7d74683af7631441c8c7f65ef5ceceaee4a5ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="useprofile-run-pgo-in-thread-safe-mode"></a>/USEPROFILE (실행 PGO 스레드 안전 모드에서)

와 함께이 링커 옵션 [/LTCG (링크 타임 코드 생성](ltcg-link-time-code-generation.md) 프로필 기반 최적화 (PGO) 학습 데이터를 사용 하 여 작성 하도록 링커에 지시 합니다.

## <a name="syntax"></a>구문

> **/USEPROFILE**[**:**{**AGGRESSIVE**|**PGD=**_filename_}]

### <a name="arguments"></a>인수

**적극적인**<br/>
이 인수는 최적화 된 코드 생성 하는 동안 적극적인 속도 최적화를 사용 해야 함을 지정 합니다.

**PGD**=*파일 이름*<br/>
.pgd 파일의 기본 파일 이름을 지정합니다. 기본적으로 링커는 p g d 확장명을 가진 기본 실행 파일 이름을 사용합니다.

## <a name="remarks"></a>설명

**/USEPROFILE** 링커 옵션은 함께 사용 되어 **/LTCG** 를 생성 하거나 PGO 교육 데이터에 따라 최적화 된 빌드를 업데이트 합니다. 해당 하는 사용 되지 않는 것이 **/ltcg: pgupdate** 및 **/ltcg: pgoptimize** 옵션입니다.

선택적 **전체 업그레이드** 인수 속도 최적화 하려고 크기 관련 된 추론을 사용 하지 않도록 설정 합니다. 이 실질적으로 프로그램 실행 파일의 크기가 증가 하 고 결과 속도 증가 하지 않을 수 있습니다 하는 최적화 될 수 있습니다. 프로 파일링 하 고 결과를 사용 하 고 사용 하지 않는 비교 해야 **전체 업그레이드**합니다. 이 인수를 명시적으로; 지정 해야 합니다. 기본적으로 사용 되지 않습니다.

**PGD** 인수에서와 같이 동일한 사용할 학습 데이터.pgd 파일에 대 한 선택적 이름을 지정 [/GENPROFILE 또는 /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)합니다. 해당 하는 사용 되지 않는 것이 **/PGD** 전환 합니다. 기본적으로 되지 않은 경우 또는 *filename* 지정 된 실행 파일이 사용 되는 것과 같이 동일한 기본 이름을 가진.pgd 파일입니다.

**/USEPROFILE** 링커 옵션은 Visual Studio 2015의 새로운 기능입니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **최적화** 속성 페이지.

1. 에 **링크 타임 코드 생성** 속성을 선택 **링크 타임 코드 생성 사용 (/ LTCG)**합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 입력은 **/USEPROFILE** 옵션 및 선택적 인수에는 **추가 옵션** 상자입니다. 선택 **확인** 변경 내용을 저장 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/GENPROFILE 및 /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)<br/>
[프로필 기반 최적화 환경 변수](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>
