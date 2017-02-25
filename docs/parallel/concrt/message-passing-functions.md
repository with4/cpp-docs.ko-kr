---
title: "메시지 전달 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메시지 전달 함수"
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# 메시지 전달 함수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비동기 에이전트 라이브러리에서는 구성 요소 간에 메시지를 전달할 수 있는 몇 가지 함수를 제공합니다.  
  
 이러한 메시지 전달 함수는 다양한 메시지 블록 형식과 함께 사용됩니다.  동시성 런타임에 정의된 메시지 블록 형식에 대한 자세한 내용은 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)을 참조하십시오.  
  
##  <a name="top"></a> 단원  
 이 항목에서는 다음과 같은 메시지 전달 함수에 대해 설명합니다.  
  
-   [send 및 asend](#send)  
  
-   [receive 및 try\_receive](#receive)  
  
-   [예제](#examples)  
  
##  <a name="send"></a> send 및 asend  
 [concurrency::send](../Topic/send%20Function.md) 함수는 지정된 대상에 동기적으로 메시지를 보내고 [concurrency::asend](../Topic/asend%20Function.md) 함수는 지정된 대상에 비동기적으로 메시지를 보냅니다.  `send`와 `asend` 함수 둘 다 대상에서 메시지를 최종적으로 수락할지 아니면 거부할지를 나타낼 때까지 기다립니다.  
  
 `send` 함수는 대상에서 메시지를 수락하거나 거부할 때까지 기다린 후 반환합니다.  `send` 함수는 메시지가 배달되었으면 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.  `send` 함수는 동기적으로 동작합니다. 따라서 `send` 함수는 대상에서 메시지를 받을 때까지 기다린 후 반환합니다.  
  
 반대로 `asend` 함수는 대상에서 메시지를 수락하거나 거부할 때까지 기다리지 않고 반환합니다.  대신 `asend` 함수는 대상에서 메시지를 수락하고 최종적으로 배달될 예정이면 `true`를 반환합니다.  그렇지 않으면 `asend`에서는 `false`를 반환하여 대상에서 메시지를 거부했거나, 메시지를 받을지 여부에 대한 결정을 연기했음을 나타냅니다.  
  
 \[[맨 위](#top)\]  
  
##  <a name="receive"></a> receive 및 try\_receive  
 [concurrency::receive](../Topic/receive%20Function.md) 및 [concurrency::try\_receive](../Topic/try_receive%20Function.md) 함수는 지정된 소스에서 데이터를 읽습니다.  `receive` 함수는 데이터를 사용할 수 있을 때까지 기다리지만 `try_receive` 함수는 즉시 반환합니다.  
  
 데이터가 있어야 계속할 수 있는 경우 `receive` 함수를 사용합니다.  현재 컨텍스트를 차단해야 하거나, 데이터가 없어도 계속할 수 있는 경우에는 `try_receive` 함수를 사용합니다.  
  
 \[[맨 위](#top)\]  
  
##  <a name="examples"></a> 예제  
 `send`, `asend` 및 `receive` 함수를 사용하는 예제를 보려면 다음 항목을 참조하십시오.  
  
-   [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [방법: 다양한 공급자\/소비자 패턴 구현](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)  
  
-   [방법: call 및 transformer 클래스에 작업 함수 제공](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)  
  
-   [방법: 데이터 파이프라인에서 transformer 사용](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)  
  
-   [방법: 완료된 작업 중에서 선택](../../parallel/concrt/how-to-select-among-completed-tasks.md)  
  
-   [방법: 정기적으로 메시지 보내기](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)  
  
-   [방법: 메시지 블록 필터 사용](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
 \[[맨 위](#top)\]  
  
## 참고 항목  
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [send 함수](../Topic/send%20Function.md)   
 [asend 함수](../Topic/asend%20Function.md)   
 [receive 함수](../Topic/receive%20Function.md)   
 [try\_receive 함수](../Topic/try_receive%20Function.md)