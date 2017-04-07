---
title: "CThreadPool 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CThreadPool
- ATLUTIL/ATL::CThreadPool
- ATLUTIL/ATL::CThreadPool::CThreadPool
- ATLUTIL/ATL::CThreadPool::AddRef
- ATLUTIL/ATL::CThreadPool::GetNumThreads
- ATLUTIL/ATL::CThreadPool::GetQueueHandle
- ATLUTIL/ATL::CThreadPool::GetSize
- ATLUTIL/ATL::CThreadPool::GetTimeout
- ATLUTIL/ATL::CThreadPool::Initialize
- ATLUTIL/ATL::CThreadPool::QueryInterface
- ATLUTIL/ATL::CThreadPool::QueueRequest
- ATLUTIL/ATL::CThreadPool::Release
- ATLUTIL/ATL::CThreadPool::SetSize
- ATLUTIL/ATL::CThreadPool::SetTimeout
- ATLUTIL/ATL::CThreadPool::Shutdown
dev_langs:
- C++
helpviewer_keywords:
- CThreadPool class
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
caps.latest.revision: 22
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
ms.openlocfilehash: 632514d03e7037ef42a1566462db5dec6f5cc1e5
ms.lasthandoff: 02/24/2017

---
# <a name="cthreadpool-class"></a>CThreadPool 클래스
이 클래스는 작업 항목의 큐를 처리 하는 작업자 스레드의 풀을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Worker, class ThreadTraits = DefaultThreadTraits>  
class CThreadPool : public IThreadPoolConfig
```  
  
#### <a name="parameters"></a>매개 변수  
 *작업자*  
 에 부합 하는 클래스는 [작업자 원형을](../../atl/reference/worker-archetype.md) 스레드 풀에 대기 중인 항목이 작업을 처리 하는 데 사용 하는 코드를 제공 합니다.  
  
 `ThreadTraits`  
 풀에서 스레드를 만드는 데 사용 하는 함수를 제공 하는 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CThreadPool::CThreadPool](#cthreadpool)|스레드 풀에 대 한 생성자입니다.|  
|[CThreadPool:: ~ CThreadPool](#dtor)|스레드 풀에 대 한 소멸자가 있습니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CThreadPool::AddRef](#addref)|구현 `IUnknown::AddRef`합니다.|  
|[CThreadPool::GetNumThreads](#getnumthreads)|풀의 스레드 수를 가져오려면이 메서드를 호출 합니다.|  
|[CThreadPool::GetQueueHandle](#getqueuehandle)|작업 항목 큐에 사용 되는 IO 완료 포트의 핸들을 가져오려면이 메서드를 호출 합니다.|  
|[CThreadPool::GetSize](#getsize)|풀의 스레드 수를 가져오려면이 메서드를 호출 합니다.|  
|[CThreadPool::GetTimeout](#gettimeout)|스레드 풀 스레드를 종료를 대기 하는 시간 (밀리초)에는 최대 시간을 가져오려면이 메서드를 호출 합니다.|  
|[CThreadPool::Initialize](#initialize)|스레드 풀을 초기화 하려면이 메서드를 호출 합니다.|  
|[CThreadPool::QueryInterface](#queryinterface)|구현 **IUnknown::QueryInterface**합니다.|  
|[CThreadPool::QueueRequest](#queuerequest)|풀의 스레드에 의해 처리 되는 작업 항목을 큐에이 메서드를 호출 합니다.|  
|[CThreadPool::Release](#release)|구현 `IUnknown::Release`합니다.|  
|[CThreadPool::SetSize](#setsize)|풀의 스레드 수를 설정 하려면이 메서드를 호출 합니다.|  
|[CThreadPool::SetTimeout](#settimeout)|스레드 풀 스레드를 종료를 대기 하는 시간 (밀리초)에는 최대 시간을 설정 하려면이 메서드를 호출 합니다.|  
|[CThreadPool::Shutdown](#shutdown)|스레드 풀을 종료 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>주의  
 풀의 스레드 생성 및 풀 초기화, 크기 조정 또는 종료 될 때 소멸 됩니다. 클래스의 인스턴스 *작업자* 풀에 있는 각 작업자 스레드의 스택에 생성 됩니다. 각 인스턴스는 스레드 수명 동안 존재 합니다.  
  
 스레드를 만든 후 즉시 *작업자*:: `Initialize` 해당 스레드와 연결 된 개체에 호출 됩니다. 스레드, 소멸 되기 직전 *작업자*:: `Terminate` 호출 됩니다. 두 방법 모두에 동의 해야는 **void\* ** 인수입니다. 이 인수의 값이를 통해 스레드 풀에 전달 되는 `pvWorkerParam` 의 매개 변수 [CThreadPool::Initialize](#initialize)합니다.  
  
 작업자 스레드는 큐와 호출 밖으로 항목에에서 있는 경우 작업 항목 큐 및 작업자 스레드 작업에 사용할 수 있는, 가져올는 **Execute** 의 메서드는 *작업자* 해당 스레드에 대 한 개체입니다. 세 개의 항목이 메서드에 전달 됩니다: 동일한 큐에서 항목 `pvWorkerParam` 에 전달 된 *작업자*:: `Initialize` 및 *작업자*:: `Terminate`에 대 한 포인터는 [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) IO 완료 포트 큐에 사용 된 구조입니다.  
  
 *작업자* 클래스 형식 정의 제공 하 여 스레드 풀에서 대기 하는 항목의 형식을 선언 *작업자*:: `RequestType`합니다. 이 형식으로 캐스팅 될 수 있어야 합니다는 **ULONG_PTR**합니다.  
  
 예로 *작업자* 클래스는 [CNonStatelessWorker 클래스](../../atl/reference/cnonstatelessworker-class.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IUnknown`  
  
 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)  
  
 `CThreadPool`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlutil.h  
  
