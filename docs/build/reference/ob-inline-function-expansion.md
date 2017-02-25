---
title: "/Ob(인라인 함수 확장) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.InlineFunctionExpansion"
  - "VC.Project.VCCLCompilerTool.InlineFunctionExpansion"
  - "/ob"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Ob 컴파일러 옵션[C++]"
  - "/Ob0 컴파일러 옵션[C++]"
  - "/Ob1 컴파일러 옵션[C++]"
  - "/Ob2 컴파일러 옵션[C++]"
  - "모든 적절한 컴파일러 옵션[C++]"
  - "비활성화 컴파일러 옵션[C++]"
  - "인라인 확장, 컴파일러 옵션"
  - "인라인 함수, 함수 확장 컴파일러 옵션[C++]"
  - "Ob 컴파일러 옵션[C++]"
  - "-Ob 컴파일러 옵션[C++]"
  - "Ob0 컴파일러 옵션[C++]"
  - "-Ob0 컴파일러 옵션[C++]"
  - "Ob1 컴파일러 옵션[C++]"
  - "-Ob1 컴파일러 옵션[C++]"
  - "Ob2 컴파일러 옵션[C++]"
  - "-Ob2 컴파일러 옵션[C++]"
  - "only __inline 컴파일러 옵션[C++]"
ms.assetid: f134e6df-e939-4980-a01d-47425dbc562a
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /Ob(인라인 함수 확장)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

함수의 인라인 확장을 제어합니다.  
  
## 구문  
  
```  
/Ob{0|1|2}  
```  
  
## 인수  
 **0**  
 인라인 확장을 사용하지 않도록 설정합니다.  기본적으로 확장은 컴파일러의 판단에 따라 모든 함수에서 발생하며, 이를 *auto\-inlining*이라고 합니다.  
  
 **1**  
 [inline](../../misc/inline-inline-forceinline.md), [\_\_inline](../../misc/inline-inline-forceinline.md) 또는 [\_\_forceinline](../../misc/inline-inline-forceinline.md)으로 표시된 함수나 클래스 선언에 정의된 C\+\+ 멤버 함수만 확장합니다.  
  
 **2**  
 기본값입니다.  `inline`, `__inline` 또는 `__forceinline`으로 표시된 함수와 컴파일러에서 선택한 기타 함수를 확장합니다.  
  
 **\/Ob2**는 [\/O1, \/O2\(크기 최소화, 속도 최대화\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) 또는 [\/Ox\(최대 최적화\)](../../build/reference/ox-full-optimization.md)를 사용할 때 적용됩니다.  
  
 이 옵션을 적용하려면 **\/O1**, **\/O2**, **\/Ox** 또는 **\/Og**를 사용하여 최적화를 활성화해야 합니다.  
  
## 설명  
 컴파일러는 인라인 확장 옵션과 키워드를 제안으로 처리합니다.  함수가 인라인 확장된다는 보장은 없습니다.  인라인 확장을 사용하지 않을 수 있으나 `__forceinline` 키워드를 사용하는 경우에도 컴파일러가 강제로 특정 함수를 인라인 확장하도록 할 수는 없습니다.  
  
 `#pragma` [auto\_inline](../../preprocessor/auto-inline.md) 지시문을 사용하여 함수가 인라인 확장 후보 고려 대상에서 제외되도록 할 수 있습니다.  `#pragma` [내장](../../preprocessor/intrinsic.md) 지시문도 참조하세요.  
  
> [!NOTE]
>  프로파일링 테스트 실행에서 수집되는 정보는 **\/Ob**, **\/Os** 또는 **\/Ot**를 지정하는 경우 적용되는 최적화를 재정의합니다.  자세한 내용은 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)를 참조하세요.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)을 참조하세요.  
  
2.  **구성 속성**, **C\/C\+\+**를 확장하고 **최적화**를 선택합니다.  
  
3.  **인라인 함수 확장** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion%2A>을 참조하세요.  
  
## 참고 항목  
 [\/O 옵션\(코드 최적화\)](../../build/reference/o-options-optimize-code.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)