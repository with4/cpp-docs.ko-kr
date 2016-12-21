---
title: "방법: 초과 구독을 사용하여 대기 오프셋 | Microsoft Docs"
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
  - "초과 구독, 사용[동시성 런타임]"
  - "초과 구독 사용[동시성 런타임]"
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
caps.latest.revision: 17
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 초과 구독을 사용하여 대기 오프셋
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

초과 구독은 대기 시간이 많은 작업을 포함하는 일부 응용 프로그램의 전반적인 효율성을 향상시킬 수 있습니다.  이 항목에서는 초과 구독을 사용하여 네트워크 연결에서 데이터 읽기를 통해 발생한 대기 시간을 오프셋하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)를 사용하여 HTTP 서버의 파일을 다운로드합니다.  `http_reader` 클래스는 [concurrency::agent](../../parallel/concrt/reference/agent-class.md)에서 파생되고, 메시지 전달을 사용하여 다운로드할 URL 이름을 비동기적으로 읽습니다.  
  
 `http_reader` 클래스는 [concurrency::task\_group](../Topic/task_group%20Class.md) 클래스를 사용하여 각 파일을 동시에 읽습니다.  각 작업에서는 `_BeginOversubscription` 매개 변수를 `true`로 설정한 상태로 [concurrency::Context::Oversubscribe](../Topic/Context::Oversubscribe%20Method.md) 메서드를 호출하여 현재 컨텍스트에서 초과 구독을 사용하도록 설정합니다.  그런 다음 MFC\(Microsoft Foundation Classes\) [CInternetSession](../../mfc/reference/cinternetsession-class.md) 및 [CHttpFile](../../mfc/reference/chttpfile-class.md) 클래스를 사용하여 파일을 다운로드합니다.  마지막으로 각 작업에서는 `_BeginOversubscription` 매개 변수를 `false`로 설정한 상태로 `Context::Oversubscribe`를 호출하여 초과 구독을 사용하지 않도록 설정합니다.  
  
 초과 구독을 사용하도록 설정하면 런타임에서는 작업을 실행하는 추가 스레드 하나를 만듭니다.  이러한 각 스레드에서 현재 컨텍스트를 초과 구독하여 추가 스레드를 만들 수도 있습니다.  `http_reader` 클래스는 [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md) 개체를 사용하여 응용 프로그램에서 사용하는 스레드의 수를 제한합니다.  에이전트는 고정된 수의 토큰 값을 사용하여 버퍼를 초기화합니다.  각 다운로드 작업을 수행할 때 에이전트는 작업이 시작되기 전에 버퍼에서 토큰 값을 읽은 다음, 작업이 끝난 후에 해당 값을 다시 버퍼에 씁니다.  버퍼가 비어 있는 경우 에이전트는 다운로드 작업 중 하나에서 값을 다시 버퍼에 쓸 때까지 기다립니다.  
  
 다음 예제에서는 동시 작업의 수를 두 번, 즉 사용 가능한 하드웨어 스레드의 수로 제한합니다.  초과 구독을 테스트할 때 이 값을 사용하여 시작하는 것이 좋습니다.  특정 처리 환경에 적합한 값을 사용하거나, 실제 작업 부하에 응답하도록 이 값을 동적으로 변경할 수 있습니다.  
  
 [!code-cpp[concrt-download-oversubscription#1](../../parallel/concrt/codesnippet/CPP/how-to-use-oversubscription-to-offset-latency_1.cpp)]  
  
 프로세서가 4개인 컴퓨터에 대해 이 예제를 실행하면 다음과 같은 결과가 출력됩니다.  
  
  **Http:\/\/www.adatum.com\/를 다운로드 하는 중...**  
**Http:\/\/www.adventure\-works.com\/를 다운로드 하는 중...**  
**Http:\/\/www.alpineskihouse.com\/를 다운로드 하는 중...**  
**Http:\/\/www.cpandl.com\/를 다운로드 하는 중...**  
**Http:\/\/www.cohovineyard.com\/를 다운로드 하는 중...**  
**Http:\/\/www.cohowinery.com\/를 다운로드 하는 중...**  
**Http:\/\/www.cohovineyardandwinery.com\/를 다운로드 하는 중...**  
**http:\/\/www.contoso.com\/...을 다운로드 하는 중...**  
**Http:\/\/www.consolidatedmessenger.com\/를 다운로드 하는 중...**  
**Http:\/\/www.fabrikam.com\/를 다운로드 하는 중...**  
**Http:\/\/www.fourthcoffee.com\/ 다운로드 중...**  
**Http:\/\/www.graphicdesigninstitute.com\/를 다운로드 하는 중...**  
**Http:\/\/www.humongousinsurance.com\/를 다운로드 하는 중...**  
**Http:\/\/www.litwareinc.com\/를 다운로드 하는 중...**  
**Http:\/\/www.lucernepublishing.com\/를 다운로드 하는 중...**  
**Http:\/\/www.margiestravel.com\/를 다운로드 하는 중...**  
**Http:\/\/www.northwindtraders.com\/를 다운로드 하는 중...**  
**Http:\/\/www.proseware.com\/를 다운로드 하는 중...**  
**Http:\/\/www.fineartschool.net를 다운로드 하는 중...**  
**Http:\/\/www.tailspintoys.com\/를 다운로드 하는 중...**  
**3276 ms에서 다운로드 한 1801040 바이트입니다.** 이 예제의 경우 초과 구독을 사용하도록 설정하면 다른 작업에서 숨은 작업이 끝날 때까지 기다리는 동안 추가 작업이 실행되므로 실행 속도가 더 빨라질 수 있습니다.  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `download-oversubscription.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령 중 하나를 실행합니다.  
  
 **cl.exe \/EHsc \/MD \/D "\_AFXDLL" download\-oversubscription.cpp**  
  
 **cl.exe \/EHsc \/MT download\-oversubscription.cpp**  
  
## 강력한 프로그래밍  
 초과 구독이 더 이상 필요하지 않게 되면 항상 사용하지 않도록 설정하십시오.  다른 함수에서 throw되는 예외를 처리하지 않는 함수를 가정해 봅니다.  함수가 반환되기 전에 초과 구독의 사용을 해제하지 않으면 추가 병렬 작업에서도 현재 컨텍스트를 초과 구독하게 됩니다.  
  
 *RAII\(Resource Acquisition Is Initialization\)* 패턴을 사용하면 초과 구독을 특정 범위로 제한할 수 있습니다.  RAII 패턴에서는 데이터 구조가 스택에 할당됩니다.  이러한 데이터 구조는 만들어질 때 리소스를 초기화하거나 획득하고, 소멸될 때 리소스를 소멸시키거나 해제합니다.  RAII 패턴을 사용하면 바깥쪽 범위를 벗어나기 전에 소멸자가 호출됩니다.  따라서 예외가 throw되거나 함수에 `return` 문이 여러 개 있는 경우 리소스가 올바르게 관리됩니다.  
  
 다음 예제에서는 `scoped_blocking_signal`이라는 구조체를 정의합니다.  `scoped_blocking_signal` 구조체의 생성자는 초과 구독 사용을 설정하고 소멸자는 초과 구독 사용을 해제합니다.  
  
 [!code-cpp[concrt-download-oversubscription#2](../../parallel/concrt/codesnippet/CPP/how-to-use-oversubscription-to-offset-latency_2.cpp)]  
  
 다음 예제에서는 RAII를 사용하여 함수가 반환되기 전에 초과 구독의 사용이 해제되도록 `download` 메서드 본문을 수정합니다.  이 방법을 사용하면 `download` 메서드에서 예외가 발생하지 않습니다.  
  
 [!code-cpp[concrt-download-oversubscription#3](../../parallel/concrt/codesnippet/CPP/how-to-use-oversubscription-to-offset-latency_3.cpp)]  
  
## 참고 항목  
 [컨텍스트](../../parallel/concrt/contexts.md)   
 [Context::Oversubscribe 메서드](../Topic/Context::Oversubscribe%20Method.md)