---
title: "/Yu(미리 컴파일된 헤더 파일 사용) | Microsoft Docs"
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
  - "/yu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch 파일, 기존 항목 사용"
  - "/Yu 컴파일러 옵션[C++]"
  - "PCH 파일, 기존 항목 사용"
  - "미리 컴파일된 헤더 파일, 기존 항목 사용"
  - "Yu 컴파일러 옵션[C++]"
  - "-Yu 컴파일러 옵션[C++]"
ms.assetid: 24f1bd0e-b624-4296-a17e-d4b53e374e1f
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Yu(미리 컴파일된 헤더 파일 사용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러가 현재 컴파일에서 기존의 미리 컴파일된 헤더\(.pch\) 파일을 사용하도록 지시합니다.  
  
## 구문  
  
```  
/Yu[filename]  
```  
  
## 인수  
 *filename*  
 **\#include** 전처리기 지시문을 사용하여 소스 파일에 포함되는 헤더 파일의 이름입니다.  
  
## 설명  
 포함 파일의 이름은 미리 컴파일된 헤더를 만드는 **\/Yc** 옵션과 미리 컴파일된 헤더 사용을 지정하는 그 뒤의 **\/Yu** 옵션 모두에 대해 같아야 합니다.  
  
 **\/Yc**의 경우 `filename`은 미리 컴파일 작업이 중지된 위치를 지정합니다. 컴파일러는 `filename`을 통해 모든 코드를 미리 컴파일하며, 포함 파일의 기본 이름과 .pch의 확장명을 사용하여 만들어진 미리 컴파일된 헤더의 이름을 지정합니다.  
  
 **\/Yc**를 사용하여 .pch 파일을 만들어야 합니다.  
  
 컴파일러는 .h 파일 전에 나오는 모든 코드를 미리 컴파일된 코드로 간주합니다.  컴파일러는 .h 파일과 연관된 **\#include** 지시문을 건너뛰어 .pch 파일에 포함된 코드를 사용한 후, `filename` 뒤에 나오는 모든 코드를 컴파일합니다.  
  
 명령줄에서 **\/Yu** 옵션과 `filename` 사이에는 공백이 없어야 합니다.  
  
 파일 이름 없이 **\/Yu** 옵션을 지정할 경우에는 소스 프로그램에 미리 컴파일된 헤더 .pch 파일의 파일 이름을 지정하는 [\#pragma hdrstop](../../preprocessor/hdrstop.md) pragma가 포함되어 있어야 합니다.  이 경우 컴파일러에서는 [\/Fp\(.Pch 파일 이름 지정\)](../../build/reference/fp-name-dot-pch-file.md)에서 이름을 지정한 미리 컴파일된 헤더\(.pch 파일\)를 사용합니다.  컴파일러는 해당 pragma의 위치로 건너뛰고, pragma에 의해 지정된 미리 컴파일된 헤더 파일의 컴파일 상태를 복원한 후, pragma 다음에 오는 코드만 컴파일합니다.  **\#pragma hdrstop**에서 파일 이름을 지정하지 않은 경우 컴파일러는 .pch 확장명과 소스 파일의 기본 이름에서 파생된 이름을 가진 파일을 찾습니다.  사용자는 또한 **\/Fp** 옵션을 사용하여 다른 .pch 파일을 지정할 수도 있습니다.  
  
 파일 이름 없이 **\/Yu** 옵션을 지정한 후 **hdrstop** pragma를 지정하는 데 실패한 경우 오류 메시지가 생성되고 컴파일은 실패합니다.  
  
 **\/Yc** `filename` 및  **\/Yu**`filename` 옵션을 동일한 명령줄에서 사용하고 이 두 옵션이 모두 동일한 파일 이름을 참조하는 경우 **\/Yc**`filename`의 우선 순위가 더 높으며 명명된 파일을 포함하여 이 파일에 이를 때까지 모든 코드가 미리 컴파일됩니다.  이 기능은 메이크파일의 작성을 단순화합니다.  
  
 .pch 파일에는 컴퓨터 환경에 대한 정보를 비롯하여 프로그램에 대한 메모리 주소 정보가 포함되므로 pch 파일은 이 파일을 만든 컴퓨터에서만 사용해야 합니다.  
  
 미리 컴파일된 헤더에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [\/Y\(미리 컴파일된 헤더\)](../../build/reference/y-precompiled-headers.md)  
  
-   [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 .cpp 파일에 대해 [\/Yc\(미리 컴파일된 헤더 파일 만들기\)](../../build/reference/yc-create-precompiled-header-file.md)를 지정합니다.  
  
2.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
3.  **C\/C\+\+** 폴더를 클릭합니다.  
  
4.  **미리 컴파일된 헤더** 속성 페이지를 클릭합니다.  
  
5.  **파일에서 PCH 만들기\/사용** 속성 또는 **미리 컴파일된 헤더 만들기\/사용** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>을 참조하십시오.  
  
## 예제  
 다음 코드를 참조하십시오.  
  
```  
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
...  
```  
  
 위 코드는 명령줄 `CL /YuMYAPP.H PROG.CPP`를 사용하여 컴파일되며, 컴파일러는 세 개의 include 문을 처리하지 않지만 MYAPP.pch의 미리 컴파일된 코드를 사용하므로, 파일 세 개 및 여기에 포함된 모든 파일을 전처리하는 데 걸리는 시간이 줄어듭니다.  
  
 [\/Fp\(.Pch 파일 이름 지정\)](../../build/reference/fp-name-dot-pch-file.md) 옵션을 **\/Yu** 옵션과 함께 사용하면 다음과 같이 이름이 **\/Yc**에 대한 파일 이름 인수나 소스 파일의 기본 이름과 다른 경우 .pch 파일의 이름을 지정할 수 있습니다.  
  
```  
CL /YuMYAPP.H /FpMYPCH.pch PROG.CPP  
```  
  
 이 명령은 MYPCH.pch라는 이름의 미리 컴파일된 헤더 파일을 지정합니다.  컴파일러는 이 파일의 내용을 사용하여 MYAPP.h를 포함한 모든 헤더 파일의 미리 컴파일된 상태를 복원합니다.  그런 다음 컴파일러는 MYAPP.h **include** 문 다음에 나오는 코드를 컴파일합니다.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)