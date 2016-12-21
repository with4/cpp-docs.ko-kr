---
title: "forward_list 클래스 | Microsoft Docs"
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
  - "std::forward_list"
  - "forward_list"
  - "forward_list/std::forward_list"
  - "std.forward_list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "forward_list 클래스"
ms.assetid: 89a3b805-ab60-4858-b772-5855130c11b1
caps.latest.revision: 25
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# forward_list 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다양한 길이의 요소 시퀀스를 제어하는 개체를 설명합니다.  각각 `Type` 형식의 멤버를 포함하는 노드의 단일 연결 목록으로 시퀀스가 저장됩니다.  
  
## 구문  
  
```  
template<  
    class Type,   
    class Allocator = allocator<Type>   
>  
class forward_list   
```  
  
#### 매개 변수  
  
|매개 변수|설명|  
|-----------|--------|  
|`Type`|forward\_list에 저장되는 요소 데이터 형식입니다.|  
|`Allocator`|forward\_list의 메모리 할당 및 할당 취소에 대한 세부 정보를 캡슐화하는 저장된 할당자 개체입니다.  이 매개 변수는 선택적 요소입니다.  기본값은 allocator\<`Type`\>입니다.|  
  
## 설명  
 `forward_list` 개체는 [allocator 클래스](../standard-library/allocator-class.md)\(일반적으로 `std::allocator)`라고 함\)를 기반으로 하는 `Allocator` 클래스의 저장된 개체를 통해 제어하는 시퀀스에 대한 저장소를 할당 및 해제합니다.  자세한 내용은 [Allocators](../standard-library/allocators.md)를 참조하세요.  할당자 개체는 템플릿 클래스 `allocator`의 개체와 같은 외부 인터페이스가 있어야 합니다.  
  
> [!NOTE]
>  컨테이너 개체를 할당하는 경우 저장된 할당자 개체는 복사되지 않습니다.  
  
 `forward_list`를 통해 제어되는 시퀀스의 요소를 지울 경우 반복기, 포인터 및 참조가 무효화될 수도 있습니다.  `forward_list`를 통해 제어되는 시퀀스에서 수행되는 삽입 및 스플라이스는 반복기를 무효화하지 않습니다.  
  
 제어되는 시퀀스에 대한 추가는 `Type(const _Type&)` 생성자를 호출하는 유일한 멤버 함수인 [forward\_list::insert\_after](../Topic/forward_list::insert_after.md)를 호출하여 발생할 수 있습니다.  `forward_list`는 이동 생성자를 호출할 수도 있습니다.  이러한 식에서 예외가 발생하는 경우 컨테이너 개체는 새 요소를 삽입하지 않고 예외를 다시 발생시킵니다.  따라서 이러한 예외가 발생하면 템플릿 클래스 `forward_list`의 개체가 알려진 상태로 유지됩니다.  
  
### 생성자  
  
