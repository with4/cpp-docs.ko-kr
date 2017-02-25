---
title: "map 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::map"
  - "map/std::map"
  - "map"
  - "std.map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "map 클래스"
ms.assetid: 7876f4c9-ebb4-4878-af1e-09364c43af0a
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# map 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

각 요소가 데이터 값과 정렬 키를 갖고 있는 쌍인 컬렉션에서 데이터의 저장과 검색에 사용됩니다.  키 값은 고유하며 데이터를 자동으로 정렬하는 데 사용됩니다.  
  
 map에 있는 요소의 값은 직접 변경할 수 있습니다.  키 값은 상수이며 변경할 수 없습니다.  대신, 이전 요소와 관련된 키 값은 삭제되어야 하며 새 요소에 대한 새 키 값이 삽입되어야 합니다.  
  
## 구문  
  
```  
template <  
   class Key,   
   class Type,   
   class Traits = less<Key>,   
   class Allocator=allocator<pair <const Key, Type> >   
> class map;  
```  
  
#### 매개 변수  
 `Key`  
 map에 저장되는 키 데이터 형식입니다.  
  
 `Type`  
 map에 저장되는 요소 데이터 형식입니다.  
  
 `Traits`  
 함수 개체를 제공하는 형식은 map 내에서의 상대적인 순서를 결정하는 정렬 키로 두 요소 값을 비교할 수 있습니다.  이 인수는 선택적이며 이진 조건자 `less<``Key``>`가 기본값입니다.  
  
 C\+\+14에서는 형식 매개 변수가 없는 std::less\<\> 조건자를 지정하여 유형이 다른 조회를 사용하도록 설정할 수 있습니다.  자세한 내용은 [연관 컨테이너의 유형이 다른 조회](../standard-library/stl-containers.md#sequence_containers)를 참조하세요.  
  
 `Allocator`  
 map의 메모리 할당 및 할당 취소에 대한 세부 정보를 캡슐화하는 저장된 할당자 개체를 나타내는 형식입니다.  이 인수는 선택 사항이며 기본값은 `allocator<pair` `<const``Key`*,* `Type``> >`입니다.  
  
## 설명  
 STL\(표준 템플릿 라이브러리\) map 클래스는 다음과 같습니다.  
  
-   연결된 키 값을 기반으로 요소 값을 효율적으로 검색하는 다양한 크기의 컨테이너  
  
-   이는 해당 요소에 액세스할 수 있는 양방향 반복기를 제공하기 때문에 되돌릴 수 있습니다.  
  
-   요소가 지정된 비교 함수에 따른 키 값으로 정렬되므로 정렬되어 있습니다.  
  
-   고유합니다.  각 요소에 고유 키가 있어야 하기 때문입니다.  
  
-   요소의 데이터 값은 키 값과 구별되기 때문에 쌍 연관 컨테이너입니다.  
  
-   제공하는 기능은 제네릭이며 요소나 키 형식과 독립적이므로 템플릿 클래스입니다.  요소와 키에 사용되는 데이터 형식은 비교 함수 및 할당자와 함께 클래스 템플릿에서 매개 변수로 지정됩니다.  
  
 map 클래스에서 제공하는 반복기는 양방향 반복기이지만, [insert](../Topic/map::insert.md) 및 [map](../Topic/map::map.md) 클래스 멤버 함수의 버전은 기능 요구 사항이 양방향 반복기 클래스에서 보장하는 것보다 약한 입력 반복기를 템플릿 매개 변수로 사용합니다.  다른 반복기 개념은 상세 기능별로 관련되어 있습니다.  각 반복기 개념에는 고유한 요구 사항 및 그 요구 사항에 의해 제한된 작업을 수행하는 알고리즘이 있습니다.  입력 반복기를 역참조하여 몇 가지 개체를 참조하고 시퀀스의 다음 반복기로 증가될 수 있습니다.  
  
 컨테이너 형식을 선택할 때에는 응용 프로그램에서 요구하는 검색 및 삽입의 종류를 기준으로 하는 것이 좋습니다.  연관 컨테이너는 조회, 삽입 및 제거 작업에 최적화되어 있습니다.  명시적으로 이러한 작업을 지원하는 멤버 함수의 수행 시간은 최악의 경우 컨테이너의 요소 개수를 진수로 하는 로그값에 비례합니다.  요소를 삽입할 경우 어떤 반복기도 무효화되지 않으며, 요소를 제거할 경우 제거된 요소를 명확히 가리키고 있는 반복기만 무효화됩니다.  
  
 값을 키와 연결하는 조건을 응용 프로그램이 충족할 경우 map을 연관 컨테이너로 선택하는 것이 좋습니다.  이러한 형식의 구조체를 위한 모델은 정의를 제공하는 연관 문자열 값이 있고 고유하게 나타나는 키 단어의 정렬된 목록입니다.  하나의 단어에 둘 이상의 올바른 정의가 있는 경우, 즉, 키가 고유하지 않은 경우 multimap은 선택의 컨테이너가 됩니다.  단어의 목록만 저장하려는 경우 set이 적절한 컨테이너일 수 있습니다.  단어가 여러 번 중복 발생하는 것을 허용한 경우 multiset이 적절할 수 있습니다.  
  
 map은 [key\_compare](../Topic/map::key_compare.md) 형식의 저장된 함수 개체를 호출하여 제어하는 요소를 정렬합니다.  이 저장된 개체는 [key\_comp](../Topic/map::key_comp.md) 방법을 호출하여 접근하는 비교 함수입니다.  일반적으로, 주어진 두 개의 요소는 하나의 요소가 다른 요소보다 작은지 또는 둘이 동등한지를 결정하기 위해 비교합니다.  모든 요소가 비교되면 동등하지 않은 요소의 정렬된 시퀀스가 생성됩니다.  
  
> [!NOTE]
>  비교 함수는 표준 수학적 의미에서 엄밀히 약한 정렬을 발생시키는 이진 조건자입니다.  이진 조건자 f\(x,y\)는 두 인수 개체 x 및 y를 가지는 함수 개체이며, `true` 또는 `false` 값을 반환합니다.  이진 조건자가 비재귀적, 비대칭, 전이적인 경우 및 동등성이 전이적인 경우 set에 적용된 정렬은 엄밀히 약한 정렬입니다. 여기서 f\(x,y\) `` 및 f\(y,x\)가 모두 `false`인 경우 두 개체 x 및 y는 동등한 것으로 정의됩니다.  키 사이의 더 강력한 같음 조건이 동등 조건을 대체하는 경우, 정렬은 전체가 되고\(모든 요소가 서로 상대적으로 정렬됨을 의미\) 일치된 키는 서로 구분할 수 없게 됩니다.  
>   
>  C\+\+14에서는 형식 매개 변수가 없는 `std::less<>` 또는 `std::greater<>` 조건자를 지정하여 유형이 다른 조회를 사용하도록 설정할 수 있습니다.  자세한 내용은 [연관 컨테이너의 유형이 다른 조회](../standard-library/stl-containers.md#sequence_containers)를 참조하세요.  
  
## 멤버  
  
### 생성자  
  
|||  
|-|-|  
|[map](../Topic/map::map.md)|특정 크기의 목록 또는 특정 값의 요소 또는 특정 `allocator`가 포함된 목록 또는 다른 map의 복사본으로 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/map::allocator_type.md)|map 개체를 위한 `allocator` 클래스의 typedef|  
|[const\_iterator](../Topic/map::const_iterator.md)|map에서 `const` 요소를 읽을 수 있는 양방향 반복기에 대한 typedef|  
|[const\_pointer](../Topic/map::const_pointer.md)|map의 `const` 요소를 가리키는 포인터에 대한 typedef|  
|[const\_reference](../Topic/map::const_reference.md)|`const` 작업을 읽고 수행하기 위해 map에 저장된 `const` 요소를 참조하기 위한 typedef|  
|[const\_reverse\_iterator](../Topic/map::const_reverse_iterator.md)|map에 있는 모든 `const` 요소를 읽을 수 있는 양방향 반복기를 제공하는 형식|  
|[difference\_type](../Topic/map::difference_type.md)|반복기가 가리키는 요소 사이의 범위에 있는 map의 요소 개수에 대한 부호 있는 정수 typedef|  
|[iterator](../Topic/map::iterator.md)|map의 모든 요소를 읽거나 수정할 수 있는 양방향 반복기를 위한 typedef|  
|[key\_compare](../Topic/map::key_compare.md)|map의 두 요소간 상대적 순서를 결정하는 두 정렬 키를 비교할 수 있는 함수 개체를 위한 typedef|  
|[key\_type](../Topic/map::key_type.md)|각 map 요소에 저장된 정렬 키에 대한 typedef|  
|[mapped\_type](../Topic/map::mapped_type.md)|각 map 요소에 저장된 데이터에 대한 typedef|  
|[포인터](../Topic/map::pointer.md)|map의 `const` 요소를 가리키는 포인터에 대한 typedef|  
|[참조](../Topic/map::reference.md)|map에 저장된 요소에 대한 참조의 typedef|  
|[reverse\_iterator](../Topic/map::reverse_iterator.md)|역순 map의 요소를 읽거나 수정할 수 있는 양방향 반복기를 위한 typedef|  
|[size\_type](../Topic/map::size_type.md)|map의 요소 수에 대한 부호 없는 정수의 typedef|  
|[value\_type](../Topic/map::value_type.md)|map의 요소로 저장된 개체의 형식에 대한 typedef|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[\/](../Topic/map::at.md)|지정된 키 값이 있는 요소를 찾습니다.|  
|[begin](../Topic/map::begin.md)|map의 첫 번째 요소를 가리키는 반복기를 반환합니다.|  
|[cbegin](../Topic/map::cbegin.md)|map의 첫 번째 요소를 가리키는 상수 반복기를 반환합니다.|  
|[cend](../Topic/map::cend.md)|마지막 요소 바로 다음의 상수 반복기를 반환합니다.|  
|[지우기](../Topic/map::clear.md)|map의 모든 요소를 지웁니다.|  
|[count](../Topic/map::count.md)|키가 매개 변수에서 지정한 키와 일치하는 map의 요소 수를 반환합니다.|  
|[crbegin](../Topic/map::crbegin.md)|역순 map에서 첫 번째 요소를 가리키는 상수 반복기를 반환합니다.|  
|[crend](../Topic/map::crend.md)|역순 map의 마지막 요소 바로 다음 위치를 가리키는 상수 반복기를 반환합니다.|  
|[emplace](../Topic/map::emplace.md)|map에 생성된 요소를 삽입합니다.|  
|[emplace\_hint](../Topic/map::emplace_hint.md)|배치 힌트를 사용하여 map에 생성된 요소를 삽입합니다.|  
|[비어 있음](../Topic/map::empty.md)|map이 비어 있으면 `true`를 반환합니다.|  
|[end](../Topic/map::end.md)|마지막 바로 다음 반복기를 반환합니다.|  
|[equal\_range](../Topic/map::equal_range.md)|반복기 쌍을 반환합니다.  `map`에서 지정된 키보다 큰 키가 있는 첫 번째 요소를 가리키는 쌍의 첫 번째 반복기  `map`에서 키보다 크거나 같은 키가 있는 첫 번째 요소를 가리키는 쌍의 두 번째 반복기|  
|[erase](../Topic/map::erase.md)|지정된 위치의 map에서 요소 또는 요소 범위를 제거합니다.|  
|[find](../Topic/map::find.md)|map에서 지정된 키와 같은 키를 가진 요소의 위치를 가리키는 반복기를 반환합니다.|  
|[get\_allocator](../Topic/map::get_allocator.md)|map을 생성하는 데 사용되는 `allocator` 개체의 복사본을 반환합니다.|  
|[삽입](../Topic/map::insert.md)|요소 또는 요소의 범위를 map의 지정된 위치에 삽입합니다.|  
|[key\_comp](../Topic/map::key_comp.md)|map에서 순서 키로 사용되는 비교 개체의 복사본을 반환합니다.|  
|[lower\_bound](../Topic/map::lower_bound.md)|map에서 지정된 키보다 같거나 큰 키 값을 가진 첫 번째 요소에 반복기를 반환합니다.|  
|[max\_size](../Topic/map::max_size.md)|map의 최대 길이를 반환합니다.|  
|[rbegin](../Topic/map::rbegin.md)|역순 map에서 첫 번째 요소를 가리키는 반복기를 반환합니다.|  
|[rend](../Topic/map::rend.md)|역순 map에서 마지막 요소 바로 다음 위치를 가리키는 반복기를 반환합니다.|  
|[size](../Topic/map::size.md)|map에 있는 요소 수를 반환합니다.|  
|[스왑](../Topic/map::swap.md)|두 map의 요소를 교환합니다.|  
|[upper\_bound](../Topic/map::upper_bound.md)|map에서 지정된 키보다 큰 키 값을 가진 첫 번째 요소에 반복기를 반환합니다.|  
|[value\_comp](../Topic/map::value_comp.md)|map에서 요소 값의 정렬에 사용되는 비교 개체의 복사본을 검색합니다.|  
  
### 운영자  
  
|||  
|-|-|  
|[operator&#91;&#93;](../Topic/map::operator[].md)|지정된 키 값을 사용하여 map에 요소를 삽입합니다.|  
|[연산자 \=](../Topic/map::operator=.md)|map의 요소를 다른 map의 복사본으로 대체합니다.|  
  
## 요구 사항  
 **헤더:** \<map\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<map\> Members](http://msdn.microsoft.com/ko-kr/7e8f0bc2-6034-40f6-9d14-76d4cef86308)   
 [컨테이너](../cpp/containers-modern-cpp.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)