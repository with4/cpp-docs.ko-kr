---
title: "/FI(강제 포함 파일 이름 지정) | Microsoft Docs"
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
  - "VC.Project.VCNMakeTool.ForcedIncludes"
  - "VC.Project.VCCLCompilerTool.ForcedIncludeFiles"
  - "VC.Project.VCCLWCECompilerTool.ForcedIncludeFiles"
  - "/fi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FI 컴파일러 옵션[C++]"
  - "FI 컴파일러 옵션[C++]"
  - "-FI 컴파일러 옵션[C++]"
  - "헤더 파일 전처리 컴파일러 옵션[C++]"
ms.assetid: 07e79577-8152-4df9-a64c-aae08c603397
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FI(강제 포함 파일 이름 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

전처리기에서 지정된 헤더 파일을 처리합니다.  
  
## 구문  
  
```  
/FI[ ]pathname  
```  
  
## 설명  
 이 옵션을 지정하면 명령줄, CL 환경 변수 또는 명령 파일에 지정된 모든 소스 파일의 첫 번째 줄에 있는 `#include` 지시문에 큰따옴표를 사용하여 파일을 지정한 것과 동일한 결과가 나옵니다.  **\/FI** 옵션을 여러 개 사용하면 CL에서 처리하는 순서대로 파일이 포함됩니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **고급** 속성 페이지를 클릭합니다.  
  
4.  **강제 포함** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>를 참조하십시오.  
  
## 참고 항목  
 [출력 파일\(\/F\) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)