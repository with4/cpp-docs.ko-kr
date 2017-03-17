---
title: "CSinusoidalTransitionFromVelocity 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_period
dev_langs:
- C++
helpviewer_keywords:
- CSinusoidalTransitionFromVelocity class
ms.assetid: cc885f17-b84b-45ee-8f1f-36a8bbb7adad
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
ms.openlocfilehash: 035c92a807fdbe9028547472a3dc816995b95c91
ms.lasthandoff: 02/24/2017

---
# <a name="csinusoidaltransitionfromvelocity-class"></a>CSinusoidalTransitionFromVelocity 클래스
애니메이션 변수의 초기 속도에 의해 진폭이 결정되는 사인 곡선 속도 전환을 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSinusoidalTransitionFromVelocity : public CBaseTransition;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity](#csinusoidaltransitionfromvelocity)|전환 개체를 생성 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSinusoidalTransitionFromVelocity::Create](#create)|캡슐화 된 전환 COM 개체를 만드는 전환 라이브러리를 호출 합니다. (재정의 [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CSinusoidalTransitionFromVelocity::m_duration](#m_duration)|전환의 기간입니다.|  
|[CSinusoidalTransitionFromVelocity::m_period](#m_period)|기간 (초)에서 사인 곡선 물결의 진동입니다.|  
  
## <a name="remarks"></a>주의  
 애니메이션 변수 값을 사인 곡선 범위 전환의 전체 기간 동안 초기 값 주위 오고 갑니다. 전환을 시작할 때의 진폭 애니메이션 변수의 속도 의해 결정 됩니다. 전환 되는 모든 자동으로 지워집니다 것이 좋습니다 하 고 할당 된 새 연산자를 사용 하 여 합니다. 캡슐화 IUIAnimationTransition COM 개체는 NULL이 될 때까지 CAnimationController::AnimateGroup, 하 여 생성 됩니다. 이 COM 개체의 생성에 영향을 주지 않습니다 후 멤버 변수를 변경 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromVelocity](../../mfc/reference/csinusoidaltransitionfromvelocity-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="create"></a>CSinusoidalTransitionFromVelocity::Create  
 캡슐화 된 전환 COM 개체를 만드는 전환 라이브러리를 호출 합니다.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>매개 변수  
 `pLibrary`  
 표준 전환 만드는 담당 하는 전환 라이브러리에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 전환을 만들었습니다. 그렇지 않으면 FALSE입니다.  
  
##  <a name="csinusoidaltransitionfromvelocity"></a>CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity  
 전환 개체를 생성 합니다.  
  
```  
CSinusoidalTransitionFromVelocity(
    UI_ANIMATION_SECONDS duration,  
    UI_ANIMATION_SECONDS period);
```  
  
### <a name="parameters"></a>매개 변수  
 `duration`  
 전환의 기간입니다.  
  
 `period`  
 기간 (초)에서 사인 곡선 물결의 진동입니다.  
  
##  <a name="m_duration"></a>CSinusoidalTransitionFromVelocity::m_duration  
 전환의 기간입니다.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_period"></a>CSinusoidalTransitionFromVelocity::m_period  
 기간 (초)에서 사인 곡선 물결의 진동입니다.  
  
```  
UI_ANIMATION_SECONDS m_period;  
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

