---
title: "/arch(x86) | Microsoft Docs"
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
ms.assetid: 9dd5a75d-06e4-4674-aade-33228486078d
caps.latest.revision: 33
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 33
---
# /arch(x86)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

x86에서 코드 생성 아키텍처를 지정합니다.  [\/arch\(x64\)](../../build/reference/arch-x64.md) 및 [\/arch\(ARM\)](../../build/reference/arch-arm.md)를 참조하세요.  
  
## 구문  
  
```  
/arch:[IA32|SSE|SSE2|AVX|AVX2]  
```  
  
## 인수  
 **\/arch:IA32**  
 고급 명령을 지정하지 않는 반면 부동 소수점 계산을 위해 x87도 지정합니다.  
  
 **\/arch:SSE**  
 SSE 명령을 사용하도록 설정합니다.  
  
 **\/arch:SSE2**  
 SSE2 명령을 사용하도록 설정합니다.  **\/arch** 옵션이 지정되지 않은 경우 x86 플랫폼에서의 기본 명령입니다.  
  
 **\/arch:AVX**  
 Intel Advanced Vector Extensions 명령을 사용하도록 설정합니다.  
  
 **\/arch:AVX2**  
 Intel 고급 벡터 확장 2 명령을 사용하도록 설정합니다.  
  
## 설명  
 SSE 및 SSE2 명령은 다양한 Intel 및 AMD 프로세서에 있습니다.  AVX 명령은 Intel Sandy Bridge 프로세서와 AMD Bulldozer 프로세서에 있습니다.  AVX2 명령은 Intel Haswell 및 Broadwell 프로세서와 AMD Excavator 기반 프로세서에서 지원합니다.  
  
 `_M_IX86_FP`, `__AVX__` 및 `__AVX2__` 매크로는 어떤 **\/arch** 컴파일러 옵션이 사용되었는지 나타냅니다\(사용한 경우\).  자세한 내용은 [미리 정의된 매크로](../../preprocessor/predefined-macros.md)를 참조하세요.  **\/arch:AVX2** 옵션 및 `__AVX2__` 매크로는 Visual Studio 2013 업데이트 2 버전 12.0.34567.1에서 도입되었습니다.  
  
 최적화 프로그램은 **\/arch** 지정 시 SSE 및 SSE2 명령을 사용할 시기와 방법을 선택합니다.  x87 부동 소수점 레지스터 스택 대신 SSE\/SSE2 명령 및 레지스터를 사용하는 게 더 빠르다고 판단하면 최적화 프로그램은 일부 스칼라 부동 소수점 계산에 SSE 및 SSE2 명령을 사용합니다.  따라서 코드에서는 부동 소수점 계산에 x87과 SSE\/SSE2를 둘 다 혼합하여 사용할 수 있습니다.  또한 **\/arch:SSE2**와 함께 SSE2 명령을 일부 64비트 정수 연산에 사용할 수 있습니다.  
  
 SSE 및 SSE2 명령을 사용하는 것 이외에 컴파일러는 SSE 및 SSE2를 지원하는 프로세서 수정 버전에 있는 다른 명령도 사용합니다.  이러한 예로 Intel 프로세서의 Pentium Pro 수정 버전에 처음으로 나타나는 CMOV 명령이 있습니다.  
  
 x86 컴파일러가 기본적으로 SSE2 명령을 사용하는 코드를 생성하므로 **\/arch:IA32**를 지정해서 x86 프로세서에 대한 SSE 및 SSE2 명령을 생성하지 않도록 해야 합니다.  
  
 **\/arch**는 네이티브 함수에 대한 코드 생성에만 영향을 미칩니다.  [\/clr](../../build/reference/clr-common-language-runtime-compilation.md)을 사용하여 컴파일하는 경우 **\/arch**는 관리되는 함수의 코드 생성에 영향을 주지 않습니다.  
  
 **\/arch** 및 [\/QIfist](../../build/reference/qifist-suppress-ftol.md)는 동일한 Compiland에서 사용할 수 없습니다.  특히 FP 제어 단어를 수정하는 데 `_controlfp`를 사용하지 않으면 런타임 시작 코드는 x87 FPU 제어 단어 정밀도 제어 필드를 53비트로 설정합니다.  따라서 식의 모든 float 및 double 연산에서는 53비트 significand와 15비트 지수를 사용합니다.  그러나 SSE 단정밀도 연산에서는 24비트 significand와 8비트 지수를 사용하고 SSE2 배정밀도 연산에서는 53비트 significand 및 11비트 지수를 사용합니다.  자세한 내용은 [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)를 참조하세요.  이러한 차이점은 하나의 식 트리에서도 발생할 수 있지만 각 하위 식 이후 사용자 할당이 수행되는 경우에는 가능하지 않습니다.  다음을 살펴보세요.  
  
```c  
  
r = f1 * f2 + d;  // Different results are possible on SSE/SSE2.  
```  
  
 비교:  
  
```c  
  
t = f1 * f2;   // Do f1 * f2, round to the type of t.  
r = t + d;     // This should produce the same overall result   
               // whether x87 stack is used or SSE/SSE2 is used.  
```  
  
### Visual Studio에서 AVX, AVX2, IA32, SSE 또는 SSE2에 대한 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하세요.  
  
2.  **구성 속성**, **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **코드 생성** 속성 페이지를 선택합니다.  
  
4.  **고급 명령 집합 사용** 속성을 수정합니다  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>을 참조하세요.  
  
## 참고 항목  
 [\/arch\(최소 CPU 아키텍처\)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)