---
title: "/Zs(구문만 검사) | Microsoft Docs"
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
  - "/zs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zs 컴파일러 옵션[C++]"
  - "구문만 검사 컴파일러 옵션"
  - "Zs 컴파일러 옵션"
  - "-Zs 컴파일러 옵션[C++]"
ms.assetid: b4b41e6a-3f41-4d09-9cb6-fde5aa2cfecf
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zs(구문만 검사)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

명령줄에서 소스 파일의 구문만 검사하도록 컴파일러에 지시합니다.  
  
## 구문  
  
```  
/Zs  
```  
  
## 설명  
 이 옵션을 사용하면 출력 파일이 작성되지 않고 오류 메시지가 표준 출력에 기록됩니다.  
  
 **\/Zs** 옵션은 소스 파일을 컴파일 및 링크하기 전에 구문 오류를 찾아 수정할 수 있는 가장 빠른 방법입니다.  
  
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