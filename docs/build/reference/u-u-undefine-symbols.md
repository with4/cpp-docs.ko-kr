---
title: "/U, /u(기호 정의 해제) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.UndefinePreprocessorDefinitions"
  - "VC.Project.VCCLWCECompilerTool.UndefinePreprocessorDefinitions"
  - "VC.Project.VCCLCompilerTool.UndefineAllPreprocessorDefinitions"
  - "/u"
  - "VC.Project.VCCLWCECompilerTool.UndefineAllPreprocessorDefinitions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/U 컴파일러 옵션[C++]"
  - "U 컴파일러 옵션[C++]"
  - "-U 컴파일러 옵션[C++]"
  - "기호 정의 해제 컴파일러 옵션"
ms.assetid: 7bc0474f-6d1f-419b-807d-0d8816763b2a
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /U, /u(기호 정의 해제)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/U** 컴파일러 옵션은 지정된 전처리기 기호의 정의를 해제합니다.  **\/u** 컴파일러 옵션은 컴파일러가 정의하는 Microsoft 전용 기호의 정의를 해제합니다.  
  
## 구문  
  
```  
/U[ ]symbol  
/u  
```  
  
## 인수  
 `symbol`  
 정의를 해제할 전처리기 기호입니다.  
  
## 설명  
 **\/U** 또는 **\/u** 옵션은 **\#define** 지시문을 사용하여 만든 기호의 정의를 해제할 수 없습니다.  
  
 **\/U** 옵션은 **\/D** 옵션을 사용하여 이전에 정의된 기호의 정의를 해제할 수 있습니다.  
  
 기본적으로 컴파일러는 다음과 같은 Microsoft 전용 기호를 정의합니다.  
  
|기호|Function|  
|--------|--------------|  
|\_CHAR\_UNSIGNED|기본 char 형식은 부호가 없습니다.  [\/J](../../build/reference/j-default-char-type-is-unsigned.md) 옵션을 지정하면 정의됩니다.|  
|\_CPPRTTI|[\/GR](../../build/reference/gr-enable-run-time-type-information.md) 옵션으로 컴파일된 코드에 대해 정의됩니다.|  
|\_CPPUNWIND|[\/EHsc](../../build/reference/eh-exception-handling-model.md) 옵션으로 컴파일된 코드에 대해 정의됩니다.|  
|\_DLL|[\/MD](../../build/reference/md-mt-ld-use-run-time-library.md) 옵션을 지정하면 정의됩니다.|  
|\_M\_IX86|기본적으로 x86 대상에 대해 600으로 정의됩니다.|  
|\_MSC\_VER|자세한 내용은 [미리 정의된 매크로](../../preprocessor/predefined-macros.md)을 참조하십시오.|  
|\_WIN32|WIN32 응용 프로그램에 대해 정의됩니다.  항상 정의되어 있습니다.|  
|\_MT|[\/MD 또는 \/MT](../../build/reference/md-mt-ld-use-run-time-library.md) 옵션을 지정하면 정의됩니다.|  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **고급** 속성 페이지를 클릭합니다.  
  
4.  **전처리기 정의 해제** 또는 **모든 전처리기 정의 해제** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions%2A> 또는 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions%2A>을 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [\/J\(부호 없는 기본 문자 형식\)](../../build/reference/j-default-char-type-is-unsigned.md)   
 [\/GR\(런타임 형식 정보 사용\)](../../build/reference/gr-enable-run-time-type-information.md)   
 [\/EH\(예외 처리 모델\)](../../build/reference/eh-exception-handling-model.md)   
 [\/MD, \/MT, \/LD\(런타임 라이브러리 사용\)](../../build/reference/md-mt-ld-use-run-time-library.md)