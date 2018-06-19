---
title: atomic 구조체 | Microsoft 문서
ms.custom: ''
ms.date: 04/20/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- atomic/std::atomic
dev_langs:
- C++
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7308c127bebd2185429509315ebafb3d83a7efea
ms.sourcegitcommit: b0d5557dbb57128da560a0a4634312ec4a050a90
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2018
ms.locfileid: "34476109"
---
# <a name="atomic-structure"></a>atomic 구조체

형식의 저장 된 값에 원자성 작업을 수행 하는 개체에 설명 *Ty*합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct atomic;
```

## <a name="members"></a>멤버

|멤버|설명|
|----------|-----------------|
|**생성자**||
|[atomic](#atomic)|atomic 개체를 생성합니다.|
|**연산자**||
|[atomic:: operator Ty](#op_ty)|저장된 값을 읽고 반환합니다. ([atomic::load](#load))|
|[atomic:: operator =](#op_eq)|지정된 값을 사용하여 저장된 값을 바꿉니다. ([atomic::store](#store))|
|[atomic:: operator + +](#op_inc)|저장된 값을 증가시킵니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.|
|[atomic:: operator + =](#op_add_eq)|지정된 값을 저장된 값에 더합니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.|
|[atomic:: operator-](#op_dec)|저장된 값을 감소시킵니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.|
|[atomic:: operator =](#op_sub_eq)|지정된 값을 저장된 값에서 뺍니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.|
|[atomic:: operator & =](#op_and_eq)|연산을 수행 하 고 지정 된 값과 저장 된 값에 있습니다. 정수 계열 특수화에서만 사용됩니다.|
|[atomic:: operator&#124;=](#op_or_eq)|연산을 수행 또는 지정 된 값과 저장 된 값입니다. 정수 계열 특수화에서만 사용됩니다.|
|[atomic:: operator ^ =](#op_xor_eq)|배타적 비트를 수행 합니다. 또는 지정 된 값과 저장 된 값입니다. 정수 계열 특수화에서만 사용됩니다.|
|**함수**||
|[compare_exchange_strong](#compare_exchange_strong)|수행 된 *atomic_compare_and_exchange* 에 대 한 작업이 **이** 결과 반환 합니다.|
|[compare_exchange_weak](#compare_exchange_weak)|수행 된 *weak_atomic_compare_and_exchange* 에 대 한 작업이 **이** 결과 반환 합니다.|
|[fetch_add](#fetch_add)|지정된 값을 저장된 값에 더합니다.|
|[fetch_and](#fetch_and)|연산을 수행 하 고 지정 된 값과 저장 된 값에 있습니다.|
|[fetch_or](#fetch_or)|연산을 수행 또는 지정 된 값과 저장 된 값입니다.|
|[fetch_sub](#fetch_sub)|지정된 값을 저장된 값에서 뺍니다.|
|[fetch_xor](#fetch_xor)|배타적 비트를 수행 합니다. 또는 지정 된 값과 저장 된 값입니다.|
|[is_lock_free](#is_lock_free)|지정 여부에 대 한 원자 단위 작업 **이** 는 *무료 잠금*합니다. 원자 형식의 어떤 원자 연산도 잠금을 사용하지 않는 경우 해당 원자 형식을 *잠금 해제*라고 합니다.|
|[load](#load)|저장된 값을 읽고 반환합니다.|
|[store](#store)|지정된 값을 사용하여 저장된 값을 바꿉니다.|

## <a name="remarks"></a>설명

형식 *Ty* 해야 *일반적으로 복사할 수*합니다. 즉, 사용 하 여 [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) 해당 바이트를 복사 생성 해야 합니다는 유효한 *Ty* 원래 개체와 같은지를 비교 하는 개체입니다. [compare_exchange_weak](#compare_exchange_weak) 및 [compare_exchange_strong](#compare_exchange_strong) 멤버 함수만 사용 [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) 두 지 여부를 결정 *Ty* 값 와 동일합니다. 이러한 함수는 사용 하지 않습니다는 *Ty*-정의 **연산자 = =** 합니다. 멤버 함수 **원자성** 사용 **memcpy** 형식의 값을 복사할 *Ty*합니다.

부분 특수화 **원자성\<Ty \* >** , 모든 포인터 형식에 대해 존재 합니다. 특수화를 사용하면 관리되는 포인터 값에 오프셋을 더하거나 값에서 오프셋을 뺄 수 있습니다. 형식의 인수를 사용 하는 산술 연산을 **ptrdiff_t** 의 크기에 따라 인수에 지정 된 조정 *Ty* 산술 일반 주소와 일치 하도록 합니다.

특수화를 제외한 모든 정수 계열 형식에 대해 존재 **bool**합니다. 각 특수화에서는 원자 산술 및 논리 연산을 위한 다양한 방법을 제공합니다.

||||
|-|-|-|
|**원자성\<char >**|**원자성\<char 서명 >**|**원자성\<char 부호 없음 >**|
|**원자성\<char16_t >**|**원자성\<char32_t >**|**원자성\<wchar_t >**|
|**원자성\<짧은 >**|**원자성\<부호 없는 short >**|**원자성\<int >**|
|**원자성\<부호 없는 int >**|**원자성\<긴 >**|**원자성\<부호 없는 long >**|
|**원자성\<long long >**|**원자성\<부호 없는 long long >**|

정수 계열 특수화 해당에서 파생 된 **atomic_integral** 형식입니다. 예를 들어 **원자성\<부호 없는 int >** 에서 파생 된 **atomic_uint**합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<원자성 >

**네임스페이스:** std

## <a name="atomic"></a> atomic:: atomic

atomic 개체를 생성합니다.

```cpp
atomic();
atomic( const atomic& );
atomic( Ty Value ) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*<br/>
초기화 값입니다.

