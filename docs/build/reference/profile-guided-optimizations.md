---
title: 프로필 기반 최적화 | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- profile-guided optimizations
- optimization, profile-guided [C++]
ms.assetid: 2225c307-d3ae-42c1-8345-a5a959d132dc
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ca4c79fd46954d59a8fdd892fabbd53d4bc985f
ms.sourcegitcommit: ee7d74683af7631441c8c7f65ef5ceceaee4a5ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="profile-guided-optimizations"></a>프로필 기반 최적화

최적화 프로그램이 .exe 또는 .dll 파일의 테스트 실행 데이터를 사용하는 프로필 기반 최적화를 사용하면 출력 파일을 최적화할 수 있습니다. 데이터는 프로그램이 프로덕션 환경에서 수행될 가능성이 있는 방법을 나타냅니다.

프로필 기반 최적화는 x86 또는 x64 네이티브 대상 수만 있습니다. 프로필 기반 최적화 공용 언어 런타임에 실행할 출력 파일에 사용할 수 없는 경우 네이티브 및 관리 코드가 혼합된 된 어셈블리를 생성 하는 경우에 (사용 하 여는 **/clr** 컴파일러 옵션), 네이티브 코드 에서만 프로필 기반 최적화를 사용할 수 없습니다. IDE에서 설정 하는이 옵션으로 프로젝트를 빌드 하려는 경우 빌드 오류가 발생 합니다.

> [!NOTE]
> 프로 파일링 테스트 실행에서 수집 되는 정보 재정의 될 수 있는 효과에 지정 하는 경우 최적화 **/Ob**, **/Os**, 또는 **/Ot**합니다. 자세한 내용은 참조 [/Ob (인라인 함수 확장)](../../build/reference/ob-inline-function-expansion.md) 및 [/Os, /Ot (크기 우선 코드, 속도 우선 코드)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)합니다.

## <a name="steps-to-optimize-your-app"></a>응용 프로그램을 최적화 하는 단계

프로필 기반 최적화를 사용 하려면 응용 프로그램을 최적화 하기 위해 다음이 단계를 수행 합니다.

- 하나 이상의 소스 코드 파일이 있는 [/GL](../../build/reference/gl-whole-program-optimization.md)합니다.

   각 모듈을 사용 하 여 빌드한 **/GL** 런타임 동작을 캡처할 프로필 기반 최적화 테스트 실행 중 검사할 수 있습니다. 프로필 기반 최적화 빌드의 모든 모듈을 사용 하 여 컴파일할 필요가 없습니다 **/GL**합니다. 그러나 이러한 모듈에만 사용 하 여 컴파일된 **/GL** 계측 하 고 나중에 사용할 수 있는 프로필 기반 최적화 됩니다.

- 사용 하 여 연결 [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) 및 [/GENPROFILE 또는 /FASTGENPROFILE](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)합니다.

   모두 사용 하 여 **/LTCG** 및 **/GENPROFILE** 또는 **/FASTGENPROFILE** 계측된 된 응용 프로그램을 실행 하는 경우.pgd 파일을 만듭니다. 테스트 실행 데이터가 .pgd 파일에 추가된 후에는 다음 링크 단계(최적화된 이미지 만들기)에 대한 입력으로 사용할 수 있습니다. 지정 하는 경우 **/GENPROFILE**, 선택적으로 추가할 수는 **PGD =**_filename_ 인수를 기본값이 아닌 이름이 나.pgd 파일의 위치를 지정 합니다. 조합의 **/LTCG** 및 **/GENPROFILE** 또는 **/FASTGENPROFILE** 링커 옵션을 사용 되지 않는 대체 **/ltcg: pginstrument** 링커 옵션입니다.

