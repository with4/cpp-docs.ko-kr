---
title: "multimap 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "multimap"
  - "std.multimap"
  - "map/std::multimap"
  - "std::multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multimap 클래스"
ms.assetid: 8796ae05-37c4-475a-9e61-75fde9d4a463
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# multimap 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

표준 템플릿 라이브러리 multimap 클래스는 각 요소가 데이터 값과 정렬 키를 갖고 있는 쌍인 컬렉션에서 데이터의 저장과 검색에 사용됩니다.  키 값은 고유할 필요가 없으며 데이터를 자동으로 정렬하는 데 사용됩니다.  multimap 요소의 값은 연관된 키 값을 제외하고 직접적으로 변경할 수 있습니다.  대신, 이전 요소와 관련된 키 값을 삭제하고 새 요소와 연결된 새 키 값을 삽입해야 합니다.  
  
## 구문  
  
```  
template <  
   class Key,   
   class Type,   
   class Traits=less<Key>,   
   class Allocator=allocator<pair <const Key, Type> >   
> class multimap;  
```  
  
#### 매개 변수  
 `Key`  
 multimap에 저장되는 키 데이터 형식입니다.  
  
 `Type`  
 multimap에 저장되는 요소 데이터 형식입니다.  
  
 `Traits`  
 함수 개체를 제공하는 형식은 multimap 내에서의 상대적인 순서를 결정하는 정렬 키로 두 요소 값을 비교할 수 있습니다.  이진 조건자 `less<Key>`가 기본값입니다.  
  
 C\+\+14에서는 형식 매개 변수가 없는 `std::less<>` 또는 `std::greater<>` 조건자를 지정하여 유형이 다른 조회를 사용하도록 설정할 수 있습니다.  자세한 내용은 [연관 컨테이너의 유형이 다른 조회](../standard-library/stl-containers.md#sequence_containers)를 참조하세요.  
  
 `Allocator`  
 map의 메모리 할당 및 할당 취소에 대한 세부 정보를 캡슐화하는 저장된 할당자 개체를 나타내는 형식입니다.  이 인수는 선택 사항이며 기본값은 `allocator<pair <const Key, Type> >`입니다.  
  
## 설명  
 STL multimap 클래스는 다음과 같습니다.  
  
-   연관된 키 값을 기준으로 하며 요소 값의 효율적인 검색을 지원하는 가변 크기 컨테이너인 연관 컨테이너입니다.  
  
-   이는 해당 요소에 액세스할 수 있는 양방향 반복기를 제공하기 때문에 되돌릴 수 있습니다.  
  
-   해당 요소가 컨테이너 내에서 지정된 비교 함수에 따라 키 값을 기준으로 정렬되므로 정렬됩니다.  
  
-   해당 요소는 고유 키를 가질 필요가 없기 때문에 복수이며, 하나의 키 값은 이와 연관된 많은 요소 데이터 값을 가질 수 있습니다.  
  
-   요소의 데이터 값은 키 값과 구별되기 때문에 쌍 연관 컨테이너입니다.  
  
-   제공하는 기능이 제네릭이고 요소 또는 키로 포함된 데이터의 특정 형식과 독립적이므로 템플릿 클래스입니다.  요소에 사용될 데이터 형식과 키는 대신 비교 함수 및 할당자와 함께 클래스 템플릿에서 매개 변수로 지정됩니다.  
  
 map 클래스에서 제공하는 반복기는 양방향 반복기이지만, [insert](../Topic/multimap::insert.md) 및 [multimap](../Topic/multimap::multimap.md) 클래스 멤버 함수의 버전은 기능 요구 사항이 양방향 반복기 클래스에서 보장하는 것보다 최소화된 약한 입력 반복기를 템플릿 매개 변수로 사용합니다.  다른 반복기 개념은 관련된 상세 기능별로 범주를 구성합니다.  각 반복기 개념은 고유한 요구 사항이 있으며 이러한 요구 사항을 적용하는 알고리즘은 해당 반복기 형식이 제공하는 요구 사항으로 가정을 제한해야 합니다.  입력 반복기를 역참조하여 몇 가지 개체를 참조하고 시퀀스의 다음 반복기로 증가되는 경우를 가정할 수 있습니다.  이는 최소한의 기능 모음이지만, 클래스 멤버 함수의 맥락에서 반복기 범위\(`[First, Last)`\)에 대해 설명하는 데에는 충분합니다.  
  
 컨테이너 형식은 일반적으로 응용 프로그램에서 필요한 검색과 삽입의 형식을 기준으로 선택해야 합니다.  연관 컨테이너들은 조회, 삽입 및 제거 작업에 최적화되어 있습니다.  이러한 작업을 명시적으로 지원하는 멤버 함수는 컨테이너의 요소 개수를 진수로 하는 로그값에 평균적으로 비례하는 시간 안에 수행하므로 효율적입니다.  요소를 삽입할 경우 어떤 반복기도 무효화되지 않으며, 요소를 제거할 경우 제거된 요소를 명확히 가리키고 있는 반복기만 무효화됩니다.  
  
 응용 프로그램에서 값과 해당 키를 연결하는 조건을 만족할 경우 적절한 연관 컨테이너는 multimap입니다.  이 구조 형식의 모델은 단어들이 항상 유일하게 정의되지 않는 "정의" 같이 문자열 값과 연결된 키 단어들의 정렬된 목록입니다.  대신 키워드가 고유하게 정의되어 키가 고유한 경우, map이 적절한 컨테이너가 됩니다.  반면에, 단어의 목록만을 저장하는 경우에는 set이 올바른 컨테이너가 됩니다.  단어의 여러 번 중복이 허용된 경우는 multiset이 적절한 컨테이너 구조입니다.  
  
 multimap은 [key\_compare](../Topic/multimap::key_compare.md) 형식의 저장된 함수 개체를 호출하여 제어하는 시퀀스를 정렬합니다.  이 저장된 개체는 [key\_comp](../Topic/multimap::key_comp.md) 멤버 함수를 호출하여 액세스할 수 있는 비교 함수입니다.  일반적으로, 이 순서를 정하려면 요소의 크기를 비교할 수 있어야 합니다. 즉, 제공된 어떤 두 요소에서 두 요소가 동일하거나\(어떤 것도 다른 것보다 작지 않음\) 하나가 다른 것보다 작음을 정할 수 있어야 합니다.  그러면 동일하지 않은 요소 사이에 정렬이 수행됩니다.  기술적으로 설명하면, 비교 함수는 표준 함수의 의미에서 엄밀히 약한 정렬을 수행하는 이진 조건자입니다.  이진 조건자 `f(x,y)`는 두 인수 개체 `x` 및 `y`를 가지는 함수 개체이며 true 또는 false를 반환합니다.  이진 조건자가 비재귀적, 비대칭, 전이적인 경우 및 동등성이 전이적인 경우 set에 적용된 정렬은 엄밀히 약한 정렬입니다. 여기서 `x` 및 `y`가 모두 false인 경우 두 개체 `f(x,y)` 및 `f(y,x)`는 동등한 것으로 정의됩니다.  키 사이의 더 강력한 같음 조건이 동등 조건을 대체하는 경우, 정렬은 전체가 되고\(모든 요소가 서로 상대적으로 정렬됨을 의미\) 일치된 키는 서로 구분할 수 없게 됩니다.  
  
 C\+\+14에서는 형식 매개 변수가 없는 `std::less<>` 또는 `std::greater<>` 조건자를 지정하여 유형이 다른 조회를 사용하도록 설정할 수 있습니다.  자세한 내용은 [연관 컨테이너의 유형이 다른 조회](../standard-library/stl-containers.md#sequence_containers)를 참조하세요.  
  
## 멤버  
  
### 생성자  
  
|||  
|-|-|  
|[multimap](../Topic/multimap::multimap.md)|비어 있거나 다른 `multimap`의 전체 또는 일부의 복사본인 `multimap`을 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/multimap::allocator_type.md)|`allocator` 개체의 `multimap` 클래스를 나타내는 형식입니다.|  
|[const\_iterator](../Topic/multimap::const_iterator.md)|`const`에 있는 `multimap` 요소를 읽을 수 있는 양방향 반복기를 제공하는 형식입니다.|  
|[const\_pointer](../Topic/multimap::const_pointer.md)|`const`에 있는 `multimap` 요소에 대한 포인터를 제공하는 형식입니다.|  
|[const\_reference](../Topic/multimap::const_reference.md)|`const` 작업을 읽고 수행하기 위해 `multimap`에 저장된 `const` 요소에 대한 참조를 제공하는 형식입니다.|  
|[const\_reverse\_iterator](../Topic/multimap::const_reverse_iterator.md)|`const`에 있는 `multimap` 요소를 읽을 수 있는 양방향 반복기를 제공하는 형식입니다.|  
|[difference\_type](../Topic/multimap::difference_type.md)|부호 있는 정수 형식은 반복기가 가리키는 요소 사이의 범위에 있는 `multimap`의 요소의 개수를 표현하는 데 사용할 수 있습니다.|  
|[iterator](../Topic/multimap::iterator.md)|동일한 `multimap` 안에서 요소를 참조하는 두 반복기 사이의 차이를 제공하는 형식입니다.|  
|[key\_compare](../Topic/multimap::key_compare.md)|`multimap`의 두 요소간 상대적 순서를 결정하는 두 정렬 키를 비교할 수 있는 함수 개체를 제공하는 형식입니다.|  
|[key\_type](../Topic/multimap::key_type.md)|`multimap`의 각 요소를 구성하는 정렬 키 개체를 설명하는 형식입니다.|  
|[mapped\_type](../Topic/multimap::mapped_type.md)|`multimap` 내에 저장된 데이터 형식을 나타내는 형식입니다.|  
|[포인터](../Topic/multimap::pointer.md)|`const`에 있는 `multimap` 요소에 대한 포인터를 제공하는 형식입니다.|  
|[참조](../Topic/multimap::reference.md)|`multimap` 내에 저장된 요소에 대한 참조를 제공하는 형식입니다.|  
|[reverse\_iterator](../Topic/multimap::reverse_iterator.md)|역순 `multimap`의 요소를 읽거나 수정할 수 있는 양방향 반복기를 제공하는 형식입니다.|  
|[size\_type](../Topic/multimap::size_type.md)|`const`의 `multimap` 요소에 대한 포인터를 제공하는 부호 없는 정수 형식입니다.|  
|[value\_type](../Topic/multimap::value_type.md)|두 요소를 정렬 키로 비교하여 `multimap`에서 상대적 순서를 결정할 수 있는 함수 개체를 제공하는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[begin](../Topic/multimap::begin.md)|`multimap`의 첫 번째 요소를 주소 지정하는 반복기를 반환합니다.|  
|[cbegin](../Topic/multimap::cbegin.md)|`multimap`의 첫 번째 요소를 주소 지정하는 상수 반복기를 반환합니다.|  
|[cend](../Topic/multimap::cend.md)|`multimap`에서 마지막 요소 다음에 나오는 위치를 주소 지정하는 상수 반복기를 반환합니다.|  
|[지우기](../Topic/multimap::clear.md)|`multimap`의 모든 요소를 지웁니다.|  
|[count](../Topic/multimap::count.md)|키가 매개 변수로 지정된 키와 일치하는 `multimap`의 요소 수를 반환합니다.|  
|[crbegin](../Topic/multimap::crbegin.md)|역순 `multimap`에서 첫 번째 요소를 주소 지정하는 상수 반복기를 반환합니다.|  
|[crend](../Topic/multimap::crend.md)|역순 `multimap`에서 마지막 요소 다음에 나오는 위치를 주소 지정하는 상수 반복기를 반환합니다.|  
|[emplace](../Topic/multimap::emplace.md)|생성된 요소를 `multimap`에 삽입합니다.|  
|[emplace\_hint](../Topic/multimap::emplace_hint.md)|배치 힌트를 사용하여 생성된 요소를 `multimap`에 삽입합니다.|  
|[비어 있음](../Topic/multimap::empty.md)|`multimap`가 비어 있는지 여부를 테스트합니다.|  
|[end](../Topic/multimap::end.md)|`multimap`에서 마지막 요소 다음에 나오는 위치를 주소 지정하는 반복기를 반환합니다.|  
|[equal\_range](../Topic/multimap::equal_range.md)|요소의 키가 지정된 값과 일치하는 요소 범위를 찾습니다.|  
|[erase](../Topic/multimap::erase.md)|지정된 위치에서 `multimap`의 요소 또는 요소의 범위를 제거하거나 지정된 키와 일치하는 요소를 제거합니다.|  
|[find](../Topic/multimap::find.md)|지정된 키와 같은 키를 가진 `multimap` 내 요소의 첫 번째 위치를 가리키는 반복기를 반환합니다.|  
|[get\_allocator](../Topic/multimap::get_allocator.md)|`allocator`을 생성하는 데 사용되는 `multimap` 개체의 복사본을 반환합니다.|  
|[삽입](../Topic/multimap::insert.md)|`multimap`에 요소 또는 요소의 범위를 삽입합니다.|  
|[key\_comp](../Topic/multimap::key_comp.md)|`multimap`에서 키를 정렬하기 위해 사용하는 비교 개체의 복사본을 검색합니다.|  
|[lower\_bound](../Topic/multimap::lower_bound.md)|`multimap`에서 지정된 키보다 같거나 큰 키를 가진 첫 번째 요소에 반복기를 반환합니다.|  
|[max\_size](../Topic/multimap::max_size.md)|`multimap`의 최대 길이를 반환합니다.|  
|[rbegin](../Topic/multimap::rbegin.md)|역순 `multimap`에서 첫 번째 요소를 참조하는 반복기를 반환합니다.|  
|[rend](../Topic/multimap::rend.md)|역순 `multimap`에서 마지막 요소 다음에 나오는 위치를 주소 지정하는 반복기를 반환합니다.|  
|[size](../Topic/multimap::size.md)|`multimap`에 있는 요소 수를 반환합니다.|  
|[스왑](../Topic/multimap::swap.md)|두 `multimap`의 요소를 교환합니다.|  
|[upper\_bound](../Topic/multimap::upper_bound.md)|`multimap`에서 지정된 키보다 큰 키를 가진 첫 번째 요소에 반복기를 반환합니다.|  
|[value\_comp](../Topic/multimap::value_comp.md)|멤버 함수는 키 값을 비교하여 `multimap`의 요소 순서를 결정하는 함수 개체를 반환합니다.|  
  
### 운영자  
  
|||  
|-|-|  
|[연산자 \=](../Topic/multimap::operator=.md)|`multimap`의 요소를 다른 `multimap`의 복사본으로 대체합니다.|  
  
## 요구 사항  
 **헤더:** \<map\>  
  
 **네임스페이스:** std  
  
 \(**키**, **값**\) 쌍은 multimap에 `pair` 형식의 개체로 저장됩니다.  쌍 클래스는 \<map\>에 의해 자동으로 포함되는 헤더 \<utility\>가 필요합니다.  
  
## 참고 항목  
 [\<map\> Members](http://msdn.microsoft.com/ko-kr/7e8f0bc2-6034-40f6-9d14-76d4cef86308)   
 [컨테이너](../cpp/containers-modern-cpp.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)