### <a name="remarks"></a>설명

원자 개체를 복사 또는 이동할 수 없습니다.

개체의 원자성 인스턴스화를\<*Ty*> 형식의 인수를 사용 하는 생성자에 의해서만 초기화 될 수 있습니다 *Ty* 및 집합체 초기화를 사용 하 여 합니다. 그러나 집합체 초기화를 사용 하 여 atomic_integral 개체를 초기화할 수 있습니다.

```cpp
atomic<int> ai0 = ATOMIC_VAR_INIT(0);
atomic<int> ai1(0);
```

## <a name="op_ty"></a> atomic:: operator *Ty*

원자성 서식 파일에 지정 된 형식에 대 한 연산자\<*Ty*> 합니다. 에 저장된 된 값을 검색  **\*이**합니다.

```cpp
atomic<Ty>::operator Ty() const volatile noexcept;
atomic<Ty>::operator Ty() const noexcept;
```

### <a name="remarks"></a>설명

이 연산자가 적용 되는 **memory_order_seq_cst** [memory_order](atomic-enums.md)합니다.

## <a name="op_eq"></a> atomic:: operator =

지정된 값을 저장합니다.

```cpp
Ty operator=(
   Ty Value
) volatile noexcept;
Ty operator=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*<br/>
A *Ty* 개체입니다.

### <a name="return-value"></a>반환 값

반환 *값*합니다.

## <a name="op_inc"></a> atomic:: operator + +

저장된 값을 증가시킵니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.

```cpp
Ty atomic<Ty>::operator++(int) volatile noexcept;
Ty atomic<Ty>::operator++(int) noexcept;
Ty atomic<Ty>::operator++() volatile noexcept;
Ty atomic<Ty>::operator++() noexcept;
```

### <a name="return-value"></a>반환 값

처음 두 연산자는 반환 된 증가 값 마지막 두 연산자는 증가 하기 전에 값을 반환 합니다. 연산자를 사용 하 여는 **memory_order_seq_cst** [memory_order](atomic-enums.md)합니다.

## <a name="op_add_eq"></a> atomic:: operator + =

지정된 값을 저장된 값에 더합니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.

```cpp
Ty atomic<Ty>::operator+=(
   Ty Value
) volatile noexcept;
Ty atomic<Ty>::operator+=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*<br/>
정수 계열 또는 포인터 값입니다.

### <a name="return-value"></a>반환 값

A *Ty* 덧셈의 결과 포함 하는 개체입니다.

### <a name="remarks"></a>설명

사용 하 여이 연산자는 **memory_order_seq_cst** [memory_order](atomic-enums.md)합니다.

## <a name="op_dec"></a> atomic:: operator-

저장된 값을 감소시킵니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.

```cpp
Ty atomic<Ty>::operator--(int) volatile noexcept;
Ty atomic<Ty>::operator--(int) noexcept;
Ty atomic<Ty>::operator--() volatile noexcept;
Ty atomic<Ty>::operator--() noexcept;
```

