---
title: "/X(표준 포함 경로 무시) | Microsoft Docs"
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
  - "/x"
  - "VC.Project.VCCLCompilerTool.IgnoreStandardIncludePath"
  - "VC.Project.VCCLWCECompilerTool.IgnoreStandardIncludePath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/X 컴파일러 옵션[C++]"
  - "표준 포함 경로 무시 컴파일러 옵션"
  - "포함 디렉터리, 표준 무시"
  - "포함 파일, 표준 경로 무시"
  - "X 컴파일러 옵션"
  - "-X 컴파일러 옵션[C++]"
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /X(표준 포함 경로 무시)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러가 PATH 및 INCLUDE 환경 변수에 지정된 디렉터리에서 포함 파일을 검색하지 않도록 합니다.  
  
## 구문  
  
```  
/X  
```  
  
## 설명  
 이 옵션은 [\/I\(추가 포함 디렉터리\)](../../build/reference/i-additional-include-directories.md)\(**\/I**`directory`\) 옵션과 함께 사용할 수 있습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **전처리기** 속성 페이지를 클릭합니다.  
  
4.  **표준 포함 경로 무시** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>를 참조하십시오.  
  
## 예제  
 다음 명령에서 `/X`는 PATH 및 INCLUDE 환경 변수에서 지정한 위치를 무시하도록 컴파일러에 지시하며, `/I`는 포함 파일을 검색할 디렉터리를 지정합니다.  
  
```  
CL /X /I \ALT\INCLUDE MAIN.C  
```  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)