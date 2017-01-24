---
title: "비동기 에이전트 라이브러리의 모범 사례 | Microsoft Docs"
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
  - "모범 사례, 비동기 에이전트 라이브러리"
  - "비동기 에이전트 라이브러리, 모범 사례"
  - "비동기 에이전트 라이브러리, 예방 방법"
  - "예방 방법, 비동기 에이전트 라이브러리"
ms.assetid: 85f52354-41eb-4b0d-98c5-f7344ee8a8cf
caps.latest.revision: 15
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 비동기 에이전트 라이브러리의 모범 사례
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 비동기 에이전트 라이브러리를 효과적으로 사용하는 방법에 대해 설명합니다.  에이전트 라이브러리는 정교하지 않은 데이터 흐름 및 파이프라인 작업을 위해 행위자 기반 프로그래밍 모델과 in\-process 메시지 전달을 지원합니다.  
  
 에이전트 라이브러리에 대한 자세한 내용은 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)를 참조하십시오.  
  
##  <a name="top"></a> 단원  
 이 문서에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [에이전트를 사용하여 상태 격리](#isolation)  
  
-   [스로틀 메커니즘을 사용하여 데이터 파이프라인의 메시지 수 제한](#throttling)  
  
-   [데이터 파이프라인에서 세분화된 작업을 수행하지 않음](#fine-grained)  
  
-   [큰 메시지 페이로드는 값으로 전달하지 않음](#large-payloads)  
  
-   [소유권이 정의되어 있지 않을 경우 데이터 네트워크에서 shared\_ptr 사용](#ownership)  
  
##  <a name="isolation"></a> 에이전트를 사용하여 상태 격리  
 에이전트 라이브러리는 비동기 메시지 전달 메커니즘을 통해 격리된 구성 요소를 연결할 수 있도록 하여 공유 상태에 대한 대안을 제공합니다.  비동기 에이전트는 내부 상태를 다른 구성 요소에서 격리할 때 가장 효과적입니다.  상태를 격리하여 일반적으로 여러 구성 요소가 공유 데이터에서 동작하지 않습니다.  상태 격리를 통해 공유 메모리에 대한 경합이 줄어들기 때문에 상태 격리를 사용하면 응용 프로그램을 확장할 수 있습니다.  또한 상태 격리를 사용하면 구성 요소가 공유 데이터에 대한 액세스를 동기화할 필요가 없으므로 교착 및 경합 상태가 발생할 가능성이 줄어듭니다.  
  
 일반적으로 에이전트의 `private` 또는 `protected` 섹션에 데이터 멤버를 포함하고 메시지 버퍼를 통해 상태 변경을 전달하여 에이전트에서 상태를 격리합니다.  다음 예제에서는 [concurrency::agent](../../parallel/concrt/reference/agent-class.md)에서 파생되는 `basic_agent` 클래스를 보여 줍니다.  `basic_agent` 클래스는 두 개의 메시지 버퍼를 사용하여 외부 구성 요소와 통신합니다.  이 메시지 버퍼 중 하나는 들어오는 메시지를 포함하고 나머지 메시지 버퍼는 보내는 메시지를 포함합니다.  
  
 [!code-cpp[concrt-simple-agent#1](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-asynchronous-agents-library_1.cpp)]  
  
 에이전트를 정의하고 사용하는 방법에 대한 전체 예제는 [연습: 에이전트 기반 응용 프로그램 만들기](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md) 및 [연습: 데이터 흐름 에이전트 만들기](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)를 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="throttling"></a> 스로틀 메커니즘을 사용하여 데이터 파이프라인의 메시지 수 제한  
 [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md)와 같은 대부분의 메시지 버퍼 형식은 개수와 관계없이 메시지를 포함할 수 있습니다.  소비자가 메시지를 처리하는 속도보다 메시지 생산자가 메시지를 데이터 파이프라인에 보내는 속도가 빠를 경우 응용 프로그램이 메모리 부족 상태가 될 수 있습니다.  스로틀 메커니즘\(예: 세마포\)을 사용하여 데이터 파이프라인에서 동시에 활성 상태가 될 수 있는 메시지 수를 제한할 수 있습니다.  
  
 다음 기본 예제에서는 세마포를 사용하여 데이터 파이프라인의 메시지 수를 제한하는 방법을 보여 줍니다.  데이터 파이프라인은 [concurrency::wait](../Topic/wait%20Function.md) 함수를 사용하여 최소 100초가 걸리는 작업을 시뮬레이션합니다.  소비자가 메시지를 처리할 수 있는 속도보다 전송자가 메시지를 생성하는 속도가 빠르기 때문에 이 예제에서는 응용 프로그램이 활성 메시지 수를 제한할 수 있도록 `semaphore` 클래스를 정의합니다.  
  
 [!code-cpp[concrt-message-throttling#1](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-asynchronous-agents-library_2.cpp)]  
  
 `semaphore` 개체는 파이프라인에서 동시에 최대 두 개의 메시지를 처리하도록 제한합니다.  
  
 이 예제에서 생산자는 비교적 적은 수의 메시지를 소비자에게 보냅니다.  따라서 이 예제에서는 발생할 수 있는 메모리 부족 상태를 보여 주지 않습니다.  그러나 데이터 파이프라인에 비교적 많은 수의 메시지가 포함되어 있는 경우 이 메커니즘이 유용합니다.  
  
 이 예제에서 사용하는 세마포 클래스를 만드는 방법에 대한 자세한 내용은 [방법: 컨텍스트 클래스를 사용하여 공동 작업 세마포 구현](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)을 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="fine-grained"></a> 데이터 파이프라인에서 세분화된 작업을 수행하지 않음  
 에이전트 라이브러리는 데이터 파이프라인에서 수행하는 작업이 정교하지 않은 경우 가장 유용합니다.  예를 들어 하나의 응용 프로그램 구성 요소가 파일 또는 네트워크 연결에서 데이터를 읽어 다른 구성 요소에 보내는 경우가 있습니다.  에이전트 라이브러리에서 메시지를 전파하는 데 사용하는 프로토콜을 사용할 경우 메시지 전파 메커니즘이 PPL\([병렬 패턴 라이브러리](../../parallel/concrt/parallel-patterns-library-ppl.md)\)에서 제공하는 작업 병렬 구문보다 많은 오버헤드를 포함하게 됩니다.  따라서 데이터 파이프라인에서 수행하는 작업이 이러한 오버헤드를 상쇄할 만큼 충분히 긴지 확인해야 합니다.  
  
 데이터 파이프라인은 해당 작업이 정교하지 않은 경우 가장 효과적이지만 데이터 파이프라인의 각 단계는 작업 그룹 및 병렬 알고리즘과 같은 PPL 구문을 사용하여 더 세분화된 작업을 수행할 수 있습니다.  각 처리 단계에서 세분화된 병렬 처리를 사용하는 정교하지 않은 데이터 네트워크의 예제를 보려면 [연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)를 참조하십시오.  
  
 \[[맨 위](#top)\]  
  
##  <a name="large-payloads"></a> 큰 메시지 페이로드는 값으로 전달하지 않음  
 런타임에서 메시지 버퍼 간에 전달하는 모든 메시지의 복사본을 만드는 경우가 있습니다.  예를 들어 [concurrency::overwrite\_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) 클래스는 받는 모든 메시지의 복사본을 각 대상에 제공합니다.  런타임에서는 [concurrency::send](../Topic/send%20Function.md) 및 [concurrency::receive](../Topic/receive%20Function.md)와 같은 메시지 전달 함수를 사용하여 메시지 버퍼에 메시지를 쓰거나 메시지 버퍼에서 메시지를 읽을 때도 메시지 데이터의 복사본을 만듭니다.  이 메커니즘을 사용하면 공유 데이터에 동시에 쓰는 위험 부담이 없어지지만 메시지 페이로드가 비교적 클 경우 메모리 성능이 저하될 수 있습니다.  
  
 페이로드가 큰 메시지를 전달할 때는 포인터 또는 참조를 사용하여 메모리 성능을 향상시킬 수 있습니다.  다음 예제에서는 큰 메시지를 값으로 전달하는 경우와 동일한 메시지 형식에 포인터를 전달하는 경우를 비교합니다.  이 예제에서는 `message_data` 개체에서 작동하는 `producer` 및 `consumer`라는 두 가지 에이전트 형식을 정의합니다.  그리고 이 예제에서는 생산자가 `message_data` 개체를 소비자에게 보내는 데 필요한 시간과 생산자 에이전트가 `message_data` 개체에 대한 여러 포인터를 소비자에게 보내는 데 필요한 시간을 비교합니다.  
  
 [!code-cpp[concrt-message-payloads#1](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-asynchronous-agents-library_3.cpp)]  
  
 이 예제를 실행하면 다음과 같은 샘플 결과가 출력됩니다.  
  
  **Message\_data 사용...**  
**437ms 시간이 걸렸습니다.**  
**Message\_data\* 사용...**  
**47ms 시간이 걸렸습니다.** 포인터를 사용하는 경우 런타임에서 생산자로부터 소비자에게 전달하는 모든 `message_data` 개체의 전체 복사본을 만들 필요가 없기 때문에 포인터를 사용하는 버전이 더 성능이 뛰어납니다.  
  
 \[[맨 위](#top)\]  
  
##  <a name="ownership"></a> 소유권이 정의되어 있지 않을 경우 데이터 네트워크에서 shared\_ptr 사용  
 메시지 전달 파이프라인 또는 네트워크를 통해 포인터를 사용하여 메시지를 보낼 때 일반적으로 각 메시지에 사용할 메모리를 네트워크의 앞에 할당하고 네트워크의 끝 부분에서 해당 메모리 공간을 확보합니다.  이 메커니즘은 대부분 제대로 작동하지만 이 메커니즘을 사용할 수 없거나 힘든 경우가 있습니다.  예를 들어 데이터 네트워크에 여러 끝 노드가 포함되어 있는 경우를 가정해 봅니다.  이 경우에는 메시지에 사용할 메모리를 확보할 확실한 위치가 없습니다.  
  
 이 문제를 해결하려면 하나의 포인터를 여러 구성 요소가 소유할 수 있도록 설정하는 [std::shared\_ptr](../../standard-library/shared-ptr-class.md)과 같은 메커니즘을 사용할 수 있습니다.  리소스가 속한 최종 `shared_ptr` 개체를 삭제하면 리소스도 해제됩니다.  
  
 다음 예제에서는 `shared_ptr`을 사용하여 여러 메시지 버퍼 간에 포인터 값을 공유하는 방법을 보여 줍니다.  그리고 [concurrency::overwrite\_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) 개체를 세 개의 [concurrency::call](../../parallel/concrt/reference/call-class.md) 개체에 연결합니다.  `overwrite_buffer` 클래스는 각 대상에 메시지를 제공합니다.  데이터 네트워크의 끝 부분에 데이터의 여러 소유자가 있으므로 이 예제에서는 `shared_ptr`을 사용하여 각 `call` 개체가 메시지의 소유권을 공유할 수 있도록 설정합니다.  
  
 [!code-cpp[concrt-message-sharing#1](../../parallel/concrt/codesnippet/CPP/best-practices-in-the-asynchronous-agents-library_4.cpp)]  
  
 이 예제를 실행하면 다음과 같은 샘플 결과가 출력됩니다.  
  
  **리소스 42 만들기...**  
**receiver1: 42 리소스를 받았습니다**  
**리소스 64 만들기...**  
**receiver1: 42 리소스를 받았습니다**  
**receiver1: 64 리소스를 받았습니다**  
**42 자원 파괴...**  
**receiver1: 64 리소스를 받았습니다**  
**64 자원 파괴...**   
## 참고 항목  
 [동시성 런타임 유용한 정보](../../parallel/concrt/concurrency-runtime-best-practices.md)   
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [연습: 에이전트 기반 응용 프로그램 만들기](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)   
 [연습: 데이터 흐름 에이전트 만들기](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)   
 [연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)   
 [병렬 패턴 라이브러리의 유용한 정보](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)   
 [동시성 런타임의 유용한 일반 정보](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)