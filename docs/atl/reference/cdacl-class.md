---
title: "CDacl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 23
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
ms.openlocfilehash: bb418919c26e3c0054a151b859cdf3f31c5d73a8
ms.lasthandoff: 02/24/2017

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
|[CDacl:: ~ CDacl](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDacl::AddAllowedAce](#addallowedace)|허용 되는 ACE (액세스 제어 항목)에 추가 된 `CDacl` 개체입니다.|  
|[CDacl::AddDeniedAce](#adddeniedace)|추가 하도록 거부 ACE는 `CDacl` 개체입니다.|  
|[CDacl::GetAceCount](#getacecount)|Ace (액세스 제어 항목)의 수를 반환 된 `CDacl` 개체입니다.|  
|[CDacl::RemoveAce](#removeace)|특정 ACE (액세스 제어 항목)에서 제거 된 `CDacl` 개체입니다.|  
|[CDacl::RemoveAllAces](#removeallaces)|에 포함 된 Ace를 모두 제거는 `CDacl` 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CDacl::operator =](#operator_eq)|대입 연산자입니다.|  
  
## <a name="remarks"></a>주의  
 개체의 보안 설명자는 DACL을 포함할 수 있습니다. DACL에는&0; 개 이상의 Ace (액세스 제어 항목 사용자 및 그룹 개체를 액세스할 수 있는 사용자를 식별 하 는) 포함 되어 있습니다. DACL 비어 있는 경우 (즉, 포함 된&0; Ace)에 액세스할 수 없는 명시적으로 허용 되 면 암시적으로 액세스할 수 있도록 합니다. 그러나 개체의 보안 설명자는 DACL이 없는 경우 개체 보호 되지 않음 및 모든 사용자에 대 한 전체 액세스 합니다.  
  
 개체의 소유자 이거나 READ_CONTROL 개체에 액세스할 수 있는 경우에 개체의 DACL을 검색 하려면 있습니다. 개체의 DACL을 변경 하려면 WRITE_DAC 개체에 액세스할 수 있어야 합니다.  
  
 만들기, 추가, 제거 및 삭제에서 Ace를 제공 하는 클래스 메서드를 사용 하 여는 `CDacl` 개체입니다. 참고 항목 [AtlGetDacl](http://msdn.microsoft.com/library/a0973648-0d46-4c1a-914f-bda861fe5d19) 및 [AtlSetDacl](http://msdn.microsoft.com/library/eb88ccb6-1f1b-444d-b0c9-8d5cd0dd6c0b)합니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오. [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CDacl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h  
  
##  <a name="addallowedace"></a>CDacl::AddAllowedAce  
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
 액세스 권한 허용 하는 마스크를 지정 지정 된 `CSid` 개체입니다.  
  
 `AceFlags`  
 ACE 상속을 제어 하는 비트 플래그 집합입니다.  
  
 `pObjectType`  
 개체 형식입니다.  
  
 `pInheritedObjectType`  
 상속 된 개체 유형입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** ACE에 추가 된 경우는 `CDacl` 개체 **false** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 A `CDacl`&0; 개 이상의 Ace (액세스 제어 항목 사용자 및 그룹 개체를 액세스할 수 있는 사용자를 식별 하 는) 개체에 포함 되어 있습니다. 에 대 한 액세스를 허용 하는 ACE를 추가 하는이 메서드는 `CDacl` 개체입니다.  
  
> [!NOTE]
>  두 번째 형태 `AddAllowedAce` Windows 2000에서 사용할 수 있으며 나중에 불과합니다.  
  
 참조 [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) 에 대 한 설명은에 설정 될 수 있는 다양 한 플래그는 `AceFlags` 매개 변수입니다.  
  
##  <a name="adddeniedace"></a>CDacl::AddDeniedAce  
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
 액세스 권한 거부할의 마스크를 지정 지정 된 `CSid` 개체입니다.  
  
 `AceFlags`  
 ACE 상속을 제어 하는 비트 플래그 집합입니다. 기본값은 메서드의 첫 번째 형태는 0입니다.  
  
 `pObjectType`  
 개체 형식입니다.  
  
 `pInheritedObjectType`  
 상속 된 개체 유형입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** ACE에 추가 된 경우는 `CDacl` 개체 **false** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 A `CDacl`&0; 개 이상의 Ace (액세스 제어 항목 사용자 및 그룹 개체를 액세스할 수 있는 사용자를 식별 하 는) 개체에 포함 되어 있습니다. 에 대 한 액세스를 거부 하는 ACE를 추가 하는이 메서드는 `CDacl` 개체입니다.  
  
> [!NOTE]
>  두 번째 형태 `AddDeniedAce` Windows 2000에서 사용할 수 있으며 나중에 불과합니다.  
  
 참조 [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) 에 대 한 설명은에 설정 될 수 있는 다양 한 플래그는 `AceFlags` 매개 변수입니다.  
  
##  <a name="cdacl"></a>CDacl::CDacl  
 생성자입니다.  
  
```
CDacl (const ACL& rhs) throw(...);  
CDacl () throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 기존 **ACL** (액세스 제어 목록) 구조입니다.  
  
### <a name="remarks"></a>주의  
 `CDacl` 개체가 생성 될 수 필요에 따라 기존를 사용 하 여 **ACL** 구조입니다. DACL (임의 액세스 제어 목록)만 해야 하 고는 SACL (시스템 액세스 제어 목록)이이 매개 변수로 전달 해야 합니다. 디버그 빌드에는 SACL 전달 어설션을 발생 합니다. 릴리스 빌드에서 SACL을 전달 하면 Ace (액세스 제어 항목)는 acl에 무시할 수 및 오류가 발생 하지 것입니다.  
  
##  <a name="dtor"></a>CDacl:: ~ CDacl  
 소멸자입니다.  
  
```
~CDacl () throw();
```  
  
### <a name="remarks"></a>주의  
 소멸자를 사용 하 여 모든 Ace (액세스 제어 항목)를 포함 하 여 개체에 가져온 모든 리소스를 해제 [CDacl::RemoveAllAces](#removeallaces)합니다.  
  
##  <a name="getacecount"></a>CDacl::GetAceCount  
 Ace (액세스 제어 항목)의 수를 반환 된 `CDacl` 개체입니다.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 에 포함 된 Ace의 수를 반환 된 `CDacl` 개체입니다.  
  
##  <a name="operator_eq"></a>CDacl::operator =  
 대입 연산자입니다.  
  
```
CDacl& operator= (const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 기존 개체에 할당할 ACL (액세스 제어 목록).  
  
### <a name="return-value"></a>반환 값  
 업데이트에 대 한 참조를 반환 합니다. `CDacl` 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 DACL (임의 액세스 제어 목록)만 전달 해야 합니다. SACL (시스템 액세스 제어 목록)을 전달이 함수를 한 어설션을 디버그 빌드에서 되지만 릴리스 빌드에 없음 오류가 발생 합니다.  
  
##  <a name="removeace"></a>CDacl::RemoveAce  
 특정 ACE (액세스 제어 항목)에서 제거 된 `CDacl` 개체입니다.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 제거할 ACE 엔트리의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는에서 파생 된 [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)합니다.  
  
##  <a name="removeallaces"></a>CDacl::RemoveAllAces  
 에 포함 된 Ace (액세스 제어 항목)를 모두 제거는 `CDacl` 개체입니다.  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>주의  
 제거 모든 **ACE** (액세스 제어 항목) 구조 (있는 경우)에 `CDacl` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [보안 샘플](../../visual-cpp-samples.md)   
 [CAcl 클래스](../../atl/reference/cacl-class.md)   
 [Acl](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [Ace](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [보안 전역 함수](../../atl/reference/security-global-functions.md)

