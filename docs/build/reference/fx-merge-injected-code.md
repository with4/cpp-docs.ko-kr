---
title: "/Fx(삽입된 코드 병합) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.ExpandAttributedSource"
  - "/Fx"
  - "VC.Project.VCCLCompilerTool.ExpandAttributedSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fx 컴파일러 옵션[C++]"
  - "-Fx 컴파일러 옵션[C++]"
  - "삽입된 코드"
  - "삽입된 코드 병합"
  - "/Fx 컴파일러 옵션[C++]"
ms.assetid: 14f0e301-3bab-45a3-bbdf-e7ce66f20560
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /Fx(삽입된 코드 병합)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

삽입된 코드를 소스에 병합하여 각 소스 파일의 복사본을 생성합니다.  
  
## 구문  
  
```  
/Fx  
```  
  
## 설명  
 병합된 소스 파일과 원본 소스 파일을 구분하기 위해 **\/Fx**에서 파일 이름과 확장명 사이에 .mrg 확장명을 추가합니다. 예를 들어 특성 사용 코드를 포함하며 **\/Fx**을 사용하여 빌드한 MyCode.cpp 파일은 다음 코드를 포함하는 MyCode.mrg.cpp라는 파일을 만듭니다.  
  
```  
//+++ Start Injected Code [no_injected_text(true)];      // Suppress injected text, it has // already been injected #pragma warning(disable: 4543) // Suppress warnings about skipping // injected text #pragma warning(disable: 4199) // Suppress warnings from attribute // providers //--- End Injected Code  
```  
  
 .mrg 파일에서 특성 때문에 삽입된 코드는 다음과 같이 구분됩니다.  
  
```  
//+++ Start Injected Code ... //--- End Injected Code  
```  
  
 [no\_injected\_text](../../windows/no-injected-text.md) 특성이 .mrg 파일에 포함되므로 텍스트를 다시 삽입하지 않고 .mrg 파일을 컴파일할 수 있습니다.  
  
 .mrg 소스 파일은 컴파일러에 의해 삽입된 소스 코드를 나타내기 위한 것입니다. .mrg 파일이 원본 소스 파일과 동일하게 컴파일되거나 실행되지 않을 수도 있습니다.  
  
 .mrg 파일에서는 매크로가 확장되지 않습니다.  
  
 프로그램이 삽입된 코드를 사용하는 헤더 파일을 포함하는 경우 **\/Fx**에서 해당 헤더에 대한 .mrg.h 파일을 생성합니다.**\/Fx**은 삽입된 코드를 사용하지 않는 include 파일을 병합하지 않습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하세요.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **출력 파일** 속성 페이지를 클릭합니다.  
  
4.  **특성 사용 소스 확장** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExpandAttributedSource%2A>을 참조하세요.  
  
## 참고 항목  
 [출력 파일\(\/F\) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)