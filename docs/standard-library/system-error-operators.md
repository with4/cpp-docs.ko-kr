---
title: '&lt;system_error&gt; 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
dev_langs:
- C++
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: 19329f90b94edada24c4afe124eed4e4e8443b74
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ltsystemerrorgt-operators"></a>&lt;system_error&gt; 연산자

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&lt;](#op_lt)|[operator==](#op_eq_eq)|

## <a name="op_eq_eq"></a>  operator==

연산자의 좌변에 있는 개체가 우변에 있는 개체와 같은지 테스트합니다.

```cpp
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`left`|같은지 테스트할 개체입니다.|
|`right`|같은지 테스트할 개체입니다.|

### <a name="return-value"></a>반환 값

개체가 같으면 **true**이고, 개체가 같지 않으면 **false**입니다.

### <a name="remarks"></a>설명

함수는 `left.category() == right.category() && left.value() == right.value()`를 반환합니다.

## <a name="op_neq"></a>  operator!=

연산자의 좌변에 있는 개체가 우변에 있는 개체와 같지 않은지 테스트합니다.

```cpp
bool operator!=(const error_code& left,
    const error_condition& right);

bool operator!=(const error_condition& left,
    const error_code& right);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`left`|같지 않은지 테스트할 개체입니다.|
|`right`|같지 않은지 테스트할 개체입니다.|

### <a name="return-value"></a>반환 값

`left`에서 전달된 개체가 `right`에서 전달된 개체와 같지 않으면 **true**이고, 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

함수는 `!(left == right)`를 반환합니다.

## <a name="op_lt"></a>  operator&lt;

개체가 비교를 위해 전달된 개체보다 작은지 여부를 테스트합니다.

```cpp
template <class _Enum>
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type right);

template <class _Enum>
inline bool operator<(
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type left, _Enum right);

template <class _Enum>
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type right);

template <class _Enum>
inline bool operator<(
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type left, _Enum right);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`left`|비교할 개체입니다.|
|`right`|비교할 개체입니다.|

### <a name="return-value"></a>반환 값

`left`에서 전달된 개체가 `right`에서 전달된 개체보다 작으면 **true**이고, 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

이 함수는 오류 순서를 테스트합니다.

## <a name="see-also"></a>참고자료

[<system_error>](../standard-library/system-error.md)<br/>
