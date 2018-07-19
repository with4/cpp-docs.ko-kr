---
title: CAnimationStoryboardEventHandler 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationStoryboardEventHandler [MFC], CAnimationStoryboardEventHandler
- CAnimationStoryboardEventHandler [MFC], CreateInstance
- CAnimationStoryboardEventHandler [MFC], OnStoryboardStatusChanged
- CAnimationStoryboardEventHandler [MFC], OnStoryboardUpdated
- CAnimationStoryboardEventHandler [MFC], SetAnimationController
ms.assetid: 10a7e86b-c02d-4124-9a2e-61ecf8ac62fc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: add30fe8bfe2c19973ff657ae05b739986965a9b
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957119"
---
# <a name="canimationstoryboardeventhandler-class"></a>CAnimationStoryboardEventHandler 클래스
스토리보드의 상태가 변경되거나 스토리보드가 업데이트될 때 애니메이션 API에서 호출하는 콜백을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CAnimationStoryboardEventHandler : public CUIAnimationStoryboardEventHandlerBase<CAnimationStoryboardEventHandler>;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler](#canimationstoryboardeventhandler)|`CAnimationStoryboardEventHandler` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationStoryboardEventHandler::CreateInstance](#createinstance)|인스턴스를 만들고 `CAnimationStoryboardEventHandler` 콜백 합니다.|  
|[CAnimationStoryboardEventHandler::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|처리 `OnStoryboardStatusChanged` 스토리 보드의 상태가 변경 될 때 발생 하는 이벤트, (재정의 `CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged`.)|  
|[CAnimationStoryboardEventHandler::OnStoryboardUpdated](#onstoryboardupdated)|처리 `OnStoryboardUpdated` 스토리 보드가 업데이트 될 때 발생 하는 이벤트, (재정의 `CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated`.)|  
|[CAnimationStoryboardEventHandler::SetAnimationController](#setanimationcontroller)|경로 이벤트에는 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.|  
  
## <a name="remarks"></a>설명  
 이 이벤트 처리기가 생성 되 고에 전달 된 `IUIAnimationStoryboard::SetStoryboardEventHandler` 메서드를 호출 하는 경우 `CAnimationController::EnableStoryboardEventHandler`합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationStoryboardEventHandlerBase`  
  
 `CAnimationStoryboardEventHandler`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="canimationstoryboardeventhandler"></a>  CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler  
 CAnimationStoryboardEventHandler 개체를 만듭니다.  
  
```  
CAnimationStoryboardEventHandler();
```  
  
##  <a name="createinstance"></a>  CAnimationStoryboardEventHandler::CreateInstance  
 CAnimationStoryboardEventHandler 콜백의 인스턴스를 만듭니다.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,  
    IUIAnimationStoryboardEventHandler** ppHandler);
```  
  
### <a name="parameters"></a>매개 변수  
 *pAnimationController*  
 이벤트를 수신 하는 애니메이션 컨트롤러에 대 한 포인터입니다.  
  
 *ppHandler*  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.  
  
##  <a name="onstoryboardstatuschanged"></a>  CAnimationStoryboardEventHandler::OnStoryboardStatusChanged  
 스토리 보드의 상태가 변경 될 때 발생 하는 OnStoryboardStatusChanged 이벤트 처리  
  
```  
IFACEMETHOD(OnStoryboardStatusChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in UI_ANIMATION_STORYBOARD_STATUS newStatus,
    __in UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```  
  
### <a name="parameters"></a>매개 변수  
 *스토리 보드*  
 상태가 변경 된 스토리 보드에 대 한 포인터입니다.  
  
 *newStatus*  
 새 스토리 보드 상태를 지정합니다.  
  
 *previousStatus*  
 이전 스토리 보드 상태를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL입니다.  
  
##  <a name="onstoryboardupdated"></a>  CAnimationStoryboardEventHandler::OnStoryboardUpdated  
 스토리 보드가 업데이트 될 때 발생 하는 OnStoryboardUpdated 이벤트 처리  
  
```  
IFACEMETHOD(OnStoryboardUpdated) (__in IUIAnimationStoryboard* storyboard);
```  
  
### <a name="parameters"></a>매개 변수  
 *스토리 보드*  
 에 대 한 포인터 스토리 보드를 업데이트 했습니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL입니다.  
  
##  <a name="setanimationcontroller"></a>  CAnimationStoryboardEventHandler::SetAnimationController  
 경로 이벤트에는 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>매개 변수  
 *pAnimationController*  
 이벤트를 수신 하는 애니메이션 컨트롤러에 대 한 포인터입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
