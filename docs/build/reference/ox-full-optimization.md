---
title: "/Ox(최대 최적화) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.ToolOptimization"
  - "/ox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Ox 컴파일러 옵션[C++]"
  - "빠른 코드"
  - "최대 최적화"
  - "Ox 컴파일러 옵션[C++]"
  - "-Ox 컴파일러 옵션[C++]"
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /Ox(최대 최적화)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Ox** 컴파일러 옵션은 코드 크기를 줄이기보다는 실행 속도를 향상시키는 코드를 만듭니다.  
  
## 구문  
  
```  
/Ox  
```  
  
## 설명  
 **\/Ox** 컴파일러 옵션을 지정하는 것은 다음 옵션을 사용하는 것과 같습니다.  
  
-   옵션 매개 변수가 2\(**\/Ob2**\)인 [\/Ob\(인라인 함수 확장\)](../../build/reference/ob-inline-function-expansion.md)  
  
-   [\/Og\(전역 최적화\)](../../build/reference/og-global-optimizations.md)  
  
-   [\/Oi\(내장 함수 만들기\)](../../build/reference/oi-generate-intrinsic-functions.md)  
  
-   [\/Ot\(코드 속도 우선\)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)  
  
-   [\/Oy\(프레임 포인터 생략\)](../../build/reference/oy-frame-pointer-omission.md)  
  
 **\/Ox**는 다음과 함께 사용할 수 없습니다.  
  
-   [\/O1\(크기 최소화\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)  
  
-   [\/O2\(속도 최대화\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)  
  
-   [\/Od\(디버그 비활성화\)](../../build/reference/od-disable-debug.md)  
  
 **\/Ox** 컴파일러 옵션을 사용하면 스택 기반 반환 값의 복사 생성자와 소멸자를 제거하는 명명된 반환 값 최적화도 활성화됩니다.  자세한 내용은 [\/O1, \/O2\(크기 최소화, 속도 최대화\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)을 참조하십시오.  
  
 **\/Ox** 컴파일러 옵션과 [\/Os\(코드 크기 우선\)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)를 조합하는 **\/Oxs**를 지정하는 경우 **\/Ox** 컴파일러 옵션을 취소할 수 있습니다.  조합된 옵션은 코드 크기를 우선합니다.  
  
 일반적으로 **\/Ox** 대신 [\/O2\(속도 최대화\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)를 지정하고, **\/Oxs** 대신 [\/O1\(크기 최소화\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)을 지정합니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **최적화** 속성 페이지를 클릭합니다.  
  
4.  **최적화** 속성을 변경합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>를 참조하십시오.  
  
## 참고 항목  
 [\/O 옵션\(코드 최적화\)](../../build/reference/o-options-optimize-code.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)