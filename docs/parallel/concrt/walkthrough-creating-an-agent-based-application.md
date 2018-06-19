---
title: '연습: 에이전트 기반 응용 프로그램 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78826bb9f00e77a80fb65dd3a3ceda7eedb38796
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692628"
---
# <a name="walkthrough-creating-an-agent-based-application"></a>연습: 에이전트 기반 응용 프로그램 만들기
이 항목에서는 기본 에이전트 기반 응용 프로그램을 만드는 방법을 설명 합니다. 이 연습에서는 텍스트 파일에서 데이터를 비동기적으로 읽는 에이전트를 만들 수 있습니다. 응용 프로그램 adler-32 체크섬 알고리즘을 사용 하 여 해당 파일의 내용 체크섬을 계산 합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료 하려면 다음 항목을 이해 해야 합니다.  
  
- [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)  
  
- [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)  
  
- [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)  
  
- [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)  
  
##  <a name="top"></a> 섹션  
 이 연습에서는 다음 작업을 수행 하는 방법을 보여 줍니다.  
  
- [콘솔 응용 프로그램 만들기](#createapplication)  
  
- [File_reader 클래스 만들기](#createagentclass)  
  
- [File_reader 클래스를 사용 하 여 응용 프로그램에서](#useagentclass)  
  
##  <a name="createapplication"></a> 콘솔 응용 프로그램 만들기  
 이 섹션에 적용 하는 헤더 파일을 참조 하는 Visual c + + 콘솔 응용 프로그램을 만드는 방법을 보여 줍니다.  
  
#### <a name="to-create-a-visual-c-application-by-using-the-win32-console-application-wizard"></a>Win32 콘솔 응용 프로그램 마법사를 사용 하 여 Visual c + + 응용 프로그램을 만들려면  
  
1.  에 **파일** 메뉴에서 클릭 **새로**, 클릭 하 고 **프로젝트** 표시 하는 **새 프로젝트** 대화 상자.  
  
2.  에 **새 프로젝트** 대화 상자는 **Visual c + +** 에서 노드는 **프로젝트 형식** 창과 선택 **Win32 콘솔 응용 프로그램** 에 **템플릿** 창. 예를 들어 프로젝트에 대 한 이름을 입력 `BasicAgent`, 클릭 하 고 **확인** 표시 하는 **Win32 콘솔 응용 프로그램 마법사**합니다.  
  
3.  에 **Win32 콘솔 응용 프로그램 마법사** 대화 상자를 클릭 **마침**합니다.  
  
4.  Stdafx.h, 다음 코드를 추가 합니다.  
  
 [!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]  
  
     기능을 포함 하는 헤더 파일 agents.h는 [concurrency:: agent](../../parallel/concrt/reference/agent-class.md) 클래스입니다.  
  
5.  응용 프로그램 빌드 및 실행 하 여 만들어졌는지 확인 합니다. 에 응용 프로그램을 작성 하는 **빌드** 메뉴를 클릭 하 여 **솔루션 빌드**합니다. 응용 프로그램이 성공적으로 빌드되면를 클릭 하 여 응용 프로그램을 실행 **디버깅 시작** 에 **디버그** 메뉴.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="createagentclass"></a> File_reader 클래스 만들기  
 이 섹션에서는를 만드는 방법을 보여 줍니다.는 `file_reader` 클래스입니다. 런타임 자체 컨텍스트에서 작업을 수행 하려는 각 에이전트를 예약 합니다. 따라서 작업을 동기적으로 수행 하지만 비동기적으로 다른 구성 요소와 상호 작용 하는 에이전트를 만들 수 있습니다. `file_reader` 클래스가 지정된 된 입력된 파일에서 데이터를 읽고 해당 파일에서 지정된 된 대상 컴퓨터에 데이터를 보냅니다.  
  
#### <a name="to-create-the-filereader-class"></a>File_reader 클래스를 만들려면  
  
1.  새 c + + 헤더 파일을 프로젝트에 추가 합니다. 이렇게 하려면 마우스 오른쪽 단추로 클릭는 **헤더 파일** 노드에서 **솔루션 탐색기**, 클릭 **추가**, 클릭 하 고 **새 항목**합니다. 에 **템플릿** 창 선택 **헤더 파일 (.h)** 합니다. 에 **새 항목 추가** 대화 상자에서 `file_reader.h` 에 **이름** 상자 한 다음 클릭 **추가**합니다.  
  
2.  File_reader.h, 다음 코드를 추가 합니다.  
  
 [!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]  
  
3.  File_reader.h, 라는 클래스를 만듭니다 `file_reader` 에서 파생 된 `agent`합니다.  
  
 [!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]  
  
4.  다음 데이터 멤버를 추가할는 `private` 클래스의 섹션입니다.  
  
 [!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]  
  
     `_file_name` 멤버는 에이전트에서 읽을 수 있는 파일 이름입니다. `_target` 멤버는 한 [concurrency:: itarget](../../parallel/concrt/reference/itarget-class.md) 에이전트 파일의 내용을 기록 하는 개체입니다. `_error` 멤버는 에이전트의 수명 중에 발생 하는 모든 오류를 저장 합니다.  
  
5.  다음 코드에 대 한 추가 `file_reader` 생성자에는 `public` 의 섹션은 `file_reader` 클래스.  
  
 [!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]  
  
     설정 하는 각 생성자 오버 로드는 `file_reader` 데이터 멤버입니다. 두 번째 및 세 번째 생성자 오버 로드를 에이전트에서 특정 스케줄러를 사용 하도록 응용을 프로그램 수 있습니다. 첫 번째 오버 로드를 에이전트 기본 스케줄러를 사용합니다.  
  
6.  추가 `get_error` 의 섹션을 공용 메서드는 `file_reader` 클래스입니다.  
  
 [!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]  
  
     `get_error` 메서드는 에이전트의 수명 중에 발생 하는 모든 오류를 검색 합니다.  
  

7.  구현 된 [concurrency::agent::run](reference/agent-class.md#run) 에서 메서드는 `protected` 클래스의 섹션입니다.  

  
 [!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]  
  
`run` 메서드 파일이 열리고 여기에서 데이터를 읽습니다. `run` 메서드 예외 처리를 사용 하 여 파일 처리 중에 발생 하는 모든 오류를 캡처합니다.  
  
   호출 될 때마다가이 메서드는 파일에서 데이터를 읽고는 [concurrency:: asend](reference/concurrency-namespace-functions.md#asend) 대상 버퍼에 해당 데이터를 보내는 함수입니다. 처리의 끝을 나타내는 대상 버퍼를 빈 문자열을 보냅니다.  

  
 다음 예제에서는 file_reader.h의 전체 내용을 보여 줍니다.  
  
 [!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="useagentclass"></a> File_reader 클래스를 사용 하 여 응용 프로그램에서  
 이 섹션에서는 사용 하는 `file_reader` 클래스 텍스트 파일의 내용을 읽을 수 있습니다. 만드는 방법을 보여 줍니다는 [concurrency:: call](../../parallel/concrt/reference/call-class.md) 이 파일 데이터를 받고 해당 adler-32 체크섬을 계산 하는 개체입니다.  
  
#### <a name="to-use-the-filereader-class-in-your-application"></a>응용 프로그램에서 file_reader 클래스를 사용 하려면  
  
1.  BasicAgent.cpp에 다음 추가 `#include` 문.  
  
 [!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]  
  
2.  BasicAgent.cpp에 다음 추가 `using` 지시문입니다.  
  
 [!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]  
  
3.  에 `_tmain` 함수를 만들는 [concurrency:: event](../../parallel/concrt/reference/event-class.md) 개체 처리의 끝입니다.  
  
 [!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]  
  
4.  만들기는 `call` 데이터를 받을 때 체크섬을 업데이트 하는 개체입니다.  
  
 [!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]  
  
     이 `call` 개체도 설정 하는 `event` 빈 문자열 처리의 끝을 받을 때 개체입니다.  
  
5.  만들기는 `file_reader` test.txt 파일에서에서 읽고 해당 파일의 내용을 기록 하는 개체는 `call` 개체입니다.  
  
 [!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]  
  
6.  에이전트를 시작 하 고 완료 될 때까지 대기 합니다.  
  
 [!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]  
  
7.  에 대 한 대기는 `call` 개체를 모든 데이터를 수신 하 고 완료 합니다.  
  
 [!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_15.cpp)]  
  
8.  오류에 대 한 파일 판독기를 확인 합니다. 오류가 발생 한 경우 최종 adler-32 합계를 계산 하 고 콘솔에 합계를 인쇄 합니다.  
  
 [!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_16.cpp)]  
  
 다음 예에서는 전체 BasicAgent.cpp 파일을 보여 줍니다.  
  
 [!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_17.cpp)]  
  
 [[맨 위로 이동](#top)]  
  
## <a name="sample-input"></a>샘플 입력  
 다음은 샘플 입력된 파일 text.txt 내용의입니다.  
  
```Output  
The quick brown fox  
jumps  
over the lazy dog  
```  
  
## <a name="sample-output"></a>샘플 출력  
 샘플 입력을 사용 하는 경우이 프로그램은 다음과 같은 출력을 생성 합니다.  
  
```Output  
Adler-32 sum is fefb0d75  
```  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 데이터 멤버에 대 한 동시 액세스를 방지 하려면 작업을 수행 하는 메서드를 추가 하는 권장는 `protected` 또는 `private` 클래스의 섹션입니다. 만을 에이전트에서 메시지 송신 또는 수신 하는 메서드를 추가할는 `public` 클래스의 섹션입니다.  
  

 항상 호출는 [concurrency:: agent:: 수행](reference/agent-class.md#done) 메서드 에이전트 완료 된 상태로 전환할 수 있습니다. 반환 하기 전에이 메서드를 일반적으로 호출 된 `run` 메서드.  

  
## <a name="next-steps"></a>다음 단계  
 에이전트 기반 응용 프로그램의 다른 예제를 보려면 [연습: join 교착 상태 방지를 사용 하 여](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)   
 [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)   
 [연습: 조인을 사용하여 교착 상태 방지](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)

