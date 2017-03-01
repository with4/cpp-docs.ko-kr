---
title: "CSinusoidalTransitionFromRange 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxanimationcontroller/CSinusoidalTransitionFromRange
- CSinusoidalTransitionFromRange
dev_langs:
- C++
helpviewer_keywords:
- CSinusoidalTransitionFromRange class
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
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
ms.openlocfilehash: f9dd0e236207c0b4139de42f4c616aaad9dcad28
ms.lasthandoff: 02/24/2017

---
# <a name="csinusoidaltransitionfromrange-class"></a>CSinusoidalTransitionFromRange 클래스
진동 범위가 지정된 사인 곡선 범위 전환을 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSinusoidalTransitionFromRange : public CBaseTransition;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange](#csinusoidaltransitionfromrange)|전환 개체를 생성 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::Create](#create)|캡슐화 된 전환 COM 개체를 만드는 전환 라이브러리를 호출 합니다. (재정의 [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::m_dblMaximumValue](#m_dblmaximumvalue)|사인 곡선 물결의 최고에서 애니메이션 변수의 값입니다.|  
|[CSinusoidalTransitionFromRange::m_dblMinimumValue](#m_dblminimumvalue)|사인 곡선 물결의 이러한에서 애니메이션 변수의 값입니다.|  
|[CSinusoidalTransitionFromRange::m_duration](#m_duration)|전환의 기간입니다.|  
|[CSinusoidalTransitionFromRange::m_period](#m_period)|기간 (초)에서 사인 곡선 물결의 진동입니다.|  
|[CSinusoidalTransitionFromRange::m_slope](#m_slope)|전환의 시작 부분에 기울기입니다.|  
  
## <a name="remarks"></a>주의  
 애니메이션 변수 값을 사인 곡선 범위 전환의 전체 기간 동안 지정된 된 최소 및 최대 값 사이 변화 합니다. 기울기 매개 변수는 다른 매개 변수에 의해 지정 된 두 개의 가능한 사인 파형을 구분 하기 위해 사용 됩니다. 전환 되는 모든 자동으로 지워집니다 것이 좋습니다 하 고 할당 된 새 연산자를 사용 하 여 합니다. 캡슐화 IUIAnimationTransition COM 개체는 NULL이 될 때까지 CAnimationController::AnimateGroup, 하 여 생성 됩니다. 이 COM 개체의 생성에 영향을 주지 않습니다 후 멤버 변수를 변경 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromRange](../../mfc/reference/csinusoidaltransitionfromrange-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="a-namecreatea--csinusoidaltransitionfromrangecreate"></a><a name="create"></a>CSinusoidalTransitionFromRange::Create  
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
  
##  <a name="a-namecsinusoidaltransitionfromrangea--csinusoidaltransitionfromrangecsinusoidaltransitionfromrange"></a><a name="csinusoidaltransitionfromrange"></a>CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange  
 전환 개체를 생성 합니다.  
  
```  
CSinusoidalTransitionFromRange(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE dblMinimumValue,  
    DOUBLE dblMaximumValue,  
    UI_ANIMATION_SECONDS period,  
    UI_ANIMATION_SLOPE slope);
```  
  
### <a name="parameters"></a>매개 변수  
 `duration`  
 전환의 기간입니다.  
  
 `dblMinimumValue`  
 사인 곡선 물결의 이러한에서 애니메이션 변수의 값입니다.  
  
 `dblMaximumValue`  
 사인 곡선 물결의 최고에서 애니메이션 변수의 값입니다.  
  
 `period`  
 기간 (초)에서 사인 곡선 물결의 진동입니다.  
  
 `slope`  
 전환의 시작 부분에 기울기입니다.  
  
##  <a name="a-namemdblmaximumvaluea--csinusoidaltransitionfromrangemdblmaximumvalue"></a><a name="m_dblmaximumvalue"></a>CSinusoidalTransitionFromRange::m_dblMaximumValue  
 사인 곡선 물결의 최고에서 애니메이션 변수의 값입니다.  
  
```  
DOUBLE m_dblMaximumValue;  
```  
  
##  <a name="a-namemdblminimumvaluea--csinusoidaltransitionfromrangemdblminimumvalue"></a><a name="m_dblminimumvalue"></a>CSinusoidalTransitionFromRange::m_dblMinimumValue  
 사인 곡선 물결의 이러한에서 애니메이션 변수의 값입니다.  
  
```  
DOUBLE m_dblMinimumValue;  
```  
  
##  <a name="a-namemdurationa--csinusoidaltransitionfromrangemduration"></a><a name="m_duration"></a>CSinusoidalTransitionFromRange::m_duration  
 전환의 기간입니다.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="a-namemperioda--csinusoidaltransitionfromrangemperiod"></a><a name="m_period"></a>CSinusoidalTransitionFromRange::m_period  
 기간 (초)에서 사인 곡선 물결의 진동입니다.  
  
```  
UI_ANIMATION_SECONDS m_period;  
```  
  
##  <a name="a-namemslopea--csinusoidaltransitionfromrangemslope"></a><a name="m_slope"></a>CSinusoidalTransitionFromRange::m_slope  
 전환의 시작 부분에 기울기입니다.  
  
```  
UI_ANIMATION_SLOPE m_slope;  
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

