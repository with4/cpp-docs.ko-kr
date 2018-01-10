---
title: "방법: 정기적으로 메시지 보내기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f12d9f8af028d1e2e1fc149eeb77181c2f6b1730
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-send-a-message-at-a-regular-interval"></a>방법: 정기적으로 메시지 보내기
이 예제에는 동시성을 사용 하는 방법을 보여 줍니다::[timer 클래스](../../parallel/concrt/reference/timer-class.md) 정기적으로 메시지를 보내려고 합니다.  
  
## <a name="example"></a>예  

 다음 예제에서는 `timer` 긴 작업 중 진행 상황을 보고 하는 개체입니다. 이 예제에서는 링크는 `timer` 개체는 [concurrency:: call](../../parallel/concrt/reference/call-class.md) 개체입니다. `call` 개체는 일정 한 간격으로 진행률 표시기를 콘솔에 출력 합니다. [concurrency::timer::start](reference/timer-class.md#start) 메서드 타이머는 별도 컨텍스트를 실행 합니다. `perform_lengthy_operation` 함수 호출의 [concurrency:: wait](reference/concurrency-namespace-functions.md#wait) 에 시간이 많이 걸리는 작업을 시뮬레이션 하는 주 컨텍스트에서 함수입니다.  

  
 [!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/cpp/how-to-send-a-message-at-a-regular-interval_1.cpp)]  
  
 이 예제는 다음과 같은 샘플 출력을 생성합니다.  
  
```Output  
Performing a lengthy operation..........done.  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `report-progress.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc report-progress.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)
