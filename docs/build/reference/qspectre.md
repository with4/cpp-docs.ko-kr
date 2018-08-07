---
title: /Qspectre | Microsoft Docs
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
ms.openlocfilehash: 6a74c6c7c2ee7aab175d7e136e5cf02a8d9f8bfc
ms.sourcegitcommit: bad2441d1930275ff506d44759d283d94cccd1c0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39375879"
---
# <a name="qspectre"></a>/Qspectre

특정 Spectre variant 1 보안 취약성을 완화 하기 위한 지침의 컴파일러 생성을 지정 합니다.

## <a name="syntax"></a>구문

> **/Qspectre**

## <a name="remarks"></a>설명

합니다 **/Qspectre** 옵션을 사용 하면 특정 완화 하기 위해 명령을 삽입 [스펙터 보안 취약점으로 인 한](https://spectreattack.com/spectre.pdf)합니다. 호출에 이러한 취약성 *투기적 실행 사이드 채널 공격*많은 운영 체제 및 Intel, AMD 프로세서를 포함 하 여 최신 프로세서에 영향을 줄 고 ARM입니다.

합니다 **/Qspectre** 옵션은 기본적으로 해제 되어 있습니다.

초기 릴리스에서는 **/Qspectre** 옵션 최적화 된 코드 에서만 작동 합니다. 최적화 옵션 중 하나를 사용 하 여 코드를 컴파일하려면 해야 (예를 들어 [/o1 또는/o2](o1-o2-minimize-size-maximize-speed.md) 있지만 [/Od](od-disable-debug.md)) 완화 적용 되도록 합니다. 마찬가지로, 사용 하는 코드를 검사할 [#pragma 최적화 ("stg", off)](../../preprocessor/optimize.md)합니다.

### <a name="applicability"></a>적용 가능성

트러스트 경계를 교차 하는 데이터에서 작동 하는 코드를 사용 하는 것이 좋습니다 경우는 **/Qspectre** 다시 빌드하고 다시 가능한 한 빨리이 문제를 완화 하기 위해 코드를 배포 하는 옵션입니다. 트러스트 경계를 교차 하는 데이터에서 작동 하는 코드의 예로 실행에 영향을 줄 수 있는 신뢰할 수 없는 입력을 로드 하는 코드, 원격 프로시저는 코드를 호출, 신뢰할 수 없는 입력 또는 파일을 구문 분석 또는 다른 로컬 간 프로세스를 사용 하 여 예를 들어, 통신 (IPC) 인터페이스입니다. 표준 샌드 박싱 기술 충분 하지 않을 수 있습니다. 에 샌드박스 코드 트러스트 경계를 넘어서지 않는 결정 하기 전에 신중 하 게 조사 해야 합니다.

### <a name="availability"></a>가용성

합니다 **/Qspectre** 옵션은 Visual Studio 2017 버전 15.5.5 및 2018 년 1 월 23 일 이후에 만든 모든 업데이트를 Microsoft Visual c + + 컴파일러 (MSVC)에서 사용할 수 있습니다.

모든 버전의 Visual Studio 2017 버전 15.5 및 모든 미리 보기의 Visual Studio 버전 15.6에는 이미는 문서화 되지 않은 옵션이 포함 되어 **/d2guardspecload**, 즉 해당 초기 동작 **/Qspectre**. 사용할 수 있습니다 **/d2guardspecload** 이러한 버전의 컴파일러에서 코드를 동일한 완화를 적용 합니다. 사용 하 여 빌드를 업데이트 하세요 **/Qspectre** ; 옵션을 지 원하는 컴파일러에서는 **/Qspectre** 컴파일러의 이후 버전에서 새 완화 옵션을 지원할 수도 있습니다.

### <a name="effect"></a>효과

합니다 **/Qspectre** 맴도 변형 1 범위 확인 바이패스를 완화 하기 위해 코드를 출력 하는 옵션 [CVE 2017-5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753)합니다. 잘못 된 코드 실행 장벽으로 작동 하는 명령 삽입 하 여 작동 합니다. 프로세서 추론을 완화 하기 위해 사용 되는 특정 지침에는 변경 될 수 있습니다 이후 버전의 컴파일러 및 프로세서 및 해당 마이크로 아키텍처에 따라 달라 집니다.

경우는 **/Qspectre** 옵션을 설정 하면 컴파일러가 투기적 실행 범위 검사를 건너뛸 수 있습니다 및 장벽 지침 삽입 위치 인스턴스를 식별 하려고 합니다. 컴파일러는 variant 1의 인스턴스를 식별 하기 위해 수행할 수 있는 분석이 제한은 두는 것이 반드시 합니다. 따라서 보장이 없습니다에서 variant 1의 모든 가능한 인스턴스는 계측 되지 않은 **/Qspectre**합니다.

### <a name="performance-impact"></a>성능에 미치는 영향

성능에 미치는 **/Qspectre** 몇 가지 매우 큰 코드 베이스에서 무시할 수 나타났습니다 보장을 아래 코드의 성능에 주는 없습니다 있지만 **/Qspectre** 그대로 유지 됩니다. 성능 옵션의 효과 확인 하는 코드 벤치 마크 해야 합니다. 사용 하 여 완화를 선택적으로 사용할 수는 성능이 중요 한 블록 또는 루프에서 필요 하지 않습니다를 알고 있는 경우는 [__declspec(spectre(nomitigation))](../../cpp/spectre.md) 지시문입니다. 이 지시문에서에서 사용할 수 없는 지 원하는 컴파일러는 **/d2guardspecload** 옵션입니다.

### <a name="required-libraries"></a>필요한 라이브러리

합니다 **/Qspectre** 컴파일러 옵션 스펙터 완화를 위해 구축 된 런타임 라이브러리의 버전을 암시적으로 연결 하는 코드를 생성 합니다. 이러한 라이브러리는 Visual Studio 설치 관리자를 사용 하 여 설치 해야 하는 선택적 구성 요소:

- VC + + 2017 버전 *version_number* (x86 및 x64) 스펙터 용 라이브러리
- Spectre Mitigations 포함 Visual C++ ATL(x86/x64)
- Spectre Mitigations 포함 x86/x64용 Visual C++ MFC

사용 하 여 코드를 작성 하는 경우 **/Qspectre** 이러한 라이브러리에는 없는 설치, 빌드 시스템 보고서 **경고 MSB8038: 스펙터 완화 설정 되어 있지만 스펙터 완화 된 라이브러리를 찾을 수 없습니다**합니다. MFC 또는 ATL 코드 빌드가 실패 하 고 링커와 같은 오류를 보고 하는 경우 **심각한 오류 LNK1104: 'oldnames.lib' 파일을 열 수 없습니다.**, 이러한 누락 된 라이브러리를 일으킬 수 있습니다.

### <a name="additional-information"></a>추가 정보

자세한 내용을 참조 하세요. 공식 [투기적 실행 사이드 채널 취약성을 완화 하기 위해 Microsoft 보안 공지 ADV180002, 지침](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002)합니다. 지침 Intel에서 제공 됩니다 [투기적 실행 쪽 채널 완화](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf), 및 ARM를 [캐시 추론 쪽 채널](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf)합니다. 스펙터와 멜트다운 완화 기능이 Windows 관련 개요를 참조 하세요 [스펙터와 멜트다운 완화 Windows 시스템 성능에 영향을 이해](https://cloudblogs.microsoft.com/microsoftsecure/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/) Microsoft 보안 블로그에서입니다. MSVC 완화에서 해결 된 스펙터 취약점의 개요를 보려면 [MSVC에 스펙터 완화](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc./) Visual c + + 팀 블로그.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)을 참조하세요.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 입력 된 **/Qspectre** 컴파일러 옵션을 **추가 옵션** 상자. 선택할 **확인** 에 변경 내용을 적용 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/Q 옵션(하위 수준 작업)](../../build/reference/q-options-low-level-operations.md)  
[컴파일러 옵션](../../build/reference/compiler-options.md)  
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)  