### <a name="return-value"></a>반환 값

처음 두 연산자는 감소 된 값을 반환 마지막 두 연산자는 감소 하기 전에 값을 반환 합니다. 연산자를 사용 하 여는 **memory_order_seq_cst** [memory_order](atomic-enums.md)합니다.

## <a name="op_sub_eq"></a> atomic:: operator =

지정된 값을 저장된 값에서 뺍니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.

```cpp
Ty atomic<Ty>::operator-=(
   Ty Value
) volatile noexcept;
Ty atomic<Ty>::operator-=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*<br/>
정수 계열 또는 포인터 값입니다.

### <a name="return-value"></a>반환 값

A *Ty* 빼기의 결과 포함 하는 개체입니다.

### <a name="remarks"></a>설명

사용 하 여이 연산자는 **memory_order_seq_cst** [memory_order](atomic-enums.md)합니다.

## <a name="op_and_eq"></a> atomic:: operator & =

연산을 수행 하 고에 지정된 된 값의 저장된 된 값  **\*이**합니다. 정수 계열 특수화에서만 사용됩니다.

```cpp
atomic<Ty>::operator&= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator&= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*<br/>
형식의 값 *Ty*합니다.

### <a name="return-value"></a>반환 값

비트의 결과 및 합니다.

### <a name="remarks"></a>설명

이 연산자의 저장된 된 값 대체를 읽기-수정-쓰기 작업을 수행  **\*이** 비트와의 *값* 에 저장 된 현재 값  **\*이**, 제약 조건에 **memory_order_seq_cst** [memory_order](atomic-enums.md)합니다.

## <a name="op_or_eq"></a> atomic:: operator&#124;=

연산을 수행 하 고 지정된 된 값의 저장된 된 값에 또는  **\*이**합니다. 정수 계열 특수화에서만 사용됩니다.

```cpp
atomic<Ty>::operator|= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator|= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*<br/>
형식의 값 *Ty*합니다.

### <a name="return-value"></a>반환 값

비트의 결과 또는 합니다.

### <a name="remarks"></a>설명

이 연산자의 저장된 된 값 대체를 읽기-수정-쓰기 작업을 수행  **\*이** 비트 또는의 *값* 에 저장 된 현재 값  **\*이**, 제약 조건에 **memory_order_seq_cst** [memory_order](atomic-enums.md) 제약 조건입니다.

## <a name="op_xor_eq"></a> atomic:: operator ^ =

배타적 비트를 수행 하 고 지정된 된 값의 저장된 된 값에 또는  **\*이**합니다. 정수 계열 특수화에서만 사용됩니다.

```cpp
atomic<Ty>::operator^= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator^= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*<br/>
형식의 값 *Ty*합니다.

### <a name="return-value"></a>반환 값

배타적 비트 결과 또는 합니다.

### <a name="remarks"></a>설명

이 연산자의 저장된 된 값 대체를 읽기-수정-쓰기 작업을 수행  **\*이** 의 배타적 비트와 *값* 에 저장 된 현재 값  **\*이**, 제약 조건에 **memory_order_seq_cst** [memory_order](atomic-enums.md) 제약 조건입니다.

## <a name="compare_exchange_strong"></a> atomic:: compare_exchange_strong

에 대해 원자성 비교 및 교환 작업을 수행  **\*이**합니다.

```cpp
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) volatile noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) volatile noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Exp*<br/>
형식의 값 *Ty*합니다.

*Value*<br/>
형식의 값 *Ty*합니다.

*Order1*<br/>
첫 번째 **memory_order** 인수입니다.

*Order2*<br/>
두 번째 **memory_order** 인수입니다.

### <a name="return-value"></a>반환 값

A **bool** 값 비교의 결과 나타내는입니다.

### <a name="remarks"></a>설명

이 원자성 비교 및 교환 작업에 저장 된 값과 비교  **\*이** 와 *Exp*합니다. 작업에 저장 된 값을 대체 값이 같으면  **\*이** 와 *값* 읽기-수정-쓰기 작업을 사용 하 고 있는 메모리 순서 제약 조건을 적용 하 여 에 지정 된 *Order1*합니다. 작업에 저장 된 값을 사용 값이 같지 않으면  **\*이** 바꾸려면 *Exp* 로 지정 된 메모리 순서 제약 조건 적용 *Order2* .

두 번째를 갖지 않는 오버 로드 **memory_order** 암시적 사용 하 여 *Order2* 의 값을 기반으로 하는 *Order1*합니다. 경우 *Order1* 은 **memory_order_acq_rel**, *Order2* 은 **memory_order_acquire**합니다. 경우 *Order1* 은 **memory_order_release**, *Order2* 은 **memory_order_relaxed**합니다. 다른 모든 경우에 *Order2* 같으면 *Order1*합니다.

두 개의 오버 로드에 대 한 **memory_order** 매개 변수 값, *Order2* 않아야 **memory_order_release** 또는 **memory_order_acq_rel**의 값 보다 더 강력한 아니어야 *Order1*합니다.

## <a name="compare_exchange_weak"></a> atomic:: compare_exchange_weak

약한 원자 비교 및 교환 작업에 대해 수행  **\*이**합니다.

```cpp
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) volatile noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) volatile noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Exp*<br/>
형식의 값 *Ty*합니다.

