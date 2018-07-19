---
title: '&lt;system_error&gt; 함수 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- system_error/std::generic_category
- system_error/std::make_error_code
- system_error/std::make_error_condition
- system_error/std::system_category
ms.assetid: 57d6f15f-f0b7-4e2f-80fe-31d3c320ee33
helpviewer_keywords:
- std::generic_category
- std::make_error_code
- std::make_error_condition
- std::system_category
ms.openlocfilehash: 838a63fc43ef71561c0911cfa4c85c76cf04bc08
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959667"
---
# <a name="ltsystemerrorgt-functions"></a>&lt;system_error&gt; 함수

||||
|-|-|-|
|[generic_category](#generic_category)|[make_error_code](#make_error_code)|[make_error_condition](#make_error_condition)|
|[system_category](#system_category)|

## <a name="generic_category"></a>  generic_category

일반 오류의 범주를 나타냅니다.

```cpp
extern const error_category& generic_category();
```

### <a name="remarks"></a>설명

합니다 `generic_category` 개체의 구현인 [error_category](../standard-library/error-category-class.md)합니다.

## <a name="make_error_code"></a>  make_error_code

오류 코드 개체를 만듭니다.

```cpp
error_code make_error_code(generic_errno _Errno);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*_Errno*|오류 코드 개체에 저장할 열거형 값입니다.|

### <a name="return-value"></a>반환 값

오류 코드 개체입니다.

### <a name="remarks"></a>설명

## <a name="make_error_condition"></a>  make_error_condition

오류 조건 개체를 만듭니다.

```cpp
error_condition make_error_condition(generic_errno _Errno);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*_Errno*|오류 조건 개체에 저장할 열거형 값입니다.|

### <a name="return-value"></a>반환 값

오류 조건 개체입니다.

### <a name="remarks"></a>설명

## <a name="system_category"></a>  system_category

하위 수준 시스템 오버플로로 인해 발생하는 오류의 범주를 나타냅니다.

```cpp
extern const error_category& system_category();
```

### <a name="remarks"></a>설명

합니다 `system_category` 개체의 구현인 [error_category](../standard-library/error-category-class.md)합니다.

## <a name="see-also"></a>참고자료

[<system_error>](../standard-library/system-error.md)<br/>
