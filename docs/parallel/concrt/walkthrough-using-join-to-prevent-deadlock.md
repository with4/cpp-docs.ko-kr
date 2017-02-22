---
title: "연습: join을 사용하여 교착 상태 방지 | Microsoft Docs"
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
  - "조인으로 교착 상태 방지[동시성 런타임]"
  - "교착 상태, 방지[동시성 런타임]"
  - "non-greedy 조인, 예제"
  - "join 클래스, 예제"
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 연습: join을 사용하여 교착 상태 방지
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 [concurrency::join](../../parallel/concrt/reference/join-class.md) 클래스를 사용하여 응용 프로그램의 교착 상태를 방지하는 방법을 보여 주기 위해 철학자들의 만찬 문제\(Dining Philosophers Problem\)를 활용합니다.  소프트웨어 응용 프로그램에서는 둘 이상의 프로세스에서 각각 리소스를 보유하는 경우 다른 프로세스가 일부 다른 리소스를 해제하기를 서로 기다릴 때 *교착 상태*가 발생합니다.  
  
 철학자들의 만찬 문제는 여러 개의 동시 프로세스 사이에서 리소스 집합이 공유되는 경우 발생할 수 있는 일반적인 문제들 중 특정한 예입니다.  
  
## 사전 요구 사항  
 이 연습을 시작하기 전에 다음 항목의 내용을 읽어 보십시오.  
  
-   [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)  
  
-   [연습: 에이전트 기반 응용 프로그램 만들기](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)  
  
-   [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)  
  
-   [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)  
  
##  <a name="top"></a> 단원  
 이 연습에는 다음 단원이 포함되어 있습니다.  
  
