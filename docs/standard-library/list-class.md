---
title: "list 클래스 | Microsoft Docs"
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
  - "std.list"
  - "list"
  - "std::list"
  - "list/std::list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "list 클래스"
ms.assetid: d3707f4a-10fd-444f-b856-f9ca2077c1cd
caps.latest.revision: 20
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# list 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

STL 목록 클래스는 선형 배열에서 해당 요소를 유지 관리하고 시퀀스 내 모든 위치에서 효율적인 삽입과 삭제를 수행할 수 있도록 하는 시퀀스 컨테이너의 템플릿 클래스입니다.  시퀀스는 양방향으로 링크된 요소의 목록으로 저장됩니다. 이러한 요소는 각각 특정 *Type* 형식의 멤버를 포함합니다.  
  
## 구문  
  
```cpp  
  
template <    class Type,     class Allocator=allocator<Type>  > class list  
```  
  
#### 매개 변수  
 *형식*  
 목록에 저장되는 요소 데이터 형식입니다.  
  
 `Allocator`  
 목록의 메모리 할당 및 할당 취소에 대한 세부 정보를 캡슐화하는 저장된 할당자 개체를 나타내는 형식입니다.  이 인수는 선택 사항이며 기본값은 **allocator**\<*Type*\>*입니다.*  
  
## 설명  
 컨테이너 형식은 일반적으로 응용 프로그램에서 필요한 검색과 삽입의 형식을 기준으로 선택해야 합니다.  요소에 대한 임의 액세스는 거의 발생하지 않으며 요소 삽입 또는 삭제는 시퀀스 끝에서만 수행하면 되는 시퀀스를 관리할 때는 벡터를 기본 컨테이너로 사용해야 합니다.  임의 액세스가 필요하며 시퀀스 시작과 끝의 삽입 및 삭제는 거의 수행되지 않는 경우에는 deque 클래스 컨테이너의 성능이 보다 뛰어납니다.  
  
 목록 멤버 함수 [merge](../Topic/list::merge.md), [reverse](../Topic/list::reverse.md), [unique](../Topic/list::unique.md), [remove](../Topic/list::remove.md) 및 [remove\_if](../Topic/list::remove_if.md)는 목록 개체에 대한 작업을 위해 최적화되었으며, 동일한 제네릭 함수에 비해 성능이 우수합니다.  
  
 멤버 함수가 목록의 요소를 삽입하거나 지워야 하면 목록 다시 할당이 수행됩니다.  이러한 모든 경우에는 제어되는 시퀀스의 지워지는 부분을 가리키는 반복기 또는 참조만 유효하지 않은 상태가 됩니다.  
  
 [컨테이너](../standard-library/stl-containers.md) 템플릿 클래스 목록과 여러 지원 템플릿을 정의하려면 STL 표준 헤더 \<list\>를 포함합니다.  
  
### 생성자  
  
