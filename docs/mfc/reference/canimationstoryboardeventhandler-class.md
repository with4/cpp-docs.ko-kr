---
title: "CAnimationStoryboardEventHandler 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CAnimationStoryboardEventHandler class
ms.assetid: 10a7e86b-c02d-4124-9a2e-61ecf8ac62fc
caps.latest.revision: 18
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
ms.openlocfilehash: bda8b0c941fd833bf821b563f4ca59cab9598cb8
ms.lasthandoff: 02/24/2017

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
|[CAnimationStoryboardEventHandler::SetAnimationController](#setanimationcontroller)|이벤트를 라우팅합니다 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.|  
  
## <a name="remarks"></a>주의  
 이 이벤트 처리기 생성 되어 전달 `IUIAnimationStoryboard::SetStoryboardEventHandler` 메서드를 호출할 때 `CAnimationController::EnableStoryboardEventHandler`합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationStoryboardEventHandlerBase`  
  
 `CAnimationStoryboardEventHandler`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="canimationstoryboardeventhandler"></a>CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler  
 CAnimationStoryboardEventHandler 개체를 만듭니다.  
  
```  
CAnimationStoryboardEventHandler();
```  
  
##  <a name="createinstance"></a>CAnimationStoryboardEventHandler::CreateInstance  
 CAnimationStoryboardEventHandler 콜백의 인스턴스를 만듭니다.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,  
    IUIAnimationStoryboardEventHandler** ppHandler);
```  
  
### <a name="parameters"></a>매개 변수  
 `pAnimationController`  
 이벤트를 받는 하는 애니메이션 컨트롤러에 대 한 포인터입니다.  
  
 `ppHandler`  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK가 반환 됩니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.  
  
##  <a name="onstoryboardstatuschanged"></a>CAnimationStoryboardEventHandler::OnStoryboardStatusChanged  
 스토리 보드의 상태가 변경 될 때 발생 하는 OnStoryboardStatusChanged 이벤트를 처리 합니다.  
  
```  
IFACEMETHOD(OnStoryboardStatusChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in UI_ANIMATION_STORYBOARD_STATUS newStatus,
    __in UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```  
  
### <a name="parameters"></a>매개 변수  
 `storyboard`  
 상태가 변경 된 스토리 보드에 대 한 포인터입니다.  
  
 `newStatus`  
 새 스토리 보드 상태를 지정합니다.  
  
 `previousStatus`  
 이전 스토리 보드 상태를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL입니다.  
  
##  <a name="onstoryboardupdated"></a>CAnimationStoryboardEventHandler::OnStoryboardUpdated  
 스토리 보드가 업데이트 될 때 발생 하는 OnStoryboardUpdated 이벤트를 처리 합니다.  
  
```  
IFACEMETHOD(OnStoryboardUpdated) (__in IUIAnimationStoryboard* storyboard);
```  
  
### <a name="parameters"></a>매개 변수  
 `storyboard`  
 업데이트 된 스토리 보드에 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL입니다.  
  
##  <a name="setanimationcontroller"></a>CAnimationStoryboardEventHandler::SetAnimationController  
 이벤트를 라우팅합니다 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>매개 변수  
 `pAnimationController`  
 이벤트를 받는 하는 애니메이션 컨트롤러에 대 한 포인터입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

