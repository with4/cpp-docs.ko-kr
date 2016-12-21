---
title: "/AI(메타데이터 디렉터리 지정) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.AdditionalUsingDirectories"
  - "VC.Project.VCNMakeTool.AssemblySearchPath"
  - "/AI"
  - "VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/AI 컴파일러 옵션[C++]"
  - "AI 컴파일러 옵션[C++]"
  - "-AI 컴파일러 옵션[C++]"
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /AI(메타데이터 디렉터리 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`#using` 지시문에 전달된 파일 참조를 확인하기 위해 컴파일러가 검색할 디렉터리를 지정합니다.  
  
## 구문  
  
```  
/AIdirectory  
```  
  
## 인수  
 `directory`  
 검색할 컴파일러의 디렉터리나 경로  
  
## 설명  
 **\/AI** 호출에 디렉터리를 하나만 전달할 수 있습니다.  컴파일러로 검색하려는 각 경로에 대해 **\/AI** 옵션 하나를 지정합니다.  예를 들어 `#using` 지시문에 대한 컴파일러 검색 경로에 C:\\Project\\Meta와 C:\\Common\\Meta를 모두 추가하려면 컴파일러 명령줄에 `/AI"C:\Project\Meta" /AI"C:\Common\Meta"`를 추가하거나 Visual Studio의 **추가 \#using 디렉터리** 속성에 각 디렉터리를 추가합니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  탐색 창에서 **구성 속성**, **C\/C\+\+**, **일반**을 선택합니다.  
  
3.  **추가 \#using 디렉터리** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [\#using 지시문](../../preprocessor/hash-using-directive-cpp.md)