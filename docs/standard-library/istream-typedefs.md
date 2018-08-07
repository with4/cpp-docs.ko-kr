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
ms.openlocfilehash: bea06c9799783feafaff1f68f4019463e452a4f2
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958857"
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt; 형식 정의

||||
|-|-|-|
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a>  iostream

형식 `basic_iostream` 에서 특수화 된 **char**합니다.

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>설명

형식은 템플릿 클래스에 대 한 동의어 [basic_iostream](../standard-library/basic-iostream-class.md)형식의 요소용으로 특수화 된 **char** 기본 문자 특성을 포함 합니다.

## <a name="istream"></a>  istream

형식 `basic_istream` 에서 특수화 된 **char**합니다.

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>설명

형식은 템플릿 클래스에 대 한 동의어 [basic_istream](../standard-library/basic-istream-class.md)형식의 요소용으로 특수화 된 **char** 기본 문자 특성을 포함 합니다.

## <a name="wiostream"></a>  wiostream

형식 `basic_iostream` 에서 특수화 된 **wchar_t**합니다.

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>설명

형식은 템플릿 클래스에 대 한 동의어 [basic_iostream](../standard-library/basic-iostream-class.md)형식의 요소용으로 특수화 된 **wchar_t** 기본 문자 특성을 포함 합니다.

## <a name="wistream"></a>  wistream

형식 `basic_istream` 에서 특수화 된 **wchar_t**합니다.

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>설명

형식은 템플릿 클래스에 대 한 동의어 [basic_istream](../standard-library/basic-istream-class.md)형식의 요소용으로 특수화 된 **wchar_t** 기본 문자 특성을 포함 합니다.

## <a name="see-also"></a>참고자료

[\<istream>](../standard-library/istream.md)<br/>
