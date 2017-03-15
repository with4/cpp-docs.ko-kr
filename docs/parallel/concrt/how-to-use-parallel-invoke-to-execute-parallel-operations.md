---
title: "방법: parallel_invoke를 사용하여 병렬 작업 실행 | Microsoft Docs"
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
  - "parallel_invoke 함수, 예제"
  - "여러 함수를 병렬로 호출[동시성 런타임]"
ms.assetid: a6aea69b-d647-4b7e-bf3b-e6a6a9880072
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# 방법: parallel_invoke를 사용하여 병렬 작업 실행
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 예제에서는 [concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md) 알고리즘을 사용하여 공유 데이터 소스에 대해 여러 작업을 수행하는 프로그램의 성능을 향상시키는 방법을 보여 줍니다.  어느 작업도 소스를 수정하지는 않으므로 간단한 방법으로 작업을 병렬로 실행할 수 있습니다.  
  
## 예제  
 `MyDataType` 형식의 변수를 만들고 함수를 호출하여 해당 변수를 초기화한 다음 해당 데이터에 대해 여러 개의 긴 작업을 수행하는 다음 코드 예제를 살펴봅니다.  
  
 [!code-cpp[concrt-parallel-word-mining#1](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-execute-parallel-operations_1.cpp)]  
  
 `lengthy_operation1`, `lengthy_operation2` 및 `lengthy_operation3` 함수가 `MyDataType` 변수를 수정하지 않는 경우 이러한 함수를 추가로 수정하지 않고 병렬로 실행할 수 있습니다.  
  
## 예제  
 다음 예제에서는 이전 예제를 병렬로 실행하도록 수정합니다.  `parallel_invoke` 알고리즘은 각 작업을 병렬로 실행하고 모든 작업이 끝난 후 반환됩니다.  
  
 [!code-cpp[concrt-parallel-word-mining#2](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-execute-parallel-operations_2.cpp)]  
  
## 예제  
 다음 예제에서는 gutenberg.org의 Homer가 만든 *The Iliad*를 다운로드하고 해당 파일에 대해 여러 작업을 수행합니다.  이 예제에서는 먼저 이러한 작업을 연속으로 수행한 다음 동일한 작업을 병렬로 수행합니다.  
  
 [!code-cpp[concrt-parallel-word-mining#3](../../parallel/concrt/codesnippet/CPP/how-to-use-parallel-invoke-to-execute-parallel-operations_3.cpp)]  
  
 이 예제를 실행하면 다음과 같은 샘플 결과가 출력됩니다.  
  
  **'The Iliad' 다운로드....**  
**직렬 버전을 실행 하는 중... 953 ms 걸렸습니다.**  
**병렬 버전을 실행 하는 중... 656 ms 걸렸습니다.**  
**가장 일반적인 단어를 5 개 이상의 문자는 다음과 같습니다.**  
 **their \(953\)**  
 **shall \(444\)**  
 **which \(431\)**  
 **great \(398\)**  
 **Hector \(349\)**  
 **Achilles \(309\)**  
 **through \(301\)**  
 **these \(268\)**  
 **chief \(259\)**  
**같은 첫 번째 문자는 단어의 긴 시퀀스입니다.**  
 **tented에 tempest를 통해**  
**다음 감사 텍스트에 표시 됩니다.**  
 **반점 중지**  
 **속도 깊이**  
 **매끄러운 추락** 이 예제에서는 `parallel_invoke` 알고리즘을 사용하여 동일한 데이터 소스에 대해 동작하는 여러 함수를 호출합니다.  `parallel_invoke` 알고리즘을 사용하여 동일한 데이터에 대해 동작하는 함수뿐 아니라 임의의 함수 집합을 병렬로 호출할 수 있습니다.  
  
 `parallel_invoke` 알고리즘은 각 작업 함수를 병렬로 호출하므로 완료하는 데 가장 오랜 시간이 소요되는 함수에 의해 성능이 정해집니다. 즉, 런타임에서는 각 함수를 별도의 프로세서에서 처리합니다.  이 예제에서 사용 가능한 프로세서 수보다 많은 작업을 병렬로 수행하는 경우 각 프로세서에서 여러 작업을 실행할 수 있습니다.  이 경우에는 완료하는 데 가장 오랜 시간이 소요되는 작업 그룹에 의해 성능이 정해집니다.  
  
 이 예제에서는 세 개의 작업을 병렬로 수행하기 때문에 프로세서가 세 개를 초과하는 컴퓨터에서는 성능이 향상되지 않습니다.  성능을 향상시키기 위해서는 최장 실행 작업을 작은 작업으로 분할한 다음 해당 작업을 병렬로 실행하면 됩니다.  
  
 취소에 대한 지원이 필요하지 않은 경우에는 [concurrency::task\_group](../Topic/task_group%20Class.md) 및 [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md) 클래스 대신 `parallel_invoke` 알고리즘을 사용할 수 있습니다.  `parallel_invoke` 알고리즘과 작업 그룹의 사용법을 비교하는 예제를 보려면 [방법: parallel\_invoke를 사용하여 병렬 정렬 루틴 작성](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)을 참조하십시오.  
  
## 코드 컴파일  
 코드를 컴파일하려면 해당 코드를 복사하여 Visual Studio 프로젝트 또는 `parallel-word-mining.cpp` 파일에 붙여 넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc \/MD \/DUNICODE \/D\_AFXDLL parallel\-word\-mining.cpp**  
  
## 참고 항목  
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [parallel\_invoke 함수](../Topic/parallel_invoke%20Function.md)