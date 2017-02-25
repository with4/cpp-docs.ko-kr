---
title: "basic_string 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.basic_string"
  - "std::basic_string"
  - "basic_string"
  - "xstring/std::basic_string"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_string 클래스"
ms.assetid: a9c3e0a2-39bf-4c8a-b093-9abe30839591
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# basic_string 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스 `basic_string`의 개체에 의해 제어되는 시퀀스는 표준 C\+\+ 문자열 클래스로 보통 문자열이라고 합니다. 이러한 문자열을 표준 C\+\+ 라이브러리 전체에서 사용되는 null로 종료되는 C 스타일 문자열과 혼동해서는 안 됩니다.  표준 C\+\+ 문자열은 비교\/연결 작업, 반복기, STL 알고리즘, 클래스 할당자 관리 메모리 복사\/할당 등의 일반 형식으로 문자열을 사용할 수 있는 컨테이너입니다.  표준 C\+\+ 문자열을 null로 종료되는 C 스타일 문자열로 변환해야 하는 경우에는 [basic\_string::c\_str](../Topic/basic_string::c_str.md) 멤버를 사용합니다.  
  
## 구문  
  
```  
template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>> class basic_string;  
```  
  
#### 매개 변수  
 `CharType`  
 문자열에 저장되는 단일 문자의 데이터 형식입니다.  표준 C\+\+ 라이브러리는 `char` 형식 요소의 경우 [string](../Topic/string%20\(C++%20STL%20%3Cstring%3E\).md), `wchar_t`의 경우 [wstring](../Topic/wstring.md), `char16_t`의 경우 [u16string](../Topic/u16string.md), `char32_t`의 경우 [u32string](../Topic/u32string.md) 형식 정의를 사용하여 이 템플릿 클래스를 특수화하는 기능을 제공합니다.  
  
 `Traits`  
 **Traits** 클래스를 통해 basic\_string 특수화 내 **CharType** 요소의 여러 중요 속성을 설명합니다.  기본값은 `char_traits`\<`CharType`\>입니다.  
  
 `Allocator`  
 문자열의 메모리 할당 및 할당 취소에 대한 세부 정보를 캡슐화하는 저장된 할당자 개체를 나타내는 형식입니다.  기본값은 **allocator**\<`CharType`\>입니다.  
  
### 생성자  
  
