---
title: "/P(파일 전처리) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.GeneratePreprocessedFile"
  - "/p"
  - "VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/P 컴파일러 옵션[C++]"
  - "출력 파일, 전처리기"
  - "P 컴파일러 옵션[C++]"
  - "-P 컴파일러 옵션[C++]"
  - "출력 파일 전처리"
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /P(파일 전처리)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C 및 C\+\+ 소스 파일을 전처리하고 전처리된 출력을 파일에 씁니다.  
  
## 구문  
  
```  
/P  
```  
  
## 설명  
 파일의 기본 이름은 소스 파일과 동일하고 확장명은 .i입니다.  처리할 때 모든 전처리기 지시문이 실행되고 매크로가 확장되며 주석이 제거됩니다.  전처리된 결과에 주석을 보존하려면 **\/P** 옵션과 함께 [\/C\(전처리 중에 주석 유지\)](../../build/reference/c-preserve-comments-during-preprocessing.md) 옵션을 사용하십시오.  
  
 **\/P** 옵션을 사용하면 포함된 파일의 시작과 끝에 그리고 조건적 컴파일을 위해 전처리기 지시문에 의해 제거된 줄에 `#line` 지시문이 추가됩니다.  이 지시문은 전처리된 파일의 행 번호를 다시 지정합니다.  따라서 프로세스의 뒷 단계에서 발생한 오류는 전처리된 파일의 줄이 아닌 원본 소스 파일의 줄 번호를 참조합니다.  `#line` 지시문이 생성되지 않도록 하려면 **\/P** 옵션과 함께 [\/EP\(\#line 지시문 없이 stdout로 전처리\)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) 옵션을 사용하십시오.  
  
 **\/P** 옵션을 사용하면 컴파일이 수행되지 않습니다.  따라서 [\/Fo\(개체 파일 이름\)](../../build/reference/fo-object-file-name.md) 옵션을 사용해도 .obj 파일이 만들어지지 않습니다.  컴파일에 필요한 사전 처리된 파일을 다시 전송해야 합니다.  또한 **\/P**를 사용하면 **\/FA**, **\/Fa** 및 **\/Fm** 옵션을 사용해도 출력 파일이 생성되지 않습니다.  자세한 내용은 [\/FA, \/Fa\(목록 파일\)](../../build/reference/fa-fa-listing-file.md) 및 [\/Fm\(맵 파일 이름 지정\)](../../build/reference/fm-name-mapfile.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **전처리기** 속성 페이지를 클릭합니다.  
  
4.  **전처리 파일 생성** 속성을 변경합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>를 참조하십시오.  
  
## 예제  
 다음 명령줄은 `ADD.C`를 전처리하고 주석을 보존하며 `#line` 지시문을 추가한 다음 결과를 `ADD.I` 파일에 씁니다.  
  
```  
CL /P /C ADD.C  
```  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [\/Fi \(출력 파일 이름 전처리\)](../../build/reference/fi-preprocess-output-file-name.md)