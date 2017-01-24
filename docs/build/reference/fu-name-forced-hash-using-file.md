---
title: "/FU(강제 #using 파일 이름 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.ForcedUsingFiles"
  - "/FU"
  - "VC.Project.VCNMakeTool.ForcedUsingAssemblies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FU 컴파일러 옵션[C++]"
  - "FU 컴파일러 옵션[C++]"
  - "-FU 컴파일러 옵션[C++]"
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FU(강제 #using 파일 이름 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

소스 코드에서 [\#using 지시문](../../preprocessor/hash-using-directive-cpp.md)으로 파일 이름을 전달하는 것과는 다른 컴파일러 옵션을 제공합니다.  
  
## 구문  
  
```  
/FU file  
```  
  
## 인수  
 `file`  
 이 컴파일 과정에서 참조할 메타데이터 파일을 지정합니다.  
  
## 설명  
 \/FU 스위치에서는 하나의 파일 이름을 가져옵니다.  여러 파일을 지정 하려면 각 하나를 사용하여 \/FU를 사용 합니다.  
  
 [!INCLUDE[cppcli](../../build/reference/includes/cppcli_md.md)] 사용하고 메타 데이터를 참조 하는 [Friend 어셈블리](../../dotnet/friend-assemblies-cpp.md) 를 사용하는 경우 **\/FU**를 사용할 수 없습니다.  코드의 메타 데이터를 참조 해야 합니다  `#using` \-함께  `[as friend]`  특성을 참조해야 합니다.  Friend 어셈블리에서는 [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)]\([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]\)이 지원 되지 않습니다.  
  
 공용 언어 런타임용 어셈블리나 모듈을 만드는 방법에 대한 자세한 내용은[\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)를 참조하십시오.  [!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]에서 만드는 방법에 대한 자세한 내용은 [응용 프로그램 및 라이브러리 빌드](../Topic/Building%20apps%20and%20libraries%20\(C++-CX\).md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **고급** 속성 페이지를 선택합니다.  
  
4.  **\#using 강제** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>를 참조하십시오.  
  
## 참고 항목  
 [출력 파일\(\/F\) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)