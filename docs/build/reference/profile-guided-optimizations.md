---
title: "프로필 기반 최적화 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- profile-guided optimizations
- optimization, profile-guided [C++]
ms.assetid: 2225c307-d3ae-42c1-8345-a5a959d132dc
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f2d72ddda460a88830f7f7692f4c9707fa3101a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="profile-guided-optimizations"></a>프로필 기반 최적화
최적화 프로그램이 .exe 또는 .dll 파일의 테스트 실행 데이터를 사용하는 프로필 기반 최적화를 사용하면 출력 파일을 최적화할 수 있습니다. 데이터는 프로그램이 프로덕션 환경에서 수행될 가능성이 있는 방법을 나타냅니다.  
  
 프로필 기반 최적화는 x86 또는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 네이티브 대상에서만 사용할 수 있습니다. 프로필 기반 최적화는 공용 언어 런타임에서 실행되는 출력 파일에 사용할 수 없습니다. 네이티브 및 관리 코드가 혼합된 된 어셈블리를 생성 하는 경우에 (사용 하 여 컴파일 **/clr**), 네이티브 코드 에서만 프로필 기반 최적화를 사용할 수 없습니다. IDE에서 이러한 옵션 설정을 사용하여 프로젝트를 빌드하려고 시도하면 빌드 오류가 발생합니다.  
  
> [!NOTE]
>  프로 파일링 테스트 실행에서 수집 되는 정보는 될 수 있는 효과에 지정 하는 경우 최적화를 재정의 합니다 **/Ob**, **/Os**, 또는 **/Ot**합니다. 자세한 내용은 참조 [/Ob (인라인 함수 확장)](../../build/reference/ob-inline-function-expansion.md) 및 [/Os, /Ot (크기 우선 코드, 속도 우선 코드)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)합니다.  
  
 성능 및 진단 허브에서 Visual C++ 플러그 인에 자동화된 프로필 기반 최적화를 사용하여 Visual Studio 내의 최적화 프로세스를 간소화하거나, Visual Studio 또는 명령줄에서 수동으로 최적화 단계를 수행할 수 있습니다. 플러그 인은 더 쉽게 사용할 수 있으므로 플러그 인을 권장합니다. 플러그 인을 가져와 앱 최적화 하기 위해 사용 하는 방법에 대 한 정보를 참조 하십시오. [프로필 기반 최적화 플러그 인](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)합니다.  
  
 프로필 기반 최적화 플러그 인과 수동 프로필 기반 최적화 모두 다음 단계에 따라 앱을 최적화합니다.  
  
-   하나 이상의 소스 코드 파일이 있는 [/GL](../../build/reference/gl-whole-program-optimization.md)합니다.  
  
     프로필 기반 최적화 테스트 실행 중 /GL로 빌드된 각 모듈을 검사하여 런타임 동작을 캡처할 수 있습니다. 프로필 기반 최적화 빌드의 모든 모듈을 /GL로 컴파일할 필요가 없습니다. 그러나 /GL을 사용하여 컴파일한 모듈만 계측되어 나중에 프로필 기반 최적화에 사용할 수 있습니다.  
  
-   사용 하 여 연결 [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) 및 [/GENPROFILE](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)합니다.  
  
     /LTCG 및 /GENPROFILE 둘 다 사용 하는 빈.pgd 파일을 만듭니다. 테스트 실행 데이터가 .pgd 파일에 추가된 후에는 다음 링크 단계(최적화된 이미지 만들기)에 대한 입력으로 사용할 수 있습니다. /GENPROFILE를 지정 하는 경우 필요에 따라 추가한: PGD =`filename` 기본값이 아닌 이름이 나.pgd 파일의 위치를 지정할 수 있습니다.  
  
-   응용 프로그램을 프로파일링합니다.  
  
     프로 파일링 된 EXE 세션이 종료 하거나 프로 파일링된 된 DLL 언로드될 때마다는 *appname*! #.pgc 파일이 만들어집니다. .pgc 파일에는 특정 응용 프로그램 테스트 실행에 대한 정보가 포함됩니다. #은 다른 수에 따라 증가 하는 1부터 시작 하는 숫자로 *appname*! #.pgc 파일 디렉터리에 있습니다. 테스트 실행이 최적화하려는 시나리오를 나타내지 않는 경우 .pgc 파일을 삭제할 수 있습니다.  
  
     테스트 실행 도중 현재 열려 있는.pgc 파일을 새.pgc 파일 만들기를 강제로 수는 [pgosweep](../../build/reference/pgosweep.md) 유틸리티 (예를 들어 경우에 테스트 시나리오의 끝 응용 프로그램 종료와 일치 하지 않는).  
  
     응용 프로그램을 프로파일링하는 경우 `PogoSafeMode` 옵션을 사용할 수 있습니다. 이 옵션을 사용하면 응용 프로그램을 안전 모드로 프로파일링할지 빠른 모드로 프로파일링할지를 지정할 수 있습니다. 이러한 모드에 대 한 자세한 내용은 참조 [PogoSafeMode](../../build/reference/pogosafemode.md)합니다.  
  
