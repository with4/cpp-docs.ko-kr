---
title: '&lt;string&gt; 형식 정의 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- string/std::string
- string/std::u16string
- string/std::u32string
- string/std::wstring
ms.assetid: fdca01e9-f2f1-4b59-abda-0093d760b3cc
ms.openlocfilehash: 5747d511777ae6f1f32d8e93bb6ee90bd0193bf9
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959981"
---
# <a name="ltstringgt-typedefs"></a>&lt;string&gt; 형식 정의

||||
|-|-|-|
|[string](#string)|[u16string](#u16string)|[u32string](#u32string)|
|[wstring](#wstring)|

## <a name="string"></a>  string

템플릿 클래스의 특수화를 설명 하는 형식 [basic_string](../standard-library/basic-string-class.md) 형식의 요소가 포함 된 **char**합니다.

`basic_string`을 특수화하는 기타 형식 정의에는 [wstring](../standard-library/string-typedefs.md#wstring), [u16string](../standard-library/string-typedefs.md#u16string), [u32string](../standard-library/string-typedefs.md#u32string) 등이 있습니다.

```cpp
typedef basic_string<char, char_traits<char>, allocator<char>> string;
```

### <a name="remarks"></a>설명

아래의 코드 두 줄은 동일한 선언입니다.

```cpp
string str("");

basic_string<char> str("");
```

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="u16string"></a>  u16string

`char16_t` 형식 요소가 포함된 템플릿 클래스 [basic_string](../standard-library/basic-string-class.md)의 특수화를 설명하는 형식입니다.

`basic_string`을 특수화하는 기타 형식 정의에는 [wstring](../standard-library/string-typedefs.md#wstring), [string](../standard-library/string-typedefs.md#string), [u32string](../standard-library/string-typedefs.md#u32string) 등이 있습니다.

```cpp
typedef basic_string<char16_t, char_traits<char16_t>, allocator<char16_t>> u16string;
```

### <a name="remarks"></a>설명

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="u32string"></a>  u32string

`char32_t` 형식 요소가 포함된 템플릿 클래스 [basic_string](../standard-library/basic-string-class.md)의 특수화를 설명하는 형식입니다.

`basic_string`을 특수화하는 기타 형식 정의에는 [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string), [wstring](../standard-library/string-typedefs.md#wstring) 등이 있습니다.

```cpp
typedef basic_string<char32_t, char_traits<char32_t>, allocator<char32_t>> u32string;
```

### <a name="remarks"></a>설명

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="wstring"></a>  wstring

템플릿 클래스의 특수화를 설명 하는 형식 [basic_string](../standard-library/basic-string-class.md) 형식의 요소가 포함 된 **wchar_t**합니다.

`basic_string`을 특수화하는 기타 형식 정의에는 [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string), [u32string](../standard-library/string-typedefs.md#u32string) 등이 있습니다.

```cpp
typedef basic_string<wchar_t, char_traits<wchar_t>, allocator<wchar_t>> wstring;
```

### <a name="remarks"></a>설명

아래의 코드 두 줄은 동일한 선언입니다.

```cpp
wstring wstr(L"");

basic_string<wchar_t> wstr(L"");
```

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

> [!NOTE]
> 크기인 **wchar_t** 구현 시 정의 됩니다. 코드에 종속 되 면 **wchar_t** 하려면 특정 크기를 검사 합니다 플랫폼의 구현 (예를 들어 `sizeof(wchar_t)`). 모든 플랫폼에서 너비가 동일하게 유지되도록 보장되는 문자열 문자 형식이 필요한 경우에는 [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string) 또는 [u32string](../standard-library/string-typedefs.md#u32string)을 사용합니다.

## <a name="see-also"></a>참고자료

[\<string>](../standard-library/string.md)<br/>
