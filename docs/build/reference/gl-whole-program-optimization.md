---
title: "/GL(전체 프로그램 최적화) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/gl"
  - "VC.Project.VCCLWCECompilerTool.WholeProgramOptimization"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GL 컴파일러 옵션[C++]"
  - "GL 컴파일러 옵션[C++]"
  - "-GL 컴파일러 옵션[C++]"
  - "전체 프로그램 최적화 및 C++ 컴파일러"
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /GL(전체 프로그램 최적화)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

전체 프로그램 최적화를 사용합니다.  
  
## 구문  
  
```  
/GL[-]  
```  
  
## 설명  
 전체 프로그램 최적화를 사용하면 컴파일러는 프로그램 내의 모든 모듈에 대한 정보를 사용하여 최적화를 수행합니다.  전체 프로그램 최적화를 사용하지 않으면 모듈\(컴파일\)별로 최적화가 수행됩니다.  
  
 전체 프로그램 최적화는 기본적으로 설정되어 있지 않으므로 명시적으로 설정해야 합니다.  그러나 **\/GL\-**를 사용하여 이 옵션을 명시적으로 해제할 수도 있습니다.  
  
 모든 모듈에 대한 정보를 사용하여 컴파일러는 다음과 같은 작업을 수행할 수 있습니다.  
  
-   함수에 관계 없이 레지스터 사용을 최적화할 수 있습니다.  
  
-   전역 데이터의 수정 사항을 더 효율적으로 추적하여 로드 및 저장 횟수를 줄일 수 있습니다.  
  
-   포인터 역참조로 수정된 항목의 가능한 집합을 더 효율적으로 추적하여 로드 및 저장 횟수를 줄일 수 있습니다.  
  
-   다른 모듈에서 정의된 함수도 모듈 내에 포함할 수 있습니다.  
  
 **\/GL**을 사용하여 생성한 .obj 파일은 [EDITBIN](../../build/reference/editbin-reference.md) 및 [DUMPBIN](../../build/reference/dumpbin-reference.md) 같은 링커 유틸리티에서는 사용할 수 없습니다.  
  
 **\/GL** 및 [\/c](../../build/reference/c-compile-without-linking.md)를 사용하여 프로그램을 컴파일하려면 \/LTCG 링커 옵션을 사용하여 출력 파일을 만들어야 합니다.  
  
 [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)는 **\/GL**과 함께 사용할 수 없습니다.  
  
 현재 버전에서 **\/GL**을 사용하여 생성한 파일 형식은 Visual C\+\+의 이후 버전에서 읽지 못할 수도 있습니다.  사용자가 현재 또는 미래에 사용할 Visual C\+\+의 모든 버전의 .lib 파일 사본을 제공하지 않으려면 **\/GL**을 사용하여 생성한 .obj 파일로 구성되는 .lib 파일을 제공해서는 안 됩니다.  
  
 **\/GL**을 사용하여 .obj 파일을 생성한 동일한 컴퓨터에서 .lib 파일이 링크되지 않는 경우, **\/GL**을 사용하여 생성한 .obj 파일과 미리 컴파일한 헤더 파일을 사용하여 .lib 파일을 빌드해서는 안 됩니다.  .obj 파일에 있는 미리 컴파일한 헤더 파일의 정보는 링크할 때 필요합니다.  
  
 참조에 사용할 수 있는 최적화 및 전체 프로그램 최적화의 제한에 대 한 자세한 내용은  [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md).   **\/GL**또한 프로필 기반 최적화를 사용할 수 있습니다;는 \/LTCG을 참조 하십시오.  프로필 기반 최적화를 사용하여 컴파일하는 경우 프로필 기반 최적화에 따라 함수의 순서를 지정하려면 [\/Gy](../../build/reference/gy-enable-function-level-linking.md)를 사용하거나 \/Gy가 내포된 컴파일러 옵션을 사용하여 컴파일해야 합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  개발 환경에서 **\/GL**을 지정하는 방법에 대한 자세한 내용은 [\/LTCG\(링크 타임 코드 생성\)](../../build/reference/ltcg-link-time-code-generation.md)를 참조하십시오.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)