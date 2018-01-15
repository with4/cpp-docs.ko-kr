---
title: "연습: join 교착 상태 방지을 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- preventing deadlock with joins [Concurrency Runtime]
- deadlock, preventing [Concurrency Runtime]
- non-greedy joins, example
- join class, example
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 894ff7da95f09b1aedaa8fd9d1d9b44f77017a8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-using-join-to-prevent-deadlock"></a>연습: join을 사용하여 교착 상태 방지
이 항목에서는 사용 하는 방법을 보여 주기 위해 철학자 들의 만찬 문제 사용는 [concurrency:: join](../../parallel/concrt/reference/join-class.md) 응용 프로그램에서 교착 상태를 방지 하는 클래스입니다. 소프트웨어 응용 프로그램에서 *교착 상태* 두 개 이상의 프로세스 각 리소스를 보유 서로 다른 프로세스를 다른 리소스를 해제 될 때까지 기다릴 때 발생 합니다.  
  
 철학자 들의 만찬 문제는 일반 리소스 집합을 여러 개의 동시 프로세스 간에 공유 되는 경우 발생할 수 있는 문제 집합의 한 예입니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 시작 하기 전에 다음 항목을 읽어보세요.  
  
- [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)  
  
- [연습: 에이전트 기반 응용 프로그램 만들기](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)  
  
- [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)  
  
- [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)  
  
- [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)  
  
##  <a name="top"></a> 섹션  
 이 연습에는 다음과 같은 섹션이 있습니다.  
  
