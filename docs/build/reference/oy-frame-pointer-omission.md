---
title: "/Oy(프레임 포인터 생략) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.OmitFramePointers"
  - "/oy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Oy 컴파일러 옵션[C++]"
  - "프레임 포인터 생략 컴파일러 옵션[C++]"
  - "프레임 포인터 생략"
  - "Oy 컴파일러 옵션[C++]"
  - "-Oy 컴파일러 옵션[C++]"
  - "스택 프레임 포인터 컴파일러 옵션[C++]"
  - "프레임 포인터 만들기 표시하지 않음"
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Oy(프레임 포인터 생략)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

호출 스택에서 프레임 포인터를 생성하지 않습니다.  
  
## 구문  
  
```  
/Oy[-]  
```  
  
## 설명  
 프레임 포인터를 설정하고 제거할 필요가 없기 때문에 이 옵션을 사용하면 함수 호출 속도가 빨라집니다.  또한 자주 사용되는 변수와 하위 식을 저장하는 데 필요한 레지스터 하나\(Intel 386 이상 버전의 EBP\)도 추가로 확보할 수 있습니다.  
  
 **\/Oy**를 사용하면 프레임 포인터를 생략할 수 있고 **\/Oy\-**를 사용하면 생략이 비활성화됩니다.  **\/Oy**는 x86 컴파일러에서만 사용할 수 있습니다.  
  
 코드에 EBP 기반 주소 지정이 필요하면  **\/Ox** 옵션 다음에 **\/Oy–** 옵션을 지정하거나 [최적화](../../preprocessor/optimize.md)에 "**y**" 및 **off** 인수를 사용하여 EBP 기반 주소 지정을 최대로 최적화할 수 있습니다.  컴파일러가 EBP 기반 주소 지정이 필요한 상황을 대부분 인식합니다. 예를 들어, `_alloca` 및 `setjmp` 함수와 구조적 예외 처리가 있는 경우에 EBP 기반 주소 지정이 필요합니다.  
  
 [\/Ox\(최대 최적화\)](../../build/reference/ox-full-optimization.md) 및 [\/O1, \/O2\(크기 최소화, 속도 최대화\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) 옵션은 **\/Oy**를 내포하고 있습니다.  **\/Ox**, **\/O1** 또는 **\/O2** 옵션 뒤에 **\/Oy–**를 지정하면 **\/Oy**가 명시적인지 암시적인지 여부와 상관없이 이 옵션이 비활성화됩니다.  
  
 **\/Oy** 컴파일러 옵션을 사용하면 컴파일러에서 프레임 포인터 정보가 제한되므로 디버거를 사용하기가 더 어려워집니다.  디버그 컴파일러 옵션\([\/Z7, \/Zi, \/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)\)을 지정하는 경우에는 다른 최적화 컴파일러 옵션 뒤에 **\/Oy\-** 옵션을 지정하는 것이 좋습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **최적화** 속성 페이지를 클릭합니다.  
  
4.  **프레임 포인터 생략** 속성을 변경합니다.  이 속성은 **\/Oy** 옵션만 추가 또는 제거합니다.  **\/Oy\-** 옵션을 추가하려면 **명령줄**을 클릭하고 **추가 옵션**을 수정해야 합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>를 참조하십시오.  
  
## 참고 항목  
 [\/O 옵션\(코드 최적화\)](../../build/reference/o-options-optimize-code.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)