---
title: '연습: 데이터 흐름 에이전트 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- creating dataflow agents [Concurrency Runtime]
- dataflow agents, creating [Concurrency Runtime]
ms.assetid: 9db5ce3f-c51b-4de1-b79b-9ac2a0cbd130
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33f7c7cf5e64d2ddf751bb97ee1b617d09df6af3
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="walkthrough-creating-a-dataflow-agent"></a>연습: 데이터 흐름 에이전트 만들기
이 문서에서는 제어 흐름의 데이터 흐름을 기반으로 하는 에이전트 기반 응용 프로그램을 만드는 방법을 보여 줍니다.  
  
 *제어 흐름* 프로그램에서 작업의 실행 순서를 가리킵니다. 조건문, 루프 등과 같은 제어 구조를 사용 하 여 제어 흐름을 조정할 됩니다. 또는 *데이터 흐름* 는 계산이 필요한 모든 데이터 사용할 수 있는 경우에 수행 되는 프로그래밍 모델을 가리킵니다. 데이터 흐름 프로그래밍 모델에 있는 프로그램의 개별 구성 요소가 서로 통신할 메시지를 전송 하 여 메시지 전달의 개념 관련이 있습니다.  
  
 비동기 에이전트에는 제어 흐름 및 데이터 흐름 프로그래밍 모델 모두 지원 합니다. 제어 흐름 모델 적합 하지만 대부분의 경우에서 데이터 흐름 모델은 적합 한 경우도 예를 들어, 에이전트 데이터를 수신 하 고 해당 데이터의 페이로드를 기반으로 하는 동작을 수행 합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 시작 하기 전에 다음 문서를 읽어 보십시오.  
  
- [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)  
  
- [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)  
  
