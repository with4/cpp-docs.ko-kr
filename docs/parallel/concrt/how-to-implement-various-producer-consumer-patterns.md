---
title: '방법: 다양 한 공급자 / 소비자 패턴 구현 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- producer-consumer patterns, implementing [Concurrency Runtime]
- implementing producer-consumer patterns [Concurrency Runtime]
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50a6683db37fb6e994c1957a8df3ab6469acff6d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-implement-various-producer-consumer-patterns"></a>방법: 다양한 공급자/소비자 패턴 구현
이 항목에서는 응용 프로그램에서 공급자-소비자 패턴을 구현 하는 방법을 설명 합니다. 이 패턴에서 *생산자*는 메시지 블록에 메시지를 보내고 *소비자*는 해당 블록에서 메시지를 읽습니다.  
  
 이 항목에서는 두 가지 시나리오를 보여 줍니다. 첫 번째 시나리오에서는 소비자는 공급자가 보내는 각 메시지를 받아야 합니다. 두 번째 시나리오에서는 소비자 데이터를 주기적으로 폴링한다 하 고 따라서 각 메시지를 받이 필요가 없습니다.  
  
 이 항목의 두 예제 공급자는 소비자에 게 메시지를 전송 하는 데 에이전트, 메시지 블록 및 메시지 전달 함수를 사용 합니다. 공급자 에이전트를 사용 하는 [concurrency:: send](reference/concurrency-namespace-functions.md#send) 메시지를 작성 하는 함수는 [concurrency:: itarget](../../parallel/concrt/reference/itarget-class.md) 개체입니다. 소비자 에이전트가 사용 하는 [concurrency:: receive](reference/concurrency-namespace-functions.md#receive) 메시지를 읽을 함수는 [concurrency:: isource](../../parallel/concrt/reference/isource-class.md) 개체입니다. 에이전트를 모두 처리의 끝에 맞게 센티널 값을 보유 합니다.  
  
 비동기 에이전트에 대 한 자세한 내용은 참조 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)합니다. 메시지 블록 및 메시지 전달 함수에 대 한 자세한 내용은 참조 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md) 및 [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 공급자 에이전트를 소비자 에이전트 일련의 숫자를 보냅니다. 소비자는 이러한 각 숫자 받아의 평균을 계산 합니다. 응용 프로그램의 평균을 콘솔에 씁니다.  
  
 사용 하 여이 예제는 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) 개체를 사용 하 여 공급자 메시지를 큐에 있습니다. `unbounded_buffer` 클래스 구현 `ITarget` 및 `ISource` 생산자와 소비자 보내고 공유 버퍼에서 메시지를 받을 수 있도록 합니다. `send` 및 `receive` 함수 소비자에 게 데이터 생산자를 전파 하는 작업을 조정 합니다.  
  
 [!code-cpp[concrt-producer-consumer-average#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
```Output  
The average is 50.  
```  
  
## <a name="example"></a>예제  
 이 예제에서는 공급자 에이전트를 소비자 에이전트 일련의 주식 시세를 보냅니다. 소비자 에이전트인 현재 견적 주기적으로 읽고를 콘솔에 출력 합니다.  
  
 이 예제에서는 이전 예제와 유사를 사용 하는 [concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) 개체를 사용 하 여 공급자 하나의 메시지 소비자와 공유할 수 있습니다. 앞의 예와 `overwrite_buffer` 클래스 구현 `ITarget` 및 `ISource` 생산자와 소비자는 공유 메시지 버퍼에서 작동할 수 있도록 합니다.  
  
 [!code-cpp[concrt-producer-consumer-quotes#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_2.cpp)]  
  
 이 예제는 다음과 같은 샘플 출력을 생성합니다.  
  
```Output  
Current quote is 24.44.  
Current quote is 24.44.  
Current quote is 24.65.  
Current quote is 24.99.  
Current quote is 23.76.  
Current quote is 22.30.  
Current quote is 25.89.  
```  
  
 와 달리와 `unbounded_buffer` 개체는 `receive` 함수에서 메시지를 제거 하지 않습니다는 `overwrite_buffer` 개체입니다. 소비자가 한 번 이상 생산자 해당 메시지를 덮어쓰기 전에 메시지 버퍼에서 읽는, 수신기 될 때마다 동일한 메시지를 가져옵니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `producer-consumer.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc 생산자-consumer.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)
