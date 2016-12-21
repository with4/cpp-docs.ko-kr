---
title: "/Fm(맵 파일 이름 지정) | Microsoft Docs"
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
  - "/fm"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fm 컴파일러 옵션[C++]"
  - "파일[C++], 맵 만들기"
  - "Fm 컴파일러 옵션[C++]"
  - "-Fm 컴파일러 옵션[C++]"
  - "맵 파일[C++], 링커 만들기"
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fm(맵 파일 이름 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

링커에서 해당 .exe 파일이나 DLL에 나타나는 순서대로 구성된 세그먼트 목록을 포함하는 맵 파일을 만들도록 지정합니다.  
  
## 구문  
  
```  
/Fmpathname  
```  
  
## 설명  
 기본적으로 맵 파일의 이름은 해당 C 또는 C\+\+ 소스 파일의 기본 이름과 .MAP 확장명을 사용하여 지정됩니다.  
  
 **\/Fm**을 지정하는 것은 [\/MAP\(맵파일 생성\)](../../build/reference/map-generate-mapfile.md) 링커 옵션을 지정하는 것과 같은 효과가 있습니다.  
  
 링크하지 않도록 [\/c\(링크 없이 컴파일\)](../../build/reference/c-compile-without-linking.md)를 지정한 경우에는 **\/Fm**이 효과가 없습니다.  
  
 컴파일러가 선행 밑줄을 변수 이름에 추가하기 때문에 대개 맵 파일의 전역 기호에는 하나 이상의 선행 밑줄이 있습니다.  맵 파일에 표시되는 많은 전역 기호는 컴파일러와 표준 라이브러리에서 내부적으로 사용합니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [출력 파일\(\/F\) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)