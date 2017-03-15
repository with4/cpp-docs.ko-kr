---
title: "mutex 클래스(C++ 표준 라이브러리)| Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::mutex
dev_langs:
- C++
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
caps.latest.revision: 11
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
ms.openlocfilehash: ff3e7e71c678ffc9bdead79ec56ad94f8e297a16
ms.lasthandoff: 02/24/2017

---
# <a name="mutex-class-c-standard-library"></a>mutex 클래스(C++ 표준 라이브러리)
*뮤텍스 형식*을 나타냅니다. 이 형식의 객체는 프로그램 내에서 상호 제외를 강제 수행하기 위해 사용될 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```
class mutex;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[mutex::mutex 생성자](#mutex__mutex_constructor)|`mutex` 개체를 생성합니다.|  
|[mutex::~mutex 소멸자](#mutex___dtormutex_destructor)|`mutex` 개체에서 사용하는 리소스를 모두 해제합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[mutex::lock 메서드](#mutex__lock_method)|스레드가 `mutex`의 소유권을 가져올 때까지 호출 스레드를 차단합니다.|  
|[mutex::native_handle 메서드](#mutex__native_handle_method)|뮤텍스 핸들을 나타내는 특정 구현 형식을 반환합니다.|  
|[mutex::try_lock 메서드](#mutex__try_lock_method)|차단되지 않고 `mutex`의 소유권을 가져오려고 시도합니다.|  
|[mutex::unlock 메서드](#mutex__unlock_method)|`mutex`의 소유권을 해제합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** mutex  
  
 **네임스페이스:** std  
  
##  <a name="a-namemutexlockmethoda--mutexlock-method"></a><a name="mutex__lock_method"></a>  mutex::lock 메서드  
 스레드가 `mutex`의 소유권을 가져올 때까지 호출 스레드를 차단합니다.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>설명  
 호출 스레드가 이미 `mutex`를 소유하고 있는 경우, 이 동작은 정의되지 않습니다.  
  
##  <a name="a-namemutexmutexconstructora--mutexmutex-constructor"></a><a name="mutex__mutex_constructor"></a>  mutex::mutex 생성자  
 잠기지 않은 `mutex` 개체를 생성합니다.  
  
```cpp  
constexpr mutex() noexcept;
```  
  
##  <a name="a-namemutexdtormutexdestructora--mutexmutex-destructor"></a><a name="mutex___dtormutex_destructor"></a>  mutex::~mutex 소멸자  
 `mutex` 개체에서 사용하는 리소스를 모두 해제합니다.  
  
```cpp  
~mutex();
```  
  
### <a name="remarks"></a>설명  
 소멸자가 실행될 때 개체가 잠겨 있는 경우, 이 동작은 정의되지 않습니다.  
  
##  <a name="a-namemutexnativehandlemethoda--mutexnativehandle-method"></a><a name="mutex__native_handle_method"></a>  mutex::native_handle 메서드  
 뮤텍스 핸들을 나타내는 특정 구현 형식을 반환합니다. 뮤텍스 핸들은 구현별 방식으로 사용할 수 있습니다.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>반환 값  
 `native_handle_type`은 `void *`로 캐스팅된 `Concurrency::critical_section *`으로 정의됩니다.  
  
##  <a name="a-namemutextrylockmethoda--mutextrylock-method"></a><a name="mutex__try_lock_method"></a>  mutex::try_lock 메서드  
 차단되지 않고 `mutex`의 소유권을 가져오려고 시도합니다.  
  
```cpp  
bool try_lock();
```  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공적으로 `true`의 소유권을 가져오면 `mutex`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 호출 스레드가 이미 `mutex`를 소유하고 있는 경우, 이 동작은 정의되지 않습니다.  
  
##  <a name="a-namemutexunlockmethoda--mutexunlock-method"></a><a name="mutex__unlock_method"></a>  mutex::unlock 메서드  
 `mutex`의 소유권을 해제합니다.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>설명  
 호출 스레드가 `mutex`를 소유하지 않은 경우, 이 동작은 정의되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