*Value*<br/>
형식의 값 *Ty*합니다.

*Order1*<br/>
첫 번째 **memory_order** 인수입니다.

*Order2*<br/>
두 번째 **memory_order** 인수입니다.

### <a name="return-value"></a>반환 값

A **bool** 값 비교의 결과 나타내는입니다.

### <a name="remarks"></a>설명

이 원자성 비교 및 교환 작업에 저장 된 값과 비교  **\*이** 와 *Exp*합니다. 작업에 저장 된 값을 대체 값이 같으면  **\*이** 와*값* 읽기-수정-쓰기 작업을 사용 하 고 있는 메모리 순서 제약 조건을 적용 하 여 에 지정 된 *Order1*합니다. 작업에 저장 된 값을 사용 값이 같지 않으면  **\*이** 바꾸려면 *Exp* 로 지정 된 메모리 순서 제약 조건 적용 *Order2* .

약한 원자 비교 및 교환 작업 비교 되는 값이 같으면 교환을 수행 합니다. 값이 같지 않으면 교환을 수행 하 고 작업을 보장 되지 않습니다.

두 번째를 갖지 않는 오버 로드 **memory_order** 암시적 사용 하 여 *Order2* 의 값을 기반으로 하는 *Order1*합니다. 경우 *Order1* 은 **memory_order_acq_rel**, *Order2* 은 **memory_order_acquire**합니다. 경우 *Order1* 은 **memory_order_release**, *Order2* 은 **memory_order_relaxed**합니다. 다른 모든 경우에 *Order2* 같으면 *Order1*합니다.

두 개의 오버 로드에 대 한 **memory_order** 매개 변수 값, *Order2* 않아야 **memory_order_release** 또는 **memory_order_acq_rel**의 값 보다 더 강력한 아니어야 *Order1*합니다.

## <a name="exchange"></a> atomic:: exchange

지정된 된 값의 저장된 된 값을 사용 하 여  **\*이**합니다.

