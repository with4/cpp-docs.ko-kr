---
title: CAnimationColor 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationColor [MFC], CAnimationColor
- CAnimationColor [MFC], AddTransition
- CAnimationColor [MFC], GetB
- CAnimationColor [MFC], GetDefaultValue
- CAnimationColor [MFC], GetG
- CAnimationColor [MFC], GetR
- CAnimationColor [MFC], GetValue
- CAnimationColor [MFC], SetDefaultValue
- CAnimationColor [MFC], GetAnimationVariableList
- CAnimationColor [MFC], m_bValue
- CAnimationColor [MFC], m_gValue
- CAnimationColor [MFC], m_rValue
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f564b70e850f3020956711ef15ab1fe9285a6ae4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="canimationcolor-class"></a>CAnimationColor 클래스
빨강, 녹색 및 파랑 구성 요소에 애니메이션을 적용할 수 있는 색 기능을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationColor::CAnimationColor](#canimationcolor)|오버로드됨. 애니메이션 컬러 개체를 생성 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationColor::AddTransition](#addtransition)|빨강, 녹색 및 파랑 구성 요소에 대 한 변환을 추가합니다.|  
|[CAnimationColor::GetB](#getb)|CAnimationVariable 파란색 구성 요소를 나타내는에 대 한 액세스를 제공 합니다.|  
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|색의 구성 요소에 대 한 기본 값을 반환합니다.|  
|[CAnimationColor::GetG](#getg)|CAnimationVariable 나타내는 녹색 구성 요소에 대 한 액세스를 제공 합니다.|  
|[CAnimationColor::GetR](#getr)|CAnimationVariable 나타내는 빨강 구성 요소에 대 한 액세스를 제공 합니다.|  
|[CAnimationColor::GetValue](#getvalue)|현재 값을 반환 합니다.|  
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|기본값을 설정합니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|목록에 캡슐화 된 애니메이션 변수를 추가합니다. (재정의 [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[COLORREF CAnimationColor::operator](#operator_colorref)||  
|[CAnimationColor::operator =](#operator_eq)|CAnimationColor에 색을 할당합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationColor::m_bValue](#m_bvalue)|캡슐화 된 애니메이션 변수 애니메이션 색의 파랑 구성 요소를 나타냅니다.|  
|[CAnimationColor::m_gValue](#m_gvalue)|캡슐화 된 애니메이션 변수 애니메이션 색의 녹색 구성 요소를 나타냅니다.|  
|[CAnimationColor::m_rValue](#m_rvalue)|캡슐화 된 애니메이션 변수 애니메이션 색의 빨강 구성 요소를 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 CAnimationColor 클래스 세 CAnimationVariable 개체를 캡슐화 하 고 색 응용 프로그램에 나타낼 수 있습니다. 예를 들어 화면에서 개체의 색 애니메이션 효과를 줄이 클래스를 사용할 수 있습니다 (텍스트 색상, 배경색 등). 응용 프로그램에서이 클래스를 사용 하려면 방금이 클래스의 개체를 인스턴스화할 CAnimationController::AddAnimationObject를 사용 하 여 애니메이션 컨트롤러를 추가 및 빨강, 녹색 및 파랑 구성 요소에 적용 될 각 전환에 대해 AddTransition를 호출 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationColor`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>  CAnimationColor::AddTransition  
 빨강, 녹색 및 파랑 구성 요소에 대 한 변환을 추가합니다.  
  
```  
void AddTransition(
    CBaseTransition* pRTransition,  
    CBaseTransition* pGTransition,  
    CBaseTransition* pBTransition);
```  
  
### <a name="parameters"></a>매개 변수  
 `pRTransition`  
 빨강 구성 요소에 대 한 전환 해야 합니다.  
  
 `pGTransition`  
 녹색 구성 요소에 대 한 전환 해야 합니다.  
  
 `pBTransition`  
 파랑 구성 요소에 대 한 전환 해야 합니다.  
  
### <a name="remarks"></a>설명  
 애니메이션 변수를 나타내는 색의 구성 요소에 적용할 변환의 내부 목록에 지정된 된 전환을 추가 하려면이 함수를 호출 합니다. 전환에 추가 하면 하지 즉시 적용 되며 내부 목록에 저장 합니다. 전환 (특정 값에 대 한 스토리 보드에 추가 된) 적용 CAnimationController::AnimateGroup를 호출 하는 경우. 색의 구성 요소 중 하나에 전환을 적용할 필요가 없으면 NULL을 전달할 수 있습니다.  
  
##  <a name="canimationcolor"></a>  CAnimationColor::CAnimationColor  
 CAnimationColor 개체를 만듭니다.  
  
```  
CAnimationColor();
 
CAnimationColor(
    COLORREF color,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `color`  
 기본 색을 지정합니다.  
  
 `nGroupID`  
 그룹 ID를 지정 합니다.  
  
 `nObjectID`  
 개체 ID를 지정 합니다.  
  
 `dwUserData`  
 사용자 정의 데이터를 지정합니다.  
  
### <a name="remarks"></a>설명  
 개체는 기본 값을 빨간색, 녹색, 파란색, 개체 ID 및 0으로 설정할 수 있는 그룹 ID로 구성 됩니다. 값은 SetDefaultValue 및 SetID를 사용 하 여 런타임에 나중에 변경할 수 있습니다.  
  
##  <a name="getanimationvariablelist"></a>  CAnimationColor::GetAnimationVariableList  
 목록에 캡슐화 된 애니메이션 변수를 추가합니다.  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>매개 변수  
 `lst`  
 함수가 반환할 때 빨강, 녹색 및 파랑 구성 요소를 나타내는 세 CAnimationVariable 개체에 대 한 포인터를 포함 합니다.  
  
##  <a name="getb"></a>  CAnimationColor::GetB  
 CAnimationVariable 파란색 구성 요소를 나타내는에 대 한 액세스를 제공 합니다.  
  
```  
CAnimationVariable& GetB();
```  
  
### <a name="return-value"></a>반환 값  
 캡슐화 된 CAnimationVariable 나타내는 파랑 구성 요소에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 파란색 구성 요소를 나타내는 기본 CAnimationVariable에 대 한 직접 액세스를 가져오려면이 메서드를 호출할 수 있습니다.  
  
##  <a name="getdefaultvalue"></a>  CAnimationColor::GetDefaultValue  
 색의 구성 요소에 대 한 기본 값을 반환합니다.  
  
```  
COLORREF GetDefaultValue();
```  
  
### <a name="return-value"></a>반환 값  
 RGB 구성 요소에 대 한 기본값을 포함 하는 COLORREF 값입니다.  
  
### <a name="remarks"></a>설명  
 생성자 또는 SetDefaultValue 여 이전에 설정 된 기본값을 검색 하려면이 함수를 호출 합니다.  
  
##  <a name="getg"></a>  CAnimationColor::GetG  
 CAnimationVariable 나타내는 녹색 구성 요소에 대 한 액세스를 제공 합니다.  
  
```  
CAnimationVariable& GetG();
```  
  
### <a name="return-value"></a>반환 값  
 캡슐화 된 CAnimationVariable 나타내는 녹색 구성에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 기본 CAnimationVariable 나타내는 녹색 구성 요소에 대 한 직접 액세스를 가져오려면이 메서드를 호출할 수 있습니다.  
  
##  <a name="getr"></a>  CAnimationColor::GetR  
 CAnimationVariable 나타내는 빨강 구성 요소에 대 한 액세스를 제공 합니다.  
  
```  
CAnimationVariable& GetR();
```  
  
### <a name="return-value"></a>반환 값  
 캡슐화 된 CAnimationVariable 나타내는 빨강 구성 요소에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 빨간색 구성 요소를 나타내는 기본 CAnimationVariable에 대 한 직접 액세스를 가져오려면이 메서드를 호출할 수 있습니다.  
  
##  <a name="getvalue"></a>  CAnimationColor::GetValue  
 현재 값을 반환 합니다.  
  
```  
BOOL GetValue(COLORREF& color);
```  
  
### <a name="parameters"></a>매개 변수  
 `color`  
 출력입니다. 이 메서드가 반환 될 때 현재 값을 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 TRUE 인 경우 현재 값을 검색 했습니다. 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 애니메이션 색의 현재 값을 검색 하려면이 함수를 호출 합니다. 이 방법이 실패 하면 색의 구성 요소에 대 한 기본 COM 개체 초기화 되지 않은 경우 색 SetDefaultValue 통하거나 생성자에서 이전에 설정 된 기본값을 포함 합니다.  
  
##  <a name="m_bvalue"></a>  CAnimationColor::m_bValue  
 캡슐화 된 애니메이션 변수 애니메이션 색의 파랑 구성 요소를 나타냅니다.  
  
```  
CAnimationVariable m_bValue;  
```  
  
##  <a name="m_gvalue"></a>  CAnimationColor::m_gValue  
 캡슐화 된 애니메이션 변수 애니메이션 색의 녹색 구성 요소를 나타냅니다.  
  
```  
CAnimationVariable m_gValue;  
```  
  
##  <a name="m_rvalue"></a>  CAnimationColor::m_rValue  
 캡슐화 된 애니메이션 변수 애니메이션 색의 빨강 구성 요소를 나타냅니다.  
  
```  
CAnimationVariable m_rValue;  
```  
  
##  <a name="operator_colorref"></a>  COLORREF CAnimationColor::operator  
  
```  
operator COLORREF();
```   
  
### <a name="return-value"></a>반환 값  
  
##  <a name="operator_eq"></a>  CAnimationColor::operator =  
 CAnimationColor에 색을 할당합니다.  
  
```  
void operator=(COLORREF color);
```  
  
### <a name="parameters"></a>매개 변수  
 `color`  
 새 애니메이션 색 값을 지정합니다.  
  
### <a name="remarks"></a>설명  
 이 연산자 SetDefaultValue 생성 된 색의 구성 요소에 대 한 기본 COM 개체를 다시 호출 하기 때문에 애니메이션이 시작 되기 전에 하는 것이 좋습니다. 이 애니메이션 개체 (재정의 또는 IntegerValueChanged) 이벤트를 구독 하는 경우 이러한 이벤트를 다시 사용 하도록 설정 해야 합니다.  
  
##  <a name="setdefaultvalue"></a>  CAnimationColor::SetDefaultValue  
 기본값을 설정합니다.  
  
```  
void SetDefaultValue(COLORREF color);
```  
  
### <a name="parameters"></a>매개 변수  
 `color`  
 빨강, 녹색 및 파랑 구성 요소에 대 한 새 기본값을 지정합니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 애니메이션 개체에 기본값을 설정 합니다. 이 메서드는 애니메이션 색의 색상 구성 요소에 기본값을 할당 합니다. 기본 COM 개체를 만든 경우 또한 다시 것입니다. 이 애니메이션 개체 (재정의 또는 IntegerValueChanged) 이벤트를 구독 하는 경우 이러한 이벤트를 다시 사용 하도록 설정 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
