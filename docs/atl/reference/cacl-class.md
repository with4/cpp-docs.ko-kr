---
title: "CAcl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAcl
- ATLSECURITY/ATL::CAcl
- ATLSECURITY/ATL::CAcl::CAccessMaskArray
- ATLSECURITY/ATL::CAcl::CAceFlagArray
- ATLSECURITY/ATL::CAcl::CAceTypeArray
- ATLSECURITY/ATL::CAcl::CAcl
- ATLSECURITY/ATL::CAcl::GetAceCount
- ATLSECURITY/ATL::CAcl::GetAclEntries
- ATLSECURITY/ATL::CAcl::GetAclEntry
- ATLSECURITY/ATL::CAcl::GetLength
- ATLSECURITY/ATL::CAcl::GetPACL
- ATLSECURITY/ATL::CAcl::IsEmpty
- ATLSECURITY/ATL::CAcl::IsNull
- ATLSECURITY/ATL::CAcl::RemoveAce
- ATLSECURITY/ATL::CAcl::RemoveAces
- ATLSECURITY/ATL::CAcl::SetEmpty
- ATLSECURITY/ATL::CAcl::SetNull
dev_langs:
- C++
helpviewer_keywords:
- CAcl class
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
caps.latest.revision: 21
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
ms.openlocfilehash: 52de083664c2e9ca00a140450cb43372aff28428
ms.lasthandoff: 02/24/2017

