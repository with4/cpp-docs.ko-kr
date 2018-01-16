---
title: "병렬 컨테이너 및 개체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
caps.latest.revision: "34"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9159b9c8170ee73afd8bee5305506a842368a231
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="parallel-containers-and-objects"></a>병렬 컨테이너 및 개체
여러 컨테이너와 해당 요소에 스레드로부터 안전한 액세스를 제공 하는 개체는 라이브러리 PPL (병렬 패턴)에 포함 되어 있습니다.  
  
 A *동시 컨테이너* 가장 중요 한 작업에 대 한 동시성 으로부터 안전한 액세스를 제공 합니다. 이러한 컨테이너의 기능을 c + + 표준 라이브러리에서 제공 하는 유사 합니다. 예를 들어는 [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) 클래스와 유사는 [std:: vector](../../standard-library/vector-class.md) 점을 제외 하 고 클래스는 `concurrent_vector` 클래스를 사용 하면 동시에 요소를 추가 합니다. 읽기와 같은 컨테이너에 대 한 쓰기를 모두 필요로 하는 병렬 코드를 있는 경우 동시 컨테이너를 사용 합니다.  
  
 A *동시 개체* 동시에 구성 요소 간에 공유 됩니다. 동시에 동시 개체의 상태를 계산 하는 프로세스는 직렬로 동일한 상태를 계산 하는 다른 프로세스와 동일한 결과 생성 합니다. [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 클래스는 동시 개체 형식의 한 가지 예입니다. `combinable` 클래스를 사용 하면 병렬에서 계산을 수행 하 고 그런 다음 이러한 계산을 최종 결과로 결합 합니다. 공유 변수 또는 리소스에 대 한 액세스를 동기화 하는 예를 들어 뮤텍스 동기화 메커니즘을 그렇지 않은 경우 사용 하는 동시 개체를 사용 합니다.  
  
##  <a name="top"></a> 섹션  
 이 항목에서는 다음 병렬 컨테이너 및 개체를 자세히 설명 합니다.  
  
 동시 컨테이너:  
  
-   [concurrent_vector 클래스](#ctor)  
  
    -   [Concurrent_vector 차이점 및 벡터](#ctor)  
  
    -   [동시성 으로부터 안전한 작업](#ctor)  
  
    -   [예외 안전성](#ctor)  
  
-   [concurrent_queue 클래스](#queue)  
  
    -   [Concurrent_queue 차이점 및 큐](#queue-differences)  
  
    -   [동시성 으로부터 안전한 작업](#queue-safety)  
  
    -   [반복기 지원](#queue-iterators)  
  
-   [concurrent_unordered_map 클래스](#unordered_map)  
  
    -   [Concurrent_unordered_map 차이점 및 unordered_map](#map-differences)  
  
    -   [동시성 으로부터 안전한 작업](#map-safety)  
  
-   [concurrent_unordered_multimap 클래스](#unordered_multimap)  
  
-   [concurrent_unordered_set 클래스](#unordered_set)  
  
-   [concurrent_unordered_multiset 클래스](#unordered_multiset)  
  
 동시 개체:  
  
-   [combinable 클래스](#combinable)  
  
    -   [메서드 및 기능](#combinable-features)  
  
    -   [예제](#combinable-examples)  
  
##  <a name="vector"></a>concurrent_vector 클래스  
 [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) 클래스는 동일 하 게 하는 시퀀스 컨테이너 클래스는 [std:: vector](../../standard-library/vector-class.md) 클래스, 해당 요소에 임의로 액세스할 수 있습니다. `concurrent_vector` 동시성 으로부터 안전한 추가 클래스를 사용 하 고 요소 액세스 작업. 추가 작업은 기존 포인터 또는 반복기를 무효화 하지 않습니다. 반복기 액세스 및 탐색 작업 동시성 으로부터 안전한 됩니다.  
  
###  <a name="vector-differences"></a>Concurrent_vector 차이점 및 벡터  
 `concurrent_vector` 유사는 `vector` 클래스입니다. 추가, 요소 액세스 및 반복기 액세스 작업의 복잡성을 `concurrent_vector` 개체에 대 한 동일는 `vector` 개체입니다. 다음 사항을 대 한 설명입니다 `concurrent_vector` 에서 다른 `vector`:  
  
-   추가, 요소 액세스, 반복기 액세스 및 반복기 통과 작업을 `concurrent_vector` 개체는 동시성 으로부터 안전한 합니다.  
  
-   끝에만 요소를 추가할 수는 `concurrent_vector` 개체입니다. `concurrent_vector` 클래스 제공 하지 않습니다는 `insert` 메서드.  
  
-   A `concurrent_vector` 개체를 사용 하지 않는 [의미 체계 이동](../../cpp/rvalue-reference-declarator-amp-amp.md) 에 추가 하는 경우.  
  

-   `concurrent_vector` 클래스 제공 하지 않습니다는 `erase` 또는 `pop_back` 메서드. 와 마찬가지로 `vector`를 사용 하 여는 [선택을 취소](reference/concurrent-vector-class.md#clear) 에서 요소를 모두 제거 하는 메서드는 `concurrent_vector` 개체입니다.  
  
-   `concurrent_vector` 클래스 메모리에 해당 요소를 연속적으로 저장 하지는 않습니다. 따라서 사용할 수 없습니다는 `concurrent_vector` 배열을 사용할 수 있는 모든 방식에서 클래스. 명명 된 변수에 대 한 예를 들어 `v` 형식의 `concurrent_vector`, 식 `&v[0]+2` 정의 되지 않은 동작이 발생 합니다.  
  
-   `concurrent_vector` 클래스 정의 [grow_by](reference/concurrent-vector-class.md#grow_by) 및 [grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) 메서드. 이러한 메서드 유사는 [크기를 조정](reference/concurrent-vector-class.md#resize) 메서드를 동시성 으로부터 안전한은 점을 제외 하 고 있습니다.  
  
-   A `concurrent_vector` 추가 하거나 크기를 조정 하는 경우 개체는 해당 요소 옮기지 않습니다. 이렇게 하면 기존 포인터 및 반복기 동시 작업 하는 동안 유효 하도록 합니다.  
  
-   런타임에서의 특수 버전을 정의 하지 않습니다 `concurrent_vector` 형식에 대 한 `bool`합니다.  
  
###  <a name="vector-safety"></a>동시성 으로부터 안전한 작업  
 에 추가 하거나의 크기가 증가 하는 모든 메서드는 `concurrent_vector` 개체 또는 요소에 액세스는 `concurrent_vector` 개체, 동시성 으로부터 안전한 됩니다. 이 규칙에 대 한 예외는 `resize` 메서드.  
  
 다음 표에서 일반적인 `concurrent_vector` 메서드 및 연산자는 동시성 으로부터 안전한입니다.  
  
||||  
|-|-|-|  

|[에서](reference/concurrent-vector-class.md#at)|[끝](reference/concurrent-vector-class.md#end)|[연산자 &#91;&#93;](reference/concurrent-vector-class.md#operator_at)|  
|[시작](reference/concurrent-vector-class.md#begin)|[앞](reference/concurrent-vector-class.md#front)|[push_back](reference/concurrent-vector-class.md#push_back)|  
|[다시](reference/concurrent-vector-class.md#back)|[grow_by](reference/concurrent-vector-class.md#grow_by)|[rbegin](reference/concurrent-vector-class.md#rbegin)|  
|[용량](reference/concurrent-vector-class.md#capacity)|[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)|  
|[빈](reference/concurrent-vector-class.md#empty)|[max_size](reference/concurrent-vector-class.md#max_size)|[크기](reference/concurrent-vector-class.md#size)|  

  
 예를 들어 런타임에 c + + 표준 라이브러리와 호환성을 위해 제공 하는 작업 `reserve`, 동시성 안전 하지 않습니다. 다음 표에서 일반적인 메서드와 동시성 으로부터 안전한 없는 연산자를 보여 줍니다.  
  
|||  
|-|-|  

|[할당](reference/concurrent-vector-class.md#assign)|[예약](reference/concurrent-vector-class.md#reserve)|  
|[선택을 취소](reference/concurrent-vector-class.md#clear)|[크기 조정](reference/concurrent-vector-class.md#resize)|  
|[연산자 =](reference/concurrent-vector-class.md#operator_eq)|[shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|  
  
 기존 요소의 값을 수정 하는 동시성 으로부터 안전한 않습니다. 와 같은 동기화 개체를 사용 하 여 한 [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) 동시 읽기를 동기화 하 고 동일한 데이터 요소에 쓰기 작업 개체입니다. 동기화 개체에 대 한 자세한 내용은 참조 [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)합니다.  
  
 사용 하는 기존 코드를 변환 하는 경우 `vector` 사용할 `concurrent_vector`, 동시 작업을 변경 하려면 응용 프로그램의 동작을 될 수 있습니다. 예를 들어 다음 프로그램에 대해 두 가지 작업을 동시에 수행 하는 `concurrent_vector` 개체입니다. 첫 번째 작업에 요소를 추가 `concurrent_vector` 개체입니다. 두 번째 작업은 동일한 개체에 있는 모든 요소의 합계를 계산합니다.  
  
 [!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]  
  

 하지만 `end` 메서드는 동시성 으로부터 안전한에 대 한 동시 호출은 [push_back](reference/concurrent-vector-class.md#push_back) 메서드를 사용 하면 반환 되는 값 `end` 변경할 수 있습니다. 반복기를 통과 하는 요소 수가 결정있지 않습니다. 따라서이 프로그램에서 다른 결과 실행 될 때마다 발생할 수 있습니다.  
  
###  <a name="vector-exceptions"></a>예외 안전성  
 증가 또는 할당 작업의 상태 예외를 throw 하는 경우는 `concurrent_vector` 개체가 무효화 됩니다. 동작은 `concurrent_vector` 별도 설명이 없으면 유효 하지 않은 상태에 있는 개체 정의 되지 않습니다. 그러나 소멸자가 항상 메모리를 해제 개체가 할당 하 고, 개체가 잘못 된 상태에 있으면도 합니다.  
  
 벡터 요소의 데이터 형식과 `T`, 다음과 같은 요구 사항을 충족 해야 합니다. 그렇지 않은 경우의 동작은 `concurrent_vector` 클래스 정의 되지 않습니다.  
  
-   소멸자가 발생 하지 않아야 합니다.  
  
-   소멸자를 사용 하 여 선언 되지 않아야 기본값 또는 복사 생성자를 throw 하는 경우는 `virtual` 키워드 이므로 0 초기화 된 메모리에서 제대로 작동 해야 합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="queue"></a>concurrent_queue 클래스  
 [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) 클래스와 동일 하 게는 [std::queue](../../standard-library/queue-class.md) 클래스, 요소 이동 했다가 그 앞에 액세스할 수 있습니다. `concurrent_queue` 하면 동시성 으로부터 안전한 enqueue 클래스 및 작업을 큐에서 제거 합니다. `concurrent_queue` 클래스에는 동시성 으로부터 안전한 하지 않은 반복기 지원을 제공 합니다.  
  
###  <a name="queue-differences"></a>Concurrent_queue 차이점 및 큐  
 `concurrent_queue` 유사는 `queue` 클래스입니다. 다음 사항을 대 한 설명입니다 `concurrent_queue` 에서 다른 `queue`:  
  
-   Enqueue 및 큐에서 제거 작업에는 `concurrent_queue` 개체는 동시성 으로부터 안전한 합니다.  
  
-   `concurrent_queue` 클래스는 동시성 으로부터 안전한 하지 않은 반복기 지원을 제공 합니다.  
  

-   `concurrent_queue` 클래스 제공 하지 않습니다는 `front` 또는 `pop` 메서드. `concurrent_queue` 정의 하 여 이러한 메서드를 대체 하는 클래스는 [try_pop](reference/concurrent-queue-class.md#try_pop) 메서드.  
  
-   `concurrent_queue` 클래스 제공 하지 않습니다는 `back` 메서드. 따라서 큐의 끝을 참조할 수 없습니다.  
  
-   `concurrent_queue` 클래스를 제공는 [unsafe_size](reference/concurrent-queue-class.md#unsafe_size) 메서드 대신는 `size` 메서드. `unsafe_size` 메서드는 동시성 으로부터 안전한 없습니다.  

  
###  <a name="queue-safety"></a>동시성 으로부터 안전한 작업  
 모든 메서드를 해당 큐에 넣기 또는에서 큐에서 제거는 `concurrent_queue` 개체는 동시성 으로부터 안전한 합니다.  
  
 다음 표에서 일반적인 `concurrent_queue` 메서드 및 연산자는 동시성 으로부터 안전한입니다.  
  
|||  
|-|-|  
|[empty](reference/concurrent-queue-class.md#empty)|[push](reference/concurrent-queue-class.md#push)|  
|[get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|  


  
 하지만 `empty` 메서드는 동시성 으로부터 안전한, 동시 작업이 큐를 확대 하거나 축소 하기 전에 발생할 수 있습니다는 `empty` 메서드 반환 합니다.  
  
 다음 표에서 일반적인 메서드와 동시성 으로부터 안전한 없는 연산자를 보여 줍니다.  
  
|||  
|-|-|  
|[clear](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|  
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|  


  
###  <a name="queue-iterators"></a>반복기 지원  
 `concurrent_queue` 동시성 으로부터 안전한 하지 않은 반복기를 제공 합니다. 만 디버깅을 위해 이러한 반복기를 사용 하는 것이 좋습니다.  
  
 A `concurrent_queue` 앞쪽으로 요소를 이동 하는 반복기입니다. 다음 표에서 각 반복기 지 원하는 연산자를 보여 줍니다.  
  
|연산자|설명|  
|--------------|-----------------|  
|[operator++](http://msdn.microsoft.com/en-us/4cfdd07e-927a-42f8-aaa0-d6881687f413)|큐에서 다음 항목으로 이동 합니다. 이 연산자는 전위 증가 및 사후 증가 모두 의미 체계를 제공 하도록 오버 로드 합니다.|  
|[operator*](http://msdn.microsoft.com/en-us/a0e671fc-76e6-4fb4-b95c-ced4dd2b2017)|현재 항목에 대 한 참조를 검색합니다.|  
|[operator->](http://msdn.microsoft.com/en-us/41fa393d-ae1e-4a38-bb4b-19e8df709ca9)|현재 항목에 대 한 포인터를 검색합니다.|  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="unordered_map"></a>concurrent_unordered_map 클래스  
 [하이퍼링크 "file:///C:\\\Users\\\thompet\\\AppData\\\Local\\\Temp\\\DxEditor\\\DduePreview\\\Default \\\798d7037-df37-4310-858b-6f590bbf6ebf\\\HTM\\\html\\\a217b4ac-af2b-4d41-94eb-09a75ee28622 "concurrency:: concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) 클래스는 프로그램 동일 하 게 하는 적절 한 연관 컨테이너 클래스는 [std:: unordered_map](../../standard-library/unordered-map-class.md) 클래스는 다양 한 길이의 요소 시퀀스를 제어 형식의 [std:: pair\<const 키, Ty >](../../standard-library/pair-structure.md)합니다. 에 키 / 값 쌍을 추가 하거나 값을 키로 조회할 수 있는 사전으로 순서가 지정 되지 않은 맵의 생각 합니다. 이 클래스는 여러 개의 스레드 또는 동시에 공유 컨테이너에 액세스, 삽입 또는 업데이트 하는 작업이 있는 경우에 유용 합니다.  
  
 다음 예제에서는 사용 하기 위한 기본 구조를 보여 줍니다. `concurrent_unordered_map`합니다. 이 예에서는 ['a', ' i'] 범위 내에 문자 키를 삽입합니다. 작업 순서를 알 수 없는 때문에 각 키에 대 한 최종 값은 또한 결정 됩니다. 그러나 삽입 하는 데는 동시에 안전 합니다.  
  
 [!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]  
  
 사용 하는 예제에 대 한 `concurrent_unordered_map` 지도 및 줄이기 병렬로 작업을 수행 하려면 참조 [하는 방법: 지도 수행 및 병렬 작업 줄이기](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)합니다.  
  
###  <a name="map-differences"></a>Concurrent_unordered_map 차이점 및 unordered_map  
 `concurrent_unordered_map` 유사는 `unordered_map` 클래스입니다. 다음 사항을 대 한 설명입니다 `concurrent_unordered_map` 에서 다른 `unordered_map`:  
  
-   `erase`, `bucket`, `bucket_count`, 및 `bucket_size` 메서드 이름은 `unsafe_erase`, `unsafe_bucket`, `unsafe_bucket_count`, 및 `unsafe_bucket_size`각각. `unsafe_` ô ä ¢ 이러한 메서드는 동시성 으로부터 안전한 나타냅니다. 동시성 안전에 대 한 자세한 내용은 참조 [동시성 으로부터 안전한 작업](#map-safety)합니다.  
  
-   지도에 이미 있는 항목의 순서를 변경은 하지도 삽입 작업은 기존 포인터 또는 반복기를 무효화 하지 않습니다. 삽입 및 이동 작업이 동시에 발생할 수 있습니다.  
  
-   `concurrent_unordered_map`지원만 반복으로 전달합니다.  
  
-   삽입을 무효화 하거나에 의해 반환 된 반복기를 업데이트 하지 않는 `equal_range`합니다. 삽입 된 범위의 끝에 같지 않은 항목을 추가할 수 있습니다. Begin 반복기 같은 항목을 가리킵니다.  
  
 교착 상태를 없는 메서드를 사용 하지 않도록 하려면 `concurrent_unordered_map` 메모리 할당자, 해시 함수, 또는 기타 사용자 지정 코드를 호출할 때 잠금을 보유 하 고 있습니다. 또한, 해시 함수는 항상 동일한 값으로 동일한 키를 평가 해야 합니다. 가장 좋은 해시 함수는 키 해시 코드 공간에서 균일 하 게 배포합니다.  
  
###  <a name="map-safety"></a>동시성 으로부터 안전한 작업  
 `concurrent_unordered_map` 클래스를 사용 하면 동시성 으로부터 안전한 삽입 및 요소 액세스 작업. 삽입 작업은 기존 포인터 또는 반복기를 무효화 하지 않습니다. 반복기 액세스 및 탐색 작업 동시성 으로부터 안전한 됩니다. 다음 표에서 일반적으로 사용 되는 `concurrent_unordered_map` 메서드와 연산자는 동시성 으로부터 안전한을 합니다.  
  
|||||  
|-|-|-|-|  
|[at](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|  
|`begin`|`empty`|`get_allocator`|`max_size`|  
|`cbegin`|`end`|`hash_function`|[operator&#91;&#93;](reference/concurrent-unordered-map-class.md#operator_at)|  
|`cend`|`equal_range`|[insert](reference/concurrent-unordered-map-class.md#insert)|`size`|  
  
 하지만 `count` 메서드는 스레드를 동시에 실행에서 안전 하 게 호출 수, 새 값을 컨테이너에 동시에 넣으면 서로 다른 여러 스레드에서 다른 결과 받을 수 있습니다.  
  
 다음 표에서 자주 사용 되는 메서드 및 동시성 으로부터 안전한 없는 연산자를 보여 줍니다.  
  
||||  
|-|-|-|  
|`clear`|`max_load_factor`|`rehash`|  
|`load_factor`|[operator=](reference/concurrent-unordered-map-class.md#operator_eq) 


  
 이러한 방법 외에도 모든 방법으로 시작 하 `unsafe_` 동시성 으로부터 안전한 하지 이기도 합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="unordered_multimap"></a>concurrent_unordered_multimap 클래스  
 [concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) 유사는 `concurrent_unordered_map` 클래스에 대 한 여러 값을 동일한 키에 매핑할 수 있다는 점이 다릅니다. 다른 `concurrent_unordered_map` 다음과 같은 방법으로:  
  
-   [concurrent_unordered_multimap:: insert](reference/concurrent-unordered-multimap-class.md#insert) 메서드 대신 반복기를 반환 합니다. `std::pair<iterator, bool>`합니다.  

  
-   `concurrent_unordered_multimap` 클래스가 제공 하지 않는 `operator[]` 와 `at` 메서드.  
  
 다음 예제에서는 사용 하기 위한 기본 구조를 보여 줍니다. `concurrent_unordered_multimap`합니다. 이 예에서는 ['a', ' i'] 범위 내에 문자 키를 삽입합니다. `concurrent_unordered_multimap`여러 값 키를 사용 하도록 설정 합니다.  
  
 [!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="unordered_set"></a>concurrent_unordered_set 클래스  
 [concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) 유사는 `concurrent_unordered_map` 클래스 제외 하 고 키 / 값 쌍이 아닌 다른 값을 관리 합니다. `concurrent_unordered_set` 클래스가 제공 하지 않는 `operator[]` 와 `at` 메서드.  
  
 다음 예제에서는 사용 하기 위한 기본 구조를 보여 줍니다. `concurrent_unordered_set`합니다. 이 예에서는 ['a', ' i'] 범위 내에 문자 값을 삽입합니다. 삽입 하는 데는 동시에 안전 합니다.  
  
 [!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="unordered_multiset"></a>concurrent_unordered_multiset 클래스  
 [concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) 유사는 `concurrent_unordered_set` 클래스 중복 값에 대 한 있다는 점이 다릅니다. 다른 `concurrent_unordered_set` 다음과 같은 방법으로:  
  

-   [concurrent_unordered_multiset:: insert](reference/concurrent-unordered-multiset-class.md#insert) 메서드 대신 반복기를 반환 합니다. `std::pair<iterator, bool>`합니다.  

  
-   `concurrent_unordered_multiset` 클래스가 제공 하지 않는 `operator[]` 와 `at` 메서드.  
  
 다음 예제에서는 사용 하기 위한 기본 구조를 보여 줍니다. `concurrent_unordered_multiset`합니다. 이 예에서는 ['a', ' i'] 범위 내에 문자 값을 삽입합니다. `concurrent_unordered_multiset`값을을 여러 번 발생할 수 있습니다.  
  
 [!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="combinable"></a>combinable 클래스  
 [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 클래스는 세분화 된 계산을 수행한 다음 이러한 계산을 최종 결과로 병합할 수 있게 해 주는 다시 사용할 수 있는, 스레드 로컬 저장소를 제공 합니다. `combinable` 개체는 환산(reduction) 변수로 간주될 수 있습니다.  
  
 `combinable` 클래스는 여러 스레드 또는 작업 간에 공유 되는 리소스를 사용할 경우 유용 합니다. `combinable` 클래스를 사용 하면 잠금 없는 방식으로 공유 리소스에 대 한 액세스를 제공 하 여 공유 상태를 제거 합니다. 따라서이 클래스는 여러 스레드에서 공유 데이터에 대 한 액세스를 동기화 하는 뮤텍스 예를 들어 동기화 메커니즘을 사용 하는 대신을 제공 합니다.  
  
###  <a name="combinable-features"></a>메서드 및 기능  
 다음 표에의 중요 한 메서드 중 일부는 `combinable` 클래스입니다. 모든에 대 한 자세한 내용은 `combinable` 클래스 메서드를 참조 하십시오. [combinable 클래스](../../parallel/concrt/reference/combinable-class.md)합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[로컬](reference/combinable-class.md#local)|연결 된 현재 스레드 컨텍스트를 로컬 변수에 대 한 참조를 검색 합니다.|  
|[clear](reference/combinable-class.md#clear)|모든 스레드 지역 변수 제거는 `combinable` 개체입니다.|  
|[combine](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|제공 된 결합 되어 감사가 만들어집니다 함수를 사용 하 여 모든 스레드 로컬 계산 집합에서 마지막 값을 생성 합니다.|  
  
 `combinable` 클래스는 병합 된 최종 결과 대해 매개 변수가 하는 템플릿 클래스입니다. 기본 생성자를 호출 하는 경우는 `T` 템플릿 매개 변수 형식에 기본 생성자 및 복사 생성자가 있어야 합니다. 경우는 `T` 템플릿 매개 변수 형식이 기본 생성자가 없는, 해당 매개 변수로 초기화 함수를 사용 하는 생성자의 오버 로드 된 버전을 호출 합니다.  
  
 추가 데이터를 저장할 수 있습니다는 `combinable` 호출한 후 개체의 [결합](reference/combinable-class.md#combine) 또는 [combine_each](reference/combinable-class.md#combine_each) 메서드. 호출할 수도 있습니다는 `combine` 및 `combine_each` 메서드를 여러 번입니다. 경우에 지역 값은 `combinable` 개체 변경는 `combine` 및 `combine_each` 메서드를 호출할 때마다 동일한 결과 생성 합니다.  
  
###  <a name="combinable-examples"></a> 예제  
 사용 하는 방법에 대 한 예는 `combinable` 다음 항목을 참조 하세요.  
  
-   [방법: combinable을 사용하여 성능 개선](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
  
-   [방법: combinable을 사용하여 집합 결합](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
  
 [[맨 위로 이동](#top)]  
  
## <a name="related-topics"></a>관련 항목  
 [방법: 병렬 컨테이너를 사용하여 효율성 향상](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)  
 병렬 컨테이너를 효율적으로 저장 및 데이터를 병렬로 액세스를 사용 하는 방법을 보여 줍니다.  
  
 [방법: combinable을 사용하여 성능 개선](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
 사용 하는 방법을 보여 줍니다.는 `combinable` 클래스 공유 상태를 제거 하 고 성능을 향상 시키는 합니다.  
  
 [방법: combinable을 사용하여 집합 결합](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
 사용 하는 방법을 보여 줍니다.는 `combine` 데이터의 스레드 로컬 집합을 병합 하는 함수입니다.  
  
 [PPL(병렬 패턴 라이브러리)](../../parallel/concrt/parallel-patterns-library-ppl.md)  
 동시 응용 프로그램을 개발 하기 위한 사용 편의성과 확장성을 하는 명령적 프로그래밍 모델을 제공 하는 PPL에 설명 합니다.  
  
## <a name="reference"></a>참조  
 [concurrent_vector 클래스](../../parallel/concrt/reference/concurrent-vector-class.md)  
  
 [concurrent_queue 클래스](../../parallel/concrt/reference/concurrent-queue-class.md)  
  
 [concurrent_unordered_map 클래스](../../parallel/concrt/reference/concurrent-unordered-map-class.md)  
  
 [concurrent_unordered_multimap 클래스](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)  
  
 [concurrent_unordered_set 클래스](../../parallel/concrt/reference/concurrent-unordered-set-class.md)  
  
 [concurrent_unordered_multiset 클래스](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)  
  
 [combinable 클래스](../../parallel/concrt/reference/combinable-class.md)
