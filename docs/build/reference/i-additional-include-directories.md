---
title: "/I(추가 포함 디렉터리) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories"
  - "VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories"
  - "/I"
  - "VC.Project.VCNMakeTool.IncludeSearchPath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/I 컴파일러 옵션[C++]"
  - "추가 포함 디렉터리 컴파일러 옵션"
  - "I 컴파일러 옵션[C++]"
  - "-I 컴파일러 옵션[C++]"
  - "포함 디렉터리, 컴파일러 옵션[C++]"
  - "포함 디렉터리 설정"
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /I(추가 포함 디렉터리)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

포함 파일을 찾기 위해 검색할 디렉터리 목록에 디렉터리를 추가합니다.  
  
## 구문  
  
```  
/I[ ]directory  
```  
  
## 인수  
 `directory`  
 포함 파일을 찾기 위해 검색할 디렉터리 목록에 추가될 디렉터리입니다.  
  
## 설명  
 두 개 이상의 디렉터리를 추가하려면 이 옵션을 두 번 이상 사용합니다.  지정한 포함 파일을 찾을 때까지만 디렉터리를 검색합니다.  
  
 표준 포함 경로 무시\([\/X\(표준 포함 경로 무시\)](../../build/reference/x-ignore-standard-include-paths.md)\) 옵션과 함께 이 옵션을 사용할 수 있습니다.  
  
 컴파일러는 다음과 같은 순서로 디렉터리를 검색합니다.  
  
1.  소스 파일이 포함된 디렉터리  
  
2.  **\/I** 옵션을 사용하여 지정한 디렉터리\(CL에 나타나는 순서대로 검색\)  
  
3.  **INCLUDE** 환경 변수에 지정한 디렉터리  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **일반** 속성 페이지를 클릭합니다.  
  
4.  **추가 포함 디렉터리** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>를 참조하십시오.  
  
## 예제  
 다음은 MAIN.c에서 요청한 포함 파일을 검색하는 명령입니다. 검색 순서는 MAIN.c가 포함된 디렉터리, \\INCLUDE 디렉터리, \\MY\\INCLUDE 디렉터리, INCLUDE 환경 변수에 할당된 디렉터리입니다.  
  
```  
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C  
```  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)