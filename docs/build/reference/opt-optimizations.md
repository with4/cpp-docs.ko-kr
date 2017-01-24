---
title: "/OPT(최적화) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.OptimizeReferences"
  - "/opt"
  - "VC.Project.VCLinkerTool.OptimizeForWindows98"
  - "VC.Project.VCLinkerTool.EnableCOMDATFolding"
  - "VC.Project.VCLinkerTool.OptimizeFolding"
  - "VC.Project.VCLinkerTool.FoldingIterations"
  - "VC.Project.VCLinkerTool.OptimizeFoldingIterations"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/OPT 링커 옵션"
  - "LINK 도구[C++], 최적화 제어"
  - "링커[C++], 최적화"
  - "OPT 링커 옵션"
  - "-OPT 링커 옵션"
  - "최적화, 링커"
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /OPT(최적화)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK가 빌드하는 동안 수행할 최적화를 제어합니다.  
  
## 구문  
  
```  
/OPT:{REF | NOREF}  
/OPT:{ICF[=iterations] | NOICF}  
/OPT:{LBR | NOLBR}  
```  
  
## 인수  
 **REF** &#124; **NOREF**  
 **\/OPT:REF**를 사용하면 참조되지 않는 함수 및 데이터가 제거되고, **\/OPT:NOREF**를 사용하면 참조되지 않는 함수 및 데이터가 유지됩니다.  
  
 \/OFT:REF를 사용하면 LINK가 참조되지 않은 패키지된 함수 및 데이터를 제거합니다.  [\/Gy](../../build/reference/gy-enable-function-level-linking.md) 옵션을 사용하여 컴파일한 개체에는 패키지 함수 및 데이터\(COMDAT\)가 포함되어 있습니다.  이러한 최적화를 전이적 COMDAT 제거라고 합니다.  기본적으로 **\/OPT:REF**는 디버그가 아닌 빌드에서 사용됩니다.  이 기본값을 무시하고 참조되지 않는 COMDAT를 프로그램에 유지하려면 **\/OPT:NOREF**를 지정합니다.  [\/INCLUDE](../../build/reference/include-force-symbol-references.md) 옵션을 사용하면 특정 기호는 제거되지 않도록 할 수 있습니다.  
  
 **\/OPT:REF**가 명시적으로 또는 기본적으로 사용되면 동일한 함수만 정리하는 제한된 형태의 **\/OPT:ICF**가 사용됩니다.  **\/OPT:ICF**를 설정하지 않고 **\/OPT:REF**를 설정하려면 **\/OPT:REF,NOICF** 또는 **\/OPT:NOICF**를 지정해야 합니다.  
  
 [\/DEBUG](../../build/reference/debug-generate-debug-info.md)를 지정한 경우 **\/OPT**에는 기본적으로 **NOREF**가 지정되어 모든 함수가 이미지에 보존됩니다.  이 기본값을 무시하고 디버깅 빌드를 최적화하려면 **\/OPT:REF**를 지정합니다.  **\/OPT:REF**가 **\/OPT:ICF**를 의미하기 때문에 디버깅 빌드에서 동일한 함수를 유지하기 위해 **\/OPT:NOICF**를 지정하는 것이 좋습니다.  이렇게 하면 스택 추적을 읽고 다른 방식으로는 함께 정리될 함수에서 종단점을 쉽게 설정할 수 있습니다.  **\/OPT:REF** 옵션을 사용하면 증분 링크를 사용할 수 없습니다.  
  
 [\_\_declspec\(selectany\)](../../cpp/selectany.md)를 사용하여 `const` 데이터를 명시적으로 COMDAT로 표시해야 합니다.  
  
 **\/OPT:ICF**를 지정해도 **\/OPT:REF** 옵션은 사용할 수 없습니다.  
  
 **ICF\[\=**  `iterations` **\] &#124; NOICF**  
 동일한 COMDAT를 정리하려면 **\/OPT:ICF\[\=**`iterations`**\]**를 사용합니다.  중복 COMDAT는 링커 출력에서 제거될 수 있습니다.  선택적인 `iterations` 매개 변수는 중복을 위해 기호를 트래버스하는 횟수를 지정합니다.  기본 반복 횟수는 2입니다.  추가 반복에서 이전 반복의 정리를 통해 발견되지 않은 중복 항목을 더 많이 찾을 수도 있습니다.  
  
 링커는 **\/OPT:REF**가 지정되고 **ICF**가 기본적으로 적용되었을 때 **\/OPT:REF,ICF**가 명시적으로 지정되었을 때와는 다르게 작동합니다.  **\/OPT:REF**와만 사용할 수 있는 **ICF** 형태는 읽기 전용 데이터를 정리하지 않습니다. 여기에는 .rdata, .pdata 및 .xdata가 포함됩니다.  따라서 이러한 모듈의 함수에 읽기 전용 데이터 종속성이 높아지기 때문에\(예: .pdata 및 .xdata\) [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]에 대해 이미지가 생성될 때 정리되는 함수가 적어집니다.  전체 **ICF** 정리 동작을 가져오려면 **\/OPT:ICF**를 명시적으로 지정합니다.  
  
 COMDAT에 함수를 배치하려면 **\/Gy** 컴파일러 옵션을 사용합니다. `const` 데이터를 배치하려면 `__declspec(selectany)`로 선언합니다.  정리할 데이터를 지정하는 방법에 대한 내용은 [selectany](../../cpp/selectany.md)를 참조하십시오.  
  
 기본적으로 **REF**가 설정되면 **ICF**가 설정됩니다.  **REF**가 설정된 경우 이 기본값을 재정의하려면 **NOICF**를 사용합니다.  **\/OPT:REF**가 디버그 빌드에서 지정되지 않았을 때 COMDAT 정리를 사용하기 위해 **\/OPT:ICF**를 명시적으로 지정해야 합니다.  그러나 **\/OPT:ICF**가 동일한 데이터 또는 함수를 병합할 수 있기 때문에 스택 추적에 표시되는 함수 이름을 변경할 수 있습니다.  특정 함수에 중단점을 설정하거나 디버거에서 일부 데이터를 검사할 수 없게 되고 코드를 단일 단계로 처리할 때 예기치 않은 함수로 이동할 수도 있습니다.  따라서 더 작은 코드의 장점이 이러한 단점보다 크지 않으면 **\/OPT:ICF**를 사용하지 않는 것이 좋습니다.  
  
