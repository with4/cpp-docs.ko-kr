---
title: "방법: 동시성 런타임을 사용하기 위해 환산 변수를 사용하는 OpenMP 루프 변환 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenMP에서 동시성 런타임으로 변환, 환산 변수"
  - "환산 변수, OpenMP에서 동시성 런타임으로 변환"
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
caps.latest.revision: 13
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 동시성 런타임을 사용하기 위해 환산 변수를 사용하는 OpenMP 루프 변환
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 예제에서는 동시성 런타임을 사용하도록 [reduction](../../parallel/openmp/reference/reduction.md) 절을 사용하는 OpenMP [parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md) 루프를 변환하는 방법을 보여 줍니다.  
  
 OpenMP `reduction` 절을 사용하면 병렬 영역 끝에서 감소 작업에 적용되는 하나 이상의 스레드\-개인 변수를 지정할 수 있습니다.  OpenMP는 감소 연산자 집합을 미리 정의합니다.  각 감소 변수는 스칼라\(예: `int`, `long` 및 `float`\)여야 합니다.  OpenMP는 병렬 영역에 감소 변수를 사용하는 방법에 대한 몇 가지 제한 사항도 정의합니다.  
  
 PPL\(병렬 패턴 라이브러리\)에서는 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) 클래스를 제공합니다. 이 클래스는 세분화된 계산을 수행한 후 이러한 계산을 최종 결과로 병합하는 데 사용할 수 있는 재사용 가능한 스레드 로컬 저장소를 제공합니다.  `combinable` 클래스는 스칼라 형식 및 복합 형식 모두에 동작하는 템플릿입니다.  `combinable` 클래스를 사용하려면 병렬 구문의 본문에서 하위 계산을 수행한 다음 [concurrency::combinable::combine](../Topic/combinable::combine%20Method.md) or [concurrency::combinable::combine\_each](../Topic/combinable::combine_each%20Method.md) 메서드를 호출하여 최종 결과를 생성합니다.  `combine` 및 `combine_each` 메서드는 각 요소 쌍을 결합하는 방법을 지정하는 *combine 함수*를 사용합니다.  따라서 `combinable` 클래스는 고정된 감소 연산자 집합으로 제한되지 않습니다.  
  
## 예제  
 이 예제에서는 OpenMP 및 동시성 런타임을 사용하여 처음 35개 피보나치\(Fibonacci\) 수의 합계를 계산합니다.  
  
 [!code-cpp[concrt-openmp#7](../../parallel/concrt/codesnippet/CPP/convert-an-openmp-loop-that-uses-a-reduction-variable_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **OpenMP를 사용하여...**  
**먼저 35 피보나치 수의 합계는 14930351입니다.**  
**\[동시성 런타임\] 사용**  
**먼저 35 피보나치 수의 합계는 14930351입니다.** `combinable` 클래스에 대한 자세한 내용은 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)를 참조하십시오.  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `concrt-omp-fibonacci-reduction.cpp` 파일에 붙여 넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-fibonacci\-reduction.cpp**  
  
## 참고 항목  
 [OpenMP에서 동시성 런타임으로 마이그레이션](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)