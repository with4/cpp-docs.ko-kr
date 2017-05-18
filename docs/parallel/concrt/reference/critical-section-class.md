---
title: "critical_section 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 58821589a4b7596b80179a77dfd6a5772531f053
ms.contentlocale: ko-kr
ms.lasthandoff: 03/17/2017

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
|[critical_section:: scoped_lock 클래스](#critical_section__scoped_lock_class)|대 한 예외 안전 RAII 래퍼에 대 한는 `critical_section` 개체입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[critical_section](#ctor)|새 중요 섹션을 생성합니다.|  
|[~ critical_section 소멸자](#dtor)|임계 영역을 삭제합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[lock](#lock)|이 중요 섹션을 가져옵니다.|  
|[native_handle](#native_handle)|있는 경우에 플랫폼 특정 네이티브 핸들을 반환 합니다.|  
|[try_lock](#try_lock)|차단 하지 않고 잠금을 획득 하려고 시도 합니다.|  
|[try_lock_for](#try_lock_for)|특정 기간(밀리초) 동안 차단하지 않고 잠금을 가져오려고 시도합니다.|  
|[unlock](#unlock)|중요 섹션을 잠금 해제합니다.|  
  
## <a name="remarks"></a>주의  
 자세한 내용은 참조 [동기화 데이터 구조](../../../parallel/concrt/synchronization-data-structures.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `critical_section`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="ctor"></a>critical_section 

 새 중요 섹션을 생성합니다.  
  
```
critical_section();
```  
  
##  <a name="dtor"></a>~ critical_section 

 임계 영역을 삭제합니다.  
  
```
~critical_section();
```  
  
### <a name="remarks"></a>설명  
 소멸자가 실행 될 때 잠금이 더 이상 유지 될 것입니다. 여전히 유지를 소멸 잠금을 사용 하는 중요 섹션 허용 하면 정의 되지 않은 동작이 발생 합니다.  
  
##  <a name="lock"></a>잠금 

 이 중요 섹션을 가져옵니다.  
  
```
void lock();
```  
  
### <a name="remarks"></a>주의  
 더 자주 활용 하 여 안전는 [scoped_lock](#critical_section__scoped_lock_class) 구문을를 확보 및 해제는 `critical_section` 예외가 개체 안전한 방법으로 합니다.  
  
 호출 컨텍스트에 의해 잠금이 이미 유지 되는 경우는 [improper_lock](improper-lock-class.md) 예외가 throw 됩니다.  
  
##  <a name="native_handle"></a>native_handle 

 있는 경우에 플랫폼 특정 네이티브 핸들을 반환 합니다.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>반환 값  
 임계 영역에 대 한 참조입니다.  
  
### <a name="remarks"></a>주의  
 A `critical_section` 개체는 Windows 운영 체제에 플랫폼 특정 네이티브 핸들에 연관 되지 않습니다. 메서드는 단순히 개체 자체에 대 한 참조를 반환합니다.  
  
##  <a name="critical_section__scoped_lock_class"></a>critical_section:: scoped_lock 클래스  
 대 한 예외 안전 RAII 래퍼에 대 한는 `critical_section` 개체입니다.  
  
```
class scoped_lock;
```  
  
##  <a name="critical_section__scoped_lock_ctor"></a>scoped_lock::scoped_lock 

 생성 한 `scoped_lock` 개체를 가져와 `critical_section` 에 전달 된 개체는 `_Critical_section` 매개 변수입니다. 중요 섹션, 다른 스레드에 의해 저장 된 경우이 호출이 차단 됩니다.  
  
```
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Critical_section`  
 임계 영역 잠금입니다.  
  
##  <a name="critical_section__scoped_lock_dtor"></a>scoped_lock:: ~ scoped_lock 

 삭제는 `scoped_lock` 개체를 해당 생성자에서 제공 하는 중요 섹션을 해제 합니다.  
  
```
~scoped_lock();
```  
  
##  <a name="try_lock"></a>try_lock 

 차단 하지 않고 잠금을 획득 하려고 시도 합니다.  
  
```
bool try_lock();
```  
  
### <a name="return-value"></a>반환 값  
 잠금이 설정 된 경우 값 `true`고, 그렇지 않으면 값 `false`합니다.  
  
##  <a name="try_lock_for"></a>try_lock_for 

 특정 기간(밀리초) 동안 차단하지 않고 잠금을 가져오려고 시도합니다.  
  
```
bool try_lock_for(unsigned int _Timeout);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Timeout`  
 시간이 초과되기 전에 대기하는 기간(밀리초)입니다.  
  
### <a name="return-value"></a>반환 값  
 잠금이 설정 된 경우 값 `true`고, 그렇지 않으면 값 `false`합니다.  
  
##  <a name="unlock"></a>잠금 해제 

 중요 섹션을 잠금 해제합니다.  
  
```
void unlock();
```  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [reader_writer_lock 클래스](reader-writer-lock-class.md)

