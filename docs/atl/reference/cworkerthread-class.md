---
title: "CWorkerThread 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWorkerThread
- ATLUTIL/ATL::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::AddHandle
- ATLUTIL/ATL::CWorkerThread::AddTimer
- ATLUTIL/ATL::CWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CWorkerThread::GetThreadId
- ATLUTIL/ATL::CWorkerThread::Initialize
- ATLUTIL/ATL::CWorkerThread::RemoveHandle
- ATLUTIL/ATL::CWorkerThread::Shutdown
dev_langs:
- C++
helpviewer_keywords:
- CWorkerThread class
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: be7a000e48cb044a67f7eee120206f46ecaef2ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cworkerthread-class"></a>CWorkerThread 클래스
이 클래스에서 작업자 스레드 또는 기존을 사용 하 여, 하나 이상의 커널 개체 핸들을 대기 만들고 핸들 중 하나에 신호가 전달 될 때 지정 된 클라이언트 함수를 실행 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class ThreadTraits = DefaultThreadTraits>  
class CWorkerThread
```  
  
#### <a name="parameters"></a>매개 변수  
 `ThreadTraits`  
 와 같은 스레드 만들기 함수를 제공 하는 클래스 [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) 또는 [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="protected-structures"></a>Protected 구조체  
  
|name|설명|  
|----------|-----------------|  
|`WorkerClientEntry`||  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CWorkerThread::CWorkerThread](#cworkerthread)|작업자 스레드에 대 한 생성자입니다.|  
|[CWorkerThread:: ~ CWorkerThread](#dtor)|작업자 스레드에 대 한 소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CWorkerThread::AddHandle](#addhandle)|작업자 스레드에 의해 관리 되는 목록에 있는 대기 가능 개체의 핸들을 추가 하려면이 메서드를 호출 합니다.|  
|[CWorkerThread::AddTimer](#addtimer)|작업자 스레드에 의해 관리 되는 목록에는 정기 대기 타이머를 추가 하려면이 메서드를 호출 합니다.|  
|[CWorkerThread::GetThreadHandle](#getthreadhandle)|작업자 스레드의 스레드 핸들을 가져오려면이 메서드를 호출 합니다.|  
|[CWorkerThread::GetThreadId](#getthreadid)|작업자 스레드의 스레드 ID를 가져오려면이 메서드를 호출 합니다.|  
|[CWorkerThread::Initialize](#initialize)|작업자 스레드를 초기화 하려면이 메서드를 호출 합니다.|  
|[CWorkerThread::RemoveHandle](#removehandle)|핸들을 대기 가능 개체의 목록에서 제거 하려면이 메서드를 호출 합니다.|  
|[CWorkerThread::Shutdown](#shutdown)|작업자 스레드를 종료 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>설명  
  
### <a name="to-use-cworkerthread"></a>CWorkerThread 사용 하려면  
  
1.  이 클래스의 인스턴스를 만듭니다.  
  
2.  호출 [CWorkerThread::Initialize](#initialize)합니다.  
  
3.  호출 [CWorkerThread::AddHandle](#addhandle) 커널 개체와의 구현에 대 한 핸들로 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)합니다.  
  
     - 또는  
  
     호출 [CWorkerThread::AddTimer](#addtimer) 의 구현에 대 한 포인터와 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)합니다.  
  
4.  구현 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) 핸들 또는 타이머 신호를 받는 경우 몇 가지 작업을 수행할 합니다.  
  
5.  대기 가능 개체의 목록에서 개체를 제거 하려면 호출 [CWorkerThread::RemoveHandle](#removehandle)합니다.  
  
6.  스레드를 종료 하려면 호출 [CWorkerThread::Shutdown](#shutdown)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlutil.h  
  
##  <a name="addhandle"></a>CWorkerThread::AddHandle  
 작업자 스레드에 의해 관리 되는 목록에 있는 대기 가능 개체의 핸들을 추가 하려면이 메서드를 호출 합니다.  
  
```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `hObject`  
 대기 가능 개체에 대 한 핸들입니다.  
  
 `pClient`  
 에 대 한 포인터는 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) 는 핸들이 신호를 받을 때 호출 될 개체의 인터페이스입니다.  
  
 `dwParam`  
 매개 변수에 전달 될 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) 핸들이 신호를 받는 경우입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) 를 통해 호출할 수 `pClient` 때 핸들에 `hObject`, 신호를 받는 합니다.  
  
##  <a name="addtimer"></a>CWorkerThread::AddTimer  
 작업자 스레드에 의해 관리 되는 목록에는 정기 대기 타이머를 추가 하려면이 메서드를 호출 합니다.  
  
