---
title: completion_future 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- completion_future
- AMPRT/completion_future
- AMPRT/Concurrency::completion_future::completion_future
- AMPRT/Concurrency::completion_future::get
- AMPRT/Concurrency::completion_future::then
- AMPRT/Concurrency::completion_future::to_task
- AMPRT/Concurrency::completion_future::valid
- AMPRT/Concurrency::completion_future::wait
- AMPRT/Concurrency::completion_future::wait_for
- AMPRT/Concurrency::completion_future::wait_until
dev_langs:
- C++
ms.assetid: 1303c62e-546d-4b02-a578-251ed3fc0b6b
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24f7012f7fdd9aaeb2443665187aba4eef483e0f
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2018
---
# <a name="completionfuture-class"></a>completion_future 클래스
나중에 해당 하는 c + + AMP 비동기 작업을 나타냅니다.  
  
### <a name="syntax"></a>구문  
  
```  
class completion_future;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[completion_future 생성자](#ctor)|`completion_future` 클래스의 새 인스턴스를 초기화합니다.|  
|[~ completion_future 소멸자](#dtor)|소멸 된 `completion_future` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[get](#get)|연결 된 비동기 작업이 완료 될 때까지 기다립니다.|  
|[then](#then)|연결에 콜백 함수 개체는 `completion_future` 연결 된 비동기 작업 실행이 끝날 때 실행 될 개체입니다.|  
|[to_task](#to_task)|반환 된 `task` 연결 된 비동기 작업에 해당 하는 개체입니다.|  
|[valid](#valid)|개체가 비동기 작업에 연결 되었는지 여부를 나타내는 부울 값을 가져옵니다.|  
|[wait](#wait)|연결 된 비동기 작업이 완료 될 때까지 차단 됩니다.|  
|[wait_for](#wait_for)|연결 된 비동기 작업이 완료 될 때까지 차단 또는 지정 된 시간 `_Rel_time` 경과 합니다.|  
|[wait_until](#wait_until)|현재 시간에서 지정한 값을 초과할 때까지 또는 연결 된 비동기 작업이 완료 될 때까지 차단 `_Abs_time`합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator std::shared_future\<void>](#operator_shared_future)|암시적으로 변환 된 `completion_future` 개체는 `std::shared_future` 개체입니다.|  
|[operator=](#operator_eq)|지정 된의 내용을 복사 `completion_future` 을 여기에 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `completion_future`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** 동시성  


## <a name="ctor"></a> completion_future 

`completion_future` 클래스의 새 인스턴스를 초기화합니다.  
  
### <a name="syntax"></a>구문  
  
```  
completion_future();  
  
completion_future(  
    const completion_future& _Other );  
  
completion_future(  
    completion_future&& _Other );  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 복사하거나 이동시킬 `completion_future` 개체입니다.  
  
### <a name="overloads-list"></a>오버 로드 목록  
  
|이름|설명|  
|----------|-----------------|  
|`completion_future();`|`completion_future` 클래스의 새 인스턴스를 초기화합니다.|  
|`completion_future(const completion_future& _Other);`|생성자를 복사하여 `completion_future` 클래스의 새 인스턴스를 초기화합니다.|  
|`completion_future(completion_future&& _Other);`|생성자를 이동시켜 `completion_future` 클래스의 새 인스턴스를 초기화합니다.|  
  
## <a name="get"></a> 가져오기 

연결 된 비동기 작업이 완료 될 때까지 기다립니다. 비동기 작업 중 하나가 발생한 경우 저장된 예외를 throw합니다.  
  
### <a name="syntax"></a>구문  
  
```  
void get() const;  
```  
  
## <a name="operator_shared_future"></a> 연산자 std::shared_future<void> 

암시적으로 변환 된 `completion_future` 개체는 `std::shared_future` 개체입니다.  
  
### <a name="syntax"></a>구문  
  
