---
title: "hash_multiset 클래스 | Microsoft Docs"
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
  - "stdext.hash_multiset"
  - "std::hash_multiset"
  - "stdext::hash_multiset"
  - "hash_multiset"
  - "std.hash_multiset"
  - "hash_set/stdext::hash_multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_multiset 클래스"
ms.assetid: 0580397a-a76e-40ad-aea2-5c6f3a9d0a21
caps.latest.revision: 23
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# hash_multiset 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  이 API는 더 이상 사용되지 않습니다.  [unordered\_multiset 클래스](../standard-library/unordered-multiset-class.md)를 대신 사용하는 것이 좋습니다.  
  
 컨테이너 클래스 hash\_multiset은 표준 템플릿 라이브러리의 확장이며, 포함된 요소의 값이 키 값으로 사용되며 고유할 필요가 없는 컬렉션에서 데이터를 저장하고 빠르게 검색하는 데 사용됩니다.  
  
## 구문  
  
```  
  
        template <  
   class Key,   
   class Traits=hash_compare<Key, less<Key> >,   
   class Allocator=allocator<Key>   
>  
class hash_multiset  
```  
  
#### 매개 변수  
 *Key*  
 hash\_multiset에 저장되는 요소 데이터 형식입니다.  
  
 `Traits`  
 두 요소 값을 정렬 키로 비교하여 상대 순서를 확인할 수 있는 이진 조건자인 클래스 비교 중 하나와 요소의 키 값을 **size\_t** 형식의 부호 없는 정수에 매핑하는 단항 조건자인 해시 함수의 두 개체를 포함하는 형식입니다.  이 인수는 선택 사항이며 `hash_compare`*\<Key,* **less***\<Key\> \>* 가 기본값입니다.  
  
 `Allocator`  
 hash\_multiset의 메모리 할당 및 할당 취소에 대한 세부 정보를 캡슐화하는 저장된 할당자 개체를 나타내는 형식입니다.  이 인수는 선택 사항이며 기본값은 **allocator***\<Key\>입니다.*  
  
## 설명  
 Hash\_multiset은  
  
-   연관된 키 값을 기준으로 하며 요소 값의 효율적인 검색을 지원하는 가변 크기 컨테이너인 연관 컨테이너입니다.  또한 해당 요소 값은 키 값과 구별되므로 간단한 연관 컨테이너입니다.  
  
-   이는 해당 요소에 액세스할 수 있는 양방향 반복기를 제공하기 때문에 되돌릴 수 있습니다.  
  
-   요소가 요소의 키 값에 적용된 해시 함수 값을 기반으로 하여 버킷으로 그룹화되기 때문에 해시됩니다.  
  
-   각각의 요소가 반드시 고유한 키를 가지고 있어야 한다는 점에서 고유성을 갖고 있습니다.  hash\_multiset은 간단한 연관 컨테이너이기도 하므로 요소 역시 고유합니다.  
  
