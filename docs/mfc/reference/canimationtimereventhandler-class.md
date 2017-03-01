---
title: "CAnimationTimerEventHandler 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxanimationcontroller/CAnimationTimerEventHandler
- CAnimationTimerEventHandler
dev_langs:
- C++
helpviewer_keywords:
- CAnimationTimerEventHandler class
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 5412c215caf85440e923e8a083ed310f8960849a
ms.lasthandoff: 02/24/2017

---
# <a name="canimationtimereventhandler-class"></a>CAnimationTimerEventHandler 클래스
타이밍 이벤트가 발생할 때 애니메이션 API에서 호출하는 콜백을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationTimerEventHandler::CreateInstance](#createinstance)|인스턴스를 만들고 `CAnimationTimerEventHandler` 콜백 합니다.|  
|[CAnimationTimerEventHandler::OnPostUpdate](#onpostupdate)|애니메이션 업데이트가 완료 된 후 발생 하는 이벤트를 처리 합니다. (`CUIAnimationTimerEventHandlerBase::OnPostUpdate`를 재정의합니다.)|  
|[CAnimationTimerEventHandler::OnPreUpdate](#onpreupdate)|애니메이션 업데이트가 시작 되기 전에 발생 하는 이벤트를 처리 합니다. (`CUIAnimationTimerEventHandlerBase::OnPreUpdate`를 재정의합니다.)|  
|[CAnimationTimerEventHandler::OnRenderingTooSlow](#onrenderingtooslow)|애니메이션에 대 한 렌더링 프레임 속도가 원하는 최소 프레임 속도 이하일 때 발생 하는 이벤트를 처리 합니다. (`CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`를 재정의합니다.)|  
|[CAnimationTimerEventHandler::SetAnimationController](#setanimationcontroller)|이벤트를 라우팅합니다 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.|  
  
## <a name="remarks"></a>주의  
 이 이벤트 처리기 생성 되어 CAnimationController::EnableAnimationTimerEventHandler를 호출할 때 IUIAnimationTimer::SetTimerEventHandler에 전달 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationTimerEventHandlerBase`  
  
 `CAnimationTimerEventHandler`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="a-namecreateinstancea--canimationtimereventhandlercreateinstance"></a><a name="createinstance"></a>CAnimationTimerEventHandler::CreateInstance  
 CAnimationTimerEventHandler 콜백의 인스턴스를 만듭니다.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,  
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```  
  
### <a name="parameters"></a>매개 변수  
 `pAnimationController`  
 이벤트를 받는 하는 애니메이션 컨트롤러에 대 한 포인터입니다.  
  
 `ppTimerEventHandler`  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK가 반환 됩니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.  
  
##  <a name="a-nameonpostupdatea--canimationtimereventhandleronpostupdate"></a><a name="onpostupdate"></a>CAnimationTimerEventHandler::OnPostUpdate  
 애니메이션 업데이트가 완료 된 후 발생 하는 이벤트를 처리 합니다.  
  
```  
IFACEMETHOD(OnPostUpdate)();
```  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL입니다.  
  
##  <a name="a-nameonpreupdatea--canimationtimereventhandleronpreupdate"></a><a name="onpreupdate"></a>CAnimationTimerEventHandler::OnPreUpdate  
 애니메이션 업데이트가 시작 되기 전에 발생 하는 이벤트를 처리 합니다.  
  
```  
IFACEMETHOD(OnPreUpdate)();
```  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL입니다.  
  
##  <a name="a-nameonrenderingtooslowa--canimationtimereventhandleronrenderingtooslow"></a><a name="onrenderingtooslow"></a>CAnimationTimerEventHandler::OnRenderingTooSlow  
 애니메이션에 대 한 렌더링 프레임 속도가 원하는 최소 프레임 속도 이하일 때 발생 하는 이벤트를 처리 합니다.  
  
```  
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```  
  
### <a name="parameters"></a>매개 변수  
 `fps`  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL입니다.  
  
##  <a name="a-namesetanimationcontrollera--canimationtimereventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>CAnimationTimerEventHandler::SetAnimationController  
 이벤트를 라우팅합니다 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>매개 변수  
 `pAnimationController`  
 이벤트를 받는 하는 애니메이션 컨트롤러에 대 한 포인터입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

