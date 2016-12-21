---
title: "동기화 데이터 구조와 Windows API의 비교 | Microsoft Docs"
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
  - "동기화 데이터 구조, Windows API와 비교"
  - "이벤트 클래스, 예제"
ms.assetid: 8b0b1a3a-ef80-408c-91fa-93e6af920b4e
caps.latest.revision: 16
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 동기화 데이터 구조와 Windows API의 비교
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 동시성 런타임에서 제공하는 동기화 데이터 구조의 동작과 Windows API에서 제공하는 동기화 데이터 구조의 동작을 비교합니다.  
  
 동시성 런타임에서 제공하는 동기화 데이터 구조는 *협조적 스레딩 모델*을 따릅니다.  협조적 스레딩 모델에서는 동기화 기본 형식이 자신의 처리 리소스를 다른 스레드에 명시적으로 양보합니다.  이는 스케줄러 또는 운영 체제를 제어하여 처리 리소스가 다른 스레드에 전송되는 *선점 스레딩 모델*과 다릅니다.  
  
## critical\_section  
 [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) 클래스는 한 프로세스의 스레드에서만 사용할 수 있으므로 Windows `CRITICAL_SECTION` 구조와 유사합니다.  Windows API의 임계 영역에 대한 자세한 내용은 [임계 영역 개체](http://msdn.microsoft.com/library/windows/desktop/ms682530)를 참조하십시오.  
  
## reader\_writer\_lock  
 [concurrency::reader\_writer\_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) 클래스는 Windows SRW\(슬림 판독기\/작성기\) 잠금과 유사합니다.  다음 표에서는 두 잠금의 차이점과 유사점에 대해 설명합니다.  
  
|기능|`reader_writer_lock`|SRW 잠금|  
|--------|--------------------------|------------|  
|재진입 안 됨|예|예|  
|판독기를 작성기로 올리기 가능\(업그레이드 지원\)|아니요|아니요|  
|작성기를 판독기로 내리기 가능\(다운그레이드 지원\)|아니요|아니요|  
|쓰기 기본 설정 잠금|예|아니요|  
|작성기에 대한 FIFO 액세스|예|아니요|  
  
 SRW 잠금에 대한 자세한 내용은 Platform SDK에서 [SRW\(슬림 판독기\/작성기\) 잠금](http://msdn.microsoft.com/library/windows/desktop/aa904937)을 참조하십시오.  
  
## event  
 [concurrency::event](../../parallel/concrt/reference/event-class.md) 클래스는 명명되지 않은 Windows 수동 재설정 이벤트와 유사합니다.  그러나 `event` 개체는 협조적으로 동작하고 Windows 이벤트는 선점하여 동작합니다.  Windows 이벤트에 대한 자세한 내용은 [이벤트 개체](http://msdn.microsoft.com/library/windows/desktop/ms682655)를 참조하십시오.  
  
## 예제  
  
### 설명  
 `event` 클래스와 Windows 이벤트 간의 차이를 더 잘 이해하려면 다음 예제를 참조하십시오.  이 예제에서는 스케줄러가 최대 두 개의 동시 작업을 만든 다음, `event` 클래스와 Windows 수동 재설정 이벤트를 사용하는 비슷한 두 함수를 호출합니다.  각 함수는 먼저 공유 이벤트가 신호를 받을 때까지 기다리는 작업을 여러 개 만듭니다.  그런 다음 각 함수는 실행 중인 작업에 양보하고 이벤트에 신호를 보냅니다.  그런 다음 각 함수는 신호를 받은 이벤트를 기다립니다.  
  
### 코드  
 [!code-cpp[concrt-event-comparison#1](../../parallel/concrt/codesnippet/CPP/comparing-synchronization-data-structures-to-the-windows-api_1.cpp)]  
  
### 설명  
 이 예제를 실행하면 다음과 같은 샘플 결과가 출력됩니다.  
  
  **공동 이벤트:**  
 **컨텍스트: 이벤트가 기다리고 있습니다.**  
 **컨텍스트: 이벤트가 기다리고 있습니다.**  
 **컨텍스트: 이벤트가 기다리고 있습니다.**  
 **컨텍스트: 이벤트가 기다리고 있습니다.**  
 **컨텍스트: 이벤트가 기다리고 있습니다.**  
 **이벤트를 설정 합니다.**  
 **5 컨텍스트: 이벤트를 받았습니다.**  
 **6 컨텍스트: 이벤트를 받았습니다.**  
 **7 컨텍스트: 이벤트를 받았습니다.**  
 **8 컨텍스트: 이벤트를 받았습니다.**  
 **9 컨텍스트: 이벤트를 받았습니다.**  
**Windows 이벤트:**  
 **컨텍스트: 이벤트가 기다리고 있습니다.**  
 **컨텍스트: 이벤트가 기다리고 있습니다.**  
 **이벤트를 설정 합니다.**  
 **12 컨텍스트: 이벤트를 받았습니다.**  
 **컨텍스트: 이벤트가 기다리고 있습니다.**  
 **15 컨텍스트: 이벤트를 받았습니다.**  
 **컨텍스트: 이벤트가 기다리고 있습니다.**  
 **17 컨텍스트: 이벤트를 받았습니다.**  
 **컨텍스트: 이벤트가 기다리고 있습니다.**  
 **19 컨텍스트: 이벤트를 받았습니다.**  
 **13 컨텍스트: 이벤트를 받았습니다.** `event` 클래스는 협조적으로 동작하므로 이벤트가 신호를 받은 상태로 들어가기 위해 대기 중일 때 스케줄러에서 다른 컨텍스트에 처리 리소스를 다시 할당할 수 있습니다.  따라서 `event` 클래스를 사용하는 버전에서 더 많은 작업이 완료됩니다.  Windows 이벤트를 사용하는 버전의 경우 대기 중인 각 작업은 다음 작업이 시작되기 전에 신호를 받은 상태로 들어가야 합니다.  
  
 작업에 대한 자세한 내용은 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)을 참조하십시오.  
  
## 참고 항목  
 [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)   
 [임계 영역 개체](http://msdn.microsoft.com/library/windows/desktop/ms682530)   
 [슬림 판독기\/기록기 \(SRW\) 잠금](http://msdn.microsoft.com/library/windows/desktop/aa904937)   
 [이벤트 개체](http://msdn.microsoft.com/library/windows/desktop/ms682655)