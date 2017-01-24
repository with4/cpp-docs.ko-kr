---
title: "방법: 동시성 런타임을 사용하기 위해 취소를 사용하는 OpenMP 루프 변환 | Microsoft Docs"
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
  - "OpenMP에서 동시성 런타임으로 변환, 취소"
  - "취소, OpenMP에서 동시성 런타임으로 변환"
ms.assetid: 4b0b3c33-bfa9-4e96-ae08-aef245a39cbb
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 동시성 런타임을 사용하기 위해 취소를 사용하는 OpenMP 루프 변환
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

일부 병렬 루프의 경우에는 모든 반복을 실행할 필요가 없습니다.  예를 들어 값을 검색하는 알고리즘은 값을 찾은 후에 종료될 수 있습니다.  OpenMP에서는 병렬 루프를 벗어나는 메커니즘을 제공하지 않습니다.  그러나 부울 값 또는 플래그를 사용하여 루프 반복이 솔루션을 찾았음을 나타내도록 할 수 있습니다.  동시성 런타임에서는 하나의 작업이 아직 시작되지 않은 다른 작업을 취소할 수 있게 하는 기능을 제공합니다.  
  
 이 예제에서는 동시성 런타임 취소 메커니즘을 사용하기 위해 모든 반복을 실행해야 할 필요는 없는 OpenMP [parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md) 루프를 변환하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서는 OpenMP 및 동시성 런타임을 사용하여 병렬 버전의 [std::any\_of](../Topic/any_of.md) 알고리즘을 구현합니다.  이 예제의 OpenMP 버전에서는 플래그를 사용하여 조건이 충족된 모든 병렬 루프 반복 간에 조정합니다.  동시성 런타임을 사용하는 버전에서는 조건이 충족되는 경우 [concurrency::Concurrency::structured\_task\_group::cancel](../Topic/structured_task_group::cancel%20Method.md) 메서드를 사용하여 전체 작업을 중지합니다.  
  
 [!code-cpp[concrt-openmp#2](../../parallel/concrt/codesnippet/CPP/convert-an-openmp-loop-that-uses-cancellation_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **OpenMP를 사용하여...**  
**9114046은 배열안에 있습니다.**  
**\[동시성 런타임\] 사용**  
**9114046은 배열안에 있습니다.** OpenMP를 사용하는 버전에서는 플래그가 설정된 경우에도 루프의 모든 반복이 실행됩니다.  또한 작업에 자식 작업이 포함될 예정인 경우 취소를 알릴 수 있도록 해당 자식 작업에서도 플래그를 사용할 수 있어야 합니다.  동시성 런타임에서 작업 그룹을 취소하면 런타임에서 자식 작업을 비롯한 전체 작업 트리를 취소합니다.  [concurrency::Concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) 알고리즘은 작업\(task\)을 사용하여 작업\(work\)을 수행합니다.  따라서 루프의 한 반복에서 루트 작업을 취소하면 전체 계산 트리도 취소됩니다.  작업\(work\) 트리를 취소하면 런타임에서 새 작업\(task\)을 시작하지 않습니다.  그러나 런타임에서는 이미 시작된 작업이 끝나도록 허용합니다.  따라서 `parallel_for_each` 알고리즘의 경우 활성 루프 반복이 해당 리소스를 정리할 수 있습니다.  
  
 이 예제의 두 버전에서 배열에 검색할 값의 복사본이 두 개 이상 있으면 여러 루프 반복에서 각각 동시에 결과를 설정하고 전체 작업을 취소할 수 있습니다.  조건이 충족될 때 하나의 작업만 수행되어야 하는 경우 임계 영역과 같은 동기화 기본 형식을 사용할 수 있습니다.  
  
 PPL을 사용하는 작업을 취소하는 데 예외 처리를 사용할 수도 있습니다.  취소에 대한 자세한 내용은 [취소](../../parallel/concrt/cancellation-in-the-ppl.md)를 참조하십시오.  
  
 `parallel_for_each` 및 기타 병렬 알고리즘에 대한 자세한 내용은 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)을 참조하십시오.  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `concrt-omp-parallel-any-of.cpp` 파일에 붙여 넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-parallel\-any\-of.cpp**  
  
## 참고 항목  
 [OpenMP에서 동시성 런타임으로 마이그레이션](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [취소](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)