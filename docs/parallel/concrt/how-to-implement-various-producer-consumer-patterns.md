---
title: "방법: 다양한 공급자/소비자 패턴 구현 | Microsoft Docs"
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
  - "공급자/소비자 패턴, 구현[동시성 런타임]"
  - "공급자/소비자 패턴 구현[동시성 런타임]"
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# 방법: 다양한 공급자/소비자 패턴 구현
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 응용 프로그램에서 공급자\/소비자 패턴을 구현하는 방법에 대해 설명합니다.  이 패턴에서 *공급자*는 메시지 블록에 메시지를 보내고 *소비자*는 해당 블록에서 메시지를 읽습니다.  
  
 이 항목에서는 두 가지 시나리오를 보여 줍니다.  첫 번째 시나리오에서 소비자는 공급자가 보내는 각 메시지를 받아야 합니다.  두 번째 시나리오에서 소비자는 주기적으로 데이터를 폴링하므로 각 메시지를 받을 필요가 없습니다.  
  
 이 항목에 나오는 두 예제에서는 모두 에이전트, 메시지 블록 및 메시지 전달 함수를 사용하여 공급자가 소비자에게 메시지를 전송합니다.  공급자 에이전트는 [concurrency::asend](../Topic/send%20Function.md) 함수를 사용하여 [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) 개체에 메시지를 작성하고,  소비자 에이전트는 [concurrency::receive](../Topic/receive%20Function.md) 함수를 사용하여 [concurrency::ISource](../../parallel/concrt/reference/isource-class.md) 개체에서 메시지를 읽습니다.  두 에이전트 모두 처리의 끝을 조정하는 데 사용할 센티널 값을 포함합니다.  
  
 비동기 에이전트에 대한 자세한 내용은 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)를 참조하십시오.  메시지 블록 및 메시지 전달 함수에 대한 자세한 내용은 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md) 및 [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)를 참조하십시오.  
  
## 예제  
 이 예제에서 공급자 에이전트는 일련의 숫자를 소비자 에이전트에게 보냅니다.  소비자는 이러한 각 숫자를 받아 평균 값을 계산합니다.  그러면 응용 프로그램에서 평균 값을 콘솔에 씁니다.  
  
 이 예제에서는 [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md) 개체를 사용하여 공급자가 메시지를 큐에 넣을 수 있도록 합니다.  `unbounded_buffer` 클래스는 `ITarget` 및 `ISource`를 구현하여 공급자와 소비자가 공유 버퍼에 메시지를 보내거나 공유 버퍼에서 메시지를 받을 수 있도록 합니다.  `send` 및 `receive` 함수는 공급자에서 소비자로 데이터를 전파하는 작업을 조정합니다.  
  
 [!code-cpp[concrt-producer-consumer-average#1](../../parallel/concrt/codesnippet/CPP/how-to-implement-various-producer-consumer-patterns_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **평균은 50입니다.**   
## 예제  
 이 예제에서 공급자 에이전트는 일련의 주식 시세를 소비자 에이전트에게 보냅니다.  소비자 에이전트는 현재 시세를 주기적으로 읽고 콘솔에 출력합니다.  
  
 이 예제는 이전 예제와 유사하지만 [concurrency::overwrite\_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) 개체를 사용하여 공급자가 하나의 메시지를 소비자와 공유할 수 있도록 한다는 점이 다릅니다.  이전 예제와 같이 `overwrite_buffer` 클래스는 `ITarget` 및 `ISource`를 구현하여 공급자와 소비자가 공유 메시지 버퍼에서 동작할 수 있도록 합니다.  
  
 [!code-cpp[concrt-producer-consumer-quotes#1](../../parallel/concrt/codesnippet/CPP/how-to-implement-various-producer-consumer-patterns_2.cpp)]  
  
 이 예제를 실행하면 다음과 같은 샘플 결과가 출력됩니다.  
  
  **현재 시세는 24.44입니다.**  
**현재 시세는 24.44입니다.**  
**현재 시세는 24.65입니다.**  
**현재 시세는 24.99입니다.**  
**현재 시세는 24.44입니다.**  
**현재 시세는 24.44입니다.**  
**현재 시세는 24.44입니다.** `unbounded_buffer` 개체와 달리 `receive` 함수는 `overwrite_buffer` 개체에서 메시지를 제거하지 않습니다.  공급자가 메시지를 덮어쓰기 전에 소비자가 해당 메시지 버퍼를 두 번 이상 읽으면 수신자는 매번 같은 메시지를 가져옵니다.  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `producer-consumer.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc producer\-consumer.cpp**  
  
## 참고 항목  
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)