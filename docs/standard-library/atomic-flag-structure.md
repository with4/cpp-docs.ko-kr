---
title: atomic_flag 구조체 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
dev_langs:
- C++
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06959bd5a22c65077f447f0f0e776025cbe5ced5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="atomicflag-structure"></a>atomic_flag 구조체

`bool` 플래그를 원자 단위로 설정하고 지우는 개체를 설명합니다. 원자 플래그에 대한 작업은 항상 잠금 해제입니다.

## <a name="syntax"></a>구문

```cpp
struct atomic_flag;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[clear](#clear)|저장된 플래그를 `false`로 설정합니다.|
|[test_and_set](#test_and_set)|저장된 플래그를 `true`로 설정하고 초기 플래그 값을 반환합니다.|

## <a name="remarks"></a>설명

`atomic_flag` 개체는 멤버가 아닌 [atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear), [atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit), [atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set) 및 [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit) 함수로 전달할 수 있습니다. `ATOMIC_FLAG_INIT` 값을 사용하여 초기화할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<원자성 >

**네임스페이스:** std

## <a name="clear"></a>  atomic_flag::clear

지정한 [memory_order](../standard-library/atomic-enums.md#memory_order_enum) 제약 조건 내에서 `*this`에 저장된 `bool` 플래그를 `false`로 설정합니다.

```cpp
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>매개 변수

`Order` A [memory_order](../standard-library/atomic-enums.md#memory_order_enum)합니다.

## <a name="test_and_set"></a>  atomic_flag::test_and_set

지정한 [memory_order](../standard-library/atomic-enums.md#memory_order_enum) 제약 조건 내에서 `*this`에 저장된 `bool` 플래그를 `true`로 설정합니다.

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>매개 변수

`Order` A [memory_order](../standard-library/atomic-enums.md#memory_order_enum)합니다.

### <a name="return-value"></a>반환 값

`*this`에 저장된 플래그의 초기 값입니다.

## <a name="see-also"></a>참고자료

[\<atomic>](../standard-library/atomic.md)<br/>
