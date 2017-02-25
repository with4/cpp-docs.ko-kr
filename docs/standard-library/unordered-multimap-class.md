---
title: "unordered_multimap 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "unordered_map/std::tr1::unordered_multimap"
  - "tr1.unordered_multimap"
  - "unordered_multimap"
  - "std.tr1.unordered_multimap"
  - "tr1::unordered_multimap"
  - "std::tr1::unordered_multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unordered_multimap 클래스"
  - "unordered_multimap 클래스[TR1]"
ms.assetid: 4baead6c-5870-4b85-940f-a47d6b891c27
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# unordered_multimap 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스는 `std::pair<const Key, Ty>` 형식의 다양한 길이의 요소 시퀀스를 제어하는 개체를 설명합니다.  시퀀스는 해시 함수로 약하게 정렬됩니다. 즉, 시퀀스를 버킷이라고 하는 하위 시퀀스의 정렬된 집합으로 분할합니다.  비교 함수는 각 버킷 내에서 요소 쌍이 동일하게 정렬되었는지 여부를 확인합니다.  각 요소는 두 개체, 정렬 키와 값을 저장합니다.  시퀀스는 최소한 모든 버킷이 대략 동일한 크기일 경우 시퀀스의 요소 수와 상관없이 작업 수를 사용하여 임의 요소를 조회, 삽입, 제거하는 방식으로 나타냅니다\(일정 시간\).  모든 요소가 하나의 버킷에 있는 최악의 경우에는 작업 수가 시퀀스의 요소 수에 비례합니다\(선형 시간\).  또한, 요소를 삽입할 경우 어떤 반복기도 무효화되지 않으며, 요소를 제거할 경우 제거된 요소를 가리키고 있는 반복기만 무효화됩니다.  
  
## 구문  
  
```  
template<class Key,  
    class Ty,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<Key> >  
    class unordered_multimap;  
```  
  
#### 매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|`Key`|키 형식입니다.|  
|`Ty`|매핑된 형식입니다.|  
|`Hash`|해시 함수 개체 형식입니다.|  
|`Pred`|같음 비교 함수 개체 형식입니다.|  
|`Alloc`|할당자 클래스입니다.|  
  
## 멤버  
  
