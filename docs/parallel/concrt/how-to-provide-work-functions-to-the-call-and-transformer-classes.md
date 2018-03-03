---
title: "방법: call 및 transformer 클래스에 작업 함수 제공 | Microsoft Docs"
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
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52ab28a015fa0312a5d064401451640c2747e9db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>방법: call 및 transformer 클래스에 작업 함수 제공
이 항목에서는 여러 가지 방법으로 작업 함수를 제공 하는 [concurrency:: call](../../parallel/concrt/reference/call-class.md) 및 [concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) 클래스입니다.  
  
 첫 번째 예제에서는 람다 식을 전달 하는 방법을 보여 줍니다는 `call` 개체입니다. 두 번째 예에 함수 개체를 전달 하는 방법을 보여 줍니다는 `call` 개체입니다. 세 번째 예제에서는 클래스 메서드를 바인딩하는 방법을 보여 줍니다.는 `call` 개체입니다.  
  
 이 항목의 모든 예제 사용 하 여 이해를 돕기는 `call` 클래스입니다. 사용 하는 예제는 `transformer` 클래스를 참조 하십시오. [하는 방법: 데이터 파이프라인에서 transformer 사용](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 일반적으로 사용 하 여 `call` 클래스입니다. 이 예제에서는 전달 하는 람다 함수는 `call` 생성자입니다.  
  
 [!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
```Output  
13 squared is 169.  
```  
  
## <a name="example"></a>예  
 다음 예제를 사용 한다는 점을 제외 하 고 이전 쿼리와 비슷하지만 `call` 함수 개체 (함수)와 함께 클래스입니다.  
  
 [!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]  
  
## <a name="example"></a>예  

 다음 예제를 사용 한다는 점을 제외 하 고 이전 쿼리와 비슷하지만 [std::bind1st](../../standard-library/functional-functions.md#bind1st) 및 [std::mem_fun](../../standard-library/functional-functions.md#mem_fun) 바인딩할 함수는 `call` 클래스 메서드는 개체입니다.  

  
 바인딩해야 하는 경우이 방법을 사용 하 여 한 `call` 또는 `transformer` 개체 대신 함수 호출 연산자는 특정 클래스, 메서드를 `operator()`합니다.  
  
 [!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]  
  
 결과 할당할 수도 있습니다는 `bind1st` 함수를 한 [std:: function](../../standard-library/function-class.md) 사용 또는 개체는 `auto` 키워드에 다음 예제와 같이 합니다.  
  
 [!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `call.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc call.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [방법: 데이터 파이프라인에서 transformer 사용](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)   
 [call 클래스](../../parallel/concrt/reference/call-class.md)   
 [transformer 클래스](../../parallel/concrt/reference/transformer-class.md)
