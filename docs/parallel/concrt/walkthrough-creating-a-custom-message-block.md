---
title: "연습: 사용자 지정 메시지 블록 만들기 | Microsoft Docs"
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
  - "사용자 지정 메시지 블록 만들기[동시성 런타임]"
  - "사용자 지정 메시지 블록 만들기 [동시성 런타임]"
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: 사용자 지정 메시지 블록 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 문서에는 들어오는 메시지를 우선 순위별로 정렬 하는 사용자 지정 메시지 블록 형식을 만드는 방법을 설명 합니다.  
  
 기본 제공 메시지 블록 형식을 다양 한 기능을 제공 하지만 메시지 블록 형식을 만들고 응용 프로그램의 요구에 맞게 사용자 지정할 수 있습니다. 비동기 에이전트 라이브러리에서 제공 되는 기본 제공 메시지 블록 형식에 대 한 참조 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)합니다.  
  
## <a name="prerequisites"></a>필수 조건  
 이 연습을 시작 하기 전에 다음 문서를 읽어 보십시오.  
  
- [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)  
  
- [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)  
  
##  <a name="a-nametopa-sections"></a><a name="top"></a> 섹션  
 이 연습에는 다음과 같은 섹션이 있습니다.  
  
- [사용자 지정 메시지 블록 디자인](#design)  
  
- [Priority_buffer 클래스를 정의합니다.](#class)  
  
- [전체 예제](#complete)  
  
##  <a name="a-namedesigna-designing-a-custom-message-block"></a><a name="design"></a> 사용자 지정 메시지 블록 디자인  
 메시지 블록의 메시지 보내기 및 받기 작업에 참여 합니다. 메시지를 보내는 메시지 블록 이라고는 *소스 블록*합니다. 메시지를 수신 하는 메시지 블록 이라고는 *대상 블록*합니다. 보내고 메시지를 수신 하는 메시지 블록 이라고는 *전파자 블록*합니다. 에이전트 라이브러리는 추상 클래스를 사용 하 여 [concurrency:: isource](../../parallel/concrt/reference/isource-class.md) 소스 블록을 나타내고 추상 클래스 [concurrency:: itarget](../../parallel/concrt/reference/itarget-class.md) 를 대상 블록을 나타냅니다. 메시지 블록에서 파생 되는 원본으로 작동 하는 형식은 `ISource`; 메시지 블록에서 파생 되는 대상으로 작동 하는 형식은 `ITarget`합니다.  
  
 직접 메시지 블록 형식을 파생할 수 있지만 `ISource` 및 `ITarget`, 대부분의 모든 메시지 블록 형식에 공통 된 기능을 수행 하는 세 가지 기본 클래스를 정의 하는 에이전트 라이브러리, 예를 들어, 오류 처리 및 메시지 연결 차단 함께 동시성이 방식입니다.  [concurrency:: source_block](../../parallel/concrt/reference/source-block-class.md) 클래스에서 파생 되며 `ISource` 하 고 다른 블록에 메시지를 보냅니다.  [concurrency:: target_block](../../parallel/concrt/reference/target-block-class.md) 클래스에서 파생 되며 `ITarget` 다른 블록에서 메시지를 받습니다.  [concurrency:: propagator_block](../../parallel/concrt/reference/propagator-block-class.md) 클래스에서 파생 되며 `ISource` 및 `ITarget` 고 메시지를 다른 블록에 보내고 다른 블록에서 메시지를 수신 합니다. 이러한 세 가지 기본 클래스를 사용 하 여 메시지 블록의 동작에 초점을 맞출 수 있도록 인프라 세부 정보를 처리 하는 것이 좋습니다.  
  
  `source_block`, `target_block`, 및 `propagator_block` 클래스는 연결을 관리 하거나 연결 하는 형식, 원본 및 대상 블록 사이 및에 메시지를 처리 하는 방법을 관리 하는 형식 매개 변수화 된 템플릿입니다. 에이전트 라이브러리에는 링크 관리를 수행 하는 두 가지 형식을 정의 [concurrency:: single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) 및 [concurrency:: multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md)합니다.  `single_link_registry` 클래스를 사용 하면 하나의 소스 나 대상을 두 개를 연결 하는 메시지 블록입니다.  `multi_link_registry` 클래스를 사용 하면 메시지 블록을 여러 원본 또는 여러 대상에 연결할 수 있습니다. 메시지 관리를 수행 하는 하나의 클래스를 정의 하는 에이전트 라이브러리 [concurrency:: ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md)합니다.  `ordered_message_processor` 클래스를 사용 하면 메시지 블록을 받는 순서 대로 메시지를 처리 합니다.  
  
 원본 및 대상을 메시지 블록의 관계를 더 잘 이해 하려면 다음 예제를 참조 하세요. 선언을 보여 주는이 예제는 [concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) 클래스입니다.  
  
 [!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_1.cpp)]  
  
  `transformer` 클래스에서 파생 되며 `propagator_block`, 따라서 소스 블록으로 및 대상 블록 역할을 합니다. 유형의 메시지를 수락 `_Input` 형식의 메시지를 보내고 `_Output`합니다.  `transformer` 클래스 지정 `single_link_registry` 모든 대상 블록에 대 한 연결 관리자 및 `multi_link_registry` 소스 블록에 대 한 연결 관리자입니다. 따라서 한 `transformer` 대상을 두 개를 개수에 제한 없이 원본 개체 있을 수 있습니다.  
  
 파생 되는 클래스 `source_block` 6 가지 메서드를 구현 해야 합니다: [propagate_to_any_targets](../Topic/source_block::propagate_to_any_targets%20Method.md), [accept_message](../Topic/source_block::accept_message%20Method.md), [reserve_message](../Topic/source_block::reserve_message%20Method.md), [consume_message](../Topic/source_block::consume_message%20Method.md), [release_message](../Topic/source_block::release_message%20Method.md), 및 [resume_propagation](../Topic/source_block::resume_propagation%20Method.md)합니다. 파생 되는 클래스 `target_block` 구현 해야는 [propagate_message](../Topic/propagator_block::propagate_message%20Method.md) 메서드 및 선택적으로 구현할 수는 [send_message](../Topic/propagator_block::send_message%20Method.md) 메서드. 파생 된 `propagator_block` 는 둘 다에서 파생 하는 기능적 `source_block` 및 `target_block`합니다.  
  
  `propagate_to_any_targets` 메서드는 동기적 또는 비동기적으로 들어오는 메시지를 처리 하 고 보내는 메시지를 전파 하는 런타임에서 호출 됩니다.  `accept_message` 메시지를 받을 대상 블록에서 메서드를 호출 합니다. 와 같은 많은 메시지 블록 형식을 `unbounded_buffer`, 를 받을 첫 번째 대상에만 메시지를 보냅니다. 따라서 대상에 메시지의 소유권을 전송합니다. 와 같은 기타 메시지 블록 형식은 [concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md), 각 대상 블록에 메시지를 제공 합니다. 따라서 `overwrite_buffer` 각 대상에 대 한 메시지의 복사본을 만듭니다.  
  
  `reserve_message`, `consume_message`, `release_message`, 및 `resume_propagation` 메서드 메시지 블록이 메시지 예약에 참여할 수 있도록 합니다. 호출을 차단 하는 대상은 `reserve_message` 메서드는 메시지를 제공 하며 나중에 사용할 메시지를 예약 해야 합니다. 대상 블록은 메시지를 예약한 후 호출할 수는 `consume_message` 해당 메시지를 사용 하는 메서드 또는 `release_message` 메서드를 예약을 취소 합니다. 와 마찬가지로 `accept_message` 메서드를 구현 `consume_message` 메시지의 소유권을 이전 하거나 메시지의 복사본을 반환 합니다. 대상 블록에 사용 하거나 예약된 된 메시지를 해제, 후에 런타임에서 호출의 `resume_propagation` 메서드. 일반적으로이 메서드는 큐에서 다음 메시지부터 시작 하는 메시지 전파를 계속 합니다.  
  
 런타임 호출의 `propagate_message` 메서드를 비동기적으로 현재 다른 블록에서 메시지를 전송 합니다.  `send_message` 메서드 유사한 `propagate_message`, 점을 제외 하 고 동기적으로 대신 비동기적으로 메시지를 보낼 대상 블록에 있습니다. 기본 구현은 `send_message` 모든 들어오는 메시지를 거부 합니다. 런타임 호출 하지 않습니다 이러한 방법 중 하나는 메시지는 대상 블록에 연결 하는 선택적 필터 함수를 전달 하지 않는 경우. 메시지 필터에 대 한 자세한 내용은 참조 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-nameclassa-defining-the-prioritybuffer-class"></a><a name="class"></a> Priority_buffer 클래스를 정의합니다.  
  `priority_buffer` 클래스는 들어오는 메시지를 먼저 정렬 한 다음 메시지를 수신 하는 순서를 우선 하는 사용자 지정 메시지 블록 형식을 합니다.  `priority_buffer` 클래스와 유사는 [concurrency:: unbounded_buffer](../Topic/unbounded_buffer%20Class.md) 메시지 큐를 포함 하기 때문에 클래스도 원본 및 대상 메시지 블록 역할을 하 고 여러 소스 및 여러 대상을 포함할 수 있으므로 합니다. 그러나 `unbounded_buffer` 메시지를 전파할 때 소스에서 메시지를 받는 순서에만 전파 합니다.  
  
  `priority_buffer` 형식의 메시지를 수신 하는 클래스 std::[튜플](../../standard-library/tuple-class.md) 를 포함 하는 `PriorityType` 및 `Type` 요소입니다. `PriorityType` 각 메시지의 우선 순위를 보유 하는 형식을 참조합니다 `Type` 메시지의 데이터 부분을 참조 합니다.  `priority_buffer` 클래스 유형의 메시지를 보냅니다 `Type`합니다.  `priority_buffer` 클래스에는 또한 두 개의 메시지 큐 관리:는 [std::priority_queue](../../standard-library/priority-queue-class.md) 들어오는 메시지에 대 한 개체와는 std::[큐](../../standard-library/queue-class.md) 보내는 메시지에 대 한 개체입니다. 우선 순위에 따라 메시지 순서 지정은 같은 경우 유용 한 `priority_buffer` 개체에서 여러 메시지를 동시에 수신 또는 소비자가 메시지를 읽기 전에 여러 메시지를 받는 경우.  
  
 7 메서드 외에도 파생 되는 클래스가 `propagator_block` 구현 해야는 `priority_buffer` 클래스도 재정의 `link_target_notification` 및 `send_message` 메서드.  `priority_buffer` 클래스는 또한 두 개의 공용 도우미 메서드를 정의 `enqueue` 및 `dequeue`, 와 전용 도우미 메서드를 `propagate_priority_order`합니다.  
  
 다음 절차를 구현 하는 방법에 설명 된 `priority_buffer` 클래스입니다.  
  
#### <a name="to-define-the-prioritybuffer-class"></a>Priority_buffer 클래스를 정의 하려면  
  
1.  C + + 헤더 파일을 만들고 이름을 `priority_buffer.h`합니다. 또는 프로젝트의 일부인 기존 헤더 파일을 사용할 수 있습니다.  
  
2.   `priority_buffer.h`, 다음 코드를 추가 합니다.  
  
 [!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_2.h)]  
  
3.  에 `std` 네임 스페이스의 특수화를 정의 [std:: less](../../standard-library/less-struct.md) 및 [std::greater](../../standard-library/greater-struct.md) 동시성에서 작동 하는::[메시지](../../parallel/concrt/reference/message-class.md) 개체입니다.  
  
 [!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_3.h)]  
  
      `priority_buffer` 저장소 클래스 `message` 개체에 `priority_queue` 개체입니다. 우선 순위에 따라 메시지를 정렬 우선 순위 큐를 사용 하는 이러한 형식을 특수화 합니다. 우선 순위는 첫 번째 요소는 `tuple` 개체입니다.  
  
