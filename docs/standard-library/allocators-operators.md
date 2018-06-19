---
title: '&lt;allocators&gt; 연산자 | Microsoft 문서'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
dev_langs:
- C++
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: 25e40157c1872df3e970bb234accab5c487c6287
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33841130"
---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt; 연산자

이것은 전역 서식 연산자 함수에 정의 된 &lt;할당자&gt;합니다. 클래스 멤버 연산자 함수를 클래스 설명서를 참조 하십시오.

|||
|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator!=

지정된 클래스의 할당자 개체가 다른지 테스트합니다.

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`left`|같지 않은지를 테스트할 할당자 개체 중 하나입니다.|
|`right`|같지 않은지를 테스트할 할당자 개체 중 하나입니다.|

### <a name="return-value"></a>반환 값

할당자 개체가 같지 않으면 **true**이고 할당자 개체가 같으면 **false**입니다.

### <a name="remarks"></a>설명

템플릿 연산자가 `!(left == right)`를 반환합니다.

## <a name="op_eq_eq"></a>  operator==

지정된 클래스의 할당자 개체가 같은지 테스트합니다.

```cpp
template <class Type, class Sync>
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`left`|같은지를 테스트할 할당자 개체 중 하나입니다.|
|`right`|같은지를 테스트할 할당자 개체 중 하나입니다.|

### <a name="return-value"></a>반환 값

할당자 개체가 같으면 **true**이고 할당자 개체가 같지 않으면 **false**입니다.

### <a name="remarks"></a>설명

템플릿 연산자가 `left.equals(right)`를 반환합니다.

## <a name="see-also"></a>참고자료

[\<allocators>](../standard-library/allocators-header.md)
