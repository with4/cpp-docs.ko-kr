---
title: "CNoWorkerThread 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CNoWorkerThread
- ATL.CNoWorkerThread
- CNoWorkerThread
dev_langs:
- C++
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
caps.latest.revision: 21
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4c38d778849a31d55a657fc1022c2e9f4a370eec
ms.lasthandoff: 02/24/2017

---
# <a name="cnoworkerthread-class"></a>CNoWorkerThread 클래스
이 클래스에 대 한 인수로 사용 하는 `MonitorClass` 캐시 클래스 동적 캐시 유지 관리를 사용 하지 않도록 설정 하려는 경우에 템플릿 매개 변수입니다.  
  
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
|[CNoWorkerThread::AddHandle](#addhandle)|작동 하지 않음 방식의 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)합니다.|  
|[CNoWorkerThread::AddTimer](#addtimer)|작동 하지 않음 방식의 [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)합니다.|  
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|작동 하지 않음 방식의 [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)합니다.|  
|[CNoWorkerThread::GetThreadId](#getthreadid)|작동 하지 않음 방식의 [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)합니다.|  
|[CNoWorkerThread::Initialize](#initialize)|작동 하지 않음 방식의 [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize)합니다.|  
|[CNoWorkerThread::RemoveHandle](#removehandle)|작동 하지 않음 방식의 [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)합니다.|  
|[CNoWorkerThread::Shutdown](#shutdown)|작동 하지 않음 방식의 [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown)합니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스와 동일한 공용 인터페이스를 제공 합니다. [CWorkerThread](../../atl/reference/cworkerthread-class.md)합니다. 이 인터페이스에서 제공 해야 하는 `MonitorClass` 캐시 클래스에 템플릿 매개 변수입니다.  
  
 이 클래스의 메서드는 아무 작업도 수행 하도록 구현 됩니다. 항상 HRESULT를 반환 하는 메서드는 S_OK를 반환 하 고 항상 핸들 또는 스레드 ID를 반환 하는 메서드가 0을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlutil.h  
  
##  <a name="a-nameaddhandlea--cnoworkerthreadaddhandle"></a><a name="addhandle"></a>CNoWorkerThread::AddHandle  
 작동 하지 않음 방식의 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)합니다.  
  
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
  
### <a name="remarks"></a>주의  
 이 클래스에서 제공 하는 구현은 아무 작업도 수행 합니다.  
  
##  <a name="a-nameaddtimera--cnoworkerthreadaddtimer"></a><a name="addtimer"></a>CNoWorkerThread::AddTimer  
 작동 하지 않음 방식의 [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)합니다.  
  
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
  
### <a name="remarks"></a>주의  
 이 클래스에서 제공 하는 구현은 아무 작업도 수행 합니다.  
  
##  <a name="a-namegetthreadhandlea--cnoworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a>CNoWorkerThread::GetThreadHandle  
 작동 하지 않음 방식의 [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)합니다.  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>반환 값  
 항상 NULL을 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 클래스에서 제공 하는 구현은 아무 작업도 수행 합니다.  
  
##  <a name="a-namegetthreadida--cnoworkerthreadgetthreadid"></a><a name="getthreadid"></a>CNoWorkerThread::GetThreadId  
 작동 하지 않음 방식의 [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)합니다.  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>반환 값  
 항상 0을 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 클래스에서 제공 하는 구현은 아무 작업도 수행 합니다.  
  
##  <a name="a-nameinitializea--cnoworkerthreadinitialize"></a><a name="initialize"></a>CNoWorkerThread::Initialize  
 작동 하지 않음 방식의 [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize)합니다.  
  
```
HRESULT Initialize() throw();
```  
  
### <a name="return-value"></a>반환 값  
 항상 S_OK를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 클래스에서 제공 하는 구현은 아무 작업도 수행 합니다.  
  
##  <a name="a-nameremovehandlea--cnoworkerthreadremovehandle"></a><a name="removehandle"></a>CNoWorkerThread::RemoveHandle  
 작동 하지 않음 방식의 [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)합니다.  
  
```
HRESULT RemoveHandle(HANDLE /* hObject
 */) throw();
```  
  
### <a name="return-value"></a>반환 값  
 항상 S_OK를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 클래스에서 제공 하는 구현은 아무 작업도 수행 합니다.  
  
##  <a name="a-nameshutdowna--cnoworkerthreadshutdown"></a><a name="shutdown"></a>CNoWorkerThread::Shutdown  
 작동 하지 않음 방식의 [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown)합니다.  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="return-value"></a>반환 값  
 항상 S_OK를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 클래스에서 제공 하는 구현은 아무 작업도 수행 합니다.