-   제공하는 기능이 제네릭이고 요소 또는 키로 포함된 데이터의 특정 형식과 독립적이므로 템플릿 클래스입니다.  요소에 사용될 데이터 형식과 키는 대신 비교 함수 및 할당자와 함께 클래스 템플릿에서 매개 변수로 지정됩니다.  
  
 해시는 정렬보다 훨씬 효율적입니다. 성공적인 해시는 정렬 방식에 대한 컨테이너의 요소 수 로그에 비례하는 시간과 비교할 때 삽입, 삭제, 찾기를 일정한 평균 시간 이내에 수행합니다.  set 요소의 값은 직접 변경할 수 없습니다.  대신, 이전 값을 삭제하고 새 값의 요소를 삽입해야 합니다.  
  
 컨테이너 형식은 일반적으로 응용 프로그램에서 필요한 검색과 삽입의 형식을 기준으로 선택해야 합니다.  해시된 연관 컨테이너는 조회, 삽입 및 제거 작업에 최적화되어 있습니다.  명시적으로 이러한 작업을 지원하는 멤버 함수는 잘 설계된 해시 함수와 함께 사용할 경우 효율적이며, 컨테이너의 요소 수에 종속되지 않는 일정한 평균 시간으로 작업을 수행합니다.  잘 설계된 해시 함수는 해시된 값의 균일한 분포를 생성하고 충돌 수를 최소화합니다. 여기서 충돌은 특정 키 값이 동일한 해시된 값에 매핑될 때 발생합니다.  가능한 최악의 해시 함수가 있는 최악의 경우에는 작업 수가 시퀀스의 요소 수에 비례합니다\(선형 시간\).  
  
 응용 프로그램에서 값과 해당 키를 연결하는 조건을 만족할 경우 적절한 연관 컨테이너는 hash\_multiset입니다.  hash\_multiset의 요소는 여러 개일 수 있고 자체 정렬 키로 사용되므로 키는 고유하지 않습니다.  이 형식의 구조에 대한 모델은 정렬된 목록입니다. 예를 들어, 단어 내의 단어가 두 번 이상 나타날 수 있습니다.  단어가 여러 번 나타날 수 있도록 허용되지 않은 경우 hash\_set가 적절한 컨테이너 구조입니다.  고유 키 단어 목록에 고유 정의가 연결된 경우 이 데이터를 포함하기 위한 적절한 구조는 hash\_map입니다.  대신, 정의가 고유하지 않은 경우는 hash\_multimap이 적절한 컨테이너입니다.  
  
 hash\_multiset은 형식 [value\_compare](../Topic/hash_multiset::value_compare.md)의 저장된 해시 특성 개체를 호출하여 제어하는 시퀀스를 정렬합니다.  이 저장된 개체는 [key\_comp](../Topic/hash_multiset::key_comp.md) 멤버 함수를 호출하여 액세스할 수 있습니다.  이와 같은 함수 개체는 클래스 `hash_compare`*\<Key,* **less***\<Key\> \>*의 개체와 동일하게 동작해야 합니다. 특히, 형식 **Key**의 모든 값 *Key*에 대해 호출 **특성**\(*Key*\)은 형식 **size\_t**의 값 분포를 생성합니다.  
  
 일반적으로, 이 순서를 정하려면 요소의 크기를 비교할 수 있어야 합니다. 즉, 제공된 어떤 두 요소에서 두 요소가 동일하거나\(어떤 것도 다른 것보다 작지 않음\) 하나가 다른 것보다 작음을 정할 수 있어야 합니다.  그러면 동일하지 않은 요소 사이에 정렬이 수행됩니다.  기술적으로 설명하면, 비교 함수는 표준 함수의 의미에서 엄밀히 약한 정렬을 수행하는 이진 조건자입니다.  이진 조건자 *f*\(*x*,*y*\)는 두 인수 개체 x, y 및 반환 값 true 또는 false가 있는 함수 개체입니다.  이진 조건자가 비재귀적, 비대칭 및 전이적인 경우 및 동등성이 전이적인 경우 hash\_multiset에 적용된 정렬은 엄밀히 약한 정렬입니다. 여기서, *f*\(*x*,*y*\)와 *f*\(*y*,*x*\)가 모두 false인 경우 x 및 y 두 개체는 동등한 것으로 정의됩니다.  키 사이의 더 강력한 같음 조건이 동등 조건을 대체하는 경우, 정렬은 전체가 되고\(모든 요소가 서로 상대적으로 정렬됨을 의미\) 일치된 키는 서로 구분할 수 없게 됩니다.  
  
 제어된 시퀀스의 실제 요소 순서는 해시 함수, 순서 지정 함수 및 컨테이너 개체에 저장된 해시 테이블의 현재 크기에 따라 달라집니다.  해시 테이블의 현재 크기를 확인할 수 없으므로 제어된 시퀀스의 요소 순서는 일반적으로 예측할 수 없습니다.  요소를 삽입할 경우 어떤 반복기도 무효화되지 않으며, 요소를 제거할 경우 제거된 요소를 명확히 가리키고 있는 반복기만 무효화됩니다.  
  
 hash\_multiset 클래스에서 제공하는 반복기는 양방향 반복기이지만, [insert](../Topic/set::insert.md) 및 [hash\_multiset](../Topic/set::set.md) 클래스 멤버 함수의 버전은 기능 요구 사항이 양방향 반복기 클래스에서 보장하는 것보다 최소화된 약한 입력 반복기를 템플릿 매개 변수로 사용합니다.  다른 반복기 개념은 관련된 상세 기능별로 범주를 구성합니다.  각 반복기 개념은 고유한 요구 사항 hash\_multiset이 있으며 이러한 요구 사항을 적용하는 알고리즘은 해당 반복기 형식이 제공하는 요구 사항으로 가정을 제한해야 합니다.  입력 반복기를 역참조하여 몇 가지 개체를 참조하고 시퀀스의 다음 반복기로 증가되는 경우를 가정할 수 있습니다.  이는 최소한의 기능 hash\_multiset이지만, 클래스 멤버 함수의 맥락에서 반복기 범위\(`_First`, `_Last`\)에 대해 설명하는 데에는 충분합니다.  
  
 Visual C\+\+ .NET 2003에서 [\<hash\_map\>](../standard-library/hash-map.md) 및 [\<hash\_set\>](../standard-library/hash-set.md) 헤더 파일의 멤버는 더 이상 std 네임스페이스에 없으며, 대신 stdext 네임스페이스로 이동되었습니다.  자세한 내용은 [stdext 네임스페이스](../standard-library/stdext-namespace.md)를 참조하세요.  
  
