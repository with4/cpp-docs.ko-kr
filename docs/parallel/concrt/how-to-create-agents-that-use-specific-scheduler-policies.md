---
title: '방법: 특정 스케줄러 정책을 사용 하는 에이전트 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scheduler policies, agents [Concurrency Runtime]
- creating agents that use specific policies [Concurrency Runtime]
ms.assetid: 46a3e265-0777-4ec3-a142-967bafc49d67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9efa40d24ed4eaee5b9fd3995a4cf9ed696eb39a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-create-agents-that-use-specific-scheduler-policies"></a>방법: 특정 스케줄러 정책을 사용하는 에이전트 만들기
에이전트는 큰 계산 작업을 해결 하기 위해 다른 구성 요소를 비동기적으로 사용 하는 응용 프로그램 구성 요소입니다. 에이전트는 일반적으로 수명 주기가 설정 하 고 상태를 유지 합니다.  
  
 모든 에이전트에는 고유한 응용 프로그램 요구 사항이 있을 수 있습니다. 예를 들어 사용자 상호 작용 (검색 입력 또는 출력 표시)를 사용 하도록 설정 하는 에이전트에는 컴퓨팅 리소스에 더 높은 우선 순위 액세스가 필요할 수 있습니다. 스케줄러 정책을 스케줄러가 작업을 관리할 때 사용 하는 전략을 제어할 수 있습니다. 이 항목에는 특정 스케줄러 정책을 사용 하는 에이전트를 만드는 방법을 보여 줍니다.  
  
 비동기 메시지 블록 함께 사용자 지정 스케줄러 정책을 사용 하는 기본 예제를 보려면 [하는 방법: 특정 스케줄러 정책 지정](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)합니다.  
  
 비동기 에이전트 라이브러리, 에이전트, 메시지 블록 및 메시지 전달 함수 같은 작업을 수행 하도록 기능을 사용 하는이 항목입니다. 비동기 에이전트 라이브러리에 대 한 자세한 내용은 참조 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 개의 클래스에서 파생 되는 [concurrency:: agent](../../parallel/concrt/reference/agent-class.md): `permutor` 및 `printer`합니다. `permutor` 클래스는 지정 된 입력된 문자열의 모든 순열을 계산 합니다. `printer` 클래스 콘솔에 진행률 메시지를 인쇄 합니다. `permutor` 클래스 계산이 많은 작업을 수행 하면 모든 사용 가능한 컴퓨팅 리소스를 사용할 수도 있습니다. 유용 하 게는 `printer` 클래스 적절 한 시간 내에 각 진행률 메시지를 출력 해야 합니다.  
  
 제공 하는 `printer` 클래스 컴퓨팅 리소스에 상당한 액세스를 사용 하는이 예제에 설명 된 단계를 [하는 방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) 사용자 지정 정책이 적용 된 스케줄러 인스턴스를 만듭니다. 사용자 지정 정책 가장 높은 우선 순위 클래스로 스레드 우선 순위를 지정 합니다.  
  
 사용자 지정 정책이 적용 된 스케줄러를 사용 하는 이점을 보여 주기 위해이 예에서는 두 번 전체 작업을 수행 합니다. 이 예제에서는 먼저 기본 스케줄러를 사용 하 여 두 작업을 예약 합니다. 예약 하는 예에서는 다음 사용 하 여 기본 스케줄러는 `permutor` 개체 및 일정을 사용자 지정 정책을 포함 하는 스케줄러는 `printer` 개체입니다.  
  
 [!code-cpp[concrt-permute-strings#1](../../parallel/concrt/codesnippet/cpp/how-to-create-agents-that-use-specific-scheduler-policies_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
```Output  
With default scheduler:  
Computing all permutations of 'Grapefruit'...  
100% complete...  
 
With higher context priority:  
Computing all permutations of 'Grapefruit'...  
100% complete...  
```  
  
 하지만 동일한 결과 생성 하는 두 가지 작업, 사용자 지정 정책을 사용 하는 버전을 사용 하면는 `printer` 동작 반응성 하도록 높은 우선 순위에서 실행 하는 개체입니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `permute-strings.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc permute strings.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [스케줄러 정책](../../parallel/concrt/scheduler-policies.md)   
 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)   
 

