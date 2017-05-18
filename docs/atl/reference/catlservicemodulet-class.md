---
title: "CAtlServiceModuleT 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::Handler
- ATLBASE/ATL::CAtlServiceModuleT::InitializeSecurity
- ATLBASE/ATL::CAtlServiceModuleT::Install
- ATLBASE/ATL::CAtlServiceModuleT::IsInstalled
- ATLBASE/ATL::CAtlServiceModuleT::LogEvent
- ATLBASE/ATL::CAtlServiceModuleT::OnContinue
- ATLBASE/ATL::CAtlServiceModuleT::OnInterrogate
- ATLBASE/ATL::CAtlServiceModuleT::OnPause
- ATLBASE/ATL::CAtlServiceModuleT::OnShutdown
- ATLBASE/ATL::CAtlServiceModuleT::OnStop
- ATLBASE/ATL::CAtlServiceModuleT::OnUnknownRequest
- ATLBASE/ATL::CAtlServiceModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlServiceModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlServiceModuleT::RegisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::Run
- ATLBASE/ATL::CAtlServiceModuleT::ServiceMain
- ATLBASE/ATL::CAtlServiceModuleT::SetServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::Start
- ATLBASE/ATL::CAtlServiceModuleT::Uninstall
- ATLBASE/ATL::CAtlServiceModuleT::Unlock
- ATLBASE/ATL::CAtlServiceModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::WinMain
- ATLBASE/ATL::CAtlServiceModuleT::m_bService
- ATLBASE/ATL::CAtlServiceModuleT::m_dwThreadID
- ATLBASE/ATL::CAtlServiceModuleT::m_hServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::m_status
- ATLBASE/ATL::CAtlServiceModuleT::m_szServiceName
dev_langs:
- C++
helpviewer_keywords:
- CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
caps.latest.revision: 20
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
ms.openlocfilehash: c8fcadca667b618d9e5f112d7910c8e6e6f6c65d
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="catlservicemodulet-class"></a>CAtlServiceModuleT 클래스
이 클래스는 서비스를 구현합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T, UINT nServiceNameID>  
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 클래스에서 파생 된 `CAtlServiceModuleT`합니다.  
  
 *nServiceNameID*  
 서비스의 리소스 식별자입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlServiceModuleT::CAtlServiceModuleT](#catlservicemodulet)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlServiceModuleT::Handler](#handler)|서비스에 대 한 처리기 루틴입니다.|  
|[CAtlServiceModuleT::InitializeSecurity](#initializesecurity)|기본 서비스에 대 한 보안 설정을 제공합니다.|  
|[CAtlServiceModuleT::Install](#install)|설치 하 고 서비스를 만듭니다.|  
|[CAtlServiceModuleT::IsInstalled](#isinstalled)|서비스가 설치 되어 있는지 확인 합니다.|  
|[CAtlServiceModuleT::LogEvent](#logevent)|이벤트 로그에 씁니다.|  
|[CAtlServiceModuleT::OnContinue](#oncontinue)|서비스를 계속 하려면이 메서드를 재정의 합니다.|  
|[CAtlServiceModuleT::OnInterrogate](#oninterrogate)|서비스를 확인 하려면이 메서드를 재정의 합니다.|  
|[CAtlServiceModuleT::OnPause](#onpause)|서비스를 일시 중지 하려면이 메서드를 재정의 합니다.|  
|[CAtlServiceModuleT::OnShutdown](#onshutdown)|서비스를 종료 하려면이 메서드를 재정의 합니다.|  
|[CAtlServiceModuleT::OnStop](#onstop)|서비스를 중지 하려면이 메서드를 재정의 합니다.|  
|[CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest)|알 수 없는 서비스에 요청을 처리 하려면이 메서드를 재정의 합니다.|  
|[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)|명령줄을 구문 분석 하 고 필요한 경우 등록을 수행 합니다.|  
|[CAtlServiceModuleT::PreMessageLoop](#premessageloop)|이 메서드는 메시지 루프에 들어가기 전에 바로 호출 됩니다.|  
|[CAtlServiceModuleT::RegisterAppId](#registerappid)|레지스트리에 서비스를 등록합니다.|  
|[CAtlServiceModuleT::Run](#run)|서비스를 실행 합니다.|  
|[CAtlServiceModuleT::ServiceMain](#servicemain)|서비스 제어 관리자에 의해 호출 되는 메서드.|  
|[CAtlServiceModuleT::SetServiceStatus](#setservicestatus)|서비스의 상태를 업데이트합니다.|  
|[CAtlServiceModuleT::Start](#start)|에 의해 호출 `CAtlServiceModuleT::WinMain` 서비스가 시작할 때입니다.|  
|[CAtlServiceModuleT::Uninstall](#uninstall)|중지 하 고 서비스를 제거 합니다.|  
|[CAtlServiceModuleT::Unlock](#unlock)|서비스의 잠금 횟수를 줄입니다.|  
|[CAtlServiceModuleT::UnregisterAppId](#unregisterappid)|레지스트리에서 서비스를 제거합니다.|  
|[CAtlServiceModuleT::WinMain](#winmain)|이 메서드는 서비스를 실행 하는 데 필요한 코드를 구현 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlServiceModuleT::m_bService](#m_bservice)|프로그램을 서비스로 실행 되 고 나타내는 플래그입니다.|  
|[CAtlServiceModuleT::m_dwThreadID](#m_dwthreadid)|스레드 식별자를 저장 하는 멤버 변수입니다.|  
|[CAtlServiceModuleT::m_hServiceStatus](#m_hservicestatus)|현재 서비스에 대 한 상태 정보 구조에 대 한 핸들을 저장 하는 멤버 변수입니다.|  
|[CAtlServiceModuleT::m_status](#m_status)|현재 서비스에 대 한 상태 정보 구조를 저장 하는 멤버 변수입니다.|  
|[CAtlServiceModuleT::m_szServiceName](#m_szservicename)|등록 되는 서비스의 이름입니다.|  
  
## <a name="remarks"></a>주의  
 `CAtlServiceModuleT`에서 파생 된 [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), ATL 서비스 모듈을 구현 합니다. `CAtlServiceModuleT`명령줄 처리, 설치, 등록 및 제거에 대 한 메서드를 제공 합니다. 추가 기능이 필요한 경우 이러한 및 다른 방법을 재정의할 수 있습니다.  
  
 이 클래스는 사용 되지 않는 대신 [CComModule 클래스](../../atl/reference/ccommodule-class.md) ATL.의 이전 버전에서 사용 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)  
  
 `CAtlServiceModuleT`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="catlservicemodulet"></a>CAtlServiceModuleT::CAtlServiceModuleT  
 생성자입니다.  
  
```
CAtlServiceModuleT() throw();
```  
  
### <a name="remarks"></a>주의  
 데이터 멤버를 초기화 하 고 초기 서비스 상태를 설정 합니다.  
  
##  <a name="handler"></a>CAtlServiceModuleT::Handler  
 서비스에 대 한 처리기 루틴입니다.  
  
```
void Handler(DWORD dwOpcode) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *dwOpcode*  
 처리기 작업을 정의 하는 스위치입니다. 자세한 내용은 설명을 참조 합니다.  
  
### <a name="remarks"></a>주의  
 서비스 제어 관리자 (SCM) 호출 일시 중지 또는 중지와 같은 서비스 및 문제 지침의 상태를 검색 하는 코드입니다. SCM에 아래 표시 된 작업 코드를 전달 `Handler` 서비스에서 수행 해야 할 작업을 나타냅니다.  
  
|작업 코드|의미|  
|--------------------|-------------|  
|SERVICE_CONTROL_STOP|서비스를 중지 합니다. 메서드를 재정의 [CAtlServiceModuleT::OnStop](#onstop) 동작을 변경 하는 atlbase.h에 있습니다.|  
|SERVICE_CONTROL_PAUSE|사용자를 구현 합니다. 빈 메서드를 재정의 [CAtlServiceModuleT::OnPause](#onpause) 서비스를 일시 중지 하는 atlbase.h에 있습니다.|  
|SERVICE_CONTROL_CONTINUE|사용자를 구현 합니다. 빈 메서드를 재정의 [CAtlServiceModuleT::OnContinue](#oncontinue) 서비스를 계속 하는 atlbase.h에 있습니다.|  
|SERVICE_CONTROL_INTERROGATE|사용자를 구현 합니다. 빈 메서드를 재정의 [CAtlServiceModuleT::OnInterrogate](#oninterrogate) 서비스를 질의 하는 atlbase.h에 있습니다.|  
|SERVICE_CONTROL_SHUTDOWN|사용자를 구현 합니다. 빈 메서드를 재정의 [CAtlServiceModuleT::OnShutdown](#onshutdown) 서비스를 종료 하는 atlbase.h에 있습니다.|  
  
 작업 코드 인식 되지 않는 경우 메서드가 [CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest) 호출 됩니다.  
  
 기본 ATL 생성 서비스 stop 명령이 처리 됩니다. SCM에 stop 명령이 통과 한 경우 서비스 지시 SCM 프로그램을 중지 하려고 합니다. 그런 다음 서비스에서 호출 `PostThreadMessage` 자신에 게 종료 메시지를 게시 하도록 합니다. 이 메시지 루프를 종료 하 고 서비스가 종료 됩니다.  
  
##  <a name="initializesecurity"></a>CAtlServiceModuleT::InitializeSecurity  
 기본 서비스에 대 한 보안 설정을 제공합니다.  
  
```
HRESULT InitializeSecurity() throw();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 Visual Studio.NET 2003에서이 메서드는 기본 클래스에서 구현 되지 않았습니다. Visual Studio 프로젝트 마법사에서 생성된 된 코드에서이 메서드를 포함 하지만 ATL 7.1를 사용 하 여 Visual c + +의 이전 버전에서 만든 프로젝트를 컴파일한 경우 컴파일 오류가 발생 합니다. 파생 되는 모든 클래스 `CAtlServiceModuleT` 파생된 클래스에서이 메서드를 구현 해야 합니다.  
  
 에 대 한 호출에서 PKT 수준 인증, RPC_C_IMP_LEVEL_IDENTIFY의 가장 수준 및 적절 한 null이 아닌 보안 설명자를 사용 하 여 **CoInitializeSecurity**합니다.  
  
 마법사 생성 하지 않는 서비스 프로젝트에 대 한 것에  
  
 [!code-cpp[NVC_ATL_Service #&1;](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]  
  
 특성 사용된 하는 서비스 프로젝트에 대 한 것에  
  
 [!code-cpp[NVC_ATL_ServiceAttrib #&1;](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]  
  
##  <a name="install"></a>CAtlServiceModuleT::Install  
 설치 하 고 서비스를 만듭니다.  
  
```
BOOL Install() throw();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 서비스 제어 관리자 (SCM) 데이터베이스에 서비스를 설치 하 고를 서비스 개체를 만듭니다. 서비스를 만들 수는 메시지 상자가 표시 되 고 메서드에서 FALSE가 반환.  
  
##  <a name="isinstalled"></a>CAtlServiceModuleT::IsInstalled  
 서비스가 설치 되어 있는지 확인 합니다.  
  
```
BOOL IsInstalled() throw();
```  
  
### <a name="return-value"></a>반환 값  
 하는 경우 서비스는 설치 됨, FALSE 그렇지 않으면 TRUE를 반환 합니다.  
  
##  <a name="logevent"></a>CAtlServiceModuleT::LogEvent  
 이벤트 로그에 씁니다.  
  
```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pszFormat`  
 이벤트 로그에 쓸 문자열입니다.  
  
 ...  
 이벤트 로그에 기록 되도록 선택적 여분의 문자열입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드 세부 정보를 작성 함수를 사용 하 여 이벤트 로그에 [ReportEvent](http://msdn.microsoft.com/library/windows/desktop/aa363679)합니다. 서비스가 실행 중인 경우에 콘솔에 문자열이 보내집니다.  
  
##  <a name="m_bservice"></a>CAtlServiceModuleT::m_bService  
 프로그램을 서비스로 실행 되 고 나타내는 플래그입니다.  
  
```
BOOL m_bService;
```  
  
### <a name="remarks"></a>주의  
 응용 프로그램 EXE 서비스 EXE 구분 하기 위해 사용 합니다.  
  
##  <a name="m_dwthreadid"></a>CAtlServiceModuleT::m_dwThreadID  
 서비스의 스레드 식별자를 저장 하는 멤버 변수입니다.  
  
```
DWORD m_dwThreadID;
```  
  
### <a name="remarks"></a>주의  
 이 변수는 현재 스레드의 스레드 식별자를 저장합니다.  
  
##  <a name="m_hservicestatus"></a>CAtlServiceModuleT::m_hServiceStatus  
 현재 서비스에 대 한 상태 정보 구조에 대 한 핸들을 저장 하는 멤버 변수입니다.  
  
```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```  
  
### <a name="remarks"></a>주의  
 [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996) 구조는 서비스에 대 한 정보를 포함 합니다.  
  
##  <a name="m_status"></a>CAtlServiceModuleT::m_status  
 현재 서비스에 대 한 상태 정보 구조를 저장 하는 멤버 변수입니다.  
  
```
SERVICE_STATUS m_status;
```  
  
### <a name="remarks"></a>주의  
 [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996) 구조는 서비스에 대 한 정보를 포함 합니다.  
  
##  <a name="m_szservicename"></a>CAtlServiceModuleT::m_szServiceName  
 등록 되는 서비스의 이름입니다.  
  
```
TCHAR [256] m_szServiceName;
```  
  
### <a name="remarks"></a>주의  
 서비스의 이름을 저장 하는 null로 끝나는 문자열입니다.  
  
##  <a name="oncontinue"></a>CAtlServiceModuleT::OnContinue  
 서비스를 계속 하려면이 메서드를 재정의 합니다.  
  
```
void OnContinue() throw();
```  
  
##  <a name="oninterrogate"></a>CAtlServiceModuleT::OnInterrogate  
 서비스를 확인 하려면이 메서드를 재정의 합니다.  
  
```
void OnInterrogate() throw();
```  
  
##  <a name="onpause"></a>CAtlServiceModuleT::OnPause  
 서비스를 일시 중지 하려면이 메서드를 재정의 합니다.  
  
```
void OnPause() throw();
```  
  
##  <a name="onshutdown"></a>CAtlServiceModuleT::OnShutdown  
 서비스를 종료 하려면이 메서드를 재정의 합니다.  
  
```
void OnShutdown() throw();
```  
  
##  <a name="onstop"></a>CAtlServiceModuleT::OnStop  
 서비스를 중지 하려면이 메서드를 재정의 합니다.  
  
```
void OnStop() throw();
```  
  
##  <a name="onunknownrequest"></a>CAtlServiceModuleT::OnUnknownRequest  
 알 수 없는 서비스에 요청을 처리 하려면이 메서드를 재정의 합니다.  
  
```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 */\*dwOpcode\*/*  
 예약됨.  
  
##  <a name="parsecommandline"></a>CAtlServiceModuleT::ParseCommandLine  
 명령줄을 구문 분석 하 고 필요한 경우 등록을 수행 합니다.  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpCmdLine`  
 명령줄입니다.  
  
 `pnRetCode`  
 (전체 걸리는) 하는 경우 해당 등록 하는 HRESULT입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 또는 명령줄에 제공 된 RGS 파일 등록 하지 못한 경우 false에서 true를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 명령줄을 구문 분석 하 고 레지스터 또는 필요한 경우 제공된 된 RGS 파일의 등록을 취소 합니다. 이 메서드는 호출 [CAtlExeModuleT::ParseCommandLine](../../atl/reference/catlexemodulet-class.md#parsecommandline) 를 확인 하려면 **/RegServer** 및 **/UnregServer**합니다. 인수 추가 **-/ 서비스** 서비스를 등록 합니다.  
  
##  <a name="premessageloop"></a>CAtlServiceModuleT::PreMessageLoop  
 이 메서드는 메시지 루프에 들어가기 전에 바로 호출 됩니다.  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nShowCmd`  
 이 매개 변수가 전달 [CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop)합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 서비스에 대 한 사용자 지정 초기화 코드를 추가 하려면이 메서드를 재정의 합니다.  
  
##  <a name="registerappid"></a>CAtlServiceModuleT::RegisterAppId  
 레지스트리에 서비스를 등록합니다.  
  
```
inline HRESULT RegisterAppId(bool bService = false) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *bService*  
 서비스를 등록 하려면 true 여야 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="run"></a>CAtlServiceModuleT::Run  
 서비스를 실행 합니다.  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nShowCmd`  
 창 표시 방법을 지정 합니다. 이 매개 변수에서 설명 하는 값 중 하나일 수는 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) 섹션입니다. 기본값은 SW_HIDE 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 호출 된 후 **실행** 호출 [CAtlServiceModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop), 및 [CAtlExeModuleT::PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop)합니다.  
  
##  <a name="servicemain"></a>CAtlServiceModuleT::ServiceMain  
 이 메서드는 서비스 제어 관리자에 의해 호출 됩니다.  
  
```
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *dwArgc*  
 Argc 인수입니다.  
  
 *lpszArgv*  
 Argv 인수입니다.  
  
### <a name="remarks"></a>주의  
 서비스 제어 관리자 (SCM)를 호출 하 여 `ServiceMain` 제어판에서 서비스 응용 프로그램을 여는 경우 서비스를 선택 하 고 시작을 클릭 합니다.  
  
 SCM 후 호출 `ServiceMain`, 서비스의 SCM 처리기 함수를 지정 해야 합니다. 이 함수는 SCM을 (예: 일시 중지 또는 중지) 특정 지침을 전달 하 고 서비스의 상태를 가져올 수 있습니다. 그 이후에, [CAtlServiceModuleT::Run](#run) 서비스의 주요 작업을 수행 하기 위해 호출 됩니다. **실행** 서비스가 중지 될 때까지 계속 실행 합니다.  
  
##  <a name="setservicestatus"></a>CAtlServiceModuleT::SetServiceStatus  
 이 메서드는 서비스의 상태를 업데이트합니다.  
  
```
void SetServiceStatus(DWORD dwState) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `dwState`  
 새 상태입니다. 참조 [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241) 가능한 값입니다.  
  
### <a name="remarks"></a>주의  
 서비스에 대 한 서비스 제어 관리자의 상태 정보를 업데이트합니다. 에 의해 호출 됩니다 [CAtlServiceModuleT::Run](#run), [CAtlServiceModuleT::ServiceMain](#servicemain) 및 다른 처리기 메서드. 상태도 멤버 변수에 저장 됩니다 [CAtlServiceModuleT::m_status](#m_status)합니다.  
  
##  <a name="start"></a>CAtlServiceModuleT::Start  
 에 의해 호출 `CAtlServiceModuleT::WinMain` 서비스가 시작할 때입니다.  
  
```
HRESULT Start(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nShowCmd`  
 창 표시 방법을 지정 합니다. 이 매개 변수에서 설명 하는 값 중 하나일 수는 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) 섹션입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 [CAtlServiceModuleT::WinMain](#winmain) 메서드 등록 및 설치를 모두 처리 뿐만 아니라 작업 관련 레지스트리 항목을 제거 하 고 모듈을 제거 합니다. 서비스를 실행 하는 경우 `WinMain` 호출 **시작**합니다.  
  
##  <a name="uninstall"></a>CAtlServiceModuleT::Uninstall  
 중지 하 고 서비스를 제거 합니다.  
  
```
BOOL Uninstall() throw();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 실행에서 서비스를 중지 하 고 서비스 제어 관리자 데이터베이스에서 제거 합니다.  
  
##  <a name="unlock"></a>CAtlServiceModuleT::Unlock  
 서비스의 잠금 횟수를 줄입니다.  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>반환 값  
 진단에 유용 하 고 디버깅 수 있는 잠금 수를 반환 합니다.  
  
##  <a name="unregisterappid"></a>CAtlServiceModuleT::UnregisterAppId  
 레지스트리에서 서비스를 제거합니다.  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="winmain"></a>CAtlServiceModuleT::WinMain  
 이 메서드는 서비스를 시작 하는 데 필요한 코드를 구현 합니다.  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nShowCmd`  
 창 표시 방법을 지정 합니다. 이 매개 변수에서 설명 하는 값 중 하나일 수는 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) 섹션입니다.  
  
### <a name="return-value"></a>반환 값  
 서비스의 반환 값을 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 명령줄 처리 (으로 [CAtlServiceModuleT::ParseCommandLine](#parsecommandline)) 한 후 서비스를 시작 (사용 하 여 [CAtlServiceModuleT::Start](#start)).  
  
## <a name="see-also"></a>참고 항목  
 [CAtlExeModuleT 클래스](../../atl/reference/catlexemodulet-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

