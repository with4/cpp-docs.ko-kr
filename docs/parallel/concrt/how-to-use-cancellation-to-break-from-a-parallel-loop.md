---
title: "방법: 취소를 사용하여 병렬 루프 중단 | Microsoft Docs"
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
  - "병렬 검색 알고리즘, 작성[동시성 런타임]"
  - "병렬 검색 알고리즘 작성[동시성 런타임]"
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# 방법: 취소를 사용하여 병렬 루프 중단
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 예제에서는 취소를 사용하여 기본 병렬 검색 알고리즘을 구현하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 취소를 사용하여 배열에서 요소를 검색합니다.  `parallel_find_any` 함수는 [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) 알고리즘과 [concurrency::structured\_task\_group](../Topic/run_with_cancellation_token%20Function.md) 함수를 사용하여 지정된 값을 포함하는 위치를 검색합니다.  병렬 루프에서 값을 찾을 때, [concurrency::cancellation\_token\_source::cancel](../Topic/cancellation_token_source::cancel%20Method.md) 메서드를 호출해  이후의 작업을 취소합니다.  
  
 [!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/CPP/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]  
  
 [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) 알고리즘은 동시에 동작합니다.  따라서 미리 결정된 순서대로 작업을 수행하지 않습니다.  지정된 값의 인스턴스가 배열에 여러 개 포함되어 있으면 결과는 해당 위치 중 하나가 될 수 있습니다.  
  
## 코드 컴파일  
 예제 코드를 복사하여  Visual Studio 프로젝트 또는 `parallel-array-search.cpp` 파일에 붙여넣고  Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 **cl.exe \/EHsc parallel\-array\-search.cpp**  
  
## 참고 항목  
 [취소](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [parallel\_for 함수](../Topic/parallel_for%20Function.md)   
 [cancellation\_token\_source 클래스](../../parallel/concrt/reference/cancellation-token-source-class.md)