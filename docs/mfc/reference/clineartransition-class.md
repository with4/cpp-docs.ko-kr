---
title: "CLinearTransition 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition::CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition::Create
- AFXANIMATIONCONTROLLER/CLinearTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CLinearTransition::m_duration
dev_langs:
- C++
helpviewer_keywords:
- CLinearTransition class
ms.assetid: 7fcb2dba-beb8-4933-9f5d-3b7fb1585ef0
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
ms.openlocfilehash: c39a3961600401f47f2f38d1a0cd735b1237813f
ms.lasthandoff: 02/24/2017

---
# <a name="clineartransition-class"></a>CLinearTransition 클래스
선형 전환을 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CLinearTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CLinearTransition::CLinearTransition](#clineartransition)|선형 전환을 개체를 생성 하 고 기간 및 최종 값으로 초기화 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CLinearTransition::Create](#create)|캡슐화 된 전환 COM 개체를 만드는 전환 라이브러리를 호출 합니다. (재정의 [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CLinearTransition::m_dblFinalValue](#m_dblfinalvalue)|전환의 끝에 있는 애니메이션 변수의 값입니다.|  
|[CLinearTransition::m_duration](#m_duration)|전환의 기간입니다.|  
  
## <a name="remarks"></a>주의  
 선형 전환 하는 동안 애니메이션 변수의 값 선형적으로 전환 초기 값에서 지정 된 마지막 값입니다. 전환 되는 모든 자동으로 지워집니다 것이 좋습니다 하 고 할당 된 새 연산자를 사용 하 여 합니다. 캡슐화 IUIAnimationTransition COM 개체는 NULL이 될 때까지 CAnimationController::AnimateGroup, 하 여 생성 됩니다. 이 COM 개체의 생성에 영향을 주지 않습니다 후 멤버 변수를 변경 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CLinearTransition](../../mfc/reference/clineartransition-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="clineartransition"></a>CLinearTransition::CLinearTransition  
 선형 전환을 개체를 생성 하 고 기간 및 최종 값으로 초기화 합니다.  
  
```  
CLinearTransition(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE dblFinalValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `duration`  
 전환의 기간입니다.  
  
 `dblFinalValue`  
 전환의 끝에 있는 애니메이션 변수의 값입니다.  
  
##  <a name="create"></a>CLinearTransition::Create  
 캡슐화 된 전환 COM 개체를 만드는 전환 라이브러리를 호출 합니다.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>매개 변수  
`pLibrary`  
 에 대 한 포인터는 [IUIAnimationTransitionLibrary 인터페이스](https://msdn.microsoft.com/library/windows/desktop/dd371897), 표준 전환의 라이브러리를 정의 하는 합니다.  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 전환을 만들었습니다. 그렇지 않으면 FALSE입니다.  
  
##  <a name="m_dblfinalvalue"></a>CLinearTransition::m_dblFinalValue  
 전환의 끝에 있는 애니메이션 변수의 값입니다.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="m_duration"></a>CLinearTransition::m_duration  
 전환의 기간입니다.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

