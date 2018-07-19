---
title: '&lt;sstream&gt; 함수 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: 354632a3c001f2352821d9a1d0b493291c21a337
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953939"
---
# <a name="ltsstreamgt-functions"></a>&lt;sstream&gt; 함수

||
|-|
|[swap](#sstream_swap)|

## <a name="sstream_swap"></a>  swap

두 `sstream` 개체 간에 값을 교환합니다.

```cpp
template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringbuf<Elem, Tr, Alloc>& left,
    basic_stringbuf<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_istringstream<Elem, Tr, Alloc>& left,
    basic_istringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_ostringstream<Elem, Tr, Alloc>& left,
    basic_ostringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringstream<Elem, Tr, Alloc>& left,
    basic_stringstream<Elem, Tr, Alloc>& right);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*left*|`sstream` 개체에 대한 참조입니다.|
|*right*|`sstream` 개체에 대한 참조입니다.|

### <a name="remarks"></a>설명

이 템플릿 함수는 `left.swap(right)`을 실행합니다.

## <a name="see-also"></a>참고자료

[\<sstream>](../standard-library/sstream.md)<br/>