---
# <a name="cacl-class"></a>CAcl 클래스
이 클래스는에 대 한 래퍼는 `ACL` (액세스 제어 목록) 구조입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CAcl
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CAcl::CAccessMaskArray](#caccessmaskarray)|배열을 `ACCESS_MASK`s.|  
|[CAcl::CAceFlagArray](#caceflagarray)|배열을 `BYTE`s.|  
|[CAcl::CAceTypeArray](#cacetypearray)|배열을 `BYTE`s.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAcl::CAcl](#cacl)|생성자입니다.|  
|[CAcl:: ~ CAcl](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAcl::GetAceCount](#getacecount)|항목 (ACE) 개체 액세스 제어의 수를 반환합니다.|  
|[CAcl::GetAclEntries](#getaclentries)|액세스 제어 목록 (ACL) 항목을 검색 된 `CAcl` 개체입니다.|  
|[CAcl::GetAclEntry](#getaclentry)|모든 항목에 대 한 정보를 검색 한 `CAcl` 개체입니다.|  
|[CAcl::GetLength](#getlength)|ACL의 길이 반환 합니다.|  
|[CAcl::GetPACL](#getpacl)|팩 (ACL에 대 한 포인터)를 반환합니다.|  
|[CAcl::IsEmpty](#isempty)|테스트는 `CAcl` 항목에 대 한 개체입니다.|  
|[CAcl::IsNull](#isnull)|상태를 반환 하는 `CAcl` 개체입니다.|  
|[CAcl::RemoveAce](#removeace)|특정 ACE (액세스 제어 항목)에서 제거 된 `CAcl` 개체입니다.|  
|[CAcl::RemoveAces](#removeaces)|모든 Ace (액세스 제어 항목)에서 제거는 `CAcl` 에 적용 되는 지정 된 `CSid`합니다.|  
|[CAcl::SetEmpty](#setempty)|표시는 `CAcl` 빈 개체입니다.|  
|[CAcl::SetNull](#setnull)|표시는 `CAcl` 개체를 `NULL`합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CAcl::operator const ACL *](#operator_const_acl__star)|캐스트는 `CAcl` 개체는 `ACL` 구조입니다.|  
|[CAcl::operator =](#operator_eq)|대입 연산자입니다.|  
  
## <a name="remarks"></a>주의  
 **ACL** 구조는 ACL (액세스 제어 목록)의 헤더입니다. ACL에&0; 개 이상의 순차적 목록이 포함 되어 [Ace](http://msdn.microsoft.com/library/windows/desktop/aa374868) (액세스 제어 항목). 0에서 ACL의 개별 Ace 매겨집니다 *n-1*여기서 *n* ACL의 Ace 수입니다. ACL을 편집할 때 응용 프로그램 ACL 내에 있는 액세스 제어 항목 (ACE) 인덱스로 참조 합니다.  
  
 두 가지가 ACL:  
  
-   임의  
  
-   시스템  
  
 개체의 소유자가 임의의 ACL 제어 또는 누구 든 지 부여 **WRITE_DAC** 개체에 액세스할 수 있습니다. 액세스 특정 사용자 및 그룹 개체에 있는 수를 지정 합니다. 예를 들어 파일의 소유자는 수 및 파일에 액세스할 수 있는 사용자 및 그룹을 제어 하는 임의 ACL을 사용할 수 있습니다.  
  
 개체에는 시스템 수준의 보안 관련 정보, 시스템 시스템 관리자에 의해 제어 되는 ACL의 형태로 있을 수도 있습니다. 시스템 ACL 개체에 대 한 액세스 권한을 얻으려고 시도 감사 하려면 시스템 관리자를 허용할 수 있습니다.  
  
 자세한 내용은 다음을 참조 하십시오.는 [ACL](http://msdn.microsoft.com/library/windows/desktop/aa374872) 의 토론의 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오. [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h  
  
##  <a name="caccessmaskarray"></a>CAcl::CAccessMaskArray  
 ACCESS_MASK 개체의 배열입니다.  
  
```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```  
  
### <a name="remarks"></a>주의  
 이 typedef 액세스 제어 항목 (Ace)에 사용 되는 액세스 권한을 저장 하는 사용할 수 있는 배열 형식을 지정 합니다.  
  
##  <a name="caceflagarray"></a>CAcl::CAceFlagArray  
 바이트 배열입니다.  
  
```
typedef CAtlArray<BYTE> CAceFlagArray;
```  
  
### <a name="remarks"></a>주의  
 이 형식 정의 액세스 제어 항목 (ACE) 유형별 제어 플래그를 정의 하는 데 배열 형식을 지정 합니다. 참조는 [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) 가능한 플래그의 전체 목록을 정의 합니다.  
  
##  <a name="cacetypearray"></a>CAcl::CAceTypeArray  
 바이트 배열입니다.  
  
```
typedef CAtlArray<BYTE> CAceTypeArray;
```  
  
### <a name="remarks"></a>주의  
 이 typedef ACCESS_ALLOWED_ACE_TYPE 또는 ACCESS_DENIED_ACE_TYPE 같은 액세스 제어 항목 (ACE) 개체의 특성을 정의 하는 데 배열 형식을 지정 합니다. 참조는 [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) 가능한 형식의 전체 목록을 정의 합니다.  
  
##  <a name="cacl"></a>CAcl::CAcl  
 생성자입니다.  
  
```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 기존 `CAcl` 개체입니다.  
  
### <a name="remarks"></a>주의  
 `CAcl` 개체가 생성 될 수 필요에 따라 기존 `CAcl` 개체입니다.  
  
##  <a name="dtor"></a>CAcl:: ~ CAcl  
 소멸자입니다.  
  
```
virtual ~CAcl() throw();
```  
  
### <a name="remarks"></a>주의  
 소멸자는 개체에 의해 획득 하는 모든 리소스를 해제 합니다.  
  
##  <a name="getacecount"></a>CAcl::GetAceCount  
 항목 (ACE) 개체 액세스 제어의 수를 반환합니다.  
  
```
virtual UINT GetAceCount() const throw() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 ACE 항목 수를 반환 합니다.는 `CAcl` 개체입니다.  
  
##  <a name="getaclentries"></a>CAcl::GetAclEntries  
 액세스 제어 목록 (ACL) 항목을 검색 된 `CAcl` 개체입니다.  
  
```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSids`  
 배열에 대 한 포인터 [CSid](../../atl/reference/csid-class.md) 개체입니다.  
  
 *pAccessMasks*  
 액세스 마스크입니다.  
  
 *pAceTypes*  
 액세스 제어 항목 ( **ACE**) 형식입니다.  
  
 *pAceFlags*  
 **ACE** 플래그입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 상세 배열 매개 변수를 채웁니다. 모든 **ACE** 에 포함 된 개체는 `CAcl` 개체입니다. 해당 특정 배열에 대 한 자세한 내용은 필요 하지 않은 경우 NULL을 사용 합니다.  
  
 각 배열의 내용을 해당 서로 즉, 첫 번째 요소는 `CAccessMaskArray` 의 첫 번째 요소에 해당 하는 배열은 `CSidArray` 배열, 크며 등등 합니다.  
  
 참조 [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) 에 대 한 자세한 내용은 ACE 유형 및 플래그입니다.  
  
##  <a name="getaclentry"></a>CAcl::GetAclEntry  
 모든 항목에는 액세스 제어 목록 (ACL)에 대 한 정보를 검색합니다.  
  
```
void GetAclEntry(
    UINT nIndex,
    CSid* pSid,
    ACCESS_MASK* pMask = NULL,
    BYTE* pType = NULL,
    BYTE* pFlags = NULL,
    GUID* pObjectType = NULL,
    GUID* pInheritedObjectType = NULL) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 검색 하는 ACL 항목을 인덱싱하십시오.  
  
 `pSid`  
 [CSid](../../atl/reference/csid-class.md) ACL 항목에 적용 되는 개체입니다.  
  
 *pMask*  
 액세스를 부여 하거나 거부 권한을 지정 하는 마스크입니다.  
  
 `pType`  
 ACE 형식입니다.  
  
 `pFlags`  
 ACE는 플래그입니다.  
  
 `pObjectType`  
 개체 형식입니다. ACE는 개체의 ACE 아닌 경우 또는 ACE에 개체 유형을 지정 하지 않으면이 GUID_NULL에 설정 됩니다.  
  
 `pInheritedObjectType`  
 상속 된 개체 유형입니다. ACE 개체 ACE 아닌 경우 또는 상속 된 개체의 ACE에 지정 하지 않으면이 GUID_NULL으로 설정 됩니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 개별 ACE 보다 더 많은 정보를 제공 하는 방법에 대 한 정보를 모두 검색 합니다 [CAcl::GetAclEntries](#getaclentries) 혼자 사용할 수 있도록 합니다.  
  
 참조 [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) 에 대 한 자세한 내용은 ACE 유형 및 플래그입니다.  
  
##  <a name="getlength"></a>CAcl::GetLength  
 액세스 제어 목록 (ACL)의 길이 반환 합니다.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 필요한 길이 저장 하는 데 필요한 바이트 단위로 반환 된 **ACL** 구조입니다.  
  
##  <a name="getpacl"></a>CAcl::GetPACL  
 액세스 제어 목록 (ACL)에 대 한 포인터를 반환합니다.  
  
```
const ACL* GetPACL() const throw(...);
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터를 반환 된 **ACL** 구조입니다.  
  
##  <a name="isempty"></a>CAcl::IsEmpty  
 테스트는 `CAcl` 항목에 대 한 개체입니다.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="remarks"></a>주의  
 반환 **true** 경우는 `CAcl` 개체가 NULL 이며에 항목이 없습니다. 반환 **false** 경우는 `CAcl` 개체가 NULL 이거나 또는 하나 이상의 항목을 포함 합니다.  
  
##  <a name="isnull"></a>CAcl::IsNull  
 상태를 반환 하는 `CAcl` 개체입니다.  
  
```
bool IsNull() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 경우는 `CAcl` 개체는 NULL이 고 **false** 그렇지 않은 경우.  
  
##  <a name="operator_const_acl__star"></a>CAcl::operator const ACL *  
 캐스트는 `CAcl` 개체는 **ACL** (액세스 제어 목록) 구조입니다.  
  
```  
operator const ACL *() const throw(...);
```  
  
### <a name="remarks"></a>주의  
 주소를 반환 하는 **ACL** 구조입니다.  
  
##  <a name="operator_eq"></a>CAcl::operator =  
 대입 연산자입니다.  
  
```
CAcl& operator= (const CAcl& rhs) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 `CAcl` 기존 개체를 할당 합니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트에 대 한 참조를 반환 합니다. `CAcl` 개체입니다.  
  
##  <a name="removeace"></a>CAcl::RemoveAce  
 특정 ACE (액세스 제어 항목)에서 제거 된 **CAcl** 개체입니다.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 제거할 ACE 엔트리의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는에서 파생 된 [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)합니다.  
  
##  <a name="removeaces"></a>CAcl::RemoveAces  
 Alls Ace (액세스 제어 항목)에서 제거 된 `CAcl` 에 적용 되는 주어진 `CSid`합니다.  
  
```
bool RemoveAces(const CSid& rSid) throw(...)
```  
  
### <a name="parameters"></a>매개 변수  
 `rSid`  
 `CSid` 개체에 대한 참조입니다.  
  
##  <a name="setempty"></a>CAcl::SetEmpty  
 표시는 `CAcl` 빈 개체입니다.  
  
```
void SetEmpty() throw();
```  
  
### <a name="remarks"></a>주의  
 `CAcl` 비어 또는 NULL로 설정할 수 있습니다: 두 가지 상태는 고유 합니다.  
  
##  <a name="setnull"></a>CAcl::SetNull  
 표시는 `CAcl` NULL로 개체입니다.  
  
```
void SetNull() throw();
```  
  
### <a name="remarks"></a>주의  
 `CAcl` 비어 또는 NULL로 설정할 수 있습니다: 두 가지 상태는 고유 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)   
 [보안 전역 함수](../../atl/reference/security-global-functions.md)

