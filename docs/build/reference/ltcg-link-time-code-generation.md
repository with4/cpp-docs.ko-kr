---
title: "/LTCG(링크 타임 코드 생성) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.LinkTimeCodeGeneration"
  - "VC.Project.VCConfiguration.WholeProgramOptimization"
  - "VC.Project.VCCLWCECompilerTool.WholeProgramOptimization"
  - "/ltcg"
  - "VC.Project.VCCLCompilerTool.WholeProgramOptimization"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LTCG 링커 옵션"
  - "C++ 링커에서 링크 시간 코드 생성"
  - "LTCG 링커 옵션"
  - "-LTCG 링커 옵션"
ms.assetid: 788c6f52-fdb8-40c2-90af-4026ea2cf2e2
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /LTCG(링크 타임 코드 생성)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LTCG[:INCREMENTAL|:NOSTATUS|:STATUS|:OFF|:PGINSTRUMENT|:PGOPTIMIZE|:PGUPDATE]  
```  
  
## 설명  
 :증분\(옵션\)  
 링커가 전체 프로젝트 대신 편집의 영향을 받는 파일 집합에만 전체 프로그램 최적화 또는 LTCG\(링크 타임 코드 생성\)를 적용하도록 지정합니다. 기본적으로 \/LTCG가 지정된 경우에는 이 플래그가 설정되지 않으며 전체 프로그램 최적화를 사용하여 전체 프로젝트가 연결됩니다.  
  
 :NOSTATUS &#124;:STATUS\(옵션\)  
 완료된 링크 비율을 표시하는 진행률 표시기가 링커에 표시되는지 여부를 지정합니다. 기본적으로 이 상태 정보는 표시되지 않습니다.  
  
 :OFF\(옵션\)  
 링크 타임 코드 생성을 사용하지 않도록 설정합니다. 이 동작은 명령줄에서 \/LTCG가 지정되지 않은 경우와 동일합니다.  
  
 :PGINSTRUMENT\(옵션\)  
 이 옵션은 사용되지 않습니다. 대신, **\/LTCG** 및 **\/GENPROFILE** 또는 **\/FASTGENPROFILE**을 사용하여 프로필 기반 최적화를 위한 계측된 빌드를 생성합니다.  
  
 계측된 실행으로부터 수집되는 데이터는 최적화된 이미지를 만드는 데 사용됩니다. 자세한 내용은 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)를 참조하세요. 이 옵션의 약식 형태는 \/LTCG:PGI입니다.  
  
 :PGOPTIMIZE\(옵션\)  
 이 옵션은 사용되지 않습니다. 대신, **\/LTCG** 및 **\/USEPROFILE**을 사용하여 최적화된 이미지를 빌드합니다. 자세한 내용은 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)를 참조하세요. 이 옵션의 약식 형태는 \/LTCG:PGO입니다.  
  
 :PGUPDATE\(옵션\)  
 이 옵션은 사용되지 않습니다. 대신, **\/LTCG** 및 **\/USEPROFILE**을 사용하여 최적화된 이미지를 빌드합니다. 자세한 내용은 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)를 참조하세요. 이 옵션의 약식 형태는 \/LTCG:PGU입니다.  
  
 \/LTCG 옵션은 링커가 컴파일러를 호출하고 전체 프로그램 최적화를 수행하도록 지정합니다. 프로필 기반 최적화를 수행할 수도 있습니다. 자세한 내용은 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)를 참조하세요.  
  
 다음과 같은 경우를 제외하고 \/LTCG 및 \/GENPROFILE 옵션의 이전 PGO 초기화 조합에 지정되지 않은 \/LTCG 및 \/USEPROFILE의 PGO 조합에 링커 옵션을 추가할 수 없습니다.  
  
-   [\/BASE](../../build/reference/base-base-address.md)  
  
-   [\/FIXED](../../build/reference/fixed-fixed-base-address.md)  
  
-   \/LTCG  
  
-   [\/MAP](../../build/reference/map-generate-mapfile.md)  
  
-   [\/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)  
  
-   [\/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)  
  
-   [\/OUT](../../build/reference/out-output-file-name.md)  
  
-   [\/PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)  
  
-   [\/PDB](../../build/reference/pdb-use-program-database.md)  
  
-   [\/PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)  
  
-   [\/STUB](../../build/reference/stub-ms-dos-stub-file-name.md)  
  
-   [\/VERBOSE](../../build/reference/verbose-print-progress-messages.md)  
  
 PGO를 초기화하기 위해 \/LTCG 및 \/GENPROFILE 옵션과 함께 지정된 링커 옵션은 암시적으로 지정되므로 \/LTCG 및 \/USEPROFILE을 사용하여 빌드할 때 지정할 필요가 없습니다.  
  
 이 항목의 나머지 부분에서는 링크\-시간 코드 생성의 관점에서 \/LTCG에 대해 설명합니다.  
  
 \/LTCG는 [\/GL](../../build/reference/gl-whole-program-optimization.md)을 사용하여 암시적으로 지정됩니다.  
  
 링커는 **\/GL** 또는 MSIL 모듈을 사용하여 컴파일된 모듈이 전달될 경우 링크 타임 코드 생성을 호출합니다\([링커 입력 파일로 사용하는 .netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md) 참조\). **\/GL** 또는 MSIL 모듈을 링커에 전달할 때 **\/LTCG**를 명시적으로 지정하지 않으면 링커에서 결국 이 상태가 감지되고 **\/LTCG**를 사용해서 링크를 다시 시작합니다. 가능한 가장 빠른 빌드 성능을 위해서는 **\/GL** 및 MSIL 모듈을 링커에 전달할 때 **\/LTCG**를 명시적으로 지정합니다.  
  
 성능을 더욱 향상시키려면 **\/LTCG:INCREMENTAL**을 사용합니다. 이 옵션은 전체 프로젝트 대신 소스 파일 변경의 영향을 받는 파일 집합만 다시 최적화하도록 링커에 지시합니다. 이렇게 하면 필요한 링크 타임을 상당히 줄일 수 있습니다. 증분 링크와 동일한 옵션이 아닙니다.  
  
 **\/LTCG**는 [\/INCREMENTAL](../../build/reference/incremental-link-incrementally.md)과 함께 사용할 수 없습니다.  
  
**\/LTCG**를 사용하여 [\/Og](../../build/reference/og-global-optimizations.md), [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md) 또는 [\/Ox](../../build/reference/ox-full-optimization.md)로 컴파일된 모듈을 연결하는 경우 다음 최적화가 수행됩니다.  
  
-   모듈 간 인라인 처리  
  
-   프로시저 간 레지스터 할당\(64비트 운영 체제만 해당\)  
  
-   사용자 지정 호출 규칙\(x86만 해당\)  
  
-   작은 TLS 치환\(x86만 해당\)  
  
-   스택 이중 맞춤\(x86만 해당\)  
  
-   향상된 메모리 명확성\(전역 변수 및 입력 매개 변수에 대한 보다 효율적인 간섭 정보\)  
  
> [!NOTE]
> 링커는 각 함수를 컴파일하는 데 사용된 최적화를 확인하고 링크 타임에 동일한 최적화를 적용합니다.  
  
**\/LTCG** 및 **\/Ogt**를 사용하면 이중 할당 최적화가 수행됩니다.  
  
**\/LTCG** 및 **\/Ogs**가 지정된 경우에는 이중 할당이 수행되지 않습니다. 응용 프로그램에 있는 대부분의 함수가 속도에 대해 컴파일되고 일부 함수가 크기에 대해 컴파일된 경우\(예: [optimize](../../preprocessor/optimize.md) pragma 사용\) 컴파일러는 이중 맞춤이 필요한 함수를 호출할 경우 크기에 대해 최적화된 함수를 이중 맞춥니다.  
  
컴파일러가 함수의 모든 호출 사이트를 식별할 수 있는 경우 컴파일러는 함수의 명시적 호출 규칙 한정자를 무시하고 함수의 호출 규칙을 최적화하려고 합니다.  
  
-   레지스터의 매개 변수 전달  
  
-   맞춤을 위해 매개 변수 다시 정렬  
  
-   사용하지 않는 매개 변수 제거  
  
함수 포인터를 통해 함수를 호출하거나 **\/GL**로 컴파일된 모듈 외부에서 함수를 호출하는 경우에는 컴파일러에서 함수의 호출 규칙을 최적화하지 않습니다.  
  
> [!NOTE]
> **\/LTCG**을 사용하고 mainCRTStartup을 다시 정의하는 경우 응용 프로그램은 전역 개체가 초기화되기 전에 실행되는 사용자 코드와 관련된 예기치 않은 동작을 가질 수 있습니다.  이 문제를 해결하는 방법은 세 가지입니다. mainCRTStartup을 다시 정의하지 않거나, **\/LTCG**를 사용해서 mainCRTStartup이 포함된 파일을 컴파일하지 않거나, 전역 변수 및 개체를 정적으로 초기화해야 합니다.  
  
## \/LTCG 및 MSIL 모듈  
[\/GL](../../build/reference/gl-whole-program-optimization.md) 및 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md)을 사용해서 컴파일된 모듈은 **\/LTCG**가 지정된 경우 링커에 대한 입력으로 사용될 수 있습니다.  
  
-   **\/LTCG**는 네이티브 개체 파일, 네이티브\/관리 개체 파일 혼합\(**\/clr**을 사용해서 컴파일\), 순수 개체 파일\(**\/clr:pure**를 사용해서 컴파일\) 및 안전한 개체 파일\(**\/clr:safe**를 사용해서 컴파일\)을 수락할 수 있습니다.  
  
-   **\/LTCG**는 Visual C\+\+의 **\/clr:safe \/LN** 및 다른 Visual Studio 컴파일러의 **\/target:module**을 사용해서 만들 수 있는 안전한 .netmodules를 수락할 수 있습니다.**\/clr** 또는 **\/clr:pure**를 사용해서 생성된 .Netmodules는 **\/LTCG**에서 수락되지 않습니다.  
  
-   \/LTCG:PGI는 **\/GL** 및 **\/clr**을 사용해서 컴파일된 네이티브 모듈 또는 순수 모듈\(**\/clr:pure**를 사용해서 생성\)을 수락하지 않습니다.  
  
#### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다.[프로젝트 속성 사용](../../ide/working-with-project-properties.md)을 참조하세요.  
  
2.  **구성 속성** 폴더를 선택합니다.  
  
3.  **일반** 속성 페이지를 클릭합니다.  
  
4.  **전체 프로그램 최적화** 속성을 수정합니다.  
  
또한 메뉴 모음에서 **빌드**, **프로필 기반 최적화**를 선택하거나 프로젝트의 바로 가기 메뉴에서 프로필 기반 최적화 옵션 중 하나를 선택해서 특정 빌드에 **\/LTCG**를 적용할 수도 있습니다.  
  
#### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>을 참조하세요.  
  
## 참고 항목  
[링커 옵션 설정](../../build/reference/setting-linker-options.md)  
[링커 옵션](../../build/reference/linker-options.md)