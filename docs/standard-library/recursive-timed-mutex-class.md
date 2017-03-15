---
title: "recursive_timed_mutex 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::recursive_timed_mutex
dev_langs:
- C++
ms.assetid: 59cc2d5c-ed80-45f3-a0a8-05652a8ead7e
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: a28e9521455f0380f412fc2aa81aecd713f9535a
ms.lasthandoff: 02/24/2017

---
# <a name="recursivetimedmutex-class"></a>recursive_timed_mutex 클래스
*시간이 지정된 뮤텍스 형식*을 나타냅니다. 이러한 형식의 개체를 사용하면 프로그램 내에서 시간이 제한된 차단을 사용하여 상호 배제를 강제로 수행할 수 있습니다. [timed_mutex](../standard-library/timed-mutex-class.md) 형식의 개체와 달리 `recursive_timed_mutex` 개체에 대한 잠금 메서드 호출의 효과는 적절하게 정의됩니다.  
  
## <a name="syntax"></a>구문  
  
```
class recursive_timed_mutex;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[recursive_timed_mutex 생성자](#recursive_timed_mutex__recursive_timed_mutex_constructor)|잠기지 않은 `recursive_timed_mutex` 개체를 생성합니다.|  
|[~recursive_timed_mutex 소멸자](#recursive_timed_mutex___dtorrecursive_timed_mutex_destructor)|`recursive_timed_mutex` 개체에서 사용하는 리소스를 모두 해제합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[lock](#recursive_timed_mutex__lock_method)|스레드가 `mutex`의 소유권을 가져올 때까지 호출 스레드를 차단합니다.|  
|[try_lock](#recursive_timed_mutex__try_lock_method)|차단되지 않고 `mutex`의 소유권을 가져오려고 시도합니다.|  
|[try_lock_for](#recursive_timed_mutex__try_lock_for_method)|지정된 시간 간격으로 `mutex`의 소유권 가져오기를 시도합니다.|  
|[try_lock_until](#recursive_timed_mutex__try_lock_until_method)|지정된 시간까지 `mutex`의 소유권 가져오기를 시도합니다.|  
|[unlock](#recursive_timed_mutex__unlock_method)|`mutex`의 소유권을 해제합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** mutex  
  
 **네임스페이스:** std  
  
##  <a name="a-namerecursivetimedmutexlockmethoda--lock"></a><a name="recursive_timed_mutex__lock_method"></a>  lock  
 스레드가 `mutex`의 소유권을 가져올 때까지 호출 스레드를 차단합니다.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>설명  
 호출 스레드가 `mutex`를 이미 소유하고 있으면 메서드는 결과를 즉시 반환하며 이전 잠금은 적용된 상태로 유지됩니다.  
  
##  <a name="a-namerecursivetimedmutexrecursivetimedmutexconstructora--recursivetimedmutex-constructor"></a><a name="recursive_timed_mutex__recursive_timed_mutex_constructor"></a>  recursive_timed_mutex 생성자  
 잠기지 않은 `recursive_timed_mutex` 개체를 생성합니다.  
  
```cpp  
recursive_timed_mutex();
```  
  
##  <a name="a-namerecursivetimedmutexdtorrecursivetimedmutexdestructora--recursivetimedmutex-destructor"></a><a name="recursive_timed_mutex___dtorrecursive_timed_mutex_destructor"></a>  ~recursive_timed_mutex 소멸자  
 `recursive_timed_mutex` 개체에서 사용하는 리소스를 모두 해제합니다.  
  
```cpp  
~recursive_timed_mutex();
```  
  
### <a name="remarks"></a>설명  
 소멸자가 실행될 때 개체가 잠겨 있는 경우, 이 동작은 정의되지 않습니다.  
  
##  <a name="a-namerecursivetimedmutextrylockmethoda--trylock"></a><a name="recursive_timed_mutex__try_lock_method"></a>  try_lock  
 차단되지 않고 `mutex`의 소유권을 가져오려고 시도합니다.  
  
```cpp  
bool try_lock() noexcept;
```  
  
### <a name="return-value"></a>반환 값  
 메서드가 `mutex`의 소유권을 정상적으로 가져오거나 호출 스레드가 `mutex`를 이미 소유하고 있으면 `true`이고 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 호출 스레드가 `mutex`를 이미 소유하고 있으면 함수는 `true`를 즉시 반환하며 이전 잠금은 적용된 상태로 유지됩니다.  
  
##  <a name="a-namerecursivetimedmutextrylockformethoda--trylockfor"></a><a name="recursive_timed_mutex__try_lock_for_method"></a>  try_lock_for  
 차단되지 않고 `mutex`의 소유권을 가져오려고 시도합니다.  
  
```cpp  
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```  
  
### <a name="parameters"></a>매개 변수  
 `Rel_time`  
 메서드가 `mutex`의 소유권을 가져오려고 시도하는 최대 시간을 지정하는 [chrono::duration](../standard-library/duration-class.md) 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 `mutex`의 소유권을 정상적으로 가져오거나 호출 스레드가 `mutex`를 이미 소유하고 있으면 `true`이고 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 호출 스레드가 `mutex`를 이미 소유하고 있으면 메서드는 `true`를 즉시 반환하며 이전 잠금은 적용된 상태로 유지됩니다.  
  
##  <a name="a-namerecursivetimedmutextrylockuntilmethoda--trylockuntil"></a><a name="recursive_timed_mutex__try_lock_until_method"></a>  try_lock_until  
 차단되지 않고 `mutex`의 소유권을 가져오려고 시도합니다.  
  
```cpp  
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```  
  
### <a name="parameters"></a>매개 변수  
 `Abs_time`  
 임계값을 지정하는 특정 시점으로, 이 시간 경과 후에는 메서드가 더 이상 `mutex`의 소유권을 가져오려고 시도하지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 `mutex`의 소유권을 정상적으로 가져오거나 호출 스레드가 `mutex`를 이미 소유하고 있으면 `true`이고 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 호출 스레드가 `mutex`를 이미 소유하고 있으면 메서드는 `true`를 즉시 반환하며 이전 잠금은 적용된 상태로 유지됩니다.  
  
##  <a name="a-namerecursivetimedmutexunlockmethoda--unlock"></a><a name="recursive_timed_mutex__unlock_method"></a>  unlock  
 `mutex`의 소유권을 해제합니다.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 `recursive_timed_mutex` 개체에 대해 [lock](#recursive_timed_mutex__lock_method), [try_lock](#recursive_timed_mutex__try_lock_method), [try_lock_for](#recursive_timed_mutex__try_lock_for_method) 및 [try_lock_until](#recursive_timed_mutex__try_lock_until_method)이 정상적으로 호출된 횟수만큼 호출된 후에만 `mutex`의 소유권을 해제합니다.  
  
 호출 스레드가 `mutex`를 소유하지 않은 경우, 이 동작은 정의되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