4.  에 `concurrencyex` 네임 스페이스 선언에서 `priority_buffer` 클래스입니다.  
  
 [!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_4.h)]  
  
     `priority_buffer` 클래스는 `propagator_block`에서 파생됩니다. 따라서 모두을 보내고 메시지를 수신 합니다.  `priority_buffer` 클래스 유형의 메시지를 수신 하는 여러 대상이 있을 수 있습니다 `Type`합니다. 형식의 메시지를 전송 하는 여러 소스 수도 `tuple<PriorityType, Type>`합니다.  
  
5.  에 `private` 의 섹션은 `priority_buffer` 클래스를 다음 멤버 변수를 추가 합니다.  
  
 [!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_5.h)]  
  
      `priority_queue` 들어오는 메시지를 보유 하는 개체 이며, `queue` 보내는 메시지를 보유 하는 개체입니다. A `priority_buffer` 개체는 동시에 여러 메시지를 받을 수 있습니다; `critical_section` 입력된 메시지의 큐에 대 한 액세스를 동기화 하는 개체입니다.  
  
6.  에 `private` 섹션 복사 생성자와 대입 연산자를 정의 합니다. 이렇게 하면 `priority_queue` 개체를 할당할 수 없게 합니다.  
  
 [!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_6.h)]  
  
