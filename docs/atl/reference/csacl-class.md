---
title: "CSacl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CSacl
- ATL::CSacl
- CSacl
dev_langs:
- C++
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
caps.latest.revision: 22
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 50f10ab765648d4b587a941ccf24726b53f14c88
ms.lasthandoff: 02/24/2017

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
|[CSacl:: ~ CSacl](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSacl::AddAuditAce](#addauditace)|감사 액세스 제어 항목 (ACE)에 추가 된 `CSacl` 개체입니다.|  
|[CSacl::GetAceCount](#getacecount)|액세스 제어 항목 (Ace)의 수를 반환 된 `CSacl` 개체입니다.|  
|[CSacl::RemoveAce](#removeace)|특정 ACE (액세스 제어 항목)에서 제거 된 **CSacl** 개체입니다.|  
|[CSacl::RemoveAllAces](#removeallaces)|에 포함 된 Ace를 모두 제거는 `CSacl` 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CSacl::operator =](#operator_eq)|대입 연산자입니다.|  
  
## <a name="remarks"></a>주의  
 SACL이 도메인 컨트롤러의 보안 이벤트 로그에 감사 레코드를 생성 하는 액세스 시도의 유형을 지정 하는 액세스 제어 항목 (Ace)를 포함 합니다. Note SACL 액세스 시도가 발생 하는 도메인 컨트롤러에 대해서만, 개체의 복제본을 포함 하는 모든 도메인 컨트롤러에 없는 로그 항목을 생성 합니다.  
  
 를 설정 하거나 개체의 보안 설명자의 SACL을 검색 하려면 SE_SECURITY_NAME 권한은 요청 하는 스레드의의 액세스 토큰에 설정 해야 합니다. 관리자 그룹에이 권한은 기본적으로 부여 되 고 다른 사용자 또는 그룹에 부여할 수 있습니다. 필요 하면 권한 부여 된 것은 아닙니다 필요: 권한으로 정의 된 작업을 수행 하려면 권한을 설정 해야 보안 액세스 토큰에 적용 하기 위해. 모델 권한을 특정 시스템 작업에 대해서만 사용 하도록 설정 되어 다음 더 이상 필요 없는 경우 사용할 수 없습니다. 참조 [AtlGetSacl](http://msdn.microsoft.com/library/1d69611f-d8a7-467b-9d57-cbe2f1610bf8) 및 [AtlSetSacl](http://msdn.microsoft.com/library/54daab9a-8c69-45fd-86c4-18eb30d59547) SE_SECURITY_NAME 사용에 대 한 예제입니다.  
  
 추가, 제거, 작성 및 삭제에서 Ace를 제공 하는 클래스 메서드를 사용 하 여 **SACL** 개체입니다. 참고 항목 [AtlGetSacl](http://msdn.microsoft.com/library/1d69611f-d8a7-467b-9d57-cbe2f1610bf8) 및 [AtlSetSacl](http://msdn.microsoft.com/library/54daab9a-8c69-45fd-86c4-18eb30d59547)합니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오. [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CSacl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h  
  
##  <a name="a-nameaddauditacea--csacladdauditace"></a><a name="addauditace"></a>CSacl::AddAuditAce  
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
 감사에 대 한 액세스의 마스크를 지정 지정 된 `CSid` 개체입니다.  
  
 `bSuccess`  
 허용 된 액세스 시도 감사할 수 있는지 여부를 지정 합니다. 이 플래그를 사용 감사; true로 설정 그렇지 않으면 false로 설정 합니다.  
  
 *bFailure*  
 거부 된 액세스 시도 감사할 수 있는지 여부를 지정 합니다. 이 플래그를 사용 감사; true로 설정 그렇지 않으면 false로 설정 합니다.  
  
 `AceFlags`  
 ACE 상속을 제어 하는 비트 플래그 집합입니다.  
  
 `pObjectType`  
 개체 형식입니다.  
  
 `pInheritedObjectType`  
 상속 된 개체 유형입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** ACE에 추가 된 경우는 `CSacl` 개체 **false** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 A `CSacl` 개체 액세스 시도 보안 이벤트 로그에서 감사 레코드를 생성 하는 유형을 지정 하는 액세스 제어 항목 (Ace)를 포함 합니다. 이 메서드를 추가 하도록 ACE는 `CSacl` 개체입니다. 두 번째 형태 `AddAuditAce` Windows 2000에서 사용할 수 있으며 나중에 불과합니다.  
  
 참조 [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) 에 대 한 설명은에 설정 될 수 있는 다양 한 플래그는 `AceFlags` 매개 변수입니다.  
  
##  <a name="a-namecsacla--csaclcsacl"></a><a name="csacl"></a>CSacl::CSacl  
 생성자입니다.  
  
```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 기존 **ACL** (액세스 제어 목록) 구조입니다.  
  
### <a name="remarks"></a>주의  
 `CSacl` 개체가 생성 될 수 필요에 따라 기존를 사용 하 여 **ACL** 구조입니다. 이 매개 변수는 임의 액세스 제어 목록 (DACL) 및 시스템 액세스 제어 목록 (SACL) 인지 확인 합니다. 디버그 빌드에 DACL 제공 되는 경우에 어설션을 발생 합니다. 릴리스 빌드에서 DACL에서 모든 항목은 무시 됩니다.  
  
##  <a name="a-namedtora--csaclcsacl"></a><a name="dtor"></a>CSacl:: ~ CSacl  
 소멸자입니다.  
  
```
~CSacl() throw();
```  
  
### <a name="remarks"></a>주의  
 소멸자는 모든 액세스 제어 항목 (Ace)를 포함 하 여 개체에 의해 획득 하는 모든 리소스를 해제 합니다.  
  
##  <a name="a-namegetacecounta--csaclgetacecount"></a><a name="getacecount"></a>CSacl::GetAceCount  
 액세스 제어 항목 (Ace)의 수를 반환 된 `CSacl` 개체입니다.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 에 포함 된 Ace의 수를 반환 된 `CSacl` 개체입니다.  
  
##  <a name="a-nameoperatoreqa--csacloperator-"></a><a name="operator_eq"></a>CSacl::operator =  
 대입 연산자입니다.  
  
```
CSacl& operator=(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 **ACL** (액세스 제어 목록)을 기존 개체를 할당 합니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트에 대 한 참조를 반환 합니다. `CSacl` 개체입니다. 확인 된 **ACL** 매개 변수는 실제로 시스템 액세스 제어 목록 (SACL)와 임의 액세스 제어 목록 (DACL). 어설션을 발생 하며 디버그 빌드 및 릴리스 빌드에서 **ACL** 매개 변수는 무시 됩니다.  
  
##  <a name="a-nameremoveacea--csaclremoveace"></a><a name="removeace"></a>CSacl::RemoveAce  
 특정 ACE (액세스 제어 항목)에서 제거 된 **CSacl** 개체입니다.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 제거할 ACE 엔트리의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는에서 파생 된 [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)합니다.  
  
##  <a name="a-nameremoveallacesa--csaclremoveallaces"></a><a name="removeallaces"></a>CSacl::RemoveAllAces  
 에 포함 된 액세스 제어 항목 (Ace)를 모두 제거는 `CSacl` 개체입니다.  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>주의  
 제거 모든 **ACE** (있는 경우) 구조는 `CSacl` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAcl 클래스](../../atl/reference/cacl-class.md)   
 [Acl](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [Ace](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [보안 전역 함수](../../atl/reference/security-global-functions.md)

