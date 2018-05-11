---
title: '&lt;istream&gt; 형식 정의 | Microsoft 문서'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: 20d92a0bf759c9f8170464985bd2b8af4d2bec08
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt; 형식 정의

||||
|-|-|-|
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a>  iostream

`char`에서 특수화된 `basic_iostream` 형식입니다.

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함하는 `char` 형식의 요소용으로 특수화된 [basic_iostream](../standard-library/basic-iostream-class.md) 템플릿 클래스의 동의어입니다.

## <a name="istream"></a>  istream

`char`에서 특수화된 `basic_istream` 형식입니다.

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함하는 `char` 형식의 요소용으로 특수화된 [basic_istream](../standard-library/basic-istream-class.md) 템플릿 클래스의 동의어입니다.

## <a name="wiostream"></a>  wiostream

`wchar_t`에서 특수화된 `basic_iostream` 형식입니다.

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함하는 `wchar_t` 형식의 요소용으로 특수화된 [basic_iostream](../standard-library/basic-iostream-class.md) 템플릿 클래스의 동의어입니다.

## <a name="wistream"></a>  wistream

`wchar_t`에서 특수화된 `basic_istream` 형식입니다.

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함하는 `wchar_t` 형식의 요소용으로 특수화된 [basic_istream](../standard-library/basic-istream-class.md) 템플릿 클래스의 동의어입니다.

## <a name="see-also"></a>참고자료

[\<istream>](../standard-library/istream.md)<br/>