7.  에 `public` 섹션에서 여러 메시지 블록 형식에 공통적으로 적용 되는 생성자를 정의 합니다. 또한 소멸자를 정의 합니다.  
  
 [!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_7.h)]  
  
8.  에 `public` 섹션에서 메서드를 정의 `enqueue` 및 `dequeue`합니다. 메시지를 전송에서 메시지를 수신 하는 또 다른 방법은 제공 하는 이러한 도우미 메서드는 `priority_buffer` 개체입니다.  
  
 [!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_8.h)]  
  
9. 에 `protected` 섹션에서 정의 된 `propagate_to_any_targets` 메서드.  
  
 [!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_9.h)]  
  
      `propagate_to_any_targets` 메서드 출력 큐에 입력된 큐의 앞 부분에 있고 출력 큐의 모든 메시지를 전파 하는 메시지를 전송 합니다.  
  
10. 에 `protected` 섹션에서 정의 된 `accept_message` 메서드.  
  
 [!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_10.h)]  
  
     대상 블록은 호출 하는 경우는 `accept_message` 메서드는 `priority_buffer` 클래스 수락 하는 첫 번째 대상 블록에 메시지의 소유권을 전송 합니다. (이의 동작과 비슷합니다 `unbounded_buffer`.)  
  
11. 에 `protected` 섹션에서 정의 된 `reserve_message` 메서드.  
  
 [!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_11.h)]  
  
      `priority_buffer` 클래스에서 제공 된 메시지 식별자가 큐의 앞에 있는 메시지의 식별자와 일치 하는 경우 메시지를 예약 하는 대상 블록을 허용 합니다. 즉, 통해 대상을 경우 메시지를 예약할 수는 `priority_buffer` 개체는 추가 메시지를 아직 받지 못한와 현재 아직 전파 되지 않습니다.  
  
