---
title: "방법: 초과 구독을 사용 하 여 대기 오프셋을 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- oversubscription, using [Concurrency Runtime]
- using oversubscription [Concurrency Runtime]
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e1a8f059abffd261de2002ed5d18067c48d74876
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-oversubscription-to-offset-latency"></a>방법: 초과 구독을 사용하여 대기 오프셋
초과 구독 대기 시간이 없는 작업을 포함 하는 일부 응용 프로그램의 전반적인 효율성을 향상 시킬 수 있습니다. 이 항목에는 네트워크 연결에서 데이터 읽기를 통해 발생 하는 대기 시간 오프셋을 초과 구독을 사용 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예  
 사용 하 여이 예제는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) HTTP 서버에서 파일을 다운로드 합니다. `http_reader` 클래스에서 파생 [concurrency:: agent](../../parallel/concrt/reference/agent-class.md) 및 사용 하 여 다운로드할 URL 이름을 비동기적으로 읽은를 전달 하는 메시지입니다.  
  
 `http_reader` 클래스에서 사용 하는 [concurrency:: task_group](reference/task-group-class.md) 클래스를 동시에 각 파일을 읽습니다. 각 태스크 호출는 [concurrency::Context::Oversubscribe](reference/context-class.md#oversubscribe) 메서드는 `_BeginOversubscription` 매개 변수 설정 `true` 초과 구독 현재 컨텍스트에서 사용할 수 있도록 합니다. 각 작업 (MFC (Microsoft Foundation Classes)에 다음 사용 하 여 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 및 [CHttpFile](../../mfc/reference/chttpfile-class.md) 클래스 파일을 다운로드 합니다. 마지막으로, 각 태스크 호출 `Context::Oversubscribe` 와 `_BeginOversubscription` 매개 변수 설정 `false` 초과 구독 사용 하지 않으려면입니다.  
  
 초과 구독을 사용 하면 런타임에서 작업을 실행 하려면 추가 스레드 하나를 만듭니다. 이러한 각 스레드는 현재 컨텍스트를 초과 구독할 수도 하 고 추가 스레드를 만들 수 있습니다. `http_reader` 클래스에서 사용 하는 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) 응용 프로그램이 사용 하는 스레드 수를 제한 하는 개체입니다. 에이전트에는 고정된 된 수의 토큰 값을 사용 하 여 버퍼를 초기화합니다. 각 다운로드 작업에 대 한 에이전트 작업을 시작 하 고 다음 해당 값에 쓰기 저장 버퍼 작업을 마친 후 전에 토큰 값을 버퍼에서 읽습니다. 버퍼가 비어 있으면 에이전트 버퍼에는 값을 쓰기 저장 하려면 다운로드 작업 중 하나에 대 한 대기 합니다.  
  
 다음 예제에서는 두 번 사용 가능한 하드웨어 스레드 수에 대 한 동시 작업 수를 제한합니다. 이 값은 초과 구독을 테스트할 때 사용할 수 있는 좋은 시작 지점입니다. 특정 처리 환경에 적합 한 값을 사용 하거나 동적으로 실제 작업 부하에 응답 하도록이 값을 변경할 수 있습니다.  
  
 [!code-cpp[concrt-download-oversubscription#1](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_1.cpp)]  
  
 이 예에서는 4 개의 프로세서가 있는 컴퓨터에는 다음과 같은 출력을 생성 합니다.  
  
```Output  
Downloading http://www.adatum.com/...  
Downloading http://www.adventure-works.com/...  
Downloading http://www.alpineskihouse.com/...  
Downloading http://www.cpandl.com/...  
Downloading http://www.cohovineyard.com/...  
Downloading http://www.cohowinery.com/...  
Downloading http://www.cohovineyardandwinery.com/...  
Downloading http://www.contoso.com/...  
Downloading http://www.consolidatedmessenger.com/...  
Downloading http://www.fabrikam.com/...  
Downloading http://www.fourthcoffee.com/...  
Downloading http://www.graphicdesigninstitute.com/...  
Downloading http://www.humongousinsurance.com/...  
Downloading http://www.litwareinc.com/...  
Downloading http://www.lucernepublishing.com/...  
Downloading http://www.margiestravel.com/...  
Downloading http://www.northwindtraders.com/...  
Downloading http://www.proseware.com/...  
Downloading http://www.fineartschool.net...  
Downloading http://www.tailspintoys.com/...  
Downloaded 1801040 bytes in 3276 ms.  
```  
  
 초과 구독을 다른 작업 latent 작업이 끝나기를 기다리는 동안 추가 작업을 실행 하기 때문에 사용할 예제에서는 더 빠르게 실행할 수 있습니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `download-oversubscription.cpp` 및 Visual Studio 명령 프롬프트 창에서 다음 중 하나를 실행된 명령을 합니다.  
  
 **cl.exe /EHsc /MD /D "_AFXDLL" download-oversubscription.cpp**  
  
 **cl.exe /EHsc /MT download-oversubscription.cpp**  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 더이상 해야하는 후에 항상 초과 구독 사용 하지 않도록 설정 합니다. 다른 함수에 의해 throw 되는 예외를 처리 하지 않는 함수를 살펴보세요. 초과 구독을 해제 하지 않으면 함수가 반환 되기 전에 추가 병렬 작업 현재 컨텍스트에 초과 구독도 됩니다.  
  
 사용할 수는 *Resource Acquisition Is Initialization* (RAII) 패턴을 지정된 된 범위를 초과 구독을 제한 합니다. RAII 패턴 데이터 구조는 스택에 할당 됩니다. 해당 데이터 구조를 초기화 하거나 생성 및 소멸 않았거나 되어 데이터 구조 소멸 될 때 해당 리소스를 해제 하는 경우 리소스를 획득 합니다. RAII 패턴을 사용 하면 바깥쪽 범위 전에 소멸자가 호출 합니다. 따라서 리소스 올바르게 관리 되는 예외가 발생 하는 경우 또는 함수에는 여러 개 포함 된 경우 `return` 문.  
  
 다음 예제에서는 라고 하는 구조를 정의 `scoped_blocking_signal`합니다. 생성자는 `scoped_blocking_signal` 구조 초과 구독 여부를 소멸자 초과 구독을 설정 합니다.  
  
 [!code-cpp[concrt-download-oversubscription#2](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_2.cpp)]  
  
 본문을 수정 하는 다음 예제는 `download` 함수가 반환 되기 전에 RAII 해당 초과 구독을 확인 하는 데 사용할 메서드를 사용할 수 없습니다. 이 방법을 사용 하면는 `download` 메서드는 예외 로부터 안전 합니다.  
  
 [!code-cpp[concrt-download-oversubscription#3](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_3.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [컨텍스트](../../parallel/concrt/contexts.md)   
 [Context:: oversubscribe 메서드](reference/context-class.md#oversubscribe)