> [!NOTE]
>  **\/OPT:ICF**로 인해 서로 다른 함수 또는 읽기 전용 데이터 멤버\(**\/Gy**를 사용하여 컴파일된 `const` 변수\)에 같은 주소가 할당될 수 있기 때문에 함수 또는 읽기 전용 데이터 멤버의 고유 주소에 의존하는 프로그램을 중단할 수 있습니다.  자세한 내용은 [\/Gy\(함수 수준 링크 사용\)](../../build/reference/gy-enable-function-level-linking.md)을 참조하십시오.  
  
 **LBR** &#124; **NOLBR**  
 **\/OPT:LBR** 및 **\/OPT:NOLBR** 옵션은 ARM 이진 파일에만 적용됩니다.  특정 ARM 프로세서 분기 명령에는 제한된 범위가 있으므로 링커가 범위를 벗어난 주소로 점프하는 것을 감지하면 분기 명령의 대상 주소를 실제 대상을 목표로 하는 분기 명령이 포함된 코드 "아일랜드"의 주소로 대체합니다.  **\/OPT:LBR**을 사용하여 긴 분기 지침 검색 및 중간 코드 아일랜드 배치를 최적화하여 전체 코드 크기를 최소화할 수 있습니다.  **\/OPT:NOLBR**은 최적화 없이 발생될 때 긴 분기 명령에 대한 코드 아일랜드를 생성하도록 링커에 지시합니다.  
  
 기본적으로 **\/OPT:LBR** 옵션은 증분 링크를 사용할 수 없을 때 설정됩니다.  증분 링크는 원하지만 긴 분기 최적화는 원하지 않는 경우 **\/OPT:NOLBR**을 지정합니다.  **\/OPT:LBR** 옵션을 사용하면 증분 링크를 사용할 수 없습니다.  
  
## 설명  
 최적화하면 일반적으로 링크 시간이 늘어나는 대신 이미지 크기가 줄어들고 프로그램 속도는 향상됩니다.  
  
 [\/VERBOSE](../../build/reference/verbose-print-progress-messages.md) 옵션을 사용하면 **\/OPT:REF**로 제거된 함수와 **\/OPT:ICF**로 정리된 함수를 표시할 수 있습니다.  
  
### Visual Studio 개발 환경에서 OPT:ICF 또는 OPT:REF 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  왼쪽 창에서 **구성 속성**, **링커**, **최적화**를 확장합니다.  
  
3.  다음 속성 중 하나를 수정합니다.  
  
    -   **COMDAT 정리 사용**  
  
    -   **참조**  
  
### Visual Studio 개발 환경에서 OPT:LBR 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **추가 옵션**에 옵션을 입력합니다.  
  
     `/opt:lbr`  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A> 속성을 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)