---
title: "/Wp64(64비트 이식성 문제 검색) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems"
  - "VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems"
  - "/wp64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Wp64 컴파일러 옵션[C++]"
  - "64비트 컴파일러[C++], 이식성 문제 검색"
  - "Wp64 컴파일러 옵션[C++]"
  - "-Wp64 컴파일러 옵션[C++]"
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# /Wp64(64비트 이식성 문제 검색)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 컴파일러 옵션은 더 이상 사용되지 않습니다. Visual Studio 2013 이전 버전에서는 [\_\_w64](../../cpp/w64.md) 키워드로도 표시된 형식에서 64비트 이식성 문제를 검색합니다.  
  
## 구문  
  
```  
/Wp64  
```  
  
## 설명  
 기본적으로 Visual Studio 2013 이전 버전에서는 **\/Wp64** 컴파일러 옵션이 Visual C\+\+ 32비트 컴파일러에서는 꺼져 있고 Visual C\+\+ 64비트 컴파일러에서는 켜져 있습니다.  
  
> [!IMPORTANT]
>  [\/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md) 컴파일러 옵션 및 [\_\_w64](../../cpp/w64.md) 키워드는 Visual Studio 2010 및 Visual Studio 2012에서 더 이상 사용되지 않으며 Visual Studio 2013부터는 지원되지 않습니다. 이 스위치를 사용하는 프로젝트를 변환하면 변환 중에 스위치가 마이그레이션되지 않습니다. Visual Studio 2010 또는 Visual Studio 2012에서 이 옵션을 사용하려면 프로젝트 속성의 **명령줄** 섹션에서 **추가 옵션** 아래에 컴파일러 스위치를 입력해야 합니다. 명령줄에서 **\/Wp64** 컴파일러 옵션을 사용하면 컴파일러에서 명령줄 경고 D9002를 표시합니다. 64비트 이식성 문제를 검색하기 위해 이 옵션과 키워드를 사용하는 대신 64비트 플랫폼을 대상으로 하는 Visual C\+\+ 컴파일러를 사용하고 [\/W4](../../build/reference/compiler-option-warning-level.md) 옵션을 지정합니다. 자세한 내용은 [64비트용 프로그램 구성](../../build/configuring-programs-for-64-bit-visual-cpp.md)을 참조하세요.  
  
 다음 유형의 변수는 64비트 운영 체제에서 사용되는 것처럼 32비트 운영 체제에서 테스트됩니다.  
  
-   int  
  
-   long  
  
-   포인터  
  
 64비트 컴파일러를 사용하여 응용 프로그램을 정기적으로 컴파일하는 경우 64비트 컴파일러가 모든 문제를 검색하므로 32비트 컴파일에서는 **\/Wp64**를 사용하지 않도록 설정하면 됩니다. Windows 64비트 운영 체제를 대상으로 지정하는 방법에 대한 자세한 내용은 [64비트용 프로그램 구성](../../build/configuring-programs-for-64-bit-visual-cpp.md)을 참조하세요.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다.  
  
     자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하세요.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **\/Wp64**를 포함하도록 **추가 옵션** 상자의 내용을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>를 참조하세요.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [64비트용 프로그램 구성](../../build/configuring-programs-for-64-bit-visual-cpp.md)