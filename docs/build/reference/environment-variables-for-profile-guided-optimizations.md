---
title: 프로필 기반 최적화에 대 한 환경 변수 | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- profile-guided optimizations, environment variables
ms.assetid: f95a6d1e-49a4-4802-a144-092026b600a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19edc9c8a2702e5b7ac9ae4a49364718f19d3900
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="environment-variables-for-profile-guided-optimizations"></a>프로필 기반 최적화 환경 변수

테스트 시나리오에 사용 하 여 만든 이미지에 영향을 주는 세 가지 환경 변수는 **/ltcg: pgi** 프로필 기반 최적화에 대 한:

- **PogoSafeMode** 응용 프로그램 프로 파일링에 대 한 빠른 모드나 안전 모드를 사용할지 여부를 지정 합니다.

- **VCPROFILE_ALLOC_SCALE** 프로파일러에서 사용 하기 위해 추가 메모리를 추가 합니다.

- **VCPROFILE_PATH** .pgc 파일에 사용 되는 폴더를 지정할 수 있습니다.

**PogoSafeMode 및 VCPROFILE_ALLOC_SCALE 환경 변수는 Visual Studio 2015부터 사용 되지 않습니다.** 링커 옵션 [/GENPROFILE 또는 /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) 및 [/USEPROFILE](useprofile.md) 이러한 환경 변수로 동일한 링커 동작을 지정 합니다.

## <a name="pogosafemode"></a>PogoSafeMode

이 환경 변수는 사용 되지 않습니다. 사용 하 여는 **EXACT** 또는 **NOEXACT** 에 대 한 인수 **/GENPROFILE** 또는 **/FASTGENPROFILE** 이 동작을 제어 합니다.

설정 하거나 취소 된 **PogoSafeMode** x86 응용 프로그램 프로 파일링에 대 한 빠른 모드나 안전 모드 사용 여부를 지정 하도록 환경 변수 시스템.

프로필 기반 최적화 (PGO)의 두 가지 가능한 모드 단계에서 프로 파일링: *고속 모드* 및 *안전 모드*합니다. 사용 하 여 프로 파일링 이면 고속 모드는 **INC** 데이터 카운터를 늘리려면 명령입니다. **INC** 명령은 빠르지만 스레드로부터 안전 하지 않습니다. 프로 파일링 하는 것은 안전 모드로 사용 하 여는 **LOCK INC** 데이터 카운터를 늘리려면 명령입니다. **LOCK INC** 명령으로 동일한 기능에는 **INC** 명령 개이고는 스레드로부터 안전 하지만 보다 느립니다는 **INC** 명령입니다.

기본적으로 빠른 모드로 작동 PGO 프로 파일링 합니다. **PogoSafeMode** 는 안전 모드를 사용 하려는 경우에 필요 합니다.

PGO 안전 모드로 프로 파일링을 실행 하거나 사용 해야 환경 변수 **PogoSafeMode** 또는 링커 스위치 **/PogoSafeMode**시스템에 따라 합니다. X64 프로 파일링 수행 중인 경우 컴퓨터를 링커 스위치를 사용 해야 합니다. X86 프로 파일링 수행 중인 경우 컴퓨터 링커를 사용할 수 있습니다 전환 하거나 설정는 **PogoSafeMode** 최적화 프로세스를 시작 하기 전에 값을 환경 변수입니다.

### <a name="pogosafemode-syntax"></a>PogoSafeMode 구문

> **set PogoSafeMode**[**=**_value_]

설정 **PogoSafeMode** 안전 모드를 사용 하도록 설정 하려면 값으로. 이전 값을 지우고 다시 고속 모드를 사용 하도록 설정 하는 값 없이 설정 합니다.

## <a name="vcprofileallocscale"></a>VCPROFILE_ALLOC_SCALE

이 환경 변수는 사용 되지 않습니다. 사용 하 여는 **MEMMIN** 및 **MEMMAX** 에 대 한 인수 **/GENPROFILE** 또는 **/FASTGENPROFILE** 이 동작을 제어 합니다.

수정 된 **VCPROFILE_ALLOC_SCALE** 프로필 데이터를 보관에 할당 된 메모리의 크기를 변경 하려면 환경 변수입니다. 드문 경우에서 지 원하는 데 사용할 수 있는 충분 한 메모리 되지 테스트 시나리오를 실행 하는 경우 프로필 데이터를 수집 합니다. 이 경우 메모리 양을 설정 하 여 늘릴 수 있습니다 **VCPROFILE_ALLOC_SCALE**합니다. 메모리가 부족 한지 여부를 나타내는 테스트 실행 도중 오류 메시지를 수신 하는 경우에 더 큰 값을 할당 **VCPROFILE_ALLOC_SCALE**테스트 실행이 메모리 부족 오류 없이 완료 될 때까지, 합니다.

### <a name="vcprofileallocscale-syntax"></a>VCPROFILE_ALLOC_SCALE 구문

> **VCPROFILE_ALLOC_SCALE 설정**[__=__*scale_value*]

*scale_value* 매개 변수는 테스트 시나리오를 실행 하기 위한 메모리 크기는 배율 인수입니다.  기본값은 1입니다. 예를 들어이 명령줄 배율 인수를 2로 설정합니다.

`set VCPROFILE_ALLOC_SCALE=2`

## <a name="vcprofilepath"></a>VCPROFILE_PATH

사용 하 여 **VCPROFILE_PATH** .pgc 파일을 만들 디렉터리를 지정 하려면 환경 변수입니다. 기본적으로 프로 파일링 되 고 바이너리와 동일한 디렉터리에.pgc 파일이 만들어집니다. 그러나 이진 파일의 절대 경로 없는 경우, 이진 작성 된 다른 컴퓨터에서 프로 파일링 시나리오를 실행할 때 대/소문자 수 있으므로, 설정할 수 있습니다 **VCPROFILE_PATH** 대상 컴퓨터에 존재 하는 경로입니다.

### <a name="vcprofilepath-syntax"></a>VCPROFILE_PATH 구문

> **VCPROFILE_PATH 설정**[**=**_경로_]

설정의 *경로* .pgc 파일을 추가 하려면 디렉터리 경로를 매개 변수입니다. 예를 들어 명령줄이 C:\profile에 폴더를 설정 합니다.

`set VCPROFILE_PATH=c:\profile`

## <a name="see-also"></a>참고자료

[프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)<br/>
[/GENPROFILE 및 /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/USEPROFILE](useprofile.md)<br/>
