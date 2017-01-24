---
title: "/bigobj(.Obj 파일의 섹션 수 늘리기) | Microsoft Docs"
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
  - "/bigobj"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/bigobj 컴파일러 옵션[C++]"
  - "bigobj 컴파일러 옵션[C++]"
  - "-bigobj 컴파일러 옵션[C++]"
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /bigobj(.Obj 파일의 섹션 수 늘리기)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/bigobj**는 개체 파일에 포함할 수 있는 섹션의 수를 늘립니다.  
  
## 구문  
  
```  
/bigobj  
```  
  
## 설명  
 기본적으로 개체 파일에서는 주소 지정 가능한 섹션을 최대 65,536\(2^16\)개까지 보유할 수 있습니다.  대상 플랫폼이 지정되는 것에 상관이 없는 경우입니다.  **\/bigobj**를 사용하면 이 주소 용량을 4,294,967,296\(2^32\)개까지 늘릴 수 있습니다.  
  
 대부분의 모듈에서는 65,536개보다 많은 섹션이 포함된 .obj 파일을 생성하지 않습니다.  그러나 컴퓨터에서 생성된 코드 또는 템플릿 라이브러리 사용량이 많은 코드의 경우 더 많은 섹션을 보유 가능한 .obj 파일이 필요할 수 있습니다.  **\/bigobj** 는 시스템에서 많은 수의 헤더를 포함하는 XAML 코드를 생성하므로 기본적으로 Windows 스토어 프로젝트에 의해 사용됩니다.  Windows 스토어 앱 프로젝트에서 이 옵션을 사용할 수 없다면 컴파일러 오류 C1128이 발생한 경우일 것 입니다.  
  
 Visual C\+\+ 2005 이전 버전과 함께 제공되는 링커에서는 **\/bigobj**를 사용하여 생성한 .obj 파일을 읽을 수 없습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)