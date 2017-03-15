---
title: "작업자 원형을 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
caps.latest.revision: 16
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
ms.openlocfilehash: 046160644cca3bd23e4293a3c52692d2b4c94cd5
ms.lasthandoff: 02/24/2017

---
# <a name="worker-archetype"></a>작업자 원형
준수 하는 클래스는 *작업자* 원형을 스레드 풀에서 대기열에 있는 프로세스 작업 항목에는 코드를 제공 합니다.  
  
 **구현**  
  
 클래스는이 원형을에 맞는 클래스를 구현 하려면 다음과 같은 기능을 제공 해야 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[초기화](#initialize)|모든 요청에 전달 되기 전에 작업자 개체를 초기화 하기 위해 호출 [Execute](#execute)합니다.|  
|[실행](#execute)|작업 항목을 처리 하기 위해 호출.|  
|[종료](#terminate)|모든 요청에 전달 된 후 작업자 개체의 초기화를 취소 하기 위해 호출 [Execute](#execute)합니다.|  
  
|Typedef|설명|  
|-------------|-----------------|  
|[RequestType](#requesttype)|작업자 클래스에 의해 처리 될 수 있는 작업 항목의 형식에 대 한 typedef입니다.|  
  
 일반적인 *작업자* 클래스는 다음과 같습니다.  
  
 [!code-cpp[NVC_ATL_Utilities #&137;](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]  
  
 **기존 구현**  
  
 이러한 클래스는이 원형의을 따릅니다.  
  
|클래스|설명|  
|-----------|-----------------|  
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|스레드 풀에서 요청을 수신 하 고으로 생성 되어 각 요청에 대 한 소멸 하는 작업자 개체를 전달 합니다.|  
  
 **사용 하 여**  
  
 이 원형에 맞게 클래스 예상 하는 템플릿 매개 변수.  
  
|매개 변수 이름|사용 주체|  
|--------------------|-------------|  
|*작업자*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|  
|*작업자*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlutil.h  
  
## <a name="a-nameexecuteaworkerarchetypeexecute"></a><a name="execute"></a>WorkerArchetype::Execute
작업 항목을 처리 하기 위해 호출.  
  
  
  
```  
void Execute(
    RequestType request,  
    void* pvWorkerParam,  
    OVERLAPPED* pOverlapped);
```  
  
#### <a name="parameters"></a>매개 변수  
 `request`  
 처리할 작업 항목입니다. 와 동일한 형식의 작업 항목은 `RequestType`합니다.  
  
 `pvWorkerParam`  
 작업자 클래스에 의해 인식 사용자 지정 매개 변수입니다. 또한 전달 `WorkerArchetype::Initialize` 및 `Terminate`합니다.  
  
 `pOverlapped`  
 에 대 한 포인터는 [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) 구조를에서 어떤 작업 항목이 대기 중인 큐를 만드는 데 사용 합니다.  
  
## <a name="a-nameinitializea-workerarchetypeinitialize"></a><a name="initialize"></a>WorkerArchetype::Initialize
모든 요청에 전달 되기 전에 작업자 개체를 초기화 하기 위해 호출 `WorkerArchetype::Execute`합니다.  
```
BOOL Initialize(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>매개 변수  
 `pvParam`  
 작업자 클래스에 의해 인식 사용자 지정 매개 변수입니다. 또한 전달 `WorkerArchetype::Terminate` 및 `WorkerArchetype::Execute`합니다.  
  
### <a name="return-value"></a>반환 값  
 반환할 **TRUE** 성공 **FALSE** 실패 합니다.  
  
## <a name="a-namerequesttypea-workerarchetyperequesttype"></a><a name="requesttype"></a>WorkerArchetype::RequestType
작업자 클래스에 의해 처리 될 수 있는 작업 항목의 형식에 대 한 typedef입니다.  
  
```  
typedef MyRequestType RequestType;    
```  
  
### <a name="remarks"></a>주의  
 이 형식은의 첫 번째 매개 변수로 사용 해야 `WorkerArchetype::Execute` 는 ULONG_PTR에서 캐스팅 될 수 있어야 하 고 있습니다.  
  
## <a name="a-nameterminatea-workerarchetypeterminate"></a><a name="terminate"></a>WorkerArchetype::Terminate
모든 요청에 전달 된 후 작업자 개체의 초기화를 취소 하기 위해 호출 `WorkerArchetype::Execute`).  
    
``` 
void Terminate(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>매개 변수  
 `pvParam`  
 작업자 클래스에 의해 인식 사용자 지정 매개 변수입니다. 또한 전달 `WorkerArchetype::Initialize` 및 `WorkerArchetype::Execute`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Archetype](../../atl/reference/atl-archetypes.md)   
 [개념](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)




