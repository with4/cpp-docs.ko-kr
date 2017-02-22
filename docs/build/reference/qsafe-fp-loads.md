---
title: "/Qsafe_fp_loads | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 2b2ce52d-ba57-4bd3-a739-47a7f8bfaba9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /Qsafe_fp_loads
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 값에 대한 정수 이동 명령을 사용하고 특정 부동 소수점 부하 최적화를 요구하지 않도록 설정합니다.  
  
## 구문  
  
```  
/Qsafe_fp_loads  
```  
  
## 설명  
 **\/Qsafe\_fp\_loads** 는 x86을 대상으로 하는 컴파일러에서 사용 되지만; x64 또는 ARM을 대상으로 하는 컴파일러에서 사용할 수는 없습니다.  
  
 **\/Qsafe\_fp\_loads** 는 컴파일러를 강제로 MMX와 메모리 간에 데이터를 이동시키기 위해 이동 부동 소수점 지침 대신 정수 이동 명령 사용 하도록 합니다.  이 옵션은 로드할 때 값이 예외를 발생할 때 여러 제어 경로에서 로드 될 수 있는 부동 소수점 값에 대한 레지스터 로드 최적화를 비활성화시킵니다. \-예를 들어, NaN 값 등.  
  
 이 옵션은 [\/fp:except](../../build/reference/fp-specify-floating-point-behavior.md)에 의해 재정의됩니다.  **\/Qsafe\_fp\_loads** 는 **\/fp:except**에 의해 지정된 컴파일러 동작의 하위 집합을 지정합니다.  
  
 **\/Qsafe\_fp\_loads**는 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) 및 [\/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md)와 호환 되지 않습니다.  부동 소수점 컴파일러 옵션에 대한 자세한 내용은 [\/fp\(부동 소수점 동작 지정\)](../../build/reference/fp-specify-floating-point-behavior.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [\/Q 옵션\(하위 수준 작업\)](../../build/reference/q-options-low-level-operations.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)