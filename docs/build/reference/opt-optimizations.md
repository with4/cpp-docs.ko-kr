---
title: /OPT (최적화) | Microsoft Docs
ms.custom: ''
ms.date: 05/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.OptimizeReferences
- /opt
- VC.Project.VCLinkerTool.OptimizeForWindows98
- VC.Project.VCLinkerTool.EnableCOMDATFolding
- VC.Project.VCLinkerTool.OptimizeFolding
- VC.Project.VCLinkerTool.FoldingIterations
- VC.Project.VCLinkerTool.OptimizeFoldingIterations
dev_langs:
- C++
helpviewer_keywords:
- LINK tool [C++], controlling optimizations
- -OPT linker option
- linker [C++], optimizations
- OPT linker option
- optimization, linker
- /OPT linker option
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc9f7f66b9bd0ee2c0da65d17eac33e1cbc8c316
ms.sourcegitcommit: da7b7533d1a4dc141cc0f09149e4e4196f2fe329
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
---
# <a name="opt-optimizations"></a>/OPT(최적화)

LINK가 빌드하는 동안 수행할 최적화를 제어합니다.

## <a name="syntax"></a>구문

> **/OPT:**{**REF** | **NOREF**}<br/>
> **/OPT:**{**ICF**[**=**_반복_] | **NOICF**}<br/>
> **/OPT:**{**LBR** | **NOLBR**}

## <a name="arguments"></a>인수

**REF** &AMP;#124; **NOREF**

**/Opt: ref** 함수와; 참조 되지 않는 데이터를 제거 합니다. **/Opt: noref** 함수 및 참조 되지 않는 데이터를 유지 합니다.

링크 참조 되지 않은 패키지에 포함 된 함수 및 데이터와 /opt: ref를 사용 하는 경우 제거 *Comdat*합니다. 이러한 최적화를 전이적 COMDAT 제거라고 합니다. **/opt: ref** 옵션 또한 증분 링크를 비활성화 합니다.

인라인 된 함수 및 클래스 선언 안에 정의 된 멤버 함수는 항상 Comdat입니다. 모든 개체 파일에 포함 된 함수를 사용 하 여 컴파일된 경우 Comdat로 설정 됩니다는 [/Gy](../../build/reference/gy-enable-function-level-linking.md) 옵션입니다. 배치 하려면 **const** Comdat에서 데이터를 선언 해야를 사용 하 여 `__declspec(selectany)`합니다. 제거 되거나 접기에 대 한 데이터를 지정 하는 방법에 대 한 정보를 참조 하십시오. [selectany](../../cpp/selectany.md)합니다.

기본적으로 **/opt: ref** 하지 않으면 링커에서 활성화 **/opt: noref** 또는 [/debug](../../build/reference/debug-generate-debug-info.md) 지정 됩니다. 이 기본값을 재정의 하 고 프로그램에 참조 되지 않은 Comdat를 유지 하려면 지정 **/opt: noref**합니다. 사용할 수는 [/include](../../build/reference/include-force-symbol-references.md) 특정 기호는 제거 되지 않도록 하려면 옵션입니다.

경우 [/debug](../../build/reference/debug-generate-debug-info.md) 지정 된에 대 한 기본 **/opt** 은 **NOREF**, 모든 함수가 이미지 중에 유지 됩니다. 이 기본값을 재정의 하 고 디버그 빌드를 최적화 하려면 지정 **/opt: ref**합니다. 이 프로그램 실행 파일의 크기를 줄일 수 있습니다 및 디버그에도 유용한 최적화 작성 될 수 있습니다. 지정 하는 것이 좋습니다 **/opt: noicf** 동일한 유지 하기 위해 디버그에서 함수 작성 합니다. 이렇게 하면 스택 추적을 읽고 다른 방식으로는 함께 정리될 함수에서 중단점을 쉽게 설정할 수 있습니다.

**ICF**\[**=**_반복_] &#124; **NOICF**

사용 하 여 **ICF**\[**=**_반복_]를 동일한 COMDAT를 정리 합니다. 중복 COMDAT는 링커 출력에서 제거될 수 있습니다. 선택적 *반복* 매개 변수는 중복 항목 기호를 트래버스하는 횟수를 지정 합니다. 기본 반복 횟수는 1입니다. 추가 반복에서 이전 반복의 정리를 통해 발견되지 않은 중복 항목을 더 많이 찾을 수도 있습니다.

기본적으로 **/opt: icf** 하지 않으면 링커에서 활성화 **/opt: noicf** 또는 [/debug](../../build/reference/debug-generate-debug-info.md) 지정 됩니다. 이 기본값을 재정의 않도록 Comdat 프로그램에서 정리 되 고, 지정 **/opt: noicf**합니다.

