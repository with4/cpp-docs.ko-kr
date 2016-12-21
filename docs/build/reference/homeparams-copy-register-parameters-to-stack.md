---
title: "/homeparams(스택에 레지스터 매개 변수 복사) | Microsoft Docs"
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
  - "/homeparams"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/homeparams 컴파일러 옵션[C++]"
  - "-homeparams 컴파일러 옵션[C++]"
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /homeparams(스택에 레지스터 매개 변수 복사)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

레지스터에 전달된 매개 변수를 함수 시작 시 스택의 해당 위치에 기록합니다.  
  
## 구문  
  
```  
/homeparams  
```  
  
## 설명  
 이 컴파일러 옵션은 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 컴파일러\(네이티브 및 크로스 컴파일\)에만 사용됩니다.  
  
 매개 변수를 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 컴파일에 전달하면 레지스터에 전달된 매개 변수라 해도 호출 규칙에 따라 매개 변수에 대한 스택 공간이 필요합니다.  자세한 내용은 [매개 변수 전달](../../build/parameter-passing.md)을 참조하십시오.  그러나 릴리스 빌드의 경우 기본적으로 레지스터 매개 변수가 스택에서 매개 변수에 이미 제공된 공간에 기록되지 않습니다.  이 경우 프로그램의 최적화된 \(릴리스\) 빌드를 디버깅하기 어렵습니다.  
  
 릴리스 빌드의 경우 **\/homeparams**를 사용하여 응용 프로그램을 디버깅할 수 있도록 해야 합니다.  **\/homeparams**를 사용하면 스택에 레지스터 매개 변수를 로드하기 위한 주기가 필요하므로 성능이 저하될 수 있습니다.  
  
 디버그 빌드에서는 레지스터에 전달된 매개 변수가 항상 스택에 기록됩니다.  
  
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