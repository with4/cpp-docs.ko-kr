---
title: "concurrent_unordered_multiset 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concurrent_unordered_set/concurrency::concurrent_unordered_multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_unordered_multiset 클래스"
ms.assetid: 219d7d67-1ff0-45f4-9400-e9cc272991a4
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# concurrent_unordered_multiset 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`concurrent_unordered_multiset` 클래스는 \_Key형식 요소의 다양한 길이의 시퀀스를 제어하는 동시성 안전 컨테이너입니다.  시퀀스는 동시성이 보장된 추가, 요소 액세스, 반복기 액세스 및 반복기 통과 작업을 활성화하는 방식으로 표현됩니다.  
  
## 구문  
  
```  
template <  
   typename _Key_type,  
   typename _Hasher = std::tr1::hash<_Key_type>,  
   typename _Key_equality = std::equal_to<_Key_type>,  
   typename _Allocator_type = std::allocator<_Key_type>  
>  
, typename _Key_equality = std::equal_to<_Key_type>, typename _Allocator_type = std::allocator<_Key_type> > class concurrent_unordered_multiset : public details::_Concurrent_hash< details::_Concurrent_unordered_set_traits<_Key_type, details::_Hash_compare<_Key_type, _Hasher, _Key_equality>, _Allocator_type, true> >;  
```  
  
#### 매개 변수  
 `_Key_type`  
 키 형식입니다.  
  
 `_Hasher`  
 해시 함수 개체 형식입니다.  이 인수는 선택적 요소이며 기본값은 `std::tr1::hash<``_Key_type``>`입니다.  
  
 `_Key_equality`  
 같음 비교 함수 개체 형식.  이 인수는 선택적 요소이며 기본값은 `std::equal_to<``_Key_type``>`입니다.  
  
 `_Allocator_type`  
 동시 벡터를 위한 할당 및 할당 취소에 대한 세부 정보를 캡슐화하는 저장된 할당기 개체를 나타내는 형식입니다.  이 인수는 선택적 요소이며 기본값은 `std::allocator<``_Key_type``>`입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`allocator_type`|저장소 관리를 위한 할당자의 형식입니다.|  
|`const_iterator`|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|`const_local_iterator`|제어되는 시퀀스에 대한 상수 버킷 반복기의 형식입니다.|  
|`const_pointer`|요소에 대한 상수 포인터의 형식입니다.|  
|`const_reference`|요소에 대한 상수 참조의 형식입니다.|  
|`difference_type`|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|`hasher`|해시 함수의 형식입니다.|  
|`iterator`|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|`key_equal`|비교 함수의 형식입니다.|  
|`key_type`|정렬 키의 형식입니다.|  
|`local_iterator`|제어되는 시퀀스에 대한 버킷 반복기의 형식입니다.|  
|`pointer`|요소에 대한 포인터의 형식입니다.|  
|`reference`|요소에 대한 참조의 형식입니다.|  
|`size_type`|두 요소 사이의 부호가 없는 거리의 형식입니다.|  
|`value_type`|요소의 형식입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[concurrent\_unordered\_multiset::concurrent\_unordered\_multiset 생성자](../Topic/concurrent_unordered_multiset::concurrent_unordered_multiset%20Constructor.md)|오버로드됨.  순서가 지정되지 않은 동시 멀티셋을 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[concurrent\_unordered\_multiset::hash\_function 메서드](../Topic/concurrent_unordered_multiset::hash_function%20Method.md)|저장된 해시 함수 코드 개체를 반환합니다.|  
|[concurrent\_unordered\_multiset::insert 메서드](../Topic/concurrent_unordered_multiset::insert%20Method.md)|오버로드됨.  `concurrent_unordered_multiset` 개체에 요소를 추가합니다.|  
|[concurrent\_unordered\_multiset::key\_eq 메서드](../Topic/concurrent_unordered_multiset::key_eq%20Method.md)|저장된 같음 비교 함수 개체입니다.|  
|[concurrent\_unordered\_multiset::swap 메서드](../Topic/concurrent_unordered_multiset::swap%20Method.md)|두 `concurrent_unordered_multiset` 개체의 내용을 바꿉니다.  이 메서드는 동시성이 보장되지 않습니다.|  
|[concurrent\_unordered\_multiset::unsafe\_erase 메서드](../Topic/concurrent_unordered_multiset::unsafe_erase%20Method.md)|오버로드됨.  지정된 위치에 있는 `concurrent_unordered_multiset`에서 요소를 제거합니다.  이 메서드는 동시성이 보장되지 않습니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[concurrent\_unordered\_multiset::operator\= 연산자](../Topic/concurrent_unordered_multiset::operator=%20Operator.md)|오버로드됨.  다른 `concurrent_unordered_multiset` 개체의 내용을 여기에 할당합니다.  이 메서드는 동시성이 보장되지 않습니다.|  
  
## 설명  
 `concurrent_unordered_multiset`에 대한 자세한 내용은 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)를 참조하십시오.  
  
## 상속 계층  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_multiset`  
  
## 요구 사항  
 **헤더:** concurrent\_unordered\_set.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)