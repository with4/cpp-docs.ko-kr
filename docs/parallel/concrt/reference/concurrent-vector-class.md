---
title: "concurrent_vector 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concurrent_vector/Concurrency::concurrent_vector"
  - "concurrent_vector/concurrency::concurrent_vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_vector 클래스"
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# concurrent_vector 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`concurrent_vector` 클래스는 모든 요소에 대한 임의 액세스를 허용하는 시퀀스 컨테이너 클래스입니다.  동시성이 보장된 추가, 요소 액세스, 반복기 액세스 및 반복기 통과 작업을 활성화합니다.  
  
## 구문  
  
```  
template<  
   typename _Ty,  
   class _Ax  
>  
class concurrent_vector: protected details::_Allocator_base<_Ty, _Ax>, private details::_Concurrent_vector_base_v4;  
```  
  
#### 매개 변수  
 `_Ty`  
 벡터에 저장될 요소의 데이터 형식입니다.  
  
 `_Ax`  
 동시 벡터를 위한 할당 및 할당 취소에 대한 세부 정보를 캡슐화하는 저장된 할당기 개체를 나타내는 형식입니다.  이 인수는 선택적 요소이며 기본값은 `allocator<``_Ty``>`입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`allocator_type`|동시 벡터의 할당자 클래스를 나타내는 형식입니다.|  
