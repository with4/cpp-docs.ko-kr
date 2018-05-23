---
title: 작업자 아키타 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cee9df0b137655fe66e68c189de756f15233a94d
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="worker-archetype"></a>작업자 아키타
준수 하는 클래스는 *작업자* 아키타 스레드 풀 큐에 대기 프로세스 작업 항목에 코드를 제공 합니다.  
  
 **구현**  
  
 이 아키타를 준수 하는 클래스를 구현 하려면 클래스는 다음 기능을 제공 해야 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[Initialize](#initialize)|모든 요청에 전달 되기 전에 worker 개체를 초기화 하기 위해 호출 [Execute](#execute)합니다.|  
|[실행](#execute)|작업 항목을 처리 하기 위해 호출 됩니다.|  
|[종료](#terminate)|모든 요청에 전달 된 후 작업자 개체의 초기화를 해제 하기 위해 호출 [Execute](#execute)합니다.|  
  
|Typedef|설명|  
|-------------|-----------------|  
|[RequestType](#requesttype)|작업자 클래스에 의해 처리 될 수 있는 작업 항목 형식에 대 한 typedef입니다.|  
  
 일반적인 *작업자* 클래스는 다음과 같습니다.  
  
 [!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]  
  
 **기존 구현**  
  
 이러한 클래스는이 아키타 준수:  
  
|클래스|설명|  
|-----------|-----------------|  
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|스레드 풀의 요청을 수신 하 고 생성 되 고 각 요청에 대 한 제거 하는 작업자 개체를 전달 하 여 합니다.|  
  
 **사용 하 여**  
  
 이러한 템플릿 매개 변수 예상이 아키타에 맞게 클래스:  
  
|매개 변수 이름|사용 주체|  
|--------------------|-------------|  
|*작업자*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|  
|*작업자*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlutil.h  
  
## <a name="execute"></a>WorkerArchetype::Execute
작업 항목을 처리 하기 위해 호출 됩니다.  
  
  
  
```  
void Execute(
    RequestType request,  
    void* pvWorkerParam,  
    OVERLAPPED* pOverlapped);
```  
  
#### <a name="parameters"></a>매개 변수  
 `request`  
 처리 해야 하는 작업 항목입니다. 와 동일한 형식의 작업 항목은 `RequestType`합니다.  
  
 `pvWorkerParam`  
 작업자 클래스에 의해 인식 사용자 지정 매개 변수입니다. 또한 전달할 `WorkerArchetype::Initialize` 및 `Terminate`합니다.  
  
 `pOverlapped`  
 에 대 한 포인터는 [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) 구조를 큐에 항목 대상 작업에 큐를 만드는 데 사용 합니다.  
  
## <a name="initialize"></a> WorkerArchetype::Initialize
모든 요청에 전달 되기 전에 worker 개체를 초기화 하기 위해 호출 `WorkerArchetype::Execute`합니다.  
```
BOOL Initialize(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>매개 변수  
 `pvParam`  
 작업자 클래스에 의해 인식 사용자 지정 매개 변수입니다. 또한 전달할 `WorkerArchetype::Terminate` 및 `WorkerArchetype::Execute`합니다.  
  
### <a name="return-value"></a>반환 값  
 반환할 **TRUE** 성공 **FALSE** 실패 합니다.  
  
## <a name="requesttype"></a> WorkerArchetype::RequestType
작업자 클래스에 의해 처리 될 수 있는 작업 항목 형식에 대 한 typedef입니다.  
  
```  
typedef MyRequestType RequestType;    
```  
  
### <a name="remarks"></a>설명  
 이 형식은의 첫 번째 매개 변수로 사용 해야 `WorkerArchetype::Execute` 는 ULONG_PTR의 캐스팅 되 고 수 있어야 하 고 있습니다.  
  
## <a name="terminate"></a> WorkerArchetype::Terminate
모든 요청에 전달 된 후 작업자 개체의 초기화를 해제 하기 위해 호출 `WorkerArchetype::Execute`).  
    
``` 
void Terminate(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>매개 변수  
 `pvParam`  
 작업자 클래스에 의해 인식 사용자 지정 매개 변수입니다. 또한 전달할 `WorkerArchetype::Initialize` 및 `WorkerArchetype::Execute`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)



