---
title: "동기화 데이터 구조 | Microsoft Docs"
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
  - "동기화 데이터 구조체"
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# 동기화 데이터 구조
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

동시성 런타임에서는 여러 스레드로부터 공유 데이터에 대한 액세스를 동기화할 수 있는 몇 가지 데이터 구조를 제공합니다.  이러한 데이터 구조는 공유 데이터를 자주 수정하지 않는 경우에 유용합니다.  예를 들어 임계 영역과 같은 동기화 개체를 사용하면 공유 리소스를 사용할 수 있을 때까지 다른 스레드가 기다립니다.  따라서 자주 사용하는 데이터에 대한 액세스를 동기화할 때 이러한 개체를 사용하면 응용 프로그램에서 확장성이 저하될 수 있습니다.  [PPL\(병렬 패턴 라이브러리\)](../../parallel/concrt/parallel-patterns-library-ppl.md)에서는 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) 클래스를 제공합니다. 이 클래스를 사용하면 동기화할 필요 없이 여러 스레드 또는 작업 간에 리소스를 공유할 수 있습니다.  `combinable` 클래스에 대한 자세한 내용은 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)를 참조하십시오.  
  
##  <a name="top"></a> 단원  
 이 항목에서는 다음과 같은 비동기 메시지 블록 형식에 대해 자세히 설명합니다.  
  