- [철학자 들의 만찬 문제](#problem)  
  
- [Naïve 구현](#deadlock)  
  
- [교착 상태 방지 하는 조인을 사용 하 여](#solution)  
  
##  <a name="problem"></a>철학자 들의 만찬 문제  
 철학자 들의 만찬 문제는 응용 프로그램에서 교착 상태가 발생 하는 방법을 보여 줍니다. 이 문제에 5 명의 philosophers 원형 테이블에 앉아 합니다. 모든 철학자 생각과 식사를 번갈아 합니다. 왼쪽에 있는 모든 철학자 젓가락을 공유 해야 사람과 오른쪽에 있습니다. 다음 그림에서는이 레이아웃을 보여 줍니다.  
  
 ![철학자 들 음식점 문제](../../parallel/concrt/media/dining_philosophersproblem.png "dining_philosophersproblem")  
  
 식사를 철학자 두 젓가락 유효 해야 합니다. 모든 철학자 하나만 젓가락 보유 하 고 다른 하나에 대 한 대기, 음식을 eat 수는 다음 한 모두 실행할 수 없게 합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="deadlock"></a>Naïve 구현  
 다음 예제에서는 철학자 들의 만찬 문제의 간단한 구현을 보여 줍니다. `philosopher` 클래스에서 파생 된 [concurrency:: agent](../../parallel/concrt/reference/agent-class.md), 각 철학자가 독립적으로 동작할 수 있습니다. 이 예제에서는의 공유 배열을 사용 하 여 [concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) 각 개체 `philosopher` 젓가락 쌍에 대 한 단독 액세스 개체입니다.  
  
 그림에서는 구현의 관계를 설정 하는 `philosopher` 하나 철학자 클래스를 나타냅니다. `int` 각 젓가락 변수를 나타냅니다. `critical_section` 개체에 젓가락 놓으면 소유자를 토대로 합니다. `run` 메서드는 철학자의 수명의 시뮬레이션 합니다. `think` 생각의 동작을 시뮬레이션 하는 메서드 및 `eat` 메서드 식의 동작을 시뮬레이션 합니다.  
  
 A `philosopher` 개체를 모두 잠급니다 `critical_section` 개체를 호출 하기 전에 소유자에서 젓가락의 제거를 시뮬레이션 하는 `eat` 메서드. 호출한 후 `eat`, `philosopher` 개체 소유자에 게 젓가락 설정 하 여 반환 된 `critical_section` 개체 잠금 해제 된 상태를 다시 합니다.  
  
 `pickup_chopsticks` 교착 상태가 발생할 수 있는 메서드를 보여 줍니다. 모든 경우 `philosopher` 개체 잠금 중 다음 없음에 대 한 액세스 권한을 얻습니다 `philosopher` 개체를 다른 잠금은 다른에 의해 제어 되므로 계속 수 `philosopher` 개체입니다.  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
  
### <a name="code"></a>코드  
 [!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_1.cpp)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `philosophers-deadlock.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc philosophers-deadlock.cpp**  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="solution"></a>교착 상태 방지 하는 조인을 사용 하 여  
 이 섹션에는 메시지 버퍼 및 메시지 전달 함수를 사용 하 여 교착 상태의 가능성을 제거 하는 방법을 보여 줍니다.  
  
 이 예에서는 이전 쿼리와 관련 시키기 위해는 `philosopher` 클래스 대신 각 `critical_section` 사용 하 여 개체는 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) 개체 및 `join` 개체입니다. `join` 젓가락 철학자를 제공 하는 중재자 역할입니다.  
  
 사용 하 여이 예제는 `unbounded_buffer` 클래스를 대상에서 메시지를 받을 때 하므로 `unbounded_buffer` 개체는 메시지가 메시지 큐에서 제거 됩니다. 이 통해는 `unbounded_buffer` 에서 젓가락을 나타내는 메시지를 보유 하는 개체를 사용할 수 있습니다. `unbounded_buffer` 없는 메시지를 보유 하는 개체에서 젓가락 사용 되 고 있음을 나타냅니다.  
  
 이 예제를 사용 하 여 non-greedy `join` 각 non-greedy 조인 제공 하기 때문에 개체 `philosopher` 젓가락 모두에 대 한 액세스 개체 경우에만 둘 다 `unbounded_buffer` 개체는 메시지를 포함 합니다. Greedy 조인 greedy 조인 사용 가능 하 게 되는 즉시 메시지를 수락 하기 때문에 교착 상태를 방지 하지 못합니다. 모든 greedy 경우 교착 상태가 발생할 수 `join` 개체 메시지 중 하나가 받기는 하지만 사용할 수 있게 하려면 다른 무기한 대기 합니다.  
  
 Greedy 및 비 greedy 조인 및 다양 한 메시지 버퍼 유형 간의 차이점에 대 한 자세한 내용은 참조 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)합니다.  
  
#### <a name="to-prevent-deadlock-in-this-example"></a>이 예에서 교착 상태를 방지 하려면  
  
1.  이 예제에서 다음 코드를 제거 합니다.  
  
 [!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_2.cpp)]  
  
2.  형식을 변경는 `_left` 및 `_right` 의 데이터 멤버는 `philosopher` 클래스를 `unbounded_buffer`합니다.  
  
 [!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_3.cpp)]  
  
3.  수정 된 `philosopher` 되려면 생성자 `unbounded_buffer` 개체를 매개 변수로 합니다.  
  
 [!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_4.cpp)]  
  
4.  수정 된 `pickup_chopsticks` 메서드를 사용 하 여 non-greedy `join` 젓가락 모두에 대 한 메시지 버퍼에서 메시지를 받는 개체입니다.  
  
 [!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_5.cpp)]  
  
5.  수정 된 `putdown_chopsticks` 젓가락 모두에 대 한 메시지 버퍼에 메시지를 전송 하 여 젓가락에 대 한 액세스를 해제 하는 메서드.  
  
 [!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_6.cpp)]  
  
6.  수정 된 `run` 의 결과 저장 하는 메서드는 `pickup_chopsticks` 메서드 하 고 해당 결과를 전달 하려면는 `putdown_chopsticks` 메서드.  
  
 [!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_7.cpp)]  
  
7.  선언을 수정는 `chopsticks` 변수에 `wmain` 함수 배열을를 `unbounded_buffer` 각각 하나의 메시지를 보관 하는 개체입니다.  
  
 [!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_8.cpp)]  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 다음은 사용 하는 전체 예제 식별 `join` 교착 상태의 위험이 제거 하는 개체입니다.  
  
### <a name="code"></a>코드  
 [!code-cpp[concrt-philosophers-join#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_9.cpp)]  
  
### <a name="comments"></a>설명  
 이 예제의 결과는 다음과 같습니다.  
  
```Output  
aristotle ate 50 times.  
descartes ate 50 times.  
hobbes ate 50 times.  
socrates ate 50 times.  
plato ate 50 times.  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `philosophers-join.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc philosophers-join.cpp**  
  
 [[맨 위로 이동](#top)]  
  
## <a name="see-also"></a>참고 항목  
 [동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)   
 [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)
