---
title: '&lt;sstream&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <sstream>
dev_langs:
- C++
helpviewer_keywords:
- sstream header
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ee9beb54dd241c6987b79db238f033f3d169497
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861677"
---
# <a name="ltsstreamgt"></a>&lt;sstream&gt;

할당된 개체 배열에 저장된 시퀀스에 대한 Iostreams 작업을 지원하는 여러 템플릿 클래스를 정의합니다. 이러한 시퀀스와 템플릿 클래스 [basic_string](../standard-library/basic-string-class.md)의 개체 간을 쉽게 변환할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
namespace std {
template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_stringbuf;
typedef basic_stringbuf<char>
stringbuf;
typedef basic_stringbuf<wchar_t> wstringbuf;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_istringstream;
typedef basic_istringstream<char>
istringstream;
typedef basic_istringstream<wchar_t> wistringstream;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_ostringstream;
typedef basic_ostringstream<char>
ostringstream;
typedef basic_ostringstream<wchar_t> wostringstream;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_stringstream;
typedef basic_stringstream<char>
stringstream;
typedef basic_stringstream<wchar_t> wstringstream;
// TEMPLATE FUNCTIONS
template <class CharType, class Traits, class Allocator>
void swap(
    basic_stringbuf<CharType, Traits, Allocator>& left,
    basic_stringbuf<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap(
    basic_istringstream<CharType, Traits, Allocator>& left,
    basic_istringstream<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap(
    basic_ostringstream<CharType, Traits, Allocator>& left,
    basic_ostringstream<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap (
    basic_stringstream<CharType, Traits, Allocator>& left,
    basic_stringstream<CharType, Traits, Allocator>& right);

}  // namespace std
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`left`|`sstream` 개체에 대한 참조입니다.|
|`right`|`sstream` 개체에 대한 참조입니다.|

## <a name="remarks"></a>설명

`char *` 형식의 개체는 스트리밍을 위해 [\<strstream>](../standard-library/strstream.md)의 기능을 사용할 수 있습니다. 그러나 \<a m >는 사용 되지 않습니다 사용 하 여 \<a m >는 것이 좋습니다.

### <a name="typedefs"></a>형식 정의

|형식 이름|설명|
|-|-|
|[istringstream](../standard-library/sstream-typedefs.md#istringstream)|`char` 템플릿 매개 변수에 대해 특수화된 `basic_istringstream` 형식을 만듭니다.|
|[ostringstream](../standard-library/sstream-typedefs.md#ostringstream)|`char` 템플릿 매개 변수에 대해 특수화된 `basic_ostringstream` 형식을 만듭니다.|
|[stringbuf](../standard-library/sstream-typedefs.md#stringbuf)|`char` 템플릿 매개 변수에 대해 특수화된 `basic_stringbuf` 형식을 만듭니다.|
|[stringstream](../standard-library/sstream-typedefs.md#stringstream)|`char` 템플릿 매개 변수에 대해 특수화된 `basic_stringstream` 형식을 만듭니다.|
|[wistringstream](../standard-library/sstream-typedefs.md#wistringstream)|`wchar_t` 템플릿 매개 변수에 대해 특수화된 `basic_istringstream` 형식을 만듭니다.|
|[wostringstream](../standard-library/sstream-typedefs.md#wostringstream)|`wchar_t` 템플릿 매개 변수에 대해 특수화된 `basic_ostringstream` 형식을 만듭니다.|
|[wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf)|`wchar_t` 템플릿 매개 변수에 대해 특수화된 `basic_stringbuf` 형식을 만듭니다.|
|[wstringstream](../standard-library/sstream-typedefs.md#wstringstream)|`wchar_t` 템플릿 매개 변수에 대해 특수화된 `basic_stringstream` 형식을 만듭니다.|

### <a name="manipulators"></a>조작자

|||
|-|-|
|[swap](../standard-library/sstream-functions.md#sstream_swap)|두 `sstream` 개체 간에 값을 교환합니다.|

### <a name="classes"></a>클래스

|클래스|설명|
|-|-|
|[basic_stringbuf](../standard-library/basic-stringbuf-class.md)|배열 개체에 저장된 요소의 시퀀스에서 문자 특성이 **Tr** 클래스에 의해 결정되는 **Elem** 형식 요소의 전송을 제어하는 스트림 버퍼에 대해 설명합니다.|
|[basic_istringstream](../standard-library/basic-istringstream-class.md)|이 템플릿 클래스는 형식 **Elem**의 요소가 있고 문자 특성이 **Tr**에 의해 결정되며 요소가 클래스 `Alloc`의 할당자에 의해 할당되는 클래스 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`>의 스트림 버퍼에서 요소 및 인코드된 개체의 추출을 제어하는 개체를 설명합니다.|
|[basic_ostringstream](../standard-library/basic-ostringstream-class.md)|이 템플릿 클래스는 형식 **Elem**의 요소가 있고 문자 특성이 **Tr**에 의해 결정되며 요소가 클래스 `Alloc`의 할당자에 의해 할당되는 클래스 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`>의 스트림 버퍼로의 요소 및 인코드된 개체 삽입을 제어하는 개체를 설명합니다.|
|[basic_stringstream](../standard-library/basic-stringstream-class.md)|이 템플릿 클래스는 형식 **Elem**의 요소가 있고 문자 특성이 **Tr**에 의해 결정되며 요소가 클래스 `Alloc`의 할당자에 의해 할당되는 클래스 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`>의 스트림 버퍼로를 사용한 요소 및 인코드된 개체 삽입 및 추출을 제어하는 개체를 설명합니다.|

## <a name="requirements"></a>요구 사항

- **헤더:** \<sstream>

- **네임스페이스:** std

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream 프로그래밍](../standard-library/iostream-programming.md)<br/>
[iostreams 규칙](../standard-library/iostreams-conventions.md)<br/>
