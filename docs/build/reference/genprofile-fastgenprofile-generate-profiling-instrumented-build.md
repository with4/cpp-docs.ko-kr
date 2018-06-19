---
title: /GENPROFILE, /FASTGENPROFILE (계측 된 빌드 프로 파일링 생성) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- GENPROFILE
- FASTGENPROFILE
- /GENPROFILE
- /FASTGENPROFILE
helpviewer_keywords:
- GENPROFILE
- FASTGENPROFILE
ms.assetid: deff5ce7-46f5-448a-b9cd-a7a83a6864c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05d7961ff46661b8f6df2768591932699c3965d4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379304"
---
# <a name="genprofile-fastgenprofile-generate-profiling-instrumented-build"></a>/GENPROFILE, /FASTGENPROFILE(계측된 빌드 프로파일링 생성)

링커에서 PGO(프로필 기반 최적화)를 지원하기 위한 .pgd 파일의 생성을 지정합니다. **/GENPROFILE** 및 **/FASTGENPROFILE** 서로 다른 기본 매개 변수를 사용 합니다. 사용 하 여 **/GENPROFILE** 프로 파일링 중 속도 및 메모리 사용 보다 정밀도 우선 하려면. 사용 하 여 **/FASTGENPROFILE** 전체 자릿수 보다 작은 메모리 사용 및 속도 중 우선 하 합니다.

## <a name="syntax"></a>구문