|||  
|-|-|  
|[basic\_string](../Topic/basic_string::basic_string.md)|비어 있거나 특정 문자로 초기화된 문자열 또는 다른 문자열 개체나 C 문자열 일부 또는 전체의 복사본인 문자열을 생성합니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_string::allocator_type.md)|문자열 개체의 `allocator` 클래스를 나타내는 형식입니다.|  
|[const\_iterator](../Topic/basic_string::const_iterator.md)|문자열의 `const` 요소 하나를 액세스하고 읽을 수 있는 임의 액세스 반복기를 제공하는 형식입니다.|  
|[const\_pointer](../Topic/basic_string::const_pointer.md)|문자열에서 `const` 요소에 대한 포인터를 제공하는 형식입니다.|  
|[const\_reference](../Topic/basic_string::const_reference.md)|`const` 작업을 읽고 수행하기 위해 문자열에 저장된 `const` 요소에 대한 참조를 제공하는 형식입니다.|  
|[const\_reverse\_iterator](../Topic/basic_string::const_reverse_iterator.md)|문자열의 모든 `const` 요소를 읽을 수 있는 임의 액세스 반복기를 제공하는 형식입니다.|  
|[difference\_type](../Topic/basic_string::difference_type.md)|동일한 문자열 내의 요소를 참조하는 두 반복기 사이의 차이를 제공하는 형식입니다.|  
|[iterator](../Topic/basic_string::iterator.md)|문자열에 있는 모든 요소를 읽거나 수정할 수 있는 임의 액세스 반복기를 제공하는 형식입니다.|  
|[npos](../Topic/basic_string::npos.md)|검색 함수에서 오류가 발생할 때 "not found" 또는 "all remaining characters"를 나타내는 \-1로 초기화된 부호 없는 정수 값입니다.|  
|[포인터](../Topic/basic_string::pointer.md)|문자열 또는 문자 배열의 문자 요소에 대한 포인터를 제공하는 형식입니다.|  
|[참조](../Topic/basic_string::reference.md)|문자열에 저장된 요소에 대한 참조를 제공하는 형식입니다.|  
|[reverse\_iterator](../Topic/basic_string::reverse_iterator.md)|역방향 문자열에 있는 모든 요소를 읽거나 수정할 수 있는 임의 액세스 반복기를 제공하는 형식입니다.|  
|[size\_type](../Topic/basic_string::size_type.md)|문자열의 요소 수에 대한 부호 없는 정수 형식입니다.|  
|[traits\_type](../Topic/basic_string::traits_type.md)|문자열에 저장된 요소의 문자 특성 형식입니다.|  
|[value\_type](../Topic/basic_string::value_type.md)|문자열에 저장된 문자의 형식을 나타내는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[append](../Topic/basic_string::append.md)|문자열 끝에 문자를 추가합니다.|  
|[assign](../Topic/basic_string::assign.md)|문자열의 내용에 새 문자 값을 할당합니다.|  
|[at](../Topic/basic_string::at.md)|문자열의 지정된 위치에 있는 요소에 대한 참조를 반환합니다.|  
|[back](../Topic/basic_string::back.md)||  
|[begin](../Topic/basic_string::begin.md)|문자열의 첫 번째 요소 주소를 지정하는 반복기를 반환합니다.|  
|[c\_str](../Topic/basic_string::c_str.md)|문자열의 내용을 C 스타일의 null로 종료되는 문자열로 변환합니다.|  
|[capacity](../Topic/basic_string::capacity.md)|문자열의 메모리 할당을 늘리지 않고도 문자열에 저장할 수 있는 요소의 최대 수를 반환합니다.|  
|[cbegin](../Topic/basic_string::cbegin.md)|문자열의 첫 번째 요소 주소를 지정하는 const 반복기를 반환합니다.|  
|[cend](../Topic/basic_string::cend.md)|문자열에서 마지막 요소 다음에 나오는 위치를 주소 지정하는 const 반복기를 반환합니다.|  
|[clear](../Topic/basic_string::clear.md)|문자열의 모든 요소를 지웁니다.|  
|[compare](../Topic/basic_string::compare.md)|문자열을 지정된 문자열과 비교하여 두 문자열이 같은지 아니면 한 문자열이 다른 문자열보다 사전순으로 더 작은지를 확인합니다.|  
|[copy](../Topic/basic_string::copy.md)|소스 문자열의 인덱싱된 위치에서 지정한 수까지의 문자를 대상 문자 배열에 복사합니다.  더 이상 사용되지 않습니다.  대신 [basic\_string::\_Copy\_s](../Topic/basic_string::_Copy_s.md)를 사용하십시오.|  
|[crbegin](../Topic/basic_string::crbegin.md)|역방향 문자열에서 첫 번째 요소의 주소를 지정하는 const 반복기를 반환합니다.|  
|[crend](../Topic/basic_string::crend.md)|역방향 문자열에서 마지막 요소 다음에 나오는 위치의 주소를 지정하는 상수 반복기를 반환합니다.|  
|[\_Copy\_s](../Topic/basic_string::_Copy_s.md)|소스 문자열의 인덱싱된 위치에서 지정한 수까지의 문자를 대상 문자 배열에 복사합니다.|  
|[data](../Topic/basic_string::data.md)|문자열의 내용을 문자 배열로 변환합니다.|  
|[empty](../Topic/basic_string::empty.md)|문자열에 문자가 있는지 테스트합니다.|  
|[end](../Topic/basic_string::end.md)|문자열에서 마지막 요소 다음에 나오는 위치의 주소를 지정하는 반복기를 반환합니다.|  
|[erase](../Topic/basic_string::erase.md)|문자열에서 지정된 위치의 요소 또는 요소 범위를 제거합니다.|  
|[find](../Topic/basic_string::find.md)|문자열에서 지정된 문자 시퀀스와 일치하는 첫 번째 하위 문자열을 정방향으로 검색합니다.|  
|[find\_first\_not\_of](../Topic/basic_string::find_first_not_of.md)|문자열에서 지정된 문자열의 요소가 아닌 첫 번째 문자를 검색합니다.|  
|[find\_first\_of](../Topic/basic_string::find_first_of.md)|문자열에서 지정된 문자열의 요소와 일치하는 첫 번째 문자를 검색합니다.|  
|[find\_last\_not\_of](../Topic/basic_string::find_last_not_of.md)|문자열에서 지정된 문자열의 요소가 아닌 마지막 문자를 검색합니다.|  
|[find\_last\_of](../Topic/basic_string::find_last_of.md)|문자열에서 지정된 문자열의 요소인 마지막 문자를 검색합니다.|  
|[front](../Topic/basic_string::front.md)|문자열의 첫 번째 요소에 대한 참조를 반환합니다.|  
|[get\_allocator](../Topic/basic_string::get_allocator.md)|문자열을 생성하는 데 사용된 `allocator` 개체의 복사본을 반환합니다.|  
|[insert](../Topic/basic_string::insert.md)|요소 하나 또는 여러 개나 요소의 범위를 문자열의 지정된 위치에 삽입합니다.|  
|[length](../Topic/basic_string::length.md)|문자열의 현재 요소 수를 반환합니다.|  
|[max\_size](../Topic/basic_string::max_size.md)|문자열이 포함할 수 있는 최대 문자 수를 반환합니다.|  
|[pop\_back](../Topic/basic_string::pop_back.md)|문자열의 마지막 요소를 지웁니다.|  
|[push\_back](../Topic/basic_string::push_back.md)|문자열 끝에 요소를 추가합니다.|  
|[rbegin](../Topic/basic_string::rbegin.md)|역방향 문자열에서 첫 번째 요소의 주소를 지정하는 반복기를 반환합니다.|  
|[rend](../Topic/basic_string::rend.md)|역방향 문자열에서 마지막 요소 바로 다음을 가리키는 반복기를 반환합니다.|  
|[replace](../Topic/basic_string::replace.md)|문자열에서 지정된 위치의 요소를 다른 범위 또는 문자열이나 C 문자열에서 복사한 문자 또는 지정된 문자로 바꿉니다.|  
|[reserve](../Topic/basic_string::reserve.md)|문자열의 용량을 최소한 지정된 숫자보다 크게 설정합니다.|  
|[resize](../Topic/basic_string::resize.md)|문자열의 새 크기를 지정하고 필요에 따라 요소를 추가하거나 지웁니다.|  
|[rfind](../Topic/basic_string::rfind.md)|문자열에서 지정된 문자 시퀀스와 일치하는 첫 번째 하위 문자열을 역방향으로 검색합니다.|  
|[shrink\_to\_fit](../Topic/basic_string::shrink_to_fit.md)|문자열의 초과 용량을 삭제합니다.|  
|[size](../Topic/basic_string::size.md)|문자열의 현재 요소 수를 반환합니다.|  
|[substr](../Topic/basic_string::substr.md)|지정된 위치부터 시작하여 문자열의 하위 문자열을 최대 특정 문자 수만큼 복사합니다.|  
|[스왑](../Topic/basic_string::swap.md)|두 문자열의 내용을 교환합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator \+\=](../Topic/basic_string::operator+=.md)|문자열에 문자를 추가합니다.|  
|[연산자 \=](../Topic/basic_string::operator=.md)|문자열의 내용에 새 문자 값을 할당합니다.|  
|[operator&#91;&#93;](../Topic/basic_string::operator.md)|문자열에서 지정된 인덱스에 있는 문자에 대한 참조를 제공합니다.|  
  
## 설명  
 함수는 [max\_size](../Topic/basic_string::max_size.md) 요소보다 긴 시퀀스를 생성하라는 요청을 받으면 [length\_error](../standard-library/length-error-class.md) 형식의 개체를 throw하여 길이 오류를 보고합니다.  
  
 제어되는 시퀀스의 요소를 지정하는 참조, 포인터 및 반복기는 제어되는 시퀀스를 변경하는 함수를 호출하거나 **const**가 아닌 멤버 함수를 처음 호출하고 나면 유효하지 않은 상태가 될 수 있습니다.  
  
## 요구 사항  
 **헤더:** \<string\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<string\>](../standard-library/string.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)