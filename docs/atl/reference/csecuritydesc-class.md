---
title: "CSecurityDesc 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::FromString
- ATLSECURITY/ATL::CSecurityDesc::GetControl
- ATLSECURITY/ATL::CSecurityDesc::GetDacl
- ATLSECURITY/ATL::CSecurityDesc::GetGroup
- ATLSECURITY/ATL::CSecurityDesc::GetOwner
- ATLSECURITY/ATL::CSecurityDesc::GetPSECURITY_DESCRIPTOR
- ATLSECURITY/ATL::CSecurityDesc::GetSacl
- ATLSECURITY/ATL::CSecurityDesc::IsDaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsDaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsDaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsDaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsGroupDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsOwnerDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsSaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsSaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::MakeAbsolute
- ATLSECURITY/ATL::CSecurityDesc::MakeSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::SetControl
- ATLSECURITY/ATL::CSecurityDesc::SetDacl
- ATLSECURITY/ATL::CSecurityDesc::SetGroup
- ATLSECURITY/ATL::CSecurityDesc::SetOwner
- ATLSECURITY/ATL::CSecurityDesc::SetSacl
- ATLSECURITY/ATL::CSecurityDesc::ToString
dev_langs:
- C++
helpviewer_keywords:
- CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 334081ba67c3b034c4b8170b095fcd77d712dda6
ms.lasthandoff: 04/04/2017

