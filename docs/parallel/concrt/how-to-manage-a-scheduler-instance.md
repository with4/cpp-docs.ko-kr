---
title: '방법: 스케줄러 인스턴스 관리 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- managing a scheduler instance [Concurrency Runtime]
- scheduler instances, managing [Concurrency Runtime]
ms.assetid: 2cc804f0-5ff3-498b-97f1-a9f67a005448
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 699abcbc75dc4f0df40d07d26c0e6987d4711fe3
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687662"
---
# <a name="how-to-manage-a-scheduler-instance"></a>방법: 스케줄러 인스턴스 관리
스케줄러 인스턴스를 사용 하면 다양 한 종류의 작업 부하를 특정 일정 예약 정책을 연결 합니다. 이 항목에는 만들고 스케줄러 인스턴스를 관리 하는 방법을 보여 주는 두 가지 기본 예제가 포함 되어 있습니다.  
  
 예제에서는 기본 스케줄러 정책을 사용 하는 스케줄러를 만듭니다. 스케줄러를 만드는 예제를 사용자 지정 정책을 사용 하 여, 참조 [하는 방법: 특정 스케줄러 정책 지정](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)합니다.  
  
### <a name="to-manage-a-scheduler-instance-in-your-application"></a>응용 프로그램에서 스케줄러 인스턴스 관리  
  
1.  만들기는 [concurrency:: schedulerpolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) 정책이 들어 있는 개체를 사용 하 여 스케줄러에 대 한 값입니다.  
  

2.  호출 된 [concurrency::CurrentScheduler::Create](reference/currentscheduler-class.md#create) 메서드 또는 [concurrency::Scheduler::Create](reference/scheduler-class.md#create) 스케줄러 인스턴스를 만드는 방법.  
  
     사용 하는 경우는 `Scheduler::Create` 메서드를 호출은 [concurrency::Scheduler::Attach](reference/scheduler-class.md#attach) 메서드에 현재 컨텍스트와 스케줄러를 연결 해야 하는 경우.  
  
3.  호출 된 [CreateEvent](http://msdn.microsoft.com/library/windows/desktop/ms682396) 신호를 자동 재설정 이벤트 개체에 대 한 핸들을 만들 함수입니다.  
  
4.  핸들을 방금 만든 이벤트 개체에 전달 된 [concurrency::CurrentScheduler::RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) 메서드 또는 [concurrency::Scheduler::RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) 메서드. 이 스케줄러에서 소멸 될 때 설정할 이벤트를 등록 합니다.  
  
5.  현재 스케줄러로 예약할 원하는 작업을 수행 합니다.  
  
6.  호출 된 [concurrency::CurrentScheduler::Detach](reference/currentscheduler-class.md#detach) 메서드를 현재 스케줄러를 분리 하 고 현재 이전 스케줄러를 복원 합니다.  
  
     사용 하는 경우는 `Scheduler::Create` 메서드를 호출은 [concurrency::Scheduler::Release](reference/scheduler-class.md#release) 의 참조 횟수를 감소 시키기 위해 메서드는 `Scheduler` 개체입니다.  
  
7.  핸들을 이벤트를 전달 된 [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032) 함수를 종료 하려면 스케줄러에 대해 기다려야 합니다.  
  
8.  호출 된 [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211) 함수를 이벤트 개체에 대 한 핸들을 닫습니다.  
  
## <a name="example"></a>예제  
 다음 코드에는 스케줄러 인스턴스를 관리 하는 두 가지 방법을 보여 줍니다. 각 예에서는 먼저 기본 스케줄러를 사용 하 여 현재 스케줄러의 고유 식별자를 출력 하는 작업을 수행 합니다. 각 예에서는 다음 스케줄러 인스턴스를 사용 하 여 같은 작업을 다시 수행 합니다. 마지막으로, 각 예에서는 현재 기본 스케줄러를 복원 하 고 작업을 한 번 더 수행 합니다.  
  
 사용 하 여 첫 번째 예제는 [concurrency:: currentscheduler](../../parallel/concrt/reference/currentscheduler-class.md) 스케줄러 인스턴스를 만들고 현재 컨텍스트와 연결 하는 클래스입니다. 사용 하 여 두 번째 예제는 [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 동일한 작업을 수행 하는 클래스입니다. 일반적으로 `CurrentScheduler` 클래스 현재 스케줄러를 사용 하는 데 사용 됩니다. 사용 하는 두 번째 예는 `Scheduler` 클래스, 스케줄러를 현재 컨텍스트와 연결 하는 경우 또는 특정 작업을 특정 스케줄러를 연결 하려면 제어 하려는 경우에 유용 합니다.  
  
 [!code-cpp[concrt-scheduler-instance#1](../../parallel/concrt/codesnippet/cpp/how-to-manage-a-scheduler-instance_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
```Output  
Using CurrentScheduler class...  
 
Current scheduler id: 0  
Creating and attaching scheduler...  
Current scheduler id: 1  
Detaching scheduler...  
Current scheduler id: 0  
 
Using Scheduler class...  
 
Current scheduler id: 0  
Creating scheduler...  
Attaching scheduler...  
Current scheduler id: 2  
Detaching scheduler...  
Current scheduler id: 0  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `scheduler-instance.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc 스케줄러 instance.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [스케줄러 인스턴스](../../parallel/concrt/scheduler-instances.md)   
 [방법: 특정 스케줄러 정책 지정](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)

