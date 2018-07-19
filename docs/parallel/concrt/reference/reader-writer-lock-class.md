---
title: reader_writer_lock 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- reader_writer_lock
- CONCRT/concurrency::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock_read
- CONCRT/concurrency::reader_writer_lock::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::lock
- CONCRT/concurrency::reader_writer_lock::lock_read
- CONCRT/concurrency::reader_writer_lock::try_lock
- CONCRT/concurrency::reader_writer_lock::try_lock_read
- CONCRT/concurrency::reader_writer_lock::unlock
dev_langs:
- C++
helpviewer_keywords:
- reader_writer_lock class
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a2f48a80efca0ec6e85a315b355a6482fb2096b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692271"
---
# <a name="readerwriterlock-class"></a>reader_writer_lock 클래스
로컬 전용 회전을 사용한 작성기 우선 큐 기반 읽기/쓰기 잠금입니다. 잠금은 작성기에 대해 FIFO(선입 선출) 액세스 권한을 부여하며 작성기의 연속 부하 상태에서는 판독기에 제공되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```
class reader_writer_lock;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-classes"></a>public 클래스  
  
|이름|설명|  
|----------|-----------------|  
|[reader_writer_lock:: scoped_lock 클래스](#scoped_lock_class)|얻는 데 사용할 수 있는 예외 안전한 RAII 래퍼입니다 `reader_writer_lock` 작성기로 개체를 잠급니다.|  
|[reader_writer_lock:: scoped_lock_read 클래스](#scoped_lock_read_class)|얻는 데 사용할 수 있는 예외 안전한 RAII 래퍼입니다 `reader_writer_lock` 판독기로 개체를 잠급니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[reader_writer_lock](#ctor)|새 `reader_writer_lock` 개체를 생성합니다.|  
|[~ reader_writer_lock 소멸자](#dtor)|소멸 된 `reader_writer_lock` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[lock](#lock)|작성기로 판독기 / 작성기 잠금을 가져옵니다.|  
|[lock_read](#lock_read)|판독기로 판독기 / 작성기 잠금을 가져옵니다. 기록기가 있는 경우 활성 판독기에는 수행 될 때까지 대기 하는 합니다. 판독기는 단순히 잠금에 관심을 등록 하 고 작성기가 해제 될 때까지 대기 합니다.|  
|[try_lock](#try_lock)|차단 하지 않고 작성기로 판독기 및 작성기 잠금을 가져오려고 시도 합니다.|  
|[try_lock_read](#try_lock_read)|차단 하지 않고 판독기로 판독기 및 작성기 잠금을 획득 하려고 시도 합니다.|  
|[unlock](#unlock)|판독기 또는 작성기를 잠근 사용자에 따라 판독기 및 작성기 잠금을 잠금 해제 합니다.|  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조 [동기화 데이터 구조](../../../parallel/concrt/synchronization-data-structures.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `reader_writer_lock`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="lock"></a> 잠금 

 작성기로 판독기 / 작성기 잠금을 가져옵니다.  
  
```
void lock();
```  
  
### <a name="remarks"></a>설명  
 안전 하 게 활용 방식은 [scoped_lock](#scoped_lock_class) 구문을를 확보 및 해제는 `reader_writer_lock` 예외가 작성기로 개체 안전한 방법으로 합니다.  
  
 작성기가 잠금을 가져오려고 시도하면 이후 판독기는 작성기가 잠금을 성공적으로 가져와 해제할 때까지 차단됩니다. 이 잠금은 작성기 중심 및 작성기의 연속 부하 상태에서 판독기를 사용할 수 없게 합니다.  
  
 작성기는 잠금을 종료 다음 작성기의에서 해제 되도록 연결 됩니다.  
  
 이미 잠금이 호출 컨텍스트에 의해 하는 경우는 [improper_lock](improper-lock-class.md) 예외가 throw 됩니다.  
  
##  <a name="lock_read"></a> lock_read 

 판독기로 판독기 / 작성기 잠금을 가져옵니다. 기록기가 있는 경우 활성 판독기에는 수행 될 때까지 대기 하는 합니다. 판독기는 단순히 잠금에 관심을 등록 하 고 작성기가 해제 될 때까지 대기 합니다.  
  
```
void lock_read();
```  
  
### <a name="remarks"></a>설명  
 안전 하 게 활용 방식은 [scoped_lock_read](#scoped_lock_read_class) 구문을를 확보 및 해제는 `reader_writer_lock` 개체에서 예외를 판독기로 안전한 방법으로 합니다.  
  
 작성기 잠금을 기다리는 경우 판독기는 줄에 있는 모든 기록기가 획득 되 고 잠금을 해제할 때까지 대기 합니다. 이 잠금은 작성기 중심 및 작성기의 연속 부하 상태에서 판독기를 사용할 수 없게 합니다.  
  
##  <a name="ctor"></a> reader_writer_lock 

 새 `reader_writer_lock` 개체를 생성합니다.  
  
```
reader_writer_lock();
```  
  
##  <a name="dtor"></a> ~reader_writer_lock 

 소멸 된 `reader_writer_lock` 개체입니다.  
  
```
~reader_writer_lock();
```  
  
### <a name="remarks"></a>설명  
 더 이상 잠금이 소멸자가 실행 되는 경우 사용할 수 없습니다. 여전히 유지를 소멸 된 잠금으로 판독기 작성기 잠금을 허용 하면 정의 되지 않은 동작이 발생 합니다.  
  
##  <a name="scoped_lock_class"></a>  reader_writer_lock:: scoped_lock 클래스  
 얻는 데 사용할 수 있는 예외 안전한 RAII 래퍼입니다 `reader_writer_lock` 작성기로 개체를 잠급니다.  
  
```
class scoped_lock;
``` 
## <a name="scoped_lock_ctor"></a> scoped_lock::scoped_lock 

생성 한 `scoped_lock` 개체를 가져옵니다는 `reader_writer_lock` 에 전달 된 개체는 `_Reader_writer_lock` 작성기로 매개 변수입니다. 다른 스레드에 의해 잠금이이 호출이 차단 됩니다.  
  
  
```
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>매개 변수  
 `_Reader_writer_lock`  
 `reader_writer_lock` 작성기로 가져올 개체입니다.  
  
