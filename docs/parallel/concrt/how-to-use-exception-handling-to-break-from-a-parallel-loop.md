---
title: "방법: 예외 처리를 사용하여 병렬 루프 중단 | Microsoft Docs"
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
  - "검색 알고리즘, 작성[동시성 런타임]"
  - "검색 알고리즘 작성[동시성 런타임]"
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
caps.latest.revision: 15
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 예외 처리를 사용하여 병렬 루프 중단
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 기본 트리 구조에 대한 검색 알고리즘을 작성하는 방법을 보여 줍니다.  
  
 [취소](../../parallel/concrt/cancellation-in-the-ppl.md) 항목에서는 병렬 패턴 라이브러리에서 취소의 역할에 대해 설명합니다.  병렬 작업을 취소할 때 예외 처리를 사용하는 것이 [concurrency::task\_group::cancel](../Topic/task_group::cancel%20Method.md) 및 [concurrency::structured\_task\_group::cancel](../Topic/structured_task_group::cancel%20Method.md) 메서드를 사용하는 것보다 효율성이 떨어지는 방법입니다.  그러나 작업\(task\) 또는 병렬 알고리즘을 사용하지만 취소할 `task_group` 또는 `structured_task_group` 개체를 제공하지 않는 타사 라이브러리를 호출하는 경우에는 예외 처리를 사용하여 작업\(work\)을 취소하는 것이 적절합니다.  
  
## 예제  
 다음 예제에서는 데이터 요소 및 자식 노드 목록을 포함하는 기본 `tree` 형식을 보여 줍니다.  다음 섹션에서는 각 자식 노드에서 작업 함수를 재귀적으로 수행하는 `for_all` 메서드 본문을 보여 줍니다.  
  
 [!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/CPP/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]  
  
## 예제  
 다음 예제에서는 `for_all` 메서드를 보여 줍니다.  이 예제에서는 [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) 알고리즘을 사용하여 트리의 각 노드에 대해 작업 함수를 병렬로 수행합니다.  
  
 [!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/CPP/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]  
  
## 예제  
 다음 예제에서는 제공된 `tree` 개체에서 값을 검색하는 `search_for_value` 함수를 보여 줍니다.  이 함수는 제공된 값을 포함하는 트리 노드를 발견하면 throw하는 작업 함수를 `for_all` 메서드에 전달합니다.  
  
 타사 라이브러리에서 `tree` 클래스가 제공되고 이 클래스를 수정할 수 없다고 가정합니다.  이 경우에는 `for_all` 메서드가 `task_group` 또는 `structured_task_group` 개체를 호출자에게 제공하지 않으므로 예외 처리를 사용하는 것이 적절합니다.  따라서 작업 함수에서 부모 작업 그룹을 직접 취소할 수 없습니다.  
  
 작업 그룹에 제공하는 작업 함수에서 예외를 throw하면 런타임에서 자식 작업 그룹을 포함하여 작업 그룹에 있는 모든 작업을 중지하고 아직 시작되지 않은 작업을 취소합니다.  `search_for_value` 함수는 `try`\-`catch` 블록을 사용하여 예외를 캡처하고 결과를 콘솔에 출력합니다.  
  
 [!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/CPP/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]  
  
## 예제  
 다음 예제에서는 `tree` 개체를 만들고 이 개체에서 여러 값을 동시에 검색합니다.  `build_tree` 함수는 이 항목의 뒷부분에 나옵니다.  
  
 [!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/CPP/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]  
  
 이 예제에서는 [concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md) 알고리즘을 사용하여 값을 병렬로 검색합니다.  이 알고리즘에 대한 자세한 내용은 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)을 참조하십시오.  
  
## 예제  
 다음 전체 예제에서는 예외 처리를 사용하여 기본 트리 구조에서 여러 값을 검색합니다.  
  
 [!code-cpp[concrt-task-tree-search#5](../../parallel/concrt/codesnippet/CPP/how-to-use-exception-handling-to-break-from-a-parallel-loop_5.cpp)]  
  
 이 예제를 실행하면 다음과 같은 샘플 결과가 출력됩니다.  
  
  **32614 값을 가진 노드를 찾았습니다.**  
**86131 값을 가진 노드를 찾았습니다.**  
**17522 값을 가진 노드를 찾을 수 없습니다.**   
## 코드 컴파일  
 예제 코드를 복사하여  Visual Studio 프로젝트 또는 `task-tree-search.cpp` 파일에 붙여넣고 Visual Studio  명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc task\-tree\-search.cpp**  
  
## 참고 항목  
 [취소](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [task\_group 클래스](../Topic/task_group%20Class.md)   
 [structured\_task\_group 클래스](../../parallel/concrt/reference/structured-task-group-class.md)   
 [parallel\_for\_each 함수](../Topic/parallel_for_each%20Function.md)