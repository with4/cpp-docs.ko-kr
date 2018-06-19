---
title: CSacl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSacl
- ATLSECURITY/ATL::CSacl
- ATLSECURITY/ATL::CSacl::CSacl
- ATLSECURITY/ATL::CSacl::AddAuditAce
- ATLSECURITY/ATL::CSacl::GetAceCount
- ATLSECURITY/ATL::CSacl::RemoveAce
- ATLSECURITY/ATL::CSacl::RemoveAllAces
dev_langs:
- C++
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 116e66d36dde016ef902a0b345eec33e46177b6c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363586"
---
# <a name="csacl-class"></a>CSacl 클래스
이 클래스는 SACL (시스템 액세스 제어 목록) 구조에 대 한 래퍼입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CSacl : public CAcl
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSacl::CSacl](#csacl)|생성자입니다.|  
|[CSacl::~CSacl](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSacl::AddAuditAce](#addauditace)|감사 액세스 제어 항목 (ACE)에 추가 된 `CSacl` 개체입니다.|  
|[CSacl::GetAceCount](#getacecount)|액세스 제어 (Ace) 항목의 수를 반환 된 `CSacl` 개체입니다.|  
|[CSacl::RemoveAce](#removeace)|특정 ACE (액세스 제어 항목)에서 제거 된 **CSacl** 개체입니다.|  
|[CSacl::RemoveAllAces](#removeallaces)|에 포함 된 Ace를 모두 제거는 `CSacl` 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CSacl::operator =](#operator_eq)|대입 연산자입니다.|  
  
## <a name="remarks"></a>설명  
 SACL은 액세스 시도 도메인 컨트롤러의 보안 이벤트 로그에 감사 레코드를 생성 하는 유형을 지정 하는 액세스 제어 항목 (Ace)를 포함 합니다. Note SACL 액세스 시도가 발생 한 도메인 컨트롤러 에서만, 개체의 복제본을 포함 하는 모든 도메인 컨트롤러에 없는 로그 항목을 생성 합니다.  
  
 를 설정 하거나 개체의 보안 설명자의 SACL을 검색 하려면 se_security_name 권한을 권한은 요청 하는 스레드의의 액세스 토큰에서 설정 해야 합니다. 관리자 그룹에이 사용 권한은 기본적으로 부여 되 고 다른 사용자 또는 그룹에 부여할 수 있습니다. 권한 부여를 것 하기만: 권한을 적용 하기 위해 보안 액세스 토큰에서 활성화 해야 권한으로 정의 된 작업을 수행 하려면. 모델은 권한을 특정 시스템 작업에 대해서만 사용 하도록 설정 되어 다음 더 이상 필요 없는 경우를 사용할 수 없습니다. 참조 [AtlGetSacl](security-global-functions.md#atlgetsacl) 및 [AtlSetSacl](security-global-functions.md#atlsetsacl) se_security_name 권한을 사용 하도록 설정에 대 한 예제입니다.  
  
 추가, 제거,를 만들고 삭제 하에서 Ace가 제공 하는 클래스 메서드를 사용 하 여는 **SACL** 개체입니다. 참고 항목 [AtlGetSacl](security-global-functions.md#atlgetsacl) 및 [AtlSetSacl](security-global-functions.md#atlsetsacl)합니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오. [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows sdk에서입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CSacl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h  
  
##  <a name="addauditace"></a>  CSacl::AddAuditAce  
 감사 액세스 제어 항목 (ACE)에 추가 된 `CSacl` 개체입니다.  
  
```
bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags = 0) throw(...);

bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rSid`  
 [CSid](../../atl/reference/csid-class.md) 개체입니다.  
  
 `AccessMask`  
 감사에 대 한 액세스 권한의 마스크를 지정에 대 한 지정 된 `CSid` 개체입니다.  
  
 `bSuccess`  
 허용 되는 액세스 시도를 감사할 수 있는지 지정 합니다. Enable 감사; true 이면이 플래그를 설정 그렇지 않으면 false로 설정 합니다.  
  
 *bFailure*  
 감사할 시도 대 한 액세스가 거부 되는지 여부를 지정 합니다. Enable 감사; true 이면이 플래그를 설정 그렇지 않으면 false로 설정 합니다.  
  
 `AceFlags`  
 집합 ACE 상속을 제어 하는 비트 플래그입니다.  
  
 `pObjectType`  
 개체 형식입니다.  
  
 `pInheritedObjectType`  
 상속 된 개체 유형입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** ACE에 추가 되 면는 `CSacl` 개체 **false** 실패 합니다.  
  
### <a name="remarks"></a>설명  
 A `CSacl` 개체에 보안 이벤트 로그에서 감사 레코드를 생성 하는 액세스 시도의 유형을 지정 하는 액세스 제어 항목 (Ace)이 포함 되어 있습니다. 이 메서드를 추가 하려면 ACE는 `CSacl` 개체입니다.  
  
 참조 [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) 에 대 한 설명은에서 설정할 수 있는 다양 한 플래그는 `AceFlags` 매개 변수입니다.  
  
##  <a name="csacl"></a>  CSacl::CSacl  
 생성자입니다.  
  
```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 기존 **ACL** (액세스 제어 목록) 구조입니다.  
  
### <a name="remarks"></a>설명  
 `CSacl` 개체 수 수 필요에 따라 사용 하 여 만든 기존 **ACL** 구조입니다. 이 매개 변수는 임의 액세스 제어 목록 (DACL) 및 SACL ()는 시스템 액세스 제어 목록 인지 확인 합니다. 디버그 빌드에 DACL를 제공 하는 경우에 어설션을 발생 합니다. 릴리스 빌드에서 DACL에서 모든 항목은 무시 됩니다.  
  
##  <a name="dtor"></a>  CSacl::~CSacl  
 소멸자입니다.  
  
```
~CSacl() throw();
```  
  
### <a name="remarks"></a>설명  
 소멸자는 모든 액세스 제어 (Ace) 항목을 포함 하는 개체에 의해 획득 하는 모든 리소스를 해제 합니다.  
  
##  <a name="getacecount"></a>  CSacl::GetAceCount  
 액세스 제어 (Ace) 항목의 수를 반환 된 `CSacl` 개체입니다.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 에 포함 된 Ace의 수를 반환 된 `CSacl` 개체입니다.  
  
##  <a name="operator_eq"></a>  CSacl::operator =  
 대입 연산자입니다.  
  
```
CSacl& operator=(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 **ACL** (액세스 제어 목록)을 기존 개체에 할당할 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된에 대 한 참조를 반환 `CSacl` 개체입니다. 확인 된 **ACL** 매개 변수는 실제로 시스템 액세스 제어 목록 (SACL)와 임의 액세스 제어 목록 (DACL). 디버그 빌드에서만 어설션을 발생 하 고 릴리스 빌드에서 **ACL** 매개 변수는 무시 됩니다.  
  
##  <a name="removeace"></a>  CSacl::RemoveAce  
 특정 ACE (액세스 제어 항목)에서 제거 된 **CSacl** 개체입니다.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 제거 하려면 ACE 항목 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는에서 파생 된 [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)합니다.  
  
##  <a name="removeallaces"></a>  CSacl::RemoveAllAces  
 에 포함 된 액세스 제어 항목 (Ace)를 모두 제거는 `CSacl` 개체입니다.  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>설명  
 제거 모든 **ACE** (있는 경우) 구조에서 `CSacl` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAcl 클래스](../../atl/reference/cacl-class.md)   
 [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [Ace](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [보안 전역 함수](../../atl/reference/security-global-functions.md)
