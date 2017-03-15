---
title: "/Oi(내장 함수 만들기) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions"
  - "/oi"
  - "VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Oi 컴파일러 옵션[C++]"
  - "내장 함수 만들기 컴파일러 옵션[C++]"
  - "내장 함수, 생성"
  - "Oi 컴파일러 옵션[C++]"
  - "-Oi 컴파일러 옵션[C++]"
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /Oi(내장 함수 만들기)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

응용 프로그램이 더욱 빠르게 실행되도록 일부 함수 호출을 내장 함수나 특정 형태의 함수로 교체합니다.  
  
## 구문  
  
```  
/Oi[-]  
```  
  
## 설명  
 내장 함수를 사용하는 프로그램은 함수 호출의 오버헤드가 없기 때문에 빠르게 실행되지만 추가 코드를 만들기 때문에 프로그램이 커질 수 있습니다.  
  
 내장 형식이 있는 함수에 대한 자세한 내용은 [내장](../../preprocessor/intrinsic.md)을 참조하십시오.  
  
 **\/Oi**는 일부 함수 호출을 내장 형식으로 바꾸도록 컴파일러에 요청하는 역할만 합니다. 컴파일러는 더 높은 성능이 발휘되는 결과에 따라 함수 호출을 내장 형식으로 바꾸지 않고 함수를 그대로 호출할 수 있습니다.  
  
 **x86 전용**  
  
 내장 부동 소수점 함수는 입력값에 대해 특별한 검사를 수행하지 않으므로 제한된 입력 범위에서 작동하고, 동일한 이름의 라이브러리 루틴과 다른 예외 처리 및 경계 조건을 사용합니다.  실제 내장 형식을 사용하면 IEEE 예외 처리와 `_matherr` 및 `errno` 기능을 사용할 수 없습니다. 이러한 기능을 사용할 수 없으면 ANSI와 호환되지 않습니다.  그러나 내장 형식을 사용하면 부동 소수점을 주로 사용하는 프로그램의 속도를 크게 높일 수 있습니다. 대부분의 프로그램에서 호환성 문제는 크게 중요하지 않습니다.  
  
 [Za](../../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션을 사용하여 실제 내장 부동 소수점 옵션의 생성을 재정의할 수 있습니다.  이 경우에는 함수가 인수를 프로그램 스택으로 푸시하는 대신 부동 소수점 칩으로 직접 전달하는 라이브러리 루틴으로 생성됩니다.  
  
 **END x86 Specific**  
  
 [내장](../../preprocessor/intrinsic.md)을 사용하여 내장 함수를 만들거나 [함수](../../preprocessor/function-c-cpp.md)을 사용하여 함수를 명시적으로 호출할 수도 있습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **최적화** 속성 페이지를 클릭합니다.  
  
4.  **내장 함수 사용** 속성을 변경합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>를 참조하십시오.  
  
## 참고 항목  
 [\/O 옵션\(코드 최적화\)](../../build/reference/o-options-optimize-code.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [컴파일러 내장 함수](../../intrinsics/compiler-intrinsics.md)