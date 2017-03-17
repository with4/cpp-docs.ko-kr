---
title: "CWorkerThread 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 24
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
ms.openlocfilehash: ab1c92c1b7442025f91007ef971d81d087351212
ms.lasthandoff: 02/24/2017

---
# <a name="cworkerthread-class"></a>CWorkerThread 클래스
이 클래스는 작업자 스레드를 생성 또는 기존을 사용 하 여, 하나 이상의 커널 개체 핸들을 대기 및 핸들 중 하나에 신호가 전달 될 때 지정 된 클라이언트 함수를 실행 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class ThreadTraits = DefaultThreadTraits>  
class CWorkerThread
```  
  
#### <a name="parameters"></a>매개 변수  
 `ThreadTraits`  
 예: 스레드 만들기 함수를 제공 하는 클래스 [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) 또는 [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="protected-structures"></a>보호 된 구조  
  
|이름|설명|  
|----------|-----------------|  
|`WorkerClientEntry`||  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CWorkerThread::CWorkerThread](#cworkerthread)|작업자 스레드에 대 한 생성자입니다.|  
|[CWorkerThread:: ~ CWorkerThread](#dtor)|작업자 스레드에 대 한 소멸자가 있습니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CWorkerThread::AddHandle](#addhandle)|작업자 스레드에 의해 유지 관리 하는 목록에 있는 대기 가능 개체의 핸들을 추가 하려면이 메서드를 호출 합니다.|  
|[CWorkerThread::AddTimer](#addtimer)|작업자 스레드에 의해 유지 관리 하는 목록에 정기적으로 대기 가능 타이머를 추가 하려면이 메서드를 호출 합니다.|  
|[CWorkerThread::GetThreadHandle](#getthreadhandle)|작업자 스레드의 스레드 핸들을 가져오려면이 메서드를 호출 합니다.|  
|[CWorkerThread::GetThreadId](#getthreadid)|작업자 스레드의 스레드 ID를 가져오려면이 메서드를 호출 합니다.|  
|[CWorkerThread::Initialize](#initialize)|작업자 스레드를 초기화 하려면이 메서드를 호출 합니다.|  
|[CWorkerThread::RemoveHandle](#removehandle)|핸들을 대기 가능 개체의 목록에서 제거 하려면이 메서드를 호출 합니다.|  
|[CWorkerThread::Shutdown](#shutdown)|작업자 스레드를 종료 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>주의  
  
### <a name="to-use-cworkerthread"></a>CWorkerThread를 사용 하 여  
  
1.  이 클래스의 인스턴스를 만듭니다.  
  
2.  호출 [CWorkerThread::Initialize](#initialize)합니다.  
  
3.  호출 [CWorkerThread::AddHandle](#addhandle) 커널 개체와의 구현에 대 한 핸들로 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)합니다.  
  
     -또는-  
  
     호출 [CWorkerThread::AddTimer](#addtimer) 의 구현에 대 한 포인터 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)합니다.  
  
4.  구현 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) 타이머 또는 핸들 신호가 전달 될 때 몇 가지 작업을 합니다.  
  
5.  대기 가능 개체의 목록에서 개체를 제거 하려면 호출 [CWorkerThread::RemoveHandle](#removehandle)합니다.  
  
6.  호출 스레드를 종료 하려면 [CWorkerThread::Shutdown](#shutdown)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlutil.h  
  
##  <a name="addhandle"></a>CWorkerThread::AddHandle  
 작업자 스레드에 의해 유지 관리 하는 목록에 있는 대기 가능 개체의 핸들을 추가 하려면이 메서드를 호출 합니다.  
  
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
 에 대 한 포인터는 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) 핸들 신호가 전달 될 때 호출 될 개체의 인터페이스입니다.  
  
 `dwParam`  
 매개 변수를 전달 하도록 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) 핸들 신호가 전달 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) 를 통해 호출 됩니다 `pClient` 때 핸들을 `hObject`, 신호 됩니다.  
  
##  <a name="addtimer"></a>CWorkerThread::AddTimer  
 작업자 스레드에 의해 유지 관리 하는 목록에 정기적으로 대기 가능 타이머를 추가 하려면이 메서드를 호출 합니다.  
  
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
 에 대 한 포인터는 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) 핸들 신호가 전달 될 때 호출 될 개체의 인터페이스입니다.  
  
 `dwParam`  
 매개 변수를 전달 하도록 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) 핸들 신호가 전달 합니다.  
  
 `phTimer`  
 [out] 새로 만든된 타이머에 대 한 핸들을 받습니다 성공 하는 핸들 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) 를 통해 호출할 수는 `pClient` 타이머 신호를 받는 경우.  
  
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
  
### <a name="remarks"></a>주의  
 호출 [CWorkerThread::Shutdown](#shutdown)합니다.  
  
##  <a name="getthreadhandle"></a>CWorkerThread::GetThreadHandle  
 작업자 스레드의 스레드 핸들을 가져오려면이 메서드를 호출 합니다.  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>반환 값  
 작업자 스레드가 초기화 되지 않은 경우에 스레드 핸들 또는 NULL을 반환 합니다.  
  
##  <a name="getthreadid"></a>CWorkerThread::GetThreadId  
 작업자 스레드의 스레드 ID를 가져오려면이 메서드를 호출 합니다.  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>반환 값  
 작업자 스레드는 초기화 되지 않은 경우에 스레드 ID 또는 NULL을 반환 합니다.  
  
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
  
### <a name="remarks"></a>주의  
 이 메서드를 호출 하 여 만든 이후 또는 함수 호출 후에 개체를 초기화 하는 [CWorkerThread::Shutdown](#shutdown)합니다.  
  
 두 개 이상 있어야 `CWorkerThread` 개체는 같은 작업자 스레드를 사용 하 여, 다음 인수를 해당 개체에 포인터를 전달 하는 전달 하지 않고 그 중 하나를 초기화는 `Initialize` 다른 방법입니다. 포인터를 사용 하 여 초기화 하는 개체 초기화 하는 데 사용 되는 개체 전에 종료 해야 합니다.  
  
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
  
### <a name="remarks"></a>주의  
 핸들 제거 되 면 [IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) 에 전달 된 연결된 된 개체에서 호출 되 [AddHandle](#addhandle)합니다. 이 호출이 실패 하면 `CWorkerThread` Windows 호출 [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211) 핸들에 대해 함수입니다.  
  
##  <a name="shutdown"></a>CWorkerThread::Shutdown  
 작업자 스레드를 종료 하려면이 메서드를 호출 합니다.  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `dwWait`  
 작업자 스레드를 종료 될 때까지 기다리는 시간 (밀리초) 시간입니다.  
  
### <a name="return-value"></a>반환 값  
 등의 실패 시 오류 HRESULT 성공 시 S_OK를 반환 합니다. 제한 시간 값을 `dwWait`을 초과 합니다.  
  
### <a name="remarks"></a>주의  
 개체를 다시 사용 하려면 호출 [CWorkerThread::Initialize](#initialize) 후이 메서드를 호출 합니다.  
  
 호출 **종료** 다른 포인터를 사용 하 여 초기화 하는 개체에 `CWorkerThread` 개체에 영향을 주지 않으며 항상 S_OK를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [클래스](../../atl/reference/atl-classes.md)   
 [다중 스레딩: 작업자 스레드 만들기](../../parallel/multithreading-creating-worker-threads.md)   
 [IWorkerThreadClient 인터페이스](../../atl/reference/iworkerthreadclient-interface.md)

