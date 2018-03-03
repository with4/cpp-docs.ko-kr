---
title: "방법: 메시지 블록 필터 사용 | Microsoft Docs"
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
- message-block filters, using [Concurrency Runtime]
- using message-block filters [Concurrency Runtime]
ms.assetid: db6b99fb-288d-4477-96dc-b9751772ebb2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: adcb300daa81c1325b216128b1971408a5931553
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-a-message-block-filter"></a>방법: 메시지 블록 필터 사용
이 문서를 수락 하거나 해당 메시지의 페이로드를 기준으로 메시지를 거부 하 여 비동기 메시지 블록을 사용 하도록 설정 하려면 필터 함수를 사용 하는 방법을 보여 줍니다.  
  
 와 같은 메시지 블록 개체를 만들 때 한 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md), [concurrency:: call](../../parallel/concrt/reference/call-class.md), 또는 [concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md)는 를제공할수있습니다*filter 함수* 결정 하는 메시지 블록 허용 여부는 메시지를 거부 합니다. 필터 함수에 메시지 블록에 특정 값만 수신 되는지 보장 하는 유용한 방법은입니다.  
  
 필터 함수는 형식으로 메시지 블록을 연결 하는 데 사용 하기 때문에 중요 한 *데이터 흐름 네트워크*합니다. 데이터 흐름 네트워크에서 메시지 블록 특정 조건을 충족 하는 메시지만 처리 하 여 데이터의 흐름을 제어 합니다. 조건문, 루프, 같은 제어 구조를 사용 하 여 데이터 흐름은 규제를 받는 위치 제어 흐름 모델을 비교할이 등에입니다.  
  
 이 문서에서는 메시지 필터를 사용 하는 방법의 기본 예제를 제공 합니다. 메시지 필터 및 데이터 흐름 모델을 사용 하 여 메시지 블록을 연결 하는 추가 예제를 보려면 [연습: 데이터 흐름 에이전트 만들기](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md) 및 [연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md) .  
  
## <a name="example"></a>예  
 다음과 같은 함수가 있다고 합시다 `count_primes`, 들어오는 메시지를 필터링 하지 않는 메시지 블록의 기본 사용법을 보여 주는 합니다. 메시지 블록에 소수 추가 [std:: vector](../../standard-library/vector-class.md) 개체입니다. `count_primes` 함수 메시지 블록에 여러 개의 번호를 전송, 메시지 블록에서 출력 값을 받는 및 해당는 숫자를 소수를 콘솔에 출력 합니다.  
  
 [!code-cpp[concrt-primes-filter#1](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_1.cpp)]  
  
 `transformer` 모든 입력된 값을 처리 하는 개체; 소수 값만 필요 합니다. 메시지 보낸 사람 소수만 보내도록 있도록 응용 프로그램으로 작성 될 수 없습니다, 메시지 수신기의 요구 사항은 항상 알 수 없습니다.  
  
## <a name="example"></a>예  
 다음 함수를 `count_primes_filter`, 동일한 작업을 수행는 `count_primes` 함수입니다. 그러나는 `transformer` 이 버전의 개체 필터 함수를 사용 하 여 소수 값만 수락 하도록 합니다. 작업을 수행 하는 함수는 소수만; 받으므로 따라서 없기를 호출 하 여 `is_prime` 함수입니다.  
  
 때문에 `transformer` 개체 받아들이므로는 `transformer` 개체 자체 소수를 포함할 수 있습니다. 즉,는 `transformer` 이 예제는 개체를 소수를 추가할 필요가 없습니다는 `vector` 개체입니다.  
  
 [!code-cpp[concrt-primes-filter#2](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_2.cpp)]  
  
 `transformer` 개체는 이제 소수 값만 처리 합니다. 이전 예에서 `transformer` 모든 메시지를 처리 하는 개체입니다. 따라서 이전 예제에는 동일한 수의 보내는 메시지에 받아야 합니다. 결과 사용 하 여이 예제는 [concurrency:: send](reference/concurrency-namespace-functions.md#send) 에서 받을 메시지를 확인 하는 함수는 `transformer` 개체입니다. `send` 함수에서 반환 `true` 메시지 버퍼에서 메시지를 수락 하는 경우 및 `false` 메시지 버퍼에서 메시지를 거부 하는 경우. 따라서 메시지 버퍼에서 메시지를 수락 하는 횟수 소수 개수와 일치 합니다.  
  
## <a name="example"></a>예  
 다음 코드에서는 전체 예제를 보여 줍니다. 이 예에서는 호출 모두는 `count_primes` 함수 및 `count_primes_filter` 함수입니다.  
  
 [!code-cpp[concrt-primes-filter#3](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_3.cpp)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `primes-filter.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc primes filter.cpp**  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 Filter 함수는 람다 함수, 함수 포인터 또는 함수 개체 수 있습니다. 모든 필터 함수는 다음 형식 중 하나를 사용 합니다.  
  
```Output  
bool (T)  
bool (T const &)  
```  
  
 데이터의 불필요 한 복사를 방지 하려면 값으로 전송 되는 집계 형식이 있을 경우 두 번째 형태를 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [연습: 데이터 흐름 에이전트 만들기](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)   
 [연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)   
 [transformer 클래스](../../parallel/concrt/reference/transformer-class.md)
