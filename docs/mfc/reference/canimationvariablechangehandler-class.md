---
title: CAnimationVariableChangeHandler 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationVariableChangeHandler [MFC], OnValueChanged
- CAnimationVariableChangeHandler [MFC], SetAnimationController
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2e35fc33b26fa6bead73458a46d7c4edee1cf136
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350994"
---
# <a name="canimationvariablechangehandler-class"></a>CAnimationVariableChangeHandler 클래스
애니메이션 변수 값이 변경될 때 애니메이션 API에서 호출하는 콜백을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|`CAnimationVariableChangeHandler` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|`CAnimationVariableChangeHandler::CreateInstance`|인스턴스를 만들고 `CAnimationVariableChangeHandler` 개체입니다.|  
|[CAnimationVariableChangeHandler::OnValueChanged](#onvaluechanged)|애니메이션 변수 값이 변경 될 때 호출 합니다. (`CUIAnimationVariableChangeHandlerBase::OnValueChanged`를 재정의합니다.)|  
|[CAnimationVariableChangeHandler::SetAnimationController](#setanimationcontroller)|경로 이벤트에는 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.|  
  
## <a name="remarks"></a>설명  
 이 이벤트 처리기가 생성 되 고에 전달 된 `IUIAnimationVariable::SetVariableChangeHandler` 메서드를 호출 하는 경우 `CAnimationVariable::EnableValueChangedEvent` 또는 `CAnimationBaseObject::EnableValueChangedEvent` (이 이벤트는 애니메이션 개체에 캡슐화 하는 모든 애니메이션 변수를 통해).  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableChangeHandlerBase`  
  
 `CAnimationVariableChangeHandler`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="onvaluechanged"></a>  CAnimationVariableChangeHandler::OnValueChanged  
 애니메이션 변수 값이 변경 될 때 호출 합니다.  
  
```  
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `storyboard`  
 변수를 애니메이션 효과 주는 스토리 보드 합니다.  
  
 `variable`  
 애니메이션 변수를 업데이트입니다.  
  
 `newValue`  
 새 값입니다.  
  
 `previousValue`  
 이전 값입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.  
  
##  <a name="setanimationcontroller"></a>  CAnimationVariableChangeHandler::SetAnimationController  
 경로 이벤트에는 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>매개 변수  
 `pAnimationController`  
 이벤트를 수신 하는 애니메이션 컨트롤러에 대 한 포인터입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