12. 에 `protected` 섹션에서 정의 된 `consume_message` 메서드.  
  
 [!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_12.h)]  
  
     호출 하는 대상 블록 `consume_message` 으로 예약 된 메시지의 소유권을 전송할 수 있습니다.  
  
13. 에 `protected` 섹션에서 정의 된 `release_message` 메서드.  
  
 [!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_13.h)]  
  
     호출 하는 대상 블록 `release_message` 메시지에 대 한 예약을 취소 합니다.  
  
14. 에 `protected` 섹션에서 정의 된 `resume_propagation` 메서드.  
  
 [!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_14.h)]  
  
     런타임 호출 `resume_propagation` 후 대화 상자는 대상 블록은 사용 하거나 예약된 된 메시지를 해제 합니다. 이 메서드는 출력 큐에 있는 모든 메시지를 전파 합니다.  
  
15. 에 `protected` 섹션에서 정의 된 `link_target_notification` 메서드.  
  
 [!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_15.h)]  
  
      `_M_pReservedFor` 멤버 변수는 기본 클래스에 의해 정의 된 `source_block`합니다. 이 멤버 변수는 출력 큐의 앞에 있는 메시지에 대 한 예약을 포함 하는 경우 대상 블록을 가리킵니다. 런타임 호출 `link_target_notification` 새 대상에 연결 되는 경우는 `priority_buffer` 개체입니다. 이 메서드를 대상이 없습니다. 한 예약을 포함 하는 경우 출력 큐에 있는 모든 메시지를 전파 합니다.  
  
