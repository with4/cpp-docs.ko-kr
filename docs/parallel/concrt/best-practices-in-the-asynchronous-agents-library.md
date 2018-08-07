---
title: 비동기 에이전트 라이브러리의 유용한 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- best practices, Asynchronous Agents Library
- Asynchronous Agents Library, best practices
- Asynchronous Agents Library, practices to avoid
- practices to avoid, Asynchronous Agents Library
ms.assetid: 85f52354-41eb-4b0d-98c5-f7344ee8a8cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f1b20342ad6bb64c653a211f9af2fb9e9130286
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692667"
---
# <a name="best-practices-in-the-asynchronous-agents-library"></a>비동기 에이전트 라이브러리의 모범 사례
이 문서에서는 비동기 에이전트 라이브러리를 효과적으로 사용 하는 방법에 설명 합니다. 에이전트 라이브러리는 행위자 기반 프로그래밍 모델 및 정교 하지 않은 데이터 흐름에 대 한 전달 및 파이프라인 작업을 위해 in-process 메시지의 수준을 올립니다.  
  
 에이전트 라이브러리에 대 한 자세한 내용은 참조 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)합니다.  
  
##  <a name="top"></a> 섹션  
 이 문서는 다음 섹션으로 구성됩니다.  
  
- [에이전트 상태 격리를 사용 하 여](#isolation)  
  
- [제한 메커니즘을 사용 하 여 데이터 파이프라인에서 메시지의 수를 제한 하려면](#throttling)  
  
- [데이터 파이프라인에서 세분화 된 작업을 수행 하지 않습니다](#fine-grained)  
  
- [값으로 큰 메시지 페이로드를 전달 하지 마십시오](#large-payloads)  
  
- [에 데이터 네트워크 때 소유권은 정의 되지 않은 shared_ptr을 사용 하 여](#ownership)  
  
##  <a name="isolation"></a> 에이전트 상태 격리를 사용 하 여  
 에이전트 라이브러리는 비동기 메시지 전달 메커니즘을 통해 독립 된 구성 요소를 연결할 수 있도록 하 여 공유 상태에 대 한 대안을 제공 합니다. 비동기 에이전트는 내부 상태를 다른 구성 요소에서 격리할 때 가장 효과적입니다. 상태를 격리 하 여 여러 개의 구성 요소가 일반적으로에 적용 되지 공유 데이터입니다. 상태 격리를 응용 프로그램을 공유 메모리에 대 한 경합이 줄어들기 때문에 확장 가능 합니다. 또한 상태 격리 구성 요소는 공유 데이터에 대 한 액세스를 동기화 할 필요는 없으므로 교착 상태 및 경합 조건 가능성을 줄입니다.  
  
 데이터 멤버를 포함 하 여 에이전트에서 상태를 일반적으로 격리는 `private` 또는 `protected` 에이전트 및 메시지 버퍼를 사용 하 여 상태 변경을 전달 하 여 섹션. 다음 예제와 `basic_agent` 클래스에서 파생 된 [concurrency:: agent](../../parallel/concrt/reference/agent-class.md)합니다. `basic_agent` 클래스 두 개의 메시지 버퍼를 사용 하 여 외부 구성 요소와 통신 합니다. 하나의 메시지 버퍼가 보유 하는 들어오는 메시지; 다른 메시지 버퍼 보내는 메시지를 보유합니다.  
  
 [!code-cpp[concrt-simple-agent#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_1.cpp)]  
  
 정의 하 고 에이전트를 사용 하는 방법에 대 한 전체 예제를 참조 하십시오. [연습: 에이전트 기반 응용 프로그램을 만드는](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md) 및 [연습: 데이터 흐름 에이전트 만들기](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="throttling"></a> 제한 메커니즘을 사용 하 여 데이터 파이프라인에서 메시지의 수를 제한 하려면  
 다양 한 메시지 버퍼 종류와 같은 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md), 메시지 개수에 제한 없이 저장할 수 있습니다. 메시지 생산자가 메시지를 보내면 데이터 파이프라인 소비자는 해당이 메시지를 처리할 수 있는 보다 더 빠르게, 응용 프로그램 메모리 부족 또는 메모리 부족 상태를 입력할 수 있습니다. 데이터 파이프라인에서 동시에 활성화 된 메시지의 수를 제한 하려면 예를 들어, 세마포, 조정 메커니즘을 사용할 수 있습니다.  
  
 다음 기본 예제에서는 데이터 파이프라인에서 메시지의 수를 제한 하려면 세마포를 사용 하는 방법을 보여 줍니다. 데이터에 사용 하 여 파이프라인의 [concurrency:: wait](reference/concurrency-namespace-functions.md#wait) 적어도 100 밀리초를 사용 하는 작업을 시뮬레이션 하는 함수입니다. 보낸 사람에 게 메시지를 소비자는 이러한 메시지를 처리할 수 있는 보다 더 빠르게 생성 하기 때문에이 예에서는 정의 `semaphore` 클래스를 사용 하는 응용 프로그램의 활성 메시지의 수를 제한 합니다.  
  
 [!code-cpp[concrt-message-throttling#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_2.cpp)]  
  
 `semaphore` 동시에 최대 두 개의 메시지를 처리 하기 위해 파이프라인을 제한 하는 개체입니다.  
  
 이 예에서 생산자 소비자에 게 상대적으로 적은 수의 메시지를 보냅니다. 따라서이 예제에서는 잠재적인 메모리 부족 또는 메모리 부족 상태를 보여 주지 않습니다. 그러나이 메커니즘은 데이터 파이프라인에 상대적으로 많은 수의 메시지가 포함 되어 있는 경우 유용 합니다.  
  
 이 예제에 사용 되는 semaphore 클래스를 만드는 방법에 대 한 자세한 내용은 참조 [하는 방법: 컨텍스트 클래스를 사용 하 여 공동 작업 세마포 구현](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="fine-grained"></a> 데이터 파이프라인에서 세분화 된 작업을 수행 하지 않습니다  
 에이전트 라이브러리는 데이터 파이프라인에서 수행 하는 작업을 정교 하지 않은 경우 가장 유용 합니다. 예를 들어 하나의 응용 프로그램 구성 요소 파일 또는 네트워크 연결에서 데이터를 읽 및 경우에 따라 다른 구성 요소에 해당 데이터를 보낼 수 있습니다. 에이전트 라이브러리 메시지를 전파 하는 데 사용 하는 프로토콜에서 제공 되는 작업 병렬 구문 보다 더 많은 오버 헤드를가 하는 메시지 전달 메커니즘 사용 하면는 [병렬 패턴 라이브러리](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL). 따라서 데이터 파이프라인에서 수행 하는 작업을이 오버 헤드를 오프셋할 수 있을 정도로 오래을 반드시 합니다.  
  
 해당 작업은 정교 하지 않은 경우 데이터 파이프라인 가장 효과적 이지만 데이터 파이프라인의 각 단계 더 세분화 된 작업을 수행 하려면 작업 그룹 및 병렬 알고리즘 같은 PPL 구문을 사용할 수 있습니다. 예를 보려면 각 처리 단계에서 세부적인 병렬 처리를 사용 하는 정교 하지 않은 데이터 네트워크 참조 [연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="large-payloads"></a> 값으로 큰 메시지 페이로드를 전달 하지 마십시오  

 일부 경우에는 런타임에서 다른 메시지 버퍼에 메시지 버퍼 간에 전달 하는 모든 메시지의 복사본을 만듭니다. 예를 들어는 [concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) 클래스는 각 대상에는 수신 하는 모든 메시지의 복사본을 제공 합니다. 와 같은 메시지 전달 함수를 사용 하는 경우 또한 메시지 데이터의 복사본을 만듭니다는 런타임에서 [concurrency:: send](reference/concurrency-namespace-functions.md#send) 및 [concurrency:: receive](reference/concurrency-namespace-functions.md#receive) 메시지에서 메시지를 읽고 메시지를 쓰는 데 버퍼입니다. 이 메커니즘을 사용 하면 공유 데이터를 쓰는 동시에 위험 제거, 하지만 메시지 페이로드는 비교적 많은 경우 메모리 성능이 저하 될 수 있습니다.  
  
 포인터를 사용할 수 있고 메시지를 전달할 때 메모리 성능을 향상에 대 한 참조는 대용량 페이로드. 다음 예제에서는 동일한 메시지 유형으로 포인터를 전달 하는 값으로 전달 큰 메시지를 비교 합니다. 이 예제에서는 두 개의 에이전트 형식이 정의 `producer` 및 `consumer`에서 작동 하는 `message_data` 개체입니다. 이 예제에서는 보내는 데 생산자에 필요한 시간을 비교 `message_data` 개체에 대 한 여러 포인터를 보내도록 공급자 에이전트에 필요한 시간을 소비자에 게 `message_data` 소비자에 게 개체입니다.  
  
 [!code-cpp[concrt-message-payloads#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_3.cpp)]  
  
 이 예제는 다음과 같은 샘플 출력을 생성합니다.  
  
```Output  
Using message_data...  
took 437ms.  
Using message_data*...  
took 47ms.  
```  
  
 포인터를 사용 하는 버전의 전체 복사본을 만드는 런타임에 대 한 요구 사항을 제거 하기 때문에 더 좋은 성능을 모든 `message_data` 공급자에서는 소비자에 게 전달 하는 개체입니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="ownership"></a> 에 데이터 네트워크 때 소유권은 정의 되지 않은 shared_ptr을 사용 하 여  
 메시지 전달 파이프라인 또는 네트워크를 통해 포인터에 의해 메시지를 보낼 때 일반적으로 네트워크의 앞에 각 메시지에 대 한 메모리를 할당 했으며 네트워크의 끝에 해당 메모리 해제 이 메커니즘 대부분 제대로 작동 하지만 인 하거나 사용할 수 없는 경우가 있습니다. 예를 들어, 데이터 네트워크에 여러 끝 노드가 포함 된 예를 살펴보겠습니다. 이 경우 위치가 없습니다 지우기는 메시지에 대 한 메모리를 해제 합니다.  
  
 이 문제를 해결 하는 메커니즘을 예를 들어 사용 수 [std:: shared_ptr](../../standard-library/shared-ptr-class.md), 여러 구성 요소에서 소유할 수에 대 한 포인터 수 있도록 합니다. 때 최종 `shared_ptr` 리소스를 소유 하는 개체가 삭제 되 면 리소스가 해제 됩니다.  
  
 다음 예제에서는 사용 하는 방법을 `shared_ptr` 여러 메시지 버퍼에서 포인터 값을 공유할 수 있습니다. 이 예제에서는 연결는 [concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) 개체를 3 개로 [concurrency:: call](../../parallel/concrt/reference/call-class.md) 개체입니다. `overwrite_buffer` 클래스에는 각 대상에 메시지를 제공 합니다. 이 예에서는 있기 때문에 데이터 네트워크의 끝 부분에 있는 데이터의 여러 소유자, `shared_ptr` 각각 사용 하도록 설정할 `call` 개체는 메시지의 소유권을 공유 합니다.  
  
 [!code-cpp[concrt-message-sharing#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_4.cpp)]  
  
 이 예제는 다음과 같은 샘플 출력을 생성합니다.  
  
```Output  
Creating resource 42...  
receiver1: received resource 42  
Creating resource 64...  
receiver2: received resource 42  
receiver1: received resource 64  
Destroying resource 42...  
receiver2: received resource 64  
Destroying resource 64...  
```  
  
## <a name="see-also"></a>참고 항목  
 [동시성 런타임에 대 한 유용한 정보](../../parallel/concrt/concurrency-runtime-best-practices.md)   
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [연습: 에이전트 기반 응용 프로그램 만들기](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)   
 [연습: 데이터 흐름 에이전트 만들기](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)   
 [연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)   
 [병렬 패턴 라이브러리의 유용한 정보](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)   
 [동시성 런타임의 유용한 일반 정보](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)

