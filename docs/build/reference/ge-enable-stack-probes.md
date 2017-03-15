---
title: "/Ge(스택 조사 사용) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/ge"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Ge 컴파일러 옵션[C++]"
  - "스택 조사 사용"
  - "Ge 컴파일러 옵션[C++]"
  - "-Ge 컴파일러 옵션[C++]"
  - "스택 확인 호출"
  - "스택 조사"
  - "스택, 스택 조사"
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /Ge(스택 조사 사용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

로컬 변수를 저장할 저장소를 요청하는 모든 함수 호출에 대해 스택 프로브를 활성화할 수 있습니다.  
  
## 구문  
  
```  
/Ge  
```  
  
## 설명  
 이러한 메커니즘은 스택 프로브의 기능을 다시 작성할 때 유용합니다.  스택 프로브를 다시 작성하는 대신 [\/Gh\(\_penter 후크 함수 사용\)](../../build/reference/gh-enable-penter-hook-function.md)를 사용하는 것이 좋습니다.  
  
 [\/Gs\(스택 검사 호출 제어\)](../../build/reference/gs-control-stack-checking-calls.md)를 사용해도 결과는 같습니다.  
  
 **\/Ge**는 사용되지 않습니다. 컴파일러가 스택 검사를 생성합니다.  자세한 내용은 [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ko-kr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)을 참조하십시오.  
  
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