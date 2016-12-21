---
title: "/FR, /Fr(.Sbr 파일 만들기) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.BrowseInformation"
  - "VC.Project.VCCLCompilerTool.BrowseInformation"
  - "/fr"
  - "VC.Project.VCCLCompilerTool.BrowseInformationFile"
  - "VC.Project.VCCLWCECompilerTool.BrowseInformationFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FR 컴파일러 옵션[C++]"
  - "FR 컴파일러 옵션[C++]"
  - "-FR 컴파일러 옵션[C++]"
  - "기호화된 브라우저 정보"
ms.assetid: 3fd8f88b-3924-4feb-9393-287036a28896
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FR, /Fr(.Sbr 파일 만들기)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

.sbr 파일을 만듭니다.  
  
## 구문  
  
```  
/FR[pathname[\filename]]  
/Fr[pathname[\filename]]  
```  
  
## 설명  
 빌드 프로세스 중 Microsoft Browse Information File Maintenance Utility\(BSCMAKE\)는 이러한 파일을 사용하여 찾아보기 정보를 표시하는 데 사용되는 .BSC 파일을 만듭니다.  
  
 **\/FR**은 전체 기호화된 정보를 사용하여 .sbr 파일을 만듭니다.  
  
 **\/Fr**은 지역 변수에 대한 정보 없이.sbr 파일을 만듭니다.  
  
 `filename`을 지정하지 않으면 .sbr 파일은 소스 파일과 동일한 기본 이름을 가져옵니다.  
  
 **\/Fr**은 사용되지 않습니다. 대신 **\/FR**을 사용하세요. 자세한 내용은 [컴파일러 옵션 범주별 목록](../../build/reference/compiler-options-listed-by-category.md)에서 사용되지 않는 컴파일러 옵션을 참조하세요.  
  
> [!NOTE]
>  .sbr 확장명을 변경하지 마세요. BSCMAKE는 해당 확장명을 사용하려면 매개자 파일이 필요합니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하세요.  
  
2.  탐색 창에서 **C\/C\+\+**, **찾아보기 정보** 속성 페이지를 선택합니다.  
  
3.  **찾아보기 정보 파일** 또는 **찾아보기 정보 사용** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformation%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformationFile%2A>을 참조하십시오.  
  
## 참고 항목  
 [출력 파일\(\/F\) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)