-   [철학자들의 만찬 문제](#problem)  
  
-   [간단한 구현](#deadlock)  
  
-   [join을 사용하여 교착 상태 방지](#solution)  
  
##  <a name="problem"></a> 철학자들의 만찬 문제  
 철학자들의 만찬 문제에서는 응용 프로그램에서 교착 상태가 어떤 식으로 발생하는지를 보여 줍니다.  이 문제에서는 다섯 명의 철학자가 원형 탁자에 앉아 있습니다.  모든 철학자는 생각과 식사를 교대로 반복합니다.  또한 모든 철학자는 왼쪽에 있는 사람과 젓가락 한 쪽을 공유하고 오른쪽에 있는 사람과 나머지 젓가락 한 쪽을 공유해야 합니다.  다음 그림에서는 이 레이아웃을 보여 줍니다.  
  
 ![철학자들의 만찬 문제](../../parallel/concrt/media/dining_philosophersproblem.png "Dining\_PhilosophersProblem")  
  
 식사를 하기 위해 철학자는 양 쪽 젓가락을 둘 다 가지고 있어야 합니다.  모든 철학자가 한 쪽 젓가락만 가지고 있고 다른 젓가락을 기다리는 상태인 경우 아무도 음식을 먹을 수 없고 모두 굶게 됩니다.  
  
 \[[맨 위](#top)\]  
  
##  <a name="deadlock"></a> 간단한 구현  
 다음 예제에서는 철학자들의 만찬 문제에 대한 간단한 구현을 보여 줍니다.  [concurrency::agent](../../parallel/concrt/reference/agent-class.md)에서 파생되는 `philosopher` 클래스를 사용하면 각 철학자가 독립적으로 동작할 수 있습니다.  이 예제에서는 [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) 개체의 공유 배열을 사용하여 각 `philosopher` 개체에 젓가락 쌍에 대한 단독 액세스 권한을 제공합니다.  
  
 그림과 구현의 관계를 설정하기 위해 `philosopher` 클래스는 한 명의 철학자를 나타냅니다.  `int` 변수는 각 젓가락 한 쪽을 나타냅니다.  `critical_section` 개체는 젓가락 받침 역할을 합니다.  `run` 메서드는 철학자의 수명을 시뮬레이션합니다.  `think` 메서드는 생각하는 행동을 시뮬레이션하고 `eat` 메서드는 먹는 행동을 시뮬레이션합니다.  
  
 `philosopher` 개체는 `eat` 메서드를 호출하기 전에 받침에서 젓가락을 제거하는 것을 시뮬레이션하기 위해 두 `critical_section` 개체를 모두 잠급니다.  `eat` 메서드를 호출한 후 `philosopher` 개체는 `critical_section` 개체를 다시 잠금 해제 상태로 설정하여 젓가락을 받침에 돌려줍니다.  
  
 `pickup_chopsticks` 메서드는 교착 상태가 발생할 수 있는 경우를 보여 줍니다.  모든 `philosopher` 개체가 잠금 중 하나에 대한 액세스 권한을 가지고 있으면 다른 잠금은 다른 `philosopher` 개체에 의해 제어되므로 `philosopher` 개체를 계속할 수 없습니다.  
  
## 예제  
  
### 설명  
  
### 코드  
 [!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_1.cpp)]  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `philosophers-deadlock.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc philosophers\-deadlock.cpp**  
  
 \[[맨 위](#top)\]  
  
##  <a name="solution"></a> join을 사용하여 교착 상태 방지  
 이 단원에서는 메시지 버퍼 및 메시지 전달 함수를 사용하여 교착 상태 가능성을 제거하는 방법을 보여 줍니다.  
  
 이전 예제와의 관계를 설정하기 위해 `philosopher` 클래스는 [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md) 개체 및 `join` 개체를 사용하여 각 `critical_section` 개체를 바꿉니다.  `join` 개체는 젓가락을 철학자에게 제공하는 중재인 역할을 합니다.  
  
 대상이 `unbounded_buffer` 개체에서 메시지를 받으면 해당 메시지가 메시지 큐에서 제거되므로 이 예제에서는 `unbounded_buffer` 클래스를 사용합니다.  이렇게 하면 메시지를 보관하는 `unbounded_buffer` 개체에서 젓가락을 사용할 수 있음을 나타낼 수 있습니다.  메시지를 보관하지 않는 `unbounded_buffer` 개체는 젓가락이 아직 사용 중임을 나타냅니다.  
  
 non\-greedy 조인은 두 `unbounded_buffer` 개체에 모두 메시지가 포함된 경우에만 각 `philosopher` 개체에 젓가락 양 쪽에 대한 액세스 권한을 제공하므로 이 예제에서는 non\-greedy `join` 개체를 사용합니다.  greedy 조인은 메시지를 사용할 수 있게 되면 즉시 해당 메시지를 수락하므로 교착 상태를 방지하지 못합니다.  모든 greedy `join` 개체가 메시지 중 하나를 받지만 다른 메시지를 사용할 수 있을 때까지 영원히 기다리는 경우 교착 상태가 발생할 수 있습니다.  
  
 greedy 조인과 non\-greedy 조인에 대한 자세한 내용 및 다양한 메시지 버퍼 형식 간의 차이점에 대한 설명은 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)을 참조하십시오.  
  
#### 이 예제에서 교착 상태를 방지하려면  
  
1.  예제에서 다음 코드를 제거합니다.  
  
     [!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_2.cpp)]  
  
2.  `philosopher` 클래스의 `_left` 및 `_right` 데이터 멤버 형식을 `unbounded_buffer`로 변경합니다.  
  
     [!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_3.cpp)]  
  
3.  `unbounded_buffer` 개체를 매개 변수로 사용하도록 `philosopher` 생성자를 수정합니다.  
  
     [!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_4.cpp)]  
  
4.  non\-greedy `join` 개체를 사용하여 젓가락 양 쪽에 대한 메시지 버퍼에서 메시지를 받도록 `pickup_chopsticks` 메서드를 수정합니다.  
  
     [!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_5.cpp)]  
  
5.  젓가락 양 쪽에 대한 메시지 버퍼에 메시지를 보내 젓가락에 대한 액세스를 해제하도록 `putdown_chopsticks` 메서드를 수정합니다.  
  
     [!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_6.cpp)]  
  
6.  `pickup_chopsticks` 메서드의 결과를 보관하고 해당 결과를 `putdown_chopsticks` 메서드에 전달하도록 `run` 메서드를 수정합니다.  
  
     [!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_7.cpp)]  
  
7.  각각 하나의 메시지를 보관하는 `unbounded_buffer` 개체의 배열이 되도록 `wmain` 함수에서 `chopsticks` 변수 선언을 수정합니다.  
  
     [!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_8.cpp)]  
  
## 예제  
  
### 설명  
 다음은 non\-greedy `join` 개체를 사용하여 교착 상태 위험을 제거하는 전체 예제를 보여 줍니다.  
  
### 코드  
 [!code-cpp[concrt-philosophers-join#1](../../parallel/concrt/codesnippet/CPP/walkthrough-using-join-to-prevent-deadlock_9.cpp)]  
  
### 설명  
 이 예제의 결과는 다음과 같습니다.  
  
  **아리스토텔레스는 50 회를 먹었다.**  
**데카르트는 50 회를 먹었다.**  
**홉은 50 회를 먹었다.**  
**소크라테스는 50 회를 먹었다.**  
**플라톤은 50 회를 먹었다.**   
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `philosophers-join.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc philosophers\-join.cpp**  
  
 \[[맨 위](#top)\]  
  
## 참고 항목  
 [동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)   
 [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)