---
title: "동시성 런타임의 유용한 일반 정보 | Microsoft Docs"
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
  - "동시성 런타임, 유용한 일반 정보"
ms.assetid: ce5c784c-051e-44a6-be84-8b3e1139c18b
caps.latest.revision: 16
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 동시성 런타임의 유용한 일반 정보
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 동시성 런타임의 여러 영역에 적용되는 유용한 정보에 대해 설명합니다.  
  
##  <a name="top"></a> 단원  
 이 문서에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [가능한 경우 협력 동기화 구문 사용](#synchronization)  
  
-   [결과가 없는 긴 작업은 허용하지 않음](#yield)  
  
-   [초과 구독을 사용하여 차단되거나 대기 시간이 긴 작업 오프셋](#oversubscription)  
  
-   [가능한 경우 동시 메모리 관리 함수 사용](#memory)  
  
-   [RAII을 사용하여 동시성 개체의 수명 관리](#raii)  
  
-   [전역 범위에서 동시성 개체를 만들지 않음](#global-scope)  
  
-   [공유 데이터 세그먼트에서 동시성 개체를 사용하지 않음](#shared-data)  
  
##  <a name="synchronization"></a> 가능한 경우 협력 동기화 구문 사용  
 동시성 런타임에서는 외부 동기화 개체가 필요 없는 여러 개의 동시성이 보장되는 구문을 제공합니다.  예를 들어 [concurrency::concurrent\_vector](../../parallel/concrt/reference/concurrent-vector-class.md) 클래스에서는 동시성이 보장되는 추가 및 요소 액세스 작업을 제공합니다.  그러나 리소스에 대한 단독 액세스가 필요한 경우 런타임에서 [Concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md), [concurrency::reader\_writer\_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) 및 [concurrency::event](../../parallel/concrt/reference/event-class.md) 클래스를 제공합니다.  이러한 형식은 협조적으로 동작하므로 첫 번째 작업이 데이터를 기다릴 때 작업 스케줄러에서 다른 컨텍스트에 처리 리소스를 다시 할당할 수 있습니다.  가능한 경우 Windows API에서 제공하며 협조적으로 동작하지 않는 메커니즘과 같은 다른 동기화 메커니즘 대신 이 동기화 형식을 사용하십시오.  이러한 동기화 형식과 코드 예제에 대한 자세한 내용은 [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md) 및 [동기화 데이터 구조와 Windows API의 비교](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)를 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="yield"></a> 결과가 없는 긴 작업은 허용하지 않음  
 작업 스케줄러가 협조적으로 동작하므로 작업 간에 공평하지 않습니다.  따라서 특정 작업으로 인해 다른 작업이 시작되지 않을 수 있습니다.  이러한 상황이 허용되는 경우도 있지만 교착 또는 고갈 상태가 발생하는 경우도 있습니다.  
  
 다음 예제에서는 할당된 처리 리소스 수보다 많은 작업을 수행합니다.  첫 번째 작업은 작업 스케줄러에 양보하지 않으므로 첫 번째 작업이 완료될 때까지 두 번째 작업이 시작되지 않습니다.  
  
 [!code-cpp[concrt-cooperative-tasks#1](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_1.cpp)]  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
 1: 250000000 1: 500000000 1: 750000000 1: 1000000000 2: 250000000 2: 500000000 2: 750000000 2: 1000000000  
  
 두 작업 간에 협조되도록 하는 여러 방법이 있습니다.  이 중 하나는 장기 실행 작업에서 작업 스케줄러에 때때로 양보하는 것입니다.  다음 예제에서는 다른 작업이 실행될 수 있도록 작업 스케줄러에 실행을 양보하는 [concurrency::Context::Yield](../Topic/Context::Yield%20Method.md) 메서드를 호출하도록 `task` 함수를 수정합니다.  
  
 [!code-cpp[concrt-cooperative-tasks#2](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_2.cpp)]  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
  **1: 250000000**  
**2: 250000000**  
**1: 500000000**  
**2: 500000000**  
**1: 750000000**  
**2: 750000000**  
**1: 1000000000**  
**2: 1000000000** `Context::Yield` 메서드는 현재 스레드가 속해 있는 스케줄러의 다른 활성 스레드, 간단한 작업 또는 다른 운영 체제 스레드만 생성합니다.  이 메서드는 [concurrency::task\_group](../Topic/task_group%20Class.md) 또는 [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md) 개체에서 실행되도록 예약되어 있지만 아직 시작되지 않은 작업에 양보하지 않습니다.  
  
 장기 실행 작업 간에 협조되도록 하는 다른 방법이 있습니다.  큰 작업은 작은 하위 작업으로 나눌 수 있습니다.  긴 작업이 실행되는 동안 초과 구독을 사용하도록 설정할 수 있습니다.  초과 구독을 사용하면 사용 가능한 하드웨어 수보다 많은 스레드를 만들 수 있습니다.  초과 구독은 긴 작업에 디스크 또는 네트워크 연결에서 데이터를 읽는 등의 긴 대기 시간이 포함되어 있는 경우 특히 유용합니다.  간단한 작업 및 초과 구독에 대한 자세한 내용은 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)를 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="oversubscription"></a> 초과 구독을 사용하여 차단되거나 대기 시간이 긴 작업 오프셋  
 동시성 런타임에서는 작업이 서로 협조적으로 차단하고 양보할 수 있도록 하는 [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md)과 같은 동기화 기본 형식을 제공합니다.  하나의 작업이 협조적으로 차단하거나 양보하는 경우 첫 번째 작업이 데이터를 기다릴 때 작업 스케줄러에서 다른 컨텍스트에 처리 리소스를 다시 할당할 수 있습니다.  
  
 동시성 런타임에서 제공하는 협조적 차단 메커니즘을 사용할 수 없는 경우가 있습니다.  예를 들어 사용하는 외부 라이브러리에서 다른 동기화 메커니즘을 사용할 수 있습니다.  Windows API `ReadFile` 함수를 사용하여 데이터 또는 네트워크 연결에서 데이터를 읽는 경우와 같이 대기 시간이 길 수 있는 작업을 수행하는 경우를 다른 예로 들 수 있습니다.  이러한 경우 초과 구독을 사용하여 다른 작업이 유휴 상태일 때 또 다른 작업이 실행되도록 설정할 수 있습니다.  초과 구독을 사용하면 사용 가능한 하드웨어 수보다 많은 스레드를 만들 수 있습니다.  
  
 지정된 URL에서 파일을 다운로드하는 `download` 함수를 살펴봅니다.  이 예제에서는 [concurrency::Context::Oversubscribe](../Topic/Context::Oversubscribe%20Method.md) 메서드를 사용하여 활성 스레드 수를 임시로 증가시킵니다.  
  
 [!code-cpp[concrt-download-oversubscription#4](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_3.cpp)]  
  
 `GetHttpFile` 함수는 잠재적으로 숨어 있는 작업을 수행하므로 초과 구독을 통해 현재 작업이 데이터를 기다릴 때 다른 작업이 실행되도록 할 수 있습니다.  이 예제의 전체 버전은 [방법: 초과 구독을 사용하여 대기 오프셋](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)을 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="memory"></a> 가능한 경우 동시 메모리 관리 함수 사용  
 비교적 수명이 짧은 작은 개체를 자주 할당하는 세분화된 작업이 있는 경우 [concurrency::Alloc](../Topic/Alloc%20Function.md) 및 [concurrency::Free](../Topic/Free%20Function.md)와 같은 메모리 관리 함수를 사용합니다.  동시성 런타임은 각 실행 스레드를 위해 별도의 메모리 캐시를 보유합니다.  `Alloc` 및 `Free` 함수는 잠금 또는 메모리 차단을 사용하지 않고도 이러한 캐시에서 메모리를 해제하거나 할당합니다.  
  
 이러한 메모리 관리 함수에 대한 자세한 내용은 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)를 참조하십시오.  이러한 함수를 사용하는 예제를 보려면 [방법: Alloc 및 Free를 사용하여 메모리 성능 개선](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)을 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="raii"></a> RAII을 사용하여 동시성 개체의 수명 관리  
 동시성 런타임은 예외 처리를 사용하여 취소와 같은 기능을 구현합니다.  따라서 런타임을 호출하는 경우 또는 런타임을 호출하는 다른 라이브러리를 호출하는 경우 예외로부터 안전한 코드를 작성하십시오.  
  
 RAII\(*Resource Acquisition Is Initialization*\) 패턴은 지정된 범위에서 동시성 개체의 수명을 안전하게 관리하는 한 가지 방법입니다.  RAII 패턴에서는 데이터 구조가 스택에 할당됩니다.  이러한 데이터 구조는 만들어질 때 리소스를 초기화하거나 획득하고, 소멸될 때 리소스를 소멸시키거나 해제합니다.  RAII 패턴을 사용하면 바깥쪽 범위를 벗어나기 전에 소멸자가 호출됩니다.  이 패턴은 함수에 `return` 문이 여러 개 포함된 경우에 유용합니다.  또한 이 패턴을 사용하여 예외로부터 안전한 코드를 작성할 수 있습니다.  `throw` 문으로 인해 스택이 해제되면 RAII 개체의 소멸자가 호출되므로 리소스가 항상 올바르게 삭제되거나 해제됩니다.  
  
 런타임은 RAII 패턴을 사용하는 [concurrency::critical\_section::scoped\_lock](../Topic/critical_section::scoped_lock%20Class.md) 및 [concurrency::reader\_writer\_lock::scoped\_lock](../Topic/reader_writer_lock::scoped_lock%20Class.md)과 같은 여러 클래스를 정의합니다.  이러한 도우미 클래스를 *범위 지정 잠금*이라고 합니다.  이러한 클래스는 [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) 또는 [concurrency::reader\_writer\_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) 개체를 사용할 때 여러 가지 이점을 제공합니다.  이러한 클래스의 생성자는 제공된 `critical_section` 또는 `reader_writer_lock` 개체에 대한 액세스 권한을 얻고 소멸자는 해당 개체에 대한 액세스를 해제합니다.  범위 지정 잠금은 상호 제외 개체가 삭제될 때 해당 개체에 대한 액세스를 자동으로 해제하므로 내부 개체의 잠금을 수동으로 해제하지 않습니다.  
  
 외부 라이브러리에서 정의되기 때문에 수정할 수 없는 `account` 클래스를 살펴봅니다.  
  
 [!code-cpp[concrt-account-transactions#1](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_4.h)]  
  
 다음 예제에서는 `account` 개체에 대한 여러 트랜잭션을 병렬로 수행합니다.  `account` 클래스는 동시성이 보장되지 않으므로 이 예제에서는 `critical_section` 개체를 사용하여 `account` 개체에 대한 액세스를 동기화합니다.  각 병렬 작업은 `critical_section::scoped_lock` 개체를 사용하여 작업이 성공하거나 실패할 때 `critical_section` 개체가 잠금 해제되도록 합니다.  계정 잔고가 마이너스일 경우 예외를 throw하여 `withdraw` 작업이 실패합니다.  
  
 [!code-cpp[concrt-account-transactions#2](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_5.cpp)]  
  
 이 예제를 실행하면 다음과 같은 샘플 결과가 출력됩니다.  
  
  **입금 전 잔액: 1924**  
**입금 후 잔액: 2924**  
**출금 전 잔액: 2924**  
**인출 후 잔액:\-76**  
**출금 전 잔액: \-76**  
**오류 정보:**  
 **음수 잔액:\-76** RAII 패턴을 사용하여 동시성 개체의 수명을 관리하는 추가 예제를 보려면 [연습: 사용자 인터페이스 스레드에서 작업 제거](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md), [방법: 컨텍스트 클래스를 사용하여 공동 작업 세마포 구현](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md) 및 [방법: 초과 구독을 사용하여 대기 오프셋](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)을 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="global-scope"></a> 전역 범위에서 동시성 개체를 만들지 않음  
 전역 범위에서 동시성 개체를 만들 때 교착 상태 나 메모리 액세스 위반 등의 문제는 응용 프로그램에서 발생할 수 있습니다.  
  
 예를 들어, 동시성 런타임 개체를 만드는 경우 런타임은 아직 만들어지지 않은 기본 스케줄러를 생성합니다.  전역 개체 생성시 생성되는 런타임 개체가 그에 따라 런타임이 기본 스케줄러를 작성하게됩니다.  그러나 이 프로세스에는 내부 잠금이 사용되므로 동시성 런타임 인프라를 지원하는 다른 개체의 초기화를 방해할 수 있습니다.  이 내부 잠금은 아직 초기화되지 않은 다른 인프라 개체가 필요할 수 있기 때문에 교착 상태는 응용 프로그램에서 발생할 수 있습니다.  
  
 다음 예제에서는 전역 [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) 개체를 만드는 방법을 보여 줍니다.  이 패턴은 `Scheduler` 클래스뿐 아니라 동시성 런타임에서 제공하는 다른 모든 형식에 적용됩니다.  응용 프로그램에서 예기치 않은 동작이 발생할 수 있기 때문에 이 패턴을 따라하지 않는 것이 좋습니다.  
  
 [!code-cpp[concrt-global-scheduler#1](../../parallel/concrt/codesnippet/CPP/general-best-practices-in-the-concurrency-runtime_6.cpp)]  
  
 `Scheduler` 개체를 만드는 올바른 방법의 예제를 보려면 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)를 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="shared-data"></a> 공유 데이터 세그먼트에서 동시성 개체를 사용하지 않음  
 동시성 런타임에서는 [data\_seg](../../preprocessor/data-seg.md) `#pragma` 지시문을 통해 생성되는 데이터 섹션과 같은 공유 데이터 섹션에 동시성 개체를 사용하도록 지원하지 않습니다.  프로세스 경계 간에 공유되는 동시성 개체는 런타임을 일관성 없거나 잘못된 상태에 둘 수 있습니다.  
  
 \[[맨 위](#top)\]  
  
## 참고 항목  
 [동시성 런타임 유용한 정보](../../parallel/concrt/concurrency-runtime-best-practices.md)   
 [PPL\(병렬 패턴 라이브러리\)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)   
 [동기화 데이터 구조와 Windows API의 비교](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)   
 [방법: Alloc 및 Free를 사용하여 메모리 성능 개선](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)   
 [방법: 초과 구독을 사용하여 대기 오프셋](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)   
 [방법: 컨텍스트 클래스를 사용하여 공동 작업 세마포 구현](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)   
 [연습: 사용자 인터페이스 스레드에서 작업 제거](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)   
 [병렬 패턴 라이브러리의 유용한 정보](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)   
 [비동기 에이전트 라이브러리의 모범 사례](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)