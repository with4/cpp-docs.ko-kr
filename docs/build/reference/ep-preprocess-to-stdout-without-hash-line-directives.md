---
title: "/EP(#line 지시문 없이 stdout로 전처리) | Microsoft Docs"
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
  - "/ep"
  - "VC.Project.VCCLCompilerTool.GeneratePreprocessedFileNoLines"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/EP 컴파일러 옵션[C++]"
  - "전처리기 출력을 표준 출력에 복사"
  - "EP 컴파일러 옵션[C++]"
  - "-EP 컴파일러 옵션[C++]"
  - "전처리기 출력, 표준 출력에 복사"
ms.assetid: 6ec411ae-e33d-4ef5-956e-0054635eabea
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /EP(#line 지시문 없이 stdout로 전처리)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C와 C\+\+ 소스 파일을 전처리하고 전처리된 파일을 표준 출력 장치에 복사합니다.  
  
## 구문  
  
```  
/EP  
```  
  
## 설명  
 처리할 때 모든 전처리기 지시문이 실행되고 매크로가 확장되며 주석이 제거됩니다.  전처리된 결과에 주석을 보존하려면 **\/EP** 옵션과 함께 [\/C\(전처리 중에 주석 유지\)](../../build/reference/c-preserve-comments-during-preprocessing.md) 옵션을 사용하십시오.  
  
 **\/EP** 옵션을 사용하면 컴파일이 수행되지 않습니다.  컴파일에 필요한 사전 처리된 파일을 다시 전송해야 합니다.  또한 **\/EP**를 사용하면 **\/FA**, **\/Fa** 및 **\/Fm** 옵션을 사용해도 출력 파일이 생성되지 않습니다.  자세한 내용은 [\/FA, \/Fa\(목록 파일\)](../../build/reference/fa-fa-listing-file.md) 및 [\/Fm\(맵 파일 이름 지정\)](../../build/reference/fm-name-mapfile.md)를 참조하십시오.  
  
 처리 후반 단계에서 발생하는 오류는 원래 소스 파일 대신 전처리된 파일의 줄 번호를 참조합니다.  원래 소스 파일의 줄 번호를 참조하려면 대신 [\/E\(stdout으로 전처리\)](../../build/reference/e-preprocess-to-stdout.md) 옵션을 사용하십시오.  **\/E** 옵션을 사용하면 원래 소스 파일의 줄 번호를 참조하도록 `#line` 지시문이 출력에 추가됩니다.  
  
 `#line` 지시문과 함께 전처리된 출력을 파일로 보내려면 대신 [\/P\(파일 전처리\)](../../build/reference/p-preprocess-to-a-file.md) 옵션을 사용하십시오.  
  
 `#line` 지시문과 함께 전처리된 출력을 stdout로 보내려면 **\/P** 옵션과 **\/EP** 옵션을 함께 사용하십시오.  
  
 **\/EP** 옵션을 사용할 경우에는 미리 컴파일된 헤더를 사용할 수 없습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **전처리기** 속성 페이지를 클릭합니다.  
  
4.  **전처리 파일 생성** 속성을 변경합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>를 참조하십시오.  
  
## 예제  
 다음 명령줄을 실행하면 `ADD.C` 파일을 전처리하고 주석을 그대로 유지하고 표준 출력 장치에 결과를 표시합니다.  
  
```  
CL /EP /C ADD.C  
```  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)