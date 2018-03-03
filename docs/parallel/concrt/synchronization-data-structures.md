---
title: "동기화 데이터 구조 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- synchronization data structures
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1dd1c47cad01e0324f8027593eb4933f70cd6191
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="synchronization-data-structures"></a>동기화 데이터 구조
동시성 런타임은 여러 스레드에서 공유 데이터에 대 한 액세스를 동기화 할 수 있는 몇 가지 데이터 구조를 제공 합니다. 이러한 데이터 구조는 공유 데이터를 자주 수정 하는 경우에 유용 합니다. 예를 들어 임계 영역 개체를 동기화 하면 다른 스레드가 공유 리소스를 사용할 수 있는 될 때까지 기다립니다. 따라서 이러한 개체를 사용 하 여 자주 사용 되는 데이터에 대 한 액세스를 동기화 하는 경우 응용 프로그램에서 확장성을 잃을 수 있습니다. [라이브러리 PPL (병렬 패턴)](../../parallel/concrt/parallel-patterns-library-ppl.md) 제공는 [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 클래스를 통해 여러 개의 스레드 또는 동기화 할 필요가 없는 작업 사이에서 리소스를 공유할 수 있습니다. 에 대 한 자세한 내용은 `combinable` 클래스를 참조 하십시오. [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)합니다.  
  
##  <a name="top"></a> 섹션  
 이 다음 비동기 메시지 블록 형식인을 자세히 설명합니다.  
  
-   [critical_section](#critical_section)  
  
-   [reader_writer_lock](#reader_writer_lock)  
  
-   [scoped_lock 및 scoped_lock_read](#scoped_lock)  
  
-   [event](#event)  
  
##  <a name="critical_section"></a>critical_section  
 [concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) 클래스 선점 하는 대신 다른 작업에 양보 하는 협조적 상호 제외 개체를 나타냅니다. 임계 영역은 여러 스레드가 단독 읽기 및 공유 데이터에 대 한 쓰기 액세스를 필요로 할 때 유용 합니다.  

 `critical_section` 클래스는 재진입 성이 아닌 합니다. [concurrency::critical_section::lock](reference/critical-section-class.md#lock) 형식의 예외를 throw [concurrency:: improper_lock](../../parallel/concrt/reference/improper-lock-class.md) 는 잠금을 이미 소유한 스레드에 의해 호출 되 면입니다.  


  
### <a name="methods-and-features"></a>메서드 및 기능  
 다음 표에서 여 정의 된 중요 한 메서드는 `critical_section` 클래스입니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[lock](reference/critical-section-class.md#lock)|임계 영역을 가져옵니다. 호출 컨텍스트 될 때까지 차단 잠금을 획득 합니다.|  
|[try_lock](reference/critical-section-class.md#try_lock)|임계 영역을 가져오려고 시도 하지만 차단 하지 않습니다.|  
|[unlock](reference/critical-section-class.md#unlock)|임계 영역을 해제합니다.|  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="reader_writer_lock"></a>reader_writer_lock  
 [concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) 클래스는 공유 데이터에 스레드로부터 안전한 읽기/쓰기 작업을 제공 합니다. 여러 스레드가 공유 리소스에 대 한 동시 읽기 액세스를 필요 하지만 거의 해당 공유 리소스에 쓸 때 판독기/작성기 잠금을 사용 합니다. 이 클래스는 개체에 언제 든 지 하나의 스레드만 쓰기 액세스를 제공합니다.  
  
 `reader_writer_lock` 클래스 수행할 수 있습니다 보다는 `critical_section` 클래스는 `critical_section` 동시 읽기 액세스 권한을 제한 하는 공유 리소스에 대 한 단독 액세스를 획득 하는 개체입니다.  
  
 마찬가지로 `critical_section` 클래스는 `reader_writer_lock` 클래스 선점 하는 대신 다른 작업에 양보 하는 협조적 상호 제외 개체를 나타냅니다.  
  
 공유 리소스에 써야 하는 스레드에서 판독기/작성기 잠금을 가져오면 작성기 잠금을 해제할 때까지 리소스에 액세스 해야 하는 다른 스레드는 차단 됩니다. `reader_writer_lock` 클래스의 예는 한 *쓰기 기본 설정* 잠금 대기 중인 판독기 차단을 해제 하기 전에 대기 기록기를 차단 해제 하는 잠금입니다.  
  
 마찬가지로 `critical_section` 클래스는 `reader_writer_lock` 클래스는 재진입 성이 아닌 합니다. [concurrency::reader_writer_lock::lock](reference/reader-writer-lock-class.md#lock) 및 [concurrency::reader_writer_lock::lock_read](reference/reader-writer-lock-class.md#lock_read) 메서드 형식의 예외를 throw `improper_lock` 이미 소유한 스레드에 의해 호출 되는 경우 잠금입니다.  


  
> [!NOTE]
>  때문에 `reader_writer_lock` 클래스는 재진입 성이 아닌, 판독기/작성기 잠금을 읽기 전용 잠금을 업그레이드 하거나 읽기 전용 잠금에 판독기/기록기 잠금으로 다운 그레이드할 수 없습니다. 이러한 작업 중 하나를 수행 하면 지정 되지 않은 동작이 발생 합니다.  
  
### <a name="methods-and-features"></a>메서드 및 기능  
 다음 표에서 여 정의 된 중요 한 메서드는 `reader_writer_lock` 클래스입니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[lock](reference/reader-writer-lock-class.md#lock)|잠금에 대 한 읽기/쓰기 권한을 가져옵니다.|  
|[try_lock](reference/reader-writer-lock-class.md#try_lock)|잠금에 대 한 읽기/쓰기 권한 획득 하려고 시도 하지만 차단 하지 않습니다.|  
|[lock_read](reference/reader-writer-lock-class.md#lock_read)|잠금에 대 한 읽기 전용 권한을 가져옵니다.|  
|[try_lock_read](reference/reader-writer-lock-class.md#try_lock_read)|잠금에 대 한 읽기 전용 액세스를 가져오려고 하지만 차단 하지 않습니다.|  
|[unlock](reference/reader-writer-lock-class.md#unlock)|잠금을 해제합니다.|  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="scoped_lock"></a>scoped_lock 및 scoped_lock_read  
 `critical_section` 및 `reader_writer_lock` 클래스 상호 제외 개체를 사용 하는 방식을 단순화 하는 중첩 된 도우미 클래스를 제공 합니다. 이러한 도우미 클래스 라고 *범위 지정 잠금*합니다.  
  
 `critical_section` 클래스에 포함 되어는 [concurrency::critical_section::scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) 클래스입니다. 제공 된에 대 한 액세스를 획득 하는 생성자 `critical_section` 개체가; 해당 개체에 대 한 소멸자 릴리스 액세스 합니다. `reader_writer_lock` 클래스에 포함 되어는 [scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) 클래스와 유사한 `critical_section::scoped_lock`제외 하 고 제공 된에 대 한 쓰기 액세스를 관리, `reader_writer_lock` 개체입니다. `reader_writer_lock` 클래스도 포함 되어는 [concurrency::reader_writer_lock::scoped_lock_read](reference/reader-writer-lock-class.md#scoped_lock_read_class) 클래스입니다. 이 클래스는 제공 된에 대 한 읽기 액세스를 관리 `reader_writer_lock` 개체입니다.  

  
 범위가 지정 된 잠금을 사용 하는 경우 몇 가지 이점을 제공 `critical_section` 및 `reader_writer_lock` 수동으로 개체입니다. 일반적으로 스택에 범위가 지정 된 잠금을 할당 합니다. 범위가 지정 된 잠금 해제의 상호 제외 개체에 대 한 자동으로; 소멸 될 때 따라서 있습니다 않으면 수동으로 잠금 해제 하지는 기본 개체. 함수에는 여러 개 포함 된 경우에 유용 `return` 문. 범위가 지정 된 잠금의 사용 예외 로부터 안전한 코드를 작성 하는 데 유용할 수 있습니다. 경우는 `throw` 문을 사용 하면 스택이 해제 하 고 활성 상태인 모든 범위가 지정 된 잠금에 대 한 소멸자가 호출 되므로 상호 제외 개체를 사용 하 여 항상 올바르게 해제 합니다.  
  
> [!NOTE]
>  사용 하는 경우는 `critical_section::scoped_lock`, `reader_writer_lock::scoped_lock`, 및 `reader_writer_lock::scoped_lock_read` 클래스, 기본 상호 제외 개체에 대 한 액세스를 수동으로 해제 하지 마십시오. 런타임에 줄이 잘못 된 상태에 수 있습니다.  
  
##  <a name="event"></a>이벤트  
 [concurrency:: event](../../parallel/concrt/reference/event-class.md) 클래스 동기화 개체를 해당 상태를 신호 또는 신호 수를 나타냅니다. 공유 데이터에 대 한 액세스를 보호 하는 것이 목적인 임계 영역 등의 동기화 개체와는 달리 이벤트 실행 흐름을 동기화 합니다.  
  
 `event` 클래스는 한 작업이 다른 작업에 대 한 작업을 완료 하는 경우 유용 합니다. 예를 들어 파일 또는 네트워크 연결에서 데이터 읽기는 다른 작업이 하나 이상의 태스크 알릴 수 있습니다.  
  
### <a name="methods-and-features"></a>메서드 및 기능  
 다음 표에서 몇 가지에 정의 된 중요 한 메서드는 `event` 클래스입니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[대기](reference/event-class.md#wait)|이벤트가 신호를 받을 때까지 기다립니다.|  
|[set](reference/event-class.md#set)|이벤트 신호 된 상태로 설정합니다.|  
|[reset](reference/event-class.md#reset)|이벤트 신호 되지 않은 상태로 설정합니다.|  
|[wait_for_multiple](reference/event-class.md#wait_for_multiple)|여러 이벤트 신호를 받을 때까지 기다립니다.|  

  
### <a name="example"></a>예  
 사용 하는 방법을 보여 주는 예제는 `event` 클래스를 참조 하십시오. [동기화 데이터 구조는 Windows API와 비교](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
## <a name="related-sections"></a>관련 단원  
 [동기화 데이터 구조와 Windows API의 비교](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)  
 동기화 데이터 구조와 Windows API에서 제공 하는 것의 동작을 비교 합니다.  
  
 [동시성 런타임](../../parallel/concrt/concurrency-runtime.md)  
 병렬 프로그래밍을 간소화하는 동시성 런타임에 대해 설명하고 관련 항목의 링크를 제공합니다.

