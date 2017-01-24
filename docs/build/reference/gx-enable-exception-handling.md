---
title: "/GX(예외 처리 사용) | Microsoft Docs"
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
  - "/gx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GX 컴파일러 옵션[C++]"
  - "cl.exe 컴파일러, 예외 처리"
  - "예외 처리 활성화 컴파일러 옵션[C++]"
  - "예외 처리, 사용"
  - "GX 컴파일러 옵션[C++]"
  - "-GX 컴파일러 옵션[C++]"
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
caps.latest.revision: 16
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /GX(예외 처리 사용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`extern` C 함수가 예외를 throw하지 않는다는 가정 하에 동기 예외 처리를 활성화합니다.  
  
## 구문  
  
```  
/GX  
```  
  
## 설명  
 이 옵션은 [\/EH\(예외 처리 모델\)](../../build/reference/eh-exception-handling-model.md)와 같습니다.  
  
 개발 환경 내에서 컴파일할 때는 기본적으로 **\/GX**가 사용됩니다.  명령줄 도구를 사용할 때는 기본적으로 **\/GX\-**가 사용됩니다.  
  
 자세한 내용은 [C\+\+ 예외 처리](../../cpp/cpp-exception-handling.md)을 참조하십시오.  
  
 **\/GX**는 사용되지 않으며 대신 [\/EH\(예외 처리 모델\)](../../build/reference/eh-exception-handling-model.md)를 사용합니다.  자세한 내용은 [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ko-kr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)을 참조하십시오.  
  
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