16. 에 `private` 섹션에서 정의 된 `propagate_priority_order` 메서드.  
  
 [!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_16.h)]  
  
     이 메서드는 출력 큐의 모든 메시지를 전파합니다. 큐에 있는 모든 메시지는 대상 블록 중 하나가 메시지를 수락할 때까지 모든 대상 블록에 제공 됩니다.  `priority_buffer` 클래스는 나가는 메시지의 순서를 유지 합니다. 따라서이 메서드는 대상 블록에 있는 다른 모든 메시지를 제공 하기 전에 출력 큐의 첫 번째 메시지는 대상 블록은가 동의 해야 합니다.  
  
17. 에 `protected` 섹션에서 정의 된 `propagate_message` 메서드.  
  
 [!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_17.h)]  
  
      `propagate_message` 메서드를 사용 하면은 `priority_buffer` 또는 메시지 수신자 역할을 클래스를 대상으로 합니다. 이 메서드는 제공 된 소스 블록에서 제공 하 고 우선 순위 큐에 메시지를 삽입 하는 메시지를 받습니다.  `propagate_message` 다음 비동기적으로 보냅니다 모든 대상 블록에 메시지를 출력 합니다.  
  
     호출할 때 런타임에서이 메서드를 호출의 [concurrency:: asend](../Topic/asend%20Function.md) 함수 또는 메시지 블록이 다른 메시지 블록에 연결 되어는 때입니다.  
  
18. 에 `protected` 섹션에서 정의 된 `send_message` 메서드.  
  
 [!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_18.h)]  
  
      `send_message` 메서드 유사한 `propagate_message`합니다. 그러나 비동기적이 아닌 동기적으로 출력 메시지를 보냅니다.  
  
     호출할 때 처럼 동기 보내기 작업을 하는 동안이 메서드를 호출 하는 런타임에서 [concurrency:: send](../Topic/send%20Function.md) 함수입니다.  
  
  `priority_buffer` 클래스는 일반적으로 여러 메시지 블록 형식에는 생성자 오버 로드를 포함 합니다. 일부 생성자 오버 로드를 [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 또는 [concurrency:: schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md) 메시지 블록을 특정 작업 스케줄러를 관리할 수 있도록 하는 개체입니다. 다른 생성자 오버 로드는 필터 함수를 받습니다. 필터 함수를 메시지 블록이 수락 하거나 거부할 페이로드를 기준으로 메시지를 사용 합니다. 메시지 필터에 대 한 자세한 내용은 참조 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)합니다. 작업 스케줄러에 대 한 자세한 내용은 참조 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)합니다.  
  
 때문에 `priority_buffer` 클래스는 메시지를 우선 순위별로 정렬 하 고 다음 메시지를 수신 하는 순서에서이 클래스는 가장 유용한 경우 메시지를 비동기적으로 받는, 예를 들어 호출 하는 경우는 [concurrency:: asend](../Topic/asend%20Function.md) 함수 또는 메시지 블록이 다른 메시지 블록에 연결 되어는 때입니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-namecompletea-the-complete-example"></a><a name="complete"></a> 전체 예제  
 다음 예제에서는의 완벽 한 정의 `priority_buffer` 클래스입니다.  
  
 [!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_19.h)]  
  
 다음 예제에서는 여러 가지를 동시에 수행 `asend` 및 [concurrency:: receive](../Topic/receive%20Function.md) 에 대 한 작업을 `priority_buffer` 개체입니다.  
  
 [!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_20.cpp)]  
  
 이 예제는 다음 예제 출력을 생성 합니다.  
  
```Output  
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36  
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24  
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12  
```  
  
  `priority_buffer` 클래스 메시지 정렬 먼저 우선 순위별로 정리한 다음 메시지를 받는 순서입니다. 이 예제에서 큰 숫자 우선 순위를 사용 하 여 메시지 큐의 앞쪽 방향으로 삽입 됩니다.  
  
 [[맨 위로 이동](#top)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나의 정의 붙여 넣습니다.는 `priority_buffer` 라는 파일에 클래스 `priority_buffer.h` 라는 파일에서 프로그램을 테스트 하 고 `priority_buffer.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc priority_buffer.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)