|||  
|-|-|  
|[list](../Topic/list::list.md)|특정 크기의 목록 또는 특정 값의 요소나 특정 `allocator`가 포함된 목록을 다른 목록의 복사본으로 생성합니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[allocator\_type](../Topic/list::allocator_type.md)|목록 개체의 `allocator` 클래스를 나타내는 형식입니다.|  
|[const\_iterator](../Topic/list::const_iterator.md)|목록의 `const` 요소 하나를 읽을 수 있는 양방향 반복기를 제공하는 형식입니다.|  
|[const\_pointer](../Topic/list::const_pointer.md)|목록의 `const` 요소에 대한 포인터를 제공하는 형식입니다.|  
|[const\_reference](../Topic/list::const_reference.md)|`const` 작업을 읽고 수행하기 위해 목록에 저장된 `const` 요소에 대한 참조를 제공하는 형식입니다.|  
|[const\_reverse\_iterator](../Topic/list::const_reverse_iterator.md)|목록의 모든 `const` 요소를 읽을 수 있는 양방향 반복기를 제공하는 형식입니다.|  
|[difference\_type](../Topic/list::difference_type.md)|동일한 목록 내의 요소를 참조하는 두 반복기 사이의 차이를 제공하는 형식입니다.|  
|[iterator](../Topic/list::iterator.md)|목록에 있는 모든 요소를 읽거나 수정할 수 있는 양방향 반복기를 제공하는 형식입니다.|  
|[포인터](../Topic/list::pointer.md)|목록의 요소에 대한 포인터를 제공하는 형식입니다.|  
|[참조](../Topic/list::reference.md)|`const` 작업을 읽고 수행하기 위해 목록에 저장된 `const` 요소에 대한 참조를 제공하는 형식입니다.|  
|[reverse\_iterator](../Topic/list::reverse_iterator.md)|역방향 목록의 요소를 읽거나 수정할 수 있는 양방향 반복기를 제공하는 형식입니다.|  
|[size\_type](../Topic/list::size_type.md)|목록의 요소 수를 계산하는 형식입니다.|  
|[value\_type](../Topic/list::value_type.md)|목록에 저장된 데이터 형식을 나타내는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[assign](../Topic/list::assign.md)|목록에서 요소를 삭제하고 대상 목록에 요소의 새 집합을 복사합니다.|  
|[back](../Topic/list::back.md)|목록의 마지막 요소에 대한 참조를 반환합니다.|  
|[begin](../Topic/list::begin.md)|목록에서 첫 번째 요소의 주소를 지정하는 반복기를 반환합니다.|  
|[list::cbegin](../Topic/list::cbegin.md)|목록에서 첫 번째 요소의 주소를 지정하는 const 반복기를 반환합니다.|  
|[list::cend](../Topic/list::cend.md)|목록에서 마지막 요소 다음에 나오는 위치의 주소를 지정하는 const 반복기를 반환합니다.|  
|[list::clear](../Topic/list::clear.md)|목록의 모든 요소를 지웁니다.|  
|[list::crbegin](../Topic/list::crbegin.md)|역방향 목록에서 첫 번째 요소의 주소를 지정하는 const 반복기를 반환합니다.|  
|[list::crend](../Topic/list::crend.md)|역방향 목록에서 마지막 요소 다음에 나오는 위치의 주소를 지정하는 상수 반복기를 반환합니다.|  
|[list::emplace](../Topic/list::emplace.md)|생성된 요소를 목록의 지정된 위치에 삽입합니다.|  
|[list::emplace\_back](../Topic/list::emplace_back.md)|생성된 요소를 목록 끝부분에 추가합니다.|  
|[list::emplace\_front](../Topic/list::emplace_front.md)|생성된 요소를 목록 시작 부분에 추가합니다.|  
|[empty](../Topic/list::empty.md)|목록이 비어 있는지 여부를 테스트합니다.|  
|[end](../Topic/list::end.md)|목록에서 마지막 요소 다음에 나오는 위치의 주소를 지정하는 반복기를 반환합니다.|  
|[erase](../Topic/list::erase.md)|목록의 지정된 위치에서 요소 또는 요소 범위를 제거합니다.|  
|[front](../Topic/list::front.md)|목록의 첫 번째 요소에 대한 참조를 반환합니다.|  
|[get\_allocator](../Topic/list::get_allocator.md)|목록을 생성하는 데 사용된 `allocator` 개체의 복사본을 반환합니다.|  
|[insert](../Topic/list::insert.md)|요소 하나 또는 여러 개나 요소의 범위를 목록의 지정된 위치에 삽입합니다.|  
|[max\_size](../Topic/list::max_size.md)|목록의 최대 길이를 반환합니다.|  
|[merge](../Topic/list::merge.md)|요소를 인수 목록에서 제거하고 대상 목록에 삽입한 다음 새로 조합된 요소 집합을 오름차순 또는 기타 지정된 순서로 정렬합니다.|  
|[pop\_back](../Topic/list::pop_back.md)|목록의 끝에 있는 요소를 삭제합니다.|  
|[pop\_front](../Topic/list::pop_front.md)|목록의 시작 부분에 있는 요소를 삭제합니다.|  
|[push\_back](../Topic/list::push_back.md)|목록의 끝에 요소를 추가합니다.|  
|[push\_front](../Topic/list::push_front.md)|목록의 시작 부분에 요소를 추가합니다.|  
|[rbegin](../Topic/list::rbegin.md)|역방향 목록에서 첫 번째 요소의 주소를 지정하는 반복기를 반환합니다.|  
|[remove](../Topic/list::remove.md)|목록에서 지정된 값과 일치하는 요소를 지웁니다.|  
|[remove\_if](../Topic/list::remove_if.md)|지정된 조건자를 충족하는 요소를 목록에서 지웁니다.|  
|[rend](../Topic/list::rend.md)|역방향 목록에서 마지막 요소 다음에 나오는 위치의 주소를 지정하는 반복기를 반환합니다.|  
|[resize](../Topic/list::resize.md)|목록의 새 크기를 지정합니다.|  
|[reverse](../Topic/list::reverse.md)|목록에 요소가 나타나는 순서를 반대로 바꿉니다.|  
|[size](../Topic/list::size.md)|목록에 있는 요소 수를 반환합니다.|  
|[sort](../Topic/list::sort.md)|오름차순 또는 기타 순서 관계를 기준으로 목록의 요소를 정렬합니다.|  
|[splice](../Topic/list::splice.md)|인수 목록에서 요소를 제거하고 대상 목록에 삽입합니다.|  
|[스왑](../Topic/list::swap.md)|두 목록의 요소를 교환합니다.|  
|[unique](../Topic/list::unique.md)|목록에서 인접하는 중복 요소 또는 기타 이진 조건자를 충족하는 인접 요소를 제거합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[list::operator\=](../Topic/list::operator=.md)|목록의 요소를 다른 목록의 복사본으로 바꿉니다.|  
  
## 요구 사항  
 **헤더**: \<list\>  
  
## 참고 항목  
 [\<list\>](../standard-library/list.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)