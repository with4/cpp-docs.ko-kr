---
title: "방법: call 및 transformer 클래스에 작업 함수 제공 | Microsoft Docs"
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
  - "call 클래스, 예제"
  - "transformer 클래스 사용[동시성 런타임]"
  - "call 클래스 사용[동시성 런타임]"
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
caps.latest.revision: 15
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: call 및 transformer 클래스에 작업 함수 제공
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 [concurrency::call](../../parallel/concrt/reference/call-class.md) 및 [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) 클래스에 작업 함수를 제공하는 몇 가지 방법을 보여 줍니다.  
  
 첫 번째 예제에서는 `call` 개체에 람다 식을 전달하는 방법을 보여 줍니다.  두 번째 예제에서는 `call` 개체에 함수 개체를 전달하는 방법을 보여 줍니다.  세 번째 예제에서는 `call` 개체에 클래스 메서드를 바인딩하는 방법을 보여 줍니다.  
  
 설명을 위해 이 항목의 모든 예제에서는 `call` 클래스를 사용합니다.  `transformer` 클래스를 사용하는 예제를 보려면 [방법: 데이터 파이프라인에서 transformer 사용](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `call` 클래스를 사용하는 일반적인 방법을 보여 줍니다.  이 예제에서는 `call` 생성자에 람다 함수를 전달합니다.  
  
 [!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **13의 제곱은 169입니다.**   
## 예제  
 다음 예제는 이전 예제와 유사하지만 `call` 클래스를 함수 개체\(functor\)와 함께 사용한다는 점이 다릅니다.  
  
 [!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]  
  
## 예제  
 다음 예제는 이전 예제와 유사하지만 [std::bind1st](../Topic/bind1st%20Function.md) 및 [std::mem\_fun](../Topic/mem_fun%20Function.md) 함수를 사용하여 `call` 개체를 클래스 메서드에 바인딩한다는 점이 다릅니다.  
  
 `call` 또는 `transformer` 개체를 함수 호출 연산자인 `operator()` 대신 특정 클래스 메서드에 바인딩해야 하는 경우 이 방법을 사용합니다.  
  
 [!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]  
  
 다음 예제와 같이 `bind1st` 함수의 결과를 [std::function](../../standard-library/function-class.md) 개체에 할당하거나 `auto` 키워드를 사용할 수도 있습니다.  
  
 [!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `call.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc call.cpp**  
  
## 참고 항목  
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [방법: 데이터 파이프라인에서 transformer 사용](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)   
 [call 클래스](../../parallel/concrt/reference/call-class.md)   
 [transformer 클래스](../../parallel/concrt/reference/transformer-class.md)