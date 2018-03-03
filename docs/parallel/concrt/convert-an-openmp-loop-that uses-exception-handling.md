---
title: "방법: 동시성 런타임을 사용 하기 위해 예외 처리를 사용 하는 OpenMP 루프 변환 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- exception handling, converting from OpenMP to the Concurrency Runtime
- converting from OpenMP to the Concurrency Runtime, exception handling
ms.assetid: 03c28196-21ba-439e-8641-afab1c283e1a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d2964c629ce8a3a83799278ac822b589992b4995
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-an-openmp-loop-that-uses-exception-handling-to-use-the-concurrency-runtime"></a>방법: 동시성 런타임을 사용하기 위해 예외 처리를 사용하는 OpenMP 루프 변환
OpenMP 변환 하는 방법을 보여 주는이 예제 [병렬](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[에 대 한](../../parallel/openmp/reference/for-openmp.md) 동시성 런타임에서 예외 처리 메커니즘을 사용 하는 예외 처리를 수행 하는 루프입니다.  
  
 Openmp에서는 병렬 영역에서 throw 되는 예외 해야 찾아서 처리할 동일한 지역에 동일한 스레드에서 합니다. 병렬 영역을 벗어나는 하는 예외는 기본적으로 프로세스를 종료 하는 처리 되지 않은 예외 처리기에 의해 발견 되었습니다.  
  

 와 같은 작업 그룹에 전달 하는 작업 함수의 본문에서 예외를 throw 하는 경우 동시성 런타임에서 [concurrency:: task_group](reference/task-group-class.md) 또는 [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) 개체 또는 와 같은 병렬 알고리즘에 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for), 런타임에서 해당 예외를 저장 하 고 작업 그룹 또는 끝나기를 알고리즘에 대 한 대기 하는 컨텍스트에 마샬링합니다. 작업 그룹에 대 한 대기 중인 컨텍스트는 호출 하는 컨텍스트로 [concurrency::task_group::wait](reference/task-group-class.md#wait), [concurrency::structured_task_group::wait](reference/structured-task-group-class.md#wait), [concurrency::task_group::run_and _wait](reference/task-group-class.md#run_and_wait), 또는 [concurrency::structured_task_group::run_and_wait](reference/structured-task-group-class.md#run_and_wait)합니다. 병렬 알고리즘에 대 한 대기 중인 컨텍스트는 해당 알고리즘을 호출한 컨텍스트입니다. 런타임에서 또한 자식 작업 그룹을 포함 하는 작업 그룹에 있는 모든 활성 작업을 중지 하 고 아직 시작 되지 않은 모든 작업 무시 합니다.  


  
## <a name="example"></a>예  
 OpenMP에서 예외를 처리 하는 방법을 보여 주는이 예제 `parallel` 영역에 대 한 호출에서 `parallel_for`합니다. `do_work` 성공 하지 못하고 따라서 형식의 예외를 throw 하는 메모리 할당 요청을 수행 하는 함수 [std:: bad_alloc](../../standard-library/bad-alloc-class.md)합니다. OpenMP를 사용 하는 버전에서 예외를 throw 하는 스레드도 catch 해야 것입니다. 즉, OpenMP 병렬 루프의 각 반복 예외를 처리 해야 합니다. 동시성 런타임을 사용 하는 버전, 주 스레드가 다른 스레드에서 throw 되는 예외를 catch 합니다.  
  
 [!code-cpp[concrt-openmp#3](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that uses-exception-handling_1.cpp)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
```Output  
Using OpenMP...  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
Using the Concurrency Runtime...  
An error of type 'class std::bad_alloc' occurred.  
```  
  
 OpenMP를 사용 하 여이 예제의 버전에서는 예외가에서 발생 하 고 각 루프 반복에 의해 처리 됩니다. 동시성 런타임을 사용 하는 버전에서는 런타임 예외를 저장, 모든 활성 작업을 중지, 작업을 시작 하 고, 아직 처리 하지 않은 취소 및 예외를 호출 하는 컨텍스트에 마샬링합니다 `parallel_for`합니다.  
  
 OpenMP를 사용 하는 버전 예외가 발생 한 후 종료는 필요한 경우 오류가 발생 한 다른 루프 반복에 신호를 부울 플래그를 사용할 수 있습니다. 항목의 예제에서와 같이 [하는 방법: 동시성 런타임을 사용 하기 위해 사용 하 여 취소 하는 OpenMP 루프 변환](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md), 후속 루프 반복은 플래그가 설정 된 경우 아무 작업도 수행 합니다. 반대로, 동시성 런타임을 사용 하는 루프에서 예외 발생 후 계속 되도록 필요한 경우 병렬 루프 본문 자체에서 예외를 처리 합니다.  
  
 비동기 에이전트 및 간단한 작업 같은 동시성 런타임을의 다른 구성 요소에서 예외를 전송할 하지 않습니다. 대신, 기본적으로 프로세스를 종료 하는 처리 되지 않은 예외 처리기에 의해 처리 되지 않은 예외가 발생 합니다. 예외 처리에 대 한 자세한 내용은 참조 [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)합니다.  
  
 에 대 한 자세한 내용은 `parallel_for` 오류 코드 및 기타 병렬 알고리즘을 참조 하십시오. [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `concrt-omp-exceptions.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc /openmp concrt-omp-exceptions.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [OpenMP에서 동시성 런타임으로 마이그레이션](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)

