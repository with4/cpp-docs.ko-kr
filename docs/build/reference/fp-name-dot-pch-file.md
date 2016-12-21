---
title: "/Fp(.Pch 파일 이름 지정) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.PrecompiledHeaderFile"
  - "/fp"
  - "VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch 파일, 명명"
  - "/Fp 컴파일러 옵션[C++]"
  - "Fp 컴파일러 옵션[C++]"
  - "-Fp 컴파일러 옵션[C++]"
  - "이름[C++], PCH"
  - "전처리 컴파일러 헤더 파일 이름 지정"
  - "PCH 파일, 명명"
  - "미리 컴파일된 헤더 파일, 명명"
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fp(.Pch 파일 이름 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 경로 이름을 사용하는 대신 미리 컴파일된 헤더의 경로 이름을 지정합니다.  
  
## 구문  
  
```  
/Fppathname  
```  
  
## 설명  
 기본 경로 이름을 사용하는 대신 미리 컴파일된 헤더의 경로 이름을 제공하려면 이 옵션을 [\/Yc\(미리 컴파일된 헤더 파일 만들기\)](../../build/reference/yc-create-precompiled-header-file.md) 또는 [\/Yu\(미리 컴파일된 헤더 파일 사용\)](../../build/reference/yu-use-precompiled-header-file.md)와 함께 사용합니다.  또한 **\/Fp**와 **\/Yc**를 함께 사용하면 **\/Yc** `filename` 인수 및 소스 파일의 기본 이름과는 다른 미리 컴파일된 헤더 파일을 사용하도록 지정할 수 있습니다.  
  
 경로 이름의 일부로 확장명을 지정하지 않으면 .pch 확장명이 사용됩니다.  파일 이름 없이 디렉터리만 지정하면 기본 파일 이름인 VC`x`0.pch가 사용되는데, 여기서 `x`는 사용 중인 Visual C\+\+의 주 버전을 나타냅니다.  
  
 **\/Fp** 옵션을 **\/Yu**와 함께 사용할 수도 있습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **미리 컴파일된 헤더** 속성 페이지를 클릭합니다.  
  
4.  **미리 컴파일된 헤더 파일** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderFile%2A>를 참조하십시오.  
  
## 예제  
 프로그램 디버깅 버전용으로 미리 컴파일된 헤더 파일을 만들고 헤더 파일과 소스 코드 모두를 컴파일하는 경우 다음과 같은 명령을 지정할 수 있습니다.  
  
```  
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP  
```  
  
## 예제  
 다음 명령은 MYPCH.pch라는 이름의 미리 컴파일된 헤더 파일을 사용하도록 지정합니다.  컴파일러는 PROG.cpp 안에 있는 소스 코드가 MYAPP.h를 통해 미리 컴파일되었고 컴파일된 코드는 MYPCH.pch에 저장되어 있다고 가정합니다.  컴파일러에서는 MYPCH.pch의 내용을 사용하고 PROG.cpp의 나머지를 컴파일하여 .obj 파일을 만듭니다.  이 예제의 출력은 PROG.exe라는 이름의 파일입니다.  
  
```  
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP  
```  
  
## 참고 항목  
 [출력 파일\(\/F\) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)