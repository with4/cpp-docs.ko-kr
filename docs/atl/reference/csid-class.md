---
title: "CSid 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSid
- ATLSECURITY/ATL::CSid
- ATLSECURITY/ATL::CSid::CSidArray
- ATLSECURITY/ATL::CSid::CSid
- ATLSECURITY/ATL::CSid::AccountName
- ATLSECURITY/ATL::CSid::Domain
- ATLSECURITY/ATL::CSid::EqualPrefix
- ATLSECURITY/ATL::CSid::GetLength
- ATLSECURITY/ATL::CSid::GetPSID
- ATLSECURITY/ATL::CSid::GetPSID_IDENTIFIER_AUTHORITY
- ATLSECURITY/ATL::CSid::GetSubAuthority
- ATLSECURITY/ATL::CSid::GetSubAuthorityCount
- ATLSECURITY/ATL::CSid::IsValid
- ATLSECURITY/ATL::CSid::LoadAccount
- ATLSECURITY/ATL::CSid::Sid
- ATLSECURITY/ATL::CSid::SidNameUse
dev_langs:
- C++
helpviewer_keywords:
- CSid class
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
caps.latest.revision: 24
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
ms.openlocfilehash: ceb0ab95d18e1336584eab45bc00ce769efd7384
ms.lasthandoff: 02/24/2017

