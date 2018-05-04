---
title: -(최적화)를 선택 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: f8ac107f8a5654601f0c974f82fa83ae6aa83518
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="opt-optimizations"></a>/OPT(최적화)
LINK가 빌드하는 동안 수행할 최적화를 제어합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/OPT:{REF | NOREF}  
/OPT:{ICF[=iterations] | NOICF}  
/OPT:{LBR | NOLBR}  
```  
  
## <a name="arguments"></a>인수  
 **REF** &AMP;#124; **NOREF**  
 **/Opt: ref** 함수와; 참조 되지 않는 데이터를 제거 합니다. **/Opt: noref** 함수 및 참조 되지 않는 데이터를 유지 합니다.  
  
 /Opt: ref를 사용 하는 링크 참조 되지 않은 패키지에 포함 된 함수 및 데이터를 제거 합니다. 개체에 포함 패키지 함수 및 데이터 (Comdat)를 사용 하 여 컴파일된는 [/Gy](../../build/reference/gy-enable-function-level-linking.md) 옵션입니다. 이러한 최적화를 전이적 COMDAT 제거라고 합니다. 기본적으로 **/opt: ref** 디버그가 아닌 빌드에서 사용 하도록 설정 합니다. 이 기본값을 재정의 하 고 프로그램에 참조 되지 않은 Comdat를 유지 하려면 지정 **/opt: noref**합니다. 사용할 수는 [/include](../../build/reference/include-force-symbol-references.md) 특정 기호는 제거 되지 않도록 하려면 옵션입니다.  
  
 때 **/opt: ref** 명시적으로 또는 제한 된 형태의 기본적으로 사용 되는 **/opt: icf** 활성화 되어 동일한 함수만 정리 하는 합니다. 원하는 경우 **/opt: ref** 아닌 **/opt: icf**를 지정 해야 **/opt: ref, NOICF** 또는 **/opt: noicf**합니다.  
  
 경우 [/debug](../../build/reference/debug-generate-debug-info.md) 지정 된에 대 한 기본 **/opt** 은 **NOREF**, 모든 함수가 이미지 중에 유지 됩니다. 이 기본값을 재정의 하 고 디버깅 빌드를 최적화 하려면 지정 **/opt: ref**합니다. 때문에 **/opt: ref** 의미 **/opt: icf**를 지정 하는 것이 좋습니다 **/opt: noicf** 에 디버깅 빌드에서 동일한 함수를 유지 하기 위해 합니다. 이렇게 하면 스택 추적을 읽고 다른 방식으로는 함께 정리될 함수에서 중단점을 쉽게 설정할 수 있습니다. **/opt: ref** 증분 링크 옵션을 해제 합니다.  
  
 명시적으로 표시 해야 `const` 데이터 COMDAT로; 사용 하 여 [__declspec (selectany)](../../cpp/selectany.md)합니다.  
  
 지정 **/opt: icf** 사용 하도록 설정 하지 않습니다는 **/opt: ref** 옵션입니다.  
  
 **ICF [=** `iterations` **] &AMP;#124; NOICF**  
 사용 하 여 **/opt: icf [=**`iterations`**]** 를 동일한 COMDAT를 정리 합니다. 중복 COMDAT는 링커 출력에서 제거될 수 있습니다. 선택적인 `iterations` 매개 변수는 중복을 위해 기호를 트래버스하는 횟수를 지정합니다. 기본 반복 횟수는 2입니다. 추가 반복에서 이전 반복의 정리를 통해 발견되지 않은 중복 항목을 더 많이 찾을 수도 있습니다.  
  
 링커는 다르게 작동 때 **/opt: ref** 지정-및 **ICF** 기본적으로 적용 되-때 보다 **ICF, /opt: ref** 명시적으로 지정 됩니다. 형식의 **ICF** 으로 사용할 수 있는 **/opt: ref** 단독 읽기 전용 데이터를 정리 하지 않습니다-여기에.rdata,.pdata 및.xdata 포함 됩니다. 따라서 이러한 모듈의 함수에 읽기 전용 데이터 종속성이 높아지기 때문에(예: .pdata 및 .xdata) [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]에 대해 이미지가 생성될 때 정리되는 함수가 적어집니다. 완전 하 게 하려면 **ICF** 정리 동작을 명시적으로 지정 **/opt: icf**합니다.  
  
 Comdat에 함수를 배치 하려면 사용 하는 **/Gy** 컴파일러 옵션을 `const` 선언 하면 데이터를 `__declspec(selectany)`합니다. 정리할 데이터를 지정 하는 방법에 대 한 정보를 참조 하십시오. [selectany](../../cpp/selectany.md)합니다.  
  
 기본적으로 **ICF** 가 설정 되 면 **REF** 켜져 있습니다. 이 기본값을 재정의 하려면이 경우 **REF** 은 지정한를 사용 하 여 **NOICF**합니다. 때 **/opt: ref** 명시적으로 지정 해야 디버그 빌드에서 지정 하지 않으면 **/opt: icf** COMDAT 정리 사용 하도록 합니다. 그러나 때문에 **/opt: icf** 동일한 데이터 또는 함수를 병합할 수, 스택 추적에 표시 되는 함수 이름을 변경할 수는 있습니다. 특정 함수에 중단점을 설정하거나 디버거에서 일부 데이터를 검사할 수 없게 되고 코드를 단일 단계로 처리할 때 예기치 않은 함수로 이동할 수도 있습니다. 따라서 권장 하지는 않습니다를 사용 하는 **/opt: icf** 디버그에서 더 작은 코드의 장점이 이러한 단점을 보다 되지를 빌드합니다.  
  
> [!NOTE]
>  때문에 **/opt: icf** 서로 다른 함수 또는 읽기 전용 데이터 멤버에 할당 될 동일한 주소를 발생할 수 있습니다 (`const` 변수를 사용 하 여 컴파일된 **/Gy**), 의존 하는 프로그램을 중단할 수 있습니다 함수 또는 읽기 전용 데이터 멤버에 대해 고유한 주소입니다. 자세한 내용은 [/Gy(함수 수준 링크 사용)](../../build/reference/gy-enable-function-level-linking.md)를 참조하세요.  
  
 **LBR** &AMP;#124; **NOLBR**  
 **/OPT:LBR** 및 **/OPT:NOLBR** 옵션 ARM 이진 파일에만 적용 합니다. 특정 ARM 프로세서 분기 명령에는 제한된 범위가 있으므로 링커가 범위를 벗어난 주소로 점프하는 것을 감지하면 분기 명령의 대상 주소를 실제 대상을 목표로 하는 분기 명령이 포함된 코드 "아일랜드"의 주소로 대체합니다. 사용할 수 있습니다 **/OPT:LBR** 긴 분기 지침 검색 및 전체 코드 크기를 최소화 하기 위해 중간 코드 아일랜드 배치를 최적화할 수 있습니다. **/OPT:NOLBR** 최적화 없이 현재 발생에 긴 분기 명령에 대 한 코드 아일랜드를 생성 하도록 링커에 지시 합니다.  
  
 기본적으로는 **/OPT:LBR** 증분 링크를 사용 하지 않을 때 옵션이 설정 되어 있습니다. 비증분 링크 원하지만 긴 분기 최적화는 원하는 경우 지정 **/OPT:NOLBR**합니다. **/OPT:LBR** 증분 링크 옵션을 해제 합니다.  
  
## <a name="remarks"></a>설명  
 최적화하면 일반적으로 링크 시간이 늘어나는 대신 이미지 크기가 줄어들고 프로그램 속도는 향상됩니다.  
  
 사용할 수는 [/verbose](../../build/reference/verbose-print-progress-messages.md) 로 제거 된 함수를 보려면 옵션 **/opt: ref** 로 정리 된 함수 및 **/opt: icf**합니다.  
  
### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 OPT:ICF 또는 OPT:REF 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  왼쪽된 창에서 확장 **구성 속성**, **링커**, **최적화**합니다.  
  
3.  다음 속성 중 하나를 수정합니다.  
  
    -   **COMDAT 정리 사용**  
  
    -   **참조**  
  
### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 OPT:LBR 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **링커** 폴더입니다.  
  
3.  선택 된 **명령줄** 속성 페이지.  
  
4.  에 옵션을 입력 **추가 옵션**:  
  
     `/opt:lbr`  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A> 속성을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)