|`const_iterator`|동시 벡터에 있는 `const` 요소를 읽을 수 있는 임의 액세스 반복기를 제공하는 형식입니다.|  
|`const_pointer`|동시 벡터에 있는 `const` 요소에 대한 포인터를 제공하는 형식입니다.|  
|`const_reference`|`const` 작업을 읽고 수행하기 위해 동시 벡터에 저장된 `const` 요소에 대한 참조를 제공하는 형식입니다.|  
|`const_reverse_iterator`|동시 벡터에 있는 모든 `const` 요소를 읽을 수 있는 임의 액세스 반복기를 제공하는 형식입니다.|  
|`difference_type`|동시 벡터에 있는 두 요소 사이의 부호가 있는 거리를 제공하는 형식입니다.|  
|`iterator`|동시 벡터에 있는 모든 요소를 읽을 수 있는 임의 액세스 반복기를 제공하는 형식입니다.  반복기를 사용한 요소의 수정은 동시성이 보장되지 않습니다.|  
|`pointer`|동시 벡터에 있는 요소에 대한 포인터를 제공하는 형식입니다.|  
|`reference`|동시 벡터에 저장된 요소에 대한 참조를 제공하는 형식입니다.|  
|`reverse_iterator`|역방향 동시 벡터에 있는 모든 요소를 읽을 수 있는 임의 액세스 반복기를 제공하는 형식입니다.  반복기를 사용한 요소의 수정은 동시성이 보장되지 않습니다.|  
|`size_type`|동시 벡터에 있는 요소의 수를 세는 형식입니다.|  
|`value_type`|동시 벡터에 저장된 데이터 형식을 나타내는 형식입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[concurrent\_vector::concurrent\_vector 생성자](../Topic/concurrent_vector::concurrent_vector%20Constructor.md)|오버로드됨.  동시 벡터를 생성합니다.|  
|[concurrent\_vector::~concurrent\_vector 소멸자](../Topic/concurrent_vector::~concurrent_vector%20Destructor.md)|모든 요소를 지우고 이 동시 벡터 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[concurrent\_vector::assign 메서드](../Topic/concurrent_vector::assign%20Method.md)|오버로드됨.  동시 벡터의 요소를 삭제하고 `_Item`의 `_N` 복사본 또는 반복기 범위 \[`_Begin`, `_End`\)에 지정된 값을 할당합니다.  이 메서드는 동시성이 보장되지 않습니다.|  
|[concurrent\_vector::at 메서드](../Topic/concurrent_vector::at%20Method.md)|오버로드됨.  동시 벡터에 지정된 인덱스에 있는 요소에 대한 액세스를 제공합니다.  이 메서드는 읽기 작업의 경우 동시성이 보장되며 벡터가 커지는 동안 값 `_Index`가 동시 벡터 크기보다 작도록 해줍니다.|  
|[concurrent\_vector::back 메서드](../Topic/concurrent_vector::back%20Method.md)|오버로드됨.  동시 벡터에서 마지막 요소에 대한 참조 또는 `const` 참조를 반환합니다.  동시 벡터가 비어 있는 경우 반환 값은 정의되지 않습니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::begin 메서드](../Topic/concurrent_vector::begin%20Method.md)|오버로드됨.  동시 벡터의 시작 부분에 대한 형식 `iterator` 또는 `const_iterator`의 반복기를 반환합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::capacity 메서드](../Topic/concurrent_vector::capacity%20Method.md)|동시 벡터가 더 많은 메모리를 할당하지 않고도 확장할 수 있는 최대 크기를 반환합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::cbegin 메서드](../Topic/concurrent_vector::cbegin%20Method.md)|동시 벡터의 시작 부분에 대한 형식 `const_iterator`의 반복기를 반환합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::cend 메서드](../Topic/concurrent_vector::cend%20Method.md)|동시 벡터의 끝 부분에 대한 형식 `const_iterator`의 반복기를 반환합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::clear 메서드](../Topic/concurrent_vector::clear%20Method.md)|동시 벡터의 모든 요소를 지웁니다.  이 메서드는 동시성이 보장되지 않습니다.|  
|[concurrent\_vector::crbegin 메서드](../Topic/concurrent_vector::crbegin%20Method.md)|동시 벡터의 시작 부분에 대한 형식 `const_reverse_iterator`의 반복기를 반환합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::crend 메서드](../Topic/concurrent_vector::crend%20Method.md)|동시 벡터의 끝 부분에 대한 형식 `const_reverse_iterator`의 반복기를 반환합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::empty 메서드](../Topic/concurrent_vector::empty%20Method.md)|이 메서드가 호출될 때 동시 벡터가 비어 있는지 테스트합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::end 메서드](../Topic/concurrent_vector::end%20Method.md)|오버로드됨.  동시 벡터의 끝 부분에 대한 형식 `iterator` 또는 `const_iterator`의 반복기를 반환합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::front 메서드](../Topic/concurrent_vector::front%20Method.md)|오버로드됨.  동시 벡터에서 첫 번째 요소에 대한 참조 또는 `const` 참조를 반환합니다.  동시 벡터가 비어 있는 경우 반환 값은 정의되지 않습니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::get\_allocator 메서드](../Topic/concurrent_vector::get_allocator%20Method.md)|동시 벡터를 생성하는 데 사용되는 할당자 복사본을 반환합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::grow\_by 메서드](../Topic/concurrent_vector::grow_by%20Method.md)|오버로드됨.  `_Delta` 요소에 의해 이 동시 벡터가 확장됩니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::grow\_to\_at\_least 메서드](../Topic/concurrent_vector::grow_to_at_least%20Method.md)|최소한 `_N` 요소가 있을 때까지 이 동시 벡터가 확장됩니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::max\_size 메서드](../Topic/concurrent_vector::max_size%20Method.md)|동시 벡터가 저장할 수 있는 요소의 최대 수를 반환합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::push\_back 메서드](../Topic/concurrent_vector::push_back%20Method.md)|오버로드됨.  지정된 항목을 동시 벡터 끝에 추가합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::rbegin 메서드](../Topic/concurrent_vector::rbegin%20Method.md)|오버로드됨.  동시 벡터의 시작 부분에 대한 형식 `reverse_iterator` 또는 `const_reverse_iterator`의 반복기를 반환합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::rend 메서드](../Topic/concurrent_vector::rend%20Method.md)|오버로드됨.  동시 벡터의 끝 부분에 대한 형식 `reverse_iterator` 또는 `const_reverse_iterator`의 반복기를 반환합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::reserve 메서드](../Topic/concurrent_vector::reserve%20Method.md)|나중에 더 많은 메모리를 할당하지 않고도 동시 벡터를 크기 `_N`으로 확장하기에 충분한 공간을 할당합니다.  이 메서드는 동시성이 보장되지 않습니다.|  
|[concurrent\_vector::resize 메서드](../Topic/concurrent_vector::resize%20Method.md)|오버로드됨.  필요에 따라 요소를 삭제하거나 추가하여 동시 벡터의 크기를 요청한 크기로 변경합니다.  이 메서드는 동시성이 보장되지 않습니다.|  
|[concurrent\_vector::shrink\_to\_fit 메서드](../Topic/concurrent_vector::shrink_to_fit%20Method.md)|조각화를 줄이고 메모리 사용을 최적화하기 위해 동시 벡터의 내부 표현을 압축합니다.  이 메서드는 동시성이 보장되지 않습니다.|  
|[concurrent\_vector::size 메서드](../Topic/concurrent_vector::size%20Method.md)|동시 벡터에 있는 요소의 수를 반환합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_vector::swap 메서드](../Topic/concurrent_vector::swap%20Method.md)|두 개의 동시 벡터 내용을 바꿉니다.  이 메서드는 동시성이 보장되지 않습니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[concurrent\_vector::operatorOperator](../Topic/concurrent_vector::operatorOperator.md)|오버로드됨.  동시 벡터에 지정된 인덱스에 있는 요소에 대한 액세스를 제공합니다.  이 메서드는 읽기 작업의 경우 동시성이 보장되며 벡터가 커지는 동안 값 `_Index`가 동시 벡터 크기보다 작도록 해줍니다.|  
|[concurrent\_vector::operator\= 연산자](../Topic/concurrent_vector::operator=%20Operator.md)|오버로드됨.  다른 `concurrent_vector` 개체의 내용을 여기에 할당합니다.  이 메서드는 동시성이 보장되지 않습니다.|  
  
## 설명  
 `concurrent_vector`에 대한 자세한 내용은 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)를 참조하십시오.  
  
## 상속 계층  
 `_Concurrent_vector_base_v4`  
  
 `_Allocator_base`  
  
 `concurrent_vector`  
  
## 요구 사항  
 **헤더:** concurrent\_vector.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)