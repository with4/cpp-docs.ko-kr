---
title: "AsyncBase 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsyncBase 클래스"
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows 런타임은 비동기 상태 시스템을 구현합니다.  
  
## 구문  
  
```  
  
template <  
   typename TComplete,  
   typename TProgress = Details::Nil,  
   AsyncResultType resultType = SingleResult  
>  
class AsyncBase : public AsyncBase< TComplete, Details::Nil, resultType >;  
  
template <  
   typename TComplete,  
   AsyncResultType resultType  
>  
class AsyncBase< TComplete, Details::Nil, resultType > : public Microsoft::WRL::Implements< IAsyncInfo >;  
```  
  
#### 매개 변수  
 `TComplete`  
 비동기 작업이 완료될 때 호출되는 이벤트 처리기입니다.  
  
 `TProgress`  
 실행 중인 비동기 작업을 작업의 현재 진행률을 보고할 때 호출 되는 이벤트 처리기입니다.  
  
 `resultType`  
 [AsyncResultType](../windows/asyncresulttype-enumeration.md) 열거형 값중 하나입니다.  기본적으로 SingleResult.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[AsyncBase::AsyncBase 생성자](../windows/asyncbase-asyncbase-constructor.md)|AsyncBase 클래스의 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[AsyncBase::Cancel 메서드](../windows/asyncbase-cancel-method.md)|비동기 작업을 취소합니다.|  
|[AsyncBase::Close 메서드](../windows/asyncbase-close-method.md)|비동기 작업을 닫습니다.|  
|[AsyncBase::FireCompletion 메서드](../windows/asyncbase-firecompletion-method.md)|완료 이벤트 처리기를 호출하거나 대리자 내부 진행으로 다시 설정합니다.|  
|[AsyncBase::FireProgress 메서드](../windows/asyncbase-fireprogress-method.md)|현재 진행 중인 이벤트 처리기를 호출합니다.|  
|[AsyncBase::get\_ErrorCode 메서드](../windows/asyncbase-get-errorcode-method.md)|현재 비동기 작업에 대한 오류 코드를 검색 합니다.|  
|[AsyncBase::get\_Id 메서드](../windows/asyncbase-get-id-method.md)|비동기 작업에 대한 핸들을 검색합니다.|  
|[AsyncBase::get\_Status 메서드](../windows/asyncbase-get-status-method.md)|비동기 작업의 상태를 나타내는 값을 검색합니다.|  
|[AsyncBase::GetOnComplete 메서드](../windows/asyncbase-getoncomplete-method.md)|지정된 된 변수를 현재 완료된 이벤트 처리기의 주소에 복사합니다.|  
|[AsyncBase::GetOnProgress 메서드](../windows/asyncbase-getonprogress-method.md)|지정된 된 변수를 현재 진행 중인 이벤트 처리기의 주소에 복사합니다.|  
|[AsyncBase::put\_Id 메서드](../windows/asyncbase-put-id-method.md)|비동기 작업에 대한 핸들을 설정합니다.|  
|[AsyncBase::PutOnComplete 메서드](../windows/asyncbase-putoncomplete-method.md)|완료 이벤트 처리기의 주소를 지정된 된 값으로 설정합니다.|  
|[AsyncBase::PutOnProgress 메서드](../windows/asyncbase-putonprogress-method.md)|진행률 이벤트 처리기의 주소를 지정된 된 값으로 설정합니다.|  
|[AsyncBase::Start 메서드](../windows/asyncbase-start-method.md)|비동기 작업을 시작합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[AsyncBase::CheckValidStateForDelegateCall 메서드](../windows/asyncbase-checkvalidstatefordelegatecall-method.md)|현재 비동기 상태에서는 대리자 속성을 수정할 수 있는지 여부를 테스트 합니다.|  
|[AsyncBase::CheckValidStateForResultsCall 메서드](../windows/asyncbase-checkvalidstateforresultscall-method.md)|현재 비동기 상태에서 비동기 작업의 결과를 수집할 수 있는지 여부를 테스트 합니다.|  
|[AsyncBase::ContinueAsyncOperation 메서드](../windows/asyncbase-continueasyncoperation-method.md)|비동기 작업 처리를 계속 중지해야 하는지 여부를 결정 합니다.|  
|[AsyncBase::CurrentStatus 메서드](../windows/asyncbase-currentstatus-method.md)|현재 비동기 작업의 상태를 검색합니다.|  
|[AsyncBase::ErrorCode 메서드](../windows/asyncbase-errorcode-method.md)|현재 비동기 작업에 대한 오류 코드를 검색 합니다.|  
|[AsyncBase::OnCancel 메서드](../windows/asyncbase-oncancel-method.md)|파생 클래스에서 재정의되는 경우 비동기 작업을 취소합니다.|  
|[AsyncBase::OnClose 메서드](../windows/asyncbase-onclose-method.md)|파생 클래스에서 재정의되는 경우 비동기 작업을 선택합니다.|  
|[AsyncBase::OnStart 메서드](../windows/asyncbase-onstart-method.md)|파생 클래스에서 재정의되는 경우 비동기 플러시 작업을 시작합니다.|  
|[AsyncBase::TryTransitionToCompleted 메서드](../windows/asyncbase-trytransitiontocompleted-method.md)|현재 비동기 작업이 완료되었는지 여부를 나타냅니다.|  
|[AsyncBase::TryTransitionToError 메서드](../windows/asyncbase-trytransitiontoerror-method.md)|지정된 오류 코드 내부에서 오류 상태를 수정할 수 있는지 여부를 나타냅니다.|  
  
## 상속 계층  
 `AsyncBase`  
  
 `AsyncBase`  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)