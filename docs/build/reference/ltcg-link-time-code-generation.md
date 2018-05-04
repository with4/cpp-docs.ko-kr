---
title: /LTCG (링크 타임 코드 생성) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.LinkTimeCodeGeneration
- VC.Project.VCConfiguration.WholeProgramOptimization
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
- /ltcg
- VC.Project.VCCLCompilerTool.WholeProgramOptimization
dev_langs:
- C++
helpviewer_keywords:
- link-time code generation in C++ linker
- /LTCG linker option
- -LTCG linker option
- LTCG linker option
ms.assetid: 788c6f52-fdb8-40c2-90af-4026ea2cf2e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d45f5b56dfb84d56bcba8ad0652ed86a8fb5223
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltcg-link-time-code-generation"></a>/LTCG(링크 타임 코드 생성)

사용 하 여 **/LTCG** 전체 프로그램 최적화를 수행 하거나 프로필 기반 최적화 (PGO) 계측, 교육, 수행 만들고 프로필 기반 액세스에 최적화 된 빌드입니다.

## <a name="syntax"></a>구문

> **/LTCG**[**:**{**INCREMENTAL**|**NOSTATUS**|**STATUS**|**OFF**}]<br/>

이러한 옵션은 Visual Studio 2015부터 사용 되지 않습니다.

> **/LTCG:**{**PGINSTRUMENT**|**PGOPTIMIZE**|**PGUPDATE**}<br/>

### <a name="arguments"></a>인수

**증분** (선택 사항)<br/>
링커가 전체 프로젝트 대신 편집의 영향을 받는 파일 집합에 전체 프로그램 최적화 또는 링크 타임 코드 생성 LTCG ()를만 적용 되도록 지정 합니다. 기본적으로이 플래그는 설정 하지 때 **/LTCG** 를 지정 하 고 전체 프로그램 최적화를 사용 하 여 전체 프로젝트가 연결 됩니다.

**NOSTATUS** &#124; **상태** (선택 사항)<br/>
완료된 링크 비율을 표시하는 진행률 표시기가 링커에 표시되는지 여부를 지정합니다. 기본적으로 이 상태 정보는 표시되지 않습니다.

**OFF** (선택 사항)<br/>
링크 타임 코드 생성을 사용 하지 않도록 설정 합니다. 이 동작은 경우와 동일 하 게 **/LTCG** 명령줄에서 지정 하지 않으면 합니다.

**PGINSTRUMENT** (선택 사항)<br/>
이 옵션은 Visual Studio 2015부터 사용 되지 않습니다. 대신를 사용 하 여 **/LTCG** 및 [/GENPROFILE 또는 /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) 를 프로필 기반 최적화에 대 한 계측된 된 빌드를 생성 합니다. 계측된 실행으로부터 수집되는 데이터는 최적화된 이미지를 만드는 데 사용됩니다. 자세한 내용은 참조 [프로필 기반 최적화](profile-guided-optimizations.md)합니다. 이 옵션의 약식 형태는 **/ltcg: pgi**합니다.

**PGOPTIMIZE** (선택 사항)<br/>
이 옵션은 Visual Studio 2015부터 사용 되지 않습니다. 대신를 사용 하 여 **/LTCG** 및 [/USEPROFILE](useprofile.md) 최적화 된 이미지를 작성 합니다. 자세한 내용은 참조 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)합니다. 이 옵션의 약식 형태는 **/ltcg: pgo**합니다.

**PGUPDATE** (선택 사항)<br/>
이 옵션은 Visual Studio 2015부터 사용 되지 않습니다. 대신를 사용 하 여 **/LTCG** 및 **/USEPROFILE** 최적화 된 이미지를 다시 작성 해야 합니다. 자세한 내용은 참조 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)합니다. 이 옵션의 약식 형태는 **/LTCG:PGU**합니다.

## <a name="remarks"></a>설명

**/LTCG** 옵션 링커가 컴파일러를 호출 하 고 전체 프로그램 최적화를 수행 합니다. 프로필 기반 최적화를 수행할 수도 있습니다. 자세한 내용은 참조 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)합니다.

다음과 같은 예외가 PGO 조합에 링커 옵션을 추가할 수 없습니다 **/LTCG** 및 **/USEPROFILE** 이전 PGO 초기화 조합에 지정 되지 않은  **/LTCG** 및 **/GENPROFILE** 옵션:

- [/BASE](../../build/reference/base-base-address.md)

- [/FIXED](../../build/reference/fixed-fixed-base-address.md)

- **/LTCG**

- [/MAP](../../build/reference/map-generate-mapfile.md)

- [/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)

- [/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)

- [/OUT](../../build/reference/out-output-file-name.md)

- [/PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)

- [/PDB](../../build/reference/pdb-use-program-database.md)

- [/PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)

- [/STUB](../../build/reference/stub-ms-dos-stub-file-name.md)

- [/VERBOSE](../../build/reference/verbose-print-progress-messages.md)

와 함께 지정 된 링커 옵션은 **/LTCG** 및 **/GENPROFILE** PGO 초기화 하려면 옵션을 사용 하 여 구성한 지정할 필요가 없습니다 **/LTCG** 및 **/USEPROFILE**; 암시적입니다.

