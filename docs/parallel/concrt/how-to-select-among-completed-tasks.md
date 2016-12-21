---
title: "방법: 완료된 작업 중에서 선택 | Microsoft Docs"
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
  - "완료된 작업 중에서 선택[동시성 런타임]"
  - "완료된 작업, 중에서 선택[동시성 런타임]"
ms.assetid: c8ccc160-043f-4599-847b-32ed270bb257
caps.latest.revision: 17
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 완료된 작업 중에서 선택
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 예제에서는 [concurrency::choice](../../parallel/concrt/reference/choice-class.md) 및 [concurrency::join](../../parallel/concrt/reference/join-class.md) 클래스를 사용하여 검색 알고리즘을 완료할 첫 번째 작업을 선택하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 두 가지 검색 알고리즘을 병렬로 수행하고 완료할 첫 번째 알고리즘을 선택합니다.  이 예제에서는 직원에 대한 숫자 식별자 및 급여를 저장하는 `employee` 형식을 정의합니다.  `find_employee` 함수는 제공된 식별자 또는 제공된 급여와 일치하는 첫 번째 직원을 찾습니다.  또한 `find_employee` 함수는 제공된 식별자 또는 급여에 해당하는 직원이 없는 경우도 처리합니다.  `wmain` 함수는 `employee` 개체의 배열을 만들고 몇 가지 식별자 및 급여 값을 검색합니다.  
  
 이 예제에서는 `choice` 개체를 사용하여 다음과 같은 경우 중에서 선택합니다.  
  
1.  제공된 식별자를 포함하는 직원이 있는 경우  
  
2.  제공된 급여를 포함하는 직원이 있는 경우  
  
3.  제공된 식별자 또는 급여를 포함하는 직원이 없는 경우  
  
 처음의 두 경우를 위해 이 예제에서는 [concurrency::single\_assignment](../../parallel/concrt/reference/single-assignment-class.md) 개체를 사용하여 식별자를 저장하고 다른 `single_assignment` 개체를 사용하여 급여를 저장합니다.  세 번째 경우를 위해서는 `join` 개체를 사용합니다.  `join` 개체는 두 가지 추가 `single_assignment` 개체로 구성되는데, 하나는 제공된 식별자를 포함하는 직원이 없는 경우에 사용되고 다른 하나는 제공된 급여를 포함하는 직원이 없는 경우에 사용됩니다.  `join` 개체는 각 멤버가 메시지를 받을 때 메시지를 보냅니다.  이 예제의 경우 `join` 개체는 제공된 식별자 또는 급여를 포함하는 직원이 없는 경우 메시지를 보냅니다.  
  
 이 예제에서는 [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md) 개체를 사용하여 두 검색 알고리즘을 병렬로 실행합니다.  각 검색 작업은 지정된 직원이 있는지 여부를 나타내기 위해 `single_assignment` 개체 중 하나에 씁니다.  이 예제에서는 [concurrency::receive](../Topic/receive%20Function.md) 함수를 사용하여 메시지를 포함하는 첫 번째 버퍼의 인덱스를 가져오고 `switch` 블록을 사용하여 결과를 출력합니다.  
  
 [!code-cpp[concrt-find-employee#1](../../parallel/concrt/codesnippet/CPP/how-to-select-among-completed-tasks_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **14758 id 가진 직원은 급여 27780.00를 포함합니다.**  
**29150.00 급여를 가진 직원은 id 84345를 포함합니다.**  
**61935 id 가진 직원은 급여 29905.00를 포함합니다.**  
**직원 id 899 또는 급여 31223.00를 가지고 있습니다.** 이 예제에서는 [concurrency::make\_choice](../Topic/make_choice%20Function.md) 도우미 함수를 사용하여 `choice` 개체를 만들고 [concurrency::make\_join](../Topic/make_join%20Function.md) 도우미 함수를 사용하여 `join` 개체를 만듭니다.  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `find-employee.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc find\-employee.cpp**  
  
## 참고 항목  
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)   
 [choice 클래스](../../parallel/concrt/reference/choice-class.md)   
 [join 클래스](../../parallel/concrt/reference/join-class.md)