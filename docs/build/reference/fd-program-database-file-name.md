---
title: "/Fd(프로그램 데이터베이스 파일 이름) | Microsoft Docs"
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
  - "/FD"
  - "VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName"
  - "VC.Project.VCCLCompilerTool.ProgramDataBaseFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb 파일, 만들기"
  - "/FD 컴파일러 옵션[C++]"
  - "FD 컴파일러 옵션[C++]"
  - "-FD 컴파일러 옵션[C++]"
  - "PDB 파일, 만들기"
  - "프로그램 데이터베이스 컴파일러 옵션[C++]"
  - "프로그램 데이터베이스 파일 이름[C++]"
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fd(프로그램 데이터베이스 파일 이름)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/Z7, \/Zi, \/ZI\(디버깅 정보 형식\)](../../build/reference/z7-zi-zi-debug-information-format.md) 옵션을 사용하여 만드는 PDB\(프로그램 데이터베이스\) 파일의 이름을 지정합니다.  
  
## 구문  
  
```  
/Fdpathname  
```  
  
## 설명  
 **\/Fd** 옵션을 지정하지 않으면 기본적으로 PDB 파일의 이름이 VC`x`0.pdb가 됩니다. 여기서 `x`는 사용하는 Visual C\+\+의 주 버전을 나타냅니다.  
  
 파일 이름을 포함하지 않는 경로 이름을 지정하면\(경로가 백슬래시로 끝나는 경우\) 컴파일러는 지정한 디렉터리에 VC`x`0.pdb라는 .pdb 파일을 만듭니다.  
  
 확장명이 없는 파일 이름을 지정하면 컴파일러는 .pdb를 확장명으로 사용합니다.  
  
 이 옵션은 최소 재빌드 및 증분 컴파일에 사용되는 상태 파일\(.idb\)의 이름도 지정합니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **출력 파일** 속성 페이지를 클릭합니다.  
  
4.  **프로그램 데이터베이스 파일 이름** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ProgramDataBaseFileName%2A>를 참조하십시오.  
  
## 예제  
 다음 명령줄을 실행하면 PROG.pdb라는 .pdb 파일과 PROG.idb라는 .idb 파일이 만들어집니다.  
  
```  
CL /DDEBUG /Zi /FdPROG.PDB PROG.CPP  
```  
  
## 참고 항목  
 [출력 파일\(\/F\) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)