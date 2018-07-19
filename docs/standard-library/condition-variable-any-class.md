---
title: condition_variable_any 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- condition_variable/std::condition_variable_any
- condition_variable/std::condition_variable_any::condition_variable_any
- condition_variable/std::condition_variable_any::notify_all
- condition_variable/std::condition_variable_any::notify_one
- condition_variable/std::condition_variable_any::wait
- condition_variable/std::condition_variable_any::wait_for
- condition_variable/std::condition_variable_any::wait_until
dev_langs:
- C++
ms.assetid: d8afe5db-1561-4ec2-8e85-21ea03ee4321
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::condition_variable_any
- std::condition_variable_any::condition_variable_any
- std::condition_variable_any::notify_all
- std::condition_variable_any::notify_one
- std::condition_variable_any::wait
- std::condition_variable_any::wait_for
- std::condition_variable_any::wait_until
ms.workload:
- cplusplus
ms.openlocfilehash: 56082c63ccc64e117d9962ff35dddc01969f403b
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959234"
---
# <a name="conditionvariableany-class"></a>condition_variable_any 클래스

`condition_variable_any` 클래스를 사용하여 모든 `mutex` 형식의 이벤트를 대기합니다.

## <a name="syntax"></a>구문

```cpp
class condition_variable_any;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[condition_variable_any](#condition_variable_any)|`condition_variable_any` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[notify_all](#notify_all)|`condition_variable_any` 개체를 대기 중인 모든 스레드를 차단 해제합니다.|
|[notify_one](#notify_one)|`condition_variable_any` 개체를 대기 중인 스레드 중 하나를 차단 해제합니다.|
|[wait](#wait)|스레드를 차단합니다.|
|[wait_for](#wait_for)|스레드를 차단하고 스레드가 차단 해제되는 시간 간격을 설정합니다.|
|[wait_until](#wait_until)|스레드를 차단하고 스레드가 차단 해제되는 최대 시점을 설정합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<condition_variable >

**네임스페이스:** std

## <a name="condition_variable_any"></a>  condition_variable_any::condition_variable_any 생성자

`condition_variable_any` 개체를 생성합니다.

```cpp
condition_variable_any();
```

### <a name="remarks"></a>설명

메모리가 부족한 경우 생성자에서 `not_enough_memory` 오류 코드가 있는 [system_error](../standard-library/system-error-class.md) 개체를 throw합니다. 몇 가지 다른 리소스를 사용할 수 없기 때문에 개체를 생성할 수 없는 경우 생성자에서 `resource_unavailable_try_again` 오류 코드가 있는 `system_error` 개체를 throw합니다.

## <a name="notify_all"></a>  condition_variable_any::notify_all

`condition_variable_any` 개체를 대기 중인 모든 스레드를 차단 해제합니다.

```cpp
void notify_all() noexcept;
```

## <a name="notify_one"></a>  condition_variable_any::notify_one

`condition_variable_any` 개체를 기다리는 스레드 중 하나를 차단 해제합니다.

```cpp
void notify_one() noexcept;
```

## <a name="wait"></a>  condition_variable_any::wait

스레드를 차단합니다.

```cpp
template <class Lock>
void wait(Lock& Lck);

template <class Lock, class Predicate>
void wait(Lock& Lck, Predicate Pred);
```

### <a name="parameters"></a>매개 변수

*Lck* 는 `mutex` 형식의 개체입니다.

*Pred* 반환 하는 식 **true** 하거나 **false**합니다.

### <a name="remarks"></a>설명

첫 번째 메서드는 `condition_variable_any` 개체에서 [notify_one](../standard-library/condition-variable-class.md#notify_one) 또는 [notify_all](../standard-library/condition-variable-class.md#notify_all)에 대한 호출을 통해 신호를 받을 때까지 차단합니다. 또한 의사적으로 대기 모드를 해제할 수도 있습니다.

두 번째 메서드는 실제로 다음 코드를 실행합니다.

```cpp
while (!Pred())
    wait(Lck);
```

## <a name="wait_for"></a>  condition_variable_any::wait_for

스레드를 차단하고 스레드가 차단 해제되는 시간 간격을 설정합니다.

```cpp
template <class Lock, class Rep, class Period>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time);

template <class Lock, class Rep, class Period, class Predicate>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time, Predicate Pred);
```

### <a name="parameters"></a>매개 변수

*Lck* 는 `mutex` 형식의 개체입니다.

*Rel_time* 는 `chrono::duration` 절전 된 시간 전에 스레드를 지정 하는 개체입니다.

*Pred* 반환 하는 식 **true** 하거나 **false**합니다.

### <a name="return-value"></a>반환 값

첫 번째 메서드는 반환 `cv_status::timeout` 대기가 종료 될 때 하는 경우 *Rel_time* 경과 합니다. 그렇지 않은 경우 메서드는 `cv_status::no_timeout`를 반환합니다.

값을 반환 하는 두 번째 방법은 *Pred*합니다.

### <a name="remarks"></a>설명

첫 번째 방법은 될 때까지 차단 합니다 `condition_variable_any` 개체를 호출 하 여 신호를 받는 [notify_one](../standard-library/condition-variable-class.md#notify_one) 또는 [notify_all](../standard-library/condition-variable-class.md#notify_all), 또는 시간 간격까지 *Rel_time* 경과 합니다. 또한 의사적으로 대기 모드를 해제할 수도 있습니다.

두 번째 메서드는 실제로 다음 코드를 실행합니다.

```cpp
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```

## <a name="wait_until"></a>  condition_variable_any::wait_until

스레드를 차단하고 스레드가 차단 해제되는 최대 시점을 설정합니다.

```cpp
template <class Lock, class Clock, class Duration>
void wait_until(Lock& Lck, const chrono::time_point<Clock, Duration>& Abs_time);

template <class Lock, class Clock, class Duration, class Predicate>
void wait_until(
    Lock& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time,
    Predicate Pred);

template <class Lock>
void wait_until(Lock Lck, const xtime* Abs_time);

template <class Lock, class Predicate>
void wait_until(
    Lock Lck,
    const xtime* Abs_time,
    Predicate Pred);
```

### <a name="parameters"></a>매개 변수

*Lck* 뮤텍스 개체입니다.

*Abs_time* A [chrono:: time_point](../standard-library/time-point-class.md) 개체입니다.

*Pred* 반환 하는 식 **true** 하거나 **false**합니다.

### <a name="return-value"></a>반환 값

반환 하는 메서드를 `cv_status` 반환 형식 `cv_status::timeout` 대기가 종료 될 때 경우 *Abs_time* 경과 합니다. 그렇지 않으면 메서드는 `cv_status::no_timeout`을 반환합니다.

반환 하는 메서드를 `bool` 의 값을 반환 *Pred*합니다.

### <a name="remarks"></a>설명

첫 번째 방법은 될 때까지 차단 합니다 `condition_variable` 개체를 호출 하 여 신호를 받는 [notify_one](../standard-library/condition-variable-class.md#notify_one) 또는 [notify_all](../standard-library/condition-variable-class.md#notify_all), 또는까지 *Abs_time*합니다. 또한 의사적으로 대기 모드를 해제할 수도 있습니다.

두 번째 메서드는 실제로 다음 코드를 실행합니다.

```cpp
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```

세 번째와 네 번째 메서드는 `xtime` 형식의 개체에 대한 포인터를 사용하여 `chrono::time_point` 개체를 대체합니다. `xtime` 개체는 신호를 기다리는 최대 시간을 지정합니다.

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[<condition_variable>](../standard-library/condition-variable.md)<br/>