---
# <a name="csecuritydesc-class"></a>CSecurityDesc 클래스
이 클래스는에 대 한 래퍼는 **SECURITY_DESCRIPTOR** 구조입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CSecurityDesc
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSecurityDesc::CSecurityDesc](#csecuritydesc)|생성자입니다.|  
|[CSecurityDesc:: ~ CSecurityDesc](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSecurityDesc::FromString](#fromstring)|유효한, 기능 보안 설명자 문자열 형식의 보안 설명자를 변환합니다.|  
|[Csecuritydesc:: Getcontrol](#getcontrol)|검색은 보안 설명자에서 정보를 제어 합니다.|  
|[CSecurityDesc::GetDacl](#getdacl)|보안 설명자에서 임의 액세스 제어 목록 (DACL) 정보를 검색합니다.|  
|[CSecurityDesc::GetGroup](#getgroup)|보안 설명자에서 주 그룹 정보를 검색합니다.|  
|[CSecurityDesc::GetOwner](#getowner)|보안 설명자에서 소유자 정보를 검색합니다.|  
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|에 대 한 포인터를 반환 합니다.는 **SECURITY_DESCRIPTOR** 구조입니다.|  
|[CSecurityDesc::GetSacl](#getsacl)|보안 설명자에서 시스템 액세스 제어 SACL (목록) 정보를 검색합니다.|  
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|DACL 자동 전파를 지원 하도록 구성 된 경우를 결정 합니다.|  
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|보안 설명자 기본 DACL 구성 된 경우를 결정 합니다.|  
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|보안 설명자의 DACL 포함 되어 있는지 여부를 결정 합니다.|  
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|DACL이 수정 작업을 방지 하기 위해 구성 된 경우를 결정 합니다.|  
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|보안 설명자의 그룹 보안 식별자 (SID) 기본적으로 설정 된 경우를 결정 합니다.|  
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|보안 설명자의 소유자 SID가 기본적으로 설정 하는 경우를 결정 합니다.|  
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|SACL 자동 전파를 지원 하도록 구성 된 경우를 결정 합니다.|  
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|보안 설명자 SACL 기본값 구성 된 경우를 결정 합니다.|  
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|보안 설명자 SACL 포함 되어 있는지 여부를 결정 합니다.|  
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|SACL 수정을 방지 하도록 구성 된 경우를 결정 합니다.|  
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|보안 설명자를 자기 상대적 형식에서 인지 확인 합니다.|  
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|보안 설명자를 절대 형식으로 변환 하려면이 메서드를 호출 합니다.|  
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|보안 설명자를 자기 상대적 형식으로 변환 하려면이 메서드를 호출 합니다.|  
|[CSecurityDesc::SetControl](#setcontrol)|보안 설명자의 제어 비트를 설정합니다.|  
|[Csecuritydesc:: Setdacl](#setdacl)|DACL에 정보를 설정합니다. 보안 설명자에 DACL 이미 있으면 자동으로 바뀝니다.|  
|[Csecuritydesc:: Setgroup](#setgroup)|이미 있는 모든 주 그룹 정보를 대체 하는 절대 형식이 보안 설명자의 주 그룹 정보를 설정 합니다.|  
|[Csecuritydesc:: Setowner](#setowner)|이미 있는 모든 소유자 정보를 대체 하는 절대 형식이 보안 설명자의 소유자 정보를 설정 합니다.|  
|[Csecuritydesc:: Setsacl](#setsacl)|SACL에 정보를 설정합니다. 보안 설명자의 SACL 이미 있으면 자동으로 바뀝니다.|  
|[CSecurityDesc::ToString](#tostring)|보안 설명자 문자열 형식으로 변환합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CSecurityDesc::operator const SECURITY_DESCRIPTOR *](#operator_const_security_descriptor__star)|에 대 한 포인터를 반환 합니다.는 **SECURITY_DESCRIPTOR** 구조입니다.|  
|[CSecurityDesc::operator =](#operator_eq)|대입 연산자입니다.|  
  
## <a name="remarks"></a>주의  
 **SECURITY_DESCRIPTOR** 구조 개체에 연결 된 보안 정보를 포함 합니다. 응용 프로그램이이 구조를 사용 하 여 설정 하 고 개체의 보안 상태를 쿼리 합니다. 참고 항목 [AtlGetSecurityDescriptor](security-global-functions.md#atlgetsecuritydescriptor)합니다.  
  
 응용 프로그램을 수정 해서는 안 된 **SECURITY_DESCRIPTOR** 구조를 직접 및 대신 메서드를 사용 해야 클래스 제공 합니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오. [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h  
  
##  <a name="csecuritydesc"></a>CSecurityDesc::CSecurityDesc  
 생성자입니다.  
  
```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );  
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 `CSecurityDesc` 개체 또는 **SECURITY_DESCRIPTOR** 새 서버에 할당 하는 구조 `CSecurityDesc` 개체입니다.  
  
### <a name="remarks"></a>주의  
 `CSecurityDesc` 를 사용 하 여 개체를 만들 수 있습니다는 **SECURITY_DESCRIPTOR** 구조 또는 이전에 정의한 `CSecurityDesc` 개체입니다.  
  
##  <a name="dtor"></a>CSecurityDesc:: ~ CSecurityDesc  
 소멸자입니다.  
  
```
virtual ~CSecurityDesc() throw();
```  
  
### <a name="remarks"></a>주의  
 소멸자는 할당 된 모든 리소스를 해제합니다.  
  
##  <a name="fromstring"></a>CSecurityDesc::FromString  
 유효한, 기능 보안 설명자 문자열 형식의 보안 설명자를 변환합니다.  
  
```
bool FromString(LPCTSTR pstr) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pstr`  
 포함 된 null로 끝나는 문자열에 대 한 포인터는 [보안 설명자 문자열 형식](http://msdn.microsoft.com/library/windows/desktop/aa379570) 변환 될 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 true를 반환 합니다. 실패 한 경우 예외를 throw 합니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 문자열을 만들 수 있습니다 [CSecurityDesc::ToString](#tostring)합니다. 보안 설명자를 문자열로 변환 쉽게 저장 하 고 전송 합니다.  
  
 이 메서드는 에서만 사용할 수 있는 Windows 2000 이상를 호출 하므로 [ConvertStringSecurityDescriptorToSecurityDescriptor](http://msdn.microsoft.com/library/windows/desktop/aa376401)합니다.  
  
##  <a name="getcontrol"></a>Csecuritydesc:: Getcontrol  
 검색은 보안 설명자에서 정보를 제어 합니다.  
  
```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *psdc*  
 에 대 한 포인터는 **SECURITY_DESCRIPTOR_CONTROL** 구조체 보안 설명자의 제어 정보입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면, false 실패할 경우 true를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는만 Windows 2000을 사용 하는 경우에 의미 있는 이상 호출할 때 [GetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa446647)합니다.  
  
##  <a name="getdacl"></a>CSecurityDesc::GetDacl  
 보안 설명자에서 임의 액세스 제어 목록 (DACL) 정보를 검색합니다.  
  
```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDacl`  
 에 대 한 포인터는 `CDacl` 보안 설명자의 DACL의 복사본을 저장 하는 구조입니다. 임의 경우 **ACL** 있는 메서드 집합 `pDacl` 보안의 주소로 설명자의 임의 **ACL**합니다. 임의 경우 **ACL** 존재 하지 않는 값이 저장 되지 합니다.  
  
 `pbPresent`  
 임의의 존재를 표시 하는 값에 대 한 포인터 **ACL** 지정 된 보안 설명자에서입니다. 보안 설명자는 임의 포함 되어 있는 경우 **ACL**,이 매개 변수가 true로 합니다. 보안 설명자는 임의 포함 되어 있지 않으면 **ACL**,이 매개 변수를 false로 설정 합니다.  
  
 `pbDefaulted`  
 SE_DACL_DEFAULTED 플래그의 값으로 설정 된 플래그에 대 한 포인터는 **SECURITY_DESCRIPTOR_CONTROL** 경우 임의 구조체 **ACL** 보안 설명자에 대 한 존재 합니다. 이 플래그는 true 인 경우는 임의 **ACL** false 인 경우, 기본 메커니즘;에 의해 검색 된 임의 **ACL** 사용자가을 명시적으로 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면, false 실패할 경우 true를 반환 합니다.  
  
##  <a name="getgroup"></a>CSecurityDesc::GetGroup  
 보안 설명자에서 주 그룹 정보를 검색합니다.  
  
```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSid`  
 에 대 한 포인터는 [CSid](../../atl/reference/csid-class.md) (보안 식별자)는 CDacl에 저장 된 그룹의 복사본을 받는 합니다.  
  
 `pbDefaulted`  
 SE_GROUP_DEFAULTED 플래그의 값으로 설정 된 플래그에 대 한 포인터는 **SECURITY_DESCRIPTOR_CONTROL** 메서드가 반환 될 때 구성 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면, false 실패할 경우 true를 반환 합니다.  
  
##  <a name="getowner"></a>CSecurityDesc::GetOwner  
 보안 설명자에서 소유자 정보를 검색합니다.  
  
```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSid`  
 에 대 한 포인터는 [CSid](../../atl/reference/csid-class.md) (보안 식별자)는 CDacl에 저장 된 그룹의 복사본을 받는 합니다.  
  
 `pbDefaulted`  
 SE_OWNER_DEFAULTED 플래그의 값으로 설정 된 플래그에 대 한 포인터는 **SECURITY_DESCRIPTOR_CONTROL** 메서드가 반환 될 때 구성 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면, false 실패할 경우 true를 반환 합니다.  
  
##  <a name="getpsecurity_descriptor"></a>CSecurityDesc::GetPSECURITY_DESCRIPTOR  
 에 대 한 포인터를 반환 합니다.는 **SECURITY_DESCRIPTOR** 구조입니다.  
  
```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터를 반환 합니다.는 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561) 구조입니다.  
  
##  <a name="getsacl"></a>CSecurityDesc::GetSacl  
 보안 설명자에서 시스템 액세스 제어 SACL (목록) 정보를 검색합니다.  
  
```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSacl`  
 에 대 한 포인터는 `CSacl` 보안 설명자의 SACL의 복사본을 저장 하는 구조입니다. 하는 경우 시스템 **ACL** 있는 메서드 집합 `pSacl` 의 보안 설명자의 시스템 주소로 **ACL**합니다. 하는 경우 시스템 **ACL** 존재 하지 않는 값이 저장 되지 합니다.  
  
 `pbPresent`  
 메서드는 시스템의 있음을 표시 하기 위해 설정 하는 플래그에 대 한 포인터 **ACL** 지정 된 보안 설명자에서입니다. 보안 설명자는 시스템을 포함 하는 경우 **ACL**,이 매개 변수가 true로 합니다. 보안 설명자에 시스템 포함 되어 있지 않으면 **ACL**,이 매개 변수를 false로 설정 합니다.  
  
 `pbDefaulted`  
 SE_SACL_DEFAULTED 플래그의 값으로 설정 된 플래그에 대 한 포인터는 **SECURITY_DESCRIPTOR_CONTROL** 경우 시스템 구조 **ACL** 보안 설명자에 대 한 존재 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면, false 실패할 경우 true를 반환 합니다.  
  
##  <a name="isdaclautoinherited"></a>CSecurityDesc::IsDaclAutoInherited  
 임의 액세스 제어 목록 (DACL)가 자동 전파를 지원 하도록 구성 하는 경우를 결정 합니다.  
  
```
bool IsDaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 보안 설명자 (Ace) 기존 자식 개체에 상속 가능한 액세스 제어 항목의 자동 전파를 지원 하도록 설정 된 DACL 포함 되어 있으면 true를 반환 합니다. 그렇지 않으면 false를 반환합니다.  
  
### <a name="remarks"></a>주의  
 시스템 개체 및 기존 자식 개체에 대 한 자동 상속 알고리즘을 수행할 때이 비트를 설정 합니다.  
  
##  <a name="isdacldefaulted"></a>CSecurityDesc::IsDaclDefaulted  
 보안 설명자는 기본 액세스 제어 목록 (DACL)으로 구성 된 경우를 결정 합니다.  
  
```
bool IsDaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 보안 설명자 포함 되어 있으면 기본 DACL, false를 반환 하지 않으면 true를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 플래그는 시스템 액세스 제어 항목 (ACE) 상속와 관련 하 여 DACL을 처리 하는 방법으로 발생할 수 있습니다. 예를 들어 개체의 작성자의 DACL을 지정 하지 않으면 개체 작성자의 액세스 토큰에서 기본 DACL을 받습니다. SE_DACL_PRESENT 플래그가 설정 되지 않은 경우이 플래그를 무시 하는 시스템.  
  
 이 플래그는 개체의 최종 DACL를 계산 해야 하는 방법을 결정 하는 데 사용 되 및 보안 개체의 보안 설명자 제어에 물리적으로 저장 되지 않습니다.  
  
 이 플래그를 설정 하려면는 [csecuritydesc:: Setdacl](#setdacl) 메서드.  
  
##  <a name="isdaclpresent"></a>CSecurityDesc::IsDaclPresent  
 보안 설명자는 임의 액세스 제어 목록 (DACL)를 포함 하는 경우를 결정 합니다.  
  
```
bool IsDaclPresent() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 보안 설명자 false가 포함 된 DACL 그렇지 않으면 true를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 플래그를 설정 하지 않으면, 또는이 플래그가 설정 되 고 DACL null 인 보안 설명자는 모든 사용자에 게 모든 액세스를 허용 합니다.  
  
 이 플래그는 보안 설명자가 보안 개체와 연결 될 때까지 호출자가 지정 된 보안 정보 유지 하기 위해 사용 됩니다. 보안 설명자는 보안 개체와 연결 되 고 나면 SE_DACL_PRESENT 플래그는 항상 보안 설명자 컨트롤에 설정 됩니다.  
  
 이 플래그를 설정 하려면는 [csecuritydesc:: Setdacl](#setdacl) 메서드.  
  
##  <a name="isdaclprotected"></a>CSecurityDesc::IsDaclProtected  
 임의 액세스 제어 목록 (DACL) 수정을 방지 하도록 구성 된 경우를 결정 합니다.  
  
```
bool IsDaclProtected() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 DACL 보안 설명자 (Ace) 상속 가능한 액세스 제어 항목 수정 하지 못하도록 방지 하기 위해 구성 된 경우 true를 반환 합니다. 그렇지 않으면 false를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 플래그를 설정 하려면는 [csecuritydesc:: Setdacl](#setdacl) 메서드.  
  
 이 메서드는만 의미 있는 이상에 대 한 Windows 2000, Windows 2000만 상속 가능한 Ace의 자동 전파를 지원 합니다.  
  
##  <a name="isgroupdefaulted"></a>CSecurityDesc::IsGroupDefaulted  
 보안 설명자의 그룹 보안 식별자 (SID) 기본적으로 설정 된 경우를 결정 합니다.  
  
```
bool IsGroupDefaulted() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 보안 설명자의 원래 공급자 보다는 기본 메커니즘을 제공 된 보안 설명자의 경우 true를 반환 그룹 SID입니다. 그렇지 않으면 false를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 플래그를 설정 하려면는 [csecuritydesc:: Setgroup](#setgroup) 메서드.  
  
##  <a name="isownerdefaulted"></a>CSecurityDesc::IsOwnerDefaulted  
 보안 설명자의 소유자 보안 식별자 (SID) 기본적으로 설정 된 경우를 결정 합니다.  
  
```
bool IsOwnerDefaulted() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 보안 설명자의 원래 공급자 보다는 기본 메커니즘을 보안 설명자의 소유자 SID를 제공 하는 경우 true를 반환 합니다. 그렇지 않으면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 플래그를 설정 하려면는 [csecuritydesc:: Setowner](#setowner) 메서드.  
  
##  <a name="issaclautoinherited"></a>CSecurityDesc::IsSaclAutoInherited  
 (SACL)의 시스템 액세스 제어 목록 자동 전파를 지원 하도록 구성 된 경우를 결정 합니다.  
  
```
bool IsSaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 보안 설명자 (Ace) 기존 자식 개체에 상속 가능한 액세스 제어 항목의 자동 전파를 지원 하도록 설정 된 SACL 포함 되어 있으면 true를 반환 합니다. 그렇지 않으면 false를 반환합니다.  
  
### <a name="remarks"></a>주의  
 시스템 개체 및 기존 자식 개체에 대 한 자동 상속 알고리즘을 수행할 때이 비트를 설정 합니다.  
  
##  <a name="issacldefaulted"></a>CSecurityDesc::IsSaclDefaulted  
 보안 설명자는 기본 시스템 액세스 제어 목록 (SACL) 구성 된 경우를 결정 합니다.  
  
```
bool IsSaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 보안 설명자 포함 되어 있으면 기본 SACL, false를 반환 하지 않으면 true를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 플래그는 시스템 액세스 제어 항목 (ACE) 상속와 관련 하 여 SACL을 처리 하는 방법으로 발생할 수 있습니다. SE_SACL_PRESENT 플래그가 설정 되지 않은 경우이 플래그를 무시 하는 시스템.  
  
 이 플래그를 설정 하려면는 [csecuritydesc:: Setsacl](#setsacl) 메서드.  
  
##  <a name="issaclpresent"></a>CSecurityDesc::IsSaclPresent  
 보안 설명자 시스템 액세스 제어 목록 SACL ()를 포함 하는 경우를 결정 합니다.  
  
```
bool IsSaclPresent() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 보안 설명자 false가 포함 된 SACL 그렇지 않으면 true를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 플래그를 설정 하려면는 [csecuritydesc:: Setsacl](#setsacl) 메서드.  
  
##  <a name="issaclprotected"></a>CSecurityDesc::IsSaclProtected  
 (SACL)의 시스템 액세스 제어 목록 수정을 방지 하도록 구성 된 경우를 결정 합니다.  
  
```
bool IsSaclProtected() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 SACL 보안 설명자 (Ace) 상속 가능한 액세스 제어 항목 수정 하지 못하도록 방지 하기 위해 구성 된 경우 true를 반환 합니다. 그렇지 않으면 false를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 플래그를 설정 하려면는 [csecuritydesc:: Setsacl](#setsacl) 메서드.  
  
 이 메서드는만 의미 있는 이상에 대 한 Windows 2000, Windows 2000만 상속 가능한 Ace의 자동 전파를 지원 합니다.  
  
##  <a name="isselfrelative"></a>CSecurityDesc::IsSelfRelative  
 보안 설명자를 자기 상대적 형식에서 인지 확인 합니다.  
  
```
bool IsSelfRelative() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 연속 된 메모리 블록의 모든 보안 정보로 보안 설명자가 자기 상대적 형식 경우 true를 반환 합니다. 절대적 형식의 보안 설명자가 false를 반환 합니다. 자세한 내용은 참조 [Absolute 및 Self-Relative 보안 설명자](http://msdn.microsoft.com/library/windows/desktop/aa374807)합니다.  
  
##  <a name="makeabsolute"></a>CSecurityDesc::MakeAbsolute  
 보안 설명자를 절대 형식으로 변환 하려면이 메서드를 호출 합니다.  
  
```
bool MakeAbsolute() throw(...);
```  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면, false 그렇지 않은 경우 true를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 절대적 형식의 보안 설명자 정보 자체 대신 포함 되는 정보에 대 한 포인터를 포함 합니다. 보안 설명자를 자기 상대적 형식으로 인접 한 메모리 블록의 정보를 포함합니다. 자기 상대적 보안 설명자에서는 **SECURITY_DESCRIPTOR** 구조는 항상에서 정보를 시작 하지만 보안 설명자의 다른 구성 요소는 순서에 관계 없이 구조를 따를 수 있습니다. 메모리 주소를 사용 하는 대신 자기 상대적 보안 설명자의 구성 요소는 보안 설명자의 시작 부분에서의 오프셋으로 식별 됩니다. 이 형식은 보안 설명자를 디스크에 저장 하거나 통신 프로토콜을 통해 전송 해야 하는 경우에 유용 합니다. 자세한 내용은 참조 [Absolute 및 Self-Relative 보안 설명자](http://msdn.microsoft.com/library/windows/desktop/aa374807)합니다.  
  
##  <a name="makeselfrelative"></a>CSecurityDesc::MakeSelfRelative  
 보안 설명자를 자기 상대적 형식으로 변환 하려면이 메서드를 호출 합니다.  
  
```
bool MakeSelfRelative() throw(...);
```  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면, false 그렇지 않은 경우 true를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 절대적 형식의 보안 설명자 정보 자체를 포함 하는 것이 아니라 포함 된 정보에 대 한 포인터를 포함 합니다. 보안 설명자를 자기 상대적 형식으로 인접 한 메모리 블록의 정보를 포함합니다. 자기 상대적 보안 설명자에서는 **SECURITY_DESCRIPTOR** 구조는 항상에서 정보를 시작 하지만 보안 설명자의 다른 구성 요소는 순서에 관계 없이 구조를 따를 수 있습니다. 보안 설명자의 구성 요소는 메모리 주소를 사용 하는 대신 보안 설명자의 시작 부분에서의 오프셋으로 식별 됩니다. 이 형식은 보안 설명자를 디스크에 저장 하거나 통신 프로토콜을 통해 전송 해야 하는 경우에 유용 합니다. 자세한 내용은 참조 [Absolute 및 Self-Relative 보안 설명자](http://msdn.microsoft.com/library/windows/desktop/aa374807)합니다.  
  
##  <a name="operator_eq"></a>CSecurityDesc::operator =  
 대입 연산자입니다.  
  
```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);  
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 **SECURITY_DESCRIPTOR** 구조 또는 `CSecurityDesc` 에 할당할은 `CSecurityDesc` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 반환 `CSecurityDesc` 개체입니다.  
  
##  <a name="operator_const_security_descriptor__star"></a>CSecurityDesc::operator const SECURITY_DESCRIPTOR *  
 값에 대 한 포인터에 캐스팅은 **SECURITY_DESCRIPTOR** 구조입니다.  
  
```  
operator const SECURITY_DESCRIPTOR *() const throw();
```  
  
##  <a name="setcontrol"></a>CSecurityDesc::SetControl  
 보안 설명자의 제어 비트를 설정합니다.  
  
```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest, 
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `ControlBitsOfInterest`  
 A **SECURITY_DESCRIPTOR_CONTROL** 제어 비트를 설정 하는 마스크입니다. 설정할 수 있는 플래그 목록은 참조 [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx)합니다.  
  
 `ControlBitsToSet`  
 `SECURITY_DESCRIPTOR_CONTROL` 마스크가 지정하는 제어 비트의 새 값을 나타내는 `ControlBitsOfInterest` 마스크입니다. 이 매개 변수는 `ControlBitsOfInterest` 매개 변수에 대해 나열된 플래그의 조합일 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 사용할 수 있는 Windows 2000 이상 에서만 호출할 때 [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx)합니다.  
  
##  <a name="setdacl"></a>Csecuritydesc:: Setdacl  
 임의 액세스 제어 목록 (DACL)에서 정보를 설정합니다. 보안 설명자에 DACL 이미 있으면 자동으로 바뀝니다.  
  
```
inline void SetDacl(  
    bool bPresent = true,
    bool bDefaulted = false) throw(...);

inline void SetDacl(  
    const CDacl& Dacl,
    bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 *Dacl*  
 에 대 한 참조는 `CDacl` 보안 설명자에 대 한 DACL을 지정 하는 개체입니다. 이 매개 변수는 NULL이 아니어야 합니다. 보안 설명자에 NULL DACL을 설정 하려면 메서드의 첫 번째 형태는 것 `bPresent` false로 설정 합니다.  
  
 `bPresent`  
 보안 설명자에 DACL의 존재 여부를 나타내는 플래그를 지정 합니다. 이 매개 변수가 true 이면 메서드 SE_DACL_PRESENT 플래그를 설정의 **SECURITY_DESCRIPTOR_CONTROL** 구조체이 고 값을 사용 하 여는 *Dacl* 및 `bDefaulted` 매개 변수입니다. 메서드가 SE_DACL_PRESENT 플래그를 지웁니다 false 이면 및 `bDefaulted` 는 무시 됩니다.  
  
 `bDefaulted`  
 DACL의 원본을 나타내는 플래그를 지정 합니다. 이 플래그가 true 이면 DACL 기본 메커니즘을 통해 검색 했습니다. False 인 경우, 사용자가 DACL은 명시적으로 지정 되어 했습니다. 메서드는이 값의 SE_DACL_DEFAULTED 플래그는 **SECURITY_DESCRIPTOR_CONTROL** 구조입니다. 이 매개 변수를 지정 하지 않으면 SE_DACL_DEFAULTED 플래그가 지워집니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 빈 및 존재 하지 않는 DACL 사이는 중요 한 차이점이 있습니다. DACL 비어 있으면 액세스 제어 항목이 없는 및 액세스 권한이 없습니다. 권한이 명시적으로 부여 합니다. 결과적으로, 개체에 대 한 암시적으로 거부 합니다. 반면에 개체에 없는 DACL을 보호 되지 않음는 개체에 할당 된 및 모든 액세스 요청에 권한이 부여 됩니다.  
  
##  <a name="setgroup"></a>Csecuritydesc:: Setgroup  
 이미 있는 모든 주 그룹 정보를 대체 하는 절대 형식이 보안 설명자의 주 그룹 정보를 설정 합니다.  
  
```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `Sid`  
 에 대 한 참조는 [CSid](../../atl/reference/csid-class.md) 보안 설명자의 새 기본 그룹에 대 한 개체입니다. 이 매개 변수는 NULL이 아니어야 합니다. 보안 설명자의 DACL 또는 SACL을 되지 않는 것으로 표시 될 수 있습니다 하지만 이러한도 그룹 및 소유자를 포함 해야 합니다 (즉, 특별 한 의미가 있는 기본 제공 SID) NULL SID 됩니다.  
  
 `bDefaulted`  
 기본 그룹 정보는 기본 메커니즘에서 파생 된 있는지 여부를 나타냅니다. 이 값은 true, 기본 정보를 하 고 경우에 SE_GROUP_DEFAULTED 플래그로이 값을 저장 하는 메서드는 **SECURITY_DESCRIPTOR_CONTROL** 구조입니다. 이 매개 변수가 0 이면 SE_GROUP_DEFAULTED 플래그가 지워집니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="setowner"></a>Csecuritydesc:: Setowner  
 절대 형식이 보안 설명자의 소유자 정보를 설정합니다. 이미 있는 모든 소유자 정보를 대체합니다.  
  
```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `Sid`  
 [CSid](../../atl/reference/csid-class.md) 보안 설명자의 새 기본 소유자에 대 한 개체입니다. 이 매개 변수는 NULL이 아니어야 합니다.  
  
 `bDefaulted`  
 소유자 정보는 기본 메커니즘에서 파생 되었는지 여부를 나타냅니다. 이 값이 true 인 경우에 기본 정보입니다. SE_OWNER_DEFAULTED 플래그도이 값을 저장 하는 메서드는 **SECURITY_DESCRIPTOR_CONTROL** 구조입니다. 이 매개 변수가 0 이면 SE_OWNER_DEFAULTED 플래그가 지워집니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="setsacl"></a>Csecuritydesc:: Setsacl  
 SACL ()는 시스템 액세스 제어 목록에 정보를 설정합니다. 보안 설명자의 SACL 이미 있으면 자동으로 바뀝니다.  
  
```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 *Sacl*  
 에 대 한 포인터는 `CSacl` 한 보안 설명자의 SACL을 지정 하는 개체입니다. 이 매개 변수는 NULL이 아니어야 하며 CSacl 개체 여야 합니다. Dacl을 달리 차이가 없습니다 NULL과 빈 SACL SACL 개체가 액세스 권한, 감사만 정보를 지정 하지 않으면으로 합니다.  
  
 `bDefaulted`  
 SACL의 원본을 나타내는 플래그를 지정 합니다. 이 플래그가 true 이면 SACL 기본 메커니즘을 통해 검색 했습니다. False 인 경우, 사용자가 SACL은 명시적으로 지정 되어 했습니다. 메서드는이 값의 SE_SACL_DEFAULTED 플래그는 **SECURITY_DESCRIPTOR_CONTROL** 구조입니다. 이 매개 변수를 지정 하지 않으면 SE_SACL_DEFAULTED 플래그가 지워집니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="tostring"></a>CSecurityDesc::ToString  
 보안 설명자 문자열 형식으로 변환합니다.  
  
```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pstr`  
 수신할는 null로 끝나는 문자열에 대 한 포인터는 [보안 설명자 문자열 형식](http://msdn.microsoft.com/library/windows/desktop/aa379570)합니다.  
  
 `si`  
 출력 문자열에 포함 하는 보안 설명자의 구성 요소를 표시 하기 위해 SECURITY_INFORMATION 비트 플래그의 조합을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>주의  
 보안 설명자 문자열 형태로 표시 되 면 보다 쉽게 저장 하거나 이동할 수 있습니다 전송 합니다. 사용 하 여는 `CSecurityDesc::FromString` 보안 설명자에 다시 문자열을 변환 하는 메서드입니다.  
  
 `si` 매개 변수는 다음 SECURITY_INFORMATION 플래그를 포함할 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|OWNER_SECURITY_INFORMATION|소유자를 포함 합니다.|  
|GROUP_SECURITY_INFORMATION|주 그룹을 포함 합니다.|  
|DACL_SECURITY_INFORMATION|DACL을 포함 합니다.|  
|SACL_SECURITY_INFORMATION|SACL을 포함 합니다.|  
  
 DACL NULL이 고 입력된 보안 설명자에 SE_DACL_PRESENT 제어 비트가 설정 메서드가 실패 합니다.  
  
 DACL NULL이 고 입력된 보안 설명자에 SE_DACL_PRESENT 제어 비트가 설정 되지 않으면 결과 보안 설명자 문자열 없는 경우 d: 구성 요소입니다. 참조 [보안 설명자 문자열 형식](http://msdn.microsoft.com/library/windows/desktop/aa379570) 내용을 확인 합니다.  
  
 이 메서드는 에서만 사용할 수 있는 Windows 2000 이상에서 호출할 때 [ConvertStringSecurityDescriptorToSecurityDescriptor](http://msdn.microsoft.com/library/windows/desktop/aa376401)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Security 샘플](../../visual-cpp-samples.md)   
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [보안 전역 함수](../../atl/reference/security-global-functions.md)

