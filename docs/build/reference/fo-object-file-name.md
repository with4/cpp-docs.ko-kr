---
title: "/Fo(개체 파일 이름) | Microsoft Docs"
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
  - "/Fo"
  - "VC.Project.VCCLCompilerTool.ObjectFile"
  - "VC.Project.VCCLWCECompilerTool.ObjectFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fo 컴파일러 옵션[C++]"
  - "Fo 컴파일러 옵션[C++]"
  - "-Fo 컴파일러 옵션[C++]"
  - "개체 파일, 명명"
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fo(개체 파일 이름)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본값 대신에 사용할 개체 파일\(.obj\) 이름이나 디렉터리를 지정합니다.  
  
## 구문  
  
```  
/Fopathname  
```  
  
## 설명  
 이 옵션을 사용하지 않으면 개체 파일은 소스 파일의 기본 이름과 .obj 확장명을 사용합니다.  원하는 이름과 확장명을 사용할 수 있지만 권장 사항은 .obj를 사용하는 것입니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **출력 파일** 속성 페이지를 클릭합니다.  
  
4.  **개체 파일 이름** 속성을 수정합니다.  개발 환경에서 개체 파일의 확장명으로는 .obj를 사용해야 합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>를 참조하십시오.  
  
## 예제  
 다음 명령줄은 B 드라이브의 기존 디렉터리 \\OBJECT에 THIS.obj라는 이름의 개체 파일을 만듭니다.  
  
```  
CL /FoB:\OBJECT\ THIS.C  
```  
  
## 참고 항목  
 [출력 파일\(\/F\) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)