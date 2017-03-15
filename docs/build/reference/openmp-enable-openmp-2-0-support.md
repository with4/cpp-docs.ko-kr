---
title: "/openmp(OpenMP 2.0 지원 활성화) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/openmp"
  - "VC.Project.VCCLCompilerTool.OpenMP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/openmp 컴파일러 옵션[C++]"
  - "-openmp 컴파일러 옵션[C++]"
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /openmp(OpenMP 2.0 지원 활성화)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러가 `#pragma` [omp](../../preprocessor/omp.md)를 처리하도록 합니다.  
  
## 구문  
  
```  
/openmp  
```  
  
## 설명  
 `#pragma omp`는 [Directives](../../parallel/openmp/reference/openmp-directives.md) 및 [Clauses](../../parallel/openmp/reference/openmp-clauses.md)를 지정하는데 사용됩니다.  컴파일할 때 **\/openmp**를 지정하지 않으면 컴파일러는 OpenMP 절 및 지시문을 무시합니다.  **\/openmp**를 지정하지 않은 경우에도 컴파일러는 [OpenMP Function](../../parallel/openmp/reference/openmp-functions.md) 호출을 처리합니다.  
  
 [Libraries](../../parallel/openmp/reference/openmp-libraries.md)를 사용하여 **\/openmp**로 컴파일된 응용 프로그램은 Windows 2000 이상의 운영 체제에서만 실행할 수 있습니다.  
  
 **\/openmp** 및 **\/clr**로 컴파일된 응용 프로그램은 단일 응용 프로그램 도메인 프로세스에서만 실행될 수 있습니다. 여러 응용 프로그램 도메인은 지원되지 않습니다.  즉, 모듈 생성자\(.cctor\)가 실행되면 모듈 생성자는 프로세스가 **\/openmp**로 컴파일되었는지 여부 및 응용 프로그램이 기본이 아닌 런타임으로 로드되고 있는지 여부를 감지합니다.  자세한 내용은 [appdomain](../../cpp/appdomain.md), [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 및 [혼합형 어셈블리 초기화](../../dotnet/initialization-of-mixed-assemblies.md)를 참조하십시오.  
  
 **\/openmp** 및 **\/clr**로 컴파일된 응용 프로그램을 기본이 아닌 응용 프로그램 도메인으로 로드하려고 하면 디버거 외부에서는 <xref:System.TypeInitializationException> 예외가 throw되고 디버거에서는 OpenMPWithMultipleAppdomainsException 예외가 throw됩니다.  
  
 이들 예외는 다음과 같은 경우에도 발생할 수 있습니다.  
  
-   **\/clr**로 컴파일되었지만 **\/openmp**는 지정되지 않은 응용 프로그램이 기본이 아닌 응용 프로그램 도메인으로 로드되었고 프로세스에 **\/openmp**로 컴파일된 응용 프로그램이 포함된 경우  
  
-   대상 어셈블리를 기본이 아닌 응용 프로그램 도메인으로 로드하는 regasm.exe\([Regasm.exe\(어셈블리 등록 도구\)](../Topic/Regasm.exe%20\(Assembly%20Registration%20Tool\).md)\)와 같은 유틸리티에 **\/clr** 응용 프로그램을 전달하는 경우  
  
 OpenMP 영역에서는 공용 언어 런타임의 코드 액세스 보안이 작동하지 않습니다.  병렬 영역 외부에서 CLR 코드 액세스 보안 특성을 적용하면 병렬 영역에는 적용되지 않습니다.  
  
 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 또는 기타 CLR 코드 액세스 보안 특성을 통해 부분적으로 신뢰할 수 있는 호출자를 허용하는 **\/openmp** 응용 프로그램은 작성하지 않는 것이 좋습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **C\/C\+\+** 노드를 확장합니다.  
  
4.  **언어** 속성 페이지를 클릭합니다.  
  
5.  **OpenMP 지원** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 threadpool 시작과 threadpool이 시작된 다음 사용하는 것의 효과를 비교하여 보여 줍니다.  x64, 단일 코어, 이중 프로세서의 경우 threadpool이 시작되는 데 약 16밀리초가 걸립니다.  시작된 다음에는 threadpool을 부하가 거의 없이 사용할 수 있습니다.  
  
 **\/openmp**로 컴파일하면 threadpool이 시작되지 않으므로 test2에 대한 두 번째 호출의 실행 시간은 **\/openmp\-**로 컴파일할 때보다 길어질 수 없습니다.  백만번 반복한 결과에서는 test2에 대한 두 번째 호출에서 **\/openmp** 버전이 **\/openmp\-** 버전보다 빠릅니다. 25번 반복한 결과에서는 **\/openmp\-**와 **\/openmp** 모두 측정 가능한 최소 시간 이하로 실행됩니다.  
  
 따라서 응용 프로그램에 루프가 한 개만 있고 이 루프의 실행 시간이 15밀리초\(컴퓨터의 대략적인 부하에 따라 조정\) 미만인 경우 **\/openmp**는 적합하지 않습니다. 그러나 실행 시간이 이보다 긴 경우 **\/openmp**를 사용할 수도 있습니다.  
  
```  
// cpp_compiler_options_openmp.cpp  
#include <omp.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <windows.h>  
  
volatile DWORD dwStart;  
volatile int global = 0;  
  
double test2(int num_steps) {  
   int i;  
   global++;  
   double x, pi, sum = 0.0, step;  
  
   step = 1.0 / (double) num_steps;  
  
   #pragma omp parallel for reduction(+:sum) private(x)  
   for (i = 1; i <= num_steps; i++) {  
      x = (i - 0.5) * step;  
      sum = sum + 4.0 / (1.0 + x*x);  
   }  
  
   pi = step * sum;  
   return pi;  
}  
  
int main(int argc, char* argv[]) {  
   double   d;  
   int n = 1000000;  
  
   if (argc > 1)  
      n = atoi(argv[1]);  
  
   dwStart = GetTickCount();  
   d = test2(n);  
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);  
  
   dwStart = GetTickCount();  
   d = test2(n);  
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);  
}  
```  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)