##  <a name="addref"></a>CThreadPool::AddRef  
 구현 `IUnknown::AddRef`합니다.  
  
```
ULONG STDMETHODCALLTYPE AddRef() throw();
```  
  
### <a name="return-value"></a>반환 값  
 항상 1을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 클래스는 참조 횟수를 사용 하 여 수명 제어를 구현 하지 않습니다.  
  
##  <a name="cthreadpool"></a>CThreadPool::CThreadPool  
 스레드 풀에 대 한 생성자입니다.  
  
```
CThreadPool() throw();
```  
  
### <a name="remarks"></a>주의  
 제한 시간 값을 초기화 [ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT](http://msdn.microsoft.com/library/c1e660a7-d490-42af-bbe1-ded76e80cc10)합니다.  
  
##  <a name="dtor"></a>CThreadPool:: ~ CThreadPool  
 스레드 풀에 대 한 소멸자가 있습니다.  
  
```
~CThreadPool() throw();
```  
  
### <a name="remarks"></a>주의  
 호출 [CThreadPool::Shutdown](#shutdown)합니다.  
  
##  <a name="getnumthreads"></a>CThreadPool::GetNumThreads  
 풀의 스레드 수를 가져오려면이 메서드를 호출 합니다.  
  
```
int GetNumThreads() throw();
```  
  
### <a name="return-value"></a>반환 값  
 풀의 스레드 수를 반환합니다.  
  
##  <a name="getqueuehandle"></a>CThreadPool::GetQueueHandle  
 작업 항목 큐에 사용 되는 IO 완료 포트의 핸들을 가져오려면이 메서드를 호출 합니다.  
  
```
HANDLE GetQueueHandle() throw();
```  
  
### <a name="return-value"></a>반환 값  
 스레드 풀이 초기화 되지 않은 경우 큐 핸들 또는 NULL을 반환 합니다.  
  
##  <a name="getsize"></a>CThreadPool::GetSize  
 풀의 스레드 수를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pnNumThreads`  
 [out] 성공 풀의 스레드 수를 수신 하는 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="gettimeout"></a>CThreadPool::GetTimeout  
 스레드 풀 스레드를 종료를 대기 하는 시간 (밀리초)에는 최대 시간을 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pdwMaxWait`  
 [out] 스레드 풀 스레드를 종료를 대기 하는 시간 (밀리초)에는 최대 시간을 받으면 성공 하는 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 제한 시간 값에서 사용 됩니다 [CThreadPool::Shutdown](#shutdown) 를 해당 메서드에 변수에 다른 값이 없는 경우.  
  
##  <a name="initialize"></a>CThreadPool::Initialize  
 스레드 풀을 초기화 하려면이 메서드를 호출 합니다.  
  
```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pvWorkerParam`  
 작업자 스레드 개체를 전달 하도록 작업자 매개 변수 `Initialize`, **Execute**, 및 `Terminate` 메서드.  
  
 `nNumThreads`  
 스레드 풀의 요청된 수입니다.  
  
 경우 `nNumThreads` 가 음수 이면 절대값이 곱할 스레드의 총 개수를 가져올 컴퓨터에서 프로세서의 수입니다.  
  
 경우 `nNumThreads` 가&0; 이면 [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) 스레드의 총 개수를 가져올 컴퓨터에서 프로세서의 수를 곱합니다.  
  
 `dwStackSize`  
 풀의 각 스레드에 대 한 스택 크기입니다.  
  
 *hCompletion*  
 완료 포트와 연결할 개체의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="queryinterface"></a>CThreadPool::QueryInterface  
 구현 **IUnknown::QueryInterface**합니다.  
  
```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```  
  
### <a name="remarks"></a>주의  
 이 클래스의 개체에 대 한 성공적으로 쿼리할 수는 **IUnknown** 및 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md) 인터페이스입니다.  
  
##  <a name="queuerequest"></a>CThreadPool::QueueRequest  
 풀의 스레드에 의해 처리 되는 작업 항목을 큐에이 메서드를 호출 합니다.  
  
```
BOOL QueueRequest(Worker::RequestType request) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `request`  
 큐에 대기 시킬 요청입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 큐에 작업 항목을 추가합니다. 풀의 스레드는 수신 된 순서 대로 큐에서 항목을 선택 합니다.  
  
##  <a name="release"></a>CThreadPool::Release  
 구현 `IUnknown::Release`합니다.  
  
```
ULONG STDMETHODCALLTYPE Release() throw();
```  
  
### <a name="return-value"></a>반환 값  
 항상 1을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 클래스는 참조 횟수를 사용 하 여 수명 제어를 구현 하지 않습니다.  
  
##  <a name="setsize"></a>CThreadPool::SetSize  
 풀의 스레드 수를 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nNumThreads`  
 스레드 풀의 요청된 수입니다.  
  
 경우 `nNumThreads` 가 음수 이면 절대값이 곱할 스레드의 총 개수를 가져올 컴퓨터에서 프로세서의 수입니다.  
  
 경우 `nNumThreads` 가&0; 이면 [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) 스레드의 총 개수를 가져올 컴퓨터에서 프로세서의 수를 곱합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 지정 된 스레드 수가 스레드 풀의 현재 개수 보다 작은 경우 개체 종료 메시지를 대기 중인 스레드에 의해 선택 하도록 큐에 넣습니다. 대기 중인 스레드는 큐 메시지를 끌어와서, 스레드 풀 알리고 스레드 절차를 종료 합니다. 풀의 스레드 수에 지정된 된 수에 도달할 때까지 또는 스레드가 없습니다에 지정 된 기간 내에서 종료 될 때까지이 프로세스가 반복 됩니다 [GetTimeout](#gettimeout)/ [SetTimeout](#settimeout)합니다. 에 해당 하는 HRESULT 메서드는 반환 하는이 상황에서 **WAIT_TIMEOUT** 보류 중인 종료 메시지 취소 됩니다.  
  
##  <a name="settimeout"></a>CThreadPool::SetTimeout  
 스레드 풀 스레드를 종료를 대기 하는 시간 (밀리초)에는 최대 시간을 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `dwMaxWait`  
 스레드 풀 스레드를 종료를 대기 하는 시간 (밀리초)에 대 한 요청 된 최대 시간입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 제한 시간으로 초기화 됩니다 [ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT](http://msdn.microsoft.com/library/c1e660a7-d490-42af-bbe1-ded76e80cc10) 생성자에 있습니다.  
  
 `dwMaxWait` 종료 하는 단일 스레드 풀을 기다리는 시간입니다. 여러 스레드 풀에서 제거를 수행할 수 있는 최대 시간 수 있습니다. 보다 약간 `dwMaxWait` 스레드 수로 곱한 결과입니다.  
  
##  <a name="shutdown"></a>CThreadPool::Shutdown  
 스레드 풀을 종료 하려면이 메서드를 호출 합니다.  
  
```
void Shutdown(DWORD dwMaxWait = 0) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `dwMaxWait`  
 스레드 풀 스레드를 종료를 대기 하는 시간 (밀리초)에 대 한 요청 된 최대 시간입니다. 이 메서드는 설정한 시간 제한 사용 0 또는 값이 없는 제공 되는 경우 [CThreadPool::SetTimeout](#settimeout)합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 풀의 모든 스레드를 종료 요청을 게시 합니다. 제한 시간이 만료 되 면이 메서드를 호출 합니다 [TerminateThread](http://msdn.microsoft.com/library/windows/desktop/ms686717) 스레드의 종료 되지 않았습니다. 이 메서드는 클래스의 소멸자에서 자동으로 호출 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IThreadPoolConfig 인터페이스](../../atl/reference/ithreadpoolconfig-interface.md)   
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [클래스](../../atl/reference/atl-classes.md)

