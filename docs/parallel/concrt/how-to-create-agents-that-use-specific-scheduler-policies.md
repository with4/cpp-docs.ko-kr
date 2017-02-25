---
title: "방법: 특정 스케줄러 정책을 사용하는 에이전트 만들기 | Microsoft Docs"
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
  - "스케줄러 정책, 에이전트[동시성 런타임]"
  - "특정 정책을 사용하는 에이전트 만들기[동시성 런타임]"
ms.assetid: 46a3e265-0777-4ec3-a142-967bafc49d67
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 방법: 특정 스케줄러 정책을 사용하는 에이전트 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

에이전트는 규모가 큰 컴퓨팅 작업을 해결하기 위해 다른 구성 요소와 함께 비동기적으로 동작하는 응용 프로그램 구성 요소입니다.  일반적으로 에이전트는 수명 주기가 설정되어 있으며 상태를 유지 관리합니다.  
  
 모든 에이전트에는 고유한 응용 프로그램 요구 사항이 있을 수 있습니다.  예를 들어 입력을 가져오거나 출력을 표시하는 등의 사용자 상호 작용이 가능한 에이전트의 경우 컴퓨팅 리소스에 대한 액세스 우선 순위가 높아야 할 수 있습니다.  스케줄러 정책을 사용하면 스케줄러가 작업을 관리할 때 사용하는 전략을 제어할 수 있습니다.  이 항목에서는 특정 스케줄러 정책을 사용하는 에이전트를 만드는 방법을 보여 줍니다.  
  
 비동기 메시지 블록과 함께 사용자 지정 스케줄러 정책을 사용하는 기본 예제를 보려면 [방법: 특정 스케줄러 정책 지정](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)을 참조하십시오.  
  
 이 항목에서는 에이전트, 메시지 블록 및 메시지 전달 함수와 같은 비동기 에이전트 라이브러리의 기능을 사용하여 작업을 수행합니다.  비동기 에이전트 라이브러리에 대한 자세한 내용은 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 [concurrency::agent](../../parallel/concrt/reference/agent-class.md)에서 파생되는 두 클래스, 즉 `permutor`와 `printer`를 정의합니다.  `permutor` 클래스는 지정된 입력 문자열의 모든 순열을 계산합니다.  `printer` 클래스는 진행 메시지를 콘솔에 출력합니다.  `permutor` 클래스는 계산을 많이 하는 작업을 수행하므로 사용 가능한 컴퓨팅 리소스를 모두 사용할 수도 있습니다.  따라서 `printer` 클래스는 적시에 각 진행 메시지를 출력해야 합니다.  
  
 이 예제에서는 `printer` 클래스가 컴퓨팅 리소스에 공평하게 액세스할 수 있도록 하기 위해 [방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)에 설명된 단계를 사용하여 사용자 지정 정책을 포함하는 스케줄러 인스턴스를 만듭니다.  사용자 지정 정책은 스레드 우선 순위가 최고 우선 순위 클래스가 되도록 지정합니다.  
  
 사용자 지정 정책을 포함하는 스케줄러를 사용할 경우의 이점을 나타내기 위해 이 예제에서는 전체 작업을 두 번 수행합니다.  이 예제에서는 먼저 기본 스케줄러를 사용하여 두 작업을 예약합니다.  그런 다음 기본 스케줄러를 사용하여 `permutor` 개체를 예약하고, 사용자 지정 정책을 포함하는 스케줄러를 사용하여 `printer` 개체를 예약합니다.  
  
 [!code-cpp[concrt-permute-strings#1](../../parallel/concrt/codesnippet/CPP/how-to-create-agents-that-use-specific-scheduler-policies_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **기본 스케줄러와 함께:**  
**모든 순열의 'Grapefruit' 컴퓨팅...**  
**100% 완료...**  
**우선 순위가 높은 컨텍스트:**  
**모든 순열의 'Grapefruit' 컴퓨팅...**  
**100% 완료...** 두 작업 모두 결과는 같지만 사용자 지정 정책을 사용하는 버전의 경우 `printer` 개체를 높은 우선 순위에서 실행할 수 있으므로 개체의 동작 반응성이 향상됩니다.  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `permute-strings.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc permute\-strings.cpp**  
  
## 참고 항목  
 [스케줄러 정책](../../parallel/concrt/scheduler-policies.md)   
 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)   
 