```  
operator std::shared_future<void>() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `std::shared_future` 개체입니다.  
  
## <a name="operator_eq"></a> operator= 

지정 된의 내용을 복사 `completion_future` 을 여기에 개체입니다.  
  
### <a name="syntax"></a>구문  
  
```  
completion_future&  operator= (const completion_future& _Other );    
completion_future&  operator= (completion_future&& _Other );  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Other`  
 복사할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이에 대 한 참조 `completion_future` 개체입니다.  
  
## <a name="overloads-list"></a>오버 로드 목록  
  
|이름|설명|  
|----------|-----------------|  
|`completion_future& operator=(const completion_future& _Other);`|전체 복사본을 사용하여 지정된 `completion_future` 개체의 내용을 여기로 복사합니다.|  
|`completion_future& operator=(completion_future&& _Other);`|이동 할당을 사용하여 지정된 `completion_future` 개체의 내용을 여기로 복사합니다.|  
  
## <a name="then"></a> 그런 다음 

연결에 콜백 함수 개체는 `completion_future` 연결 된 비동기 작업 실행이 끝날 때 실행 될 개체입니다.  
  
### <a name="syntax"></a>구문  
  
```  
template <typename _Functor>  
void then(const _Functor & _Func ) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Functor`  
 콜백 구조 함수입니다.  
  
 `_Func`  
 콜백 함수 개체입니다.  
  
## <a name="to_task"></a> to_task 

반환 된 `task` 연결 된 비동기 작업에 해당 하는 개체입니다.  
  
### <a name="syntax"></a>구문  
  
```  
concurrency::task<void> to_task() const;  
```  
  
### <a name="return-value"></a>반환 값  
 연결된 비동기 작업에 해당하는 `task` 개체입니다.  
  
## <a name="valid"></a> 유효한 

개체가 비동기 작업에 연결되어 있는지 여부를 나타내는 부울 값을 가져옵니다.  
  
### <a name="syntax"></a>구문  
  
```  
bool valid() const;  
```  
  
### <a name="return-value"></a>반환 값  
 개체가 비동기 작업에 연결되어 있으면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## <a name="wait"></a> 대기 

연결 된 비동기 작업이 완료 될 때까지 차단 됩니다.  
  
### <a name="syntax"></a>구문  
  
```  
void wait() const;  
```  
  
## <a name="wait_for"></a> wait_for 

연결 된 비동기 작업이 완료 될 때까지 차단 또는 지정 된 시간 `_Rel_time` 경과 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
template <  
    class _Rep,  
    class _Period  
>  
std::future_status::future_status wait_for(  
    const std::chrono::duration< _Rep, _Period>& _Rel_time ) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Rep`  
 틱 수를 나타내는 산술 형식입니다.  
  
 `_Period`  
 틱 당 경과 하는 시간 (초) 수를 나타내는 std::ratio 합니다.  
  
 `_Rel_time`  
 최대 양을 작업이 완료 될 때까지 기다리는 시간입니다.  
  
### <a name="return-value"></a>반환 값  
 반환합니다.  
  
-   `std::future_status::deferred` 연결 된 비동기 작업을 실행 하지 않으면 합니다.  
  
-   `std::future_status::ready` 경우 연결 된 비동기 작업 완료 됩니다.  
  
-   `std::future_status::timeout` 지정 된 시간 동안 경과 되었습니다 하는 경우.  
  
## <a name="wait_until"></a> wait_until 

현재 시간에서 지정한 값을 초과할 때까지 또는 연결 된 비동기 작업이 완료 될 때까지 차단 `_Abs_time`합니다.  
  
### <a name="syntax"></a>구문  
  
```  
template <  
    class _Clock,  
    class _Duration  
>  
std::future_status::future_status wait_until(  
    const std::chrono::time_point< _Clock, _Duration>& _Abs_time ) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Clock`  
 이 시점 측정 되는 클록입니다.  
  
 `_Duration`  
 시간 간격의 시작 된 이후 `_Clock`의 epoch, 지나면 함수는 시간이 초과 됩니다.  
  
 `_Abs_time`  
 지정 시간 제한 시간이 되기 함수입니다.  
  
### <a name="return-value"></a>반환 값  
 반환합니다.  
  
1.  `std::future_status::deferred` 연결 된 비동기 작업을 실행 하지 않으면 합니다.  
  
2.  `std::future_status::ready` 경우 연결 된 비동기 작업 완료 됩니다.  
  
3.  `std::future_status::timeout` 지정 된 시간 동안 경과 되었습니다.  
  
## <a name="dtor"></a> ~completion_future 

소멸 된 `completion_future` 개체입니다.  
  
### <a name="syntax"></a>구문  
  
```  
~completion_future();  
```  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
