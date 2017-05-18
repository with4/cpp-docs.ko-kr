---
title: "CAnimationValue 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationValue::GetValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationValue::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationValue::m_value
dev_langs:
- C++
helpviewer_keywords:
- CAnimationValue class
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
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
ms.openlocfilehash: 083c8be9a0d9d518d5353b6d02c0050944312805
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="canimationvalue-class"></a>CAnimationValue 클래스
하나의 값을 갖는 애니메이션 개체 기능을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CAnimationValue : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationValue::CAnimationValue](#canimationvalue)|오버로드됨. CAnimationValue 개체를 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationValue::AddTransition](#addtransition)|값에 적용할에 전환을 추가 합니다.|  
|[CAnimationValue::GetValue](#getvalue)|오버로드됨. 현재 값을 검색 합니다.|  
|[CAnimationValue::GetVariable](#getvariable)|캡슐화 된 애니메이션 변수에 대 한 액세스를 제공합니다.|  
|[CAnimationValue::SetDefaultValue](#setdefaultvalue)|기본값을 설정합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationValue::GetAnimationVariableList](#getanimationvariablelist)|목록에 캡슐화 된 애니메이션 변수를 추가합니다. (재정의 [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationValue::operator DOUBLE](#operator_double)|CAnimationValue 및 DOUBLE 간의 변환을 제공합니다.|  
|[CAnimationValue::operator INT32](#operator_int32)|INT32 CAnimationValue 사이의 변환을 제공합니다.|  
|[CAnimationValue::operator =](#operator_eq)|오버로드됨. CAnimationValue을 INT32 값을 할당합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationValue::m_value](#m_value)|캡슐화 된 애니메이션 변수를 애니메이션 값을 나타냅니다.|  
  
## <a name="remarks"></a>주의  
 CAnimationValue 클래스는 단일 CAnimationVariable 개체를 캡슐화 하 고 단일 애니메이션된 값을 응용 프로그램에 나타낼 수 있습니다. 애니메이션된 투명성 (페이드 효과), 각도 (개체 회전)에 대 한이 클래스에 사용할 수는 예를 들어, 나는 경우에는 다른 단일 애니메이션된 값에 따라 애니메이션을 만들어야 하는 경우. 응용 프로그램에서이 클래스를 사용 하 여 방금이 클래스의 개체를 인스턴스화할 CAnimationController::AddAnimationObject를 사용 하 여 애니메이션 컨트롤러를 추가 및 값에 적용할 각 전환에 대해 AddTransition를 호출 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationValue`
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationValue::AddTransition  
 값에 적용할에 전환을 추가 합니다.  
  
```  
void AddTransition(CBaseTransition* pTransition);
```  
  
### <a name="parameters"></a>매개 변수  
 `pTransition`  
 전환 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 애니메이션 변수를 적용할 수는 전환의 내부 목록에 전환을 추가 하려면이 함수를 호출 합니다. 전환에 추가 되지 즉시 적용 되며 내부 목록에 저장 합니다. 전환 (특정 값에 대 한 스토리 보드에 추가 된) 적용 CAnimationController::AnimateGroup를 호출 하는 경우.  
  
##  <a name="canimationvalue"></a>CAnimationValue::CAnimationValue  
 CAnimationValue 개체를 만듭니다.  
  
```  
CAnimationValue();

 
CAnimationValue(
    DOUBLE dblDefaultValue,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `dblDefaultValue`  
 기본값을 지정합니다.  
  
 `nGroupID`  
 그룹 ID를 지정 합니다.  
  
 `nObjectID`  
 개체 ID를 지정 합니다.  
  
 `dwUserData`  
 사용자 정의 데이터를 지정합니다.  
  
### <a name="remarks"></a>주의  
 기본 속성으로 CAnimationValue 개체를 생성 합니다: 기본 값, 그룹 ID 및 개체 ID는 0으로 설정 됩니다.  
  
##  <a name="getanimationvariablelist"></a>CAnimationValue::GetAnimationVariableList  
 목록에 캡슐화 된 애니메이션 변수를 추가합니다.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>매개 변수  
 `lst`  
 함수가 반환 될 때 애니메이션된 값을 나타내는 CAnimationVariable에 대 한 포인터를 포함 합니다.  
  
##  <a name="getvalue"></a>CAnimationValue::GetValue  
 현재 값을 검색 합니다.  
  
```  
BOOL GetValue(DOUBLE& dblValue);  
BOOL GetValue(INT32& nValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `dblValue`  
 출력입니다. 함수는 반환 될 때 애니메이션 변수의 현재 값을 포함 합니다.  
  
 `nValue`  
 출력입니다. 함수는 반환 될 때 애니메이션 변수의 현재 값을 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 현재 값이 성공적으로 검색 된 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 현재 값을 검색 하려면이 함수를 호출 합니다. 이 구현에서는 캡슐화 된 COM 개체를 호출 하 고 호출이 실패 한 경우이 메서드 또는 SetDefaultValue 생성자에서 이전에 설정 된 기본 값을 반환 합니다.  
  
##  <a name="getvariable"></a>CAnimationValue::GetVariable  
 캡슐화 된 애니메이션 변수에 대 한 액세스를 제공합니다.  
  
```  
CAnimationVariable& GetVariable();
```  
  
### <a name="return-value"></a>반환 값  
 캡슐화 된 애니메이션 변수에 대 한 참조입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 캡슐화 된 애니메이션 변수에 액세스 합니다. CAnimationVariable에서 애니메이션 변수의 생성 되지 않은 경우 해당 포인터가 NULL이 될 수 기본 IUIAnimationVariable 개체에 액세스할 수 있게 합니다.  
  
##  <a name="m_value"></a>CAnimationValue::m_value  
 캡슐화 된 애니메이션 변수를 애니메이션 값을 나타냅니다.  
  
```  
CAnimationVariable m_value;  
```  
  
##  <a name="operator_double"></a>CAnimationValue::operator DOUBLE  
 CAnimationValue 및 DOUBLE 간의 변환을 제공합니다.  
  
```  
operator DOUBLE();
```   
  
### <a name="return-value"></a>반환 값  
 애니메이션 값의 현재 값입니다.  
  
### <a name="remarks"></a>주의  
 CAnimationValue 및 DOUBLE 간의 변환을 제공합니다. 이 메서드는 내부적으로 GetValue를 호출 하 고 오류를 확인 하지 않습니다. Getvalue가 실패 하는 경우 반환 되는 값 또는 SetDefaultValue 생성자에서 이전에 설정한 기본값을 포함 됩니다.  
  
##  <a name="operator_int32"></a>CAnimationValue::operator INT32  
 INT32 CAnimationValue 사이의 변환을 제공합니다.  
  
```  
operator INT32();
```   
  
### <a name="return-value"></a>반환 값  
 정수로 애니메이션 값의 현재 값입니다.  
  
### <a name="remarks"></a>주의  
 INT32 CAnimationValue 사이의 변환을 제공합니다. 이 메서드는 내부적으로 GetValue를 호출 하 고 오류를 확인 하지 않습니다. Getvalue가 실패 하는 경우 반환 되는 값 또는 SetDefaultValue 생성자에서 이전에 설정한 기본값을 포함 됩니다.  
  
##  <a name="operator_eq"></a>CAnimationValue::operator =  
 CAnimationValue에 DOUBLE 값을 할당합니다.  
  
```  
void operator=(DOUBLE dblVal);  
void operator=(INT32 nVal);
```  
  
### <a name="parameters"></a>매개 변수  
 `dblVal`  
 애니메이션 값에 할당할 값을 지정 합니다.  
  
 `nVal`  
 애니메이션 값에 할당할 값을 지정 합니다.  
  
### <a name="remarks"></a>주의  
 CAnimationValue에 DOUBLE 값을 할당합니다. 이 값은 캡슐화 된 애니메이션 변수를 기본값으로 설정 됩니다. 이 애니메이션 개체 (ValueChanged 또는 IntegerValueChanged) 이벤트를 구독 하는 경우 이러한 이벤트를 다시 사용 하도록 설정 해야 합니다.  
  
##  <a name="setdefaultvalue"></a>CAnimationValue::SetDefaultValue  
 기본값을 설정합니다.  
  
```  
void SetDefaultValue(DOUBLE dblDefaultValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `dblDefaultValue`  
 기본값을 지정합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 기본값을 설정 합니다. 애니메이션 시작 되지 않은 및/또는 기본 COM 개체 생성 되지 않은 경우 기본값은 응용 프로그램에 반환 됩니다. CAnimationVarible에 캡슐화 하는 기본 COM 개체를 이미 만든 경우이 메서드를 다시 만드는 것, 따라서 EnableValueChanged/EnableIntegerValueChanged 메서드를 다시 호출 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