```cpp
Ty atomic<Ty>::exchange(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::exchange(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*<br/>
형식의 값 *Ty*합니다.

*순서*<br/>
**memory_order**.

### <a name="return-value"></a>반환 값

저장 된 값의  **\*이** 교환 하기 전입니다.

### <a name="remarks"></a>설명

이 작업을 사용 하는 읽기-수정-쓰기 작업 수행 *값* 에 저장 된 값으로 바꾸는  **\*이**, 지정 된 메모리 제약 조건 내에서  *주문*합니다.

## <a name="fetch_add"></a> atomic:: fetch_add

에 저장 된 값을 인출  **\*이**, 한 후 저장 된 값을 지정된 된 값을 추가 합니다.

```cpp
Ty atomic<Ty>::fetch_add (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_add (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*<br/>
형식의 값 *Ty*합니다.

*순서*<br/>
**memory_order**.

### <a name="return-value"></a>반환 값

A *Ty* 개체에 저장 된 값이 포함 된  **\*이** 추가 하기 전에.

### <a name="remarks"></a>설명

**fetch_add** 원자적으로 추가 하는 읽기-수정-쓰기 작업을 수행 하는 메서드 *값* 에 저장 된 값  **\*이**, 메모리 적용 됩니다. 지정 된 제약 조건을 *순서*합니다.

## <a name="fetch_and"></a> atomic:: fetch_and

연산을 수행에 저장 된 기존 값 및 값에 및  **\*이**합니다.

```cpp
Ty atomic<Ty>::fetch_and (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_and (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*<br/>
형식의 값 *Ty*합니다.

*순서*<br/>
**memory_order**.

### <a name="return-value"></a>반환 값

A *Ty* 비트의 결과 포함 하는 개체 및 합니다.

### <a name="remarks"></a>설명

**fetch_and** 의 저장된 된 값을 대체 하기는 읽기-수정-쓰기 작업을 수행 하는 메서드  **\*이** 비트와의 *값* 및 현재 에 저장 된 값  **\*이**, 지정 된 메모리 제약 조건 내에서 *순서*합니다.

## <a name="fetch_or"></a> atomic:: fetch_or

연산을 수행에 저장 된 기존 값 및 값에 또는  **\*이**합니다.

```cpp
Ty atomic<Ty>::fetch_or (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_or (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*<br/>
형식의 값 *Ty*합니다.

*순서*<br/>
**memory_order**.

### <a name="return-value"></a>반환 값

A *Ty* 비트의 결과 포함 하는 개체 또는 합니다.

### <a name="remarks"></a>설명

**fetch_or** 의 저장된 된 값을 대체 하기는 읽기-수정-쓰기 작업을 수행 하는 메서드  **\*이** 비트 또는의 *값* 및 현재 값 에 저장 된  **\*이**, 지정 된 메모리 제약 조건 내에서 *순서*합니다.

## <a name="fetch_sub"></a> atomic:: fetch_sub

지정된 값을 저장된 값에서 뺍니다.

```cpp
Ty atomic<Ty>::fetch_sub (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_sub (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*<br/>
형식의 값 *Ty*합니다.

*순서*<br/>
**memory_order**.

### <a name="return-value"></a>반환 값

A *Ty* 빼기의 결과 포함 하는 개체입니다.

### <a name="remarks"></a>설명

**fetch_sub** 원자적으로 뺄 읽기-수정-쓰기 작업을 수행 하는 메서드 *값* 에 저장된 된 값에서  **\*이**, 메모리 내에서 지정 된 제약 조건을 *순서*합니다.

## <a name="fetch_xor"></a> atomic:: fetch_xor

배타적 비트 수행에 저장 된 기존 값 및 값에 또는  **\*이**합니다.

```cpp
Ty atomic<Ty>::fetch_xor (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_xor (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*<br/>
형식의 값 *Ty*합니다.

*순서*<br/>
**memory_order**.

### <a name="return-value"></a>반환 값

A *Ty* 배타적 비트의 결과 포함 하는 개체 또는 합니다.

### <a name="remarks"></a>설명

**fetch_xor** 의 저장된 된 값을 대체 하기는 읽기-수정-쓰기 작업을 수행 하는 메서드  **\*이** 의 배타적 비트와 *값* 및 에 저장 된 현재 값  **\*이**, 지정 된 메모리 제약 조건 적용 *순서*합니다.

## <a name="is_lock_free"></a> atomic:: is_lock_free

지정 여부에 대 한 원자 단위 작업  **\*이** 잠금 무료는 합니다.

```cpp
bool is_lock_free() const volatile noexcept;
```

### <a name="return-value"></a>반환 값

에 대 한 true 이면 원자성 작업  **\*이** 는 잠금 무료, 그렇지않으면 false입니다.

### <a name="remarks"></a>설명

원자성 유형이 해당 형식에 없는 원자성 작업 잠금을 사용 하는 경우 무료 잠금입니다.

## <a name="load"></a> atomic:: load

에 저장된 된 값을 검색  **\*이**, 지정한 메모리 제약 조건 내에서.

```cpp
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const volatile noexcept;
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const noexcept;
```

### <a name="parameters"></a>매개 변수

*순서*<br/>
**memory_order**. *주문* 않아야 **memory_order_release** 또는 **memory_order_acq_rel**합니다.

### <a name="return-value"></a>반환 값

에 저장 된 검색 된 값  **\*이**합니다.

## <a name="store"></a> atomic:: store

지정된 값을 저장합니다.

```cpp
void atomic<Ty>::store(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
void atomic<Ty>::store(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*<br/>
A *Ty* 개체입니다.

*순서*<br/>
A **memory_order** 제약 조건입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 원자 단위로 저장 *값* 에 `*this`, 지정 된 메모리 제약 조건 내에서 *순서*합니다.

## <a name="see-also"></a>참고자료

[\<atomic>](../standard-library/atomic.md)<br/>
[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
