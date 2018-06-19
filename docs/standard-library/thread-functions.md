---
title: '&lt;thread&gt; 함수 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- thread/std::get_id
- thread/std::sleep_for
- thread/std::sleep_until
- thread/std::swap
- thread/std::yield
ms.assetid: bb1aa1ef-fe3f-4e2c-8b6e-e22dbf2f5a19
helpviewer_keywords:
- std::get_id [C++]
- std::sleep_for [C++]
- std::sleep_until [C++]
- std::swap [C++]
- std::yield [C++]
ms.openlocfilehash: f151bbaf692d914fa1072021e2f14262b2c72ce4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855905"
---
# <a name="ltthreadgt-functions"></a>&lt;thread&gt; 함수

||||
|-|-|-|
|[get_id](#get_id)|[sleep_for](#sleep_for)|[sleep_until](#sleep_until)|
|[swap](#swap)|[yield](#yield)|

## <a name="get_id"></a>  get_id

현재 실행 스레드를 고유하게 식별합니다.

```cpp
thread::id this_thread::get_id() noexcept;
```

### <a name="return-value"></a>반환 값

현재 실행 스레드를 고유하게 식별하는 [thread::id](../standard-library/thread-class.md) 형식의 개체입니다.

## <a name="sleep_for"></a>  sleep_for

호출 스레드를 차단합니다.

```cpp
template <class Rep,
class Period>
inline void sleep_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>매개 변수

`Rel_time` A [기간](../standard-library/duration-class.md) 시간 간격을 지정 하는 개체입니다.

### <a name="remarks"></a>설명

함수는 최소한 `Rel_time`에서 지정한 시간 동안 호출 스레드를 차단합니다. 이 함수는 예외를 throw하지 않습니다.

## <a name="sleep_until"></a>  sleep_until

최소한 지정된 시간까지 호출 스레드를 차단합니다.

```cpp
template <class Clock, class Duration>
void sleep_until(const chrono::time_point<Clock, Duration>& Abs_time);

void sleep_until(const xtime *Abs_time);
```

### <a name="parameters"></a>매개 변수

`Abs_time` 에 시각을 나타냅니다.

### <a name="remarks"></a>설명

이 함수는 예외를 throw하지 않습니다.

## <a name="swap"></a>  swap

두 `thread` 개체의 상태를 바꿉니다.

```cpp
void swap(thread& Left, thread& Right) noexcept;
```

### <a name="parameters"></a>매개 변수

`Left` 왼쪽 `thread` 개체입니다.

`Right` 오른쪽 `thread` 개체입니다.

### <a name="remarks"></a>설명

함수는 `Left.swap(Right)`을 호출합니다.

## <a name="yield"></a>  yield

정상적인 경우라면 현재 스레드가 계속 실행되더라도 운영 체제에 다른 스레드를 실행할 것을 알립니다.

```cpp
inline void yield() noexcept;
```

## <a name="see-also"></a>참고자료

[\<thread>](../standard-library/thread.md)<br/>
