---
title: 메시지 전달 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9eecb7d2a45079ff14740167a192eafaab268150
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="message-passing-functions"></a>메시지 전달 함수
비동기 에이전트 라이브러리 구성 요소 간에 메시지를 전달할 수 있는 여러 함수를 제공 합니다.  
  
 이러한 메시지 전달 함수는 다양 한 메시지 블록 형식으로 사용 됩니다. 동시성 런타임에 의해 정의 된 메시지 블록 형식에 대 한 자세한 내용은 참조 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)합니다.  
  
##  <a name="top"></a> 섹션  
 이 항목에서는 다음과 같은 메시지 전달 함수를 설명합니다.  
  
-   [send 및 asend](#send)  
  
-   [수신 및 try_receive](#receive)  
  
-   [예제](#examples)  
  
##  <a name="send"></a> send 및 asend  

 [concurrency:: send](reference/concurrency-namespace-functions.md#send) 함수 지정된 된 대상에 동기적으로 메시지를 보냅니다 및 [concurrency:: asend](reference/concurrency-namespace-functions.md#asend) 함수 지정된 된 대상에 비동기적으로 메시지를 보냅니다. 둘 다는 `send` 및 `asend` 함수는 것은 결국 수락 또는 거부 메시지 대상 나타냅니다 될 때까지 기다립니다.  
  
 `send` 함수 대상을 수락 하거나 반환 하기 전에 메시지를 거부 될 때까지 대기 합니다. `send` 함수에서 반환 `true` 메시지가 배달 하는 경우 및 `false` 그렇지 않은 경우. 때문에 `send` 함수를 동기적으로 작동 하는 `send` 함수를 반환 하기 전에 메시지를 받는 대상을 때까지 대기 합니다.  
  
 반대로,는 `asend` 함수를 허용 하거나 반환 하기 전에 메시지를 거부할 대상 기다리지 않습니다. 대신,는 `asend` 함수에서 반환 `true` 대상 메시지를 수락 하 고 최종적 합니다. 그렇지 않으면 `asend` 반환 `false` 되었음을 나타내려면 대상 중 하나에서 메시지를 거부 메시지를 받을지 여부에 대 한 결정을 연기 합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="receive"></a> 수신 및 try_receive  

 [concurrency:: receive](reference/concurrency-namespace-functions.md#receive) 및 [concurrency:: try_receive](reference/concurrency-namespace-functions.md#try_receive) 함수는 지정 된 소스에서 데이터를 읽습니다. `receive` 함수에 데이터를 사용할 수 있을 때까지 대기 반면는 `try_receive` 함수는 즉시 반환 합니다.  
  
 사용 된 `receive` 데이터를 계속 해야 합니다. 경우에 작동 합니다. 사용 된 `try_receive` 함수는 현재 컨텍스트를 차단 해야 하거나 데이터를 계속 하려면 필요가 없습니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="examples"></a> 예제  
 사용 하는 예는 `send` 및 `asend`, 및 `receive` 함수는 다음 항목을 참조 합니다.  
  
-   [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [방법: 다양한 공급자-소비자 패턴 구현](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)  
  
-   [방법: call 및 transformer 클래스에 작업 함수 제공](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)  
  
-   [방법: 데이터 파이프라인에서 transformer 사용](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)  
  
-   [방법: 완료된 작업 간 선택](../../parallel/concrt/how-to-select-among-completed-tasks.md)  
  
-   [방법: 정기적으로 메시지 보내기](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)  
  
-   [방법: 메시지 블록 필터 사용](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
 [[맨 위로 이동](#top)]  
  
## <a name="see-also"></a>참고 항목  
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [send 함수](reference/concurrency-namespace-functions.md#send)   
 [asend 함수](reference/concurrency-namespace-functions.md#asend)   
 [receive 함수](reference/concurrency-namespace-functions.md#receive)   
 [try_receive 함수](reference/concurrency-namespace-functions.md#try_receive)


