---
title: "OpenMP에서 동시성 런타임으로 마이그레이션 | Microsoft Docs"
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
  - "동시성 런타임, OpenMP에서 마이그레이션"
  - "OpenMP, 동시성 런타임으로 마이그레이션"
ms.assetid: 9bab7bb1-e45d-44b2-8509-3b226be2c93b
caps.latest.revision: 12
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP에서 동시성 런타임으로 마이그레이션
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

동시성 런타임은 다양한 프로그래밍 모델을 사용할 수 있도록 합니다.  이러한 모델은 다른 라이브러리의 모델을 보완하거나 겹칠 수 있습니다.  이 단원의 문서에서는 [OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md)를 동시성 런타임과 비교하고, 동시성 런타임을 사용하도록 기존 OpenMP 코드를 마이그레이션하는 방법에 대한 예제를 제공합니다.  
  
 OpenMP 프로그래밍 모델은 Open 표준에 정의되어 있으며 Fortran 및 C\/C\+\+ 프로그래밍 언어에 대해 잘 정의된 바인딩이 있습니다.  Visual C\+\+ 컴파일러에서 지원하는 OpenMP 버전 2.0 및 2.5는 반복적인 병렬 알고리즘에 적합합니다. 즉, 데이터 배열에 대한 병렬 반복을 수행합니다.  OpenMP 3.0에서는 반복 작업과 함께 비 반복 작업을 지원합니다.  
  
 OpenMP는 병렬 처리 수준이 미리 결정되고 시스템의 사용 가능한 리소스와 일치하는 경우 가장 효율적입니다.  OpenMP 모델은 매우 큰 계산 문제가 한 컴퓨터의 처리 리소스 전체에 분산되어 있는 고성능 컴퓨팅에 특히 적합합니다.  이 시나리오에서는 하드웨어 환경이 일반적으로 고정되어 있고 개발자는 알고리즘이 실행될 때 모든 컴퓨팅 리소스에 대한 단독 액세스 권한을 가질 수 있습니다.  
  
 그러나 덜 제한된 컴퓨팅 환경은 OpenMP에 적합하지 않을 수 있습니다.  예를 들어 QuickSort 알고리즘 또는 데이터 트리 검색과 같은 재귀적 문제는 OpenMP 2.0 및 2.5를 사용하여 구현하기가 더 어렵습니다.  동시성 런타임은 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 및 PPL\([병렬 패턴 라이브러리](../../parallel/concrt/parallel-patterns-library-ppl.md)\)을 제공하여 OpenMP의 기능을 보완합니다.  비동기 에이전트 라이브러리에서는 정교하지 않은 작업 병렬 처리를 지원하며, PPL에서는 더 세분화된 병렬 작업을 지원합니다.  동시성 런타임에서는 작업을 병렬로 수행하는 데 필요한 인프라를 제공하므로 사용자는 응용 프로그램의 논리에 초점을 맞출 수 있습니다.  그러나 동시성 런타임을 사용하면 다양한 프로그래밍 모델을 사용할 수 있으므로 OpenMP와 같은 다른 동시성 라이브러리보다 예약 오버헤드가 클 수 있습니다.  따라서 동시성 런타임을 사용하기 위해 기존 OpenMP 코드를 변환하는 경우 성능을 증분 방식으로 테스트하는 것이 좋습니다.  
  
## OpenMP에서 동시성 런타임으로 마이그레이션해야 하는 경우  
 다음 사례에서는 동시성 런타임을 사용하도록 기존 OpenMP 코드를 마이그레이션하는 것이 좋을 수 있습니다.  
  