-   [critical\_section](#critical_section)  
  
-   [reader\_writer\_lock](#reader_writer_lock)  
  
-   [scoped\_lock 및 scoped\_lock\_read](#scoped_lock)  
  
-   [event](#event)  
  
##  <a name="critical_section"></a> critical\_section  
 [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) 클래스는 다른 작업을 선점하는 대신 이러한 작업에 양보하는 협조적 상호 제외 개체를 나타냅니다.  임계 영역은 여러 스레드에서 공유 데이터에 대해 단독으로 읽고 쓸 수 있는 권한이 필요한 경우에 유용합니다.  
  
 `critical_section` 클래스는 재진입성이 아닙니다.  [concurrency::critical\_section::lock](../Topic/critical_section::lock%20Method.md) 메서드는 잠금을 이미 소유한 스레드에 의해 호출될 경우 [concurrency::improper\_lock](../../parallel/concrt/reference/improper-lock-class.md) 형식의 예외를 throw합니다.  
  
### 메서드 및 기능  
 다음 표에서는 `critical_section` 클래스에 정의된 중요한 메서드를 보여 줍니다.  
  
|메서드|설명|  
|---------|--------|  
|[잠금](../Topic/critical_section::lock%20Method.md)|임계 영역을 가져옵니다.  호출 컨텍스트는 잠금을 가져올 때까지 차단합니다.|  
|[try\_lock](../Topic/critical_section::try_lock%20Method.md)|임계 영역을 가져오려고 하지만 차단하지 않습니다.|  
|[unlock](../Topic/critical_section::unlock%20Method.md)|임계 영역을 해제합니다.|  
  
 \[[맨 위](#top)\]  
  
##  <a name="reader_writer_lock"></a> reader\_writer\_lock  
 [concurrency::reader\_writer\_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) 클래스는 스레드로부터 안전한 공유 데이터 읽기\/쓰기 작업을 제공합니다.  여러 스레드에서 공유 리소스에 대한 동시 읽기 권한이 필요하지만 해당 공유 리소스에 쓰기 작업은 거의 하지 않는 경우 판독기\/작성기 잠금을 사용합니다.  이 클래스는 개체에 대한 쓰기 권한을 한 스레드에만 제공합니다.  
  
 `critical_section` 개체는 공유 리소스에 대한 단독 액세스 권한을 가져와 동시에 읽을 수 없게 하므로 `reader_writer_lock` 클래스가 `critical_section` 클래스보다 효율적입니다.  
  
 `critical_section` 클래스와 마찬가지로 `reader_writer_lock` 클래스는 다른 작업을 선점하는 대신 이러한 작업에 양보하는 협조적 상호 제외 개체를 나타냅니다.  
  
 공유 리소스에 써야 하는 스레드에서 판독기\/작성기 잠금을 가져오면 해당 리소스에 액세스해야 하는 다른 스레드는 작성기에서 잠금을 해제할 때까지 차단됩니다.  `reader_writer_lock` 클래스는 대기 중인 판독기의 차단을 해제하기 전에 대기 중인 작성기의 차단을 해제하는 *쓰기 기본 설정* 잠금의 한 유형입니다.  
  
 `critical_section` 클래스와 마찬가지로 `reader_writer_lock` 클래스는 재진입성이 아닙니다.  [concurrency::reader\_writer\_lock::lock](../Topic/reader_writer_lock::lock%20Method.md) 및 [concurrency::reader\_writer\_lock::lock\_read](../Topic/reader_writer_lock::lock_read%20Method.md) 메서드는 잠금을 이미 소유한 스레드에 의해 호출될 경우 `improper_lock` 형식의 예외를 throw합니다.  
  
> [!NOTE]
>  `reader_writer_lock` 클래스는 재진입성이 아니기 때문에 읽기 전용 잠금을 판독기\/작성기 잠금으로 업그레이드하거나 판독기\/작성기 잠금을 읽기 전용 잠금으로 다운그레이드할 수 없습니다.  이러한 작업 중 하나를 수행하면 지정되지 않은 동작이 발생합니다.  
  
### 메서드 및 기능  
 다음 표에서는 `reader_writer_lock` 클래스에 정의된 중요한 메서드를 보여 줍니다.  
  
|메서드|설명|  
|---------|--------|  
|[잠금](../Topic/reader_writer_lock::lock%20Method.md)|잠금에 대한 읽기\/쓰기 권한을 가져옵니다.|  
|[try\_lock](../Topic/reader_writer_lock::try_lock%20Method.md)|잠금에 대한 읽기\/쓰기 권한을 가져오려고 하지만 차단하지 않습니다.|  
|[lock\_read](../Topic/reader_writer_lock::lock_read%20Method.md)|잠금에 대한 읽기 전용 권한을 가져옵니다.|  
|[try\_lock\_read](../Topic/reader_writer_lock::try_lock_read%20Method.md)|잠금에 대한 읽기 전용 권한을 가져오려고 하지만 차단하지 않습니다.|  
|[unlock](../Topic/reader_writer_lock::unlock%20Method.md)|잠금을 해제합니다.|  
  
 \[[맨 위](#top)\]  
  
##  <a name="scoped_lock"></a> scoped\_lock 및 scoped\_lock\_read  
 `critical_section` 및 `reader_writer_lock` 클래스는 상호 제외 개체를 사용하는 방법을 간소화하는 중첩 도우미 클래스를 제공합니다.  이러한 도우미 클래스를 *범위 지정 잠금*이라고 합니다.  
  
 `critical_section` 클래스는 [concurrency::critical\_section::scoped\_lock](../Topic/critical_section::scoped_lock%20Class.md) 클래스를 포함합니다.  생성자는 제공된 `critical_section` 개체에 대한 액세스 권한을 얻고 소멸자는 해당 개체에 대한 액세스를 해제합니다.  `reader_writer_lock` 클래스는 `critical_section::scoped_lock`과 유사하지만 제공된 `reader_writer_lock` 개체에 대한 쓰기 권한을 관리한다는 차이점이 있는 [concurrency::reader\_writer\_lock::scoped\_lock](../Topic/reader_writer_lock::scoped_lock%20Class.md) 클래스를 포함합니다.  또한 `reader_writer_lock` 클래스는 [concurrency::reader\_writer\_lock::scoped\_lock\_read](../Topic/reader_writer_lock::scoped_lock_read%20Class.md) 클래스도 포함합니다.  이 클래스는 제공된 `reader_writer_lock` 개체에 대한 읽기 권한을 관리합니다.  
  
 범위 지정 잠금은 `critical_section` 및 `reader_writer_lock` 개체를 수동으로 사용하는 경우에 몇 가지 이점을 제공합니다.  일반적으로 스택에서 범위 지정 잠금을 할당합니다.  범위 지정 잠금은 상호 제외 개체가 소멸될 때 해당 개체에 대한 액세스를 자동으로 해제하므로 내부 개체의 잠금을 수동으로 해제하지 않습니다.  이는 함수에 `return` 문이 여러 개 포함된 경우에 유용합니다.  또한 범위 지정 잠금을 사용하면 예외로부터 안전한 코드를 작성할 수 있습니다.  `throw` 문으로 인해 스택이 해제되면 활성화된 범위 지정 잠금의 소멸자가 호출되므로 상호 제외 개체가 항상 올바르게 해제됩니다.  
  
> [!NOTE]
>  `critical_section::scoped_lock`, `reader_writer_lock::scoped_lock` 및 `reader_writer_lock::scoped_lock_read` 클래스를 사용하는 경우에는 내부 상호 제외 개체에 대한 액세스를 수동으로 해제하지 마십시오.  그렇지 않으면 런타임이 잘못된 상태가 될 수 있습니다.  
  
##  <a name="event"></a> event  
 [concurrency::event](../../parallel/concrt/reference/event-class.md) 클래스는 상태에서 신호를 받을 수 있거나 받을 수 없는 동기화 개체를 나타냅니다.  공유 데이터에 대한 액세스를 보호하는 것이 목적인 동기화 개체\(예: 임계 영역\)와 달리 이벤트는 실행 흐름을 동기화합니다.  
  
 `event` 클래스는 한 작업\(task\)에서 다른 작업\(task\)에 필요한 작업\(work\)을 완료한 경우에 유용합니다.  예를 들어 한 작업에서 네트워크 연결 또는 파일의 데이터를 읽었음을 다른 작업에 알릴 수 있습니다.  
  
### 메서드 및 기능  
 다음 표에서는 `event` 클래스에 정의된 중요한 메서드 중 몇 가지를 보여 줍니다.  
  
|메서드|설명|  
|---------|--------|  
|[wait](../Topic/event::wait%20Method.md)|이벤트에서 신호를 보내게 될 때까지 기다립니다.|  
|[set](../Topic/event::set%20Method.md)|이벤트를 신호된 상태로 설정합니다.|  
|[reset](../Topic/event::reset%20Method.md)|이벤트를 신호되지 않은 상태로 설정합니다.|  
|[wait\_for\_multiple](../Topic/event::wait_for_multiple%20Method.md)|여러 이벤트에서 신호를 보내게 될 때까지 기다립니다.|  
  
### 예제  
 `event` 클래스를 사용하는 방법을 보여 주는 예제를 보려면 [동기화 데이터 구조와 Windows API의 비교](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)를 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
## 관련 단원  
 [동기화 데이터 구조와 Windows API의 비교](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)  
 Windows API에서 제공하는 동기화 데이터 구조와 해당 동기화 데이터 구조의 동작을 비교합니다.  
  
 [동시성 런타임](../../parallel/concrt/concurrency-runtime.md)  
 병렬 프로그래밍을 단순화하는 동시성 런타임에 대해 설명하고 관련 항목에 대한 링크를 포함합니다.