### 생성자  
  
|||  
|-|-|  
|[hash\_multiset](../Topic/hash_multiset::hash_multiset.md)|비어 있거나 다른 `hash_multiset`의 전체 또는 일부의 복사본인 `hash_multiset`을 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/hash_multiset::allocator_type.md)|`allocator` 개체의 `hash_multiset` 클래스를 나타내는 형식입니다.|  
|[const\_iterator](../Topic/hash_multiset::const_iterator.md)|`const`에 있는 `hash_multiset` 요소를 읽을 수 있는 양방향 반복기를 제공하는 형식입니다.|  
|[const\_pointer](../Topic/hash_multiset::const_pointer.md)|`const`에 있는 `hash_multiset` 요소에 대한 포인터를 제공하는 형식입니다.|  
|[const\_reference](../Topic/hash_multiset::const_reference.md)|`const` 작업을 읽고 수행하기 위해 `hash_multiset`에 저장된 `const` 요소에 대한 참조를 제공하는 형식입니다.|  
|[const\_reverse\_iterator](../Topic/hash_multiset::const_reverse_iterator.md)|`const`에 있는 `hash_multiset` 요소를 읽을 수 있는 양방향 반복기를 제공하는 형식입니다.|  
|[difference\_type](../Topic/hash_multiset::difference_type.md)|동일한 `hash_multiset` 안에서 요소를 다루는 두 반복기 사이의 차이를 제공하는 부호 있는 정수 형식입니다.|  
|[iterator](../Topic/hash_multiset::iterator.md)|`hash_multiset`에 있는 모든 요소를 읽거나 수정할 수 있는 양방향 반복기를 제공하는 형식입니다.|  
|[key\_compare](../Topic/hash_multiset::key_compare.md)|`hash_multiset`의 두 요소간 상대적 순서를 결정하는 두 정렬 키를 비교할 수 있는 함수 개체를 제공하는 형식입니다.|  
|[key\_type](../Topic/hash_multiset::key_type.md)|해당 용량 내 `hash_set` 요소로 저장된 개체를 정렬 키로 설명하는 형식입니다.|  
|[포인터](../Topic/hash_multiset::pointer.md)|`hash_multiset`의 요소에 대한 포인터를 제공하는 형식입니다.|  
|[참조](../Topic/hash_multiset::reference.md)|`hash_multiset` 내에 저장된 요소에 대한 참조를 제공하는 형식입니다.|  
|[reverse\_iterator](../Topic/hash_multiset::reverse_iterator.md)|역순 `hash_multiset`의 요소를 읽거나 수정할 수 있는 양방향 반복기를 제공하는 형식입니다.|  
|[size\_type](../Topic/hash_multiset::size_type.md)|`hash_multiset`에서 요소 수를 표현할 수 있는 부호 없는 정수 형식입니다.|  
|[value\_compare](../Topic/hash_multiset::value_compare.md)|`hash_multiset`의 두 요소 값을 비교하여 상대 순서를 확인할 수 있는 클래스 비교의 이진 조건자와 요소를 해시하는 단항 조건자인 두 함수 개체를 제공하는 형식입니다.|  
|[value\_type](../Topic/hash_multiset::value_type.md)|해당 용량 내 `hash_multiset` 요소로 저장된 개체를 값으로 설명하는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[begin](../Topic/hash_multiset::begin.md)|`hash_multiset`의 첫 번째 요소를 주소 지정하는 반복기를 반환합니다.|  
|[hash\_multiset::cbegin](../Topic/hash_multiset::cbegin.md)|`hash_multiset`의 첫 번째 요소를 주소 지정하는 상수 반복기를 반환합니다.|  
|[hash\_multiset::cend](../Topic/hash_multiset::cend.md)|`hash_multiset`에서 마지막 요소 다음에 나오는 위치를 주소 지정하는 상수 반복기를 반환합니다.|  
|[지우기](../Topic/hash_multiset::clear.md)|`hash_multiset`의 모든 요소를 지웁니다.|  
|[count](../Topic/hash_multiset::count.md)|키가 매개 변수로 지정된 키와 일치하는 `hash_multiset`의 요소 수를 반환합니다.|  
|[hash\_multiset::crbegin](../Topic/hash_multiset::crbegin.md)|역순 `hash_multiset`에서 첫 번째 요소를 주소 지정하는 상수 반복기를 반환합니다.|  
|[hash\_multiset::crend](../Topic/hash_multiset::crend.md)|역순 `hash_multiset`에서 마지막 요소 다음에 나오는 위치를 주소 지정하는 상수 반복기를 반환합니다.|  
|[hash\_multiset::emplace](../Topic/hash_multiset::emplace.md)|생성된 요소를 `hash_multiset`에 삽입합니다.|  
|[hash\_multiset::emplace\_hint](../Topic/hash_multiset::emplace_hint.md)|배치 힌트를 사용하여 생성된 요소를 `hash_multiset`에 삽입합니다.|  
|[비어 있음](../Topic/hash_multiset::empty.md)|`hash_multiset`가 비어 있는지 여부를 테스트합니다.|  
|[end](../Topic/hash_multiset::end.md)|`hash_multiset`에서 마지막 요소 다음에 나오는 위치를 주소 지정하는 반복기를 반환합니다.|  
|[equal\_range](../Topic/hash_multiset::equal_range.md)|지정된 키보다 더 큰 키를 가진 `hash_multiset`의 첫 번째 요소와 지정된 키보다 더 크거나 같은 키를 가진 `hash_multiset`의 첫 번째 요소에 반복기의 쌍을 각각 반환합니다.|  
|[erase](../Topic/hash_multiset::erase.md)|지정된 위치에서 `hash_multiset`의 요소 또는 요소의 범위를 제거하거나 지정된 키와 일치하는 요소를 제거합니다.|  
|[find](../Topic/hash_multiset::find.md)|지정된 키와 같은 키를 가진 `hash_multiset` 내 요소의 위치를 가리키는 반복기를 반환합니다.|  
|[get\_allocator](../Topic/hash_multiset::get_allocator.md)|`allocator`을 생성하는 데 사용되는 `hash_multiset` 개체의 복사본을 반환합니다.|  
|[삽입](../Topic/hash_multiset::insert.md)|`hash_multiset`에 요소 또는 요소의 범위를 삽입합니다.|  
|[key\_comp](../Topic/hash_multiset::key_compare.md)|`hash_multiset`에서 키를 정렬하기 위해 사용하는 비교 개체의 복사본을 검색합니다.|  
|[lower\_bound](../Topic/hash_multiset::lower_bound.md)|`hash_multiset`에서 지정된 키보다 크거나 같은 키를 가진 첫 번째 요소에 반복기를 반환합니다.|  
|[max\_size](../Topic/hash_multiset::max_size.md)|`hash_multiset`의 최대 길이를 반환합니다.|  
|[rbegin](../Topic/hash_multiset::rbegin.md)|역순 `hash_multiset`에서 첫 번째 요소를 참조하는 반복기를 반환합니다.|  
|[rend](../Topic/hash_multiset::rend.md)|역순 `hash_multiset`에서 마지막 요소 다음에 나오는 위치를 주소 지정하는 반복기를 반환합니다.|  
|[size](../Topic/hash_multiset::size.md)|`hash_multiset`에 있는 요소 수를 반환합니다.|  
|[스왑](../Topic/hash_multiset::swap.md)|두 `hash_multiset`의 요소를 교환합니다.|  
|[upper\_bound](../Topic/hash_multiset::upper_bound.md)|`hash_multiset`에서 지정된 키보다 같거나 큰 키를 가진 첫 번째 요소에 반복기를 반환합니다.|  
|[value\_comp](../Topic/hash_multiset::value_comp.md)|`hash_multiset`의 요소 키 값을 해시하고 정렬하는 데 사용되는 해시 특성 개체의 복사본을 검색합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[hash\_multiset::operator\=](../Topic/hash_multiset::operator=.md)|의 요소를 다른 의 복사본으로 바꿉니다.|  
  
## 요구 사항  
 **헤더:** \<hash\_set\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)