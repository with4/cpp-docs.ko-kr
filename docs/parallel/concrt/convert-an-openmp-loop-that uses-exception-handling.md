---
title: "방법: 동시성 런타임을 사용하기 위해 예외 처리를 사용하는 OpenMP 루프 변환 | Microsoft Docs"
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
  - "예외 처리, OpenMP에서 동시성 런타임으로 변환"
  - "OpenMP에서 동시성 런타임으로 변환, 예외 처리"
ms.assetid: 03c28196-21ba-439e-8641-afab1c283e1a
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 동시성 런타임을 사용하기 위해 예외 처리를 사용하는 OpenMP 루프 변환
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 예제에서는 동시성 런타임 예외 처리 메커니즘을 사용하도록 예외 처리를 수행하는 OpenMP [parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md) 루프를 변환하는 방법을 보여 줍니다.  
  
 OpenMP에서 병렬 영역에 throw되는 예외는 동일한 스레드에 의해 동일한 영역에서 catch 및 처리되어야 합니다.  병렬 영역을 벗어나는 예외는 처리되지 않은 예외 처리기에 의해 catch되어 기본적으로 프로세스가 종료됩니다.  
  
 동시성 런타임에서 [concurrency::task\_group](../Topic/task_group%20Class.md) 또는 [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md) 개체와 같은 작업\(task\) 그룹이나 [concurrency::parallel\_for](../Topic/parallel_for%20Function.md)와 같은 병렬 알고리즘에 전달하는 작업\(work\) 함수의 본문에서 예외를 throw하면 런타임에서 해당 예외를 저장하고 작업\(task\) 그룹이나 알고리즘이 끝날 때까지 기다리는 컨텍스트로 예외를 마샬링합니다.  작업 그룹의 경우 대기 중인 컨텍스트는 [concurrency::task\_group::wait](../Topic/task_group::wait%20Method.md), [concurrency::structured\_task\_group::wait](../Topic/structured_task_group::wait%20Method.md), [concurrency::task\_group::run\_and\_wait](../Topic/task_group::run_and_wait%20Method.md) 또는 [concurrency::structured\_task\_group::run\_and\_wait](../Topic/structured_task_group::run_and_wait%20Method.md)를 호출하는 컨텍스트입니다.  병렬 알고리즘의 경우 대기 중인 컨텍스트는 해당 알고리즘을 호출한 컨텍스트입니다.  또한 런타임에서는 자식 작업 그룹의 작업을 포함하여 작업 그룹에 있는 모든 활성 작업을 중지하고 아직 시작되지 않은 작업을 취소합니다.  
  
## 예제  
 이 예제에서는 OpenMP `parallel` 영역 및 `parallel_for`에 대한 호출에서 예외를 처리하는 방법을 보여 줍니다.  `do_work` 함수는 실패하는 메모리 할당 요청을 수행하므로 [std::bad\_alloc](../../standard-library/bad-alloc-class.md) 형식의 예외를 throw합니다.  OpenMP를 사용하는 버전에서 예외를 throw하는 스레드는 예외를 catch도 해야 합니다.  즉, OpenMP 병렬 루프의 각 반복에서 예외를 처리해야 합니다.  동시성 런타임을 사용하는 버전에서 기본 스레드는 다른 스레드에서 throw되는 예외를 catch해야 합니다.  
  
 [!code-cpp[concrt-openmp#3](../../parallel/concrt/codesnippet/CPP/convert-an-openmp-loop-that uses-exception-handling_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **OpenMP를 사용하여...**  
**'클래스 std::bad\_alloc' 형식의 오류가 발생 했습니다.**  
**'클래스 std::bad\_alloc' 형식의 오류가 발생 했습니다.**  
**'클래스 std::bad\_alloc' 형식의 오류가 발생 했습니다.**  
**'클래스 std::bad\_alloc' 형식의 오류가 발생 했습니다.**  
**'클래스 std::bad\_alloc' 형식의 오류가 발생 했습니다.**  
**'클래스 std::bad\_alloc' 형식의 오류가 발생 했습니다.**  
**'클래스 std::bad\_alloc' 형식의 오류가 발생 했습니다.**  
**'클래스 std::bad\_alloc' 형식의 오류가 발생 했습니다.**  
**'클래스 std::bad\_alloc' 형식의 오류가 발생 했습니다.**  
**'클래스 std::bad\_alloc' 형식의 오류가 발생 했습니다.**  
**\[동시성 런타임\] 사용**  
**'클래스 std::bad\_alloc' 형식의 오류가 발생 했습니다.** OpenMP를 사용하는 이 예제의 버전에서는 예외가 발생하고 이 예외는 각 루프 반복에 의해 처리됩니다.  동시성 런타임을 사용하는 버전에서 런타임은 예외를 저장하고, 모든 활성 작업을 중지하고, 아직 시작되지 않은 작업을 모두 무시하고, `parallel_for`를 호출하는 컨텍스트로 예외를 마샬링합니다.  
  
 예외가 발생한 후 OpenMP를 사용하는 버전을 종료해야 하는 경우 부울 플래그를 사용하여 오류가 발생한 다른 루프 반복에 알려야 합니다.  [방법: 동시성 런타임을 사용하기 위해 취소를 사용하는 OpenMP 루프 변환](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md) 항목의 예제에서와 같이 플래그가 설정되어 있는 경우 후속 루프 반복은 아무 작업도 수행하지 않습니다.  반대로, 예외가 발생한 후 동시성 런타임을 사용하는 루프가 계속되어야 하는 경우 병렬 루프 본문 자체에서 예외를 처리합니다.  
  
 동시성 런타임의 기타 구성 요소\(예: 비동기 에이전트 및 간단한 작업\)에서는 예외를 전송하지 않습니다.  대신 처리되지 않은 예외가 처리되지 않은 예외 처리기에 의해 catch되어 기본적으로 프로세스가 종료됩니다.  예외 처리에 대한 자세한 내용은 [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)를 참조하십시오.  
  
 `parallel_for` 및 기타 병렬 알고리즘에 대한 자세한 내용은 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)을 참조하십시오.  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트 또는 `concrt-omp-exceptions.cpp` 파일에 붙여 넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-exceptions.cpp**  
  
## 참고 항목  
 [OpenMP에서 동시성 런타임으로 마이그레이션](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)