|||  
|-|-|  
|[forward\_list](../Topic/forward_list::forward_list.md)|`forward_list` 형식의 개체를 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/forward_list::allocator_type.md)|정방향 목록 개체의 할당자 클래스를 나타내는 형식입니다.|  
|[const\_iterator](../Topic/forward_list::const_iterator.md)|정방향 목록에 대한 상수 반복기를 제공하는 형식입니다.|  
|[const\_pointer](../Topic/forward_list::const_pointer.md)|정방향 목록의 `const` 요소에 대한 포인터를 제공하는 형식입니다.|  
|[const\_reference](../Topic/forward_list::const_reference.md)|정방향 목록의 요소에 대한 상수 참조를 제공하는 형식입니다.|  
|[difference\_type](../Topic/forward_list::difference_type.md)|반복기가 가리키는 요소 사이의 범위에 있는 정방향 목록의 요소 수를 나타내는 데 사용할 수 있는 부호 있는 정수 형식입니다.|  
|[iterator](../Topic/forward_list::iterator.md)|정방향 목록에 대한 반복기를 제공하는 형식입니다.|  
|[포인터](../Topic/forward_list::pointer.md)|정방향 목록의 요소에 대한 포인터를 제공하는 형식입니다.|  
|[참조](../Topic/forward_list::reference.md)|정방향 목록의 요소에 대한 참조를 제공하는 형식입니다.|  
|[size\_type](../Topic/forward_list::size_type.md)|두 요소 사이의 부호가 없는 거리를 나타내는 형식입니다.|  
|[value\_type](../Topic/forward_list::value_type.md)|정방향 목록에 저장된 요소의 형식을 나타내는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[assign](../Topic/forward_list::assign.md)|정방향 목록에서 요소를 삭제하고 대상 정방향 목록에서 요소의 새 집합을 복사합니다.|  
|[before\_begin](../Topic/forward_list::before_begin.md)|정방향 목록에서 첫 번째 요소 앞의 위치에 주소를 지정하는 반복기를 반환합니다.|  
|[begin](../Topic/forward_list::begin.md)|정방향 목록에서 첫 번째 요소의 주소를 지정하는 반복기를 반환합니다.|  
|[cbefore\_begin](../Topic/forward_list::cbefore_begin.md)|정방향 목록에서 첫 번째 요소 앞의 위치에 주소를 지정하는 const 반복기를 반환합니다.|  
|[cbegin](../Topic/forward_list::cbegin.md)|정방향 목록에서 첫 번째 요소의 주소를 지정하는 const 반복기를 반환합니다.|  
|[cend](../Topic/forward_list::cend.md)|정방향 목록에서 마지막 요소 다음에 나오는 위치의 주소를 지정하는 const 반복기를 반환합니다.|  
|[지우기](../Topic/forward_list::clear.md)|정방향 목록의 모든 요소를 지웁니다.|  
|[emplace\_after](../Topic/forward_list::emplace_after.md)|이동 후 지정된 위치 뒤에 새 요소를 생성합니다.|  
|[emplace\_front](../Topic/forward_list::emplace_front.md)|생성된 요소를 목록 시작 부분에 추가합니다.|  
|[비어 있음](../Topic/forward_list::empty.md)|정방향 목록이 비어 있는지 테스트합니다.|  
|[end](../Topic/forward_list::end.md)|정방향 목록에서 마지막 요소 다음에 나오는 위치의 주소를 지정하는 반복기를 반환합니다.|  
|[erase\_after](../Topic/forward_list::erase_after.md)|정방향 목록의 지정된 위치 뒤에서 요소를 제거합니다.|  
|[front](../Topic/forward_list::front.md)|정방향 목록의 첫 번째 요소에 대한 참조를 반환합니다.|  
|[get\_allocator](../Topic/forward_list::get_allocator.md)|정방향 목록을 생성하는 데 사용되는 할당자 개체의 복사본을 반환합니다.|  
|[insert\_after](../Topic/forward_list::insert_after.md)|정방향 목록의 지정된 위치 뒤에 요소를 추가합니다.|  
|[max\_size](../Topic/forward_list::max_size.md)|정방향 목록의 최대 길이를 반환합니다.|  
|[병합](../Topic/forward_list::merge.md)|요소를 인수 목록에서 제거하고 대상 정방향 목록에 삽입한 다음 새로 조합된 요소 집합을 오름차순 또는 기타 지정된 순서로 정렬합니다.|  
|[pop\_front](../Topic/forward_list::pop_front.md)|정방향 목록의 시작 부분에 있는 요소를 삭제합니다.|  
|[push\_front](../Topic/forward_list::push_front.md)|정방향 목록의 시작 부분에 요소를 추가합니다.|  
|[remove](../Topic/forward_list::remove.md)|정방향 목록에서 지정된 값과 일치하는 요소를 지웁니다.|  
|[remove\_if](../Topic/forward_list::remove_if.md)|지정된 조건자를 충족하는 요소를 정방향 목록에서 지웁니다.|  
|[크기 조정](../Topic/forward_list::resize.md)|정방향 목록의 새 크기를 지정합니다.|  
|[reverse](../Topic/forward_list::reverse.md)|정방향 목록에 요소가 나타나는 순서를 반대로 바꿉니다.|  
|[sort](../Topic/forward_list::sort.md)|오름차순 또는 조건자를 통해 지정된 순서로 요소를 정렬합니다.|  
|[splice\_after](../Topic/forward_list::splice_after.md)|노드 간의 연결을 다시 붙입니다.|  
|[스왑](../Topic/forward_list::swap.md)|두 정방향 목록의 요소를 교환합니다.|  
|[unique](../Topic/forward_list::unique.md)|지정된 테스트를 통과하는 인접 요소를 제거합니다.|  
  
### 운영자  
  
|||  
|-|-|  
|[연산자 \=](../Topic/forward_list::operator=.md)|정방향 목록의 요소를 다른 정방향 목록의 복사본으로 바꿉니다.|  
  
## 요구 사항  
 **헤더:** \<forward\_list\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<forward\_list\>](../standard-library/forward-list.md)