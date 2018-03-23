---
title: / POGOSAFEMODE (실행 PGO 스레드 안전 모드에서) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- POGOSAFEMODE
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 886fbae5fbeb7606ec0321595f061d2262988170
ms.sourcegitcommit: ee7d74683af7631441c8c7f65ef5ceceaee4a5ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="pogosafemode-run-pgo-in-thread-safe-mode"></a>/ POGOSAFEMODE (실행 PGO 스레드 안전 모드에서)

**/POGOSAFEMODE 옵션은 Visual Studio 2015부터 사용 되지 않습니다는**합니다. 사용 하 여는 [/GENPROFILE: 정확한](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) 및 **/GENPROFILE:NOEXACT** 대신 옵션입니다. **/POGOSAFEMODE** 링커 옵션 스레드 안전 모드 실행 학습 (PGO) 프로필 기반 최적화 중 프로필 데이터 캡처를 사용 하 여 계측 된 빌드 목록을 만들도록 지정 합니다.

## <a name="syntax"></a>구문

> **/POGOSAFEMODE**

## <a name="remarks"></a>설명

프로필 기반 최적화 (PGO)의 두 가지 가능한 모드 단계에서 프로 파일링: *고속 모드* 및 *안전 모드*합니다. 프로 파일링 빠른 모드 이면 데이터 카운터를 늘리려면 증가 명령을 사용 합니다. 증분 명령은 빠르지만 스레드로부터 안전 하지 않습니다. 프로 파일링 하는 것은 안전 모드에서 데이터 카운터를 늘리려면 연동 증가 명령을 사용 합니다. 이 명령은 동일한 기능을 같습니다 증가 명령 개이고 스레드로부터 안전 하 게 보호 되지만 속도가 느립니다.

**/POGOSAFEMODE** 안전 모드를 사용 하 여 계측 된 빌드를 설정 하는 옵션입니다. 이 옵션에만 될 수 있습니다 때 사용 되는 사용 되지 않는 [/ltcg: pginstrument](ltcg-link-time-code-generation.md) PGO 계측 링커 단계를 지정 합니다.

기본적으로 빠른 모드로 작동 PGO 프로 파일링 합니다. **/ POGOSAFEMODE** 는 안전 모드를 사용 하려는 경우에 필요 합니다.

PGO 안전 모드로 프로 파일링을 실행 하려면 하나를 사용 해야 **/GENPROFILE: 정확한** (기본 설정), 환경 변수를 사용 하거나 [PogoSafeMode](environment-variables-for-profile-guided-optimizations.md) 또는 링커 스위치 **/POGOSAFEMODE**시스템에 따라 합니다. X64 프로 파일링 수행 중인 경우 컴퓨터를 링커 스위치를 사용 해야 합니다. X86 프로 파일링 수행 중인 경우 컴퓨터를 링커 스위치를 사용 하거나 PGO 계측 프로세스를 시작 하기 전에 환경 변수 값을 정의할 수 있습니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **최적화** 속성 페이지.

1. 에 **링크 타임 코드 생성** 속성을 선택 **프로필 기반 최적화-계측 (/: pginstrument)**합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 입력은 **/POGOSAFEMODE** 옵션에 **추가 옵션** 상자입니다. 선택 **확인** 변경 내용을 저장 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/GENPROFILE 및 /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)<br/>
[프로필 기반 최적화 환경 변수](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>