> **/GENPROFILE**[**:**{[**COUNTER32**|**COUNTER64**]|[**EXACT**|**NOEXACT**]|**MEMMAX=**_#_|**MEMMIN=**_#_|[**PATH**|**NOPATH** ]|[**TRACKEH** |**NOTRACKEH** ]|**PGD=**_filename_}]<br/>
> **/FASTGENPROFILE**[**:**{[**COUNTER32**|**COUNTER64**]|[**EXACT**|**NOEXACT**]|**MEMMAX=**_#_|**MEMMIN=**_#_|[**PATH**|**NOPATH** ]|[**TRACKEH** |**NOTRACKEH** ]|**PGD=**_filename_}]

### <a name="arguments"></a>인수

다음 인수 중 하나를 지정할 수 있습니다 **/GENPROFILE** 또는 **/FASTGENPROFILE**합니다. 여기에 나열 된 인수 파이프로 구분 된 (**|**) 문자는 함께 사용할 수 없습니다. 쉼표를 사용 하 여 (**,**) 옵션을 구분 하는 문자입니다.

**COUNTER32** &AMP;#124; **COUNTER64**<br/>
사용 하 여 **COUNTER32** 32 비트 프로브 카운터를 사용 하도록 지정할 및 **COUNTER64** 64 비트 프로브 카운터를 지정할 수 있습니다. 지정 하는 경우 **/GENPROFILE**, 기본값은 **COUNTER64**합니다. 지정 하는 경우 **/FASTGENPROFILE**, 기본값은 **COUNTER32**합니다.

**정확한** &AMP;#124; **NOEXACT**<br/>
사용 하 여 **EXACT** 프로브에 대해 스레드로부터 안전한 연관된 증분을 지정할 수 있습니다. **NOEXACT** 프로브에 대해 보호 되지 않는 증분 작업을 지정 합니다. 기본값은 **NOEXACT**합니다.

**MEMMAX**=*값*, **MEMMIN**=*값*<br/>
사용 하 여 **MEMMAX** 및 **MEMMIN** 메모리의 학습 데이터에 대 한 최대 및 최소 예약 크기를 지정할 수 있습니다. 값은 예약할 메모리의 크기(바이트)입니다. 기본적으로 이러한 값은 내부 추론에 의해 결정됩니다.

**PATH**  &#124; **NOPATH** <br/>
사용 하 여 **경로** 별도의 함수에 고유한 각 경로 대 한 PGO 카운터 집합을 지정할 수 있습니다. 사용 하 여 **NOPATH** 각 함수에 대 한 카운터 집합이 하나만 지정할 수 있습니다. 지정 하는 경우 **/GENPROFILE**, 기본값은 **경로** 합니다. 지정 하는 경우 **/FASTGENPROFILE**, 기본값은 **NOPATH** 합니다.

**TRACKEH** &AMP;#124; **NOTRACKEH**  <br/>
학습 중 예외가 throw되면 정확한 개수를 유지하기 위해 추가 카운터를 사용할지 여부를 지정합니다. 사용 하 여 **TRACKEH** 정확한 개수를 위해 추가 카운터를 지정할 수 있습니다. 사용 하 여 **NOTRACKEH** 예외를 사용 하지 않는 코드에 대 한 단일 카운터를 지정 하 여 처리 하거나 예외가 발생 하지 않는 학습 시나리오에서 합니다.  지정 하는 경우 **/GENPROFILE**, 기본값은 **TRACKEH** 합니다. 지정 하는 경우 **/FASTGENPROFILE**, 기본값은 **NOTRACKEH** 합니다.

**PGD**=*파일 이름*<br/>
.pgd 파일의 기본 파일 이름을 지정합니다. 기본적으로 링커는.pgd 확장명을 가진 기본 실행 가능 이미지 파일 이름을 사용합니다.

## <a name="remarks"></a>설명

**/GENPROFILE** 및 **/FASTGENPROFILE** 옵션 (PGO) 프로필 기반 최적화를 위한 학습 응용 프로그램을 지 원하는 데 필요한 프로 파일링 계측 파일을 생성 하도록 링커에 지시 합니다. 이러한 옵션은 Visual Studio 2015의 새로운 기능입니다. 이러한 옵션을 사용 되지 않는 것을 선호 **/ltcg: pginstrument**, **/PGD** 및 **/POGOSAFEMODE** 옵션 및 **PogoSafeMode**,  **VCPROFILE_ALLOC_SCALE** 및 **VCPROFILE_PATH** 환경 변수입니다. 학습 응용 프로그램에 의해 생성된 프로파일링 정보는 빌드 중 전체 대상 프로그램 최적화를 수행하기 위한 입력으로 사용됩니다. 앱 학습 및 빌드 중 성능을 위해 다양한 프로파일링 기능을 제어하는 추가 옵션을 설정할 수 있습니다. 기본 옵션으로 지정 된 **/GENPROFILE** 특히 대규모의 복잡 한 다중 스레드 앱에 대 한 가장 정확한 결과 제공 합니다. **/FASTGENPROFILE** 옵션은 다른 기본값을 사용 하 여 메모리 사용 및 저하 학습 속도 향상 시키기 합니다.

사용 하 여 빌드한 후 계측된 된 응용 프로그램을 실행할 때 캡처된 프로 파일링 정보 **/GENPROFILE** 의 **/FASTGENPROFILE**합니다. 지정 하는 경우이 정보가 캡처됩니다는 [/USEPROFILE](useprofile.md) 프로 파일링을 수행 하는 링커 옵션 단계 및는 최적화 된 빌드 단계를 안내 하는 데 사용 됩니다. 응용 프로그램을 학습 하는 방법에 대 한 자세한 내용 및 수집 된 데이터에 대 한 세부 정보에 대 한 참조 [프로필 기반 최적화](profile-guided-optimizations.md)합니다.

도 지정 해야 **/LTCG** 지정 하는 경우 **/GENPROFILE** 또는 **/FASTGENPROFILE**합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 입력은 **/GENPROFILE** 또는 **/FASTGENPROFILE** 옵션 및 인수에는 **추가 옵션** 상자입니다. 선택 **확인** 변경 내용을 저장 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[링커 옵션 설정](../../build/reference/setting-linker-options.md)<br/>
[링커 옵션](../../build/reference/linker-options.md)<br/>
[/LTCG(링크 타임 코드 생성)](../../build/reference/ltcg-link-time-code-generation.md)<br/>