- 응용 프로그램을 프로파일링합니다.

   프로 파일링 된 EXE 세션이 종료 하거나 프로 파일링된 된 DLL 언로드될 때마다는 *appname*! #.pgc 파일이 만들어집니다. .pgc 파일에는 특정 응용 프로그램 테스트 실행에 대한 정보가 포함됩니다. #은 다른 수에 따라 증가 하는 1부터 시작 하는 숫자로 *appname*! #.pgc 파일 디렉터리에 있습니다. 테스트 실행이 최적화하려는 시나리오를 나타내지 않는 경우 .pgc 파일을 삭제할 수 있습니다.

   테스트 실행 도중 현재 열려 있는.pgc 파일을 새.pgc 파일 만들기를 강제로 수는 [pgosweep](../../build/reference/pgosweep.md) 유틸리티 (예를 들어 경우에 테스트 시나리오의 끝 응용 프로그램 종료와 일치 하지 않는).

   응용 프로그램 수 PGO 함수를 호출도 간접적 [PgoAutoSweep](pgoautosweep.md),.pgc 파일으로 호출 지점 프로 파일 데이터를 캡처하려고 합니다. 이.pgc 파일에 캡처된 데이터가 적용 되는 코드 보다 세부적으로 제어를 제공할 수 있습니다. 이 함수를 사용 하는 방법의 예제를 보려면는 [PgoAutoSweep](pgoautosweep.md) 설명서입니다.

   기본적으로 계측 된 빌드를 만들 때 데이터 컬렉션은 빠르게 되지만 정확성이 떨어질 수는 스레드로부터 안전 모드에서 수행 됩니다. 사용 하 여는 **EXACT** 인수를 **/GENPROFILE** 또는 **/FASTGENPROFILE**,이 더 정확 하지만 느린는 스레드로부터 안전 모드에서 데이터 수집을 지정할 수 있습니다. 이 옵션은 사용 되지 않는 설정 하는 경우 사용할 수 있는 [PogoSafeMode](environment-variables-for-profile-guided-optimizations.md#pogosafemode) 환경 변수 또는 사용 되지 않는 **/POGOSAFEMODE** 링커 옵션을 계측 된 빌드를 만들 때.

- 사용 하 여 연결 **/LTCG** 및 **/USEPROFILE**합니다.

   둘 모두 사용 하는 **/LTCG** 및 [/USEPROFILE](useprofile.md) 링커 옵션을 최적화 된 이미지를 만듭니다. 이 단계에서는 입력으로 .pgd 파일을 사용합니다. 지정 하는 경우 **/USEPROFILE**, 선택적으로 추가할 수는 **PGD =**_filename_ 인수를 기본값이 아닌 이름이 나.pgd 파일의 위치를 지정 합니다. 사용 되지 않는 사용 하 여이 이름을 지정할 수도 있습니다 **/PGD** 링커 옵션입니다. 조합의 **/LTCG** 및 **/USEPROFILE** 사용 되지 않는 대체 **/ltcg: pgoptimize** 및 **/ltcg: pgupdate** 링커 옵션입니다.

최적화된 출력 파일을 만들고 나중에 보다 최적화된 이미지를 만드는 데 추가 프로파일링이 유용한지를 확인할 수 있습니다. 추가 테스트 실행을 닫을 수 있고 동일한를 사용 하 여 최신.pgd 파일로 최적화 된 이미지를 다시 계측 된 이미지와 해당.pgd 파일을 사용할 수 있으면 **/LTCG** 및 **/USEPROFILE** 링커 옵션 .

## <a name="optimizations-performed-by-pgo"></a>PGO에서 수행한 최적화

다음은 프로필 기반 최적화 목록입니다.

- **인라인 처리** 예를 들어 있으면 함수는 함수 B를 자주 호출 하 고 함수 B는 상대적으로 작은 경우 그런 다음 프로필 기반 최적화에서는 함수 A에서에서 B 인라인 함수

- **가상 호출 추론** -가상 호출 또는 함수 포인터를 통한 호출이 자주 특정 함수를 대상 하는 경우 프로필 기반 최적화 대상 함수를 직접 호출 조건부로 실행할를 삽입할 수 고 직접 호출은 인라인 처리할 수 있습니다.

- **레지스터 할당** -더 나은 레지스터 할당에서 프로필 데이터 결과로 최적화 합니다.

- **기본 블록 최적화** -기본 블록 최적화 시간적 페이지 (지역)의 동일한 집합에 지정된 된 프레임 내에서 실행 하는 기본 실행된 블록 수 있습니다. 따라서 사용되는 페이지 수가 최소화되므로 메모리 오버헤드도 최소홥니다.

- **크기/속도 최적화** -함수는 프로그램에서 자주 사용 되는 속도 대 한 최적화 될 수 있습니다.

- **함수 레이아웃** -호출 그래프를 기반으로 하며 호출자/호출 수신자 동작 프로 파일링 동일한 실행 경로 따르는 경향이 있는 함수가 동일한 섹션에 배치 됩니다.

- **조건부 분기 최적화** -값 프로브를 프로필 기반 최적화에서 switch 문에 지정된 된 값은 다른 값 보다 더 자주 사용 하는 경우를 확인할 수 있습니다.  그런 다음 switch 문에서 이 값을 끌어올 수 있습니다.  더 자주 true가 되는 블록에 따라 if 도는 else 블록이 먼저 배치되도록 최적화 프로그램에서 if/else의 순서를 지정할 수 있는 if/else 명령을 사용하여 동일한 작업을 수행할 수 있습니다.

- **데드 코드 분리** -프로 파일링 하는 동안 호출 되지 않은 코드를 섹션 집합의 끝에 추가 되는 특별 한 섹션으로 이동 합니다. 그러면 이 섹션이 자주 사용되는 페이지에서 효과적으로 유지됩니다.

- **EH 코드 분리** -프로필 기반 최적화는 예외가 예외 조건 에서만 발생 하는지를 확인할 수 있는 예외적으로 실행 되는 EH 코드 별도 섹션으로 이동할 종종 있습니다.

- **메모리 내장** -내장 함수가 자주 호출 되는지 확인할 수 있으면는 내장 함수의 확장을 더 잘 결정할 수 있습니다. 또한 내장 함수는 이동 또는 복사의 블록 크기에 따라 최적화할 수 있습니다.

Visual Studio 2013을 사용 하는 경우 사용할 수 있습니다는 자동화 된 [프로필 기반 최적화 플러그 인](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md) Visual c + +의 성능 및 진단 허브를 Visual Studio 내의 최적화 프로세스를 간소화 합니다. 이 플러그인은 Visual Studio의 이후 버전에서 사용할 수 없습니다.

## <a name="next-steps"></a>다음 단계

이러한 환경 변수, 함수 및 도구에 대해 자세히 알아보십시오 프로필 기반 최적화에 사용할 수 있습니다.

[프로필 기반 최적화 환경 변수](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>
테스트 시나리오의 런타임 동작을 지정 하려면 이러한 변수를 사용할 수 있습니다. 인해 사용 되지 않으면 새로운 링커 옵션 환경 변수에서 링커 옵션을 이동할 수 있도록 하려면이 옵션을 읽습니다.

[PgoAutoSweep](pgoautosweep.md)<br/>
세분화 된.pgc 파일 데이터 캡처 제어를 제공 하기 위해 앱에 추가할 수는 함수입니다.

[pgosweep](../../build/reference/pgosweep.md)<br/>
.Pgc 파일에 모든 프로필 데이터를 기록 하는 명령줄 유틸리티.pgc 파일을 닫고 새.pgc 파일을 엽니다.

[pgomgr](../../build/reference/pgomgr.md)<br/>
.Pgd 파일에 하나 이상의.pgc 파일에서 프로필 데이터를 추가 하는 명령줄 유틸리티입니다.

[방법: 병합 여러 개의 PGO 프로필을 단일 프로필로](../../build/reference/how-to-merge-multiple-pgo-profiles-into-a-single-profile.md) 몇 가지 **pgomgr** 사용 합니다.

## <a name="see-also"></a>참고자료

[C/C++ 빌드 도구](../../build/reference/c-cpp-build-tools.md)
