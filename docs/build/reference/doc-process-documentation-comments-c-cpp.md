---
title: "/doc(문서 주석 처리)(C/C++) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles"
  - "/doc"
  - "VC.Project.VCCLCompilerTool.XMLDocumentationFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/doc 컴파일러 옵션[C++]"
  - "주석, C++ 코드"
  - "-doc 컴파일러 옵션[C++]"
  - "XML 문서, 소스 파일의 주석"
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /doc(문서 주석 처리)(C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러가 소스 코드 파일의 문서 주석을 처리할 수 있도록 하고 문서 주석이 있는 각 소스 코드 파일에 대해 .xdc 파일을 만들 수 있도록 합니다.  
  
## 구문  
  
```  
/doc[name]  
```  
  
## 인수  
 `name`  
 컴파일러가 만드는 .xdc 파일의 이름입니다.  문서에 .cpp 파일 하나를 전달한 경우에만 유효합니다.  
  
## 설명  
 .xdc 파일은 xdcmake.exe를 사용하여 .xml 파일로 처리됩니다.  자세한 내용은 [XDCMake 참조](../../ide/xdcmake-reference.md)을 참조하십시오.  
  
 소스 코드 파일에 문서 주석을 추가할 수 있습니다.  자세한 내용은 [문서 주석에 대한 권장 태그](../../ide/recommended-tags-for-documentation-comments-visual-cpp.md)을 참조하십시오.  
  
 **\/doc**이 **\/clr:oldSyntax**과 호환되지 않는 경우.  자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)를 참조하십시오.  
  
 생성된 .xml 파일을 IntelliSense와 함께 사용하려면, .xml 파일의 파일 이름을 지원하려는 어셈블리와 같도록 설정한 다음 해당 .xml 파일을 어셈블리와 같은 디렉터리에 넣습니다.  Visual Studio 프로젝트에서 이 어셈블리가 참조되는 경우에는 해당 .xml 파일도 함께 찾습니다.  자세한 내용은 [IntelliSense 사용](../Topic/Using%20IntelliSense.md) 및 [XML 코드 주석 제공](../Topic/Supplying%20XML%20Code%20Comments.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **C\/C\+\+** 노드를 확장합니다.  
  
4.  **출력 파일** 속성 페이지를 선택합니다.  
  
5.  **XML 문서 파일 생성** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)