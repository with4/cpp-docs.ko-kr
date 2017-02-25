---
title: "CAccessToken Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATLSECURITY/CAccessToken"
  - "ATL.CAccessToken"
  - "CAccessToken"
  - "ATL::CAccessToken"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccessToken class"
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CAccessToken Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 액세스 토큰에 대 한 래퍼입니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CAccessToken  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAccessToken::~CAccessToken](../Topic/CAccessToken::~CAccessToken.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAccessToken::Attach](../Topic/CAccessToken::Attach.md)|지정 된 액세스 토큰 핸들의 소유권을 가져오려면이 메서드를 호출 합니다.|  
|[CAccessToken::CheckTokenMembership](../Topic/CAccessToken::CheckTokenMembership.md)|지정 된 SID를 사용 하는지 확인 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::CreateImpersonationToken](../Topic/CAccessToken::CreateImpersonationToken.md)|새 가장 액세스 토큰을 만들 때이 메서드를 호출 합니다.|  
|[CAccessToken::CreatePrimaryToken](../Topic/CAccessToken::CreatePrimaryToken.md)|새 주 토큰을 만들 때이 메서드를 호출 합니다.|  
|[CAccessToken::CreateProcessAsUser](../Topic/CAccessToken::CreateProcessAsUser.md)|표시 되는 사용자의 보안 컨텍스트에서 실행 되는 새 프로세스를 만들려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::CreateRestrictedToken](../Topic/CAccessToken::CreateRestrictedToken.md)|새로 만들려면이 메서드를 호출 합니다. 제한 된 `CAccessToken` 개체입니다.|  
|[CAccessToken::Detach](../Topic/CAccessToken::Detach.md)|액세스 토큰의 소유권을 해지 하려면이 메서드를 호출 합니다.|  
|[CAccessToken::DisablePrivilege](../Topic/CAccessToken::DisablePrivilege.md)|권한을 사용 하지 않으려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::DisablePrivileges](../Topic/CAccessToken::DisablePrivileges.md)|에 하나 이상의 권한을 사용 하지 않으려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::EnablePrivilege](../Topic/CAccessToken::EnablePrivilege.md)|권한을 사용할 수 있도록이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::EnablePrivileges](../Topic/CAccessToken::EnablePrivileges.md)|에 하나 이상의 권한을 사용 가능 하도록이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetDefaultDacl](../Topic/CAccessToken::GetDefaultDacl.md)|반환 하려면이 메서드를 호출 하 여 `CAccessToken` 개체의 DACL을 기본.|  
|[CAccessToken::GetEffectiveToken](../Topic/CAccessToken::GetEffectiveToken.md)|가져오려면이 메서드를 호출 하는 `CAccessToken` 개체 액세스 토큰을 현재 스레드에 대 한 적용 합니다.|  
|[CAccessToken::GetGroups](../Topic/CAccessToken::GetGroups.md)|반환 하려면이 메서드를 호출 하는 `CAccessToken` 토큰 개체의 그룹입니다.|  
|[CAccessToken::GetHandle](../Topic/CAccessToken::GetHandle.md)|액세스 토큰에 대 한 핸들을 검색 하려면이 메서드를 호출 합니다.|  
|[CAccessToken::GetImpersonationLevel](../Topic/CAccessToken::GetImpersonationLevel.md)|가장 수준의 액세스 토큰에서 가져오도록이 메서드를 호출 합니다.|  
|[CAccessToken::GetLogonSessionId](../Topic/CAccessToken::GetLogonSessionId.md)|관련 된 로그온 세션 ID를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetLogonSid](../Topic/CAccessToken::GetLogonSid.md)|연관 된 로그온 SID를 얻으려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetOwner](../Topic/CAccessToken::GetOwner.md)|연결 소유자를 가져오려면이 메서드를 호출 하 여 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetPrimaryGroup](../Topic/CAccessToken::GetPrimaryGroup.md)|관련 된 주 그룹을 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetPrivileges](../Topic/CAccessToken::GetPrivileges.md)|관련 된 권한을 얻으려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetProcessToken](../Topic/CAccessToken::GetProcessToken.md)|초기화 하는이 메서드를 호출 하는 `CAccessToken` 지정 된 프로세스에서 액세스 토큰.|  
|[CAccessToken::GetProfile](../Topic/CAccessToken::GetProfile.md)|관련 사용자 프로 파일을 가리키는 핸들을 가져오려면이 메서드를 호출 하 여 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetSource](../Topic/CAccessToken::GetSource.md)|소스를 가져오려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetStatistics](../Topic/CAccessToken::GetStatistics.md)|관련 정보를 가져오려면이 메서드를 호출 하 여 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetTerminalServicesSessionId](../Topic/CAccessToken::GetTerminalServicesSessionId.md)|연결 된 터미널 서비스 세션 ID를 가져오려면이 메서드를 호출 하 여 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetThreadToken](../Topic/CAccessToken::GetThreadToken.md)|초기화 하는이 메서드를 호출 하는 `CAccessToken` 토큰에서 지정 된 스레드.|  
|[CAccessToken::GetTokenId](../Topic/CAccessToken::GetTokenId.md)|토큰에 연결 된 ID를 가져오려면이 메서드를 호출 하 여 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetType](../Topic/CAccessToken::GetType.md)|토큰 형식을 가져오려면이 메서드를 호출 하 여 `CAccessToken` 개체입니다.|  
|[CAccessToken::GetUser](../Topic/CAccessToken::GetUser.md)|와 관련 된 사용자를 확인 하려면이 메서드를 호출 하 여 `CAccessToken` 개체입니다.|  
|[CAccessToken::HKeyCurrentUser](../Topic/CAccessToken::HKeyCurrentUser.md)|관련 사용자 프로 파일을 가리키는 핸들을 가져오려면이 메서드를 호출 하 여 `CAccessToken` 개체입니다.|  
|[CAccessToken::Impersonate](../Topic/CAccessToken::Impersonate.md)|할당 된 가장이이 메서드를 호출 `CAccessToken` 스레드 수입니다.|  
|[CAccessToken::ImpersonateLoggedOnUser](../Topic/CAccessToken::ImpersonateLoggedOnUser.md)|호출 스레드는 로그온 한 사용자의 보안 컨텍스트를 가장할 수 있도록이 메서드를 호출 합니다.|  
|[CAccessToken::IsTokenRestricted](../Topic/CAccessToken::IsTokenRestricted.md)|테스트 하는 경우이 메서드를 호출 하는 `CAccessToken` 개체의 제한 된 Sid 목록을 포함 합니다.|  
|[CAccessToken::LoadUserProfile](../Topic/CAccessToken::LoadUserProfile.md)|관련 된 사용자 프로필을 로드 하려면이 메서드를 호출 하는 `CAccessToken` 개체입니다.|  
|[CAccessToken::LogonUser](../Topic/CAccessToken::LogonUser.md)|지정 된 자격 증명과 관련 된 사용자에 로그온 세션을 만들려면이 메서드를 호출 합니다.|  
|[CAccessToken::OpenCOMClientToken](../Topic/CAccessToken::OpenCOMClientToken.md)|초기화 하는 클라이언트에서 호출을 처리 하는 COM 서버 내에서이 메서드를 호출 하는 `CAccessToken` COM 클라이언트에서 액세스 토큰.|  
|[CAccessToken::OpenNamedPipeClientToken](../Topic/CAccessToken::OpenNamedPipeClientToken.md)|초기화는 명명 된 파이프를 통해이 서버에서이 메서드 호출 기록 요청은 `CAccessToken` 액세스 토큰을 클라이언트에서.|  
|[CAccessToken::OpenRPCClientToken](../Topic/CAccessToken::OpenRPCClientToken.md)|초기화 하는 RPC 클라이언트에서 호출을 처리 하는 서버에서이 메서드를 호출의 `CAccessToken` 액세스 토큰은 클라이언트에서에.|  
|[CAccessToken::OpenThreadToken](../Topic/CAccessToken::OpenThreadToken.md)|가장 수준을 설정 하 고 다음 초기화 하려면이 메서드를 호출 하는 `CAccessToken` 토큰에서 지정 된 스레드입니다.|  
|[CAccessToken::PrivilegeCheck](../Topic/CAccessToken::PrivilegeCheck.md)|지정 된 집합의 권한 있는 사용에 있는지 확인 하려면이 메서드를 호출 하는  **CAccessToken**  개체.|  
|[CAccessToken::Revert](../Topic/CAccessToken::Revert.md)|가장 토큰을 사용 하 여 스레드를 중지 하려면이 메서드를 호출 합니다.|  
|[CAccessToken::SetDefaultDacl](../Topic/CAccessToken::SetDefaultDacl.md)|기본값을 설정 하려면이 메서드를 호출의 DACL의 `CAccessToken` 개체입니다.|  
|[CAccessToken::SetOwner](../Topic/CAccessToken::SetOwner.md)|소유자를 설정 하려면이 메서드를 호출 하 여 `CAccessToken` 개체입니다.|  
|[CAccessToken::SetPrimaryGroup](../Topic/CAccessToken::SetPrimaryGroup.md)|주 그룹을 설정 하려면이 메서드를 호출 하 여 `CAccessToken` 개체입니다.|  
  
## 설명  
 [액세스 토큰](http://msdn.microsoft.com/library/windows/desktop/aa374909) 프로세스 또는 스레드의 보안 컨텍스트를 설명 하 고 Windows NT 또는 Windows 2000 시스템에 로그온 한 각 사용자에 게 할당 되는 개체입니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오.  [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 요구 사항  
 **헤더:** atlsecurity.h  
  
## 참고 항목  
 [ATLSecurity 샘플](../../top/visual-cpp-samples.md)   
 [Access Tokens](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Class Overview](../../atl/atl-class-overview.md)