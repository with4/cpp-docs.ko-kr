---
title: OpenMP에서 동시성 런타임으로 마이그레이션 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Concurrency Runtime, migrating from OpenMP
- OpenMP, migrating to the Concurrency Runtime
ms.assetid: 9bab7bb1-e45d-44b2-8509-3b226be2c93b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 16e10287526e6b815ba56183a8e3d590102507aa
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690490"
---
# <a name="migrating-from-openmp-to-the-concurrency-runtime"></a>OpenMP에서 동시성 런타임으로 마이그레이션
동시성 런타임은 다양한 프로그래밍 모델을 사용합니다. 이러한 모델은 중복되거나 다른 라이브러리의 모델을 보완할 수 있습니다. 이 문서의 섹션 비교 [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp) 에서 동시성 런타임으로 고 동시성 런타임을 사용 하기 위해 기존 OpenMP 코드를 마이그레이션하는 방법에 대 한 예제를 제공 합니다.  
  
 OpenMP 프로그래밍 모델은 공개 표준에 의해 정의되며, Fortran 및 C/C++ 프로그래밍 언어에 대한 잘 정의된 바인딩을 가지고 있습니다. OpenMP 2.0 버전 2.5에서는 Visual c + + 컴파일러에서 지원 되는 병렬 알고리즘은 반복; 적합 즉, 데이터의 배열에 대해 병렬 반복을 수행 합니다. OpenMP 3.0 반복적인 작업 외에도 비 반복 작업을 지원합니다.  
  
 OpenMP는 병렬 처리 수준이 미리 결정되어 있고 시스템에서 사용 가능한 리소스와 일치할 때 가장 효율적입니다. OpenMP 모델은 매우 큰 계산 문제가 한 컴퓨터의 처리 리소스는 분산 고성능 컴퓨팅 특히 적합 합니다. 이 시나리오에서는 일반적으로 하드웨어 환경 고정 되어 있고 개발자는 알고리즘이 실행 될 때 모든 컴퓨팅 리소스에 대 한 단독 액세스를 가질 수 있습니다.  
  
 그러나 제한 된 컴퓨팅 환경을 덜 아니어야 OpenMP에 적합 합니다. 예를 들어 재귀 문제 (예: quicksort 알고리즘 또는 데이터의 트리를 검색 합니다.)는 OpenMP 2.0 및 2.5를 사용 하 여 구현 하기가 더 어렵습니다. 동시성 런타임은 OpenMP의 기능을 제공 하 여 보완는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 및 [병렬 패턴 라이브러리](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL). 비동기 에이전트 라이브러리 정교 하지 않은 작업 병렬 처리;를 지원합니다. PPL 더 세분화 된 병렬 작업을 지원합니다. 동시성 런타임은 응용 프로그램의 논리에 집중할 수 있도록 병렬에서 작업을 수행 하는 데 필요한 인프라를 제공 합니다. 그러나 수 있기 때문에 동시성 런타임을 사용 하면 다양 한 프로그래밍 모델, 예약 오버 헤드가 OpenMP 등의 다른 동시성 라이브러리 보다 큽니다. 따라서, 성능을 테스트 하는 증분 동시성 런타임을 사용 하기 위해 기존 OpenMP 코드를 변환 하는 것이 좋습니다.  
  
## <a name="when-to-migrate-from-openmp-to-the-concurrency-runtime"></a>OpenMP에서 동시성 런타임으로 마이그레이션 시기  
 다음과 같은 경우에 동시성 런타임을 사용 하기 위해 기존 OpenMP 코드를 마이그레이션하는 것이 도움이 수도 있습니다.  
  
