---
title: regex_iterator 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- regex/std::regex_iterator
- regex/std::regex_iterator::operator==
- regex/std::regex_iterator::operator!=
- regex/std::regex_iterator::operator*
- regex/std::regex_iterator::operator->
- regex/std::regex_iterator::operator++
dev_langs:
- C++
helpviewer_keywords:
- std::regex_iterator
- std::regex_iterator::operator==
- std::regex_iterator::operator!=
- std::regex_iterator::operator*
- std::regex_iterator::operator->
- std::regex_iterator::operator++
ms.assetid: 0cfd8fd0-5a95-4f3c-bf8e-6ef028c423d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fffa778854519bff6f947aec779e36b77fd4e202
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861300"
---
# <a name="regexiterator-class"></a>regex_iterator 클래스

일치 항목에 대한 반복기 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_iterator {
public:
   typedef basic_regex<Elem, RXtraits> regex_type;
   typedef match_results<BidIt> value_type;
   typedef std::forward_iterator_tag iterator_category;
   typedef std::ptrdiff_t difference_type;
   typedef const match_results<BidIt>* pointer;
   typedef const match_results<BidIt>& reference;

   regex_iterator();
   regex_iterator(
      BidIt first, BidIt last, const regex_type& re,
      regex_constants::match_flag_type f = regex_constants::match_default);

   bool operator==(const regex_iterator& right);
   bool operator!=(const regex_iterator& right);
   const match_results<BidIt>& operator*();
   const match_results<BidIt> * operator->();
   regex_iterator& operator++();
   regex_iterator& operator++(int);

private:
   BidIt begin; // exposition only
   BidIt end; // exposition only
   regex_type *pregex;     // exposition only
   regex_constants::match_flag_type flags; // exposition only
   match_results<BidIt> match; // exposition only
   };
```

### <a name="parameters"></a>매개 변수

`BidIt` 부분 일치에 대 한 반복기 형식입니다.

`Elem` 와 일치 하도록 요소의 형식입니다.

`RXtraits` 요소에 대 한 특성 클래스입니다.

## <a name="remarks"></a>설명

템플릿 클래스는 일정한 정방향 반복기 개체를 설명합니다. 반복기 범위 `match_results<BidIt>` 에 정의된 문자 시퀀스에 정규식 개체 `*pregex` 를 반복적으로 적용하여 `[begin, end)`형식의 개체를 추출합니다.

## <a name="examples"></a>예제

정규식에 대한 예제는 다음 항목을 참조하세요.

- [regex_match](../standard-library/regex-functions.md#regex_match)

- [regex_replace](../standard-library/regex-functions.md#regex_replace)

- [regex_search](../standard-library/regex-functions.md#regex_search)

- [swap](../standard-library/regex-functions.md#swap)

## <a name="requirements"></a>요구 사항

**헤더:** \<regex>

**네임스페이스:** std

## <a name="difference_type"></a>  regex_iterator::difference_type

반복기 차이의 형식입니다.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>설명

이 형식은 `std::ptrdiff_t`의 동의어입니다.

### <a name="example"></a>예제

```cpp
// std__regex__regex_iterator_difference_type.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }
```

```Output
match == a
match == a
match == a
```

## <a name="iterator_category"></a>  regex_iterator::iterator_category

반복기 범주의 형식입니다.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>설명

이 형식은 `std::forward_iterator_tag`의 동의어입니다.

### <a name="example"></a>예제

```cpp
// std__regex__regex_iterator_iterator_category.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }
```

```Output
match == a
match == a
match == a
```

## <a name="op_neq"></a>  regex_iterator::operator!=

반복기가 같지 않은지 비교합니다.

```cpp
bool operator!=(const regex_iterator& right);
```

### <a name="parameters"></a>매개 변수

`right` 비교할 반복기입니다.

### <a name="remarks"></a>설명

멤버 함수는 `!(*this == right)`를 반환합니다.

### <a name="example"></a>예제

```cpp
// std__regex__regex_iterator_operator_ne.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }
```

```Output
match == a
match == a
match == a
```

## <a name="op_star"></a>  regex_iterator::operator*

지정된 일치 항목에 액세스합니다.

```cpp
const match_results<BidIt>& operator*();
```

### <a name="remarks"></a>설명

이 멤버 함수는 저장된 값 `match`를 반환합니다.

### <a name="example"></a>예제

```cpp
// std__regex__regex_iterator_operator_star.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }
```

```Output
match == a
match == a
match == a
```

## <a name="op_add_add"></a>  regex_iterator::operator++

반복기를 증가시킵니다.

```cpp
regex_iterator& operator++();
regex_iterator& operator++(int);
```

### <a name="remarks"></a>설명

현재 일치 항목에 문자가 없으면 첫 번째 연산자가 `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail | regex_constants::match_not_null)`를 호출하고, 그렇지 않으면 저장된 값 `begin` 으로 이동하여 현재 일치 항목 다음의 첫 번째 문자를 가리킨 다음 `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail)`을 호출합니다. 두 경우 모두 검색에 실패하면 연산자가 개체를 시퀀스의 끝 반복기로 설정합니다. 연산자가 개체를 반환합니다.

두 번째 연산자는 개체의 복사본을 만들고 개체를 증가시킨 다음 복사본을 반환합니다.

### <a name="example"></a>예제

```cpp
// std__regex__regex_iterator_operator_inc.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }
```

```Output
match == a
match == a
match == a
```

## <a name="op_eq"></a>  regex_iterator::operator=

반복기가 같은지 비교합니다.

```cpp
bool operator==(const regex_iterator& right);
```

### <a name="parameters"></a>매개 변수

`right` 비교할 반복기입니다.

### <a name="remarks"></a>설명

멤버 함수는 `*this` 와 `right` 가 둘 다 시퀀스의 끝 반복기이거나 둘 다 시퀀스의 끝 반복기가 아니고 `begin == right.begin`, `end == right.end`, `pregex == right.pregex`및 `flags == right.flags`가 아닌 경우 true를 반환합니다. 그렇지 않으면 false를 반환합니다.

### <a name="example"></a>예제

```cpp
// std__regex__regex_iterator_operator_as.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }
```

```Output
match == a
match == a
match == a
```

## <a name="op_arrow"></a>  regex_iterator::operator-&gt;

지정된 일치 항목에 액세스합니다.

```cpp
const match_results<BidIt> * operator->();
```

### <a name="remarks"></a>설명

멤버 함수는 저장된 값 `match`의 주소를 반환합니다.

### <a name="example"></a>예제

```cpp
// std__regex__regex_iterator_operator_arrow.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }
```

```Output
match == a
match == a
match == a
```

## <a name="pointer"></a>  regex_iterator::pointer

일치 항목에 대한 포인터의 형식입니다.

```cpp
typedef match_results<BidIt> *pointer;
```

### <a name="remarks"></a>설명

이 형식은 `match_results<BidIt>*`의 동의어로, 여기서 `BidIt` 는 템플릿 매개 변수입니다.

### <a name="example"></a>예제

```cpp
// std__regex__regex_iterator_pointer.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }
```

```Output
match == a
match == a
match == a
```

## <a name="reference"></a>  regex_iterator::reference

일치 항목에 대한 참조의 형식입니다.

```cpp
typedef match_results<BidIt>& reference;
```

### <a name="remarks"></a>설명

이 형식은 `match_results<BidIt>&`의 동의어로, 여기서 `BidIt` 는 템플릿 매개 변수입니다.

### <a name="example"></a>예제

```cpp
// std__regex__regex_iterator_reference.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }

```

```Output
match == a
match == a
match == a
```

## <a name="regex_iterator"></a>  regex_iterator::regex_iterator

반복기를 생성합니다.

```cpp
regex_iterator();

regex_iterator(BidIt first,
    BidIt last,
    const regex_type& re,
    regex_constants::match_flag_type f = regex_constants::match_default);
```

### <a name="parameters"></a>매개 변수

`first` 일치 하는 시퀀스의 시작입니다.

`last` 일치 하는 시퀀스의 끝입니다.

`re` 정규식 일치 항목입니다.

`f` 일치 하는 항목에 대 한 플래그입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 시퀀스의 끝 반복기를 생성합니다. 두 번째 생성자는 `begin` 로 저장된 값 `first`, `end` 로 저장된 값 `last`, `pregex` 로 저장된 값 `&re`및 `flags` 로 저장된 값 `f`를 초기화합니다. 그런 다음 `regex_search(begin, end, match, *pregex, flags)`를 호출합니다. 검색에 실패하면 생성자는 개체를 시퀀스의 끝 반복기로 설정합니다.

### <a name="example"></a>예제

```cpp
// std__regex__regex_iterator_construct.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }

```

```Output
match == a
match == a
match == a
```

## <a name="regex_type"></a>  regex_iterator::regex_type

일치 항목을 찾을 정규식의 형식입니다.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>설명

typedef는 `basic_regex<Elem, RXtraits>`의 동의어입니다.

### <a name="example"></a>예제

```cpp
// std__regex__regex_iterator_regex_type.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }

```

```Output
match == a
match == a
match == a
```

## <a name="value_type"></a>  regex_iterator::value_type

일치 항목의 형식입니다.

```cpp
typedef match_results<BidIt> value_type;
```

### <a name="remarks"></a>설명

이 형식은 `match_results<BidIt>`의 동의어로, 여기서 `BidIt` 는 템플릿 매개 변수입니다.

### <a name="example"></a>예제

```cpp
// std__regex__regex_iterator_value_type.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }

```

```Output
match == a
match == a
match == a
```

## <a name="see-also"></a>참고자료

[\<regex>](../standard-library/regex.md)<br/>
[regex_constants 클래스](../standard-library/regex-constants-class.md)<br/>
[regex_error 클래스](../standard-library/regex-error-class.md)<br/>
[\<regex> 함수](../standard-library/regex-functions.md)<br/>
[regex_iterator 클래스](../standard-library/regex-iterator-class.md)<br/>
[\<regex> 연산자](../standard-library/regex-operators.md)<br/>
[regex_token_iterator 클래스](../standard-library/regex-token-iterator-class.md)<br/>
[regex_traits 클래스](../standard-library/regex-traits-class.md)<br/>
[\<regex> 형식 정의](../standard-library/regex-typedefs.md)<br/>