## <a name="scoped_lock_dtor"></a> scoped_lock::~scoped_lock 

제거는 `reader_writer_lock` 개체를 해당 생성자에 제공 된 잠금을 해제 합니다.   

```
~scoped_lock();
```  
  
##  <a name="scoped_lock_read_class"></a>  reader_writer_lock:: scoped_lock_read 클래스  
 얻는 데 사용할 수 있는 예외 안전한 RAII 래퍼입니다 `reader_writer_lock` 판독기로 개체를 잠급니다.  
  
```
class scoped_lock_read;
```  
  
##  <a name="try_lock"></a> try_lock 

 차단 하지 않고 작성기로 판독기 및 작성기 잠금을 가져오려고 시도 합니다.  

## <a name="scoped_lock_read_ctor"></a> scoped_lock_read::scoped_lock_read 

생성 한 `scoped_lock_read` 개체를 가져옵니다는 `reader_writer_lock` 에 전달 된 개체는 `_Reader_writer_lock` 판독기로 매개 변수입니다. 보류 중인 작성기 잠금을 보유 하 고 다른 스레드가 작성기로,이 호출은 차단 됩니다.  
  
```
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>매개 변수  
 `_Reader_writer_lock`  
 `reader_writer_lock` 판독기로 가져올 개체입니다.  
  
## <a name="a-namescopedlockreaddtor--readerwriterlockscopedlockreadscopedlockread-destructor"></a><a name="scoped_lock_read_dtor">  reader_writer_lock:: scoped_lock_read:: ~ scoped_lock_read 소멸자
제거는 `scoped_lock_read` 개체를 해당 생성자에 제공 된 잠금을 해제 합니다.  

```
~scoped_lock_read();
```  
  
## <a name="try_lock"></a> try_lock 

```
bool try_lock();
```  
  
### <a name="return-value"></a>반환 값  
 잠금을 획득 하는 경우 값 `true`, 그렇지 않으면 값 `false`합니다.  
  
##  <a name="try_lock_read"></a> try_lock_read 

 차단 하지 않고 판독기로 판독기 및 작성기 잠금을 획득 하려고 시도 합니다.  
  
```
bool try_lock_read();
```  
  
### <a name="return-value"></a>반환 값  
 잠금을 획득 하는 경우 값 `true`, 그렇지 않으면 값 `false`합니다.  
  
##  <a name="unlock"></a> 잠금 해제 

 판독기 또는 작성기를 잠근 사용자에 따라 판독기 및 작성기 잠금을 잠금 해제 합니다.  
  
```
void unlock();
```  
  
### <a name="remarks"></a>설명  
 작성기 잠금을 기다리는 경우 잠금 해제 항상 FIFO 순서에 따라 다음 작성기로 전환 됩니다. 이 잠금은 작성기 중심 및 작성기의 연속 부하 상태에서 판독기를 사용할 수 없게 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [critical_section 클래스](critical-section-class.md)
