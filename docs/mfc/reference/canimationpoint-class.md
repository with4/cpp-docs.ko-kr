---
title: CAnimationPoint 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetX
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetY
- AFXANIMATIONCONTROLLER/CAnimationPoint::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_xValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_yValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationPoint [MFC], CAnimationPoint
- CAnimationPoint [MFC], AddTransition
- CAnimationPoint [MFC], GetDefaultValue
- CAnimationPoint [MFC], GetValue
- CAnimationPoint [MFC], GetX
- CAnimationPoint [MFC], GetY
- CAnimationPoint [MFC], SetDefaultValue
- CAnimationPoint [MFC], GetAnimationVariableList
- CAnimationPoint [MFC], m_xValue
- CAnimationPoint [MFC], m_yValue
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58c8c9aaaf212e98fdeff1e639bb09423304e643
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957405"
---
# <a name="canimationpoint-class"></a>CAnimationPoint 클래스
좌표에 애니메이션을 적용할 수 있는 점 기능을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CAnimationPoint : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationPoint::CAnimationPoint](#canimationpoint)|오버로드됨. CAnimationPoint 개체를 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationPoint::AddTransition](#addtransition)|X에 대 한 변환을 추가 및 Y 좌표입니다.|  
|[CAnimationPoint::GetDefaultValue](#getdefaultvalue)|X에 대 한 기본값을 반환 및 Y 좌표입니다.|  
|[CAnimationPoint::GetValue](#getvalue)|현재 값을 반환 합니다.|  
|[CAnimationPoint::GetX](#getx)|X 좌표에 대 한 CAnimationVariable에 대 한 액세스를 제공합니다.|  
|[CAnimationPoint::GetY](#gety)|CAnimationVariable에 Y 좌표에 대 한 액세스를 제공합니다.|  
|[CAnimationPoint::SetDefaultValue](#setdefaultvalue)|기본값을 설정합니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationPoint::GetAnimationVariableList](#getanimationvariablelist)|목록에 캡슐화 된 애니메이션 변수를 추가합니다. (재정의 [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationPoint::operator CPoint](#operator_cpoint)|CPoint는 CAnimationPoint 변환합니다.|  
|[CAnimationPoint::operator =](#operator_eq)|CAnimationPoint ptSrc 할당합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[CAnimationPoint::m_xValue](#m_xvalue)|X 나타내는 캡슐화 된 애니메이션 변수 애니메이션 점의 좌표입니다.|  
|[CAnimationPoint::m_yValue](#m_yvalue)|캡슐화 된 애니메이션 변수 애니메이션 점의 Y 좌표를 나타내는입니다.|  
  
## <a name="remarks"></a>설명  
 CAnimationPoint 클래스는 두 CAnimationVariable 개체를 캡슐화 하 고 지점을 응용 프로그램에 나타낼 수 있습니다. 예를 들어 화면 (예: 텍스트 문자열, 원, 지점 등)에 개체의 위치에 애니메이션 효과를 줄이 클래스를 사용할 수 있습니다. 응용 프로그램에서이 클래스를 사용 하려면 방금이 클래스의 개체, CAnimationController::AddAnimationObject를 사용 하 여 애니메이션 컨트롤러를 추가 인스턴스화하고 호출에 적용 될 각 전환에 대해 AddTransition X 및 Y 좌표입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationPoint`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>  CAnimationPoint::AddTransition  
 X에 대 한 변환을 추가 및 Y 좌표입니다.  
  
```  
void AddTransition(
    CBaseTransition* pXTransition,  
    CBaseTransition* pYTransition);
```  
  
### <a name="parameters"></a>매개 변수  
 *pXTransition*  
 X 좌표에 대 한 전환에 대 한 포인터입니다.  
  
 *pYTransition*  
 Y에 대 한 전환에 대 한 포인터를 조정 합니다.  
  
### <a name="remarks"></a>설명  
 지정된 된 전환을 X에 대 한 변수 애니메이션에 적용할 변환의 내부 목록에 추가 하려면이 함수를 호출 및 Y 좌표입니다. 전환에 추가 하면 하지 즉시 적용 되며 내부 목록에 저장 합니다. 전환 (특정 값에 대 한 스토리 보드에 추가 된) 적용 CAnimationController::AnimateGroup를 호출 하는 경우. 전환을 좌표 중 하나에 적용할 필요가 없으면 NULL을 전달할 수 있습니다.  
  
##  <a name="canimationpoint"></a>  CAnimationPoint::CAnimationPoint  
 CAnimationPoint 개체를 만듭니다.  
  
```  
CAnimationPoint();

 
CAnimationPoint(
    const CPoint& ptDefault,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 *ptDefault*  
 기본 좌표를 시작점 좌표를 지정합니다.  
  
 *nGroupID*  
 그룹 ID를 지정 합니다.  
  
 *nObjectID*  
 개체 ID를 지정 합니다.  
  
 *dwUserData*  
 사용자 정의 데이터를 지정합니다.  
  
### <a name="remarks"></a>설명  
 기본 속성으로 CAnimationPoint 개체를 생성: 점 좌표를 기본값, 그룹 ID 및 개체 ID는 0으로 설정 됩니다.  
  
##  <a name="getanimationvariablelist"></a>  CAnimationPoint::GetAnimationVariableList  
 목록에 캡슐화 된 애니메이션 변수를 추가합니다.  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>매개 변수  
 *lst*  
 함수가 반환할 때 X 및 Y 좌표를 나타내는 두 개의 CAnimationVariable 개체에 대 한 포인터를 포함 합니다.  
  
##  <a name="getdefaultvalue"></a>  CAnimationPoint::GetDefaultValue  
 X에 대 한 기본값을 반환 및 Y 좌표입니다.  
  
```  
CPoint GetDefaultValue();
```  
  
### <a name="return-value"></a>반환 값  
 지점에 포함 된 기본 값입니다.  
  
### <a name="remarks"></a>설명  
 생성자 또는 SetDefaultValue 여 이전에 설정 된 기본값을 검색 하려면이 함수를 호출 합니다.  
  
##  <a name="getvalue"></a>  CAnimationPoint::GetValue  
 현재 값을 반환 합니다.  
  
```  
BOOL GetValue(CPoint& ptValue);
```  
  
### <a name="parameters"></a>매개 변수  
 *ptValue*  
 출력입니다. 이 메서드가 반환 될 때 현재 값을 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 TRUE 인 경우 현재 값을 검색 했습니다. 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 애니메이션 포인트의 현재 값을 검색 하려면이 함수를 호출 합니다. 이 메서드가 실패 또는 기본 COM 개체 X에 대 한 Y 좌표 초기화 되지 않은 경우 ptValue SetDefaultValue 통하거나 생성자에서 이전에 설정 된 기본값을 포함 합니다.  
  
##  <a name="getx"></a>  CAnimationPoint::GetX  
 X 좌표에 대 한 CAnimationVariable에 대 한 액세스를 제공합니다.  
  
```  
CAnimationVariable& GetX();
```  
  
### <a name="return-value"></a>반환 값  
 캡슐화 된 CAnimationVariable 나타내는 X에 대 한 참조를 조정 합니다.  
  
### <a name="remarks"></a>설명  
 기본 CAnimationVariable 나타내는 X에 대 한 직접 액세스를 가져오려면이 메서드를 호출할 수를 조정 합니다.  
  
##  <a name="gety"></a>  CAnimationPoint::GetY  
 CAnimationVariable에 Y 좌표에 대 한 액세스를 제공합니다.  
  
```  
CAnimationVariable& GetY();
```  
  
### <a name="return-value"></a>반환 값  
 캡슐화 된 CAnimationVariable Y 좌표를 나타내는에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 Y 좌표를 나타내는 기본 CAnimationVariable에 대 한 직접 액세스를 가져오려면이 메서드를 호출할 수 있습니다.  
  
##  <a name="m_xvalue"></a>  CAnimationPoint::m_xValue  
 X 나타내는 캡슐화 된 애니메이션 변수 애니메이션 점의 좌표입니다.  
  
```  
CAnimationVariable m_xValue;  
```  
  
##  <a name="m_yvalue"></a>  CAnimationPoint::m_yValue  
 캡슐화 된 애니메이션 변수 애니메이션 점의 Y 좌표를 나타내는입니다.  
  
```  
CAnimationVariable m_yValue;  
```  
  
##  <a name="operator_cpoint"></a>  CAnimationPoint::operator CPoint  
 CPoint는 CAnimationPoint 변환합니다.  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>반환 값  
 CAnimationPoint CPoint로의 현재 값입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 GetValue 내부적으로 호출 합니다. Getvalue가 어떤 이유로 실패 하는 경우 반환 된 X에 대 한 기본 값이 포함 됩니다 및 Y 좌표입니다.  
  
##  <a name="operator_eq"></a>  CAnimationPoint::operator =  
 CAnimationPoint ptSrc 할당합니다.  
  
```  
void operator=(const CPoint& ptSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 *ptSrc*  
 CPoint 또는 포인트를 나타냅니다.  
  
### <a name="remarks"></a>설명  
 CAnimationPoint ptSrc 할당합니다. 애니메이션이 시작 되기 전에이 연산자는 SetDefaultValue을 호출 하기 때문에 다시 기본 COM 개체가 하 만든 경우 X 및 Y 좌표에 대 한 작업을 수행 하는 것이 좋습니다. 이 애니메이션 개체 (재정의 또는 IntegerValueChanged) 이벤트를 구독 하는 경우 이러한 이벤트를 다시 사용 하도록 설정 해야 합니다.  
  
##  <a name="setdefaultvalue"></a>  CAnimationPoint::SetDefaultValue  
 기본값을 설정합니다.  
  
```  
void SetDefaultValue(const POINT& ptDefault);
```  
  
### <a name="parameters"></a>매개 변수  
 *ptDefault*  
 기본 점 값을 지정합니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 애니메이션 개체에 기본값을 설정 합니다. 이 메서드 기본값을 할당 애니메이션 점의 X 및 Y 좌표입니다. 기본 COM 개체를 만든 경우 또한 다시 것입니다. 이 애니메이션 개체 (재정의 또는 IntegerValueChanged) 이벤트를 구독 하는 경우 이러한 이벤트를 다시 사용 하도록 설정 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
