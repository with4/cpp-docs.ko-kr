---
title: "코드 최적화 | Microsoft Docs"
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
helpviewer_keywords: 
  - "cl.exe 컴파일러, 성능"
  - "코드, 최적화"
  - "최적화"
  - "최적화, C++ 코드"
  - "성능, 컴파일러"
  - "성능, 코드 최적화"
ms.assetid: 4f33e6c7-9870-43b3-9c2f-d7e44f764971
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# 코드 최적화
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

실행 파일을 최적화하여 실행 속도는 높이면서 코드 크기는 작게 할 수 있습니다.  이 항목에서는 코드 최적화를 위해 Visual C\+\+에서 제공하는 몇 가지 메커니즘에 대해 설명합니다.  
  
## 언어 기능  
 다음 항목에서는 C\/C\+\+ 언어의 몇 가지 최적화 기능에 대해 설명합니다.  
  
 [최적화 pragma 및 키워드](../../build/reference/optimization-pragmas-and-keywords.md)  
 코드에 사용하여 성능을 향상시킬 수 있는 키워드 및 pragma의 목록입니다.  
  
 [컴파일러 옵션 범주별 목록](../../build/reference/compiler-options-listed-by-category.md)  
 특히 실행 속도나 코드 크기에 영향을 주는 **\/O** 컴파일러의 목록입니다.  
  
 [Rvalue 참조 선언자: &&](../../cpp/rvalue-reference-declarator-amp-amp.md)  
 Rvalue 참조는 *의미 체계 이동*의 구현을 지원합니다.  의미 체계 이동을 사용하여 템플릿 라이브러리를 구현하면 해당 템플릿을 사용하는 응용 프로그램의 성능을 상당히 향상시킬 수 있습니다.  
  
### 최적화 pragma  
 코드의 최적화된 한 섹션으로 인해 오류가 발생하거나 속도가 느려지는 경우에는 [optimize](../../preprocessor/optimize.md) pragma를 사용하여 해당 섹션에 대해 최적화가 적용되지 않도록 할 수 있습니다.  
  
 다음과 같이 두 pragma 사이에 코드를 포함합니다.  
  
```  
#pragma optimize("", off)  
// some code here   
#pragma optimize("", on)  
```  
  
## 프로그래밍 방법  
 또한 최적화와 함께 코드를 컴파일하면 경고 메시지가 나타날 수도 있습니다.  이는 최적화된 코드에만 관련되기 때문이며 예상된 동작입니다.  이러한 경고에 주의하면 여러 가지 최적화 문제를 방지할 수 있습니다.  
  
 프로그램 속도를 향상시키려고 최적화를 했는데 코드가 더 느리게 실행되는 경우도 있습니다.  이는 속도 향상을 위해 최적화하면 코드가 커지는 경우가 있기 때문입니다.  예를 들어 함수를 인라이닝하면 함수 호출의 오버헤드는 제거되지만  너무 많은 코드를 인라이닝하면 프로그램 크기가 너무 커져서 가상 메모리 페이지 폴트가 증가할 수 있습니다.  따라서 함수 호출을 제거함으로써 빨라진 속도가 메모리 스와핑으로 인해 느려질 수 있습니다.  
  
 다음 항목에서는 좋은 프로그래밍 방법에 대해 설명합니다.  
  
 [시간 중심의 코드 성능 향상을 위한 팁](../../build/reference/tips-for-improving-time-critical-code.md)  
 좋은 코딩 방법을 사용하면 성능이 향상될 수 있습니다.  이 항목에서는 시간 중심의 코드 부분 성능을 향상시킬 수 있는 코딩 방법을 설명합니다.  
  
 [최적화를 위한 유용한 정보](../../build/reference/optimization-best-practices.md)  
 응용 프로그램을 가장 적절하게 최적화하는 데 대한 일반 지침을 제공합니다.  
  
## 최적화된 코드 디버깅  
 최적화를 수행하면 컴파일러에 의해 생성된 코드가 변경될 수 있으므로 응용 프로그램을 디버깅하고 성능을 측정한 다음 코드를 최적화하는 것이 좋습니다.  
  
 다음 항목에서는 디버깅 방법에 대한 기본 정보를 제공합니다.  
  
-   [Visual Studio의 디버깅](../Topic/Debugging%20in%20Visual%20Studio.md)  
  
-   [릴리스 빌드를 만들 때의 일반적인 문제](../../build/reference/common-problems-when-creating-a-release-build.md)  
  
 다음 항목에서는 디버깅 방법에 대한 고급 정보를 제공합니다.  
  
-   [방법: 최적화된 코드 디버깅](../Topic/How%20to:%20Debug%20Optimized%20Code.md)  
  
-   [부동 소수점 숫자의 정밀도가 떨어지는 이유](../../build/reference/why-floating-point-numbers-may-lose-precision.md)  
  
 다음 일련의 항목에서는 코드 빌드, 로드 및 실행을 최적화하는 방법에 대한 정보를 제공합니다.  
  
-   [컴파일러 처리량 향상](../../build/reference/improving-compiler-throughput.md)  
  
-   [함수 이름을 \(\) 없이 사용하면 코드가 생성되지 않음](../../build/reference/using-function-name-without-parens-produces-no-code.md)  
  
-   [인라인 어셈블리 최적화](../../assembler/inline/optimizing-inline-assembly.md)  
  
-   [ATL 프로젝트에 대한 컴파일러 최적화 지정](../../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)  
  
-   [로드 시 클라이언트 응용 프로그램의 성능을 향상시키려면 어떤 최적화 기술을 사용해야 합니까?](../../build/what-optimization-techniques-should-i-use.md)  
  
-   DLL 메서드를 로드하는 시간을 줄이는 방법에 대한 [!INCLUDE[crabout](../../build/reference/includes/crabout_md.md)]는 [MSDN Library](http://go.microsoft.com/fwlink/?linkid=556) 웹 사이트의 "MSDN Magazine"에 있는 "Under the Hood" 칼럼의 "Optimizing DLL Load Time Performance"를 참조하십시오.  
  
-   응용 프로그램의 페이징을 최소화하는 방법에 대한 [!INCLUDE[crabout](../../build/reference/includes/crabout_md.md)]는 [MSDN Library](http://go.microsoft.com/fwlink/?linkid=556) 웹 사이트의 "MSDN Magazine"에 있는 "Bugslayer" 칼럼의 "Improving Runtime Performance with the Smooth Working Set Tool" 및 "Improving Runtime Performance with the Smooth Working Set Tool—Part 2"를 참조하십시오.  
  
## 참고 항목  
 [C\/C\+\+ 빌드 참조](../../build/reference/c-cpp-building-reference.md)