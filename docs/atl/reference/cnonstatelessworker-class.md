---
title: "CNonStatelessWorker 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CNonStatelessWorker<Worker>
- ATL::CNonStatelessWorker
- ATL.CNonStatelessWorker
- CNonStatelessWorker
- ATL::CNonStatelessWorker<Worker>
dev_langs:
- C++
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 804b87bf752aac5cecf64cb61b4d53d6269963f2
ms.lasthandoff: 02/24/2017

---
# <a name="cnonstatelessworker-class"></a>CNonStatelessWorker 클래스
스레드 풀의 요청을 수신 하 고 각 요청에 대해 생성 되 고 삭제 하는 작업자 개체에 전달 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Worker>  
class CNonStatelessWorker
```  
  
#### <a name="parameters"></a>매개 변수  
 *작업자*  
 에 부합 하는 작업자 스레드 클래스는 [작업자 원형을](../../atl/reference/worker-archetype.md) 에 큐의 요청 처리에 대해 적합 한 [CThreadPool](../../atl/reference/cthreadpool-class.md)합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CNonStatelessWorker::RequestType](#requesttype)|구현 [WorkerArchetype::RequestType](worker-archetype.md#requesttype)합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CNonStatelessWorker::Execute](#execute)|구현 [WorkerArchetype::Execute](worker-archetype.md#execute)합니다.|  
|[CNonStatelessWorker::Initialize](#initialize)|구현 [WorkerArchetype::Initialize](worker-archetype.md#initialize)합니다.|  
|[CNonStatelessWorker::Terminate](#terminate)|구현 [WorkerArchetype::Terminate](worker-archetype.md#terminate)합니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스와 함께 사용할 간단한 작업자 스레드는 [CThreadPool](../../atl/reference/cthreadpool-class.md)합니다. 이 클래스는 자체의 모든 요청 처리 기능을 제공 하지 않습니다. 인스턴스 하나를 인스턴스화하여 대신 *작업자* 요청당 해당 인스턴스를 해당 메서드의 구현을 위임 합니다.  
  
 이 클래스의 장점은 기존 작업자 스레드 클래스에 대 한 상태 모델을 변경 하는 편리한 방법을 제공 한다는 것입니다. `CThreadPool`단일 작업자 스레드를의 수명 동안 만듭니다 상태를 포함 하는 작업자 클래스를 그 여러 요청에 대해 저장할 수 있도록 합니다. 에 해당 클래스를 단순히 래핑하여는 `CNonStatelessWorker` 템플릿을 사용 하 여 사용 하기 전에 `CThreadPool`, 작업자 및 단일 요청으로 제한 됩니다 보유 상태 수명입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlutil.h  
  
##  <a name="a-nameexecutea--cnonstatelessworkerexecute"></a><a name="execute"></a>CNonStatelessWorker::Execute  
 구현 [WorkerArchetype::Execute](worker-archetype.md#execute)합니다.  

  
```
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```  
  
### <a name="remarks"></a>주의  
 인스턴스를 만들고이 메서드는 *작업자* 스택 및 호출에서 클래스 [초기화](worker-archetype.md#initialize) 해당 개체에 합니다. 성공적으로 초기화 하는 경우이 메서드 호출 [Execute](worker-archetype.md#execute) 및 [Terminate](worker-archetype.md#terminate) 같은 개체에 있습니다.  

  
##  <a name="a-nameinitializea--cnonstatelessworkerinitialize"></a><a name="initialize"></a>CNonStatelessWorker::Initialize  
 구현 [WorkerArchetype::Initialize](worker-archetype.md#initialize)합니다.  
  
```
BOOL Initialize(void* /* pvParam */) throw();
```  
  
### <a name="return-value"></a>반환 값  
 항상 TRUE를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 클래스 초기화를 수행 하지 않습니다 `Initialize`합니다.  
  
##  <a name="a-namerequesttypea--cnonstatelessworkerrequesttype"></a><a name="requesttype"></a>CNonStatelessWorker::RequestType  
 구현 [WorkerArchetype::RequestType](worker-archetype.md#requesttype)합니다.  
  
```
typedef Worker::RequestType RequestType;
```  
  
### <a name="remarks"></a>주의  
 에 사용 되는 클래스와 동일한 형식의 작업 항목을 처리 하는이 클래스는 *작업자* 템플릿 매개 변수입니다. 참조 [CNonStatelessWorker 개요](../../atl/reference/cnonstatelessworker-class.md) 대 한 자세한 내용은 합니다.  
  
##  <a name="a-nameterminatea--cnonstatelessworkerterminate"></a><a name="terminate"></a>CNonStatelessWorker::Terminate  
 구현 [WorkerArchetype::Terminate](worker-archetype.md#terminate)합니다.  
  
```
void Terminate(void* /* pvParam */) throw();
```  
  
### <a name="remarks"></a>주의  
 이 클래스 모든 정리를 수행 하지 않습니다 `Terminate`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CThreadPool 클래스](../../atl/reference/cthreadpool-class.md)   
 [작업자 원형](../../atl/reference/worker-archetype.md)   
 [클래스](../../atl/reference/atl-classes.md)

