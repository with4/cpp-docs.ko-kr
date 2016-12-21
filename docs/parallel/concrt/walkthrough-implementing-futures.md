---
title: "연습: 미래 구현 | Microsoft Docs"
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
  - "미래 구현[동시성 런타임]"
  - "미래, 구현[동시성 런타임]"
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
caps.latest.revision: 25
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: 미래 구현
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 응용 프로그램에 future를 구현 하는 방법을 보여 줍니다. 이 항목에는 기존 기능으로 결합 하는 동시성 런타임에서 작업 많은 기능을 수행 하는 방법을 보여 줍니다.  
  
> [!IMPORTANT]
>  이 항목에서는 이해를 돕기 위해 미래의 개념에 대해 설명합니다. 사용 하는 것이 좋습니다 [std:: future](../../standard-library/future-class.md) 또는 [concurrency:: task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) 나중에 사용할 값을 계산 하는 비동기 작업이 필요한 경우.  
  
 A *작업* 은 추가, 좀 더 세분화 된 계산으로 분해할 수 있는 합니다. A *향후* 나중에 사용할 값을 계산 하는 비동기 작업입니다.  
  
 이 항목에서는 미래를 구현 하기는 `async_future` 클래스입니다.  `async_future` 동시성 런타임 구성이 요소를 사용 하는 클래스:는 [concurrency:: task_group](../Topic/task_group%20Class.md) 클래스 및 [concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) 클래스입니다.  `async_future` 클래스에서 사용 하는 `task_group` 클래스는 값을 비동기적으로 계산 하 고 `single_assignment` 계산의 결과 저장 하는 클래스입니다. 생성자는 `async_future` 는 결과 계산 하는 작업 함수를 사용 하는 클래스가 및 `get` 메서드 결과 검색 합니다.  
  
### <a name="to-implement-the-asyncfuture-class"></a>async_future 클래스를 구현하려면  
  
1.  명명 된 템플릿 클래스를 선언 `async_future` 결과 계산의 형식에 대해 매개 변수가입니다. 추가 `public` 및 `private` 이 클래스에는 섹션입니다.  
  
 [!code-cpp[concrt-futures#2](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_1.cpp)]  
  
2.  에 `private` 의 섹션은 `async_future` 클래스를 선언는 `task_group` 및 `single_assignment` 데이터 멤버입니다.  
  
 [!code-cpp[concrt-futures#3](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_2.cpp)]  
  
3.  에 `public` 의 섹션은 `async_future` 클래스 생성자를 구현 합니다. 생성자는 결과 계산 하는 작업 함수에서 매개 변수화 된 템플릿입니다. 에 작업 함수를 비동기적으로 실행 하는 생성자는 `task_group` 사용 하 여 데이터 멤버는 [concurrency:: send](../Topic/send%20Function.md) 결과를 작성 하는 함수는 `single_assignment` 데이터 멤버입니다.  
  
 [!code-cpp[concrt-futures#4](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_3.cpp)]  
  
4.  에 `public` 의 섹션은 `async_future` 클래스 소멸자를 구현 합니다. 소멸자는 작업이 완료 되기를 기다립니다.  
  
 [!code-cpp[concrt-futures#5](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_4.cpp)]  
  
5.  에 `public` 의 섹션은 `async_future` 클래스를 구현는 `get` 메서드. 이 메서드는 사용 된 [concurrency:: receive](../Topic/receive%20Function.md) 작업 함수의 결과 검색 하는 함수입니다.  
  
 [!code-cpp[concrt-futures#6](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_5.cpp)]  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 전체 `async_future` 클래스 및 해당 사용법의 예입니다.  `wmain` 함수 만듭니다는 std::[벡터](../../standard-library/vector-class.md) 10, 000 임의의 정수 값을 포함 하는 개체입니다. 다음 사용 하 여 `async_future` 에 포함 된 최소 및 최대 값을 찾는 개체는 `vector` 개체입니다.  
  
### <a name="code"></a>코드  
 [!code-cpp[concrt-futures#1](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_6.cpp)]  
  
### <a name="comments"></a>설명  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```Output  
smallest: 0  
largest:  9999  
average:  4981  
```  
  
 이 예제에서는 사용은 `async_future::get` 계산의 결과 검색 하는 메서드입니다.  `async_future::get` 메서드 계산 여전히 활성 상태 이면 끝날 때까지 기다립니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 확장 하는 `async_future` 수정, 작업 함수에서 throw 된 예외를 처리 하는 클래스는 `async_future::get` 메서드를 호출 하는 [concurrency::task_group::wait](../Topic/task_group::wait%20Method.md) 메서드.  `task_group::wait` 작업 함수에서 생성 된 모든 예외를 throw 합니다.  
  
 다음 예제에서는 수정된 된 버전의는 `async_future` 클래스입니다.  `wmain` 함수는 `try`-`catch` 블록의 결과 인쇄 하는 `async_future` 개체 또는 작업 함수에서 생성 되는 예외 값을 인쇄 합니다.  
  
 [!code-cpp[concrt-futures-with-eh#1](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_7.cpp)]  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```Output  
caught exception: error  
```  
  
 동시성 런타임에서 예외 처리 모델에 대 한 자세한 내용은 참조 [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `futures.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc futures.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [task_group 클래스](../Topic/task_group%20Class.md)   
 [single_assignment 클래스](../../parallel/concrt/reference/single-assignment-class.md)
