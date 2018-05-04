---
title: CNoWorkerThread 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread::AddHandle
- ATLUTIL/ATL::CNoWorkerThread::AddTimer
- ATLUTIL/ATL::CNoWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CNoWorkerThread::GetThreadId
- ATLUTIL/ATL::CNoWorkerThread::Initialize
- ATLUTIL/ATL::CNoWorkerThread::RemoveHandle
- ATLUTIL/ATL::CNoWorkerThread::Shutdown
dev_langs:
- C++
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85e1962d10f274f4f8c35ba27cb05c41e8bf19cb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="cnoworkerthread-class"></a>CNoWorkerThread 클래스
이 클래스를 사용 하 여에 대 한 인수로 `MonitorClass` 동적 캐시 유지 관리를 사용 하지 않도록 설정 하려는 경우 캐시 클래스에 템플릿 매개 변수입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CNoWorkerThread
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CNoWorkerThread::AddHandle](#addhandle)|기능 이외에 해당 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)합니다.|  
|[CNoWorkerThread::AddTimer](#addtimer)|기능 이외에 해당 [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)합니다.|  
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|기능 이외에 해당 [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)합니다.|  
|[CNoWorkerThread::GetThreadId](#getthreadid)|기능 이외에 해당 [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)합니다.|  
|[CNoWorkerThread::Initialize](#initialize)|기능 이외에 해당 [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize)합니다.|  
|[CNoWorkerThread::RemoveHandle](#removehandle)|기능 이외에 해당 [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)합니다.|  
|[CNoWorkerThread::Shutdown](#shutdown)|기능 이외에 해당 [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown)합니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스와 동일한 공용 인터페이스는 제공 [CWorkerThread](../../atl/reference/cworkerthread-class.md)합니다. 이 인터페이스에서 제공 해야 하는 `MonitorClass` 캐시 클래스에 템플릿 매개 변수입니다.  
  
 이 클래스의 메서드는 아무 작업도 수행 하도록 구현 됩니다. HRESULT 값을 항상 반환 하는 메서드는 S_OK를 반환 하 고 항상 핸들 또는 스레드 ID를 반환 하는 메서드가 0을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlutil.h  
  
##  <a name="addhandle"></a>  CNoWorkerThread::AddHandle  
 기능 이외에 해당 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)합니다.  
  
```
HRESULT AddHandle(HANDLE /* hObject
 */,
    IWorkerThreadClient* /* pClient
 */,
    DWORD_PTR /* dwParam
 */) throw();
```  
  
### <a name="return-value"></a>반환 값  
 항상 S_OK를 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 클래스에서 제공 하는 구현을 아무 작업도 수행 합니다.  
  
##  <a name="addtimer"></a>  CNoWorkerThread::AddTimer  
 기능 이외에 해당 [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)합니다.  
  
```
HRESULT AddTimer(DWORD /* dwInterval
 */,
    IWorkerThreadClient* /* pClient
 */,
    DWORD_PTR /* dwParam
 */,
    HANDLE* /* phTimer
 */) throw();
```  
  
### <a name="return-value"></a>반환 값  
 항상 S_OK를 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 클래스에서 제공 하는 구현을 아무 작업도 수행 합니다.  
  
##  <a name="getthreadhandle"></a>  CNoWorkerThread::GetThreadHandle  
 기능 이외에 해당 [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)합니다.  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>반환 값  
 항상 NULL을 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 클래스에서 제공 하는 구현을 아무 작업도 수행 합니다.  
  
##  <a name="getthreadid"></a>  CNoWorkerThread::GetThreadId  
 기능 이외에 해당 [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)합니다.  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>반환 값  
 항상 0을 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 클래스에서 제공 하는 구현을 아무 작업도 수행 합니다.  
  
##  <a name="initialize"></a>  CNoWorkerThread::Initialize  
 기능 이외에 해당 [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize)합니다.  
  
```
HRESULT Initialize() throw();
```  
  
### <a name="return-value"></a>반환 값  
 항상 S_OK를 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 클래스에서 제공 하는 구현을 아무 작업도 수행 합니다.  
  
##  <a name="removehandle"></a>  CNoWorkerThread::RemoveHandle  
 기능 이외에 해당 [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)합니다.  
  
```
HRESULT RemoveHandle(HANDLE /* hObject
 */) throw();
```  
  
### <a name="return-value"></a>반환 값  
 항상 S_OK를 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 클래스에서 제공 하는 구현을 아무 작업도 수행 합니다.  
  
##  <a name="shutdown"></a>  CNoWorkerThread::Shutdown  
 기능 이외에 해당 [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown)합니다.  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="return-value"></a>반환 값  
 항상 S_OK를 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 클래스에서 제공 하는 구현을 아무 작업도 수행 합니다.
