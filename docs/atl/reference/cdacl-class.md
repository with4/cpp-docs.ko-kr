---
title: CDacl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
dev_langs:
- C++
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2724eebd218cea2795d483351ef91b34c9f1bf39
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364772"
---
# <a name="cdacl-class"></a>CDacl 클래스
이 클래스는 DACL (임의 액세스 제어 목록) 구조에 대 한 래퍼입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CDacl : public CAcl
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDacl::CDacl](#cdacl)|생성자입니다.|  
|[CDacl::~CDacl](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDacl::AddAllowedAce](#addallowedace)|허용 되는 ACE (액세스 제어 항목)에 추가 된 `CDacl` 개체입니다.|  
|[CDacl::AddDeniedAce](#adddeniedace)|추가를 거부 ACE는 `CDacl` 개체입니다.|  
|[CDacl::GetAceCount](#getacecount)|Ace (액세스 제어 항목)의 수를 반환 된 `CDacl` 개체입니다.|  
|[CDacl::RemoveAce](#removeace)|특정 ACE (액세스 제어 항목)에서 제거 된 `CDacl` 개체입니다.|  
|[CDacl::RemoveAllAces](#removeallaces)|에 포함 된 Ace를 모두 제거는 `CDacl` 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CDacl::operator =](#operator_eq)|대입 연산자입니다.|  
  
## <a name="remarks"></a>설명  
 개체의 보안 설명자의 DACL을 포함할 수 있습니다. DACL에는 0 개 이상의 Ace (액세스 제어 항목는 사용자 및 그룹 개체를 액세스할 수 있는 사용자를 식별 하 는) 포함 되어 있습니다. DACL이 비어 있으면 (즉, 포함 된 0 Ace) 암시적으로 액세스할 수 있도록에 액세스할 수 없는, 명시적으로 부여 합니다. 그러나 개체의 보안 설명자의 DACL이 없는 경우 개체는 비보호 상태가 및 모든 사용자는 전체 액세스 합니다.  
  
 개체의 DACL을 검색 하려면 개체의 소유자 여야 또는 READ_CONTROL 개체에 대 한 액세스 권한이 있어야 합니다. 개체의 DACL을 변경 하려면 WRITE_DAC 개체에 액세스할 수 있어야 합니다.  
  
 추가, 제거, 만들고 삭제 하에서 Ace가 제공 하는 클래스 메서드를 사용 하 여는 `CDacl` 개체입니다. 참고 항목 [AtlGetDacl](security-global-functions.md#atlgetdacl) 및 [AtlSetDacl](security-global-functions.md#atlsetdacl)합니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오. [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows sdk에서입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CDacl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h  
  
##  <a name="addallowedace"></a>  CDacl::AddAllowedAce  
 허용 되는 ACE (액세스 제어 항목)에 추가 된 `CDacl` 개체입니다.  
  
```
bool AddAllowedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rSid`  
 A [CSid](../../atl/reference/csid-class.md) 개체입니다.  
  
 `AccessMask`  
 권한을 부여할 액세스 권한의 마스크를 지정 지정 된 `CSid` 개체입니다.  
  
 `AceFlags`  
 집합 ACE 상속을 제어 하는 비트 플래그입니다.  
  
 `pObjectType`  
 개체 형식입니다.  
  
 `pInheritedObjectType`  
 상속 된 개체 유형입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** ACE에 추가 되 면는 `CDacl` 개체 **false** 실패 합니다.  
  
### <a name="remarks"></a>설명  
 A `CDacl` 0 개 이상의 Ace (액세스 제어 항목는 사용자 및 그룹 개체를 액세스할 수 있는 사용자를 식별 하 는) 개체에 포함 되어 있습니다. 이 메서드는 추가에 대 한 액세스를 허용 하는 ACE는 `CDacl` 개체입니다.  
  
 참조 [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) 에 대 한 설명은에서 설정할 수 있는 다양 한 플래그는 `AceFlags` 매개 변수입니다.  
  
##  <a name="adddeniedace"></a>  CDacl::AddDeniedAce  
 거부 ACE (액세스 제어 항목)에 추가 된 `CDacl` 개체입니다.  
  
```
bool AddDeniedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rSid`  
 `CSid` 개체입니다.  
  
 `AccessMask`  
 거부할 사용 권한 마스크를 지정에 대 한 지정 된 `CSid` 개체입니다.  
  
 `AceFlags`  
 집합 ACE 상속을 제어 하는 비트 플래그입니다. 기본값은 메서드의 첫 번째 형태는 0입니다.  
  
 `pObjectType`  
 개체 형식입니다.  
  
 `pInheritedObjectType`  
 상속 된 개체 유형입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** ACE에 추가 되 면는 `CDacl` 개체 **false** 실패 합니다.  
  
### <a name="remarks"></a>설명  
 A `CDacl` 0 개 이상의 Ace (액세스 제어 항목는 사용자 및 그룹 개체를 액세스할 수 있는 사용자를 식별 하 는) 개체에 포함 되어 있습니다. 이 메서드는 추가에 대 한 액세스를 거부 하는 ACE는 `CDacl` 개체입니다.  
  
 참조 [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) 에 대 한 설명은에서 설정할 수 있는 다양 한 플래그는 `AceFlags` 매개 변수입니다.  
  
##  <a name="cdacl"></a>  CDacl::CDacl  
 생성자입니다.  
  
```
CDacl (const ACL& rhs) throw(...);  
CDacl () throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 기존 **ACL** (액세스 제어 목록) 구조입니다.  
  
### <a name="remarks"></a>설명  
 `CDacl` 개체 수 수 필요에 따라 사용 하 여 만든 기존 **ACL** 구조입니다. 만 DACL (임의 액세스 제어 목록)에 유의 해야 하 고는 SACL (시스템 액세스 제어 목록)이이 매개 변수로 전달 되어야 합니다. 디버그 빌드에 SACL 전달 어설션을 발생 합니다. 릴리스 빌드에서 SACL 전달 됩니다 Ace (액세스 제어 항목) 무시 되는 ACL에서 시키며, 오류가 발생 하지 것입니다.  
  
##  <a name="dtor"></a>  CDacl::~CDacl  
 소멸자입니다.  
  
```
~CDacl () throw();
```  
  
### <a name="remarks"></a>설명  
 소멸자를 사용 하 여 모든 Ace (액세스 제어 항목)를 포함 하는 개체에 의해 획득 리소스 해제 [CDacl::RemoveAllAces](#removeallaces)합니다.  
  
##  <a name="getacecount"></a>  CDacl::GetAceCount  
 Ace (액세스 제어 항목)의 수를 반환 된 `CDacl` 개체입니다.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 에 포함 된 Ace의 수를 반환 된 `CDacl` 개체입니다.  
  
##  <a name="operator_eq"></a>  CDacl::operator =  
 대입 연산자입니다.  
  
```
CDacl& operator= (const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 ACL (액세스 제어 목록)을 기존 개체에 할당 합니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된에 대 한 참조를 반환 `CDacl` 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 함수에 DACL (임의 액세스 제어 목록)만 전달 해야 합니다. SACL (시스템 액세스 제어 목록)를 전달 합니다.이 함수에이 ASSERT 디버그 빌드에서 하지만 릴리스 빌드에 없음 오류가 발생 합니다.  
  
##  <a name="removeace"></a>  CDacl::RemoveAce  
 특정 ACE (액세스 제어 항목)에서 제거 된 `CDacl` 개체입니다.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 제거 하려면 ACE 항목 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는에서 파생 된 [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)합니다.  
  
##  <a name="removeallaces"></a>  CDacl::RemoveAllAces  
 에 포함 된 Ace (액세스 제어 항목)를 모두 제거는 `CDacl` 개체입니다.  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>설명  
 제거 모든 **ACE** (액세스 제어 항목) 구조 (있는 경우)에 `CDacl` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Security 샘플](../../visual-cpp-samples.md)   
 [CAcl 클래스](../../atl/reference/cacl-class.md)   
 [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [Ace](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [보안 전역 함수](../../atl/reference/security-global-functions.md)
