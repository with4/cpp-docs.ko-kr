---
title: AsyncBase 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase
dev_langs:
- C++
helpviewer_keywords:
- AsyncBase class
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5c9dbd5d7296edaed9e850e6453f1b1b593ddba9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="asyncbase-class"></a>AsyncBase 클래스
Windows 런타임 비동기 상태 컴퓨터를 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
template <  
   typename TComplete,  
   typename TProgress = Details::Nil,  
   AsyncResultType resultType = SingleResult  
>  
class AsyncBase : public AsyncBase<TComplete, Details::Nil, resultType>;  
  
template <  
   typename TComplete,  
   AsyncResultType resultType  
>  
class AsyncBase<TComplete, Details::Nil, resultType> : public Microsoft::WRL::Implements<IAsyncInfo>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `TComplete`  
 비동기 작업이 완료 될 때 호출 되는 이벤트 처리기입니다.  
  
 `TProgress`  
 작업의 현재 진행률을 보고 하는 비동기 작업 실행 될 때 호출 되는 이벤트 처리기입니다.  
  
 `resultType`  
 중 하나는 [AsyncResultType](../windows/asyncresulttype-enumeration.md) 열거형 값입니다. 기본적으로 SingleResult입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[AsyncBase::AsyncBase 생성자](../windows/asyncbase-asyncbase-constructor.md)|AsyncBase 클래스의 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[AsyncBase::Cancel 메서드](../windows/asyncbase-cancel-method.md)|비동기 작업을 취소합니다.|  
|[AsyncBase::Close 메서드](../windows/asyncbase-close-method.md)|비동기 작업을 닫습니다.|  
|[AsyncBase::FireCompletion 메서드](../windows/asyncbase-firecompletion-method.md)|완료 이벤트 처리기를 호출 하거나 내부 진행률 대리자를 다시 설정 합니다.|  
|[AsyncBase::FireProgress 메서드](../windows/asyncbase-fireprogress-method.md)|현재 진행률 이벤트 처리기를 호출합니다.|  
|[AsyncBase::get_ErrorCode 메서드](../windows/asyncbase-get-errorcode-method.md)|현재 비동기 작업에 대 한 오류 코드를 검색합니다.|  
|[AsyncBase::get_Id 메서드](../windows/asyncbase-get-id-method.md)|비동기 작업의 핸들을 검색 합니다.|  
|[AsyncBase::get_Status 메서드](../windows/asyncbase-get-status-method.md)|비동기 작업의 상태를 나타내는 값을 검색 합니다.|  
|[AsyncBase::GetOnComplete 메서드](../windows/asyncbase-getoncomplete-method.md)|지정된 된 변수를 현재 완료 이벤트 처리기의 주소를 복사합니다.|  
|[AsyncBase::GetOnProgress 메서드](../windows/asyncbase-getonprogress-method.md)|지정된 된 변수를 현재 진행률 이벤트 처리기의 주소를 복사합니다.|  
|[AsyncBase::put_Id 메서드](../windows/asyncbase-put-id-method.md)|비동기 작업의 핸들을 설정합니다.|  
|[AsyncBase::PutOnComplete 메서드](../windows/asyncbase-putoncomplete-method.md)|지정된 된 값으로는 완료 이벤트 처리기의 주소를 설정합니다.|  
|[AsyncBase::PutOnProgress 메서드](../windows/asyncbase-putonprogress-method.md)|진행률 이벤트 처리기의 주소 지정된 된 값으로 설정합니다.|  
|[AsyncBase::Start 메서드](../windows/asyncbase-start-method.md)|비동기 작업을 시작 합니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[AsyncBase::CheckValidStateForDelegateCall 메서드](../windows/asyncbase-checkvalidstatefordelegatecall-method.md)|현재 비동기 상태에서 대리자 속성을 수정할 수 있는지 테스트 합니다.|  
|[AsyncBase::CheckValidStateForResultsCall 메서드](../windows/asyncbase-checkvalidstateforresultscall-method.md)|현재 비동기 상태에서 비동기 작업의 결과 수집할 수 있는지 테스트 합니다.|  
|[AsyncBase::ContinueAsyncOperation 메서드](../windows/asyncbase-continueasyncoperation-method.md)|비동기 작업을 계속 처리 해야 중단 되어야 하는지 여부를 결정 합니다.|  
|[AsyncBase::CurrentStatus 메서드](../windows/asyncbase-currentstatus-method.md)|현재 비동기 작업의 상태를 검색 합니다.|  
|[AsyncBase::ErrorCode 메서드](../windows/asyncbase-errorcode-method.md)|현재 비동기 작업에 대 한 오류 코드를 검색합니다.|  
|[AsyncBase::OnCancel 메서드](../windows/asyncbase-oncancel-method.md)|파생된 클래스에서 재정의 되 면 비동기 작업을 취소 합니다.|  
|[AsyncBase::OnClose 메서드](../windows/asyncbase-onclose-method.md)|파생된 클래스에서 재정의 하는 경우 비동기 작업을 닫습니다.|  
|[AsyncBase::OnStart 메서드](../windows/asyncbase-onstart-method.md)|파생된 클래스에서 재정의 되 면 비동기 작업을 시작 합니다.|  
|[AsyncBase::TryTransitionToCompleted 메서드](../windows/asyncbase-trytransitiontocompleted-method.md)|현재 비동기 작업이 완료 되었는지 여부를 나타냅니다.|  
|[AsyncBase::TryTransitionToError 메서드](../windows/asyncbase-trytransitiontoerror-method.md)|지정된 된 오류 코드 내부 오류 상태를 수정할 수 있는지 여부를 나타냅니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `AsyncBase`  
  
 `AsyncBase`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)