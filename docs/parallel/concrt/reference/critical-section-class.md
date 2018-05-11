---
title: critical_section 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- critical_section
- CONCRT/concurrency::critical_section
- CONCRT/concurrency::critical_section::critical_section::scoped_lock Class
- CONCRT/concurrency::critical_section::critical_section
- CONCRT/concurrency::critical_section::lock
- CONCRT/concurrency::critical_section::native_handle
- CONCRT/concurrency::critical_section::try_lock
- CONCRT/concurrency::critical_section::try_lock_for
- CONCRT/concurrency::critical_section::unlock
dev_langs:
- C++
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0287c74155e7b4fe827bb015b43cfca3384f3b1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="criticalsection-class"></a>critical_section 클래스
동시성 런타임을 명시적으로 인식하는 재진입성이 아닌 뮤텍스입니다.  
  
## <a name="syntax"></a>구문  
  
```
class critical_section;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`native_handle_type`|`critical_section` 개체에 대한 참조입니다.|  
  
### <a name="public-classes"></a>public 클래스  
  
|이름|설명|  
|----------|-----------------|  
|[critical_section:: scoped_lock 클래스](#critical_section__scoped_lock_class)|예외 안전한 RAII 래퍼에 대 한는 `critical_section` 개체입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[critical_section](#ctor)|새 임계 영역을 생성합니다.|  
|[~ critical_section 소멸자](#dtor)|임계 영역을 제거합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[lock](#lock)|이 임계 영역을 가져옵니다.|  
|[native_handle](#native_handle)|있는 경우에 플랫폼 특정 네이티브 핸들을 반환 합니다.|  
|[try_lock](#try_lock)|차단 하지 않고 잠금을 가져오려고 시도 합니다.|  
|[try_lock_for](#try_lock_for)|특정 기간(밀리초) 동안 차단하지 않고 잠금을 가져오려고 시도합니다.|  
|[unlock](#unlock)|임계 영역 잠금을 해제합니다.|  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조 [동기화 데이터 구조](../../../parallel/concrt/synchronization-data-structures.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `critical_section`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="ctor"></a> critical_section 

 새 임계 영역을 생성합니다.  
  
```
critical_section();
```  
  
##  <a name="dtor"></a> ~critical_section 

 임계 영역을 제거합니다.  
  
```
~critical_section();
```  
  
### <a name="remarks"></a>설명  
 더 이상 잠금이 소멸자가 실행 되는 경우 사용할 수 없습니다. 여전히 유지를 소멸 된 잠금으로 임계 영역 허용 하면 정의 되지 않은 동작이 발생 합니다.  
  
##  <a name="lock"></a> 잠금 

 이 임계 영역을 가져옵니다.  
  
```
void lock();
```  
  
### <a name="remarks"></a>설명  
 안전 하 게 활용 방식은 [scoped_lock](#critical_section__scoped_lock_class) 구문을를 확보 및 해제는 `critical_section` 예외가 개체 안전한 방법으로 합니다.  
  
 이미 잠금이 호출 컨텍스트에 의해 하는 경우는 [improper_lock](improper-lock-class.md) 예외가 throw 됩니다.  
  
##  <a name="native_handle"></a> native_handle 

 있는 경우에 플랫폼 특정 네이티브 핸들을 반환 합니다.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>반환 값  
 임계 영역에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 A `critical_section` 개체는 Windows 운영 체제에 대 한 플랫폼 특정 네이티브 핸들 연결 되어 있지 않습니다. 메서드는 단순히 개체 자체에 대 한 참조를 반환합니다.  
  
##  <a name="critical_section__scoped_lock_class"></a>  critical_section:: scoped_lock 클래스  
 예외 안전한 RAII 래퍼에 대 한는 `critical_section` 개체입니다.  
  
```
class scoped_lock;
```  
  
##  <a name="critical_section__scoped_lock_ctor"></a> scoped_lock::scoped_lock 

 생성 한 `scoped_lock` 개체를 가져옵니다는 `critical_section` 에 전달 된 개체는 `_Critical_section` 매개 변수입니다. 임계 영역, 다른 스레드에서 보유 하는 경우에이 호출이 차단 됩니다.  
  
```
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Critical_section`  
 임계 영역 잠금입니다.  
  
##  <a name="critical_section__scoped_lock_dtor"></a> scoped_lock::~scoped_lock 

 제거는 `scoped_lock` 개체를 해당 생성자에 제공 된 중요 한 섹션을 해제 합니다.  
  
```
~scoped_lock();
```  
  
##  <a name="try_lock"></a> try_lock 

 차단 하지 않고 잠금을 가져오려고 시도 합니다.  
  
```
bool try_lock();
```  
  
### <a name="return-value"></a>반환 값  
 잠금을 획득 하는 경우 값 `true`, 그렇지 않으면 값 `false`합니다.  
  
##  <a name="try_lock_for"></a> try_lock_for 

 특정 기간(밀리초) 동안 차단하지 않고 잠금을 가져오려고 시도합니다.  
  
```
bool try_lock_for(unsigned int _Timeout);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Timeout`  
 시간이 초과되기 전에 대기하는 기간(밀리초)입니다.  
  
### <a name="return-value"></a>반환 값  
 잠금을 획득 하는 경우 값 `true`, 그렇지 않으면 값 `false`합니다.  
  
##  <a name="unlock"></a> 잠금 해제 

 임계 영역 잠금을 해제합니다.  
  
```
void unlock();
```  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [reader_writer_lock 클래스](reader-writer-lock-class.md)
