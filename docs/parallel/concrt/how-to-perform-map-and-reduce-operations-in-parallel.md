---
title: "방법: 매핑 수행 및 병렬 작업 줄이기 | Microsoft Docs"
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
  - "parallel_transform 함수, 예:"
  - "병렬 매핑 및 줄이기, 예제"
  - "parallel_reduce 함수, 예:"
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 방법: 매핑 수행 및 병렬 작업 줄이기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용 하는 방법을 보여 주는이 예제는 [concurrency:: parallel_transform](../Topic/parallel_transform%20Function.md) 및 [concurrency:: parallel_reduce](../Topic/parallel_reduce%20Function.md) 알고리즘 및 [concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) 파일에서 단어의 개수를 클래스입니다.  
  
 A *맵* 작업 시퀀스의 각 값에 함수를 적용 합니다. A *줄일* 작업 하나의 값으로 시퀀스의 요소를 결합 합니다. 표준 템플릿 라이브러리 (STL)를 사용할 수 있습니다 [std:: transform](../Topic/transform.md)[std:: accumulate](../Topic/accumulate.md) 매핑 수행 및 감소 작업을 하는 클래스입니다. 그러나 많은 문제에 대해 성능을 향상시키기 위해 `parallel_transform` 알고리즘을 사용하여 매핑 작업을 병렬로 수행하고, `parallel_reduce` 알고리즘을 사용하여 줄이기 작업을 병렬로 수행할 수 있습니다. 경우에 따라 `concurrent_unordered_map`을 사용하여 매핑과 줄이기를 하나의 작업으로 수행할 수도 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 파일에서 단어가 나타나는 횟수를 계산합니다. 사용 하 여 [std:: vector](../../standard-library/vector-class.md) 두 파일의 내용을 나타내는 데 있습니다. 매핑 작업은 각 벡터에서 각 단어가 나타나는 횟수를 계산합니다. 줄이기 작업은 두 벡터의 단어 개수를 누적합니다.  
  
 [!code-cpp[concrt-parallel-map-reduce#1](../../parallel/concrt/codesnippet/CPP/how-to-perform-map-and-reduce-operations-in-parallel_1.cpp)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 코드를 컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 하거나 라는 파일에 붙여 `parallel-map-reduce.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc 병렬-맵-reduce.cpp**  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 이 예제에서는 concurrent_unordered_map.h에서 정의된 `concurrent_unordered_map` 클래스를 사용하여 매핑과 줄이기를 하나의 작업으로 수행할 수 있습니다.  
  
 [!code-cpp[concrt-parallel-map-reduce#2](../../parallel/concrt/codesnippet/CPP/how-to-perform-map-and-reduce-operations-in-parallel_2.cpp)]  
  
 일반적으로 외부 또는 내부 루프만 평행화합니다. 비교적 적은 파일이 있고 각 파일이 많은 단어를 포함하는 경우 내부 루프를 평행화합니다. 비교적 많은 파일이 있고 각 파일이 적은 단어를 포함하는 경우 외부 루프를 평행화합니다.  
  
## <a name="see-also"></a>참고 항목  
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [parallel_transform 함수](../Topic/parallel_transform%20Function.md)   
 [parallel_reduce 함수](../Topic/parallel_reduce%20Function.md)   
 [concurrent_unordered_map 클래스](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
