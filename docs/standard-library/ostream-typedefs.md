---
title: '&lt;ostream&gt; 형식 정의 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: 8c451b16a581ab13f87c7bcca793efe3a0f07bf5
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; 형식 정의

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>  ostream

`char`에서 특수화된 basic_ostream 및 `char`에서 특수화된 `char_traits`를 통해 형식을 만듭니다.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함하는 `char` 형식의 요소용으로 특수화된 [basic_ostream](../standard-library/basic-ostream-class.md) 템플릿 클래스와 동일한 의미입니다.

## <a name="wostream"></a>  wostream

`wchar_t`에서 특수화된 basic_ostream 및 `wchar_t`에서 특수화된 `char_traits`를 통해 형식을 만듭니다.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함하는 `wchar_t` 형식의 요소용으로 특수화된 [basic_ostream](../standard-library/basic-ostream-class.md) 템플릿 클래스와 동일한 의미입니다.

## <a name="see-also"></a>참고자료

[\<ostream>](../standard-library/ostream.md)<br/>
