---
title: "연습: 에이전트 기반 응용 프로그램 만들기 | Microsoft Docs"
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
  - "비동기 에이전트, 만들기"
  - "에이전트 클래스, 예제"
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# 연습: 에이전트 기반 응용 프로그램 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 에이전트를 기반으로 한 기본 응용 프로그램을 만드는 방법에 대해 설명합니다.  이 연습을 통해 텍스트 파일에서 비동기적으로 데이터를 읽는 에이전트를 만들 수 있습니다.  응용 프로그램에서는 Adler\-32 체크섬 알고리즘을 사용하여 해당 파일 콘텐츠의 체크섬을 계산합니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 항목의 내용을 이해해야 합니다.  
  
-   [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)  
  
-   [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)  
  
-   [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)  
  
##  <a name="top"></a> 단원  
 이 연습에서는 다음과 같은 작업을 수행하는 방법을 보여 줍니다.  
  
-   [콘솔 응용 프로그램 만들기](#createApplication)  
  
-   [file\_reader 클래스 만들기](#createAgentClass)  
  
-   [응용 프로그램에서 file\_reader 클래스 사용](#useAgentClass)  
  
##  <a name="createApplication"></a> 콘솔 응용 프로그램 만들기  
 이 단원에서는 프로그램에서 사용할 헤더 파일을 참조하는 Visual C\+\+ 콘솔 응용 프로그램을 만드는 방법을 보여 줍니다.  
  
#### Win32 콘솔 응용 프로그램 마법사를 사용하여 Visual C\+\+ 응용 프로그램을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 클릭하여 **새 프로젝트** 대화 상자를 표시합니다.  
  
2.  **새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Visual C\+\+** 노드를 선택한 다음, **템플릿** 창에서 **Win32 콘솔 응용 프로그램**을 선택합니다.  프로젝트 이름\(예: `BasicAgent`\)을 입력하고 **확인**을 클릭하여 **Win32 콘솔 응용 프로그램 마법사**를 표시합니다.  
  
3.  **Win32 콘솔 응용 프로그램 마법사** 대화 상자에서 **마침**을 클릭합니다.  
  
4.  stdafx.h에서 다음 코드를 추가합니다.  
  
     [!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_1.h)]  
  
     헤더 파일 agents.h에는 [concurrency::agent](../../parallel/concrt/reference/agent-class.md) 클래스의 기능이 포함되어 있습니다.  
  
5.  응용 프로그램을 빌드하고 실행하여 제대로 만들어졌는지 확인합니다.  응용 프로그램을 빌드하려면 **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  응용 프로그램이 제대로 빌드되면 **디버그** 메뉴에서 **디버깅 시작**을 클릭하여 응용 프로그램을 실행합니다.  
  
 \[[맨 위](#top)\]  
  
##  <a name="createAgentClass"></a> file\_reader 클래스 만들기  
 이 단원에서는 `file_reader` 클래스를 만드는 방법을 보여 줍니다.  런타임에서는 각 에이전트가 자체의 컨텍스트에서 작업을 수행하도록 예약합니다.  따라서 동기적으로 작업을 수행하지만 다른 구성 요소와 비동기적으로 상호 작용하는 에이전트를 만들 수 있습니다.  `file_reader` 클래스는 지정된 입력 파일에서 데이터를 읽고 지정된 대상 컴퓨터에 해당 파일의 데이터를 보냅니다.  
  
#### file\_reader 클래스를 만들려면  
  
1.  프로젝트에 새 C\+\+ 헤더 파일을 추가합니다.  이렇게 하려면 **솔루션 탐색기**에서 **헤더 파일** 노드를 마우스 오른쪽 단추로 클릭하고 **추가**를 클릭한 다음, **새 항목**을 클릭합니다.  그런 다음 **템플릿** 창에서 **헤더 파일 \(.h\)**을 선택합니다.  **새 항목 추가** 대화 상자가 나타나면 **이름** 상자에 `file_reader.h`를 입력하고 **추가**를 클릭합니다.  
  
2.  file\_reader.h에서 다음 코드를 추가합니다.  
  
     [!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_2.h)]  
  
3.  file\_reader.h에 `agent`에서 파생되는 `file_reader` 클래스를 만듭니다.  
  
     [!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_3.h)]  
  
4.  다음 데이터 멤버를 클래스의 `private` 섹션에 추가합니다.  
  
     [!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_4.h)]  
  
     `_file_name` 멤버는 에이전트가 읽는 파일 이름입니다.  `_target` 멤버는 에이전트가 파일 콘텐츠를 쓰는 [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) 개체입니다.  `_error` 멤버는 에이전트의 수명 동안 발생하는 모든 오류를 저장합니다.  
  
5.  `file_reader` 생성자에 대한 다음 코드를 `file_reader` 클래스의 `public` 섹션에 추가합니다.  
  
     [!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_5.h)]  
  
     각 생성자 오버로드는 `file_reader` 데이터 멤버를 설정합니다.  두 번째 및 세 번째 생성자 오버로드를 통해 응용 프로그램에서 특정 스케줄러를 에이전트에 사용할 수 있습니다.  첫 번째 오버로드는 에이전트에 기본 스케줄러를 사용합니다.  
  
