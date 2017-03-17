---
title: "CAnimationRect 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationRect::GetBottom
- AFXANIMATIONCONTROLLER/CAnimationRect::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetLeft
- AFXANIMATIONCONTROLLER/CAnimationRect::GetRight
- AFXANIMATIONCONTROLLER/CAnimationRect::GetTop
- AFXANIMATIONCONTROLLER/CAnimationRect::GetValue
- AFXANIMATIONCONTROLLER/CAnimationRect::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bFixedSize
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bottomValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_leftValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_rightValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_szInitial
- AFXANIMATIONCONTROLLER/CAnimationRect::m_topValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationRect class
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
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
ms.sourcegitcommit: 73410ae17465880f455e5b15026f6cc010803c19
ms.openlocfilehash: f935884301030166572e356fffe88439f843f2c7
ms.lasthandoff: 02/24/2017

---
# <a name="canimationrect-class"></a>CAnimationRect 클래스
면에 애니메이션을 적용할 수 있는 사각형 기능을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CAnimationRect : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationRect::CAnimationRect](#canimationrect)|오버로드됨. 애니메이션 rect 개체를 생성 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationRect::AddTransition](#addtransition)|왼쪽, 위쪽, 오른쪽 및 아래쪽 좌표에 대 한 전환을 추가합니다.|  
|[CAnimationRect::GetBottom](#getbottom)|아래쪽 좌표를 나타내는 CAnimationVariable에 대 한 액세스를 제공 합니다.|  
|[CAnimationRect::GetDefaultValue](#getdefaultvalue)|사각형의 경계에 대 한 기본 값을 반환합니다.|  
|[CAnimationRect::GetLeft](#getleft)|왼쪽된 좌표를 나타내는 CAnimationVariable에 대 한 액세스를 제공 합니다.|  
|[CAnimationRect::GetRight](#getright)|오른쪽 좌표를 나타내는 CAnimationVariable에 대 한 액세스를 제공 합니다.|  
|[CAnimationRect::GetTop](#gettop)|위쪽 좌표를 나타내는 CAnimationVariable에 대 한 액세스를 제공 합니다.|  
|[CAnimationRect::GetValue](#getvalue)|현재 값을 반환 합니다.|  
|[CAnimationRect::SetDefaultValue](#setdefaultvalue)|기본값을 설정합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|목록에 캡슐화 된 애니메이션 변수를 추가합니다. (재정의 [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[RECT CAnimationRect::operator](#operator_rect)|사각형을 한 CAnimationRect 변환|  
|[CAnimationRect::operator =](#operator_eq)|CAnimationRect에 rect을 할당합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationRect::m_bFixedSize](#m_bfixedsize)|사각형 크기는 수정 여부를 지정 합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationRect::m_bottomValue](#m_bottomvalue)|아래쪽을 나타내는 캡슐화 된 애니메이션 변수의 애니메이션 사각형의 경계입니다.|  
|[CAnimationRect::m_leftValue](#m_leftvalue)|애니메이션 사각형의 왼쪽을 나타내는 캡슐화 된 애니메이션 변수의 바인딩됩니다.|  
|[CAnimationRect::m_rightValue](#m_rightvalue)|오른쪽을 나타내는 캡슐화 된 애니메이션 변수의 애니메이션 사각형의 경계입니다.|  
|[CAnimationRect::m_szInitial](#m_szinitial)|애니메이션 사각형의 초기 크기를 지정합니다.|  
|[CAnimationRect::m_topValue](#m_topvalue)|애니메이션 사각형의 위쪽을 나타내는 캡슐화 된 애니메이션 변수의 바인딩됩니다.|  
  
## <a name="remarks"></a>주의  
 CAnimationRect 클래스는&4; 개의 CAnimationVariable 개체를 캡슐화 하 고 사각형 응용 프로그램에 나타낼 수 있습니다. 응용 프로그램에서이 클래스를 사용 하 여 방금이 클래스의 개체를 인스턴스화할 CAnimationController::AddAnimationObject를 사용 하 여 애니메이션 컨트롤러를 추가 및 왼쪽, 오른쪽 위쪽 및 아래쪽 좌표에 적용 될 각 전환에 대해 AddTransition를 호출 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationRect`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationRect::AddTransition  
 왼쪽, 위쪽, 오른쪽 및 아래쪽 좌표에 대 한 전환을 추가합니다.  
  
```  
void AddTransition(
    CBaseTransition* pLeftTransition,  
    CBaseTransition* pTopTransition,  
    CBaseTransition* pRightTransition,  
    CBaseTransition* pBottomTransition);
```  
  
### <a name="parameters"></a>매개 변수  
 `pLeftTransition`  
 왼쪽에 대 한 전환을 지정합니다.  
  
 `pTopTransition`  
 위쪽에 대 한 전환을 지정합니다.  
  
 `pRightTransition`  
 오른쪽에 대 한 전환을 지정합니다.  
  
 `pBottomTransition`  
 아래쪽에 대 한 전환을 지정합니다.  
  
### <a name="remarks"></a>주의  
 지정된 된 전환을 각 사각형 측면에 대 한 변수를 애니메이션에 적용할 변환의 내부 목록에 추가 하려면이 함수를 호출 합니다. 전환에 추가 되지 즉시 적용 되며 내부 목록에 저장 합니다. 전환 (특정 값에 대 한 스토리 보드에 추가 된) 적용 CAnimationController::AnimateGroup를 호출 하는 경우. 사각형 측면 중 하나에 전환을 적용할 필요가 없으면 NULL을 전달할 수 있습니다.  
  
##  <a name="canimationrect"></a>CAnimationRect::CAnimationRect  
 CAnimationRect 개체를 만듭니다.  
  
```  
CAnimationRect();

 
CAnimationRect(
    const CRect& rect,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);

 
CAnimationRect(
    const CPoint& pt,  
    const CSize& sz,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);

 
CAnimationRect(
    int nLeft,  
    int nTop,  
    int nRight,  
    int nBottom,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 기본 사각형을 지정합니다.  
  
 `nGroupID`  
 그룹 ID를 지정 합니다.  
  
 `nObjectID`  
 개체 ID를 지정 합니다.  
  
 `dwUserData`  
 사용자 정의 데이터를 지정합니다.  
  
 `pt`  
 왼쪽 위 모퉁이의 좌표입니다.  
  
 `sz`  
 사각형의 크기입니다.  
  
 `nLeft`  
 경계의 왼쪽 좌표를 지정합니다.  
  
 `nTop`  
 위쪽 경계의 좌표를 지정 합니다.  
  
 `nRight`  
 오른쪽 경계의 좌표를 지정합니다.  
  
 `nBottom`  
 바인딩된 아래쪽의 좌표를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 개체를 생성 하 여 기본값으로 왼쪽, 위쪽, 오른쪽 및 아래쪽에 대 한 개체 ID와 그룹 ID를 0으로 설정 됩니다. SetDefaultValue 및 SetID를 사용 하 여 런타임에 나중에 변경할 수 있습니다.  
  
##  <a name="getanimationvariablelist"></a>CAnimationRect::GetAnimationVariableList  
 목록에 캡슐화 된 애니메이션 변수를 추가합니다.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>매개 변수  
 `lst`  
 함수가 반환 하는 경우 사각형의 좌표를 나타내는&4; 개의 CAnimationVariable 개체에 대 한 포인터가 포함 되어 있습니다.  
  
##  <a name="getbottom"></a>CAnimationRect::GetBottom  
 아래쪽 좌표를 나타내는 CAnimationVariable에 대 한 액세스를 제공 합니다.  
  
```  
CAnimationVariable& GetBottom();
```  
  
### <a name="return-value"></a>반환 값  
 캡슐화 된 CAnimationVariable 아래쪽 좌표를 나타내는에 대 한 참조입니다.  
  
### <a name="remarks"></a>주의  
 아래쪽 좌표를 나타내는 기본 CAnimationVariable에 대 한 직접 액세스를 가져오려면이 메서드를 호출할 수 있습니다.  
  
##  <a name="getdefaultvalue"></a>CAnimationRect::GetDefaultValue  
 사각형의 경계에 대 한 기본 값을 반환합니다.  
  
```  
CRect GetDefaultValue();
```  
  
### <a name="return-value"></a>반환 값  
 왼쪽, 오른쪽, 위쪽 및 아래쪽에 대 한 기본값을 포함 하는 CRect 값입니다.  
  
### <a name="remarks"></a>주의  
 생성자 또는 SetDefaultValue 하 여 이전에 설정 된 기본값을 검색 하려면이 함수를 호출 합니다.  
  
##  <a name="getleft"></a>CAnimationRect::GetLeft  
 왼쪽된 좌표를 나타내는 CAnimationVariable에 대 한 액세스를 제공 합니다.  
  
```  
CAnimationVariable& GetLeft();
```  
  
### <a name="return-value"></a>반환 값  
 캡슐화 된 CAnimationVariable 왼쪽된 좌표를 나타내는에 대 한 참조입니다.  
  
### <a name="remarks"></a>주의  
 왼쪽된 좌표를 나타내는 기본 CAnimationVariable에 대 한 직접 액세스를 가져오려면이 메서드를 호출할 수 있습니다.  
  
##  <a name="getright"></a>CAnimationRect::GetRight  
 오른쪽 좌표를 나타내는 CAnimationVariable에 대 한 액세스를 제공 합니다.  
  
```  
CAnimationVariable& GetRight();
```  
  
### <a name="return-value"></a>반환 값  
 캡슐화 된 CAnimationVariable 오른쪽 좌표를 나타내는에 대 한 참조입니다.  
  
### <a name="remarks"></a>주의  
 오른쪽 좌표를 나타내는 기본 CAnimationVariable에 대 한 직접 액세스를 가져오려면이 메서드를 호출할 수 있습니다.  
  
##  <a name="gettop"></a>CAnimationRect::GetTop  
 위쪽 좌표를 나타내는 CAnimationVariable에 대 한 액세스를 제공 합니다.  
  
```  
CAnimationVariable& GetTop();
```  
  
### <a name="return-value"></a>반환 값  
 캡슐화 된 CAnimationVariable 위쪽 좌표를 나타내는에 대 한 참조입니다.  
  
### <a name="remarks"></a>주의  
 위쪽 좌표를 나타내는 기본 CAnimationVariable에 대 한 직접 액세스를 가져오려면이 메서드를 호출할 수 있습니다.  
  
##  <a name="getvalue"></a>CAnimationRect::GetValue  
 현재 값을 반환 합니다.  
  
```  
BOOL GetValue(CRect& rect);
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 출력입니다. 이 메서드가 반환 될 때 현재 값을 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 True 이면 현재 값을 검색 했습니다. 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 애니메이션 사각형의 현재 값을 검색 하려면이 함수를 호출 합니다. 이 메서드가 실패 또는 기본 COM 개체 남아 있는 경우 위쪽, 오른쪽 및 아래쪽 초기화 되지 않은, rect SetDefaultValue 또는 생성자에서 이전에 설정 된 기본값을 포함 합니다.  
  
##  <a name="m_bfixedsize"></a>CAnimationRect::m_bFixedSize  
 사각형 크기는 수정 여부를 지정 합니다.  
  
```  
BOOL m_bFixedSize;  
```  
  
### <a name="remarks"></a>주의  
 이 멤버가 true 인 경우 사각형의 크기가 고정 되 고 오른쪽 하 고 하위 값이 고정된 크기에 따라 왼쪽 위의 이동 될 때마다 다시 계산 됩니다. 이 값을 쉽게 화면 주위로 사각형을 이동 하려면 TRUE로 설정 합니다. 이 경우 오른쪽 및 아래쪽 좌표에 적용 된 전환은 무시 됩니다. 크기는 개체를 생성 하거나 SetDefaultValue를 호출 하는 경우 내부적으로 저장 됩니다. 이 멤버는 기본적으로 FALSE로 설정 됩니다.  
  
##  <a name="m_bottomvalue"></a>CAnimationRect::m_bottomValue  
 아래쪽을 나타내는 캡슐화 된 애니메이션 변수의 애니메이션 사각형의 경계입니다.  
  
```  
CAnimationVariable m_bottomValue;  
```  
  
##  <a name="m_leftvalue"></a>CAnimationRect::m_leftValue  
 애니메이션 사각형의 왼쪽을 나타내는 캡슐화 된 애니메이션 변수의 바인딩됩니다.  
  
```  
CAnimationVariable m_leftValue;  
```  
  
##  <a name="m_rightvalue"></a>CAnimationRect::m_rightValue  
 오른쪽을 나타내는 캡슐화 된 애니메이션 변수의 애니메이션 사각형의 경계입니다.  
  
```  
CAnimationVariable m_rightValue;  
```  
  
##  <a name="m_szinitial"></a>CAnimationRect::m_szInitial  
 애니메이션 사각형의 초기 크기를 지정합니다.  
  
```  
CSize m_szInitial;  
```  
  
##  <a name="m_topvalue"></a>CAnimationRect::m_topValue  
 애니메이션 사각형의 위쪽을 나타내는 캡슐화 된 애니메이션 변수의 바인딩됩니다.  
  
```  
CAnimationVariable m_topValue;  
```  
  
##  <a name="operator_rect"></a>RECT CAnimationRect::operator  
 사각형을 한 CAnimationRect 변환  
  
```  
operator RECT();
```   
  
### <a name="return-value"></a>반환 값  
 사각형으로 애니메이션 사각형의 현재 값  
  
### <a name="remarks"></a>주의  
 이 함수는 GetValue 내부적으로 호출 합니다. 어떤 이유로 getvalue가 실패 하면 반환 되는 RECT 모든 사각형 좌표에 대 한 기본 값이 포함 됩니다.  
  
##  <a name="operator_eq"></a>CAnimationRect::operator =  
 CAnimationRect에 rect을 할당합니다.  
  
```  
void operator=(const RECT& rect);
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 애니메이션 사각형의 새 값입니다.  
  
### <a name="remarks"></a>주의  
 이 연산자는 생성 된 색 구성 요소에 대 한 기본 COM 개체를 다시 만드는 SetDefaultValue를 호출 하기 때문에 애니메이션이 시작 되기 전에 하는 것이 좋습니다. 이 애니메이션 개체 (ValueChanged 또는 IntegerValueChanged) 이벤트를 구독 하는 경우 이러한 이벤트를 다시 사용 하도록 설정 해야 합니다.  
  
##  <a name="setdefaultvalue"></a>CAnimationRect::SetDefaultValue  
 기본값을 설정합니다.  
  
```  
void SetDefaultValue(const CRect& rect);
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 왼쪽, 위쪽, 오른쪽 및 아래쪽에 대 한 새 기본값을 지정합니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 사용 하 여 애니메이션 개체에 기본값을 설정 합니다. 이 메서드는 사각형의 경계를 기본 값을 할당 합니다. 기본 COM 개체를 만든 경우도 다시 것입니다. 이 애니메이션 개체 (ValueChanged 또는 IntegerValueChanged) 이벤트를 구독 하는 경우 이러한 이벤트를 다시 사용 하도록 설정 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

