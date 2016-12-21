---
title: "/Yc(미리 컴파일된 헤더 파일 만들기) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.UsePrecompiledHeader"
  - "/yc"
  - "VC.Project.VCCLWCECompilerTool.PrecompiledHeaderThrough"
  - "VC.Project.VCCLWCECompilerTool.UsePrecompiledHeader"
  - "VC.Project.VCCLCompilerTool.PrecompiledHeaderThrough"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch 파일, 만들기"
  - "/Yc 컴파일러 옵션[C++]"
  - "PCH 파일, 만들기"
  - "미리 컴파일된 헤더 파일, 만들기"
  - "Yc 컴파일러 옵션[C++]"
  - "-Yc 컴파일러 옵션[C++]"
ms.assetid: 47c2e555-b4f5-46e6-906e-ab5cf21f0678
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Yc(미리 컴파일된 헤더 파일 만들기)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러가 특정 지점에 컴파일 상태를 나타내는 미리 컴파일된 헤더\(.pch\) 파일을 만들도록 지시합니다.  
  
## 구문  
  
```  
/Yc[filename]  
```  
  
## 인수  
 `filename`  
 헤더 파일\(.h\)을 지정합니다.  이 인수를 사용하면 컴파일러에서 .h 파일에 이르는 모든 코드가 컴파일됩니다. 여기에는 .h 파일도 포함됩니다.  
  
## 설명  
 인수 없이 **\/Yc**를 지정한 경우 컴파일러는 기본 소스 파일의 끝까지 또는 기본 파일에서 [hdrstop](../../preprocessor/hdrstop.md)이 발생한 지점까지 모든 코드를 컴파일합니다.  결과로 만들어진 .pch 파일은 사용자가 **hdrstop** pragma 또는 **\/Fp** 옵션을 사용하여 다른 파일 이름을 지정하지 않는 한 기본 소스 파일과 동일한 기본 이름을 갖게 됩니다.  
  
 미리 컴파일된 코드는 **\/Yc** 옵션을 사용하여 지정된 파일의 기본 이름에서 만든 이름과 .pch 확장명을 가진 파일에 저장됩니다.  사용자는 또한 [\/Fp\(.Pch 파일 이름 지정\)](../../build/reference/fp-name-dot-pch-file.md) 옵션을 사용하여 미리 컴파일된 헤더 파일에 대한 이름을 지정할 수도 있습니다.  
  
 헤더를 통해 **\/Yc**`filename`을 사용하는 경우 컴파일러는 **\/Yu** 옵션으로 다음에 사용하기 위해 지정한 파일을 포함하여 모든 코드를 컴파일합니다.  
  
 **\/Yc** `filename` 및 [\/Yu\(미리 컴파일된 헤더 파일 사용\)](../../build/reference/yu-use-precompiled-header-file.md)`filename` 옵션을 동일한 명령줄에 사용하고 이 두 옵션이 모두 동일한 파일 이름을 참조하거나 암시하는 경우 **\/Yc**`filename`의 우선 순위가 더 높습니다.  이 기능은 메이크파일의 작성을 단순화합니다.  
  
 미리 컴파일된 헤더에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [\/Y\(미리 컴파일된 헤더\)](../../build/reference/y-precompiled-headers.md)  
  
-   [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  .cpp 파일을 선택합니다.  .cpp 파일은 미리 컴파일된 헤더 정보가 들어 있는 .h 파일에 대해 \#include를 수행해야 합니다.  프로젝트의 **\/Yc** 설정은 파일 수준에서 재정의될 수 있습니다.  
  
2.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
3.  **C\/C\+\+** 폴더를 클릭합니다.  
  
4.  **미리 컴파일된 헤더** 속성 페이지를 클릭합니다.  
  
5.  **파일에서 PCH 만들기\/사용** 속성 또는 **미리 컴파일된 헤더 만들기\/사용** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>을 참조하십시오.  
  
## 예제  
 다음 코드를 살펴보십시오.  
  
```  
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
...  
```  
  
 `CL /YcMYAPP.H PROG.CPP` 명령을 사용하여 이 코드를 컴파일하는 경우 컴파일러는 MYAPP.pch라는 미리 컴파일된 헤더 파일에서 AFXWIN.h, RESOURCE.h 및 MYAPP.h에 대한 모든 전처리를 저장합니다.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)