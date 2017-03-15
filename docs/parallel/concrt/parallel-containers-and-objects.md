---
title: "병렬 컨테이너 및 개체 | Microsoft Docs"
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
  - "병렬 개체"
  - "병렬 컨테이너"
  - "동시 컨테이너"
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
caps.latest.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 34
---
# 병렬 컨테이너 및 개체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

몇 가지 컨테이너 및 해당 요소에 스레드로부터 안전한 액세스를 제공 하는 개체는 라이브러리 PPL (병렬 패턴)에 포함 되어 있습니다.  
  
 A *동시 컨테이너* 가장 중요 한 작업에 대 한 동시성이 액세스를 제공 합니다. 이러한 컨테이너의 기능을 제공 되는 표준 템플릿 라이브러리 (STL)에서 유사 합니다. 예를 들어는 [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) 클래스와 유사는 [std:: vector](../../standard-library/vector-class.md) 점을 제외 하 고 클래스는 `concurrent_vector` 클래스를 사용 하면 요소를에서 추가 합니다. 읽기와 같은 컨테이너에 대 한 쓰기 액세스 해야 하는 병렬 코드가 있는 경우 동시 컨테이너를 사용 합니다.  
  
 A *동시 개체* 동시에 구성 요소 간에 공유 됩니다. 동시에 동시 개체의 상태를 계산 하는 프로세스는 동일한 상태를 순차적으로 계산 하는 다른 프로세스와 같은 결과 생성 합니다.  [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 클래스는 동시 개체 형식의 한 가지 예입니다.  `combinable` 클래스를 사용 하면 병렬에서 계산을 수행 하 고 해당 계산 결과 최종 결과로 결합 합니다. 공유 변수 또는 리소스에 대 한 액세스를 동기화 하는 예를 들어 뮤텍스 동기화 메커니즘을 그렇지 않은 경우 사용 하는 동시 개체를 사용 합니다.  
  
##  <a name="a-nametopa-sections"></a><a name="top"></a> 섹션  
 이 항목에서는 다음 병렬 컨테이너 및 개체를 자세히 설명 합니다.  
  
 동시 컨테이너:  
  
-   [concurrent_vector 클래스](#vector)  
  
    -   [차이점 동시 벡터와 벡터](#vector-differences)  
  
    -   [동시성이 작업](#vector-safety)  
  
    -   [예외 안전성](#vector-exceptions)  
  
-   [concurrent_queue 클래스](#queue)  
  
    -   [Concurrent_queue 차이점 및 큐](#queue-differences)  
  
    -   [동시성이 작업](#queue-safety)  
  
    -   [반복기 지원](#queue-iterators)  
  
-   [concurrent_unordered_map 클래스](#unordered_map)  
  
    -   [Concurrent_unordered_map 차이점 및 unordered_map](#map-differences)  
  
    -   [동시성이 작업](#map-safety)  
  
-   [concurrent_unordered_multimap 클래스](#unordered_multimap)  
  
-   [concurrent_unordered_set 클래스](#unordered_set)  
  
-   [concurrent_unordered_multiset 클래스](#unordered_multiset)  
  
 동시 개체:  
  
-   [combinable 클래스](#combinable)  
  
    -   [메서드 및 기능](#combinable-features)  
  
    -   [예제](#combinable-examples)  
  
##  <a name="a-namevectora-concurrentvector-class"></a><a name="vector"></a> concurrent_vector 클래스  
  [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) 클래스는 동일 하 게 하는 시퀀스 컨테이너 클래스는 [std:: vector](../../standard-library/vector-class.md) 클래스, 해당 요소에 임의로 액세스할 수 있습니다.  `concurrent_vector` 클래스를 사용 하면 동시성이 추가 및 요소 작업에 액세스 합니다. 추가 작업은 기존 포인터 또는 반복기를 무효화 하지 않습니다. 반복기 액세스 및 이동 작업 동시성이 보장 됩니다.  
  
###  <a name="a-namevector-differencesa-differences-between-concurrentvector-and-vector"></a><a name="vector-differences"></a> 차이점 동시 벡터와 벡터  
  `concurrent_vector` 클래스와 매우 유사는 `vector` 클래스입니다. 추가, 요소 액세스 및 반복기 액세스 작업의 복잡성을 `concurrent_vector` 개체는 동일한 방식으로 `vector` 개체입니다. 다음 사항을 대 한 설명입니다 `concurrent_vector` 에서 다른 `vector`:  
  
-   추가, 요소 액세스, 반복기 액세스 및 반복기 통과 작업은 `concurrent_vector` 개체는 동시성이 보장 합니다.  
  
-   끝에만 요소를 추가할 수는 `concurrent_vector` 개체입니다.  `concurrent_vector` 클래스는 제공 하지는 `insert` 메서드.  
  
-   A `concurrent_vector` 개체를 사용 하지 않는 [의미 체계 이동](../../cpp/rvalue-reference-declarator-amp-amp.md) 에 추가 하는 경우.  
  
-    `concurrent_vector` 클래스는 제공 하지는 `erase` 또는 `pop_back` 메서드. 와 마찬가지로 `vector`, 를 사용 하 여는 [의 선택을 취소](../Topic/concurrent_vector::clear%20Method.md) 에서 모든 요소를 제거 하는 메서드는 `concurrent_vector` 개체입니다.  
  
-    `concurrent_vector` 클래스 메모리에 해당 요소를 연속적으로 저장 하지는 않습니다. 따라서 사용할 수 없습니다는 `concurrent_vector` 배열을 사용할 수 있는 모든 방법으로는 클래스입니다. 명명 된 변수에 대 한 예를 들어 `v` 형식의 `concurrent_vector`, 식 `&v[0]+2` 하면 정의 되지 않은 동작이 발생 합니다.  
  
-    `concurrent_vector` 클래스 정의 [grow_by](../Topic/concurrent_vector::grow_by%20Method.md) 및 [grow_to_at_least](../Topic/concurrent_vector::grow_to_at_least%20Method.md) 메서드. 이러한 메서드 유사는 [크기를 조정](../Topic/concurrent_vector::resize%20Method.md) 메서드를 동시성이 있는 점을 제외 하 고 있습니다.  
  
-   A `concurrent_vector` 을 추가 하거나 크기를 조정 하는 경우 개체는 해당 요소 옮기지 않습니다. 이 통해 기존 포인터 및 반복기에서 동시 작업을 하는 동안 유효 하도록 합니다.  
  
-   런타임에서의 특수 버전을 정의 하지 않습니다 `concurrent_vector` 형식에 대 한 `bool`합니다.  
  
###  <a name="a-namevector-safetya-concurrency-safe-operations"></a><a name="vector-safety"></a> 동시성이 작업  
 에 추가 하거나의 크기가 증가 하는 모든 메서드는 `concurrent_vector` 개체 또는 요소에 액세스는 `concurrent_vector` 개체, 동시성이 보장 됩니다. 이 규칙에 대 한 예외는 `resize` 메서드.  
  
 다음 표에서 일반적인 `concurrent_vector` 메서드 및 연산자는 동시성이입니다.  
  
||||  
|-|-|-|  
|[에서](../Topic/concurrent_vector::at%20Method.md)|[끝](../Topic/concurrent_vector::end%20Method.md)|[연산자 &#91; &#93;](../Topic/concurrent_vector::operatorOperator.md)|  
|[시작](../Topic/concurrent_vector::begin%20Method.md)|[앞면](../Topic/concurrent_vector::front%20Method.md)|[push_back](../Topic/concurrent_vector::push_back%20Method.md)|  
|[뒤로](../Topic/concurrent_vector::back%20Method.md)|[grow_by](../Topic/concurrent_vector::grow_by%20Method.md)|[rbegin](../Topic/concurrent_vector::rbegin%20Method.md)|  
|[용량](../Topic/concurrent_vector::capacity%20Method.md)|[grow_to_at_least](../Topic/concurrent_vector::grow_to_at_least%20Method.md)|[rend](../Topic/concurrent_vector::rend%20Method.md)|  
|[빈](../Topic/concurrent_vector::empty%20Method.md)|[max_size](../Topic/concurrent_vector::max_size%20Method.md)|[크기](../Topic/concurrent_vector::size%20Method.md)|  
  
 예를 들어, 런타임에서 STL의 호환을 위해 제공 하는 작업 `reserve`, 동시성 안전 하지 않습니다. 다음 표에서 공용 메서드와 동시성이 보장 되지 않는 연산자를 보여 줍니다.  
  
|||  
|-|-|  
|[할당](../Topic/concurrent_vector::assign%20Method.md)|[예약](../Topic/concurrent_vector::reserve%20Method.md)|  
|[지우기](../Topic/concurrent_vector::clear%20Method.md)|[크기 조정](../Topic/concurrent_vector::resize%20Method.md)|  
|[연산자 =](../Topic/concurrent_vector::operator=%20Operator.md)|[shrink_to_fit](../Topic/concurrent_vector::shrink_to_fit%20Method.md)|  
  
 기존 요소의 값을 수정 하는 작업 동시성이 보장 되지 않습니다. 와 같은 동기화 개체를 사용 하 여 한 [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) 개체 동기화 동시 읽기 및 쓰기 작업을 동일한 데이터 요소입니다. 동기화 개체에 대 한 자세한 내용은 참조 [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)합니다.  
  
 사용 하는 기존 코드를 변환 하는 경우 `vector` 사용 하 여 `concurrent_vector`, 동시 작업에는 변경 하려면 응용 프로그램의 동작이 발생할 수 있습니다. 예를 들어 동시에 두 가지 작업을 수행 하는 다음 프로그램을 `concurrent_vector` 개체입니다. 첫 번째 작업에 요소를 추가 `concurrent_vector` 개체입니다. 두 번째 작업 같은 개체에 있는 모든 요소의 합계를 계산 합니다.  
  
 [!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_1.cpp)]  
  
 하지만 `end` 메서드는 동시성이 보장에 대 한 동시 호출은 [push_back](../Topic/concurrent_vector::push_back%20Method.md) 메서드를 사용 하면 반환 되는 값 `end` 변경할 수 있습니다. 반복기에서 트래버스하는 요소의 수를 확정적있지 않습니다. 따라서이 프로그램 다른 결과 실행 하는 때마다 생성할 수 있습니다.  
  
###  <a name="a-namevector-exceptionsa-exception-safety"></a><a name="vector-exceptions"></a> 예외 안전성  
 증가 또는 할당 작업의 상태 예외를 throw 하는 경우는 `concurrent_vector` 개체 수 없게 됩니다. 동작을 `concurrent_vector` 언급이 잘못 된 상태에 있는 개체 정의 되지 않습니다. 그러나 소멸자가 항상 메모리를 해제 개체가 할당 하는 개체가 잘못 된 상태에 있으면 하는 경우에 있습니다.  
  
 벡터 요소의 데이터 형식을 `T`, 다음과 같은 요구 사항을 충족 해야 합니다. 그렇지 않은 경우의 동작에서 `concurrent_vector` 클래스 정의 되지 않습니다.  
  
-   소멸자를 throw 하면 안 됩니다.  
  
-   소멸자를 사용 하 여 선언 되지 않아야 기본 또는 복사 생성자를 throw 하는 경우는 `virtual` 키워드와 그 메모리를 0으로 초기화 제대로 작동 해야 합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-namequeuea-concurrentqueue-class"></a><a name="queue"></a> concurrent_queue 클래스  
  [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) 클래스와 동일 하 게는 [std::queue](../../standard-library/queue-class.md) 클래스, 앞면이 액세스 하 고 요소를 백업할 수 있습니다.  `concurrent_queue` 클래스 수 있도록 동시성이 큐에 삽입 하 고 큐에서 제거 작업 합니다.  `concurrent_queue` 클래스 동시성이 보장 되지 않는 반복기 지원 기능을 제공 합니다.  
  
###  <a name="a-namequeue-differencesa-differences-between-concurrentqueue-and-queue"></a><a name="queue-differences"></a> Concurrent_queue 차이점 및 큐  
  `concurrent_queue` 클래스와 매우 유사는 `queue` 클래스입니다. 다음 사항을 대 한 설명입니다 `concurrent_queue` 에서 다른 `queue`:  
  
-   큐에 추가 하 고 큐에서 제거 작업에는 `concurrent_queue` 개체는 동시성이.  
  
-    `concurrent_queue` 클래스는 동시성이 보장 되지 않는 반복기 지원을 제공 합니다.  
  
-    `concurrent_queue` 클래스는 제공 하지는 `front` 또는 `pop` 메서드.  `concurrent_queue` 클래스를 정의 하 여 이러한 메서드를 대체는 [try_pop](../Topic/concurrent_queue::try_pop%20Method.md) 메서드.  
  
-    `concurrent_queue` 클래스는 제공 하지는 `back` 메서드. 따라서 큐의 끝을 참조할 수 없습니다.  
  
-    `concurrent_queue` 클래스는 제공 된 [unsafe_size](../Topic/concurrent_queue::unsafe_size%20Method.md) 메서드 대신는 `size` 메서드.  `unsafe_size` 방법은 동시성이 보장 하지는 않습니다.  
  
###  <a name="a-namequeue-safetya-concurrency-safe-operations"></a><a name="queue-safety"></a> 동시성이 작업  
 모든 메서드를 해당 큐에 넣기 또는에서 큐에서 제거는 `concurrent_queue` 개체는 동시성이 합니다.  
  
 다음 표에서 일반적인 `concurrent_queue` 메서드 및 연산자는 동시성이입니다.  
  
|||  
|-|-|  
|[빈](../Topic/concurrent_queue::empty%20Method.md)|[푸시](../Topic/concurrent_queue::push%20Method.md)|  
|[get_allocator](../Topic/concurrent_queue::get_allocator%20Method.md)|[try_pop](../Topic/concurrent_queue::try_pop%20Method.md)|  
  
 하지만 `empty` 메서드는 동시성이, 동시 작업을 수행 하는 큐를 확대 하거나 축소 하기 전에 발생할 수 있습니다는 `empty` 메서드 반환 합니다.  
  
 다음 표에서 공용 메서드와 동시성이 보장 되지 않는 연산자를 보여 줍니다.  
  
|||  
|-|-|  
|[지우기](../Topic/concurrent_queue::clear%20Method.md)|[unsafe_end](../Topic/concurrent_queue::unsafe_end%20Method.md)|  
|[unsafe_begin](../Topic/concurrent_queue::unsafe_begin%20Method.md)|[unsafe_size](../Topic/concurrent_queue::unsafe_size%20Method.md)|  
  
###  <a name="a-namequeue-iteratorsa-iterator-support"></a><a name="queue-iterators"></a> 반복기 지원  
  `concurrent_queue` 동시성이 보장 되지 않는 반복기를 제공 합니다. 만 디버깅을 위해 이러한 반복기를 사용 하는 것이 좋습니다.  
  
 A `concurrent_queue` 반복기 요소 앞 으로만 이동 합니다. 다음 표에서 각 반복기 지 원하는 연산자를 보여 줍니다.  
  
|연산자|설명|  
|--------------|-----------------|  
|[operator + +](http://msdn.microsoft.com/ko-kr/4cfdd07e-927a-42f8-aaa0-d6881687f413)|큐에서 다음 항목으로 이동 합니다. 이 연산자는 전위 증가 및 후 위 증가 모두 의미 체계를 제공 하는 오버 로드 합니다.|  
|[연산자 *](http://msdn.microsoft.com/ko-kr/a0e671fc-76e6-4fb4-b95c-ced4dd2b2017)|현재 항목에 대 한 참조를 검색합니다.|  
|[-> 연산자](http://msdn.microsoft.com/ko-kr/41fa393d-ae1e-4a38-bb4b-19e8df709ca9)|현재 항목에 대 한 포인터를 검색합니다.|  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-nameunorderedmapa-concurrentunorderedmap-class"></a><a name="unordered_map"></a> concurrent_unordered_map 클래스  
  [HYPERLINK "file:///C:\\\Users\\\thompet\\\AppData\\\Local\\\Temp\\\DxEditor\\\DduePreview\\\Default\\\798d7037-df37-4310-858b-6f590bbf6ebf\\\HTM\\\html\\\a217b4ac-af2b-4d41-94eb-09a75ee28622" concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) 클래스는 동일 하 게 하는 결합형 컨테이너 클래스는 [std:: unordered_map](../../standard-library/unordered-map-class.md) 클래스, 다양 한 길이의 요소 시퀀스를 유형의 제어 [std::pair \< const 키, Ty >](../../standard-library/pair-structure.md)합니다. 에 키 / 값 쌍을 추가 하거나 키 값을 조회할 수 있는 사전으로 순서가 지정 되지 않은 맵의 생각 합니다. 이 클래스는 여러 스레드 또는 동시에 공유 컨테이너에 액세스, 삽입 또는 업데이트 하는 작업이 있는 경우에 유용 합니다.  
  
 다음 예제에서는 사용 하기 위한 기본 구조를 보여 줍니다. `concurrent_unordered_map`합니다. 이 예제에서는 ['a', ' i'] 범위에 문자 키를 삽입 합니다. 작업의 순서를 알 수 없는 때문에 각 키에 대 한 최종 값은도 결정 합니다. 그러나 삽입 하는 데는 동시에 안전 합니다.  
  
 [!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_2.cpp)]  
  
 사용 하는 예제에 대 한 `concurrent_unordered_map` 지도 수행 하 고 줄이기 병렬로 작업을 참조 하십시오. [하는 방법: 지도 수행 및 병렬 작업 줄이기](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)합니다.  
  
###  <a name="a-namemap-differencesa-differences-between-concurrentunorderedmap-and-unorderedmap"></a><a name="map-differences"></a> Concurrent_unordered_map 차이점 및 unordered_map  
  `concurrent_unordered_map` 클래스와 매우 유사는 `unordered_map` 클래스입니다. 다음 사항을 대 한 설명입니다 `concurrent_unordered_map` 에서 다른 `unordered_map`:  
  
-    `erase`, `bucket`, `bucket_count`, 및 `bucket_size` 메서드 이름은 `unsafe_erase`, `unsafe_bucket`, `unsafe_bucket_count`, 및 `unsafe_bucket_size`, 각각.  `unsafe_` 명명 규칙 이러한 메서드는 동시성이 나타냅니다. 안전성에 대 한 자세한 내용은 참조 [동시성이 작업](#map-safety)합니다.  
  
-   삽입 작업은 기존 포인터 또는 반복기를 무효화 하지도 지도에 이미 있는 항목의 순서 변경지 않습니다. 삽입 및 이동 작업이 동시에 발생할 수 있습니다.  
  
-   `concurrent_unordered_map` 지원만 반복으로 전달합니다.  
  
-   삽입을 무효화 하지 않거나 업데이트에 의해 반환 된 반복기 `equal_range`합니다. 삽입 범위 끝에 같지 않은 항목을 추가할 수 있습니다. Begin 반복기 같은 항목을 가리킵니다.  
  
 교착 상태를 없음 메서드를 사용 하지 않도록 하려면 `concurrent_unordered_map` 메모리 할당자, 해시 함수 또는 기타 사용자 지정 코드를 호출할 때 잠금을 보유 하 고 있습니다. 또한, 해시 함수 같은 키 값과 동일한 값을 계산 하는 항상 확인 해야 합니다. 가장 좋은 해시 함수는 키 해시 코드 공간에서 균일 하 게 배포합니다.  
  
###  <a name="a-namemap-safetya-concurrency-safe-operations"></a><a name="map-safety"></a> 동시성이 작업  
  `concurrent_unordered_map` 클래스를 사용 하면 동시성이 삽입 및 요소 액세스 작업. 삽입 작업은 기존 포인터 또는 반복기를 무효화 하지 않습니다. 반복기 액세스 및 이동 작업 동시성이 보장 됩니다. 다음 표에서 자주 사용 되는 `concurrent_unordered_map` 메서드 및 연산자는 동시성이입니다.  
  
|||||  
|-|-|-|-|  
|[에서](../Topic/concurrent_unordered_map::at%20Method.md)|`count`|`find`|[key_eq](../Topic/concurrent_unordered_map::key_eq%20Method.md)|  
|`begin`|`empty`|`get_allocator`|`max_size`|  
|`cbegin`|`end`|`hash_function`|[연산자 &#91; &#93;](../Topic/concurrent_unordered_map::operatorOperator.md)|  
|`cend`|`equal_range`|[삽입](../Topic/concurrent_unordered_map::insert%20Method.md)|`size`|  
  
 하지만 `count` 스레드를 동시에 실행에서 메서드를 안전 하 게 호출할 수, 다른 스레드를 컨테이너에 새 값을 동시에 삽입 하는 경우 다른 결과 받을 수 있습니다.  
  
 다음 표에서 자주 사용 되는 메서드 및 동시성이 보장 되지 않는 연산자를 보여 줍니다.  
  
||||  
|-|-|-|  
|`clear`|`max_load_factor`|`rehash`|  
|`load_factor`|[연산자 =](../Topic/concurrent_unordered_map::operator=%20Operator.md)|[스왑](../Topic/concurrent_unordered_map::swap%20Method.md)|  
  
 이러한 방법 외에도 모든 방법으로 시작 하 `unsafe_` 동시성이 하지 이기도 합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-nameunorderedmultimapa-concurrentunorderedmultimap-class"></a><a name="unordered_multimap"></a> concurrent_unordered_multimap 클래스  
  [concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) 클래스와 매우 유사는 `concurrent_unordered_map` 클래스를 제외 하 고 동일한 키에 매핑하는 여러 값을 허용 합니다. 또한에서 서로 다른 `concurrent_unordered_map` 다음과 같은 방법으로:  
  
-    [concurrent_unordered_multimap:: insert](../Topic/concurrent_unordered_multimap::insert%20Method.md) 대신 반복기를 반환 하는 메서드 `std::pair<iterator, bool>`합니다.  
  
-    `concurrent_unordered_multimap` 클래스가 제공 하지 않는 `operator[]` 또는 `at` 메서드.  
  
 다음 예제에서는 사용 하기 위한 기본 구조를 보여 줍니다. `concurrent_unordered_multimap`합니다. 이 예제에서는 ['a', ' i'] 범위에 문자 키를 삽입 합니다. `concurrent_unordered_multimap` 여러 값에 대 한 키를 수 있습니다.  
  
 [!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_3.cpp)]  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-nameunorderedseta-concurrentunorderedset-class"></a><a name="unordered_set"></a> concurrent_unordered_set 클래스  
  [concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) 클래스와 매우 유사는 `concurrent_unordered_map` 키 / 값 쌍이 아닌 값 관리 한다는 클래스입니다.  `concurrent_unordered_set` 클래스가 제공 하지 않는 `operator[]` 또는 `at` 메서드.  
  
 다음 예제에서는 사용 하기 위한 기본 구조를 보여 줍니다. `concurrent_unordered_set`합니다. 이 예에서는 ['a', ' i'] 범위에서 문자 값을 삽입합니다. 삽입 하는 데는 동시에 안전 합니다.  
  
 [!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_4.cpp)]  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-nameunorderedmultiseta-concurrentunorderedmultiset-class"></a><a name="unordered_multiset"></a> concurrent_unordered_multiset 클래스  
  [concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) 클래스와 매우 유사는 `concurrent_unordered_set` 클래스 중복 값에 대 한 있다는 점이 다릅니다. 또한에서 서로 다른 `concurrent_unordered_set` 다음과 같은 방법으로:  
  
-    [concurrent_unordered_multiset:: insert](../Topic/concurrent_unordered_multiset::insert%20Method.md) 대신 반복기를 반환 하는 메서드 `std::pair<iterator, bool>`합니다.  
  
-    `concurrent_unordered_multiset` 클래스가 제공 하지 않는 `operator[]` 또는 `at` 메서드.  
  
 다음 예제에서는 사용 하기 위한 기본 구조를 보여 줍니다. `concurrent_unordered_multiset`합니다. 이 예에서는 ['a', ' i'] 범위에서 문자 값을 삽입합니다. `concurrent_unordered_multiset` 값을 여러 번 발생할 수 있습니다.  
  
 [!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_5.cpp)]  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="a-namecombinablea-combinable-class"></a><a name="combinable"></a> combinable 클래스  
  [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 클래스는 세분화 된 계산을 수행 하 고 다음 최종 결과에 이러한 계산을 병합할 수 있는 재사용 가능한, 스레드 로컬 저장소를 제공 합니다. `combinable` 개체는 환산(reduction) 변수로 간주될 수 있습니다.  
  
  `combinable` 클래스는 여러 스레드 또는 작업 간에 공유 되는 리소스를 사용할 경우 유용 합니다.  `combinable` 클래스를 사용 하면 공유 상태 잠금이 필요 없는 방식으로 공유 리소스에 대 한 액세스를 제공 하 여 제거 합니다. 따라서이 클래스는 여러 스레드에서 공유 데이터에 대 한 액세스를 동기화 하는 뮤텍스 예를 들어 동기화 메커니즘을 사용 하는 대신을 제공 합니다.  
  
###  <a name="a-namecombinable-featuresa-methods-and-features"></a><a name="combinable-features"></a> 메서드 및 기능  
 다음 표에서 중요 한 메서드 중 일부는 `combinable` 클래스입니다. 모든 작업에 대 한 자세한 내용은 `combinable` 클래스 메서드를 참조 하십시오 [combinable 클래스](../../parallel/concrt/reference/combinable-class.md)합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[로컬](../Topic/combinable::local%20Method.md)|현재 스레드 컨텍스트 연관 된 로컬 변수에 대 한 참조를 검색 합니다.|  
|[지우기](../Topic/combinable::clear%20Method.md)|모든 스레드 지역 변수 제거는 `combinable` 개체입니다.|  
|[결합](../Topic/combinable::combine%20Method.md)<br /><br /> [combine_each](../Topic/combinable::combine_each%20Method.md)|제공된 된 combine 함수를 사용 하 여 모든 스레드 로컬 계산 집합에서 마지막 값을 생성 합니다.|  
  
  `combinable` 클래스는 병합 된 최종 결과 대해 매개 변수가 하는 템플릿 클래스입니다. 기본 생성자를 호출 하는 경우는 `T` 템플릿 매개 변수 형식 기본 생성자 및 복사 생성자가 있어야 합니다. 하는 경우는 `T` 템플릿 매개 변수 형식에 기본 생성자가 없는, 해당 매개 변수로 초기화 함수를 사용 하는 생성자의 오버 로드 된 버전을 호출 합니다.  
  
 에 추가 데이터를 저장할 수는 `combinable` 호출한 후 개체는 [결합](../Topic/combinable::combine%20Method.md) 또는 [combine_each](../Topic/combinable::combine_each%20Method.md) 메서드. 호출할 수도 있습니다는 `combine` 및 `combine_each` 메서드를 여러 번입니다. 지역 값의 경우는 `combinable` 개체 변경는 `combine` 및 `combine_each` 메서드가 호출 될 때마다 동일한 결과 생성 합니다.  
  
###  <a name="a-namecombinable-examplesa-examples"></a><a name="combinable-examples"></a> 예제  
 사용 하는 방법에 대 한 예는 `combinable` 클래스에 다음 항목을 참조 하십시오.  
  
-   [방법: combinable 성능을 향상 시키는 사용 하 여](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
  
-   [방법: combinable 집합 결합을 사용 하 여](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
  
 [[맨 위로 이동](#top)]  
  
## <a name="related-topics"></a>관련 항목  
 [방법: 병렬 컨테이너를 사용 하 여 효율성을 높이기 위해](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)  
 병렬 컨테이너를 사용 하 여 효율적으로 저장 하 고 병렬로 데이터를 액세스 하는 방법을 보여 줍니다.  
  
 [방법: combinable 성능을 향상 시키는 사용 하 여](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
 사용 하는 방법을 보여 줍니다는 `combinable` 클래스 공유 상태를 제거 하 고 성능을 향상 시키는 합니다.  
  
 [방법: combinable 집합 결합을 사용 하 여](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
 사용 하는 방법을 보여 줍니다는 `combine` 데이터의 스레드 로컬 집합을 병합 하는 함수입니다.  
  
 [병렬 패턴 라이브러리 PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)  
 동시 응용 프로그램 개발에 대 한 사용 편의성과 확장성을 명령적 프로그래밍 모델을 제공 하는 PPL에 설명 합니다.  
  
## <a name="reference"></a>참조  
 [concurrent_vector 클래스](../../parallel/concrt/reference/concurrent-vector-class.md)  
  
 [concurrent_queue 클래스](../../parallel/concrt/reference/concurrent-queue-class.md)  
  
 [concurrent_unordered_map 클래스](../../parallel/concrt/reference/concurrent-unordered-map-class.md)  
  
 [concurrent_unordered_multimap 클래스](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)  
  
 [concurrent_unordered_set 클래스](../../parallel/concrt/reference/concurrent-unordered-set-class.md)  
  
 [concurrent_unordered_multiset 클래스](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)  
  
 [combinable 클래스](../../parallel/concrt/reference/combinable-class.md)
