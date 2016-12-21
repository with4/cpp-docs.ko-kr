---
title: "비동기 메시지 블록 | Microsoft Docs"
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
  - "non-greedy 조인[동시성 런타임]"
  - "비동기 메시지 블록"
  - "greedy 조인[동시성 런타임]"
ms.assetid: 79c456c0-1692-480c-bb67-98f2434c1252
caps.latest.revision: 36
caps.handback.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 비동기 메시지 블록
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

에이전트 라이브러리는 스레드로부터 안전한 방식으로 응용 프로그램 구성 요소 간에 메시지를 전파할 수 있도록 하는 몇 가지 메시지 블록 형식을 제공 합니다. 이러한 메시지 블록 형식은 종종 같은 사용 되어 다양 한 메시지 전달 루틴을 사용 하 여 [concurrency:: send](../Topic/send%20Function.md), [concurrency:: asend](../Topic/asend%20Function.md), [concurrency:: receive](../Topic/receive%20Function.md), 및 [concurrency:: try_receive](../Topic/try_receive%20Function.md)합니다. 메시지 전달 에이전트 라이브러리에서 정의 된 루틴에 대 한 자세한 내용은 참조 [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)합니다.  
  
##  <a name="a-nametopa-sections"></a><a name="top"></a> 섹션  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
- [소스 및 대상](#sources_and_targets)  
  
- [메시지 전파](#propagation)  
  
- [메시지 블록 형식 개요](#overview)  
  
- [unbounded_buffer 클래스](#unbounded_buffer)  
  
- [overwrite_buffer 클래스](#overwrite_buffer)  
  
- [single_assignment 클래스](#single_assignment)  
  
- [call 클래스](#call)  
  
- [transformer 클래스](#transformer)  
  
- [choice 클래스](#choice)  
  
- [조인 및 multitype_join 클래스](#join)  
  
- [timer 클래스](#timer)  
  
- [메시지 필터링](#filtering)  
  
- [메시지 예약](#reservation)  
  
##  <a name="a-namesourcesandtargetsa-sources-and-targets"></a><a name="sources_and_targets"></a> 소스 및 대상  
 소스 및 대상 메시지 전달의 두 가지 중요 한 참가자가 됩니다. A *소스* 은 메시지를 보내는 통신의 끝점을 나타냅니다. A *대상* 은 메시지를 수신 하는 통신의 끝점을 나타냅니다. 끝점에서 읽은 소스 및 대상에 기록 하는 끝점으로 생각할 수 있습니다. 폼에 소스와 대상을 서로 연결 하는 응용 프로그램 *메시징 네트워크*합니다.  
  
 에이전트 라이브러리는 두 가지 추상 클래스를 사용 하 여 소스와 대상을 나타내는: [concurrency:: isource](../../parallel/concrt/reference/isource-class.md) 및 [concurrency:: itarget](../../parallel/concrt/reference/itarget-class.md)합니다. 메시지 블록에서 파생 되는 원본으로 작동 하는 형식은 `ISource`; 메시지 블록에서 파생 되는 대상으로 작동 하는 형식은 `ITarget`합니다. 메시지 블록 원본으로 작동 하는 형식 및 대상 둘 다에서 파생 `ISource` 및 `ITarget`합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-namepropagationa-message-propagation"></a><a name="propagation"></a> 메시지 전파  
 *메시지 전파* 다른 하나의 구성 요소에서 메시지를 전송 하는 동작입니다. 메시지 블록은 제공 된 경우 수락을 거부 하거나 해당 메시지를 연기할 수 것입니다. 모든 메시지 블록 형식을 저장 하 고 다른 방법으로 메시지를 전송 합니다. 예를 들어는 `unbounded_buffer` 개수에 제한 없이 메시지를 저장 하는 클래스는 `overwrite_buffer` 한 번에 하나의 메시지를 저장 하는 클래스 및 transformer 클래스는 각 메시지의 변경된 된 버전을 저장 합니다. 이러한 메시지 블록 형식은이 문서의 뒷부분에 자세히 설명 되어 있습니다.  
  
 메시지 블록에서 메시지를 수락 하는 경우 수 필요에 따라 작업을 수행 하 고, 메시지 블록에서 소스, 결과 메시지는 네트워크의 다른 멤버에 전달 합니다. 메시지를 수신 하지 않을 것을 거부 하도록 메시지 블록 필터 함수를 사용할 수 있습니다. 필터 섹션에서이 항목의 뒷부분에 자세히 설명 되어 [메시지 필터링](#filtering)합니다. 메시지를 연기 하는 메시지 블록 해당 메시지를 예약 하 고 나중에 사용할 수 있습니다. 메시지 예약 섹션에서이 항목의 뒷부분에 자세히 설명 되어 [메시지 예약](#reservation)합니다.  
  
 에이전트 라이브러리 메시지 블록을 비동기적으로 사용 하거나 동기적으로 메시지를 전달 합니다. 전달 하는 경우 메시지는 메시지 블록에 동기적으로 예를 들어를 사용 하 여는 `send` 함수의 경우, 런타임은 현재 컨텍스트를 차단 대상 블록은 수락 또는 해당 메시지를 거부 될 때까지 합니다. 전달 하는 경우 메시지는 메시지 블록에 비동기적으로 예를 들어를 사용 하 여는 `asend` 함수, 런타임에서 대상에 메시지를 제공 하 고 대상에서 메시지를 수락 하는 경우 런타임에서 수신자에 게 메시지를 전파 하는 비동기 작업을 예약 합니다. 런타임에서 협조적 방식으로 메시지를 전파 하 간단한 작업을 사용 합니다. 간단한 작업에 대 한 자세한 내용은 참조 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)합니다.  
  
 응용 프로그램 소스와 대상을 연결 함께 메시징 네트워크를 구성 합니다. 일반적으로, 네트워크 및 호출 링크 `send` 또는 `asend` 네트워크에 데이터를 전달할 수 있습니다. 소스 메시지 블록을 대상에 연결 하려면 호출의 [concurrency::ISource::link_target](../Topic/ISource::link_target%20Method.md) 메서드. 대상에서 소스 블록 연결을 끊으려면 호출의 [concurrency::ISource::unlink_target](../Topic/ISource::unlink_target%20Method.md) 메서드. 모든 대상에서 소스 블록 연결을 끊으려면 호출의 [concurrency::ISource::unlink_targets](../Topic/ISource::unlink_targets%20Method.md) 메서드. 미리 정의 된 메시지 블록 형식 중 하나가 범위를 벗어나거나 소멸 되,이 자동으로 연결이 끊어집니다 자체 모든 대상 블록에서. 일부 메시지 블록 형식은 쓸 수 있는 대상의 최대 수를 제한 합니다. 다음 섹션에는 미리 정의 된 메시지 블록 형식에 적용 되는 제한을 설명 합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-nameoverviewa-overview-of-message-block-types"></a><a name="overview"></a> 메시지 블록 형식 개요  
 다음 표에서 중요 한 메시지 블록 형식의 역할을 간략하게 설명합니다.  
  
 [unbounded_buffer](#unbounded_buffer)  
 메시지 큐를 저장합니다.  
  
 [overwrite_buffer](#overwrite_buffer)  
 에 기록 하 고 여러 번에서 읽을 수 있는 하나의 메시지를 저장 합니다.  
  
 [single_assignment](#single_assignment)  
 한 번에 기록 하 고 여러 번에서 읽을 수 있는 하나의 메시지를 저장 합니다.  
  
 [호출](#call)  
 메시지를 받을 때 작업을 수행 합니다.  
  
 [변환기](#transformer)  
 데이터를 받고 다른 대상 블록에 해당 작업의 결과 전송 하는 경우 작업을 수행 합니다.  `transformer` 클래스는 서로 다른 입력 및 출력 형식에서 작동할 수 있습니다.  
  
 [선택](#choice)  
 일련의 소스에서 가능한 첫 번째 메시지를 선택합니다.  
  
 [조인 및 다중 조인](#join)  
 모든 메시지를 소스 집합에서 받을 수와 다음 다른 메시지 블록에 대 한 하나의 메시지에 메시지를 결합 될 때까지 기다립니다.  
  
 [타이머](#timer)  
 일정 한 간격으로 대상 블록에 메시지를 보냅니다.  
  
 이러한 메시지 블록 형식은 다른 상황에 유용 하 게 하는 다른 특징을 갖습니다. 다음은 일부의 특성입니다.  
  
- *전파 형식*: 메시지 블록에서 데이터, 데이터, 수신기 또는 둘 다의 원본으로 작동 하는 여부.  
  
- *메시지 순서*: 메시지 블록에서 메시지의 전송 또는 수신 원래 순서를 유지 하는 여부. 각 미리 정의 된 메시지 블록 형식은 원래 순서를 보내거나 받을 메시지를 유지 관리 합니다.  
  
- *Count 원본*: 메시지 블록에서 읽을 수 있는 원본의 최대 수입니다.  
  
- *개수를 대상으로*: 메시지 블록에 쓸 수 있는 대상의 최대 수입니다.  
  
 다음 표에서 다양 한 메시지 블록 형식에 이러한 특성의 관계를 보여 줍니다.  
  
|메시지 블록 형식|전파 형식 (원본, 대상 또는 둘 다)|메시지 순서 지정 (Ordered 또는 순서 지정 안 됨)|소스 개수|대상 개수|  
|------------------------|--------------------------------------------------|-----------------------------------------------|------------------|------------------|  
|`unbounded_buffer`|Both|Ordered|바인딩되지 않은|바인딩되지 않은|  
|`overwrite_buffer`|Both|Ordered|바인딩되지 않은|바인딩되지 않은|  
|`single_assignment`|Both|Ordered|바인딩되지 않은|바인딩되지 않은|  
|`call`|Target|Ordered|바인딩되지 않은|해당 없음|  
|`transformer`|Both|Ordered|바인딩되지 않은|1|  
|`choice`|Both|Ordered|10|1|  
|`join`|Both|Ordered|바인딩되지 않은|1|  
|`multitype_join`|Both|Ordered|10|1|  
|`timer`|소스|해당 없음|해당 없음|1|  
  
 다음 섹션에서는 메시지 블록 형식에서 더 자세하게 설명합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-nameunboundedbuffera-unboundedbuffer-class"></a><a name="unbounded_buffer"></a> unbounded_buffer 클래스  
  [concurrency:: unbounded_buffer](../Topic/unbounded_buffer%20Class.md) 클래스는 일반적인 용도의 비동기 메시징 구조를 나타냅니다. 이 클래스는 여러 소스가 기록하거나 여러 대상이 읽을 수 있는 메시지의 FIFO(선입 선출) 큐를 저장합니다. 대상에서 메시지를 수신 하는 경우는 `unbounded_buffer` 개체를 해당 메시지가 메시지 큐에서 제거 됩니다. 따라서 있지만 `unbounded_buffer` 개체에는 여러 대상이 있을 수 있습니다, 하나의 대상만 각 메시지를 받게 됩니다. `unbounded_buffer` 클래스는 여러 메시지를 다른 구성 요소에 전달하려고 할 때 유용하고 해당 구성 요소는 각 메시지를 수신해야 합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 작업 방법의 기본 구조는 `unbounded_buffer` 클래스입니다. 이 예제에서는 세 가지 값을 보냅니다는 `unbounded_buffer` 개체와 다음 다시 동일한 개체에서에서 해당 값을 읽습니다.  
  
 [!code-cpp[concrt-unbounded_buffer-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_1.cpp)]  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```Output  
334455  
```  
  
 사용 하는 방법을 보여 주는 전체 예제는 `unbounded_buffer` 클래스를 참조 하십시오 [하는 방법: 공급자-소비자 패턴을 다양 한 구현](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-nameoverwritebuffera-overwritebuffer-class"></a><a name="overwrite_buffer"></a> overwrite_buffer 클래스  
  [concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) 클래스와 유사는 `unbounded_buffer` 점을 제외 하 고 클래스는 `overwrite_buffer` 하나의 메시지를 저장 하는 개체입니다. 대상에서 메시지를 받았을 때 뿐만 아니라는 `overwrite_buffer` 개체를 해당 메시지 버퍼에서 제거 되지 않습니다. 따라서 여러 대상이 하나의 메시지 복사본을 수신합니다.  
  
  `overwrite_buffer` 클래스는 다른 구성 요소에 여러 메시지를 전달 하려고 하지만 해당 구성 요소는 가장 최근의 값만 필요한 경우 유용 합니다. 이 클래스는 여러 구성 요소에 메시지를 브로드캐스트하려고 할 때도 유용합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 작업 방법의 기본 구조는 `overwrite_buffer` 클래스입니다. 이 예제에서는 세 가지 값을 보냅니다는 `overwrite _buffer` 개체를 다음 동일한 개체에서 현재 값을 세 번 읽습니다. 이 예제는에 대 한 예제와 비슷한는 `unbounded_buffer` 클래스입니다. 그러나는 `overwrite_buffer` 클래스는 하나의 메시지를 저장 합니다. 또한 런타임에 메시지에서 제거 되지 않습니다는 `overwrite_buffer` 를 읽은 다음 개체입니다.  
  
 [!code-cpp[concrt-overwrite_buffer-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_2.cpp)]  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```Output  
555555  
```  
  
 사용 하는 방법을 보여 주는 전체 예제는 `overwrite_buffer` 클래스를 참조 하십시오 [하는 방법: 공급자-소비자 패턴을 다양 한 구현](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-namesingleassignmenta-singleassignment-class"></a><a name="single_assignment"></a> single_assignment 클래스  
  [concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) 클래스와 유사는 `overwrite_buffer` 점을 제외 하 고 클래스는 `single_assignment` 개체에 한 번만 쓸 수 있습니다. `overwrite_buffer` 클래스처럼 대상이 `single_assignment` 개체에서 메시지를 수신할 때 해당 메시지는 해당 개체에서 제거되지 않습니다. 따라서 여러 대상이 하나의 메시지 복사본을 수신합니다.  `single_assignment` 클래스는 여러 구성 요소를 하나의 메시지를 브로드캐스트 하려고 할 경우 유용 합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 작업 방법의 기본 구조는 `single_assignment` 클래스입니다. 이 예제에서는 세 가지 값을 보냅니다는 `single_assignment` 개체를 다음 동일한 개체에서 현재 값을 세 번 읽습니다. 이 예제는에 대 한 예제와 비슷한는 `overwrite_buffer` 클래스입니다. 하지만 둘 다는 `overwrite_buffer` 및 `single_assignment` 클래스는 단일 메시지를 저장할는 `single_assignment` 클래스에 한 번만 쓸 수 있습니다.  
  
 [!code-cpp[concrt-single_assignment-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_3.cpp)]  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```Output  
333333  
```  
  
 사용 하는 방법을 보여 주는 전체 예제는 `single_assignment` 클래스를 참조 하십시오 [연습: 미래 구현](../../parallel/concrt/walkthrough-implementing-futures.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-namecalla-call-class"></a><a name="call"></a> call 클래스  
  [concurrency:: call](../../parallel/concrt/reference/call-class.md) 클래스의 데이터를 받을 경우 작업 함수에서 수행 하는 메시지 받는 사람 역할입니다. 이 작업 함수는 람다 식, 함수 개체 또는 함수 포인터를 수 있습니다. A `call` 개체에 메시지를 보내는 다른 구성 요소를 병렬로 동작 하므로 일반적인 함수 호출과 다르게 동작 합니다. 경우에 `call` 개체는 메시지를 받을 때 작업을 수행 중이지, 해당 메시지를 큐에 추가 합니다. 모든 `call` 대기 중인 메시지는 수신 된 순서 개체 처리 합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 작업 방법의 기본 구조는 `call` 클래스입니다. 이 예제에서는 한 `call` 콘솔에는 수신 하는 각 값을 출력 하는 개체입니다. 예제에서는 다음 세 가지 값을 전달 하는 `call` 개체입니다. 때문에 `call` 별도 스레드에서 메시지를 처리 하는 개체, 또한이 예제에서는 카운터 변수 및 [이벤트](../../parallel/concrt/reference/event-class.md) 되도록 개체는 `call` 하기 전에 모든 메시지를 처리 하는 개체는 `wmain` 함수에서 반환 합니다.  
  
 [!code-cpp[concrt-call-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_4.cpp)]  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```Output  
334455  
```  
  
 사용 하는 방법을 보여 주는 전체 예제는 `call` 클래스를 참조 하십시오 [하는 방법: call 및 transformer 클래스에 작업 함수 제공](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-nametransformera-transformer-class"></a><a name="transformer"></a> transformer 클래스  
  [concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) 클래스 역할을 모두 메시지 받는 사람 및 메시지 보낸 사람으로 합니다.  `transformer` 클래스와 유사는 `call` 클래스에 있으므로 데이터를 받을 때에 사용자 정의 작업 기능을 수행 합니다. 그러나는 `transformer` 클래스 수신기 개체에도 작업 함수의 결과 보냅니다. 마찬가지로 `call` 개체는 `transformer` 개체는 메시지를 보내는 다른 구성 요소를 병렬로 역할입니다. 경우에 `transformer` 개체는 메시지를 받을 때 작업을 수행 중이지, 해당 메시지를 큐에 추가 합니다. 모든 `transformer` 는 수신 된 순서 대로 해당 큐에 대기 중인된 메시지를 처리 하는 개체입니다.  
  
  `transformer` 클래스를 하나의 대상에는 메시지를 보냅니다. 설정 하는 경우는 `_PTarget` 매개 변수를 생성자에서 `NULL`, 대상을 호출 하 여 나중에 지정할 수 있습니다는 [concurrency::link_target](../Topic/source_block::link_target%20Method.md) 메서드.  
  
 에이전트 라이브러리에서 제공 되는 다른 모든 비동기 메시지 블록 형식과 달리는 `transformer` 클래스는 서로 다른 입력 및 출력 형식에서 작동할 수 있습니다. 이 기능은 다른가를 한 형식에서 데이터를 변환 하는 `transformer` 많은 동시 네트워크에서 핵심 구성 요소 클래스입니다. 작업 함수에서 더 세분화 된 병렬 기능을 추가할 수는 또한는 `transformer` 개체입니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 작업 방법의 기본 구조는 `transformer` 클래스입니다. 이 예제에서는 한 `transformer` 배수는 각 입력을 하는 개체 `int` 값을 생성 하기 위해 0.33으로는 `double` 값을 출력으로 합니다. 그런 다음 메시지를 받고 변환 된 값과 동일한 `transformer` 개체는 콘솔에 출력 합니다.  
  
 [!code-cpp[concrt-transformer-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_5.cpp)]  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```Output  
10.8914.5218.15  
```  
  
 사용 하는 방법을 보여 주는 전체 예제는 `transformer` 클래스를 참조 하십시오 [하는 방법: 데이터 파이프라인에서 transformer 사용](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-namechoicea-choice-class"></a><a name="choice"></a> choice 클래스  
  [concurrency:: choice](../../parallel/concrt/reference/choice-class.md) 클래스 소스 집합에서 가능한 첫 번째 메시지를 선택 합니다.  `choice` 클래스는 데이터 흐름 메커니즘 대신 흐름 제어 메커니즘을 나타냅니다 (항목 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 데이터 흐름 및 제어 흐름 사이의 차이점을 설명).  
  
 Windows API 함수를 호출 하는 선택한 개체에서 읽는 유사한 `WaitForMultipleObjects` 했을 때의 `bWaitAll` 매개 변수 설정 `FALSE`합니다. 그러나는 `choice` 클래스에는 대신 이벤트 자체는 외부 동기화 개체를 데이터 바인딩합니다.  
  
 일반적으로 사용 된 `choice` 와 함께 클래스는 [concurrency:: receive](../Topic/receive%20Function.md) 응용 프로그램에서 제어 흐름을 구동 하는 함수입니다. 사용 된 `choice` 다른 형식을 포함 하는 메시지 버퍼에서 선택 해야 할 때 클래스입니다. 사용 된 `single_assignment` 동일한 유형을 가진 메시지 버퍼에서 선택 해야 할 때 클래스입니다.  
  
 소스를 연결 하는 순서는 `choice` 개체는 선택 되어 있는 메시지를 결정할 수 없기 때문에 중요 합니다. 예를 들어 메시지를 이미 포함 되어 있는 여러 메시지 버퍼 연결 하는 경우는 `choice` 개체입니다.  `choice` 개체에 연결 된 첫 번째 소스에서 메시지를 선택 합니다. 모든 원본에 연결한 후는 `choice` 개체는 각 원본 메시지를 수신 하는 순서를 유지 합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 작업 방법의 기본 구조는 `choice` 클래스입니다. 사용 하 여이 예제는 [concurrency::make_choice](../Topic/make_choice%20Function.md) 만드는 함수를 한 `choice` 세 개의 메시지 블록 중 하나를 선택 하는 개체입니다. 그런 다음 다양 한 지연 된 피보나치 수를 계산 하 고 다른 메시지 블록의 각 결과 저장 합니다. 이 예제에서는 다음 출력 콘솔 먼저 완료 한 작업을 기반으로 하는 메시지입니다.  
  
 [!code-cpp[concrt-choice-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_6.cpp)]  
  
 이 예제에서는 다음 샘플 출력을 생성합니다.  
  
```Output  
fib35 received its value first. Result = 9227465  
```  
  
 때문에 35를 계산 하는 작업<sup>th</sup> 먼저 완료 피보나치 수 보장이 없습니다,이 예제의 출력은 다를 수 있습니다.  
  
 사용 하 여이 예제는 [concurrency:: parallel_invoke](../Topic/parallel_invoke%20Function.md) 알고리즘을 병렬에서 피보나치 수를 계산 합니다. 에 대 한 자세한 내용은 `parallel_invoke`, 참조 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.  
  
 사용 하는 방법을 보여 주는 전체 예제는 `choice` 클래스를 참조 하십시오 [하는 방법: 완료 된 작업 간 선택](../../parallel/concrt/how-to-select-among-completed-tasks.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-namejoina-join-and-multitypejoin-classes"></a><a name="join"></a> 조인 및 multitype_join 클래스  
  [concurrency:: join](../../parallel/concrt/reference/join-class.md) 및 [concurrency::multitype_join](../../parallel/concrt/reference/multitype-join-class.md) 클래스는 메시지를 받을 소스 집합의 각 멤버에 대 한 대기 수 있습니다.  `join` 일반적인 메시지 형식이 있는 소스 개체에서 클래스 동작 합니다.  `multitype_join` 다양 한 메시지 형식을 가질 수 있는 소스 개체에서 클래스 동작 합니다.  
  
 읽기는 `join` 또는 `multitype_join` 개체 유사한 Windows API 함수를 호출 `WaitForMultipleObjects` 했을 때의 `bWaitAll` 매개 변수 설정 `TRUE`합니다. 그러나 마찬가지로 `choice` 개체를 `join` 및 `multitype_join` 개체는 대신 이벤트 자체는 외부 동기화 개체를 데이터에 바인딩하는 이벤트 메커니즘을 사용 합니다.  
  
 읽기는 `join` 개체가 생성 하는 std::[벡터](../../standard-library/vector-class.md) 개체입니다. 읽기는 `multitype_join` 개체가 생성 하는 std::[튜플](../../standard-library/tuple-class.md) 개체입니다. 해당 소스 버퍼에 연결 되어 않으므로 동일한 순서로 이러한 개체에 표시 되는 요소는 `join` 또는 `multitype_join` 개체입니다. 소스를 연결 하는 순서를 버퍼링 하기 때문에 `join` 또는 `multitype_join` 개체 결과에서 요소의 순서와 연결 된 `vector` 또는 `tuple` 개체를 조인에서 기존 소스 버퍼를 끊지 않는 것이 좋습니다. 이렇게 지정 되지 않은 동작이 발생할 수 있습니다.  
  
### <a name="greedy-versus-non-greedy-joins"></a>Greedy 및 Non-greedy 조인  
  `join` 및 `multitype_join` 클래스 식별 합니다 greedy 조인의 개념을 지원 합니다. A *greedy 조인* 메시지가 모든 메시지를 사용할 때까지 사용할 수 있을 때 각 소스에서 메시지를 수락 합니다. A *non-greedy 조인* 두 단계로 메시지를 수신 합니다. 첫째, non-greedy 조인 메시지 각 소스에서 제공 될 때까지 대기 합니다. 둘째, 모든 소스 메시지를 사용할 수 있는 후 non-greedy 조인 각 메시지를 예약 하려고 합니다. 각 메시지를 예약할 수 있는 모든 메시지를 사용 하 고 대상에 전파 합니다. 그렇지 않은 경우 릴리스, 또는 메시지 예약을 취소 하 고 다시 각 원본 메시지를 받을 때까지 대기 합니다.  
  
 Greedy 조인 메시지를 즉시 수락 하기 때문에 non-greedy 조인 보다 더 잘 수행 합니다. 그러나 드문 경우 지만 greedy 조인 하면 교착 상태가 발생할 수 있습니다. Non-greedy 조인을 사용 하 여 하나 이상의 공유 소스 개체를 포함 하는 여러 조인이 있는 경우.  
  
### <a name="example"></a>예제  
 다음 예제에서는 작업 방법의 기본 구조는 `join` 클래스입니다. 사용 하 여이 예제는 [concurrency::make_join](../Topic/make_join%20Function.md) 함수를 만드는 `join` 3에서 수신 하는 개체 `single_assignment` 개체입니다. 이 예제에서는 여러 피보나치 수 계산, 각 결과 다른 저장 `single_assignment` 개체를 각 콘솔에 출력 한 다음 결과 집합이 결과 하는 `join` 개체에 포함 합니다. 이 예제는에 대 한 예제와 비슷한는 `choice` 점을 제외 하 고 클래스는 `join` 클래스 모든 소스 메시지 블록이 메시지를 받을 때까지 대기 합니다.  
  
 [!code-cpp[concrt-join-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_7.cpp)]  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```Output  
fib35 = 9227465fib37 = 24157817half_of_fib42 = 1.33957e+008  
```  
  
 사용 하 여이 예제는 [concurrency:: parallel_invoke](../Topic/parallel_invoke%20Function.md) 알고리즘을 병렬에서 피보나치 수를 계산 합니다. 에 대 한 자세한 내용은 `parallel_invoke`, 참조 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.  
  
 사용 하는 방법을 보여 주는 전체 예제는 `join` 클래스를 참조 하십시오 [하는 방법: 완료 된 작업 간 선택](../../parallel/concrt/how-to-select-among-completed-tasks.md) 및 [연습: 교착 상태 방지에 대 한 조인을 사용 하 여](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-nametimera-timer-class"></a><a name="timer"></a> timer 클래스  
 동시성::[timer 클래스](../../parallel/concrt/reference/timer-class.md) 메시지 소스 역할을 합니다. A `timer` 시간이 경과한 후 개체는 대상에 메시지를 보냅니다.  `timer` 클래스는 메시지를 보내는 연기 해야 하거나 일정 한 간격으로 메시지를 전송 하려는 경우 유용 합니다.  
  
  `timer` 클래스는 하나의 대상에는 메시지를 보냅니다. 설정 하는 경우는 `_PTarget` 매개 변수를 생성자에서 `NULL`, 대상을 호출 하 여 나중에 지정할 수 있습니다는 [concurrency::ISource::link_target](../Topic/source_block::link_target%20Method.md) 메서드.  
  
 A `timer` 개체를 반복 하거나 반복 되지 않는 수 있습니다. 반복 되는 타이머를 만들려면 전달 `true` 에 대 한는 `_Repeating` 매개 변수는 생성자를 호출 합니다. 그렇지 않은 경우, 전달 `false` 에 대 한는 `_Repeating` 매개 변수를 반복 되지 않는 타이머를 만듭니다. 반복 되는 타이머 보냅니다 같은 오류 메시지가 대상에 각 간격.  
  
 에이전트 라이브러리에서는 `timer` 시작 되지 않은 상태의 개체입니다. 타이머 개체를 시작 하려면 호출의 [concurrency::timer::start](../Topic/timer::start%20Method.md) 메서드. 중지 하는 `timer` 개체, 개체 또는 호출 삭제는 [concurrency::timer::stop](../Topic/timer::stop%20Method.md) 메서드. 반복 되는 타이머를 일시 중지 하려면 호출의 [concurrency::timer::pause](../Topic/timer::pause%20Method.md) 메서드.  
  
### <a name="example"></a>예제  
 다음 예제에서는 작업 방법의 기본 구조는 `timer` 클래스입니다. 이 예제에서는 사용 `timer` 및 `call` 긴 작업의 진행률을 보고할 개체입니다.  
  
 [!code-cpp[concrt-timer-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_8.cpp)]  
  
 이 예제에서는 다음 샘플 출력을 생성합니다.  
  
```Output  
Computing fib(42)..................................................result is 267914296  
```  
  
 사용 하는 방법을 보여 주는 전체 예제는 `timer` 클래스를 참조 하십시오 [하는 방법: 정기적으로 메시지 보내기](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-namefilteringa-message-filtering"></a><a name="filtering"></a> 메시지 필터링  
 메시지 블록 개체를 만들 때 제공할 수 있습니다는 *filter 함수* 결정 하는 메시지 블록에서 수락 여부는 메시지를 거부 합니다. 필터 함수 메시지 블록에 특정 값만 받도록 보장 하는 유용한 방법입니다.  
  
 다음 예제에서는 만드는 방법을 보여 줍니다.는 `unbounded_buffer` 짝수만 허용 하는 필터 함수를 사용 하는 개체입니다.  `unbounded_buffer` 개체 홀수 번호를 거부 하 고 음수는 대상 블록에 전파 하지 않습니다.  
  
 [!code-cpp[concrt-filter-function#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_9.cpp)]  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```Output  
0 2 4 6 8  
```  
  
 Filter 함수는 람다 함수, 함수 포인터 또는 함수 개체를 수 있습니다. 모든 필터 함수는 다음 형식 중 하나를 사용 합니다.  
  
```Output  
bool (T)  
bool (T const &)  
```  
  
 불필요 한 복사 하는 데이터를 제거 하려면 집계 값으로 전파 되는 형식이 있을 경우 두 번째 형태를 사용 합니다.  
  
 메시지 필터링 지원은 *데이터 흐름* 프로그래밍 모델을 수행 하는 구성 요소 계산 데이터를 받을 때입니다. 필터 함수를 사용 하 여 메시지 전달 네트워크에 있는 데이터의 흐름을 제어 하는 예제를 보려면 [하는 방법: 메시지 블록 필터를 사용 하 여](../../parallel/concrt/how-to-use-a-message-block-filter.md), [연습: 데이터 흐름 에이전트 만들기](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md), 및 [연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-namereservationa-message-reservation"></a><a name="reservation"></a> 메시지 예약  
 *메시지 예약* 메시지 블록이 나중에 사용할 메시지를 예약 하는 수 있습니다. 일반적으로 메시지 예약 직접 사용 되지 않습니다. 그러나 이해 메시지 예약 데 도움이 됩니다 일부 미리 정의 된 메시지 블록 형식의 동작을 이해 합니다.  
  
 식별 및 greedy 조인을 것이 좋습니다. 이러한 두 메시지 예약을 사용 나중에 사용할 메시지를 사용 합니다. 설명자 앞서 non-greedy 조인 메시지를 받는 두 단계로 합니다. 첫 번째 단계, non-greedy `join` 개체는 각 메시지를 받을 소스 기다립니다. Non-greedy 조인 각 메시지를 예약 하려고 합니다. 각 메시지를 예약할 수 있는 모든 메시지를 사용 하 고 대상에 전파 합니다. 그렇지 않은 경우 릴리스, 또는 메시지 예약을 취소 하 고 다시 각 원본 메시지를 받을 때까지 대기 합니다.  
  
 Greedy 조인 또한 여러 소스에서에서 입력된 메시지를 읽고, 메시지를 받는 각 소스에서 대기 하는 동안 추가 메시지를 읽으려면 메시지 예약을 사용 합니다. 예를 들어 메시지 블록에서 메시지를 받는 greedy 조인 `A` 및 `B`합니다. Greedy 조인 B에서 두 개의 메시지를 수신 하지만 아직에서 메시지를 받지 못한 경우 `A`, greedy 조인에서 두 번째 메시지에 대 한 고유한 메시지 식별자를 저장 `B`합니다. Greedy 조인에서 메시지를 받은 후 `A` 전파 하 고 이러한 메시지를 사용 하 여 저장된 된 메시지 식별자에서 두 번째 메시지를 `B` 계속 사용할 수 있습니다.  
  
 사용자 고유의 사용자 지정 메시지 블록 형식을 구현 하는 경우 메시지 예약을 사용할 수 있습니다. 사용자 지정 메시지 블록 형식을 만드는 방법에 대 한 예제를 참조 하십시오. [연습: 사용자 지정 메시지 블록 만들기](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md)합니다.  
  
 [[맨 위로 이동](#top)]  
  
## <a name="see-also"></a>참고 항목  
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)

