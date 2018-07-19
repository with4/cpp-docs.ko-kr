---
title: / Qspectre | Microsoft Docs
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- /Qspectre
helpviewer_keywords:
- /Qspectre
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d87850ae5413ccf876eb4d4b44b34e34527ef9a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379421"
---
# <a name="qspectre"></a>/ Qspectre

특정 유령 variant 1 보안 취약점을 완화 하기 위한 지침의 컴파일러 생성을 지정 합니다.

## <a name="syntax"></a>구문

> **/Qspectre**

## <a name="remarks"></a>설명

**/Qspectre** 옵션을 사용 하면 특정을 완화 하기 위해 명령을 삽입 [유령 보안 취약점](https://spectreattack.com/spectre.pdf)합니다. 호출 하는 이러한 취약점을 *추론 실행 사이드 채널 공격*많은 운영 체제 및의 Intel, AMD 프로세서를 포함 하는 최신 프로세서에 영향을, 및 ARM 합니다.

**/Qspectre** 옵션은 기본적으로 해제 되어 있습니다.

초기 릴리스에서는 **/Qspectre** 옵션에 최적화 된 코드에만 작동 합니다. 최적화 옵션 중 하나를 사용 하 여 코드를 컴파일할 수 있는지 확인 해야 (예를 들어 [/O1 또는 /O2](o1-o2-minimize-size-maximize-speed.md) 아닌 [/Od](od-disable-debug.md)) 완화 적용 되도록 합니다. 마찬가지로, 사용 하는 코드를 검사 [#pragma 최적화 ("stg", off)](../../preprocessor/optimize.md)합니다.

### <a name="applicability"></a>적용 가능성

트러스트 경계를 교차 하는 데이터에서 작동 하는 코드 경우 다음을 사용 하는 것이 좋습니다는 **/Qspectre** 다시 작성 하 고 가능한 한 빨리이 문제를 완화 하기 위해 코드를 다시 배포 하는 옵션입니다. 원격 프로시저 하는 코드를 호출, 신뢰할 수 없는 입력 또는 파일을 구문 분석 하거나 다른 지역 간 프로세스를 사용 하 여 예를 들어, 트러스트 경계를 교차 하는 데이터에서 작동 하는 코드의 예로 실행에 영향을 줄 수 있는 신뢰할 수 없는 입력을 로드 하는 코드 통신 (IPC) 인터페이스입니다. 표준 샌드 박싱 기술을 충분할 수 있습니다. 프로그램 샌드박스 코드 트러스트 경계를 교차 하지 않으며 결정 하기 전에 신중 하 게 조사 해야 합니다.

### <a name="availability"></a>가용성

**/Qspectre** 옵션은 Visual Studio 2017 버전 15.5.5 및 2018 년 1 월 23, 이후에 만든 모든 업데이트를 Microsoft Visual c + + 컴파일러 (MSVC)에서 사용할 수 있습니다.

모든 버전의 Visual Studio 2017 버전 15.5 되 고 모든 미리 보기의 Visual Studio 버전 15.6에는 이미는 문서화 되지 않은 옵션이 포함 되어 **/d2guardspecload**, 즉 해당 키의 초기 동작과 **/Qspectre**. 사용할 수 있습니다 **/d2guardspecload** 동일한 완화 이러한 버전의 컴파일러에서 코드를 적용할 수 있습니다. 사용 하도록 빌드를 업데이트 하십시오 **/Qspectre** ; 옵션을 지 원하는 컴파일러에서는 **/Qspectre** 컴파일러의 이후 버전에서 새 완화 옵션을 지원할 수도 있습니다.

### <a name="effect"></a>효과

**/Qspectre** 맴 variant 1, 범위 확인 바이패스를 완화 하기 위해 코드를 출력 하는 옵션 [CVE-2017-5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753)합니다. 잘못 된 코드 실행 장벽으로 작동 하는 지침으로 삽입 하 여 작동 합니다. 프로세서 추론을 완화 하기 위해 사용 되는 특정 지침 프로세서와 해당 마이크로 아키텍처에 따라 달라 집니다 및 변경 될 수 있습니다 이후 버전의 컴파일러입니다.

경우는 **/Qspectre** 옵션을 설정 하면 컴파일러에서 추론 실행 범위 검사를 바이패스할 수 있습니다 및 장벽 설명을 삽입 위치 인스턴스를 식별 하려고 합니다. 컴파일러 variant 1의 인스턴스를 식별 하기 위해 수행할 수 있는 분석이 제한은 하는 것이 유용 합니다. 따라서 보장이 없습니다 variant 1의 모든 가능한 인스턴스는 아래에서 계측 **/Qspectre**합니다.

### <a name="performance-impact"></a>성능에 미치는 영향

성능 영향 **/Qspectre** 여러 매우 큰 코드 베이스에서 무시할 수 나타났습니다 있지만 보장 되지 아래 코드의 성능에 주는 **/Qspectre** 그대로 유지 됩니다. 성능에 대 한 옵션을 확인 하는 코드 벤치 마크 해야 합니다. 사용 하 여 완화를 선택적으로 사용할 수는 성능이 중요 한 블록 또는 루프에서 완화 필요 하지 않은 알고 있는 경우는 [__declspec(spectre(nomitigation))](../../cpp/spectre.md) 지시문입니다. 이 지시문만 지 원하는 컴파일러에서 사용할 수 없는 **/d2guardspecload** 옵션입니다.

### <a name="additional-information"></a>추가 정보

자세한 내용을 참조 하십시오. 공식 [추론 실행 사이드 채널 취약성을 완화 하기 위해 Microsoft 보안 권고 ADV180002, 지침](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002)합니다. 제공 되는 지침은 인텔의 [잘못 된 실행 측면 채널 완화](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf), 및 ARM [캐시 추론 쪽 채널](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf)합니다. Windows 관련 유령 및 Meltdown 완화 기능의 개요를 참조 하십시오. [유령 및 Meltdown 완화 방식이 Windows 시스템의 성능 영향을 이해](https://cloudblogs.microsoft.com/microsoftsecure/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/) Microsoft 보안 블로그. MSVC 완화에서 해결 된 유령 취약점의 개요를 참조 하십시오. [MSVC의 유령 완화](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc./) Visual c + + 팀 블로그.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 입력은 **/Qspectre** 컴파일러 옵션에는 **추가 옵션** 상자입니다. 선택 **확인** 에 변경 내용을 적용 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/Q 옵션(하위 수준 작업)](../../build/reference/q-options-low-level-operations.md)  
[컴파일러 옵션](../../build/reference/compiler-options.md)  
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)  
