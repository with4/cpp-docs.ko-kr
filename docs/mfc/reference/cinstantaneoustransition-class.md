---
title: CInstantaneousTransition 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CInstantaneousTransition [MFC], CInstantaneousTransition
- CInstantaneousTransition [MFC], Create
- CInstantaneousTransition [MFC], m_dblFinalValue
ms.assetid: c3d5121f-2c6b-4221-9e57-10e082a31120
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 894d782f0f896837474c24255703a60e228737ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366738"
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
|[CInstantaneousTransition::m_dblFinalValue](#m_dblfinalvalue)|전환의 끝에서 애니메이션 변수의 값입니다.|  
  
## <a name="remarks"></a>설명  
 순간 전환을 하는 동안 애니메이션 변수의 값 변경 즉시 현재 값에서 지정 된 최종 값 합니다. 이 전환 기간은 항상 0입니다. 모든 전환을 자동으로 취소 되므로 것이 좋습니다에 할당 된 새 연산자를 사용 합니다. 캡슐화 된 IUIAnimationTransition COM 개체는 NULL이 될 때까지 CAnimationController::AnimateGroup, 여 생성 됩니다. 이 COM 개체 만들기는 아무런 영향을 주지 후 멤버 변수를 변경 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CInstantaneousTransition](../../mfc/reference/cinstantaneoustransition-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="cinstantaneoustransition"></a>  CInstantaneousTransition::CInstantaneousTransition  
 전환 개체를 생성 하 고 최종 값을 초기화 합니다.  
  
```  
CInstantaneousTransition(DOUBLE dblFinalValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `dblFinalValue`  
 전환의 끝에서 애니메이션 변수의 값입니다.  
  
##  <a name="create"></a>  CInstantaneousTransition::Create  
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
  
##  <a name="m_dblfinalvalue"></a>  CInstantaneousTransition::m_dblFinalValue  
 전환의 끝에서 애니메이션 변수의 값입니다.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
