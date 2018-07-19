---
title: '&lt;ostream&gt; 형식 정의 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 094952a76d8e46e4244cf57a8c5a47c929f3ae37
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960356"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; 형식 정의

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>  ostream

특수화 된 basic_ostream에서 유형을 만듭니다 **char** 하 고 `char_traits` 에서 특수화 된 **char**합니다.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>설명

형식은 템플릿 클래스에 대 한 동의어 [basic_ostream](../standard-library/basic-ostream-class.md)형식의 요소용으로 특수화 된 **char** 기본 문자 특성을 포함 합니다.

## <a name="wostream"></a>  wostream

특수화 된 basic_ostream에서 유형을 만듭니다 **wchar_t** 하 고 `char_traits` 에서 특수화 된 **wchar_t**합니다.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>설명

형식은 템플릿 클래스에 대 한 동의어 [basic_ostream](../standard-library/basic-ostream-class.md)형식의 요소용으로 특수화 된 **wchar_t** 기본 문자 특성을 포함 합니다.

## <a name="see-also"></a>참고자료

[\<ostream>](../standard-library/ostream.md)<br/>
