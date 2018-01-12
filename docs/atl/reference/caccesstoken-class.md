---
title: "CAccessToken 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAccessToken
- ATLSECURITY/ATL::CAccessToken
- ATLSECURITY/ATL::CAccessToken::Attach
- ATLSECURITY/ATL::CAccessToken::CheckTokenMembership
- ATLSECURITY/ATL::CAccessToken::CreateImpersonationToken
- ATLSECURITY/ATL::CAccessToken::CreatePrimaryToken
- ATLSECURITY/ATL::CAccessToken::CreateProcessAsUser
- ATLSECURITY/ATL::CAccessToken::CreateRestrictedToken
- ATLSECURITY/ATL::CAccessToken::Detach
- ATLSECURITY/ATL::CAccessToken::DisablePrivilege
- ATLSECURITY/ATL::CAccessToken::DisablePrivileges
- ATLSECURITY/ATL::CAccessToken::EnablePrivilege
- ATLSECURITY/ATL::CAccessToken::EnablePrivileges
- ATLSECURITY/ATL::CAccessToken::GetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::GetEffectiveToken
- ATLSECURITY/ATL::CAccessToken::GetGroups
- ATLSECURITY/ATL::CAccessToken::GetHandle
- ATLSECURITY/ATL::CAccessToken::GetImpersonationLevel
- ATLSECURITY/ATL::CAccessToken::GetLogonSessionId
- ATLSECURITY/ATL::CAccessToken::GetLogonSid
- ATLSECURITY/ATL::CAccessToken::GetOwner
- ATLSECURITY/ATL::CAccessToken::GetPrimaryGroup
- ATLSECURITY/ATL::CAccessToken::GetPrivileges
- ATLSECURITY/ATL::CAccessToken::GetProcessToken
- ATLSECURITY/ATL::CAccessToken::GetProfile
- ATLSECURITY/ATL::CAccessToken::GetSource
- ATLSECURITY/ATL::CAccessToken::GetStatistics
- ATLSECURITY/ATL::CAccessToken::GetTerminalServicesSessionId
- ATLSECURITY/ATL::CAccessToken::GetThreadToken
- ATLSECURITY/ATL::CAccessToken::GetTokenId
- ATLSECURITY/ATL::CAccessToken::GetType
- ATLSECURITY/ATL::CAccessToken::GetUser
- ATLSECURITY/ATL::CAccessToken::HKeyCurrentUser
- ATLSECURITY/ATL::CAccessToken::Impersonate
- ATLSECURITY/ATL::CAccessToken::ImpersonateLoggedOnUser
- ATLSECURITY/ATL::CAccessToken::IsTokenRestricted
- ATLSECURITY/ATL::CAccessToken::LoadUserProfile
- ATLSECURITY/ATL::CAccessToken::LogonUser
- ATLSECURITY/ATL::CAccessToken::OpenCOMClientToken
- ATLSECURITY/ATL::CAccessToken::OpenNamedPipeClientToken
- ATLSECURITY/ATL::CAccessToken::OpenRPCClientToken
- ATLSECURITY/ATL::CAccessToken::OpenThreadToken
- ATLSECURITY/ATL::CAccessToken::PrivilegeCheck
- ATLSECURITY/ATL::CAccessToken::Revert
- ATLSECURITY/ATL::CAccessToken::SetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::SetOwner
- ATLSECURITY/ATL::CAccessToken::SetPrimaryGroup
dev_langs: C++
helpviewer_keywords: CAccessToken class
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3df4c5ac46c159cd3ed955621af914c677182a57
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="caccesstoken-class"></a>CAccessToken 클래스
이 클래스는 액세스 토큰에 대 한 래퍼입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CAccessToken
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAccessToken:: ~ CAccessToken](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAccessToken::Attach](#attach)|지정 된 액세스 토큰 핸들의 소유권을 갖도록이 메서드를 호출 합니다.|  
|[CAccessToken::CheckTokenMembership](#checktokenmembership)|에 지정 된 SID가 설정 되었는지 확인 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::CreateImpersonationToken](#createimpersonationtoken)|새 가장 액세스 토큰을 만들려면이 메서드를 호출 합니다.|  
|[CAccessToken::CreatePrimaryToken](#createprimarytoken)|새 기본 토큰을 만들려면이 메서드를 호출 합니다.|  
|[CAccessToken::CreateProcessAsUser](#createprocessasuser)|가 나타내는 사용자의 보안 컨텍스트에서 실행 되는 새 프로세스를 만들려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::CreateRestrictedToken](#createrestrictedtoken)|이 메서드를 새로 만드는 제한 `CAccessToken` 개체입니다.|  
|[CAccessToken::Detach](#detach)|액세스 토큰의 소유권을 취소 하려면이 메서드를 호출 합니다.|  
|[CAccessToken::DisablePrivilege](#disableprivilege)|권한 사용 하지 않도록 설정 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::DisablePrivileges](#disableprivileges)|하나 이상의 권한을 사용 하지 않도록 설정 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::EnablePrivilege](#enableprivilege)|권한에서 사용 하도록 설정 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::EnablePrivileges](#enableprivileges)|하나 이상의 권한을 사용 하도록 설정 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetDefaultDacl](#getdefaultdacl)|호출 반환 하려면이 메서드는 `CAccessToken` 개체의 DACL 기본 합니다.|  
|[CAccessToken::GetEffectiveToken](#geteffectivetoken)|가져오려면이 메서드를 호출 하는 `CAccessToken` 개체와 같은 액세스 토큰에 현재 스레드에 적용 합니다.|  
|[CAccessToken::GetGroups](#getgroups)|호출 반환 하려면이 메서드는 `CAccessToken` 토큰 개체의 그룹입니다.|  
|[CAccessToken::GetHandle](#gethandle)|액세스 토큰에 대 한 핸들을 검색 하려면이 메서드를 호출 합니다.|  
|[CAccessToken::GetImpersonationLevel](#getimpersonationlevel)|액세스 토큰에서 가장 수준을 가져오려면이 메서드를 호출 합니다.|  
|[CAccessToken::GetLogonSessionId](#getlogonsessionid)|와 관련 된 로그온 세션 ID를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetLogonSid](#getlogonsid)|와 관련 된 로그온 SID를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetOwner](#getowner)|와 연결 된 소유자를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetPrimaryGroup](#getprimarygroup)|와 연결 된 주 그룹을 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetPrivileges](#getprivileges)|연결 된 권한을 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetProcessToken](#getprocesstoken)|지정된 프로세스의 액세스 토큰을 사용해서 `CAccessToken`을 초기화하려면 이 메서드를 호출합니다.|  
|[CAccessToken::GetProfile](#getprofile)|와 연결 된 사용자 프로필을 가리키는 핸들을 가져올이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetSource](#getsource)|소스를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetStatistics](#getstatistics)|와 관련 된 정보를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetTerminalServicesSessionId](#getterminalservicessessionid)|와 연결 된 터미널 서비스 세션 ID를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetThreadToken](#getthreadtoken)|초기화 하려면이 메서드를 호출의 `CAccessToken` 주어진된 스레드의에서 토큰으로 사용 합니다.|  
|[CAccessToken::GetTokenId](#gettokenid)|와 연결 된 토큰 ID를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetType](#gettype)|토큰의 형식을 가져오기 위해이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetUser](#getuser)|연결 된 사용자를 식별 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::HKeyCurrentUser](#hkeycurrentuser)|와 연결 된 사용자 프로필을 가리키는 핸들을 가져올이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::Impersonate](#impersonate)|가장을 할당 하려면이 메서드를 호출 `CAccessToken` 스레드에 있습니다.|  
|[CAccessToken::ImpersonateLoggedOnUser](#impersonateloggedonuser)|호출 스레드에서 로그온 한 사용자의 보안 컨텍스트를 가장할 수 있도록 하려면이 메서드를 호출 합니다.|  
|[CAccessToken::IsTokenRestricted](#istokenrestricted)|테스트 하기 위해이 메서드를 호출 하는 `CAccessToken` 개체 제한 된 Sid의 목록이 포함 되어 있습니다.|  
|[CAccessToken::LoadUserProfile](#loaduserprofile)|와 연결 된 사용자 프로필을 로드 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::LogonUser](#logonuser)|지정된 된 자격 증명와 관련 된 사용자에 대 한 로그온 세션을 만들려면이 메서드를 호출 합니다.|  
|[CAccessToken::OpenCOMClientToken](#opencomclienttoken)|초기화 하는 클라이언트에서 호출을 처리 하는 COM 서버에서이 메서드를 호출 하 여 `CAccessToken` COM 클라이언트에서 액세스 토큰으로 합니다.|  
|[CAccessToken::OpenNamedPipeClientToken](#opennamedpipeclienttoken)|호출 하는 서버에서이 메서드를 만들기 요청 초기화를 명명 된 파이프를 통한는 `CAccessToken` 클라이언트에서 액세스 토큰으로 합니다.|  
|[CAccessToken::OpenRPCClientToken](#openrpcclienttoken)|초기화는 RPC 클라이언트에서 호출을 처리 하는 서버에서이 메서드를 호출 하 여 `CAccessToken` 클라이언트에서 액세스 토큰으로 합니다.|  
|[CAccessToken::OpenThreadToken](#openthreadtoken)|가장 수준을 설정 하 고 다음을 초기화 하려면이 메서드를 호출는 `CAccessToken` 주어진된 스레드의에서 토큰으로 사용 합니다.|  
|[CAccessToken::PrivilegeCheck](#privilegecheck)|호출에 지정 된 특권 집합을 사용할지를 확인 하려면이 메서드는 **CAccessToken** 개체입니다.|  
|[CAccessToken::Revert](#revert)|가장 토큰을 사용 하는 스레드를 중지 하려면이 메서드를 호출 합니다.|  
|[CAccessToken::SetDefaultDacl](#setdefaultdacl)|기본값을 설정 하려면이 메서드 호출의 DACL에서 `CAccessToken` 개체입니다.|  
|[CAccessToken::SetOwner](#setowner)|소유자를 설정 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::SetPrimaryGroup](#setprimarygroup)|주 그룹을 설정 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 [액세스 토큰](http://msdn.microsoft.com/library/windows/desktop/aa374909) 프로세스 또는 스레드의 보안 컨텍스트를 설명 하 고 Windows NT 또는 Windows 2000 시스템에 로그온 한 각 사용자에 게 할당 하는 개체입니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오. [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows sdk에서입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h  
  
##  <a name="attach"></a>CAccessToken::Attach  
 지정 된 액세스 토큰 핸들의 소유권을 갖도록이 메서드를 호출 합니다.  
  
```
void Attach(HANDLE hToken) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *hToken*  
 액세스 토큰에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 디버그 빌드에서 경우 어설션 오류가 발생 합니다는 `CAccessToken` 개체 액세스 토큰의 소유권을 이미가지고 있습니다.  
  
##  <a name="dtor"></a>CAccessToken:: ~ CAccessToken  
 소멸자입니다.  
  
```
virtual ~CAccessToken() throw();
```  
  
### <a name="remarks"></a>설명  
 할당 된 모든 리소스를 해제합니다.  
  
##  <a name="checktokenmembership"></a>CAccessToken::CheckTokenMembership  
 에 지정 된 SID가 설정 되었는지 확인 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool CheckTokenMembership(
    const CSid& rSid, 
    bool* pbIsMember) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rSid`  
 에 대 한 참조는 [CSid 클래스](../../atl/reference/csid-class.md) 개체입니다.  
  
 `pbIsMember`  
 포인터 검사의 결과 수신 하는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 `CheckTokenMembership` 메서드 그룹 Sid 액세스 토큰을 확인 하 고 사용자의 SID가 있는지 확인 합니다. SID가 있고 SE_GROUP_ENABLED 특성이 있으면 *pbIsMember* 가 false로 설정 하 고, 그렇지 않으면 true를 설정 합니다.  
  
 디버그 빌드에 어설션 오류가 발생 하는 경우 발생 합니다 `pbIsMember` 유효한 포인터가 아닙니다.  
  
> [!NOTE]
>  `CAccessToken` 하면 가장 토큰과 주 토큰 하지 개체 여야 합니다.  
  
##  <a name="createimpersonationtoken"></a>CAccessToken::CreateImpersonationToken  
 가장 액세스 토큰을 만들려면이 메서드를 호출 합니다.  
  
```
bool CreateImpersonationToken(
    CAccessToken* pImp, 
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pImp`  
 새 포인터 `CAccessToken` 개체입니다.  
  
 `sil`  
 지정는 [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) 열거 새 토큰의 가장 수준을 제공 하는 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 `CreateImpersonationToken`호출 [DuplicateToken](http://msdn.microsoft.com/library/windows/desktop/aa446616) 새 가장 토큰을 만들어야 합니다.  
  
##  <a name="createprimarytoken"></a>CAccessToken::CreatePrimaryToken  
 새 기본 토큰을 만들려면이 메서드를 호출 합니다.  
  
```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 *pPri*  
 새 포인터 `CAccessToken` 개체입니다.  
  
 `dwDesiredAccess`  
 새 토큰에 대 한 요청 된 액세스 권한을 지정합니다. 기본값 MAXIMUM_ALLOWED, 호출자가 사용할 수 있는 모든 액세스 권한을 요청 합니다. 참조 [액세스 권한 및 액세스 마스크](http://msdn.microsoft.com/library/windows/desktop/aa374902) 에 더 많은 액세스 권한을 대 한 합니다.  
  
 *pTokenAttributes*  
 에 대 한 포인터는 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) 새 토큰에 대 한 보안 설명자를 지정 하 고 자식 프로세스 토큰을 상속할 수 있는지 여부를 결정 하는 구조입니다. 경우 *pTokenAttributes* null, 토큰 기본 보안 설명자를 가져오고 핸들을 상속할 수 없습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 `CreatePrimaryToken`호출 [DuplicateTokenEx](http://msdn.microsoft.com/library/windows/desktop/aa446617) 새 기본 토큰을 만들어야 합니다.  
  
##  <a name="createprocessasuser"></a>CAccessToken::CreateProcessAsUser  
 가 나타내는 사용자의 보안 컨텍스트에서 실행 되는 새 프로세스를 만들려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool CreateProcessAsUser(
    LPCTSTR pApplicationName,
    LPTSTR pCommandLine,
    LPPROCESS_INFORMATION pProcessInformation,
    LPSTARTUPINFO pStartupInfo,
    DWORD dwCreationFlags = NORMAL_PRIORITY_CLASS,
    bool bLoadProfile = false,
    const CSecurityAttributes* pProcessAttributes = NULL,
    const CSecurityAttributes* pThreadAttributes = NULL,
    bool bInherit = false,
    LPCTSTR pCurrentDirectory = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *pApplicationName*  
 모듈에서 실행 하도록 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 이 매개 변수는 NULL 일 수 없습니다.  
  
 *pCommandLine*  
 실행할 명령줄을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.  
  
 *pProcessInformation*  
 에 대 한 포인터는 [PROCESS_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/ms684873) 새 프로세스에 대 한 식별 정보를 수신 하는 구조입니다.  
  
 *pStartupInfo*  
 에 대 한 포인터는 [STARTUPINFO](http://msdn.microsoft.com/library/windows/desktop/ms686331) 새로운 프로세스에 대 한 주 창의 표시 되는 방식을 지정 하는 구조입니다.  
  
 `dwCreationFlags`  
 프로세스 생성 및 우선 순위 클래스를 제어 하는 추가 플래그를 지정 합니다. Win32 함수를 참조 [CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429) 플래그 목록은 합니다.  
  
 *bLoadProfile*  
 True 인 경우와 사용자 프로필 로드 됩니다 [LoadUserProfile](http://msdn.microsoft.com/library/windows/desktop/bb762281)합니다.  
  
 *pProcessAttributes*  
 에 대 한 포인터는 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) 새로운 프로세스에 대 한 보안 설명자를 지정 하 고 자식 프로세스에 반환된 된 핸들을 상속할 수 있는지 여부를 결정 하는 구조입니다. 경우 *pProcessAttributes* 가 NULL이 고, 프로세스 기본 보안 설명자를 가져옵니다. 핸들을 상속할 수 없습니다.  
  
 *pThreadAttributes*  
 에 대 한 포인터는 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) 새 스레드에 대 한 보안 설명자를 지정 하 고 자식 프로세스에 반환된 된 핸들을 상속할 수 있는지 여부를 결정 하는 구조입니다. 경우 *pThreadAttributes* 은 NULL, 스레드가 기본 보안 설명자를 가져오고 핸들을 상속할 수 없습니다.  
  
 *bInherit*  
 새 프로세스가 핸들 호출 프로세스에서 상속 되는지 여부를 나타냅니다. True 인 경우, 각 상속 가능한 열린 핸들 호출 프로세스에서 새 프로세스에 의해 상속 됩니다. 상속 된 핸들에는 원래 핸들으로 동일한 값 및 액세스 권한이 있어야 합니다.  
  
 *pCurrentDirectory*  
 새로운 프로세스에 대 한 디렉터리와 현재 드라이브를 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 문자열에는 드라이브 문자를 포함 하는 전체 경로 여야 합니다. 이 매개 변수가 NULL 이면 새 프로세스에 호출 프로세스와 같은 현재 드라이브와 디렉터리 제공 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 **CreateProcessAsUser** 사용 하 여는 `CreateProcessAsUser` 나타내는 사용자의 보안 컨텍스트에서 실행 되는 새 프로세스를 만드는 Win32 함수는 `CAccessToken` 개체입니다. 에 대 한 설명을 참조는 [CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429) 함수에 대 한 전체 설명은 필요한 매개 변수입니다.  
  
 이 메서드가 성공 하려면에 대 한는 `CAccessToken` 개체가 보유 하 고 있어야 AssignPrimaryToken (하지 않은 제한 된 토큰) 및 IncreaseQuota 권한.  
  
##  <a name="createrestrictedtoken"></a>CAccessToken::CreateRestrictedToken  
 이 메서드를 새로 만드는 제한 `CAccessToken` 개체입니다.  
  
```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 *pRestrictedToken*  
 새로운 제한 `CAccessToken` 개체입니다.  
  
 `SidsToDisable`  
 A `CTokenGroups` 거부 전용 Sid를 지정 하는 개체입니다.  
  
 *SidsToRestrict*  
 A `CTokenGroups` 제한 Sid를 지정 하는 개체입니다.  
  
 `PrivilegesToDelete`  
 A `CTokenPrivileges` 삭제 하는 권한이 제한 된 토큰에 지정 하는 개체입니다. 기본값은 빈 개체를 만듭니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 `CreateRestrictedToken`사용 하 여는 [CreateRestrictedToken](http://msdn.microsoft.com/library/windows/desktop/aa446583) Win32 함수를 만드는 새 `CAccessToken` 제한 사항이 있는 개체입니다.  
  
> [!NOTE]
>  이 메서드는 에서만 이상 Windows 2000에서 사용할 수 있습니다.  
  
> [!IMPORTANT]
>  사용 하는 경우 `CreateRestrictedToken`, 다음을 확인: 기존 토큰은 유효한 (및 사용자가 입력 한 하지) 및 `SidsToDisable` 및 `PrivilegesToDelete` 모두 유효한 (및 사용자가 입력 한 하지) 됩니다. 메서드가 false를 반환 하면 기능을 거부 합니다.  
  
##  <a name="detach"></a>CAccessToken::Detach  
 액세스 토큰의 소유권을 취소 하려면이 메서드를 호출 합니다.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 핸들을 반환 된 `CAccessToken` 는 분리 되었습니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 해지는 `CAccessToken`의 액세스 토큰의 소유권 합니다.  
  
##  <a name="disableprivilege"></a>CAccessToken::DisablePrivilege  
 권한 사용 하지 않도록 설정 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pszPrivilege`  
 사용 하지 않도록 설정할 수 있는 권한을 포함 하는 문자열에 대 한 포인터는 `CAccessToken` 개체입니다.  
  
 `pPreviousState`  
 에 대 한 포인터는 `CTokenPrivileges` 권한의 이전 상태를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="disableprivileges"></a>CAccessToken::DisablePrivileges  
 하나 이상의 권한을 사용 하지 않도록 설정 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rPrivileges`  
 사용 하지 않도록 설정 하는 권한을 포함 하는 문자열의 배열에 대 한 포인터는 `CAccessToken` 개체입니다.  
  
 `pPreviousState`  
 에 대 한 포인터는 `CTokenPrivileges` 권한의 이전 상태를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="enableprivilege"></a>CAccessToken::EnablePrivilege  
 권한에서 사용 하도록 설정 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pszPrivilege`  
 사용할 수 있도록 권한을 포함 하는 문자열에 대 한 포인터는 `CAccessToken` 개체입니다.  
  
 `pPreviousState`  
 에 대 한 포인터는 `CTokenPrivileges` 권한의 이전 상태를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="enableprivileges"></a>CAccessToken::EnablePrivileges  
 하나 이상의 권한을 사용 하도록 설정 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rPrivileges`  
 사용 하도록 설정 하는 권한을 포함 하는 문자열의 배열에 대 한 포인터는 `CAccessToken` 개체입니다.  
  
 `pPreviousState`  
 에 대 한 포인터는 `CTokenPrivileges` 권한의 이전 상태를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="getdefaultdacl"></a>CAccessToken::GetDefaultDacl  
 호출 반환 하려면이 메서드는 `CAccessToken` 개체의 DACL 기본 합니다.  
  
```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDacl`  
 에 대 한 포인터는 [CDacl 클래스](../../atl/reference/cdacl-class.md) 를 수신할 개체는 **CAccessToken** 개체의 DACL 기본 합니다.  
  
### <a name="return-value"></a>반환 값  
 기본 DACL 되었으면이 고, false 복구 된 그렇지 않으면 true를 반환 합니다.  
  
##  <a name="geteffectivetoken"></a>CAccessToken::GetEffectiveToken  
 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체와 같은 액세스 토큰에 현재 스레드에 적용 합니다.  
  
```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDesiredAccess`  
 액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="getgroups"></a>CAccessToken::GetGroups  
 호출 반환 하려면이 메서드는 `CAccessToken` 토큰 개체의 그룹입니다.  
  
```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 *pGroups*  
 에 대 한 포인터는 [CTokenGroups 클래스](../../atl/reference/ctokengroups-class.md) 그룹 정보를 받을 수 있는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="gethandle"></a>CAccessToken::GetHandle  
 액세스 토큰에 대 한 핸들을 검색 하려면이 메서드를 호출 합니다.  
  
```
HANDLE GetHandle() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 핸들을 반환 합니다.는 `CAccessToken` 개체의 액세스 토큰입니다.  
  
##  <a name="getimpersonationlevel"></a>CAccessToken::GetImpersonationLevel  
 액세스 토큰에서 가장 수준을 가져오려면이 메서드를 호출 합니다.  
  
```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 *pImpersonationLevel*  
 에 대 한 포인터는 [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) 가장 수준 정보를 수신할 열거형 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="getlogonsessionid"></a>CAccessToken::GetLogonSessionId  
 와 관련 된 로그온 세션 ID를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pluid`  
 에 대 한 포인터는 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) 는 로그온 세션 id입니다.는 수신할  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 디버그 빌드에 어설션 오류가 발생 하는 경우 발생 합니다 `pluid` 사용할 값입니다.  
  
##  <a name="getlogonsid"></a>CAccessToken::GetLogonSid  
 와 관련 된 로그온 SID를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool GetLogonSid(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSid`  
 에 대 한 포인터는 [CSid 클래스](../../atl/reference/csid-class.md) 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 디버그 빌드에 어설션 오류가 발생 하는 경우 발생 합니다 *pSid* 사용할 값입니다.  
  
##  <a name="getowner"></a>CAccessToken::GetOwner  
 와 연결 된 소유자를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool GetOwner(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSid`  
 에 대 한 포인터는 [CSid 클래스](../../atl/reference/csid-class.md) 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 소유자는이 액세스 토큰이 적용 되는 동안 생성 된 모든 개체에 기본적으로 설정 됩니다.  
  
##  <a name="getprimarygroup"></a>CAccessToken::GetPrimaryGroup  
 와 연결 된 주 그룹을 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSid`  
 에 대 한 포인터는 [CSid 클래스](../../atl/reference/csid-class.md) 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 그룹은이 액세스 토큰이 적용 되는 동안 생성 된 모든 개체에 기본적으로 설정 됩니다.  
  
##  <a name="getprivileges"></a>CAccessToken::GetPrivileges  
 연결 된 권한을 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pPrivileges`  
 에 대 한 포인터는 [CTokenPrivileges 클래스](../../atl/reference/ctokenprivileges-class.md) 개체 권한을 받게 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="getprocesstoken"></a>CAccessToken::GetProcessToken  
 지정된 프로세스의 액세스 토큰을 사용해서 `CAccessToken`을 초기화하려면 이 메서드를 호출합니다.  
  
```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDesiredAccess`  
 액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.  
  
 *hProcess*  
 액세스 토큰이 열린 프로세스에 대한 핸들입니다. 기본값 `NULL`이 사용된 경우 현재 프로세스가 사용됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 `true`를 반환하고 실패하면 `false`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 호출 된 [OpenProcessToken](http://msdn.microsoft.com/library/aa379295\(vs.85\).aspx) Win32 함수입니다.  
  
##  <a name="getprofile"></a>CAccessToken::GetProfile  
 와 연결 된 사용자 프로필을 가리키는 핸들을 가져올이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
HANDLE GetProfile() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 프로필이 없는 경우 사용자 프로필 또는 NULL을 가리키는 핸들을 반환 합니다.  
  
##  <a name="getsource"></a>CAccessToken::GetSource  
 소스를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 *pSource*  
 에 대 한 포인터는 [TOKEN_SOURCE](http://msdn.microsoft.com/library/windows/desktop/aa379631) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="getstatistics"></a>CAccessToken::GetStatistics  
 와 관련 된 정보를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 *pStatistics*  
 에 대 한 포인터는 [TOKEN_STATISTICS](http://msdn.microsoft.com/library/windows/desktop/aa379632) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="getterminalservicessessionid"></a>CAccessToken::GetTerminalServicesSessionId  
 와 연결 된 터미널 서비스 세션 ID를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 *pdwSessionId*  
 터미널 서비스 세션 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="getthreadtoken"></a>CAccessToken::GetThreadToken  
 초기화 하려면이 메서드를 호출의 `CAccessToken` 주어진된 스레드의에서 토큰으로 사용 합니다.  
  
```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDesiredAccess`  
 액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.  
  
 `hThread`  
 해당 액세스 토큰이 열린 스레드를 처리 합니다.  
  
 `bOpenAsSelf`  
 스레드 호출의 보안 컨텍스트에 대해 수행 되는 액세스 검사 인지를 나타내는 `GetThreadToken` 메서드 또는 호출 스레드에 대 한 프로세스의 보안 컨텍스트에 대 한 합니다.  
  
 이 매개 변수가 false 인 경우 보안 컨텍스트를 사용 하 여 호출 스레드에 대 한 액세스 검사가 수행 됩니다. 스레드는 클라이언트를 가장 하는 경우이 보안 컨텍스트는 클라이언트 프로세스의 수 있습니다. 이 매개 변수가 true 이면 호출 스레드에 대 한 프로세스의 보안 컨텍스트를 사용 하 여 액세스 검사는 수행 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="gettokenid"></a>CAccessToken::GetTokenId  
 와 연결 된 토큰 ID를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool GetTokenId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pluid`  
 에 대 한 포인터는 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) id입니다. 토큰을 받게 됩니다는  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="gettype"></a>CAccessToken::GetType  
 토큰의 형식을 가져오기 위해이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pType`  
 주소는 [TOKEN_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379633) 성공 시 토큰의 유형을 수신 된 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 **TOKEN_TYPE** 주 토큰 및 가장 토큰을 구분 하는 값을 포함 하는 열거형 형식입니다.  
  
##  <a name="getuser"></a>CAccessToken::GetUser  
 연결 된 사용자를 식별 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool GetUser(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSid`  
 에 대 한 포인터는 [CSid 클래스](../../atl/reference/csid-class.md) 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
##  <a name="hkeycurrentuser"></a>CAccessToken::HKeyCurrentUser  
 와 연결 된 사용자 프로필을 가리키는 핸들을 가져올이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
HKEY HKeyCurrentUser() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 프로필이 없는 경우 사용자 프로필 또는 NULL을 가리키는 핸들을 반환 합니다.  
  
##  <a name="impersonate"></a>CAccessToken::Impersonate  
 가장을 할당 하려면이 메서드를 호출 `CAccessToken` 스레드에 있습니다.  
  
```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `hThread`  
 가장 토큰을 지정 하는 스레드를 처리 합니다. 이 핸들을 TOKEN_IMPERSONATE 액세스 권한으로 열려 있어야 합니다. 경우 `hThread` 가 NULL 인 메서드를 호출 하면 스레드는 가장 토큰을 사용 하 여 중지 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 디버그 빌드에 어설션 오류가 발생 하는 경우 발생 합니다 `CAccessToken` 토큰에 대 한 유효한 포인터는 없습니다.  
  
 [CAutoRevertImpersonation 클래스](../../atl/reference/cautorevertimpersonation-class.md) 자동으로 가장된 액세스 토큰 revert 데 사용할 수 있습니다.  
  
##  <a name="impersonateloggedonuser"></a>CAccessToken::ImpersonateLoggedOnUser  
 호출 스레드에서 로그온 한 사용자의 보안 컨텍스트를 가장할 수 있도록 하려면이 메서드를 호출 합니다.  
  
```
bool ImpersonateLoggedOnUser() const throw(...);
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
  
> [!IMPORTANT]
>  어떤 이유로 든 실패 하면 가장 함수 호출 클라이언트를 가장할 수 없습니다 및 클라이언트 요청 호출을 한 프로세스의 보안 컨텍스트에서 수행 됩니다. 관리 그룹의 멤버로 사용자 작업을 수행할 수 있습니다 또는 높은 권한 있는 계정으로 진행 하는 경우 자신이 그렇지 않은 경우 허용 되지 것입니다. 따라서이 함수에 대 한 반환 값 항상 확인 합니다.  
  
##  <a name="istokenrestricted"></a>CAccessToken::IsTokenRestricted  
 테스트 하기 위해이 메서드를 호출 하는 `CAccessToken` 개체 제한 된 Sid의 목록이 포함 되어 있습니다.  
  
```
bool IsTokenRestricted() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 개체 목록을 제한 Sid, 제한 없는 Sid 없는 경우 false를 포함 하는 경우 또는 메서드가 실패 하는 경우 true를 반환 합니다.  
  
##  <a name="loaduserprofile"></a>CAccessToken::LoadUserProfile  
 와 연결 된 사용자 프로필을 로드 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool LoadUserProfile() throw(...);
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 디버그 빌드에 어설션 오류가 발생 하는 경우 발생 합니다는 `CAccessToken` 유효한 토큰을 포함 하지 않거나 사용자가 이미 프로 파일링 하는 경우 존재 합니다.  
  
##  <a name="logonuser"></a>CAccessToken::LogonUser  
 지정된 된 자격 증명와 관련 된 사용자에 대 한 로그온 세션을 만들려면이 메서드를 호출 합니다.  
  
```
bool LogonUser(
    LPCTSTR pszUserName,
    LPCTSTR pszDomain,
    LPCTSTR pszPassword,
    DWORD dwLogonType = LOGON32_LOGON_INTERACTIVE,
    DWORD dwLogonProvider = LOGON32_PROVIDER_DEFAULT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pszUserName`  
 사용자 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 에 로그온 한 사용자 계정의 이름입니다.  
  
 *pszDomain*  
 도메인 또는 계정 데이터베이스를 포함 하는 서버 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터는 `pszUserName` 계정.  
  
 `pszPassword`  
 지정한 사용자 계정에 대 한 일반 텍스트 암호를 지정 하는 null로 끝나는 문자열에 대 한 포인터 `pszUserName`합니다.  
  
 *dwLogonType*  
 수행할 로그온 작업 유형을 지정 합니다. 참조 [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) 내용을 확인 합니다.  
  
 *dwLogonProvider*  
 로그온 공급자를 지정합니다. 참조 [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) 내용을 확인 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 과 연결 될 로그온에서 토큰 발생 액세스는 `CAccessToken`합니다. 이 메서드가 성공 하려면에 대 한는 `CAccessToken` 개체 소유자 기본 신뢰할 수 있는 컴퓨터의 일부로 식별 SE_TCB_NAME 권한을 보유 해야 합니다. 참조 [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) 필요한 권한에 대 한 자세한 내용은 합니다.  
  
##  <a name="opencomclienttoken"></a>CAccessToken::OpenCOMClientToken  
 초기화 하는 클라이언트에서 호출을 처리 하는 COM 서버에서이 메서드를 호출 하 여 `CAccessToken` COM 클라이언트에서 액세스 토큰으로 합니다.  
  
```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDesiredAccess`  
 액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.  
  
 `bImpersonate`  
 True 이면 현재 스레드는이 호출이 완료 되 면 호출 COM 클라이언트를 가장 합니다. False 인 경우, 액세스 토큰이 열린 있지만 스레드가 가장 토큰은이 호출이 완료 될 때입니다.  
  
 `bOpenAsSelf`  
 스레드 호출의 보안 컨텍스트에 대해 수행 되는 액세스 검사 인지를 나타내는 [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) 메서드 또는 호출 스레드에 대 한 프로세스의 보안 컨텍스트에 대 한 합니다.  
  
 이 매개 변수가 false 인 경우 보안 컨텍스트를 사용 하 여 호출 스레드에 대 한 액세스 검사가 수행 됩니다. 스레드는 클라이언트를 가장 하는 경우이 보안 컨텍스트는 클라이언트 프로세스의 수 있습니다. 이 매개 변수가 true 이면 호출 스레드에 대 한 프로세스의 보안 컨텍스트를 사용 하 여 액세스 검사는 수행 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 [CAutoRevertImpersonation 클래스](../../atl/reference/cautorevertimpersonation-class.md) 자동으로 설정 하 여 만든 가장된 액세스 토큰 revert 데 사용할 수는 `bImpersonate` 플래그를 *true*합니다.  
  
##  <a name="opennamedpipeclienttoken"></a>CAccessToken::OpenNamedPipeClientToken  
 호출 하는 서버에서이 메서드를 만들기 요청 초기화를 명명 된 파이프를 통한는 `CAccessToken` 클라이언트에서 액세스 토큰으로 합니다.  
  
```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 *hPipe*  
 명명된 된 파이프에 대 한 핸들입니다.  
  
 `dwDesiredAccess`  
 액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.  
  
 `bImpersonate`  
 True 이면 현재 스레드는이 호출이 완료 되 면 호출 파이프 클라이언트를 가장 합니다. False 인 경우, 액세스 토큰이 열린 있지만 스레드가 가장 토큰은이 호출이 완료 될 때입니다.  
  
 `bOpenAsSelf`  
 스레드 호출의 보안 컨텍스트에 대해 수행 되는 액세스 검사 인지를 나타내는 [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) 메서드 또는 호출 스레드에 대 한 프로세스의 보안 컨텍스트에 대 한 합니다.  
  
 이 매개 변수가 false 인 경우 보안 컨텍스트를 사용 하 여 호출 스레드에 대 한 액세스 검사가 수행 됩니다. 스레드는 클라이언트를 가장 하는 경우이 보안 컨텍스트는 클라이언트 프로세스의 수 있습니다. 이 매개 변수가 true 이면 호출 스레드에 대 한 프로세스의 보안 컨텍스트를 사용 하 여 액세스 검사는 수행 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 [CAutoRevertImpersonation 클래스](../../atl/reference/cautorevertimpersonation-class.md) 자동으로 설정 하 여 만든 가장된 액세스 토큰 revert 데 사용할 수는 `bImpersonate` 플래그를 *true*합니다.  
  
##  <a name="openrpcclienttoken"></a>CAccessToken::OpenRPCClientToken  
 초기화는 RPC 클라이언트에서 호출을 처리 하는 서버에서이 메서드를 호출 하 여 `CAccessToken` 클라이언트에서 액세스 토큰으로 합니다.  
  
```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 *BindingHandle*  
 클라이언트에 대 한 바인딩을 나타내는 서버 바인딩 핸들입니다.  
  
 `dwDesiredAccess`  
 액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.  
  
 `bImpersonate`  
 True 이면 현재 스레드는이 호출이 완료 되 면 호출 RPC 클라이언트를 가장 합니다. False 인 경우, 액세스 토큰이 열린 있지만 스레드가 가장 토큰은이 호출이 완료 될 때입니다.  
  
 `bOpenAsSelf`  
 스레드 호출의 보안 컨텍스트에 대해 수행 되는 액세스 검사 인지를 나타내는 [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) 메서드 또는 호출 스레드에 대 한 프로세스의 보안 컨텍스트에 대 한 합니다.  
  
 이 매개 변수가 false 인 경우 보안 컨텍스트를 사용 하 여 호출 스레드에 대 한 액세스 검사가 수행 됩니다. 스레드는 클라이언트를 가장 하는 경우이 보안 컨텍스트는 클라이언트 프로세스의 수 있습니다. 이 매개 변수가 true 이면 호출 스레드에 대 한 프로세스의 보안 컨텍스트를 사용 하 여 액세스 검사는 수행 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 [CAutoRevertImpersonation 클래스](../../atl/reference/cautorevertimpersonation-class.md) 자동으로 설정 하 여 만든 가장된 액세스 토큰 revert 데 사용할 수는 `bImpersonate` 플래그를 *true*합니다.  
  
##  <a name="openthreadtoken"></a>CAccessToken::OpenThreadToken  
 가장 수준을 설정 하 고 다음을 초기화 하려면이 메서드를 호출는 `CAccessToken` 주어진된 스레드의에서 토큰으로 사용 합니다.  
  
```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDesiredAccess`  
 액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.  
  
 `bImpersonate`  
 True 이면이 메서드가 완료 된 후 스레드가 요청 된 가장 수준에 남게 됩니다. False 이면 스레드는 원래 가장 수준으로 되돌아갑니다.  
  
 `bOpenAsSelf`  
 스레드 호출의 보안 컨텍스트에 대해 수행 되는 액세스 검사 인지를 나타내는 [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) 메서드 또는 호출 스레드에 대 한 프로세스의 보안 컨텍스트에 대 한 합니다.  
  
 이 매개 변수가 false 인 경우 보안 컨텍스트를 사용 하 여 호출 스레드에 대 한 액세스 검사가 수행 됩니다. 스레드는 클라이언트를 가장 하는 경우이 보안 컨텍스트는 클라이언트 프로세스의 수 있습니다. 이 매개 변수가 true 이면 호출 스레드에 대 한 프로세스의 보안 컨텍스트를 사용 하 여 액세스 검사는 수행 됩니다.  
  
 `sil`  
 지정 된 [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) 열거 토큰의 가장 수준을 제공 하는 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 `OpenThreadToken`비슷합니다 [CAccessToken::GetThreadToken](#getthreadtoken), 초기화 하기 전에 가장 수준으로 설정 된 `CAccessToken` 는 스레드의 액세스 토큰에서 합니다.  
  
 [CAutoRevertImpersonation 클래스](../../atl/reference/cautorevertimpersonation-class.md) 자동으로 설정 하 여 만든 가장된 액세스 토큰 revert 데 사용할 수는 `bImpersonate` 플래그를 *true*합니다.  
  
##  <a name="privilegecheck"></a>CAccessToken::PrivilegeCheck  
 호출에 지정 된 특권 집합을 사용할지를 확인 하려면이 메서드는 **CAccessToken** 개체입니다.  
  
```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
     bool* pbResult) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *RequiredPrivileges*  
 에 대 한 포인터는 [PRIVILEGE_SET](http://msdn.microsoft.com/library/windows/desktop/aa379307) 구조입니다.  
  
 *pbResult*  
 이 메서드는 값에 대 한 포인터를 지정 된 권한 중 일부 또는 모두에 사용 되는지 여부를 나타내는 설정한는 `CAccessToken` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 때 `PrivilegeCheck` 반환는 **특성** 의 각 구성원 [LUID_AND_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379263) 해당 권한을 사용 하도록 설정 하는 경우 구조 SE_PRIVILEGE_USED_FOR_ACCESS로 설정 됩니다. 이 메서드는 [PrivilegeCheck](http://msdn.microsoft.com/library/windows/desktop/aa379304) Win32 함수입니다.  
  
##  <a name="revert"></a>CAccessToken::Revert  
 가장 토큰을 사용 하 여 스레드를 중지 하려면이 메서드를 호출 합니다.  
  
```
bool Revert(HANDLE hThread = NULL) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `hThread`  
 가장에서 되돌리려면 스레드를 처리 합니다. 경우 *hThread* 가 NULL 이면 현재 스레드에 간주 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 가장 토큰의 버전으로 자동으로 수행할 수는 [CAutoRevertImpersonation 클래스](../../atl/reference/cautorevertimpersonation-class.md)합니다.  
  
##  <a name="setdefaultdacl"></a>CAccessToken::SetDefaultDacl  
 기본값을 설정 하려면이 메서드 호출의 DACL에서 `CAccessToken` 개체입니다.  
  
```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rDacl`  
 새 기본 [CDacl 클래스](../../atl/reference/cdacl-class.md) 정보입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 기본 DACL은 새 개체가 만들어질 때이 액세스 토큰으로 적용 기본적으로 사용 되는 DACL 됩니다.  
  
##  <a name="setowner"></a>CAccessToken::SetOwner  
 소유자를 설정 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool SetOwner(const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rSid`  
 [CSid 클래스](../../atl/reference/csid-class.md) 소유자 정보를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 소유자는이 액세스 토큰이 적용 되는 동안 생성 된 새 개체에 사용 되는 기본 소유자가입니다.  
  
##  <a name="setprimarygroup"></a>CAccessToken::SetPrimaryGroup  
 주 그룹을 설정 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.  
  
```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rSid`  
 [CSid 클래스](../../atl/reference/csid-class.md) 주 그룹 정보를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 기본 그룹에는이 액세스 토큰이 적용 되는 동안 생성 된 새 개체에 대 한 기본 그룹이입니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATLSecurity 샘플](../../visual-cpp-samples.md)   
 [액세스 토큰](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [클래스 개요](../../atl/atl-class-overview.md)