|사례|동시성 런타임의 장점|  
|--------|-----------------|  
|확장 가능한 동시 프로그래밍 프레임워크가 필요한 경우|동시성 런타임에서 제공하는 대부분의 기능은 확장될 수 있습니다.  또한 기존 기능을 결합하여 새 기능을 구성할 수도 있습니다.  OpenMP는 컴파일러 지시문을 사용하므로 쉽게 확장할 수 없습니다.|  
|응용 프로그램에 협조적 차단이 도움이 되는 경우|아직 사용할 수 없는 리소스가 필요하기 때문에 작업이 차단되는 경우 동시성 런타임은 첫 번째 작업이 리소스를 기다리는 동안 다른 작업을 수행할 수 있습니다.|  
|응용 프로그램에 동적 부하 분산이 도움이 되는 경우|동시성 런타임에서는 작업 부하가 변경되는 경우 컴퓨팅 리소스의 할당을 조정하는 예약 알고리즘을 사용합니다.  OpenMP에서는 스케줄러에서 컴퓨팅 리소스를 병렬 영역에 할당하면 해당 리소스 할당이 계산 전체적으로 고정됩니다.|  
|예외 처리 지원이 필요한 경우|PPL을 사용하면 병렬 영역 또는 루프의 내부와 외부 예외를 catch할 수 있습니다.  OpenMP에서는 병렬 영역 또는 루프의 내부 예외를 처리해야 합니다.|  
|취소 메커니즘이 필요한 경우|PPL을 사용하면 응용 프로그램에서 작업\(work\)의 병렬 트리와 개별 작업\(task\)을 취소할 수 있습니다.  OpenMP의 경우에는 응용 프로그램에서 고유 취소 메커니즘을 구현해야 합니다.|  
|병렬 코드가 시작되는 컨텍스트와 다른 컨텍스트에서 끝나야 하는 경우|동시성 런타임을 사용하면 하나의 컨텍스트에서 작업을 시작한 다음 다른 컨텍스트에서 해당 작업을 기다리거나 취소할 수 있습니다.  OpenMP에서는 모든 병렬 작업이 시작되는 컨텍스트에서 끝나야 합니다.|  
|고급 디버깅 지원이 필요한 경우|Visual Studio에서는 **병렬 스택** 창과 **병렬 작업** 창을 제공하므로 다중 스레드 응용 프로그램을 더 쉽게 디버깅할 수 있습니다.<br /><br /> 동시성 런타임 지원 디버깅에 대한 자세한 내용은 [작업 창 사용](../Topic/Using%20the%20Tasks%20Window.md), [병렬 스택 창 사용](../Topic/Using%20the%20Parallel%20Stacks%20Window.md) 및 [연습: 병렬 응용 프로그램 디버깅](../Topic/Walkthrough:%20Debugging%20a%20Parallel%20Application.md)을 참조하십시오.|  
  
## OpenMP에서 동시성 런타임으로 마이그레이션하지 말아야 하는 경우  
 다음 사례에서는 동시성 런타임을 사용하도록 기존 OpenMP 코드를 마이그레이션하는 것이 적합하지 않을 수 있는 경우에 대해 설명합니다.  
  
|사례|설명|  
|--------|--------|  
|응용 프로그램이 이미 요구 사항을 충족하는 경우|응용 프로그램 성능 및 현재 디버깅 지원에 만족하는 경우 마이그레이션이 적합하지 않을 수 있습니다.|  
|병렬 루프 본문이 거의 작업을 수행하지 않는 경우|특히 루프 본문이 비교적 작은 경우에는 동시성 런타임 작업 스케줄러의 오버헤드가 루프 본문을 병렬로 실행하여 얻는 이점보다 크지 않을 수 있습니다.|  
|응용 프로그램이 C 언어로 작성된 경우|동시성 런타임에서는 여러 C\+\+ 기능을 사용하므로 C 응용 프로그램에서 해당 기능을 모두 사용하도록 설정하는 코드를 작성할 수 없는 경우에는 동시성 런타임이 적합하지 않을 수 있습니다.|  
  
## 관련 항목  
 [방법: 동시성 런타임을 사용하기 위해 OpenMP parallel for 루프 변환](../../parallel/concrt/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime.md)  
 OpenMP [parallel](../../parallel/openmp/reference/parallel.md) 및 [for](../../parallel/openmp/reference/for-openmp.md) 지시문을 사용하는 기본 루프가 제공된 경우 동시성 런타임 [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) 알고리즘을 사용하도록 해당 루프를 변환하는 방법을 보여 줍니다.  
  
 [방법: 동시성 런타임을 사용하기 위해 취소를 사용하는 OpenMP 루프 변환](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)  
 모든 반복을 실행해야 할 필요는 없는 OpenMP [parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md) 루프가 지정된 경우 동시성 런타임 취소 메커니즘을 사용하도록 해당 루프를 변환하는 방법을 보여 줍니다.  
  
 [방법: 동시성 런타임을 사용하기 위해 예외 처리를 사용하는 OpenMP 루프 변환](../../parallel/concrt/convert-an-openmp-loop-that uses-exception-handling.md)  
 예외 처리를 수행하는 OpenMP [parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md) 루프가 지정된 경우 동시성 런타임 예외 처리 메커니즘을 사용하도록 해당 루프를 변환하는 방법을 보여 줍니다.  
  
 [방법: 동시성 런타임을 사용하기 위해 환산 변수를 사용하는 OpenMP 루프 변환](../../parallel/concrt/convert-an-openmp-loop-that-uses-a-reduction-variable.md)  
 [reduction](../../parallel/openmp/reference/reduction.md) 절을 사용하는 OpenMP [parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md) 루프가 지정된 경우 동시성 런타임을 사용하도록 해당 루프를 변환하는 방법을 보여 줍니다.  
  
## 참고 항목  
 [동시성 런타임](../../parallel/concrt/concurrency-runtime.md)   
 [OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md)   
 [PPL\(병렬 패턴 라이브러리\)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)