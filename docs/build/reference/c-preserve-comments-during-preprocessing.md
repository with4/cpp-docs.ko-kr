---
title: "/C(전처리 중에 주석 유지) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.KeepComments"
  - "/c"
  - "VC.Project.VCCLWCECompilerTool.KeepComments"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/c 컴파일러 옵션[C++]"
  - "c 컴파일러 옵션[C++]"
  - "-c 컴파일러 옵션[C++]"
  - "주석, 전처리 중 제거 안 함"
  - "전처리하는 동안 주석 유지"
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /C(전처리 중에 주석 유지)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

전처리하는 동안 주석을 유지합니다.  
  
## 구문  
  
```  
/C  
```  
  
## 설명  
 이 컴파일러 옵션은 **\/E**, **\/P** 또는 **\/EP** 옵션과 함께 사용해야 합니다.  
  
 다음 코드 샘플에서는 소스 코드 주석이 표시됩니다.  
  
```  
// C_compiler_option.cpp  
// compile with: /E /C /c  
int i;   // a variable  
```  
  
 이 샘플의 출력 결과는 다음과 같습니다.  
  
```  
#line 1 "C_compiler_option.cpp"  
int i;   // a variable  
```  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **전처리기** 속성 페이지를 클릭합니다.  
  
4.  **주석 유지** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [\/E\(stdout으로 전처리\)](../../build/reference/e-preprocess-to-stdout.md)   
 [\/P\(파일 전처리\)](../../build/reference/p-preprocess-to-a-file.md)   
 [\/EP\(\#line 지시문 없이 stdout로 전처리\)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)