- [방법: 메시지 블록 필터 사용](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
##  <a name="top"></a> 섹션  
 이 연습에는 다음과 같은 섹션이 있습니다.  
  
- [기본 제어 흐름 에이전트 만들기](#control-flow)  
  
- [기본 데이터 흐름 에이전트 만들기](#dataflow)  
  
- [메시지 로깅 에이전트 만들기](#logging)  
  
##  <a name="control-flow"></a> 기본 제어 흐름 에이전트 만들기  
 예를 들어 다음을 정의 하는 `control_flow_agent` 클래스입니다. `control_flow_agent` 세 개의 메시지 버퍼에서 클래스 동작: 하나의 입력 버퍼와 출력 버퍼 두 개 있습니다. `run` 메서드는 루프에서 소스 메시지 버퍼에서 읽고 조건문 사용 하 여 프로그램 실행의 흐름. 에이전트 음수, 0이 아닌 값에 대 한 하나의 카운터를 증가 하 고, 0이 아닌 양수 값에 대 한 다른 카운터를 증가 합니다. 에이전트 센티널 값 0 받은 후 카운터 값에서 출력 메시지 버퍼에 보냅니다. `negatives` 및 `positives` 메서드를 사용 하면 응용 프로그램 에이전트에서 양수 및 음수 값의 개수를 읽을 수 있습니다.  
  
 [!code-cpp[concrt-dataflow-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_1.cpp)]  
  
 에이전트를 제어 흐름의 기본적인 사용 하는이 예제를 기반으로 흐름 제어 프로그래밍의 직렬 특성을 보여 줍니다. 여러 메시지 입력된 메시지 버퍼에서 사용할 수 있지만 각 메시지를 순차적으로 처리 되어야 합니다. 데이터 흐름 모델 두 분기를의 조건부 문 동시에 실행할 수 있습니다. 또한 데이터 흐름 모델을 사용 하면 데이터를 사용할 수 있도록 작업을 수행 하는 보다 복잡 한 메시징 네트워크를 만들 수 있습니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="dataflow"></a> 기본 데이터 흐름 에이전트 만들기  
 이 섹션에서는 변환 하는 방법을 보여 줍니다.는 `control_flow_agent` 동일한 작업을 수행 하려면 데이터 흐름 모델을 사용 하는 클래스입니다.  
  
 데이터 흐름 에이전트는 특정 용도로 사용 되는 메시지 버퍼의 네트워크를 만들어 작동 합니다. 특정 메시지 블록 필터 함수를 사용 하 여를 수락 하거나 페이로드를 기준으로 메시지를 거부 합니다. 필터 함수 메시지 블록에 특정 값만 수신 되는지 확인 합니다.  
  
#### <a name="to-convert-the-control-flow-agent-to-a-dataflow-agent"></a>데이터 흐름 에이전트에 제어 흐름 에이전트를 변환 하려면  
  
1.  본문 복사는 `control_flow_agent` 예를 들어 다른 클래스에는 클래스 `dataflow_agent`합니다. 또는 이름을 바꿀 수 있습니다는 `control_flow_agent` 클래스입니다.  
  
2.  호출 하는 루프의 본문을 제거 `receive` 에서 `run` 메서드.  
  
 [!code-cpp[concrt-dataflow-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_2.cpp)]  
  
3.  에 `run` 변수 초기화 후 메서드 `negative_count` 및 `positive_count`, 추가 `countdown_event` 활성 작업 수를 추적 하는 개체입니다.  
  
 [!code-cpp[concrt-dataflow-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_3.cpp)]  
  
     `countdown_event` 클래스는이 항목의 뒷부분에 나오는 나옵니다.  
  
4.  데이터 흐름 네트워크에서 메시지는 참여 하는 버퍼 개체를 만듭니다.  
  
 [!code-cpp[concrt-dataflow-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_4.cpp)]  
  
5.  메시지 버퍼를 네트워크를 연결 합니다.  
  
 [!code-cpp[concrt-dataflow-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_5.cpp)]  
  
6.  에 대 한 대기는 `event` 및 `countdown event` 개체를 설정할 수 있습니다. 에이전트에서 센티널 값을 받았음을 하 고 모든 작업이 완료 될 이러한 이벤트 신호입니다.  
  
 [!code-cpp[concrt-dataflow-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_6.cpp)]  
  
 다음 그림에에 대 한 전체 데이터 흐름 네트워크의 `dataflow_agent` 클래스:  
  
 ![데이터 흐름 네트워크](../../parallel/concrt/media/concrt_dataflow.png "concrt_dataflow")  
  
 다음 표에서는 네트워크의 멤버를 설명합니다.  
  
|멤버|설명|  
|------------|-----------------|  
|`increment_active`|A [concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) 활성 이벤트 카운터가 증가 하 고 네트워크의 나머지 부분에 입력된 값을 전달 하는 개체입니다.|  
|`negatives`, `positives`|[concurrency:: call](../../parallel/concrt/reference/call-class.md) 활성 이벤트 카운터의 숫자와 감소 횟수를 증가 하는 개체입니다. 이 개체는 각각 양수 또는 음수 값을 받아들이는 필터를 사용 합니다.|  
|`sentinel`|A [concurrency:: call](../../parallel/concrt/reference/call-class.md) 활성 이벤트 카운터 0이 되 고 감소의 센티널 값만 허용 하는 개체입니다.|  
|`connector`|A [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) 소스 메시지 버퍼의 내부 네트워크에 연결 하는 개체입니다.|  
  
 때문에 `run` 별도 스레드에서 메서드가 호출 되 면 다른 스레드가 메시지를 보낼 수는 네트워크의 네트워크가 완전히 연결 되기 전에 합니다. `_source` 데이터 멤버는 한 `unbounded_buffer` 에이전트에 응용 프로그램에서 전송 되는 모든 입력을 버퍼링 하는 개체입니다. 모든 입력된 메시지를 처리 하는 네트워크, 에이전트 먼저 네트워크의 내부 노드를 연결 하 한 다음 해당 네트워크의 시작 부분에 연결 되도록 하려면 `connector`을 `_source` 데이터 멤버입니다. 이 메시지 처리 되지 않습니다는 네트워크를 구성 하는 대로 보장 합니다.  
  
 이 예에서 네트워크 데이터 흐름을 기반으로 하므로 보다는 제어 흐름에 네트워크 통신 해야 에이전트에는 각 입력된 값을 처리 하지 못한 및 센티널 노드에서 해당 값을 받았음을 합니다. 사용 하 여이 예제는 `countdown_event` 신호를 보내 모든 입력된 값이 처리 된 개체와 [concurrency:: event](../../parallel/concrt/reference/event-class.md) 센티널 노드에서 해당 값을 받았음을 나타내기 위해 개체입니다. `countdown_event` 클래스에서 사용 하는 `event` 카운터 값을 0에 도달할 때 신호를 보내 개체입니다. 데이터 흐름 네트워크의 머리는 값을 받을 때마다 카운터를 증가 시킵니다. 모든 터미널 노드 네트워크 감소의 입력된 값 처리 된 후 카운터입니다. 설정 하려면 센티널 노드 기다리는 에이전트 폼 데이터 흐름 네트워크 후는 `event` 개체 및에 대 한는 `countdown_event` 개체를 해당 카운터 0에 도달 했습니다.  
  
 다음 예제와 `control_flow_agent`, `dataflow_agent`, 및 `countdown_event` 클래스입니다. `wmain` 함수를 만듭니다는 `control_flow_agent` 및 `dataflow_agent` 개체와 사용 하 여는 `send_values` 에이전트에는 일련의 임의 값을 보내는 함수입니다.  
  
 [!code-cpp[concrt-dataflow-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_7.cpp)]  
  
 이 예제는 다음과 같은 샘플 출력을 생성합니다.  
  
```Output  
Control-flow agent:  
There are 500523 negative numbers.  
There are 499477 positive numbers.  
Dataflow agent:  
There are 500523 negative numbers.  
There are 499477 positive numbers.  
```  
  
### <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `dataflow-agent.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc 데이터 흐름 agent.cpp**  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="logging"></a> 메시지 로깅 에이전트 만들기  
 다음 예제와 `log_agent` 클래스와 유사한는 `dataflow_agent` 클래스입니다. `log_agent` 쓰기 파일 및 콘솔에 메시지를 기록 하는 비동기 로깅 에이전트 클래스를 구현 합니다. `log_agent` 클래스를 사용 하면 메시지를 정보, 경고 또는 오류를 분류 하는 응용 프로그램입니다. 또한 응용 프로그램을 로그 범주별 파일, 콘솔, 또는 둘 다에 기록 되는지 여부를 지정할 수 있습니다. 이 예제에서는 콘솔에 모든 파일에 로그 메시지 및 오류 메시지만 씁니다.  
  
 [!code-cpp[concrt-log-filter#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_8.cpp)]  
  
 이 예제에서는 콘솔에는 다음과 같은 출력을 씁니다.  
  
```Output  
error: This is a sample error message.  
```  
  
 이 예제에는 다음 텍스트를 포함 하는 log.txt 파일을 생성 합니다.  
  
```Output  
info: ===Logging started.=== 
warning: This is a sample warning message.  
error: This is a sample error message.  
info: ===Logging finished.=== 
```  
  
### <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `log-filter.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc 로그 filter.cpp**  
  
 [[맨 위로 이동](#top)]  
  
## <a name="see-also"></a>참고 항목  
 [동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

