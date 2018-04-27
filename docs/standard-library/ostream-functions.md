---
title: '&lt;ostream&gt; 함수 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
caps.latest.revision: 15
manager: ghogen
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.openlocfilehash: 41463d912b3ab33812a1f7c0a0ea5f8172036e57
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt; 함수

이것은에 정의 된 기본 서식 파일 함수 &lt;ostream&gt;합니다. 멤버 함수에 대 한 참조는 [basic_ostream 클래스](basic-ostream-class.md) 설명서입니다.

||||
|-|-|-|
|[endl](#endl)|[ends](#ends)|[flush](#flush)|
|[swap](#swap)|

## <a name="endl"></a>endl

줄을 종료하고 버퍼를 플러시합니다.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& endl(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>매개 변수

*Elem* 요소 형식입니다.

*Ostr* 형식의 개체로 **basic_ostream**합니다.

*Tr* 문자 특성입니다.

### <a name="return-value"></a>반환 값

형식의 개체 **basic_ostream**합니다.

### <a name="remarks"></a>설명

조작자 호출 *Ostr*.[ 배치](../standard-library/basic-ostream-class.md#put)(*Ostr*.[ 확대 변환](../standard-library/basic-ios-class.md#widen)('\n')), 한 다음 호출 *Ostr*.[ 플러시](../standard-library/basic-ostream-class.md#flush)합니다. 반환 *Ostr*합니다.

### <a name="example"></a>예제

```cpp
// ostream_endl.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << endl;
}
```

```Output
testing
```

## <a name="ends"></a>끝

문자열을 종료합니다.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& ends(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>매개 변수

*Elem* 요소 형식입니다.

*Ostr* 형식의 개체로 **basic_ostream**합니다.

*Tr* 문자 특성입니다.

### <a name="return-value"></a>반환 값

형식의 개체 **basic_ostream**합니다.

### <a name="remarks"></a>설명

조작자 호출 *Ostr*.[ 배치](../standard-library/basic-ostream-class.md#put)(*Elem*('\0')). 반환 *Ostr*합니다.

### <a name="example"></a>예제

```cpp
// ostream_ends.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "a";
   cout << "b" << ends;
   cout << "c" << endl;
}
```

```Output
ab c
```

## <a name="flush"></a>flush

버퍼를 플러시합니다.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& flush(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>매개 변수

*Elem* 요소 형식입니다.

*Ostr* 형식의 개체로 **basic_ostream**합니다.

*Tr* 문자 특성입니다.

### <a name="return-value"></a>반환 값

형식의 개체 **basic_ostream**합니다.

### <a name="remarks"></a>설명

조작자 호출 *Ostr*.[ 플러시](../standard-library/basic-ostream-class.md#flush)합니다. 반환 *Ostr*합니다.

### <a name="example"></a>예제

```cpp
// ostream_flush.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << flush;
}
```

```Output
testing
```

## <a name="swap"></a>swap

두 값을 교환 **basic_ostream** 개체입니다.

```cpp
template <class Elem, class Tr>
void swap(
   basic_ostream<Elem, Tr>& left,
   basic_ostream<Elem, Tr>& right);
```

### <a name="parameters"></a>매개 변수

*Elem* 요소 형식입니다.

*Tr* 문자 특성입니다.

*왼쪽* 에 대 한 lvalue 참조는 **basic_ostream** 개체입니다.

*오른쪽* 에 대 한 lvalue 참조는 **basic_ostream** 개체입니다.

### <a name="remarks"></a>설명

템플릿 함수 **스왑** 실행 `left.swap(right)`합니다.

## <a name="see-also"></a>참고자료

[\<ostream>](../standard-library/ostream.md)
