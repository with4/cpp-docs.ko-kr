---
title: '&lt;istream&gt; 연산자 | Microsoft 문서'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- istream/std::operator&gt;&gt;
dev_langs:
- C++
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 60ec526dd8874529b60558f7131c31f0bf4a2d3b
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961115"
---
# <a name="ltistreamgt-operators"></a>&lt;istream&gt; 연산자

## <a name="op_gt_gt"></a>  operator&gt;&gt;

스트림에서 문자 및 문자열을 추출합니다.

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem* str);

template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char& Ch);

template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

### <a name="parameters"></a>매개 변수

*Ch* 문자입니다.

*Istr* 스트림입니다.

*str* 문자열입니다.

*val* 형식입니다.

### <a name="return-value"></a>반환 값

스트림

### <a name="remarks"></a>설명

`basic_istream` 클래스도 여러 가지 추출 연산자를 정의합니다. 자세한 내용은 [basic_istream::operator>>](../standard-library/basic-istream-class.md#op_gt_gt)를 참조하세요.

다음 템플릿 함수는

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

이 함수는 최대 *N* - 1개 요소를 추출하여 _ *Str*에서 시작하는 배열에 저장합니다. `Istr`. [width](../standard-library/ios-base-class.md#width)가 0보다 큰 경우 *N*은 `Istr`. **너비**이 고, 그렇지 않으면 것이 가장 큰 배열 크기 `Elem` 선언할 수 있습니다. 함수는 항상 값을 저장 `Elem()` 추출 된 요소를 저장 합니다. 추출은 파일의 끝, **Elem**(0) 값을 갖는 문자(추출되지 않음) 또는 [ws](../standard-library/istream-functions.md#ws)에 의해 삭제될 모든 요소(추출되지 않음)에서 미리 중지됩니다. 함수가 요소를 추출하지 않는 경우 `Istr`. [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). 어떤 경우든 `Istr`. **너비**(0)를 반환 *Istr*합니다.

**보안 참고** null로 끝나는 문자열 입력 스트림에서 추출 되는 대상 버퍼의 크기를 초과할 수 없습니다 *str*합니다. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요.

다음 템플릿 함수는

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

가능 하 고 저장 하는 경우 요소를 추출 *Ch*합니다. 그렇지 않으면 **is**. [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**)를 호출합니다. 어떤 경우에 반환 *Istr*합니다.

다음 템플릿 함수는

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

`Istr` >> ( `char`**\***) `str`을 반환합니다.

다음 템플릿 함수는

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

`Istr` >> ( **char&**) `Ch`를 반환합니다.

다음 템플릿 함수는

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

`Istr` >> ( **char \***) `str`을 반환합니다.

템플릿 함수는 다음과 같습니다.

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

`Istr` >> ( **char&**) `Ch`를 반환합니다.

다음 템플릿 함수는

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

`Istr` `>>` `val`을 반환하고 프로세스에서 `Istr`에 대한 `rvalue reference`를 `lvalue`로 변환합니다.

### <a name="example"></a>예

```cpp
// istream_op_extract.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   ws( cin );
   char c[10];

   cin.width( 9 );
   cin >> c;
   cout << c << endl;
}
```

## <a name="see-also"></a>참고자료

[\<istream>](../standard-library/istream.md)<br/>
