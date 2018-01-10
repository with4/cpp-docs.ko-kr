---
title: "방법: 예외 처리를 중단 병렬 루프에서 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- search algorithm, writing [Concurrency Runtime]
- writing a search algorithm [Concurrency Runtime]
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 29140c339614e572733988bd7ca5e14561cee5dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-exception-handling-to-break-from-a-parallel-loop"></a>방법: 예외 처리를 사용하여 병렬 루프 중단
이 항목에서는 기본적인 트리 구조에 대 한 검색 알고리즘을 작성 하는 방법을 보여 줍니다.  
  
 항목 [취소](cancellation-in-the-ppl.md) 병렬 패턴 라이브러리에서 취소의 역할에 설명 합니다. 예외 처리 사용은 덜 효율적인 방법 사용 보다 병렬 작업을 취소 하는 [concurrency::task_group::cancel](reference/task-group-class.md#cancel) 및 [concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) 메서드. 그러나 작업을 취소 하는 예외 처리 사용 하 여 적절 한 가지 시나리오는 작업 또는 병렬 알고리즘을 사용 하 여 하지만 제공 하지 않습니다는 타사 라이브러리를 호출 하는 경우는 `task_group` 또는 `structured_task_group` 취소 하는 개체입니다.  

  
## <a name="example"></a>예  
 다음 예제에서는 기본 `tree` 데이터 요소 및 자식 노드 목록이 포함 된 형식입니다. 다음 단원에서는의 본문은 `for_all` 메서드, 각 자식 노드에서 작업 함수를 재귀적으로 수행 합니다.  
  
 [!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]  
  
## <a name="example"></a>예  
 다음 예제와 `for_all` 메서드. 사용 하 여는 [concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) 병렬로 트리의 각 노드에 작업 함수를 수행 하는 알고리즘이 있습니다.  
  
 [!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]  
  
## <a name="example"></a>예  
 다음 예제에서는 제공된 `tree` 개체에서 값을 검색하는 `search_for_value` 함수를 보여 줍니다. 이 함수에 전달 된 `for_all` 메서드는 제공 된 값이 포함 된 트리 노드를 발견 한 경우 throw 하는 작업 함수입니다.  
  
 가정은 `tree` 클래스는 타사 라이브러리에서 제공 되 고 수정할 수 없습니다. 이 경우 예외 처리를 사용 하는 적절 한 때문에 `for_all` 방법은 제공 하지 않습니다는 `task_group` 또는 `structured_task_group` 호출자에 게 개체입니다. 따라서, 작업 함수를 직접 부모 작업 그룹을 취소할 수 하지 않습니다.  
  
 작업 그룹에 제공 하는 작업 함수에서 예외를 throw 하는 경우 런타임에서 (자식 작업 그룹 포함) 작업 그룹에 있는 모든 작업을 중지 하 고 아직 시작 되지 않은 모든 작업을 무시 합니다. `search_for_value` 함수는 한 `try` - `catch` 블록을 예외를 캡처하고 결과를 콘솔에 출력 합니다.  
  
 [!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]  
  
## <a name="example"></a>예  
 다음 예제에서는 한 `tree` 개체를 동시에 여러 값을 검색 합니다. `build_tree` 함수는이 항목의 뒷부분에 표시 됩니다.  
  
 [!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]  
  
 사용 하 여이 예제는 [concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) 알고리즘을 병렬 값을 검색 합니다. 이 알고리즘에 대 한 자세한 내용은 참조 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.  
  
## <a name="example"></a>예  
 다음 전체 예제에서는 예외 처리를 사용 하 여 기본적인 트리 구조에서 값을 검색 하려면.  
  
 [!code-cpp[concrt-task-tree-search#5](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_5.cpp)]  
  
 이 예제는 다음과 같은 샘플 출력을 생성합니다.  
  
```Output  
Found a node with value 32614.  
Found a node with value 86131.  
Did not find node with value 17522.  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `task-tree-search.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc 작업-트리-search.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [PPL에서의 취소](cancellation-in-the-ppl.md)   
 [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [task_group 클래스](reference/task-group-class.md)   
 [structured_task_group 클래스](../../parallel/concrt/reference/structured-task-group-class.md)   
 [parallel_for_each 함수](reference/concurrency-namespace-functions.md#parallel_for_each)