디버그 빌드를 명시적으로 지정 해야 **/opt: icf** COMDAT 정리 사용 하도록 합니다. 그러나 때문에 **/opt: icf** 동일한 데이터 또는 함수를 병합할 수, 스택 추적에 표시 되는 함수 이름을 변경할 수는 있습니다. 못할 수 있습니다도 특정 함수에 중단점을 설정 하거나 디버거에서 일부 데이터를 검사 하 고 예기치 않은 함수로 이동할 수 있습니다 때 코드를 단계별로 실행 하는 단일 있습니다. 코드의 동작은 동일 하지만, 디버거 프레젠테이션 매우 복잡할 수 있습니다. 따라서 권장 하지는 않습니다를 사용 하는 **/opt: icf** 디버그에서 더 작은 코드의 장점이 이러한 단점을 보다 되지를 빌드합니다.

> [!NOTE]
> 때문에 **/opt: icf** 서로 다른 함수 또는 읽기 전용 데이터 멤버에 할당 될 동일한 주소를 발생할 수 있습니다 (즉, **const** 변수를 사용 하 여 컴파일하면 **/Gy**), 함수 또는 읽기 전용 데이터 멤버의 고유 주소에 의존 하는 프로그램을 중단할 수 있습니다. 자세한 내용은 [/Gy(함수 수준 링크 사용)](../../build/reference/gy-enable-function-level-linking.md)를 참조하세요.

**LBR** &AMP;#124; **NOLBR**

**/OPT:LBR** 및 **/OPT:NOLBR** 옵션 ARM 이진 파일에만 적용 합니다. 특정 ARM 프로세서 분기 명령에는 제한된 범위가 있으므로 링커가 범위를 벗어난 주소로 점프하는 것을 감지하면 분기 명령의 대상 주소를 실제 대상을 목표로 하는 분기 명령이 포함된 코드 "아일랜드"의 주소로 대체합니다. 사용할 수 있습니다 **/OPT:LBR** 긴 분기 지침 검색 및 전체 코드 크기를 최소화 하기 위해 중간 코드 아일랜드 배치를 최적화할 수 있습니다. **/OPT:NOLBR** 최적화 없이 현재 발생에 긴 분기 명령에 대 한 코드 아일랜드를 생성 하도록 링커에 지시 합니다.

기본적으로는 **/OPT:LBR** 증분 링크를 사용 하지 않을 때 옵션이 설정 되어 있습니다. 비증분 링크 원하지만 긴 분기 최적화는 원하는 경우 지정 **/OPT:NOLBR**합니다. **/OPT:LBR** 증분 링크 옵션을 해제 합니다.

## <a name="remarks"></a>설명

기본적으로 링커 명령줄에서 사용 하는 경우 **ICF, /opt: ref LBR**합니다. 경우 **/debug** 지정, 기본값은 **NOICR, /opt: noref NOLBR**합니다.

**/opt** 최적화 일반적으로 이미지 크기를 줄이고 프로그램 속도 증가 합니다. 따라서 기본적으로 일반 정품 빌드에 대해 설정 된 이러한 향상 된이 기능에서 대용량 프로그램 상당한 수 있습니다.

링커 최적화가 추가 시간, 사용 하지만 최적화 된 코드 및 적은 디버그 정보를 처리 하 고 PDB에 작성 했을 때 더 많은 시간을 절약 링커를 수정할 수 있도록 더 적은 재배치 개이고 최종 이미지를 작게 만듭니다 시간을 절약할 수도. 최적화를 사용할 때 만들어질 수 있습니다 더 빠른 링크 타임에 전반적으로 때 분석 중에 작은 추가 비용 절감 링커 작은 이진 위로 이동할 시간 만큼 오프셋 보다 더 많을 수 있습니다.

**/opt** 인수 지정할 수 있습니다, 쉼표로 구분 합니다. 예를 들어 대신의 **/opt: ref /opt: noicf**를 지정할 수 있습니다 **/opt: ref, NOICF**합니다.

사용할 수는 [/verbose](../../build/reference/verbose-print-progress-messages.md) 로 제거 된 함수를 보려면 링커 옵션 **/opt: ref** 로 정리 된 함수 및 **/opt: icf**합니다.

**/opt** 인수를 사용 하 여 만든 프로젝트에 대해 설정 종종는 **새 프로젝트** 대화 상자는 Visual Studio IDE에 많으며 일반적으로 디버그에 대해 다른 값을가지고 및 릴리스 구성을 합니다. 값이 없는 프로젝트에서이 링커 옵션을 설정 하는 경우 명령줄에서 링커에서 사용 하는 기본 값과에서 다를 수 있는 프로젝트 기본값 발생할 수 있습니다.

### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 OPT:ICF 또는 OPT:REF 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **최적화** 속성 페이지.

1. 다음 속성 중 하나를 수정합니다.

   - **COMDAT 정리 사용**

   - **참조**

### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 OPT:LBR 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 에 옵션을 입력 **추가 옵션**:

   `/opt:lbr` 또는 `/opt:nolbr`

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A> 속성을 참조하십시오.

## <a name="see-also"></a>참고자료

- [링커 옵션 설정](../../build/reference/setting-linker-options.md)
- [링커 옵션](../../build/reference/linker-options.md)