6.  `get_error` 메서드를 `file_reader` 클래스의 public 섹션에 추가합니다.  
  
     [!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_6.h)]  
  
     `get_error` 메서드는 에이전트의 수명 동안 발생하는 모든 오류를 검색합니다.  
  
7.  클래스의 `protected` 섹션에서 [concurrency::agent::run](../Topic/agent::run%20Method.md) 메서드를 구현합니다.  
  
     [!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_7.h)]  
  
     `run` 메서드는 파일을 열고 데이터를 읽습니다.  `run` 메서드는 예외 처리를 사용하여 파일 처리 중에 발생한 오류를 캡처합니다.  
  
     이 메서드는 파일에서 데이터를 읽을 때마다 [concurrency::asend](../Topic/asend%20Function.md) 함수를 호출하여 해당 데이터를 대상 버퍼에 보냅니다.  또한 대상 버퍼에 빈 문자열을 보내 처리가 끝났음을 나타냅니다.  
  
 다음 예제에서는 file\_reader.h의 전체 내용을 보여 줍니다.  
  
 [!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_8.h)]  
  
 \[[맨 위](#top)\]  
  
##  <a name="useAgentClass"></a> 응용 프로그램에서 file\_reader 클래스 사용  
 이 단원에서는 `file_reader` 클래스를 사용하여 텍스트 파일의 내용을 읽는 방법을 보여 줍니다.  또한 이 파일 데이터를 받고 Adler\-32 체크섬을 계산하는 [concurrency::call](../../parallel/concrt/reference/call-class.md) 개체를 만드는 방법도 보여 줍니다.  
  
#### 응용 프로그램에서 file\_reader 클래스를 사용하려면  
  
1.  BasicAgent.cpp에서 다음 `#include` 문을 추가합니다.  
  
     [!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_9.cpp)]  
  
2.  BasicAgent.cpp에서 다음 `using` 지시문을 추가합니다.  
  
     [!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_10.cpp)]  
  
3.  `_tmain` 함수에서 처리의 끝을 알리는 [concurrency::event](../../parallel/concrt/reference/event-class.md) 개체를 만듭니다.  
  
     [!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_11.cpp)]  
  
4.  데이터를 받으면 체크섬을 업데이트하는 `call` 개체를 만듭니다.  
  
     [!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_12.cpp)]  
  
     또한 이 `call` 개체는 빈 문자열을 받으면 처리가 끝났음을 알리도록 `event` 개체를 설정합니다.  
  
5.  test.txt 파일에서 읽고 이 파일의 내용을 `call` 개체에 쓰는 `file_reader` 개체를 만듭니다.  
  
     [!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_13.cpp)]  
  
6.  에이전트를 시작한 후 끝날 때까지 기다립니다.  
  
     [!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_14.cpp)]  
  
7.  `call` 개체가 모든 데이터를 받고 끝날 때까지 기다립니다.  
  
     [!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_15.cpp)]  
  
8.  파일 판독기에서 오류를 확인합니다.  오류가 없으면 최종 Adler\-32 합계를 계산하여 콘솔에 출력합니다.  
  
     [!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_16.cpp)]  
  
 다음 예제에서는 전체 BasicAgent.cpp 파일을 보여 줍니다.  
  
 [!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_17.cpp)]  
  
 \[[맨 위](#top)\]  
  
## 샘플 입력  
 다음 샘플은 text.txt 입력 파일의 내용입니다.  
  
  **빠른 갈색 여우**  
**이동 합니다.**  
**게으른 개**   
## 샘플 출력  
 샘플 입력과 함께 사용하여 이 프로그램을 실행하면 다음과 같은 결과가 출력됩니다.  
  
  **Adler\-32 합계는 fefb0d75**   
## 강력한 프로그래밍  
 데이터 멤버에 동시에 액세스할 수 없게 하려면 작업을 수행하는 메서드를 클래스의 `protected` 또는 `private` 섹션에 추가하는 것이 좋습니다.  에이전트에서 메시지를 받거나 에이전트에 메시지를 보내는 메서드만 클래스의 `public` 섹션에 추가하십시오.  
  
 항상 [concurrency::agent::done](../Topic/agent::done%20Method.md) 메서드를 호출하여 에이전트를 완료 상태로 이동합니다.  일반적으로 `run` 메서드에서 반환하기 전에 이 메서드를 호출합니다.  
  
## 다음 단계  
 에이전트 기반 응용 프로그램의 다른 예제를 보려면 [연습: join을 사용하여 교착 상태 방지](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)를 참조하십시오.  
  
## 참고 항목  
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)   
 [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)   
 [연습: join을 사용하여 교착 상태 방지](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)