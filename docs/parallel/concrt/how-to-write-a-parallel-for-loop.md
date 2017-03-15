---
title: "방법: parallel_for 루프 작성 | Microsoft Docs"
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
  - "parallel_for 루프 작성[동시성 런타임]"
  - "parallel_for 함수, 예제"
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# 방법: parallel_for 루프 작성
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 예제에서는 [concurrency::parallel\_for](../Topic/parallel_for%20Function.md)를 사용하여 두 매트릭스의 곱을 계산하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 두 정방 매트릭스의 곱을 계산하는 `matrix_multiply` 함수를 보여 줍니다.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#1](../../parallel/concrt/codesnippet/CPP/how-to-write-a-parallel-for-loop_1.cpp)]  
  
## 예제  
 다음 예제에서는 `parallel_for` 알고리즘을 사용하여 외부 루프를 병렬로 수행하는 `parallel_matrix_multiply` 함수를 보여 줍니다.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#2](../../parallel/concrt/codesnippet/CPP/how-to-write-a-parallel-for-loop_2.cpp)]  
  
 이 예제에서는 외부 루프에서 수행하는 작업의 양이 충분하여 병렬 처리의 오버헤드로부터 이점을 얻을 수 있으므로 외부 루프만 병렬화합니다.  내부 루프를 병렬화할 경우에는 병렬 처리의 오버헤드보다 내부 루프에서 수행하는 작업의 양이 적다는 것이 더 문제가 되므로 성능상의 이점을 얻을 수 없습니다.  따라서 대부분의 시스템에서 동시성의 이점을 최대화하려면 외부 루프만 병렬화하는 것이 가장 좋은 방법입니다.  
  
## 예제  
 다음에 나오는 더 자세한 예제에서는 `matrix_multiply` 함수와 `parallel_matrix_multiply` 함수의 성능을 비교합니다.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#3](../../parallel/concrt/codesnippet/CPP/how-to-write-a-parallel-for-loop_3.cpp)]  
  
 다음 샘플은 프로세서가 4개인 컴퓨터에 대한 출력입니다.  
  
  **직렬: 3853**  
**parallel: 1311**   
## 코드 컴파일  
 코드를 컴파일하려면 코드를 복사한 다음, Visual Studio 프로젝트 또는 `parallel-matrix-multiply.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc parallel\-matrix\-multiply.cpp**  
  
## 참고 항목  
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [parallel\_for 함수](../Topic/parallel_for%20Function.md)