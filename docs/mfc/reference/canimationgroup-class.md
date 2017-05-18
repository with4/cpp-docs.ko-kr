---
title: "CAnimationGroup 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::Animate
- AFXANIMATIONCONTROLLER/CAnimationGroup::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationGroup::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::Schedule
- AFXANIMATIONCONTROLLER/CAnimationGroup::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutoclearTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstKeyFrames
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pStoryboard
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pParentController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationGroup class
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a59d8a86fde68510d48e4a3398b6590b2215cbea
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="canimationgroup-class"></a>CAnimationGroup 클래스
애니메이션 스토리 보드, 애니메이션 개체 및 애니메이션을 정의 하는 전환을 결합 하는 애니메이션 그룹을 구현 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CAnimationGroup;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationGroup::CAnimationGroup](#canimationgroup)|애니메이션 그룹을 생성 합니다.|  
|[CAnimationGroup:: ~ CAnimationGroup](#canimationgroup__~canimationgroup)|소멸자입니다. 애니메이션 그룹 소멸 될 때 호출 됩니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationGroup::Animate](#animate)|그룹에 애니메이션을 적용 합니다.|  
|[CAnimationGroup::ApplyTransitions](#applytransitions)|전환 애니메이션 개체에 적용 됩니다.|  
|[CAnimationGroup::FindAnimationObject](#findanimationobject)|지정된 된 애니메이션 변수를 포함 하는 애니메이션 개체를 찾습니다.|  
|[CAnimationGroup::GetGroupID](#getgroupid)|그룹 Id를 반환합니다.|  
|[CAnimationGroup::RemoveKeyframes](#removekeyframes)|제거 하 고 필요에 따라 애니메이션 그룹에 속하는 모든 키프레임을 삭제 합니다.|  
|[CAnimationGroup::RemoveTransitions](#removetransitions)|전환 애니메이션 그룹에 속해 있는 애니메이션 개체에서 제거 합니다.|  
|[CAnimationGroup::Schedule](#schedule)|지정된 된 시간에 애니메이션을 예약합니다.|  
|[CAnimationGroup::SetAutodestroyTransitions](#setautodestroytransitions)|자동으로 그룹에 속하는 모든 애니메이션 개체 전환을 소멸 지시 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationGroup::AddKeyframes](#addkeyframes)|스토리 보드에 키 프레임을 추가 하는 도우미입니다.|  
|[CAnimationGroup::AddTransitions](#addtransitions)|스토리 보드에 전환을 추가 하는 도우미입니다.|  
|[CAnimationGroup::CreateTransitions](#createtransitions)|COM 전환 개체를 생성 하는 도우미입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationGroup::m_bAutoclearTransitions](#m_bautocleartransitions)|그룹에 속해 있는 애니메이션 개체에서 전환을 선택을 취소 하는 방법을 지정 합니다. 이 멤버는 결과가 TRUE 이면 전환 애니메이션 예약 된 경우에 자동으로 제거 됩니다. 그렇지 않으면 전환을 수동으로 제거 해야 합니다.|  
|[CAnimationGroup::m_bAutodestroyAnimationObjects](#m_bautodestroyanimationobjects)|애니메이션 개체를 소멸 하는 방법을 지정 합니다. 이 매개 변수가 TRUE 인 경우 그룹 소멸 될 때 애니메이션 개체 자동으로 소멸 됩니다. 그렇지 않으면 애니메이션 개체 수동으로 삭제 해야 합니다. 기본값은 FALSE입니다. 그룹에 속하는 모든 애니메이션 개체 new 연산자를 사용 하 여 동적으로 할당 되는 경우에이 값을 TRUE로 설정 합니다.|  
|[CAnimationGroup::m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|키 프레임을 제거 하는 방법을 지정 합니다. 모든 키프레임은 제거 되 고 삭제 합니다;이 값이 TRUE 이면 그렇지 않으면만 목록에서 제거 됩니다. 기본값은 TRUE입니다.|  
|[CAnimationGroup::m_lstAnimationObjects](#m_lstanimationobjects)|애니메이션 개체의 목록이 포함 되어 있습니다.|  
|[CAnimationGroup::m_lstKeyFrames](#m_lstkeyframes)|키 프레임의 목록이 포함 되어 있습니다.|  
|[CAnimationGroup::m_pStoryboard](#m_pstoryboard)|애니메이션 스토리 보드를 가리킵니다. 이 포인터가 애니메이션에 호출한 후에 유효 합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationGroup::m_nGroupID](#m_ngroupid)|애니메이션 그룹의 고유 식별자입니다.|  
|[CAnimationGroup::m_pParentController](#m_pparentcontroller)|이 그룹이 속한 애니메이션 컨트롤러에 대 한 포인터입니다.|  
  
## <a name="remarks"></a>주의  
 애니메이션 그룹은 CAnimationController::AddAnimationObject를 사용 하 여 애니메이션 개체를 추가 하면 애니메이션 컨트롤러 (CAnimationController)에 의해 자동으로 만들어집니다. 애니메이션 그룹 애니메이션 그룹을 조작에 대 한 매개 변수로 일반적으로 사용 되는 그룹 Id로 식별 됩니다. GroupID 새 애니메이션 그룹에 추가 되 고 첫 번째 애니메이션 개체에서 가져옵니다. 캡슐화 된 애니메이션 스토리 보드 CAnimationController::AnimateGroup를 호출 하 고 공용 멤버 m_pStoryboard를 통해 액세스할 수 후에 생성 됩니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CAnimationGroup`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationgroup"></a>CAnimationGroup:: ~ CAnimationGroup  
 소멸자입니다. 애니메이션 그룹 소멸 될 때 호출 됩니다.  
  
```  
~CAnimationGroup();
```  
  
##  <a name="addkeyframes"></a>CAnimationGroup::AddKeyframes  
 스토리 보드에 키 프레임을 추가 하는 도우미입니다.  
  
```  
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStoryboard`  
 스토리 보드 COM 개체에 대 한 포인터입니다.  
  
 `bAddDeep`  
 이 메서드는 다른 키 프레임에 의존 하는 스토리 보드 키 프레임 추가 해야 하는지 여부를 지정 합니다.  
  
##  <a name="addtransitions"></a>CAnimationGroup::AddTransitions  
 스토리 보드에 전환을 추가 하는 도우미입니다.  
  
```  
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStoryboard`  
 스토리 보드 COM 개체에 대 한 포인터입니다.  
  
 `bDependOnKeyframes`  
  
##  <a name="animate"></a>CAnimationGroup::Animate  
 그룹에 애니메이션을 적용 합니다.  
  
```  
BOOL Animate(
    IUIAnimationManager* pManager,  
    IUIAnimationTimer* pTimer,  
    BOOL bScheduleNow);
```  
  
### <a name="parameters"></a>매개 변수  
 `pManager`  
 `pTimer`  
 `bScheduleNow`  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 내부 스토리 보드 만듭니다 및 전환을 적용 하 고 bScheduleNow이 true 인 경우 애니메이션을 예약 합니다. BScheduleNow FALSE 인 경우 지정된 된 시간에 애니메이션을 시작 하는 일정을 호출 해야 합니다.  
  
##  <a name="applytransitions"></a>CAnimationGroup::ApplyTransitions  
 전환 애니메이션 개체에 적용 됩니다.  
  
```  
void ApplyTransitions();
```  
  
### <a name="remarks"></a>주의  
 이 메서드는 스토리 보드 생성 되지 않은 경우 디버그 모드에서 어설션 합니다. 전환 되는 모든 먼저, 다음 "정적" 키프레임 (오프셋에 종속 되는 키프레임)를 추가, 키 프레임에 종속 되지 않는 전환을 추가, 전환에 따라 및 다른 키프레임을 추가 만들고 마지막 키 프레임에 종속 된 전환을 추가 합니다.  
  
##  <a name="canimationgroup"></a>CAnimationGroup::CAnimationGroup  
 애니메이션 그룹을 생성 합니다.  
  
```  
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```  
  
### <a name="parameters"></a>매개 변수  
 `pParentController`  
 그룹을 만듭니다. 애니메이션 컨트롤러에 대 한 포인터입니다.  
  
 `nGroupID`  
 그룹 Id를 지정합니다.  
  
##  <a name="createtransitions"></a>CAnimationGroup::CreateTransitions  
 COM 전환 개체를 생성 하는 도우미입니다.  
  
```  
BOOL CreateTransitions();
```  
  
### <a name="return-value"></a>반환 값  
 TRUE는 메서드가 성공 하면, 그렇지 않으면 FALSE입니다.  
  
##  <a name="findanimationobject"></a>CAnimationGroup::FindAnimationObject  
 지정된 된 애니메이션 변수를 포함 하는 애니메이션 개체를 찾습니다.  
  
```  
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>매개 변수  
 `pVariable`  
 애니메이션 변수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 애니메이션 개체 또는 애니메이션 개체가 없는 경우 NULL 포인터입니다.  
  
##  <a name="getgroupid"></a>CAnimationGroup::GetGroupID  
 그룹 Id를 반환합니다.  
  
```  
UINT32 GetGroupID() const;  
```  
  
### <a name="return-value"></a>반환 값  
 그룹 식별자입니다.  
  
##  <a name="m_bautocleartransitions"></a>CAnimationGroup::m_bAutoclearTransitions  
 그룹에 속해 있는 애니메이션 개체에서 전환을 선택을 취소 하는 방법을 지정 합니다. 이 멤버는 결과가 TRUE 이면 전환 애니메이션 예약 된 경우에 자동으로 제거 됩니다. 그렇지 않으면 전환을 수동으로 제거 해야 합니다.  
  
```  
BOOL m_bAutoclearTransitions;  
```  
  
##  <a name="m_bautodestroyanimationobjects"></a>CAnimationGroup::m_bAutodestroyAnimationObjects  
 애니메이션 개체를 소멸 하는 방법을 지정 합니다. 이 매개 변수가 TRUE 인 경우 그룹 소멸 될 때 애니메이션 개체 자동으로 소멸 됩니다. 그렇지 않으면 애니메이션 개체 수동으로 삭제 해야 합니다. 기본값은 FALSE입니다. 그룹에 속하는 모든 애니메이션 개체 new 연산자를 사용 하 여 동적으로 할당 되는 경우에이 값을 TRUE로 설정 합니다.  
  
```  
BOOL m_bAutodestroyAnimationObjects;  
```  
  
##  <a name="m_bautodestroykeyframes"></a>CAnimationGroup::m_bAutodestroyKeyframes  
 키 프레임을 제거 하는 방법을 지정 합니다. 모든 키프레임은 제거 되 고 삭제 합니다;이 값이 TRUE 이면 그렇지 않으면만 목록에서 제거 됩니다. 기본값은 TRUE입니다.  
  
```  
BOOL m_bAutodestroyKeyframes;  
```  
  
##  <a name="m_lstanimationobjects"></a>CAnimationGroup::m_lstAnimationObjects  
 애니메이션 개체의 목록이 포함 되어 있습니다.  
  
```  
CObList m_lstAnimationObjects;  
```  
  
##  <a name="m_lstkeyframes"></a>CAnimationGroup::m_lstKeyFrames  
 키 프레임의 목록이 포함 되어 있습니다.  
  
```  
CObList m_lstKeyFrames;  
```  
  
##  <a name="m_ngroupid"></a>CAnimationGroup::m_nGroupID  
 애니메이션 그룹의 고유 식별자입니다.  
  
```  
UINT32 m_nGroupID;  
```  
  
##  <a name="m_pparentcontroller"></a>CAnimationGroup::m_pParentController  
 이 그룹이 속한 애니메이션 컨트롤러에 대 한 포인터입니다.  
  
```  
CAnimationController* m_pParentController;  
```  
  
##  <a name="m_pstoryboard"></a>CAnimationGroup::m_pStoryboard  
 애니메이션 스토리 보드를 가리킵니다. 이 포인터가 애니메이션에 호출한 후에 유효 합니다.  
  
```  
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;  
```  
  
##  <a name="removekeyframes"></a>CAnimationGroup::RemoveKeyframes  
 제거 하 고 필요에 따라 애니메이션 그룹에 속하는 모든 키프레임을 삭제 합니다.  
  
```  
void RemoveKeyframes();
```  
  
### <a name="remarks"></a>주의  
 키 프레임 제거 되며 소멸 된 후 m_bAutodestroyKeyframes 멤버가 TRUE 키프레임 키프레임 내부 목록에서 방금 제거 되는 그렇지 않은 경우.  
  
##  <a name="removetransitions"></a>CAnimationGroup::RemoveTransitions  
 전환 애니메이션 그룹에 속해 있는 애니메이션 개체에서 제거 합니다.  
  
```  
void RemoveTransitions();
```  
  
### <a name="remarks"></a>주의  
 M_bAutoclearTransitions 플래그가 TRUE로 설정 된 경우이 메서드는 그룹에 속하는 모든 애니메이션 개체를 반복 하 고 CAnimationObject::ClearTransitions(FALSE)를 호출 합니다.  
  
##  <a name="schedule"></a>CAnimationGroup::Schedule  
 지정된 된 시간에 애니메이션을 예약합니다.  
  
```  
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```  
  
### <a name="parameters"></a>매개 변수  
 `pTimer`  
 애니메이션 타이머에 대 한 포인터입니다.  
  
 `time`  
 애니메이션을 예약 하는 시간을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 FALSE는 메서드가 실패 하거나 애니메이션 하는 경우 호출 되지 않았습니다와 bScheduleNow FALSE로 설정 합니다.  
  
### <a name="remarks"></a>주의  
 지정된 된 시간에 애니메이션을 예약 하려면이 함수를 호출 합니다. BScheduleNow 먼저 FALSE로 설정 된 애니메이션을 호출 해야 합니다.  
  
##  <a name="setautodestroytransitions"></a>CAnimationGroup::SetAutodestroyTransitions  
 자동으로 그룹에 속하는 모든 애니메이션 개체 전환을 소멸 지시 합니다.  
  
```  
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bAutoDestroy`  
 전환을 소멸 하는 방법을 지정 합니다.  
  
### <a name="remarks"></a>주의  
 이 값을 전환 스택에 할당 하는 경우에 FALSE로 설정 합니다. 기본값은 TRUE, 따라서 것이 좋습니다 새 연산자를 사용 하 여 전환 개체를 할당 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

