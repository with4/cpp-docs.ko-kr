---
title: CAnimationVariable 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationVariable::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::Create
- AFXANIMATIONCONTROLLER/CAnimationVariable::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_dblDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_lstTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_pParentObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_variable
dev_langs:
- C++
helpviewer_keywords:
- CAnimationVariable [MFC], CAnimationVariable
- CAnimationVariable [MFC], AddTransition
- CAnimationVariable [MFC], ApplyTransitions
- CAnimationVariable [MFC], ClearTransitions
- CAnimationVariable [MFC], Create
- CAnimationVariable [MFC], CreateTransitions
- CAnimationVariable [MFC], EnableIntegerValueChangedEvent
- CAnimationVariable [MFC], EnableValueChangedEvent
- CAnimationVariable [MFC], GetDefaultValue
- CAnimationVariable [MFC], GetParentAnimationObject
- CAnimationVariable [MFC], GetValue
- CAnimationVariable [MFC], GetVariable
- CAnimationVariable [MFC], SetDefaultValue
- CAnimationVariable [MFC], SetParentAnimationObject
- CAnimationVariable [MFC], m_bAutodestroyTransitions
- CAnimationVariable [MFC], m_dblDefaultValue
- CAnimationVariable [MFC], m_lstTransitions
- CAnimationVariable [MFC], m_pParentObject
- CAnimationVariable [MFC], m_variable
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 207adbba4635b80ba7b60af53f920b1af376e93d
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957301"
---
# <a name="canimationvariable-class"></a>CAnimationVariable 클래스
애니메이션 변수를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CAnimationVariable;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationVariable::CAnimationVariable](#canimationvariable)|애니메이션 변수 개체를 생성 합니다.|  
|[CAnimationVariable:: ~ CAnimationVariable](#canimationvariable__~canimationvariable)|소멸자입니다. CAnimationVariable 개체가 소멸 될 때 호출 됩니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationVariable::AddTransition](#addtransition)|전환을 추가 합니다.|  
|[CAnimationVariable::ApplyTransitions](#applytransitions)|스토리 보드에 내부 목록에서 전환을 추가 합니다.|  
|[CAnimationVariable::ClearTransitions](#cleartransitions)|전환을 지웁니다.|  
|[CAnimationVariable::Create](#create)|기본 애니메이션 변수 COM 개체를 만듭니다.|  
|[CAnimationVariable::CreateTransitions](#createtransitions)|이 애니메이션 변수에 적용 될 모든 전환을 만듭니다.|  
|[CAnimationVariable::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|사용 하거나 IntegerValueChanged 이벤트를 사용 하지 않도록 설정 합니다.|  
|[CAnimationVariable::EnableValueChangedEvent](#enablevaluechangedevent)|사용 하거나 경우 재정의 사용 하지 않도록 설정 합니다.|  
|[CAnimationVariable::GetDefaultValue](#getdefaultvalue)|기본값을 반환합니다.|  
|[CAnimationVariable::GetParentAnimationObject](#getparentanimationobject)|부모를 반환 애니메이션 개체입니다.|  
|[CAnimationVariable::GetValue](#getvalue)|오버로드됨. 애니메이션 변수의 현재 값을 반환합니다.|  
|[CAnimationVariable::GetVariable](#getvariable)|IUIAnimationVariable COM 개체에 대 한 포인터를 반환합니다.|  
|[CAnimationVariable::SetDefaultValue](#setdefaultvalue)|기본값을 설정 하 고 IUIAnimationVariable COM 개체를 해제 합니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationVariable::SetParentAnimationObject](#setparentanimationobject)|애니메이션 변수 및 애니메이션 개체 간의 관계를 설정합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationVariable::m_bAutodestroyTransitions](#m_bautodestroytransitions)|관련 된 전환을 개체를 삭제할지 여부를 지정 합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[CAnimationVariable::m_dblDefaultValue](#m_dbldefaultvalue)|IUIAnimationVariable로 전파 되는 기본값을 지정 합니다.|  
|[CAnimationVariable::m_lstTransitions](#m_lsttransitions)|이 애니메이션 변수 애니메이션 효과 적용 하는 전환 목록을 포함 합니다.|  
|[CAnimationVariable::m_pParentObject](#m_pparentobject)|이 애니메이션 변수를 캡슐화 하는 애니메이션 개체에 대 한 포인터입니다.|  
|[CAnimationVariable::m_variable](#m_variable)|IUIAnimationVariable COM 개체에 대 한 포인터를 저장합니다. COM 개체에 아직 생성 되지 않았거나 만들지 못한 NULL입니다.|  
  
## <a name="remarks"></a>설명  
 CAnimationVariable 클래스 IUIAnimationVariable COM 개체를 캡슐화합니다. 스토리 보드에서 애니메이션 변수에 적용 될 전환 목록을 저장 합니다. CAnimationVariable 개체는 응용 프로그램 애니메이션된 값, 포인트, 크기, 색 및 사각형에 나타낼 수 있는 애니메이션 개체에 포함 됩니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CAnimationVariable`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationvariable"></a>  CAnimationVariable:: ~ CAnimationVariable  
 소멸자입니다. CAnimationVariable 개체가 소멸 될 때 호출 됩니다.  
  
```  
virtual ~CAnimationVariable();
```  
  
##  <a name="addtransition"></a>  CAnimationVariable::AddTransition  
 전환을 추가 합니다.  
  
```  
void AddTransition(CBaseTransition* pTransition);
```  
  
### <a name="parameters"></a>매개 변수  
 *pTransition*  
 추가할 전환에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 애니메이션 변수에 적용할 변환의 내부 목록에 전환을 추가 하려면이 메서드는 합니다. 이 목록은 애니메이션 예약 된 경우 지워야 합니다.  
  
##  <a name="applytransitions"></a>  CAnimationVariable::ApplyTransitions  
 스토리 보드에 내부 목록에서 전환을 추가 합니다.  
  
```  
void ApplyTransitions(
    CAnimationController* pController,  
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>매개 변수  
 *pController*  
 부모 애니메이션 컨트롤러에 대 한 포인터입니다.  
  
 *pStoryboard*  
 스토리 보드에 대 한 포인터입니다.  
  
 *bDependOnKeyframes*  
 이 메서드는 키 프레임에 종속 되는 전환을 추가 해야 하는 경우 TRUE입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 스토리 보드에 내부 목록에서 전환을 추가 합니다. 호출 될 최상위 수준 코드에서 여러 번 전환을 사용 하 여 키 프레임에 따라 달라 집니다 전환 키 프레임에 의존 하는 추가 추가 합니다. 애니메이션 변수 기본 COM 개체를 만들지 않은 경우이 메서드가이 단계에서 만듭니다.  
  
##  <a name="canimationvariable"></a>  CAnimationVariable::CAnimationVariable  
 애니메이션 변수 개체를 생성 합니다.  
  
```  
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```  
  
### <a name="parameters"></a>매개 변수  
 *dblDefaultValue*  
 기본값을 지정합니다.  
  
### <a name="remarks"></a>설명  
 애니메이션 변수 개체를 생성 하 고 기본값을 설정 합니다. 기본 값에는 변수 움직이지 않으면 또는 애니메이션을 적용할 수 없을 때 사용 됩니다.  
  
##  <a name="cleartransitions"></a>  CAnimationVariable::ClearTransitions  
 전환을 지웁니다.  
  
```  
void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>매개 변수  
 *bAutodestroy*  
 이 메서드 변환 개체를 삭제 해야 하는지 여부를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 모든 전환을 전환의 내부 목록에서 제거합니다. BAutodestroy TRUE, 또는 m_bAutodestroyTransitions은 TRUE, 전환 삭제 됩니다. 그렇지 않은 경우 호출자에 게 전환 개체 할당을 취소 해야 합니다.  
  
##  <a name="create"></a>  CAnimationVariable::Create  
 기본 애니메이션 변수 COM 개체를 만듭니다.  
  
```  
virtual BOOL Create(IUIAnimationManager* pManager);
```  
  
### <a name="parameters"></a>매개 변수  
 *pManager*  
 애니메이션 관리자에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 애니메이션 변수 성공적으로 만들었습니다. 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드 내부 애니메이션 변수 COM 개체를 만들고 기본값을 설정 합니다.  
  
##  <a name="createtransitions"></a>  CAnimationVariable::CreateTransitions  
 이 애니메이션 변수에 적용 될 모든 전환을 만듭니다.  
  
```  
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>매개 변수  
*pLibrary*  
 에 대 한 포인터는 [IUIAnimationTransitionLibrary 인터페이스](https://msdn.microsoft.com/library/windows/desktop/dd371897), 표준 전환의 라이브러리를 정의 하는 합니다.  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 전환; 성공적으로 만들어졌습니다. 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전환의 변수의 내부 목록에 추가 된 전환 해야 할 때 프레임 워크에서 호출 됩니다.  
  
##  <a name="enableintegervaluechangedevent"></a>  CAnimationVariable::EnableIntegerValueChangedEvent  
 사용 하거나 IntegerValueChanged 이벤트를 사용 하지 않도록 설정 합니다.  
  
```  
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>매개 변수  
 *pController*  
 부모 컨트롤러에 대 한 포인터입니다.  
  
 *bEnable*  
 TRUE-이벤트를 이벤트 사용 안 함-FALSE를 설정 합니다.  
  
### <a name="remarks"></a>설명  
 필요한 경우 재정의 사용 하는 프레임 워크 CAnimationController::OnAnimationIntegerValueChanged 가상 메서드를 호출 합니다. 이 이벤트를 처리 하기 위해 CAnimationController에서 파생 된 클래스에서 재정의 해야 합니다. 이 메서드는 애니메이션 변수의 정수 값이 변경 될 때마다 호출 됩니다.  
  
##  <a name="enablevaluechangedevent"></a>  CAnimationVariable::EnableValueChangedEvent  
 사용 하거나 경우 재정의 사용 하지 않도록 설정 합니다.  
  
```  
void EnableValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>매개 변수  
 *pController*  
 부모 컨트롤러에 대 한 포인터입니다.  
  
 *bEnable*  
 TRUE-이벤트를 이벤트 사용 안 함-FALSE를 설정 합니다.  
  
### <a name="remarks"></a>설명  
 필요한 경우 재정의 사용 하는 프레임 워크 CAnimationController::OnAnimationValueChanged 가상 메서드를 호출 합니다. 이 이벤트를 처리 하기 위해 CAnimationController에서 파생 된 클래스에서 재정의 해야 합니다. 이 메서드는 애니메이션 변수의 값이 변경 될 때마다 호출 됩니다.  
  
##  <a name="getdefaultvalue"></a>  CAnimationVariable::GetDefaultValue  
 기본값을 반환합니다.  
  
```  
DOUBLE GetDefaultValue() const;  
```  
  
### <a name="return-value"></a>반환 값  
 기본값입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 애니메이션 변수의 기본값을 얻습니다. 생성자에서 나 SetDefaultValue 방법에는 기본값을 설정할 수 있습니다.  
  
##  <a name="getparentanimationobject"></a>  CAnimationVariable::GetParentAnimationObject  
 부모를 반환 애니메이션 개체입니다.  
  
```  
CAnimationBaseObject* GetParentAnimationObject();
```  
  
### <a name="return-value"></a>반환 값  
 관계가 설정 된 경우 부모 애니메이션 개체에 대 한 포인터 그렇지 않으면 NULL입니다.  
  
### <a name="remarks"></a>설명  
 부모 애니메이션 개체 (컨테이너)에 대 한 포인터를 검색 하려면이 메서드를 호출할 수 있습니다.  
  
##  <a name="getvalue"></a>  CAnimationVariable::GetValue  
 애니메이션 변수의 현재 값을 반환합니다.  
  
```  
HRESULT GetValue(DOUBLE& dblValue);  
HRESULT GetValue(INT32& nValue);
```  
  
### <a name="parameters"></a>매개 변수  
 *dblValue*  
 애니메이션 변수의 현재 값입니다.  
  
 *n 값*  
 애니메이션 변수의 현재 값입니다.  
  
### <a name="return-value"></a>반환 값  
 하면 s_ok이 고 값을 성공적으로 가져온 또는 기본 애니메이션 변수 만들어지지 않았습니다. 그렇지 않으면 HRESULT 오류 코드입니다.  
  
### <a name="remarks"></a>설명  
 애니메이션 변수의 현재 값을 검색 하려면이 메서드를 호출할 수 있습니다. 기본 COM 개체를 만들지 않은 경우 함수가 반환할 때 dblValue 기본값을 포함 됩니다.  
  
##  <a name="getvariable"></a>  CAnimationVariable::GetVariable  
 IUIAnimationVariable COM 개체에 대 한 포인터를 반환합니다.  
  
```  
IUIAnimationVariable* GetVariable();
```  
  
### <a name="return-value"></a>반환 값  
 애니메이션 변수를 만들지 못했습니다 있거나 만들 수 없는 경우에 NULL 이나 IUIAnimationVariable COM 개체에 대 한 유효한 포인터.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 내부 IUIAnimationVariable COM 개체에 액세스 하 고 필요한 경우 해당 메서드를 직접 호출 합니다.  
  
##  <a name="m_bautodestroytransitions"></a>  CAnimationVariable::m_bAutodestroyTransitions  
 관련 된 전환을 개체를 삭제할지 여부를 지정 합니다.  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
### <a name="remarks"></a>설명  
 전환의 내부 목록에서 제거 될 때 변환 개체를 강제 삭제 true 이면이 값을 설정 합니다. 이 값이 FALSE는 전환은 응용 프로그램을 호출 하 여 삭제 해야 합니다. 애니메이션을 예약한 후의 전환 목록은 항상 지워집니다. 기본값은 FALSE입니다.  
  
##  <a name="m_dbldefaultvalue"></a>  CAnimationVariable::m_dblDefaultValue  
 IUIAnimationVariable로 전파 되는 기본값을 지정 합니다.  
  
```  
DOUBLE m_dblDefaultValue;  
```  
  
##  <a name="m_lsttransitions"></a>  CAnimationVariable::m_lstTransitions  
 이 애니메이션 변수 애니메이션 효과 적용 하는 전환 목록을 포함 합니다.  
  
```  
CObList m_lstTransitions;  
```  
  
##  <a name="m_pparentobject"></a>  CAnimationVariable::m_pParentObject  
 이 애니메이션 변수를 캡슐화 하는 애니메이션 개체에 대 한 포인터입니다.  
  
```  
CAnimationBaseObject* m_pParentObject;  
```  
  
##  <a name="m_variable"></a>  CAnimationVariable::m_variable  
 IUIAnimationVariable COM 개체에 대 한 포인터를 저장합니다. COM 개체에 아직 생성 되지 않았거나 만들지 못한 NULL입니다.  
  
```  
ATL::CComPtr<IUIAnimationVariable> m_variable;  
```  
  
##  <a name="setdefaultvalue"></a>  CAnimationVariable::SetDefaultValue  
 기본값을 설정 하 고 IUIAnimationVariable COM 개체를 해제 합니다.  
  
```  
void SetDefaultValue(DOUBLE dblDefaultValue);
```  
  
### <a name="parameters"></a>매개 변수  
 *dblDefaultValue*  
 새 기본값을 지정합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 기본값을 다시 설정 합니다. 이 메서드는 해제 내부 IUIAnimationVariable COM 개체를 따라서 애니메이션 변수 다시 만들어질 때, 내부 COM 개체의 새 기본값을 가져옵니다 합니다. 애니메이션 변수를 나타내는 COM 개체를 만들지 않은 경우 또는 변수 애니메이션이 적용 되지 경우 기본값 GetValue에 의해 반환 됩니다.  
  
##  <a name="setparentanimationobject"></a>  CAnimationVariable::SetParentAnimationObject  
 애니메이션 변수 및 애니메이션 개체 간의 관계를 설정합니다.  
  
```  
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```  
  
### <a name="parameters"></a>매개 변수  
 *pParentObject*  
 이 변수를 포함 하는 애니메이션 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 내부적으로 애니메이션 변수와 캡슐화 하는 애니메이션 개체 간에 일대일 관계를 설정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
