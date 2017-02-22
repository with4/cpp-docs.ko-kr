---
title: "방법: 특정 Scheduler 정책 지정 | Microsoft Docs"
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
  - "스케줄러 정책 지정[동시성 런타임]"
  - "스케줄러 정책, 지정[동시성 런타임]"
ms.assetid: 9c5149f9-ac34-4ff3-9e79-0bad103e4e6b
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# 방법: 특정 Scheduler 정책 지정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스케줄러 정책에는 스케줄러에서 작업을 관리할 때을 사용 하는 전략을 제어할 수 있습니다. 이 항목에는 진행률 표시기는 콘솔에 출력 하는 작업의 스레드 우선 순위를 높이 스케줄러 정책을 사용 하는 방법을 보여 줍니다.  
  
 비동기 에이전트와 함께 사용자 지정 스케줄러 정책을 사용 하는 예제를 보려면 [하는 방법: 에이전트를 사용 하 여 특정 스케줄러 정책 만들기](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 동시에 두 가지 작업을 수행 합니다. N을 계산 하는 첫 번째 작업<sup>th</sup> 피보나치 수 있습니다. 두 번째 태스크는 진행률 표시기는 콘솔에 인쇄합니다.  
  
 첫 번째 작업 재귀적 분해를 사용 하 여 피보나치 수를 계산 합니다. 즉, 각 작업 재귀적으로 전체 결과 계산 하는 데 하위 작업을 만듭니다. 재귀적 분해를 사용 하는 작업은 사용 가능한 모든 리소스를 사용 하 여 수도 있으며 함으로써 다른 작업을 이용할 수 있습니다. 이 예제에서는 작업의 진행률 표시기를 출력 하는 컴퓨팅 리소스에 대 한 시기 적절 한 액세스를 받지 못할 수 있습니다.  
  
 이 예제에서는 컴퓨팅 리소스에는 진행률 메시지 공정 하 게 액세스를 출력 하는 작업을 제공 하려면에 설명 된 단계를 사용 [하는 방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) 사용자 지정 정책을 포함 하는 스케줄러 인스턴스를 만듭니다. 사용자 지정 정책을 가장 높은 우선 순위 클래스를 스레드 우선 순위를 지정 합니다.  
  
 사용 하 여이 예제는 [concurrency:: call](../../parallel/concrt/reference/call-class.md) 및 [concurrency:: timer](../../parallel/concrt/reference/timer-class.md) 진행률 표시기를 인쇄 하는 클래스입니다. 이러한 클래스에 대 한 참조를 사용 하는 생성자의 버전에는 한 [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 해당 일정을 예약 하는 개체입니다. 기본 스케줄러를 사용 하 여 피보나치 수를 계산 하는 진행률 표시기를 출력 하는 작업을 예약 하려면 스케줄러 인스턴스 작업을 예약 하는 예제입니다.  
  
 를 설명 하기 위해 사용자 지정 정책을 포함 하는 스케줄러를 사용 하는 이점을이 예제에서는 두 번 전체 작업을 수행 합니다. 예제에서는 먼저 기본 스케줄러를 사용 하 여 두 작업을 예약 합니다. 다음 예제에서는 첫 번째 작업을 예약 하려면 기본 스케줄러 및 사용자 지정 정책을 두 번째 작업을 예약 하는 스케줄러를 사용 하 여 합니다.  
  
 [!code-cpp[concrt-scheduler-policy#1](../../parallel/concrt/codesnippet/CPP/how-to-specify-specific-scheduler-policies_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
```Output  
Default scheduler:  
...........................................................................done  
Scheduler that has a custom policy:  
...........................................................................done  
```  
  
 하지만 작업 집합이 모두 동일한 결과 생성, 사용자 지정 정책을 사용 하는 버전을 실행 하려면 높은 우선 순위에 동작 반응성 진행률 표시기를 출력 하는 작업이 있습니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `scheduler-policy.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc 스케줄러 policy.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [스케줄러 정책](../../parallel/concrt/scheduler-policies.md)   
 [방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)   
 [방법: 특정 스케줄러 정책을 사용 하는 에이전트 만들기](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)

