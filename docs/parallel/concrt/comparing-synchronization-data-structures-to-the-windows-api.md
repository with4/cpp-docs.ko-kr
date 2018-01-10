---
title: "동기화 데이터 구조와 Windows API의 비교 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- synchronization data structures, compared to Windows API
- event class, example
ms.assetid: 8b0b1a3a-ef80-408c-91fa-93e6af920b4e
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4590724bfc34d0ed9136e74e85b09db6a805c50c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="comparing-synchronization-data-structures-to-the-windows-api"></a>동기화 데이터 구조와 Windows API의 비교
이 항목에서는 Windows API에서 제공 된, 동시성 런타임에서 제공 되는 동기화 데이터 구조체의 동작을 비교 합니다.  
  
 동시성 런타임에서 제공 되는 동기화 데이터 구조에 따라는 *스레딩 모델 협조적*합니다. 협조적 스레딩 모델에서 동기화 기본 형식을 명시적으로 자신의 처리 리소스를 다른 스레드를 생성합니다. 이 점에서 차이가 *선점형 스레딩 모델*, 여기서 처리 리소스 제어 스케줄러 또는 운영 체제 하 여 다른 스레드에 전송 됩니다.  
  
## <a name="criticalsection"></a>critical_section  
 [concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) Windows와 유사 `CRITICAL_SECTION` 한 프로세스의 스레드에 의해만 사용할 수 없기 때문에 구성 합니다. Windows API에서 중요 한 섹션에 대 한 자세한 내용은 참조 [임계 영역 개체](http://msdn.microsoft.com/library/windows/desktop/ms682530)합니다.  
  
## <a name="readerwriterlock"></a>reader_writer_lock  
 [concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) Windows 슬림 판독기/기록기 (SRW) 잠금와 유사 합니다. 다음 표에서 공통점과 차이점을 설명 합니다.  
  
|기능|`reader_writer_lock`|SRW 잠금|  
|-------------|--------------------------|--------------|  
|재진입|예|예|  
|판독기는 기록기 (업그레이드 지원)를 승격할 수 있습니다.|아니요|아니요|  
|실행 하는 기록기가 판독기 (다운 그레이드 지원)를|아니요|아니요|  
|쓰기 기본 설정|예|아니요|  
|작성기에 대 한 FIFO 액세스|예|아니요|  
  
 SRW 잠금에 대 한 자세한 내용은 참조 [슬림 판독기/작성기 (SRW) 잠금을](http://msdn.microsoft.com/library/windows/desktop/aa904937) 플랫폼 SDK에 있습니다.  
  
## <a name="event"></a>이벤트(event)  
 [concurrency:: event](../../parallel/concrt/reference/event-class.md) 명명 되지 않은 Windows 수동 재설정 이벤트와 유사 합니다. 그러나는 `event` 선점 하 여 Windows 이벤트 동작 하지만 개체는 협조적으로 동작 합니다. Windows 이벤트에 대 한 자세한 내용은 참조 [이벤트 개체](http://msdn.microsoft.com/library/windows/desktop/ms682655)합니다.  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 간의 차이 더 잘 이해 하려면는 `event` 클래스 및 Windows 이벤트를 다음 예제를 참조 하세요. 최대 두 개의 동시 작업 및 사용 하는 두 개의 비슷한 함수 호출을 만드는 스케줄러를 사용 하는이 예제는 `event` 클래스와 Windows 수동 다시 설정 이벤트입니다. 각 함수는 먼저 공유 이벤트가 신호를 받을 때까지 대기 하는 여러 작업을 만듭니다. 각 함수 다음 실행 중인 작업을 생성 하 고 이벤트에 신호를 보냅니다. 그런 다음 각 함수는 신호를 받은 이벤트 기다립니다.  
  
### <a name="code"></a>코드  
 [!code-cpp[concrt-event-comparison#1](../../parallel/concrt/codesnippet/cpp/comparing-synchronization-data-structures-to-the-windows-api_1.cpp)]  
  
### <a name="comments"></a>설명  
 이 예제는 다음과 같은 샘플 출력을 생성합니다.  
  
```Output  
Cooperative event:  
    Context 0: waiting on an event.  
    Context 1: waiting on an event.  
    Context 2: waiting on an event.  
    Context 3: waiting on an event.  
    Context 4: waiting on an event.  
    Setting the event.  
    Context 5: received the event.  
    Context 6: received the event.  
    Context 7: received the event.  
    Context 8: received the event.  
    Context 9: received the event.  
Windows event:  
    Context 10: waiting on an event.  
    Context 11: waiting on an event.  
    Setting the event.  
    Context 12: received the event.  
    Context 14: waiting on an event.  
    Context 15: received the event.  
    Context 16: waiting on an event.  
    Context 17: received the event.  
    Context 18: waiting on an event.  
    Context 19: received the event.  
    Context 13: received the event.  
```  
  
 때문에 `event` 클래스는 협조적 동작, 이벤트 신호를 받은 상태로 전환 하려고 대기 하는 경우 스케줄러 처리 리소스를 다른 컨텍스트를 다시 할당할 수 있습니다. 사용 하는 버전에서 더 많은 작업은 완료 하는 따라서는 `event` 클래스입니다. Windows 이벤트를 사용 하는 버전, 다음 작업이 시작 되기 전에 대기 중인 각 작업 신호를 받은 상태로 입력 해야 합니다.  
  
 작업에 대 한 자세한 내용은 참조 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)
