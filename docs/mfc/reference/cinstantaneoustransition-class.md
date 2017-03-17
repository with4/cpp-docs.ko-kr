---
title: "CInstantaneousTransition 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::Create
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::m_dblFinalValue
dev_langs:
- C++
helpviewer_keywords:
- CInstantaneousTransition class
ms.assetid: c3d5121f-2c6b-4221-9e57-10e082a31120
caps.latest.revision: 17
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
ms.openlocfilehash: d0d6d4bee051222bec4333f486f493c2feeda9d6
ms.lasthandoff: 02/24/2017

---
# <a name="cinstantaneoustransition-class"></a>CInstantaneousTransition 클래스
순간 전환을 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CInstantaneousTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CInstantaneousTransition::CInstantaneousTransition](#cinstantaneoustransition)|전환 개체를 생성 하 고 최종 값을 초기화 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CInstantaneousTransition::Create](#create)|캡슐화 된 전환 COM 개체를 만드는 전환 라이브러리를 호출 합니다. (재정의 [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CInstantaneousTransition::m_dblFinalValue](#m_dblfinalvalue)|전환의 끝에 있는 애니메이션 변수의 값입니다.|  
  
## <a name="remarks"></a>주의  
 순간 전환 하는 동안 애니메이션 변수 값을 즉시 현재 값에서는 지정 된 최종 값으로 변경 합니다. 이 전환 기간은 항상&0;입니다. 전환 되는 모든 자동으로 지워집니다 것이 좋습니다 하 고 할당 된 새 연산자를 사용 하 여 합니다. 캡슐화 IUIAnimationTransition COM 개체는 NULL이 될 때까지 CAnimationController::AnimateGroup, 하 여 생성 됩니다. 이 COM 개체의 생성에 영향을 주지 않습니다 후 멤버 변수를 변경 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CInstantaneousTransition](../../mfc/reference/cinstantaneoustransition-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="cinstantaneoustransition"></a>CInstantaneousTransition::CInstantaneousTransition  
 전환 개체를 생성 하 고 최종 값을 초기화 합니다.  
  
```  
CInstantaneousTransition(DOUBLE dblFinalValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `dblFinalValue`  
 전환의 끝에 있는 애니메이션 변수의 값입니다.  
  
##  <a name="create"></a>CInstantaneousTransition::Create  
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
  
##  <a name="m_dblfinalvalue"></a>CInstantaneousTransition::m_dblFinalValue  
 전환의 끝에 있는 애니메이션 변수의 값입니다.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