이 문서의 나머지 부분에서는 **/LTCG** 링크 타임 코드 생성의 관점에서 합니다.

**/LTCG** 없이 포함 된 [/GL](../../build/reference/gl-whole-program-optimization.md)합니다.

사용 하 여 컴파일된 모듈이 전달 된 경우 링커가 링크 타임 코드 생성을 호출 **/GL** 또는 MSIL 모듈 (참조 [링커 입력 파일로.netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)). 명시적으로 지정 하지 않으면 **/LTCG** 전달 하는 경우 **/GL** MSIL 모듈을 링커에 링커에서 결국이 검색 하 고 사용 하 여 링크를 다시 시작 또는 **/LTCG**합니다. 명시적으로 지정 **/LTCG** 전달 하는 경우 **/GL** 및 MSIL 모듈을 링커에 가능한 가장 빠른 빌드 성능을 합니다.

사용 하 여 성능을 더욱 향상 시키려면 **/LTCG: 증분**합니다. 이 옵션은 전체 프로젝트 대신 소스 파일 변경의 영향을 받는 파일 집합만 다시 최적화하도록 링커에 지시합니다. 이렇게 하면 필요한 링크 타임을 상당히 줄일 수 있습니다. 증분 링크 동일한 옵션이 아닙니다.

**/LTCG** 는 [/INCREMENTAL](../../build/reference/incremental-link-incrementally.md)를 참조하세요.

때 **/LTCG** 하는 데 사용 하 여 컴파일된 모듈 링크 [/Og](../../build/reference/og-global-optimizations.md), [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), 또는 [/Ox](../../build/reference/ox-full-optimization.md), 다음과 같은 최적화를 수행 합니다.

- 모듈 간 인라인 처리

- 프로시저 간 레지스터 할당(64비트 운영 체제만 해당)

- 사용자 지정 호출 규칙(x86만 해당)

- 작은 TLS 치환(x86만 해당)

- 스택 이중 맞춤(x86만 해당)

- 향상된 메모리 명확성(전역 변수 및 입력 매개 변수에 대한 보다 효율적인 간섭 정보)

> [!NOTE]
> 링커는 각 함수를 컴파일하는 데 사용된 최적화를 확인하고 링크 타임에 동일한 최적화를 적용합니다.

사용 하 여 **/LTCG** 및 **/Ogt** 하면 이중 할당 최적화 합니다.

경우 **/LTCG** 및 **/Ogs** 지정, 이중 할당이 수행 되지 않습니다. 크기에 대 한 일부 함수를 사용 하 여 속도 대 한 대부분의 응용 프로그램의 함수는 컴파일한 (사용 하 여 예를 들어는 [최적화](../../preprocessor/optimize.md) pragma), 함수를 호출 하는 경우 크기에 맞게 최적화 된 컴파일러 더블-정렬 이중 할당을 필요로 하는 함수입니다.

컴파일러가 함수의 모든 호출 사이트를 식별할 수 있는 경우 컴파일러는 함수의 명시적 호출 규칙 한정자를 무시하고 함수의 호출 규칙을 최적화하려고 합니다.

- 레지스터의 매개 변수 전달

- 맞춤을 위해 매개 변수 다시 정렬

- 사용하지 않는 매개 변수 제거

함수 포인터를 통해 호출 하는 함수 또는 함수를 사용 하 여 컴파일된 모듈 외부에서 호출 하는 경우 **/GL**, 컴파일러는 함수의 호출 규칙을 최적화 하려고 시도 하지 않습니다.

> [!NOTE]
> 사용 하는 경우 **/LTCG** 다시 정의 `mainCRTStartup`, 응용 프로그램은 전역 개체가 초기화 되기 전에 실행 되는 사용자 코드와 관련 된 예기치 않은 동작이 있을 수 있습니다. 이 문제를 해결 하는 방법은 세 가지가: 다시 정의 하지 `mainCRTStartup`를 포함 하는 파일을 컴파일하지 않거나 `mainCRTStartup` 를 사용 하 여 **/LTCG**, 또는 전역 변수 및 개체를 정적으로 초기화 합니다.

### <a name="ltcg-and-msil-modules"></a>/LTCG 및 MSIL 모듈

[/GL](../../build/reference/gl-whole-program-optimization.md) 및 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 을 사용해서 컴파일된 모듈은 **/LTCG** 가 지정된 경우 링커에 대한 입력으로 사용될 수 있습니다.

- **/LTCG** 네이티브 개체 파일을 허용할 수 있으며 혼합 네이티브/관리 개체 파일 (사용 하 여 컴파일된 **/clr**). **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.

- **/Ltcg: pgi** 를 사용 하 여 컴파일된 네이티브 모듈을 받아들이지 않는 **/GL** 및 **/clr**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **일반** 속성 페이지.

1. **전체 프로그램 최적화** 속성을 수정합니다.

적용할 수 있습니다 **/LTCG** 선택 하 여 특정 빌드에 **빌드** > **프로필 기반 최적화** 프로필 중 하나를 선택 하거나 메뉴 모음에서 프로젝트에 대 한 바로 가기 메뉴에서 최적화 옵션을 안내 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[링커 옵션 설정](../../build/reference/setting-linker-options.md)<br/>
[링커 옵션](../../build/reference/linker-options.md)<br/>