```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *dwInterval*  
 타이머의 기간을 밀리초 단위로 지정 합니다.  
  
 `pClient`  
 에 대 한 포인터는 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) 는 핸들이 신호를 받을 때 호출 될 개체의 인터페이스입니다.  
  
 `dwParam`  
 매개 변수에 전달 될 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) 핸들이 신호를 받는 경우입니다.  
  
 `phTimer`  
 [out] 성공할 경우 새로 만든된 타이머에 대 한 핸들을 수신 하는 핸들 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) 를 통해 호출할 수 `pClient` 타이머 신호를 보낼 때.  
  
 타이머 핸들을 전달 `phTimer` 를 [CWorkerThread::RemoveHandle](#removehandle) 를 타이머를 닫습니다.  
  
##  <a name="cworkerthread"></a>CWorkerThread::CWorkerThread  
 생성자입니다.  
  
```
CWorkerThread() throw();
```  
  
##  <a name="dtor"></a>CWorkerThread:: ~ CWorkerThread  
 소멸자입니다.  
  
```
~CWorkerThread() throw();
```  
  
### <a name="remarks"></a>설명  
 호출 [CWorkerThread::Shutdown](#shutdown)합니다.  
  
##  <a name="getthreadhandle"></a>CWorkerThread::GetThreadHandle  
 작업자 스레드의 스레드 핸들을 가져오려면이 메서드를 호출 합니다.  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>반환 값  
 작업자 스레드를 초기화 되지 않은 경우 스레드 핸들 또는 NULL을 반환 합니다.  
  
##  <a name="getthreadid"></a>CWorkerThread::GetThreadId  
 작업자 스레드의 스레드 ID를 가져오려면이 메서드를 호출 합니다.  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>반환 값  
 작업자 스레드를 초기화 되지 않은 경우의 스레드 ID 또는 NULL을 반환 합니다.  
  
##  <a name="initialize"></a>CWorkerThread::Initialize  
 작업자 스레드를 초기화 하려면이 메서드를 호출 합니다.  
  
```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pThread`  
 기존 작업자 스레드입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 호출 하 여 만든 이후 또는 호출한 후에 개체를 초기화 하는 [CWorkerThread::Shutdown](#shutdown)합니다.  
  
 두 개 이상이 있어야 `CWorkerThread` 개체 동일한 작업자 스레드를 사용 하 여 인수를 해당 개체에 대 한 포인터를 전달 합니다 전달 하지 않고 그 중 하나를 초기화 합니다.는 `Initialize` 메서드는 다른 인스턴스의 합니다. 개체 초기화에 사용 하기 전에 마우스 포인터를 사용 하 여 초기화 개체 종료 합니다.  
  
 참조 [CWorkerThread::Shutdown](#shutdown) 기존 개체에 대 한 포인터를 사용 하 여 초기화 될 때 해당 메서드의 동작이 변경 하는 방법에 대 한 내용은 합니다.  
  
##  <a name="removehandle"></a>CWorkerThread::RemoveHandle  
 핸들을 대기 가능 개체의 목록에서 제거 하려면이 메서드를 호출 합니다.  
  
```
HRESULT RemoveHandle(HANDLE hObject) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `hObject`  
 제거에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 핸들이 제거 되 면 [IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) 에 전달 된 연결된 된 개체에 대해 [AddHandle](#addhandle)합니다. 이 호출이 실패 한 경우 `CWorkerThread` Windows 호출 [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211) 핸들에 대해 함수입니다.  
  
##  <a name="shutdown"></a>CWorkerThread::Shutdown  
 작업자 스레드를 종료 하려면이 메서드를 호출 합니다.  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `dwWait`  
 작업자 스레드를 종료 될 때까지 기다리는 시간 (밀리초)에 대 한 시간입니다. ATL_WORKER_THREAD_WAIT 기본값 10 초입니다. 필요한 경우 atlutil.h 포함 하기 전에이 기호에 대 한 사용자가 직접 값을 정의할 수 있습니다. 
  
### <a name="return-value"></a>반환 값  
 성공 또는 실패의 경우와 같이 오류 HRESULT에 S_OK를 반환 합니다. 제한 시간 값 `dwWait`를 초과 합니다.  
  
### <a name="remarks"></a>설명  
 개체를 다시 사용 하려면 호출 [CWorkerThread::Initialize](#initialize) 후이 메서드를 호출 합니다.  
  
 호출 **종료** 다른에 대 한 포인터를 사용 하 여 초기화 하는 개체에 `CWorkerThread` 개체 아무 효과가 없으며 항상 S_OK를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [클래스](../../atl/reference/atl-classes.md)   
 [다중 스레딩: 작업자 스레드 만들기](../../parallel/multithreading-creating-worker-threads.md)   
 [IWorkerThreadClient 인터페이스](../../atl/reference/iworkerthreadclient-interface.md)
