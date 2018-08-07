---
title: CInterpolatorBase 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CreateInstance
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDependencies
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetFinalValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetCustomInterpolator
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetInitialValueAndVelocity
dev_langs:
- C++
helpviewer_keywords:
- CInterpolatorBase [MFC], CInterpolatorBase
- CInterpolatorBase [MFC], CreateInstance
- CInterpolatorBase [MFC], GetDependencies
- CInterpolatorBase [MFC], GetDuration
- CInterpolatorBase [MFC], GetFinalValue
- CInterpolatorBase [MFC], InterpolateValue
- CInterpolatorBase [MFC], InterpolateVelocity
- CInterpolatorBase [MFC], SetCustomInterpolator
- CInterpolatorBase [MFC], SetDuration
- CInterpolatorBase [MFC], SetInitialValueAndVelocity
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81ad51fe00a0b205000b15a05ede9497850f488e
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041275"
---
# <a name="cinterpolatorbase-class"></a>CInterpolatorBase 클래스
애니메이션 API에서 애니메이션 변수의 새 값을 계산해야 할 때 호출하는 콜백을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CInterpolatorBase::CInterpolatorBase](#cinterpolatorbase)|생성 된 `CInterpolatorBase` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CInterpolatorBase::CreateInstance](#createinstance)|인스턴스를 만들고 `CInterpolatorBase` 이벤트를 처리 하는 사용자 지정 보간에 대 한 포인터를 저장 합니다.|  
|[CInterpolatorBase::GetDependencies](#getdependencies)|보간의 종속성을 가져옵니다. (`CUIAnimationInterpolatorBase::GetDependencies`를 재정의합니다.)|  
|[CInterpolatorBase::GetDuration](#getduration)|보간의 기간을 가져옵니다. (`CUIAnimationInterpolatorBase::GetDuration`를 재정의합니다.)|  
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|보간 잠재 고객 최종 값을 가져옵니다. (`CUIAnimationInterpolatorBase::GetFinalValue`를 재정의합니다.)|  
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|지정된 된 오프셋 위치에서 값을 보간합니다 (재정의 `CUIAnimationInterpolatorBase::InterpolateValue`.)|  
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|지정된 된 오프셋 위치에서 속도 보간합니다 (재정의 `CUIAnimationInterpolatorBase::InterpolateVelocity`.)|  
|[CInterpolatorBase::SetCustomInterpolator](#setcustominterpolator)|이벤트를 처리 하는 사용자 지정 보간에 대 한 포인터를 저장 합니다.|  
|[CInterpolatorBase::SetDuration](#setduration)|보간의 기간 설정 (재정의 `CUIAnimationInterpolatorBase::SetDuration`.)|  
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|보간의 초기 값 및 개발 속도 설정합니다. (`CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`를 재정의합니다.)|  
  
## <a name="remarks"></a>설명  
 이 처리기가 생성 되 고 전달 `IUIAnimationTransitionFactory::CreateTransition` 때는 `CCustomTransition` 애니메이션 초기화 프로세스의 일부로 개체를 만들고 (에 의해 시작 `CAnimationController::AnimateGroup`). 일반적으로이 클래스를 직접 사용 하지 않아도에 모든 이벤트를 방금 routs는 `CCustomInterpolator`-파생 클래스를 가진 포인터의 생성자에 전달 됩니다 `CCustomTransition`합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationInterpolatorBase`  
  
 `CInterpolatorBase`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="cinterpolatorbase"></a>  CInterpolatorBase::CInterpolatorBase  
 CInterpolatorBase 개체를 만듭니다.  
  
```  
CInterpolatorBase();
```  
  
##  <a name="createinstance"></a>  CInterpolatorBase::CreateInstance  
 CInterpolatorBase의 인스턴스를 만들고 이벤트를 처리 하는 사용자 지정 보간에 대 한 포인터를 저장 합니다.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,  
    IUIAnimationInterpolator** ppHandler);
```  
  
### <a name="parameters"></a>매개 변수  
 *pInterpolator*  
 사용자 지정 보간에 대 한 포인터입니다.  
  
 *ppHandler*  
 출력입니다. 함수가 반환할 때 CInterpolatorBase의 인스턴스에 대 한 포인터를 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="getdependencies"></a>  CInterpolatorBase::GetDependencies  
 보간의 종속성을 가져옵니다.  
  
```  
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```  
  
### <a name="parameters"></a>매개 변수  
 *initialValueDependencies*  
 출력입니다. 보간의 초기 값에 종속 된 측면 SetInitialValueAndVelocity에 전달 합니다.  
  
 *initialVelocityDependencies*  
 출력입니다. 보간의 초기 속도에 종속 된 측면 SetInitialValueAndVelocity에 전달 합니다.  
  
 *durationDependencies*  
 출력입니다. 보간의 기간에 종속 된 측면 SetDuration에 전달 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다. CCustomInterpolator 설정 되지 않은 경우 또는 사용자 지정 구현을 GetDependencies 메서드에서 FALSE 반환 하는 경우에 E_FAIL을 반환 합니다.  
  
##  <a name="getduration"></a>  CInterpolatorBase::GetDuration  
 보간의 기간을 가져옵니다.  
  
```  
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```  
  
### <a name="parameters"></a>매개 변수  
 *duration*  
 출력입니다. 시간 (초)에 있는 전환의 기간입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다. CCustomInterpolator 설정 되지 않은 경우 또는 사용자 지정 구현을 GetDuration 메서드에서 FALSE 반환 하는 경우에 E_FAIL을 반환 합니다.  
  
##  <a name="getfinalvalue"></a>  CInterpolatorBase::GetFinalValue  
 보간 잠재 고객 최종 값을 가져옵니다.  
  
```  
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```  
  
### <a name="parameters"></a>매개 변수  
 *값*  
 출력입니다. 전환의 끝에 변수의 최종 값입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다. CCustomInterpolator 설정 되지 않은 경우 또는 사용자 지정 구현을 GetFinalValue 메서드에서 FALSE 반환 하는 경우에 E_FAIL을 반환 합니다.  
  
##  <a name="interpolatevalue"></a>  CInterpolatorBase::InterpolateValue  
 지정된 된 오프셋 위치에서 값을 보간합니다.  
  
```  
IFACEMETHOD(InterpolateValue)(
  __in UI_ANIMATION_SECONDS offset, 
  __out DOUBLE* value);
```  
  
### <a name="parameters"></a>매개 변수  
 *offset*  
 전환의 시작 오프셋입니다. 오프셋은 항상 보다 큰 또는 0과 같은 하며 전환의 기간 보다 작아야 합니다. 전환의 기간은 0 경우에이 메서드가 호출 되지 않습니다.  
  
 *값*  
 출력입니다. 보간된 값입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다. CCustomInterpolator 설정 되지 않은 경우 또는 사용자 지정 구현을 InterpolateValue 메서드에서 FALSE 반환 하는 경우에 E_FAIL을 반환 합니다.  
  
##  <a name="interpolatevelocity"></a>  CInterpolatorBase::InterpolateVelocity  
 지정된 된 오프셋에 속도를 보간합니다.  
  
```  
IFACEMETHOD(InterpolateVelocity)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* velocity);
```  
  
### <a name="parameters"></a>매개 변수  
 *offset*  
 전환의 시작 오프셋입니다. 오프셋은 항상 0 보다 크거나 및 전환의 기간입니다. 전환의 기간은 0 경우에이 메서드가 호출 되지 않습니다.  
  
 *개발 속도*  
 출력입니다. 속도 오프셋에 있는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다. CCustomInterpolator 설정 되지 않은 경우 또는 사용자 지정 구현을 InterpolateVelocity 메서드에서 FALSE 반환 하는 경우에 E_FAIL을 반환 합니다.  
  
##  <a name="setcustominterpolator"></a>  CInterpolatorBase::SetCustomInterpolator  
 이벤트를 처리 하는 사용자 지정 보간에 대 한 포인터를 저장 합니다.  
  
```  
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```  
  
### <a name="parameters"></a>매개 변수  
 *pInterpolator*  
 사용자 지정 보간에 대 한 포인터입니다.  
  
##  <a name="setduration"></a>  CInterpolatorBase::SetDuration  
 보간의 기간을 설정합니다.  
  
```  
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>매개 변수  
 *duration*  
 전환의 기간입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다. CCustomInterpolator 설정 되지 않은 경우 또는 사용자 지정 구현을 SetDuration 메서드에서 FALSE 반환 하는 경우에 E_FAIL을 반환 합니다.  
  
##  <a name="setinitialvalueandvelocity"></a>  CInterpolatorBase::SetInitialValueAndVelocity  
 보간의 초기 값 및 개발 속도 설정합니다.  
  
```  
IFACEMETHOD(SetInitialValueAndVelocity)(
  __in DOUBLE initialValue, 
  __in DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>매개 변수  
 *초기 값*  
 전환의 시작 부분에 변수의 값입니다.  
  
 *initialVelocity*  
 전환의 시작에 변수의 속도입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다. CCustomInterpolator 설정 되지 않은 경우 또는 사용자 지정 구현을 SetInitialValueAndVelocity 메서드에서 FALSE 반환 하는 경우에 E_FAIL을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
