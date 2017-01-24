---
title: "/Gm(최소 다시 빌드 사용) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.MinimalRebuild"
  - "/Gm"
  - "/FD"
  - "VC.Project.VCCLWCECompilerTool.MinimalRebuild"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gm 컴파일러 옵션[C++]"
  - "최소 재빌드 사용 컴파일러 옵션[C++]"
  - "Gm 컴파일러 옵션[C++]"
  - "-Gm 컴파일러 옵션[C++]"
  - "최소 다시 빌드"
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Gm(최소 다시 빌드 사용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

변경된 C\+\+ 클래스 정의\(헤더 파일\(.h\)에 저장됨\)가 포함된 C\+\+ 소스 파일을 다시 컴파일해야 할지 여부를 결정하는 최소 다시 빌드가 가능하도록 설정합니다.  
  
## 구문  
  
```  
/Gm  
```  
  
## 설명  
 컴파일러는 첫 번째 컴파일 중 소스 파일과 .idb 파일의 클래스 정의 간의 종속성 정보를 저장합니다.  종속성 정보는 어떤 소스 파일이 어떤 클래스 정의에 종속되어 있는지 그리고 어떤 .h 파일에 정의가 위치해 있는지 알려줍니다. 소스 파일에 수정된 .h 파일이 포함되어 있는 경우라도 후속 컴파일에서는 .idb 파일에 저장된 정보를 사용하여 소스 파일을 컴파일해야 할지를 결정합니다.  
  
> [!NOTE]
>  최소 다시 빌드는 포함 파일 간에 변경되지 않는 클래스 정의를 사용합니다.  .idb 파일의 종속성 정보는 전체 프로젝트에 대해 생성되므로 클래스 정의는 프로젝트에 대해 전역적이어야 합니다\(지정된 클래스에 대해서는 정의가 하나만 있어야 함\).  프로젝트에 클래스 정의가 두 개 이상 있는 경우 최소 다시 빌드를 사용하지 마세요.  
  
 Incremental Linker는 [\/ZW\(Windows Runtime 컴파일\)](../../build/reference/zw-windows-runtime-compilation.md) 옵션을 사용하여 .obj 파일에 포함된 Windows 메타데이터를 지원하지 않으므로 **\/Gm** 옵션은 **\/ZW**와 호환되지 않습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **코드 생성** 속성 페이지를 클릭합니다.  
  
4.  **최소 다시 빌드 가능** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild%2A>을 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)