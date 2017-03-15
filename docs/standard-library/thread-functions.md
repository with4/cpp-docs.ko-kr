---
title: "&lt;thread&gt; 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb1aa1ef-fe3f-4e2c-8b6e-e22dbf2f5a19
caps.latest.revision: 12
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: de302b9a2d971b2a39d4ce775799f27dd7244a5c
ms.lasthandoff: 02/24/2017

---
# <a name="ltthreadgt-functions"></a>&lt;thread&gt; 함수
||||  
|-|-|-|  
|[get_id](#get_id_function)|[sleep_for](#sleep_for_function)|[sleep_until](#sleep_until_function)|  
|[swap](#swap_function)|[yield](#yield_function)|  
  
##  <a name="a-namegetidfunctiona--getid"></a><a name="get_id_function"></a>  get_id  
 현재 실행 스레드를 고유하게 식별합니다.  
  
```  
thread::id this_thread::get_id() noexcept;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 실행 스레드를 고유하게 식별하는 [thread::id](../standard-library/thread-class.md) 형식의 개체입니다.  
  
##  <a name="a-namesleepforfunctiona--sleepfor"></a><a name="sleep_for_function"></a>  sleep_for  
 호출 스레드를 차단합니다.  
  
```  
template <class Rep,  
class Period>  
inline void sleep_for(const chrono::duration<Rep, Period>& Rel_time);
```  
  
### <a name="parameters"></a>매개 변수  
 `Rel_time`  
 시간 간격을 지정하는 [duration](../standard-library/duration-class.md) 개체입니다.  
  
### <a name="remarks"></a>설명  
 함수는 최소한 `Rel_time`에서 지정한 시간 동안 호출 스레드를 차단합니다. 이 함수는 예외를 throw하지 않습니다.  
  
##  <a name="a-namesleepuntilfunctiona--sleepuntil"></a><a name="sleep_until_function"></a>  sleep_until  
 최소한 지정된 시간까지 호출 스레드를 차단합니다.  
  
```  
template <class Clock, class Duration>  
void sleep_until(const chrono::time_point<Clock, Duration>& Abs_time);

void sleep_until(const xtime *Abs_time);
```  
  
### <a name="parameters"></a>매개 변수  
 `Abs_time`  
 특정 시점을 나타냅니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 예외를 throw하지 않습니다.  
  
##  <a name="a-nameswapfunctiona--swap"></a><a name="swap_function"></a>  swap  
 두 `thread` 개체의 상태를 바꿉니다.  
  
```  
void swap(thread& Left, thread& Right) noexcept;  
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 왼쪽 `thread` 개체입니다.  
  
 `Right`  
 오른쪽 `thread` 개체입니다.  
  
### <a name="remarks"></a>설명  
 함수는 `Left.swap(Right)`을 호출합니다.  
  
##  <a name="a-nameyieldfunctiona--yield"></a><a name="yield_function"></a>  yield  
 정상적인 경우라면 현재 스레드가 계속 실행되더라도 운영 체제에 다른 스레드를 실행할 것을 알립니다.  
  
```  
inline void yield() noexcept;  
```  
  
## <a name="see-also"></a>참고 항목  
 [\<thread>](../standard-library/thread.md)