|||  
|-|-|  
|형식 정의|설명|  
|[unordered\_multimap::allocator\_type](../Topic/unordered_multimap::allocator_type.md)|저장소 관리를 위한 할당자의 형식입니다.|  
|[unordered\_multimap::const\_iterator](../Topic/unordered_multimap::const_iterator.md)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|[unordered\_multimap::const\_local\_iterator](../Topic/unordered_multimap::const_local_iterator.md)|제어되는 시퀀스에 대한 상수 버킷 반복기의 형식입니다.|  
|[unordered\_multimap::const\_pointer](../Topic/unordered_multimap::const_pointer.md)|요소에 대한 상수 포인터의 형식입니다.|  
|[unordered\_multimap::const\_reference](../Topic/unordered_multimap::const_reference.md)|요소에 대한 상수 참조의 형식입니다.|  
|[unordered\_multimap::difference\_type](../Topic/unordered_multimap::difference_type.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[unordered\_multimap::hasher](../Topic/unordered_multimap::hasher.md)|해시 함수의 형식입니다.|  
|[unordered\_multimap::iterator](../Topic/unordered_multimap::iterator.md)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[unordered\_multimap::key\_equal](../Topic/unordered_multimap::key_equal.md)|비교 함수의 형식입니다.|  
|[unordered\_multimap::key\_type](../Topic/unordered_multimap::key_type.md)|정렬 키의 형식입니다.|  
|[unordered\_multimap::local\_iterator](../Topic/unordered_multimap::local_iterator.md)|제어되는 시퀀스에 대한 버킷 반복기의 형식입니다.|  
|[unordered\_multimap::mapped\_type](../Topic/unordered_multimap::mapped_type.md)|각 키와 연결된 매핑된 값의 형식입니다.|  
|[unordered\_multimap::pointer](../Topic/unordered_multimap::pointer.md)|요소에 대한 포인터의 형식입니다.|  
|[unordered\_multimap::reference](../Topic/unordered_multimap::reference.md)|요소에 대한 참조의 형식입니다.|  
|[unordered\_multimap::size\_type](../Topic/unordered_multimap::size_type.md)|두 요소 사이의 부호가 없는 거리의 형식입니다.|  
|[unordered\_multimap::value\_type](../Topic/unordered_multimap::value_type.md)|요소의 형식입니다.|  
  
|||  
|-|-|  
|멤버 함수|설명|  
|[unordered\_multimap::begin](../Topic/unordered_multimap::begin.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[unordered\_multimap::bucket](../Topic/unordered_multimap::bucket.md)|키 값에 대한 버킷 개수를 가져옵니다.|  
|[unordered\_multimap::bucket\_count](../Topic/unordered_multimap::bucket_count.md)|버킷 개수를 가져옵니다.|  
|[unordered\_multimap::bucket\_size](../Topic/unordered_multimap::bucket_size.md)|버킷의 크기를 가져옵니다.|  
|[unordered\_multimap::cbegin](../Topic/unordered_multimap::cbegin.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[unordered\_multimap::cend](../Topic/unordered_multimap::cend.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[unordered\_multimap::clear](../Topic/unordered_multimap::clear.md)|모든 요소를 제거합니다.|  
|[unordered\_multimap::count](../Topic/unordered_multimap::count.md)|지정한 키와 일치하는 요소의 수를 찾습니다.|  
|[unordered\_multimap::emplace](../Topic/unordered_multimap::emplace.md)|생성된 요소를 추가합니다.|  
|[unordered\_multimap::emplace\_hint](../Topic/unordered_multimap::emplace_hint.md)|힌트와 함께 생성된 요소를 추가합니다.|  
|[unordered\_multimap::empty](../Topic/unordered_multimap::empty.md)|요소가 있는지 여부를 테스트합니다.|  
|[unordered\_multimap::end](../Topic/unordered_multimap::end.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[unordered\_multimap::equal\_range](../Topic/unordered_multimap::equal_range.md)|지정된 키가 일치하는 범위를 찾습니다.|  
|[unordered\_multimap::erase](../Topic/unordered_multimap::erase.md)|지정된 위치에 있는 요소를 제거합니다.|  
|[unordered\_multimap::find](../Topic/unordered_multimap::find.md)|지정된 키와 일치하는 요소를 찾습니다.|  
|[unordered\_multimap::get\_allocator](../Topic/unordered_multimap::get_allocator.md)|저장된 할당자 개체를 가져옵니다.|  
|[unordered\_multimap::hash\_function](../Topic/unordered_multimap::hash_function.md)|저장된 해시 함수 개체를 가져옵니다.|  
|[unordered\_multimap::insert](../Topic/unordered_multimap::insert.md)|요소를 추가합니다.|  
|[unordered\_multimap::key\_eq](../Topic/unordered_multimap::key_eq.md)|저장된 비교 함수 개체를 가져옵니다.|  
|[unordered\_multimap::load\_factor](../Topic/unordered_multimap::load_factor.md)|버킷당 평균 요소 수를 계산합니다.|  
|[unordered\_multimap::max\_bucket\_count](../Topic/unordered_multimap::max_bucket_count.md)|최대 버킷 개수를 가져옵니다.|  
|[unordered\_multimap::max\_load\_factor](../Topic/unordered_multimap::max_load_factor.md)|버킷당 최대 요소 수를 가져오거나 설정합니다.|  
|[unordered\_multimap::max\_size](../Topic/unordered_multimap::max_size.md)|제어된 시퀀스의 최대 크기를 가져옵니다.|  
|[unordered\_multimap::rehash](../Topic/unordered_multimap::rehash.md)|해시 테이블을 다시 빌드합니다.|  
|[unordered\_multimap::size](../Topic/unordered_multimap::size.md)|요소의 수를 셉니다.|  
|[unordered\_multimap::swap](../Topic/unordered_multimap::swap.md)|두 컨테이너의 내용을 바꿉니다.|  
|[unordered\_multimap::unordered\_multimap](../Topic/unordered_multimap::unordered_multimap.md)|컨테이너 개체를 만듭니다.|  
  
|||  
|-|-|  
|연산자|설명|  
|[unordered\_multimap::operator\=](../Topic/unordered_multimap::operator=.md)|해시 테이블을 복사합니다.|  
  
## 설명  
 개체는 저장된 두 개체, [unordered\_multimap::key\_equal](../Topic/unordered_multimap::key_equal.md) 형식의 비교 함수 개체, [unordered\_multimap::hasher](../Topic/unordered_multimap::hasher.md) 형식의 해시 함수 개체를 호출하여 제어하는 시퀀스를 정렬합니다.  첫 번째 저장된 개체는 멤버 함수 [unordered\_multimap::key\_eq](../Topic/unordered_multimap::key_eq.md)`()`를 호출하여 액세스하며, 두 번째 저장된 개체는 멤버 함수 [unordered\_multimap::hash\_function](../Topic/unordered_multimap::hash_function.md)`()`을 호출하여 액세스합니다.  특히 `Key` 형식의 모든 값 `X` 및 `Y`의 경우 두 인수 값이 순서 지정이 동일할 경우 호출 `key_eq()(X, Y)`에서 true를 반환하며, 호출 `hash_function()(keyval)`은 형식 `size_t`의 값 분포를 생성합니다.  템플릿 클래스 [unordered\_map 클래스](../standard-library/unordered-map-class.md)과 달리, 템플릿 클래스 `unordered_multimap`의 개체는 `key_eq()(X, Y)`가 제어된 시퀀스의 두 요소에 대해 항상 false라는 점에 대해 보장하지 않습니다. \(키는 고유할 필요가 없습니다.\)  
  
 개체는 또한 최대 로드 비율\(버킷당 최대 평균 요소 수를 원하는 대로 지정\)를 저장합니다.  요소를 삽입할 때 [unordered\_multimap::load\_factor](../Topic/unordered_multimap::load_factor.md)`()`에서 최대 로드 비율이 초과될 경우 컨테이너는 버킷 수를 증가시키고 필요에 따라 해시 테이블을 다시 빌드합니다.  
  
 제어된 시퀀스의 실제 요소 순서는 해시 함수, 비교 함수, 삽입 순서, 최대 로드 비율, 현재 버킷 수에 따라 달라집니다.  제어된 시퀀스의 요소 순서는 일반적으로 예측할 수 없습니다.  하지만 동일하게 정렬된 요소의 하위 집합은 제어된 시퀀스에서 항상 인접해 있습니다.  
  
 개체는 [unordered\_multimap::allocator\_type](../Topic/unordered_multimap::allocator_type.md) 형식의 저장된 할당자 개체를 통해 제어하는 시퀀스에 대한 저장소를 할당하고 해제합니다.  그러한 할당자 개체는 템플릿 클래스 `allocator`의 개체와 같은 외부 인터페이스가 있어야 합니다.  컨테이너 개체를 할당하는 경우 저장된 할당자 개체는 복사되지 않습니다.  
  
## 요구 사항  
 **헤더:** \<unordered\_map\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<unordered\_map\>](../standard-library/unordered-map.md)   
 [컨테이너](../cpp/containers-modern-cpp.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)