-   /LTCG 및 /USEPROFILE를 사용 하 여 연결 합니다.  
  
     /LTCG 및 /USEPROFILE 둘 다 사용 하 여 최적화 된 이미지를 만듭니다. 이 단계에서는 입력으로 .pgd 파일을 사용합니다. /USEPROFILE를 지정할 때는 추가할 수도 있습니다: PGD =`filename` 기본값이 아닌 이름이 나.pgd 파일의 위치를 지정할 수 있습니다. 자세한 내용은 참조 [/LTCG](../../build/reference/ltcg-link-time-code-generation.md)합니다.  
  
 최적화된 출력 파일을 만들고 나중에 보다 최적화된 이미지를 만드는 데 추가 프로파일링이 유용한지를 확인할 수 있습니다. 계측된 이미지와 해당 .pgd 파일을 사용할 수 있는 경우 추가 테스트 실행을 수행하고 최신 .pgd 파일로 최적화된 이미지를 다시 작성할 수 있습니다.  
  
 다음은 프로필 기반 최적화 목록입니다.  
  
-   **인라인 처리** 예를 들어 있으면 함수는 함수 B를 자주 호출 하 고 함수 B는 상대적으로 작은 경우 그런 다음 프로필 기반 최적화에서는 함수 A에서에서 B 인라인 함수  
  
-   **가상 호출 추론** -가상 호출 또는 함수 포인터를 통한 호출이 자주 특정 함수를 대상 하는 경우 프로필 기반 최적화 대상 함수를 직접 호출 조건부로 실행할를 삽입할 수 고 직접 호출은 인라인 처리할 수 있습니다.  
  
-   **레지스터 할당** -더 나은 레지스터 할당에서 프로필 데이터 결과로 최적화 합니다.  
  
-   **기본 블록 최적화** -기본 블록 최적화 시간적 페이지 (지역)의 동일한 집합에 지정된 된 프레임 내에서 실행 하는 기본 실행된 블록 수 있습니다. 따라서 사용되는 페이지 수가 최소화되므로 메모리 오버헤드도 최소홥니다.  
  
-   **크기/속도 최적화** -함수는 프로그램에서 자주 사용 되는 속도 대 한 최적화 될 수 있습니다.  
  
-   **함수 레이아웃** -호출 그래프를 기반으로 하며 호출자/호출 수신자 동작 프로 파일링 동일한 실행 경로 따르는 경향이 있는 함수가 동일한 섹션에 배치 됩니다.  
  
-   **조건부 분기 최적화** -값 프로브를 프로필 기반 최적화에서 switch 문에 지정된 된 값은 다른 값 보다 더 자주 사용 하는 경우를 확인할 수 있습니다.  그런 다음 switch 문에서 이 값을 끌어올 수 있습니다.  더 자주 true가 되는 블록에 따라 if 도는 else 블록이 먼저 배치되도록 최적화 프로그램에서 if/else의 순서를 지정할 수 있는 if/else 명령을 사용하여 동일한 작업을 수행할 수 있습니다.  
  
-   **데드 코드 분리** -프로 파일링 하는 동안 호출 되지 않은 코드를 섹션 집합의 끝에 추가 되는 특별 한 섹션으로 이동 합니다. 그러면 이 섹션이 자주 사용되는 페이지에서 효과적으로 유지됩니다.  
  
-   **EH 코드 분리** -프로필 기반 최적화는 예외가 예외 조건 에서만 발생 하는지를 확인할 수 있는 예외적으로 실행 되는 EH 코드 별도 섹션으로 이동할 종종 있습니다.  
  
-   **메모리 내장** -내장 함수가 자주 호출 되는지 확인할 수 있으면는 내장 함수의 확장을 더 잘 결정할 수 있습니다. 또한 내장 함수는 이동 또는 복사의 블록 크기에 따라 최적화할 수 있습니다.  
  
 IDE에서 수동 최적화 수행에 또는 명령줄에 자세한 내용은 참조 [프로필 기반 최적화 플러그 인](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [프로필 기반 최적화 플러그 인](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)  
  
 [수동 프로필 기반 최적화 도구](../../build/reference/tools-for-manual-profile-guided-optimization.md)  
  
 [방법: 여러 개의 PGO 프로필을 단일 프로필로 병합](../../build/reference/how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)  
  
## <a name="see-also"></a>참고 항목  
 [ 빌드 도구](../../build/reference/c-cpp-build-tools.md)