---
title: '방법: Alloc 사용 및 사용 가능한 메모리 성능을 향상 시키는 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Alloc and Free, using [Concurrency Runtime]
- Using Alloc and Free [Concurrency Runtime]
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0be6fa309975663126331a7e38be0f2bea7dcf17
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-alloc-and-free-to-improve-memory-performance"></a>방법: Alloc 및 Free를 사용하여 메모리 성능 개선

이 문서에서는 사용 하는 [concurrency:: alloc](reference/concurrency-namespace-functions.md#alloc) 및 [concurrency:: free](reference/concurrency-namespace-functions.md#free) 메모리 성능을 향상 시키는 기능. 비교 해야 하는 세 가지 다른 형식에 대 한 병렬에서 배열 요소를 반대로 하는 시간 지정 각는 `new` 및 `delete` 연산자입니다.  

  
 `Alloc` 및 `Free` 함수는 둘 다는 여러 스레드 자주 호출할 때 가장 유용 `Alloc` 및 `Free`합니다. 런타임은 각 스레드에;에 대 한 별도 메모리 캐시를 보유합니다. 따라서 런타임에 잠금 또는 메모리 장벽을 사용 하지 않고 메모리를 관리합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 각각 지정 하는 세 가지 종류의 `new` 및 `delete` 연산자입니다. `new_delete` 클래스를 사용 하 여 전역 `new` 및 `delete` 연산자는 `malloc_free` 클래스 C 런타임을 사용 하 여 [malloc](../../c-runtime-library/reference/malloc.md) 및 [무료](../../c-runtime-library/reference/free.md) 함수 및 `Alloc_Free` 클래스는 동시성 런타임을 사용 하 여 `Alloc` 및 `Free` 함수입니다.  
  
 [!code-cpp[concrt-allocators#1](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_1.cpp)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `swap` 및 `reverse_array` 함수를 보여 줍니다. `swap` 함수 배열에서 지정된 된 인덱스의 내용을 교환 합니다. 임시 변수의 힙에서 메모리를 할당합니다. `reverse_array` 함수 대형 배열을 만들고 동시에 여러 번 배열의 하는 데 필요한 시간을 계산 합니다.  
  
 [!code-cpp[concrt-allocators#2](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_2.cpp)]  
  
## <a name="example"></a>예제  
 다음 예제와 `wmain` 에 필요한 시간을 계산 하는 함수는 `reverse_array` 를 보여는 `new_delete`, `malloc_free`, 및 `Alloc_Free` 각각 사용 하는 다른 메모리 할당 체계 형식입니다.  
  
 [!code-cpp[concrt-allocators#3](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_3.cpp)]  
  
## <a name="example"></a>예제  
 전체 예제와 같습니다.  
  
 [!code-cpp[concrt-allocators#4](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_4.cpp)]  
  
 이 예에서는 4 개의 프로세서가 있는 컴퓨터에 대 한 다음 샘플 출력을 생성 합니다.  
  
```Output  
Took 2031 ms with new/delete.  
Took 1672 ms with malloc/free.  
Took 656 ms with Alloc/Free.  
```  
  
 이 예에서 사용 하는 형식의 `Alloc` 및 `Free` 함수 때문에 메모리 성능을 높일 수는 `Alloc` 및 `Free` 함수 자주 할당 하 고 여러에서 메모리 블록을 해제 하기 위해 최적화 스레드입니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣거나 라는 파일에 붙여 `allocators.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe /EHsc allocators.cpp**  
  
## <a name="see-also"></a>참고 항목  
 [메모리 관리 함수](../../parallel/concrt/memory-management-functions.md)   
 [Alloc 함수](reference/concurrency-namespace-functions.md#alloc)   
 [Free 함수](reference/concurrency-namespace-functions.md#free)

