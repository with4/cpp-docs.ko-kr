---
title: "CBaseTransition 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboardAtKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::Clear
- AFXANIMATIONCONTROLLER/CBaseTransition::Create
- AFXANIMATIONCONTROLLER/CBaseTransition::GetEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::GetStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::GetType
- AFXANIMATIONCONTROLLER/CBaseTransition::IsAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::SetKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::SetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_transition
- AFXANIMATIONCONTROLLER/CBaseTransition::m_type
dev_langs:
- C++
helpviewer_keywords:
- CBaseTransition class
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
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
ms.openlocfilehash: b979d03587ada42486d0462733dfe6fd22f9f7cc
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cbasetransition-class"></a>CBaseTransition 클래스
기본 전환을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CBaseTransition : public CObject;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-enumerations"></a>public 열거형  
  
|이름|설명|  
|----------|-----------------|  
|[CBaseTransition::TRANSITION_TYPE 열거형](#transition_type_enumeration)|현재 Windows 애니메이션 API의 MFC 구현에서 지 원하는 전환 유형을 정의 합니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CBaseTransition::CBaseTransition](#cbasetransition)|기본 전환 개체를 생성합니다.|  
|[CBaseTransition:: ~ CBaseTransition](#cbasetransition__~cbasetransition)|소멸자입니다. 전환 개체가 소멸 될 때 호출 됩니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CBaseTransition::AddToStoryboard](#addtostoryboard)|전환을 스토리 보드에 추가 합니다.|  
|[CBaseTransition::AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|전환을 스토리 보드에 추가 합니다.|  
|[CBaseTransition::Clear](#clear)|릴리스는 IUIAnimationTransition COM 개체를 캡슐화 합니다.|  
|[CBaseTransition::Create](#create)|COM 전환을 만듭니다.|  
|[CBaseTransition::GetEndKeyframe](#getendkeyframe)|시작 키 프레임을 반환 합니다.|  
|[CBaseTransition::GetRelatedVariable](#getrelatedvariable)|관련 된 변수에 대 한 포인터를 반환합니다.|  
|[CBaseTransition::GetStartKeyframe](#getstartkeyframe)|시작 키 프레임을 반환 합니다.|  
|[CBaseTransition::GetTransition](#gettransition)|오버로드됨. 기본 COM 전환 개체에 대 한 포인터를 반환합니다.|  
|[CBaseTransition::GetType](#gettype)|반환 형식으로 전환 되었습니다.|  
|[CBaseTransition::IsAdded](#isadded)|전환을 스토리 보드에 추가 되어 있는지 알려 줍니다.|  
|[CBaseTransition::SetKeyframes](#setkeyframes)|전환에 대 한 키 프레임을 설정합니다.|  
|[CBaseTransition::SetRelatedVariable](#setrelatedvariable)|애니메이션 변수 및 전환 사이의 관계를 설정 합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CBaseTransition::m_bAdded](#m_badded)|전환을 스토리 보드에 추가 되어 있는지를 지정 합니다.|  
|[CBaseTransition::m_pEndKeyframe](#m_pendkeyframe)|전환의 끝을 지정 하는 키 프레임에 대 한 포인터를 저장 합니다.|  
|[CBaseTransition::m_pRelatedVariable](#m_prelatedvariable)|M_transition에 저장 된 전환 애니메이션을 적용 하는 애니메이션 변수에 대 한 포인터입니다.|  
|[CBaseTransition::m_pStartKeyframe](#m_pstartkeyframe)|전환의 시작을 지정 하는 키 프레임에 대 한 포인터를 저장 합니다.|  
|[CBaseTransition::m_transition](#m_transition)|IUIAnimationTransition에 대 한 포인터를 저장합니다. COM 전환 개체 생성 되지 않은 경우 NULL입니다.|  
|[CBaseTransition::m_type](#m_type)|변환 유형을 저장합니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 IUIAnimationTransition 인터페이스를 캡슐화 하 고 모든 전환에 대 한 기본 클래스 역할을 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CBaseTransition`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="_dtorcbasetransition"></a>CBaseTransition:: ~ CBaseTransition  
 소멸자입니다. 전환 개체가 소멸 될 때 호출 됩니다.  
  
```  
virtual ~CBaseTransition();
```  
  
##  <a name="addtostoryboard"></a>CBaseTransition::AddToStoryboard  
 전환을 스토리 보드에 추가 합니다.  
  
```  
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStoryboard`  
 관련된 된 변수에 애니메이션 효과 적용할 스토리 보드에 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 TRUE로 전환 스토리 보드에 추가 했습니다.  
  
### <a name="remarks"></a>주의  
 스토리 보드에 있는 관련 변수에 전환을 적용합니다. 이 스토리 보드에서이 변수에 적용 된 첫 번째 전환 인 경우 전환이 스토리 보드의 시작 부분에서 시작 합니다. 그렇지 않으면 전환 변수의 가장 최근에 추가 된 전환에 추가 됩니다.  
  
##  <a name="addtostoryboardatkeyframes"></a>CBaseTransition::AddToStoryboardAtKeyframes  
 전환을 스토리 보드에 추가 합니다.  
  
```  
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStoryboard`  
 관련된 된 변수에 애니메이션 효과 적용할 스토리 보드에 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 TRUE로 전환 스토리 보드에 추가 했습니다.  
  
### <a name="remarks"></a>주의  
 스토리 보드에 있는 관련 변수에 전환을 적용합니다. 시작 키 프레임을 지정 하는 경우 해당 키 프레임에서 전환을 시작 합니다. End 키 프레임을 지정 하는 경우 전환 시작 키 프레임에서 시작 및 끝 키 프레임에서 중단 합니다. 전환을 지정 된 기간 매개 변수를 만든 경우 해당 시간 기간 시작 및 종료 키 프레임 간격을 덮어씁니다. 없는 키 프레임을 지정 하는 경우 전환이 변수의 가장 최근에 추가 된 전환에 추가 됩니다.  
  
##  <a name="cbasetransition"></a>CBaseTransition::CBaseTransition  
 기본 전환 개체를 생성합니다.  
  
```  
CBaseTransition();
```  
  
##  <a name="clear"></a>CBaseTransition::Clear  
 릴리스는 IUIAnimationTransition COM 개체를 캡슐화 합니다.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>주의  
 이 메서드는 파생된 클래스의 Create 메서드에서 IUITransition 인터페이스 누수를 방지 하기 위해 호출 되어야 합니다.  
  
##  <a name="create"></a>CBaseTransition::Create  
 COM 전환을 만듭니다.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* pFactory) = 0;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pLibrary`  
 전환 라이브러리를 만드는 표준 전환에 대 한 포인터입니다. 사용자 지정 전환을 NULL이 될 수 있습니다.  
  
 `pFactory`  
 사용자 지정 전환을 만드는 전환 팩토리에 대 한 포인터입니다. 표준 전환에 대 한 NULL 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 전환 COM 개체를 만들었습니다. 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 파생된 클래스에서 재정의 해야 하는 순수 가상 함수입니다. 기본 COM 전환 개체를 인스턴스화하 려는 프레임 워크에서 호출 됩니다.  
  
##  <a name="getendkeyframe"></a>CBaseTransition::GetEndKeyframe  
 시작 키 프레임을 반환 합니다.  
  
```  
CBaseKeyFrame* GetEndKeyframe();
```  
  
### <a name="return-value"></a>반환 값  
 유효한 포인터를 키프레임 또는 전환 키 프레임 간에 삽입 해야 하는 경우에 NULL입니다.  
  
### <a name="remarks"></a>주의  
 Setkeyframes에 의해 이전에 설정 된 키 프레임 개체에 액세스 하려면이 메서드를 사용할 수 있습니다. 최상위 수준 코드에서 전환 스토리 보드에 추가 될 때 호출 됩니다.  
  
##  <a name="getrelatedvariable"></a>CBaseTransition::GetRelatedVariable  
 관련 된 변수에 대 한 포인터를 반환합니다.  
  
```  
CAnimationVariable* GetRelatedVariable();
```  
  
### <a name="return-value"></a>반환 값  
 애니메이션 변수 또는 애니메이션 변수 SetRelatedVariable로 설정 되지 않은 경우 NULL을 유효한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 관련 된 애니메이션 변수에 대 한 접근자입니다.  
  
##  <a name="getstartkeyframe"></a>CBaseTransition::GetStartKeyframe  
 시작 키 프레임을 반환 합니다.  
  
```  
CBaseKeyFrame* GetStartKeyframe();
```  
  
### <a name="return-value"></a>반환 값  
 유효한 포인터를 키프레임 또는 키프레임 뒤의 전환을 시작 하지 않아야 하는 경우에 NULL입니다.  
  
### <a name="remarks"></a>주의  
 Setkeyframes에 의해 이전에 설정 된 키 프레임 개체에 액세스 하려면이 메서드를 사용할 수 있습니다. 최상위 수준 코드에서 전환 스토리 보드에 추가 될 때 호출 됩니다.  
  
##  <a name="gettransition"></a>CBaseTransition::GetTransition  
 기본 COM 전환 개체에 대 한 포인터를 반환합니다.  
  
```  
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* pFactory);  
  
IUIAnimationTransition* GetTransition();
```  
  
### <a name="parameters"></a>매개 변수  
 `pLibrary`  
 전환 라이브러리를 만드는 표준 전환에 대 한 포인터입니다. 사용자 지정 전환을 NULL이 될 수 있습니다.  
  
 `pFactory`  
 사용자 지정 전환을 만드는 전환 팩토리에 대 한 포인터입니다. 표준 전환에 대 한 NULL 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 IUIAnimationTransition 또는 내부 전환 하는 경우에 NULL에 대 한 유효한 포인터를 만들 수 없습니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 기본 COM 전환 개체에 대 한 포인터를 반환 하 고 필요한 경우 만듭니다.  
  
##  <a name="gettype"></a>CBaseTransition::GetType  
 반환 형식으로 전환 되었습니다.  
  
```  
TRANSITION_TYPE GetType() const;  
```  
  
### <a name="return-value"></a>반환 값  
 값 열거 TRANSITION_TYPE 중 하나입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드 유형을 기준으로 전환 개체를 식별 하려면 사용할 수 있습니다. 파생된 클래스의 생성자에는 형식이 설정 됩니다.  
  
##  <a name="isadded"></a>CBaseTransition::IsAdded  
 전환을 스토리 보드에 추가 되어 있는지 알려 줍니다.  
  
```  
BOOL IsAdded();
```  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면 FALSE 스토리 보드에 전환을 추가 되었습니다 경우 TRUE를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 최상위 수준 코드를 사용 하는 스토리 보드에 전환을 추가 하는 경우이 플래그는 내부적으로 설정 됩니다.  
  
##  <a name="m_badded"></a>CBaseTransition::m_bAdded  
 전환을 스토리 보드에 추가 되어 있는지를 지정 합니다.  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="m_pendkeyframe"></a>CBaseTransition::m_pEndKeyframe  
 전환의 끝을 지정 하는 키 프레임에 대 한 포인터를 저장 합니다.  
  
```  
CBaseKeyFrame* m_pEndKeyframe;  
```  
  
##  <a name="m_prelatedvariable"></a>CBaseTransition::m_pRelatedVariable  
 M_transition에 저장 된 전환 애니메이션을 적용 하는 애니메이션 변수에 대 한 포인터입니다.  
  
```  
CAnimationVariable* m_pRelatedVariable;  
```  
  
##  <a name="m_pstartkeyframe"></a>CBaseTransition::m_pStartKeyframe  
 전환의 시작을 지정 하는 키 프레임에 대 한 포인터를 저장 합니다.  
  
```  
CBaseKeyFrame* m_pStartKeyframe;  
```  
  
##  <a name="m_transition"></a>CBaseTransition::m_transition  
 IUIAnimationTransition에 대 한 포인터를 저장합니다. COM 전환 개체 생성 되지 않은 경우 NULL입니다.  
  
```  
ATL::CComPtr<IUIAnimationTransition> m_transition;  
```  
  
##  <a name="m_type"></a>CBaseTransition::m_type  
 변환 유형을 저장합니다.  
  
```  
TRANSITION_TYPE m_type;  
```  
  
##  <a name="setkeyframes"></a>CBaseTransition::SetKeyframes  
 전환에 대 한 키 프레임을 설정합니다.  
  
```  
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,  
    CBaseKeyFrame* pEnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStart`  
 전환의 시작을 지정 하는 키 프레임입니다.  
  
 `pEnd`  
 전환의 끝을 지정 하는 키 프레임입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드의 지시에 시작 하 고 필요에 따라 보류가 NULL 인 경우 종료로 전환을 지정 된 키 프레임 전 합니다. 전환을 지정 된 기간 매개 변수를 만든 경우 해당 시간 기간 시작 및 종료 키 프레임 간격을 덮어씁니다.  
  
##  <a name="setrelatedvariable"></a>CBaseTransition::SetRelatedVariable  
 애니메이션 변수 및 전환 사이의 관계를 설정 합니다.  
  
```  
void SetRelatedVariable(CAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>매개 변수  
 `pVariable`  
 관련 된 애니메이션 변수에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 애니메이션 변수 및 전환 사이의 관계를 설정 합니다. 전환은 변수 하나에 적용할 수 있습니다.  
  
##  <a name="transition_type_enumeration"></a>CBaseTransition::TRANSITION_TYPE 열거형  
 현재 Windows 애니메이션 API의 MFC 구현에서 지 원하는 전환 유형을 정의 합니다.  
  
```  
enum TRANSITION_TYPE;  
```  
  
### <a name="remarks"></a>주의  
 변환 유형은 특정 전환의 생성자에서 설정 됩니다. 예를 들어 CSinusoidalTransitionFromRange SINUSOIDAL_FROM_RANGE 해당 유형을 설정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