|Cases|동시성 런타임의 이점|  
|-----------|-------------------------------------------|  
|확장 된 동시 프로그래밍 프레임 워크에 필요합니다.|동시성 런타임의 기능 중 다수는 확장 가능합니다. 기존 기능을 결합하여 새 기능을 구성할 수도 있습니다. OpenMP 컴파일러 지시문을 사용 하기 쉽게 확장할 수 없습니다.|  
|응용 프로그램에서 협조적 차단 것이 좋습니다.|동시성 런타임 작업이 차단 되는 아직 사용할 수 없는 리소스를 필요 하기 때문에, 첫 번째 작업은 리소스를 기다리는 동안 다른 작업 수행할 수 있습니다.|  
|응용 프로그램에서 동적 부하 분산 것이 좋습니다.|동시성 런타임 작업 변화에 따른 컴퓨팅 리소스의 할당을 조정 하는 일정 알고리즘을 사용 합니다. OpenMP 스케줄러를 병렬 영역에 컴퓨팅 리소스를 할당 하면 해당 리소스 할당이 계산 전체적 고정 됩니다.|  
|예외 처리를 지 원하는 필요 합니다.|PPL의 병렬 영역 또는 루프 외부 및 내부 예외를 catch 수 있습니다. Openmp에서는 병렬 영역 또는 루프 내부 예외를 처리 해야 합니다.|  
|취소 메커니즘이 필요합니다.|PPL에는 개별 작업 및 작업의 병렬 트리 모두를 취소 하려면 응용 프로그램이 있습니다. OpenMP 취소 메커니즘을 구현 하는 응용 프로그램을 필요 합니다.|  
|병렬 코드 시작 되는 각기 다른 컨텍스트에서 완료 하는 데 필요 합니다.|동시성 런타임을 사용 하면 하나의 컨텍스트에서 작업을 시작 하 고 다음 대기 하거나 다른 컨텍스트에서 해당 작업을 취소할 수 있습니다. OpenMP에서는 시작 하는 컨텍스트에서 모든 병렬 작업이 완료 되어야 합니다.|  
|향상 된 디버깅 지원이 필요합니다.|Visual Studio에서 제공 된 **병렬 스택** 및 **병렬 작업** windows 다중 스레드 응용 프로그램을 보다 쉽게 디버깅할 수 있도록 합니다.<br /><br /> 동시성 런타임에 대 한 디버깅 지원에 대 한 자세한 내용은 참조 [작업 창을 사용 하 여](/visualstudio/debugger/using-the-tasks-window), [병렬 스택 창을 사용 하 여](/visualstudio/debugger/using-the-parallel-stacks-window), 및 [연습: 병렬 디버깅 응용 프로그램](/visualstudio/debugger/walkthrough-debugging-a-parallel-application)합니다.|  
  
## <a name="when-not-to-migrate-from-openmp-to-the-concurrency-runtime"></a>OpenMP에서 동시성 런타임으로 마이그레이션 하지 않는 경우  
 동시성 런타임을 사용 하기 위해 기존 OpenMP 코드 마이그레이션에 적합 하지 않을 때 다음과 같은 경우에 설명 합니다.  
  
|Cases|설명|  
|-----------|-----------------|  
|요구 사항을 충족 하는 응용 프로그램에 이미 있습니다.|응용 프로그램 성능 및 현재 디버깅 지원 만족 하는 경우 마이그레이션 적절 한 아닐 수 있습니다.|  
|병렬 루프 본문이 약간의 작업을 수행합니다.|동시성 런타임 작업 스케줄러의 오버 헤드는 특히 루프 본문은 상대적으로 작은 경우 병렬로 루프 본문이 실행의 이점 크지 않을 수 있습니다.|  
|C에서 작성 된 응용 프로그램|동시성 런타임에서 다양 한 c + + 기능을 사용 하므로 아닐 적합 한 C 응용 프로그램에 완벽 하 게 사용 하 여 코드를 쓸 수 없는 경우.|  
  
## <a name="related-topics"></a>관련 항목  
 [방법: 동시성 런타임을 사용하기 위해 OpenMP parallel for 루프 변환](../../parallel/concrt/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime.md)  

 OpenMP를 사용 하는 기본 루프가 지정 된 [병렬](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) 및 [에 대 한](../../parallel/openmp/reference/for-openmp.md) 지시문 동시성 런타임을 사용 하도록 변환 하는 방법을 보여 줍니다. [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) 알고리즘입니다.  

  
 [방법: 동시성 런타임을 사용하기 위해 취소를 사용하는 OpenMP 루프 변환](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)  
 OpenMP 지정 [병렬](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[에 대 한](../../parallel/openmp/reference/for-openmp.md) 루프를 실행 하려면 모든 반복 하지 않아도 되는 동시성 런타임에서 취소 메커니즘을 사용 하도록 변환 하는 방법을 보여 줍니다.  
  
 [방법: 동시성 런타임을 사용하기 위해 예외 처리를 사용하는 OpenMP 루프 변환](../../parallel/concrt/convert-an-openmp-loop-that uses-exception-handling.md)  
 OpenMP 지정 [병렬](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[에 대 한](../../parallel/openmp/reference/for-openmp.md) 예외 처리를 수행 하는 루프에는 동시성 런타임에서 예외 처리 메커니즘을 사용 하도록 변환 하는 방법을 보여 줍니다.  
  
 [방법: 동시성 런타임을 사용하기 위해 환산 변수를 사용하는 OpenMP 루프 변환](../../parallel/concrt/convert-an-openmp-loop-that-uses-a-reduction-variable.md)  
 OpenMP 지정 [병렬](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[에 대 한](../../parallel/openmp/reference/for-openmp.md) 루프를 사용 하는 [감소](../../parallel/openmp/reference/reduction.md) 절에 동시성 런타임을 사용 하도록 변환 하는 방법을 보여 줍니다.  
  
## <a name="see-also"></a>참고 항목  
 [동시성 런타임](../../parallel/concrt/concurrency-runtime.md)   
 [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp)   
 [PPL(병렬 패턴 라이브러리)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)