---
# <a name="csid-class"></a>CSid 클래스
이 클래스는에 대 한 래퍼는 `SID` (보안 식별자) 구조입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CSid
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CSid::CSidArray](#csidarray)|`CSid` 개체의 배열입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSid::CSid](#csid)|생성자입니다.|  
|[CSid:: ~ CSid](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSid::AccountName](#accountname)|와 연결 된 계정의 이름을 반환 하는 `CSid` 개체입니다.|  
|[CSid::Domain](#domain)|연결 된 도메인의 이름을 반환 하는 `CSid` 개체입니다.|  
|[CSid::EqualPrefix](#equalprefix)|테스트 `SID` 같은지 (보안 식별자) 접두사입니다.|  
|[CSid::GetLength](#getlength)|길이 반환 된 `CSid` 개체입니다.|  
|[CSid::GetPSID](#getpsid)|에 대 한 포인터를 반환 합니다.는 `SID` 구조입니다.|  
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|에 대 한 포인터를 반환 된 **SID_IDENTIFIER_AUTHORITY** 구조입니다.|  
|[CSid::GetSubAuthority](#getsubauthority)|에 지정 된 subauthority 반환는 **SID** 구조입니다.|  
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|Subauthority 수를 반환 합니다.|  
|[CSid::IsValid](#isvalid)|테스트는 `CSid` 유효성에 대 한 개체입니다.|  
|[CSid::LoadAccount](#loadaccount)|업데이트는 `CSid` 계정 이름 및 도메인 또는 기존 지정 된 개체 `SID` 구조입니다.|  
|[CSid::Sid](#sid)|ID 문자열을 반환 합니다.|  
|[CSid::SidNameUse](#sidnameuse)|상태에 대 한 설명을 반환는 `CSid` 개체입니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자 =](#operator_eq)|대입 연산자입니다.|  
|[연산자 const SID *](#operator_const_sid__star)|캐스트는 `CSid` 개체에 대 한 포인터는 `SID` 구조입니다.|  
  
### <a name="global-operators"></a>전역 연산자  
  
|||  
|-|-|  
|[연산자 = =](#operator_eq_eq)|두 개의 보안 설명자 개체가 같은지를 테스트합니다.|  
|[연산자! =](#operator_neq)|두 개의 보안 설명자 개체가 다른 지 테스트합니다.|  
|[연산자\<](#operator_lt_)|두 가지 보안 설명자 개체의 상대 값을 비교합니다.|  
|[연산자 >](#operator_gt_)|두 가지 보안 설명자 개체의 상대 값을 비교합니다.|  
|[연산자\<=](#operator_lt__eq)|두 가지 보안 설명자 개체의 상대 값을 비교합니다.|  
|[연산자 > =](#operator_gt__eq)|두 가지 보안 설명자 개체의 상대 값을 비교합니다.|  
  
## <a name="remarks"></a>주의  
 `SID` 구조는 사용자 또는 그룹을 고유 하 게 식별 하는 데 사용 되는 가변 길이 구조입니다.  
  
 응용 프로그램을 수정 하지 않아야는 `SID` 구조를 직접 않고 대신 사용 하 여이 래퍼 클래스에서 제공 하는 방법입니다. 참고 항목 [AtlGetOwnerSid](http://msdn.microsoft.com/library/0e3a2606-74b8-4412-9803-bb437e22da85), [AtlSetGroupSid](http://msdn.microsoft.com/library/83531d32-11ab-4a68-a3c6-1bfa54ab8dfa), [AtlGetGroupSid](http://msdn.microsoft.com/library/8e7ec6b9-15c8-4a8a-977e-1e4c853d0be7), 및 [AtlSetOwnerSid](http://msdn.microsoft.com/library/3a8abb76-1d2c-465d-a5e8-62a12a3c37f3)합니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오. [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h  
  
##  <a name="accountname"></a>CSid::AccountName  
 와 연결 된 계정의 이름을 반환 하는 `CSid` 개체입니다.  
  
```
LPCTSTR AccountName() const throw(...);
```  
  
### <a name="return-value"></a>반환 값  
 반환 된 `LPCTSTR` 계정의 이름을 가리킵니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 지정 된 이름을 찾으려고 `SID` (보안 식별자)입니다. 자세한 내용은 참조 하십시오. [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166)합니다.  
  
 에 대 한 계정 이름이 없는 경우는 `SID` 를 찾을 수 있는 `AccountName` 빈 문자열을 반환 합니다. 네트워크 제한 시간 하이 메서드는 이름을 찾는 수 없는 경우 발생할 수 있습니다. 또한는 로그온과 같은 해당 계정 이름이 없는 보안 식별자에 대 한 발생 `SID` 로그온 세션을 식별 하는 합니다.  
  
##  <a name="csid"></a>CSid::CSid  
 생성자입니다.  
  
```
CSid() throw();
CSid(const SID& rhs) throw(...);
CSid(const CSid& rhs) throw(...);

CSid(
    const SID_IDENTIFIER_AUTHORITY& IdentifierAuthority,
    BYTE nSubAuthorityCount,
    ...) throw(...);

explicit CSid(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

explicit CSid(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 기존 `CSid` 개체 또는 `SID` (보안 식별자) 구조입니다.  
  
 *IdentifierAuthority*  
 인증 기관입니다.  
  
 *nSubAuthorityCount*  
 Subauthority 수입니다.  
  
 `pszAccountName`  
 계정 이름입니다.  
  
 `pszSystem`  
 시스템 이름입니다. 이 문자열에는 원격 컴퓨터의 이름일 수 있습니다. 이 문자열이 NULL 이면 로컬 시스템 대신 사용 됩니다.  
  
 `pSid`  
 에 대 한 포인터는 `SID` 구조입니다.  
  
### <a name="remarks"></a>주의  
 생성자가 초기화 하는 `CSid` 개체, 내부 데이터 멤버를 설정 *SidTypeInvalid*, 또는 기존 설정을 복사 하 여 `CSid`, `SID`, 또는 기존 계정.  
  
 초기화가 실패 하면 생성자에서 throw 한 [CAtlException 클래스](../../atl/reference/catlexception-class.md)합니다.  
  
##  <a name="dtor"></a>CSid:: ~ CSid  
 소멸자입니다.  
  
```
virtual ~CSid() throw();
```  
  
### <a name="remarks"></a>주의  
 소멸자는 개체에 의해 획득 하는 모든 리소스를 해제 합니다.  
  
##  <a name="csidarray"></a>CSid::CSidArray  
 배열을 [CSid](../../atl/reference/csid-class.md) 개체입니다.  
  
```
typedef CAtlArray<CSid> CSidArray;
```  
  
### <a name="remarks"></a>주의  
 이 typedef에는 ACL (액세스 제어 목록)에서 보안 식별자를 검색 하는 데 사용할 수 있는 배열 형식을 지정 합니다. 참조 [CAcl::GetAclEntries](../../atl/reference/cacl-class.md#getaclentries)합니다.  
  
##  <a name="domain"></a>CSid::Domain  
 연결 된 도메인의 이름을 반환 하는 `CSid` 개체입니다.  
  
```
LPCTSTR Domain() const throw(...);
```  
  
### <a name="return-value"></a>반환 값  
 반환 된 `LPCTSTR` 도메인을 가리킵니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 지정 된 이름을 찾으려고 `SID` (보안 식별자)입니다. 자세한 내용은 참조 하십시오. [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166)합니다.  
  
 에 대 한 계정 이름이 없는 경우는 `SID` 를 찾을 수 있는 **도메인** 빈 문자열로 도메인을 반환 합니다. 네트워크 제한 시간 하이 메서드는 이름을 찾는 수 없는 경우 발생할 수 있습니다. 또한는 로그온과 같은 해당 계정 이름이 없는 보안 식별자에 대 한 발생 `SID` 로그온 세션을 식별 하는 합니다.  
  
##  <a name="equalprefix"></a>CSid::EqualPrefix  
 테스트 `SID` 같은지 (보안 식별자) 접두사입니다.  
  
```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 `SID` (보안 식별자) 구조 또는 `CSid` 비교할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 성공 **false** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 참조 [EqualPrefixSid](http://msdn.microsoft.com/library/windows/desktop/aa446621) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 대 한 자세한 내용은 합니다.  
  
##  <a name="getlength"></a>CSid::GetLength  
 길이 반환 된 `CSid` 개체입니다.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 바이트의 길이 반환 합니다.는 `CSid` 개체입니다.  
  
### <a name="remarks"></a>주의  
 하는 경우는 `CSid` 구조가 올바르지 않습니다, 반환 값은 정의 되지 않습니다. 호출 하기 전에 `GetLength`를 사용 하 여는 [CSid::IsValid](#isvalid) 멤버 함수를 확인 하는 `CSid` 유효 합니다.  
  
> [!NOTE]
>  함수는 ASSERT 경우 발생 하는 디버그 빌드에서 `CSid` 개체가 유효 하지 않습니다.  
  
##  <a name="getpsid"></a>CSid::GetPSID  
 에 대 한 포인터를 반환 합니다.는 `SID` (보안 식별자) 구조입니다.  
  
```
const SID* GetPSID() const throw(...);
```  
  
### <a name="return-value"></a>반환 값  
 주소를 반환 하는 `CSid` 개체의 기본 `SID` 구조입니다.  
  
##  <a name="getpsid_identifier_authority"></a>CSid::GetPSID_IDENTIFIER_AUTHORITY  
 에 대 한 포인터를 반환 된 **SID_IDENTIFIER_AUTHORITY** 구조입니다.  
  
```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 주소를 반환 메서드가 성공 하는 경우는 **SID_IDENTIFIER_AUTHORITY** 구조입니다. 실패 한 경우 반환 값은 정의 되지 않습니다. 경우 오류가 발생할 수 있습니다는 `CSid` 개체가 유효 하지는 쿼리에서 [CSid::IsValid](#isvalid) 메서드가 반환 **false**합니다. 함수 `GetLastError` 확장된 오류 정보에 대해 호출할 수 있습니다.  
  
> [!NOTE]
>  함수는 ASSERT 경우 발생 하는 디버그 빌드에서 `CSid` 개체가 유효 하지 않습니다.  
  
##  <a name="getsubauthority"></a>CSid::GetSubAuthority  
 에 지정 된 subauthority 반환는 `SID` (보안 식별자) 구조입니다.  
  
```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *nSubAuthority*  
 Subauthority 합니다.  
  
### <a name="return-value"></a>반환 값  
 참조 subauthority 반환 *nSubAuthority 합니다.* Subauthority 값이 상대 식별자 (RID).  
  
### <a name="remarks"></a>주의  
 *nSubAuthority* 매개 변수는 메서드가 반환할 subauthority 배열 요소를 식별 하는 인덱스 값을 지정 합니다. 메서드는이 값에 없는 유효성 검사 테스트를 수행합니다. 응용 프로그램에서 호출할 수 [CSid::GetSubAuthorityCount](#getsubauthoritycount) 를 사용할 수 있는 값의 범위를 검색 합니다.  
  
> [!NOTE]
>  함수는 ASSERT 경우 발생 하는 디버그 빌드에서 `CSid` 개체가 유효 하지 않습니다.  
  
##  <a name="getsubauthoritycount"></a>CSid::GetSubAuthorityCount  
 Subauthority 수를 반환 합니다.  
  
```
UCHAR GetSubAuthorityCount() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하는 경우 반환 값은 subauthority 수입니다.  
  
 메서드가 실패 하면 반환 값은 정의 되지 않습니다. 메서드가 실패 하는 경우는 `CSid` 개체가 유효 하지 않습니다. 확장 오류 정보를 가져오려면 `GetLastError`를 호출합니다.  
  
> [!NOTE]
>  함수는 ASSERT 경우 발생 하는 디버그 빌드에서 `CSid` 개체가 유효 하지 않습니다.  
  
##  <a name="isvalid"></a>CSid::IsValid  
 테스트는 `CSid` 유효성에 대 한 개체입니다.  
  
```
bool IsValid() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 경우는 `CSid` 개체가 올바른지 **false** 그렇지 않은 경우. 이 메서드;에 대 한 확장된 오류 정보가 없습니다. 호출 하지 마십시오 `GetLastError`합니다.  
  
### <a name="remarks"></a>주의  
 `IsValid` 유효성을 검사는 `CSid` 알려진된 범위 내에서 수정 번호 이며 하위 권한 수가 최대값 보다 작은지를 확인 하 여 개체입니다.  
  
##  <a name="loadaccount"></a>CSid::LoadAccount  
 업데이트는 `CSid` 계정 이름 및 도메인 또는 기존 SID (보안 식별자) 구조를 지정 된 개체입니다.  
  
```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pszAccountName`  
 계정 이름입니다.  
  
 `pszSystem`  
 시스템 이름입니다. 이 문자열에는 원격 컴퓨터의 이름일 수 있습니다. 이 문자열이 NULL 이면 로컬 시스템 대신 사용 됩니다.  
  
 `pSid`  
 에 대 한 포인터는 [SID](http://msdn.microsoft.com/library/windows/desktop/aa379594\(v=vs.85\).aspx) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 성공 **false** 실패 합니다. 확장 오류 정보를 가져오려면 `GetLastError`를 호출합니다.  
  
### <a name="remarks"></a>주의  
 `LoadAccount`지정된 된 이름에 대 한 보안 식별자를 찾으려고 시도 합니다. 참조 [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166\(v=vs.85\).aspx) 대 한 자세한 내용은 합니다.  
  
##  <a name="operator_eq"></a>CSid::operator =  
 대입 연산자입니다.  
  
```
CSid& operator= (const CSid& rhs) throw(...);  
CSid& operator= (const SID& rhs) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 `SID` (보안 식별자) 또는 `CSid` 에 할당 하는 `CSid` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트에 대 한 참조를 반환 합니다. `CSid` 개체입니다.  
  
##  <a name="operator_eq_eq"></a>CSid::operator = =  
 두 개의 보안 설명자 개체가 같은지를 테스트합니다.  
  
```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lhs`  
 `SID` (보안 식별자) 또는 `CSid` 의 왼쪽에 표시 되는 = = 연산자입니다.  
  
 `rhs`  
 `SID` (보안 식별자) 또는 `CSid` 의 오른쪽에 표시 되는 = = 연산자입니다.  
  
### <a name="return-value"></a>반환 값  
 **true 이면** 그렇지 않으면 보안 설명자가 같으면 **false**합니다.  
  
##  <a name="operator_neq"></a>CSid::operator! =  
 두 개의 보안 설명자 개체가 다른 지 테스트합니다.  
  
```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lhs`  
 `SID` (보안 식별자) 또는 `CSid` 의 왼쪽에 표시 되는! = 연산자입니다.  
  
 `rhs`  
 `SID` (보안 식별자) 또는 `CSid` 의 오른쪽에 표시 되는! = 연산자입니다.  
  
### <a name="return-value"></a>반환 값  
 **true 이면** 보안 설명자 같지 않으면, 그렇지 않으면 **false**합니다.  
  
##  <a name="operator_lt"></a>CSid::operator&lt;  
 두 가지 보안 설명자 개체의 상대 값을 비교합니다.  
  
```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lhs`  
 `SID` (보안 식별자) 또는 `CSid` 의 왼쪽에 표시 되는! = 연산자입니다.  
  
 `rhs`  
 `SID` (보안 식별자) 또는 `CSid` 의 오른쪽에 표시 되는! = 연산자입니다.  
  
### <a name="return-value"></a>반환 값  
 **true 이면** 경우 `lhs` 는 보다 작은 `rhs`, 그렇지 않으면 **false**합니다.  
  
##  <a name="operator_lt__eq"></a>CSid::operator&lt;=  
 두 가지 보안 설명자 개체의 상대 값을 비교합니다.  
  
```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lhs`  
 `SID` (보안 식별자) 또는 `CSid` 의 왼쪽에 표시 되는! = 연산자입니다.  
  
 `rhs`  
 `SID` (보안 식별자) 또는 `CSid` 의 오른쪽에 표시 되는! = 연산자입니다.  
  
### <a name="return-value"></a>반환 값  
 **true 이면** 경우 `lhs` 값 보다 작거나 `rhs`, 그렇지 않으면 **false**합니다.  
  
##  <a name="operator_gt"></a>CSid::operator&gt;  
 두 가지 보안 설명자 개체의 상대 값을 비교합니다.  
  
```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lhs`  
 `SID` (보안 식별자) 또는 `CSid` 의 왼쪽에 표시 되는! = 연산자입니다.  
  
 `rhs`  
 `SID` (보안 식별자) 또는 `CSid` 의 오른쪽에 표시 되는! = 연산자입니다.  
  
### <a name="return-value"></a>반환 값  
 **true 이면** 경우 `lhs` 보다 크면 `rhs`, 그렇지 않으면 **false**합니다.  
  
##  <a name="operator_gt__eq"></a>CSid::operator&gt;=  
 두 가지 보안 설명자 개체의 상대 값을 비교합니다.  
  
```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```  
  
### <a name="parameters"></a>매개 변수  
 `lhs`  
 `SID` (보안 식별자) 또는 `CSid` 의 왼쪽에 표시 되는! = 연산자입니다.  
  
 `rhs`  
 `SID` (보안 식별자) 또는 `CSid` 의 오른쪽에 표시 되는! = 연산자입니다.  
  
### <a name="return-value"></a>반환 값  
 **true 이면** 경우 `lhs` 보다 크거나 같지 `rhs`, 그렇지 않으면 **false**합니다.  
  
##  <a name="operator_const_sid__star"></a>CSid::operator const SID *  
 캐스트는 `CSid` 개체에 대 한 포인터는 `SID` (보안 식별자) 구조입니다.  
  
```  
operator const SID *() const throw(...);
```  
  
### <a name="remarks"></a>주의  
 주소를 반환 하는 `SID` 구조입니다.  
  
##  <a name="sid"></a>CSid::Sid  
 반환 된 `SID` 문자열로 (보안 식별자) 구조입니다.  
  
```
LPCTSTR Sid() const throw(...);
```  
  
### <a name="return-value"></a>반환 값  
 반환 된 `SID` 디스플레이, 저장 또는 전송에 적합 한 형식에서 문자열로 구조입니다. 에 해당 [ConvertSidToStringSid](http://msdn.microsoft.com/library/windows/desktop/aa376399),이 함수는만 이상 Windows 2000에서 사용할 수 있지만 및 이전 버전의 운영 체제에 대 한 에뮬레이션 하도록 합니다.  
  
##  <a name="sidnameuse"></a>CSid::SidNameUse  
 상태에 대 한 설명을 반환는 `CSid` 개체입니다.  
  
```
SID_NAME_USE SidNameUse() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 상태를 설명 하는 값을 저장 하는 데이터 멤버의 값을 반환 된 `CSid` 개체입니다.  
  
|값|설명|  
|-----------|-----------------|  
|SidTypeUser|사용자를 나타내는 `SID` (보안 식별자)입니다.|  
|SidTypeGroup|그룹을 나타냅니다 `SID`합니다.|  
|SidTypeDomain|도메인을 나타내는 `SID`합니다.|  
|SidTypeAlias|별칭을 나타내는 `SID`합니다.|  
|SidTypeWellKnownGroup|나타냅니다는 `SID` 잘 알려진 그룹입니다.|  
|SidTypeDeletedAccount|나타냅니다는 `SID` 는 삭제 된 계정에 대 한 합니다.|  
|SidTypeInvalid|잘못 된 나타냅니다 `SID`합니다.|  
|SidTypeUnknown|알 수 없는 나타냅니다 `SID` 유형입니다.|  
|SidTypeComputer|나타냅니다는 `SID` 컴퓨터입니다.|  
  
### <a name="remarks"></a>주의  
 호출 [CSid::LoadAccount](#loadaccount) 업데이트 하는 `CSid` 호출 하기 전에 개체 `SidNameUse` 해당 상태를 반환할 수 있습니다. `SidNameUse`개체의 상태를 변경 하지 않습니다 (을 호출 하 여 **LookupAccountName** 또는 **LookupAccountSid**), 하지만 현재 상태를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [보안 샘플](../../visual-cpp-samples.md)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [보안 전역 함수](../../atl/reference/security-global-functions.md)   
 [연산자](../../atl/reference/atl-operators.md)

