---
title: "CWinApp 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinApp
- AFXWIN/CWinApp
- AFXWIN/CWinApp::CWinApp
- AFXWIN/CWinApp::AddDocTemplate
- AFXWIN/CWinApp::AddToRecentFileList
- AFXWIN/CWinApp::ApplicationRecoveryCallback
- AFXWIN/CWinApp::CloseAllDocuments
- AFXWIN/CWinApp::CreatePrinterDC
- AFXWIN/CWinApp::DelRegTree
- AFXWIN/CWinApp::DoMessageBox
- AFXWIN/CWinApp::DoWaitCursor
- AFXWIN/CWinApp::EnableD2DSupport
- AFXWIN/CWinApp::EnableHtmlHelp
- AFXWIN/CWinApp::EnableTaskbarInteraction
- AFXWIN/CWinApp::ExitInstance
- AFXWIN/CWinApp::GetApplicationRecoveryParameter
- AFXWIN/CWinApp::GetApplicationRecoveryPingInterval
- AFXWIN/CWinApp::GetApplicationRestartFlags
- AFXWIN/CWinApp::GetAppRegistryKey
- AFXWIN/CWinApp::GetDataRecoveryHandler
- AFXWIN/CWinApp::GetFirstDocTemplatePosition
- AFXWIN/CWinApp::GetHelpMode
- AFXWIN/CWinApp::GetNextDocTemplate
- AFXWIN/CWinApp::GetPrinterDeviceDefaults
- AFXWIN/CWinApp::GetProfileBinary
- AFXWIN/CWinApp::GetProfileInt
- AFXWIN/CWinApp::GetProfileString
- AFXWIN/CWinApp::GetSectionKey
- AFXWIN/CWinApp::HideApplication
- AFXWIN/CWinApp::HtmlHelp
- AFXWIN/CWinApp::InitInstance
- AFXWIN/CWinApp::IsTaskbarInteractionEnabled
- AFXWIN/CWinApp::LoadCursor
- AFXWIN/CWinApp::LoadIcon
- AFXWIN/CWinApp::LoadOEMCursor
- AFXWIN/CWinApp::LoadOEMIcon
- AFXWIN/CWinApp::LoadStandardCursor
- AFXWIN/CWinApp::LoadStandardIcon
- AFXWIN/CWinApp::OnDDECommand
- AFXWIN/CWinApp::OnIdle
- AFXWIN/CWinApp::OpenDocumentFile
- AFXWIN/CWinApp::ParseCommandLine
- AFXWIN/CWinApp::PreTranslateMessage
- AFXWIN/CWinApp::ProcessMessageFilter
- AFXWIN/CWinApp::ProcessShellCommand
- AFXWIN/CWinApp::ProcessWndProcException
- AFXWIN/CWinApp::Register
- AFXWIN/CWinApp::RegisterWithRestartManager
- AFXWIN/CWinApp::ReopenPreviousFilesAtRestart
- AFXWIN/CWinApp::RestartInstance
- AFXWIN/CWinApp::RestoreAutosavedFilesAtRestart
- AFXWIN/CWinApp::Run
- AFXWIN/CWinApp::RunAutomated
- AFXWIN/CWinApp::RunEmbedded
- AFXWIN/CWinApp::SaveAllModified
- AFXWIN/CWinApp::SelectPrinter
- AFXWIN/CWinApp::SetHelpMode
- AFXWIN/CWinApp::SupportsApplicationRecovery
- AFXWIN/CWinApp::SupportsAutosaveAtInterval
- AFXWIN/CWinApp::SupportsAutosaveAtRestart
- AFXWIN/CWinApp::SupportsRestartManager
- AFXWIN/CWinApp::Unregister
- AFXWIN/CWinApp::WinHelp
- AFXWIN/CWinApp::WriteProfileBinary
- AFXWIN/CWinApp::WriteProfileInt
- AFXWIN/CWinApp::WriteProfileString
- AFXWIN/CWinApp::EnableShellOpen
- AFXWIN/CWinApp::LoadStdProfileSettings
- AFXWIN/CWinApp::OnContextHelp
- AFXWIN/CWinApp::OnFileNew
- AFXWIN/CWinApp::OnFileOpen
- AFXWIN/CWinApp::OnFilePrintSetup
- AFXWIN/CWinApp::OnHelp
- AFXWIN/CWinApp::OnHelpFinder
- AFXWIN/CWinApp::OnHelpIndex
- AFXWIN/CWinApp::OnHelpUsing
- AFXWIN/CWinApp::RegisterShellFileTypes
- AFXWIN/CWinApp::SetAppID
- AFXWIN/CWinApp::SetRegistryKey
- AFXWIN/CWinApp::UnregisterShellFileTypes
- AFXWIN/CWinApp::m_bHelpMode
- AFXWIN/CWinApp::m_eHelpType
- AFXWIN/CWinApp::m_hInstance
- AFXWIN/CWinApp::m_lpCmdLine
- AFXWIN/CWinApp::m_nCmdShow
- AFXWIN/CWinApp::m_pActiveWnd
- AFXWIN/CWinApp::m_pszAppID
- AFXWIN/CWinApp::m_pszAppName
- AFXWIN/CWinApp::m_pszExeName
- AFXWIN/CWinApp::m_pszHelpFilePath
- AFXWIN/CWinApp::m_pszProfileName
- AFXWIN/CWinApp::m_pszRegistryKey
- AFXWIN/CWinApp::m_dwRestartManagerSupportFlags
- AFXWIN/CWinApp::m_nAutosaveInterval
- AFXWIN/CWinApp::m_pDataRecoveryHandler
dev_langs:
- C++
helpviewer_keywords:
- CWinApp class
- application objects [C++]
- HINSTANCE
- main object
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
caps.latest.revision: 27
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
ms.openlocfilehash: 292816c8f753a7b47b563a3fcd0fa336e08acd6a
ms.lasthandoff: 02/24/2017

---
# <a name="cwinapp-class"></a>CWinApp 클래스
Windows 응용 프로그램 개체를 파생하는 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CWinApp : public CWinThread  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CWinApp::CWinApp](#cwinapp)|`CWinApp` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CWinApp::AddDocTemplate](#adddoctemplate)|문서 서식 파일을 사용할 수 있는 문서 템플릿의 응용 프로그램의 목록에 추가합니다.|  
|[CWinApp::AddToRecentFileList](#addtorecentfilelist)|가장 최근에 사용한 (MRU) 파일 목록에 파일 이름을 추가합니다.|  
|[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)|응용 프로그램이 예기치 않게 종료 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CWinApp::CloseAllDocuments](#closealldocuments)|열려 있는 모든 문서를 닫습니다.|  
|[CWinApp::CreatePrinterDC](#createprinterdc)|프린터 장치 컨텍스트를 만듭니다.|  
|[CWinApp::DelRegTree](#delregtree)|지정된 된 키와 모든 하위 키를 삭제합니다.|  
|[CWinApp::DoMessageBox](#domessagebox)|구현 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) 응용 프로그램입니다.|  
|[CWinApp::DoWaitCursor](#dowaitcursor)|대기 커서를 설정 및 해제 합니다.|  
|[CWinApp::EnableD2DSupport](#enabled2dsupport)|응용 프로그램을 사용 하면 `D2D` 지원 합니다. 주 창이 초기화되기 전에 이 메서드를 호출합니다.|  
|[CWinApp::EnableHtmlHelp](#enablehtmlhelp)|WinHelp 보다는 응용 프로그램을 위해 HTMLHelp를 구현합니다.|  
|[CWinApp::EnableTaskbarInteraction](#enabletaskbarinteraction)|작업 표시줄으로 상호 작용할을 수 있습니다.|  
|[CWinApp::ExitInstance](#exitinstance)|응용 프로그램이 종료 될 때 정리를 수행 하려면이 옵션을 재정의 합니다.|  
|[CWinApp::GetApplicationRecoveryParameter](#getapplicationrecoveryparameter)|응용 프로그램 복구 방법에 대 한 입력된 매개 변수를 검색합니다.|  
|[CWinApp::GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|다시 시작 관리자를 반환 하는 복구 콜백 함수에 대 한 대기 시간의 길이 반환 합니다.|  
|[CWinApp::GetApplicationRestartFlags](#getapplicationrestartflags)|다시 시작 관리자에 대 한 플래그를 반환 합니다.|  
|[CWinApp::GetAppRegistryKey](#getappregistrykey)|HKEY_CURRENT_USER에 대 한 반환 키\\"소프트웨어" \RegistryKey\ProfileName 합니다.|  
|[CWinApp::GetDataRecoveryHandler](#getdatarecoveryhandler)|응용 프로그램의이 인스턴스에 대 한 데이터 복구 처리기를 가져옵니다.|  
|[CWinApp::GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|첫 번째 문서 서식 파일의 위치를 검색 합니다.|  
|[CWinApp::GetHelpMode](#gethelpmode)|응용 프로그램에서 사용 하는 도움말의 유형을 검색 합니다.|  
|[CWinApp::GetNextDocTemplate](#getnextdoctemplate)|문서 서식 파일의 위치를 검색 합니다. 재귀적으로 사용할된 수 있습니다.|  
|[CWinApp::GetPrinterDeviceDefaults](#getprinterdevicedefaults)|프린터 장치 기본값을 검색합니다.|  
|[CWinApp::GetProfileBinary](#getprofilebinary)|응용 프로그램의 진입점에서 이진 데이터를 검색합니다. INI 파일입니다.|  
|[CWinApp::GetProfileInt](#getprofileint)|응용 프로그램의 항목에서 정수를 검색합니다. INI 파일입니다.|  
|[CWinApp::GetProfileString](#getprofilestring)|응용 프로그램의 진입점에서 문자열을 검색합니다. INI 파일입니다.|  
|[CWinApp::GetSectionKey](#getsectionkey)|HKEY_CURRENT_USER에 대 한 반환 키\\"소프트웨어" \RegistryKey\AppName\lpszSection 합니다.|  
|[CWinApp::HideApplication](#hideapplication)|모든 문서를 닫기 전에 응용 프로그램을 숨깁니다.|  
|[CWinApp::HtmlHelp](#htmlhelp)|호출 된 `HTMLHelp` Windows 함수입니다.|  
|[CWinApp::InitInstance](#initinstance)|창 개체를 만드는 것과 같은 Windows 인스턴스 초기화를 수행 하도록 재정의 합니다.|  
|[CWinApp::IsTaskbarInteractionEnabled](#istaskbarinteractionenabled)|Windows 7 작업 표시줄의 상호 작용 사용 되는지 여부를 알려 줍니다.|  
|[CWinApp::LoadCursor](#loadcursor)|커서 리소스를 로드합니다.|  
|[CWinApp::LoadIcon](#loadicon)|아이콘 리소스를 로드합니다.|  
|[CWinApp::LoadOEMCursor](#loadoemcursor)|로드 Windows OEM 커서를 미리 정의 하는 **OCR_** WINDOWS에서 상수를 지정 합니다.&8;.|  
|[CWinApp::LoadOEMIcon](#loadoemicon)|Windows OEM 미리 정의 된 아이콘을 로드 하는 **OIC_** WINDOWS에서 상수를 지정 합니다.&8;.|  
|[CWinApp::LoadStandardCursor](#loadstandardcursor)|로드 Windows 커서를 미리 정의 하는 **IDC_** WINDOWS에서 상수를 지정 합니다.&8;.|  
|[CWinApp::LoadStandardIcon](#loadstandardicon)|Windows 미리 정의 된 아이콘을 로드 하는 **IDI_** WINDOWS에서 상수를 지정 합니다.&8;.|  
|[CWinApp::OnDDECommand](#onddecommand)|호출에 대 한 응답에 대 한 동적 데이터 프레임 워크에서 교환 (DDE)는 명령을 실행 합니다.|  
|[CWinApp::OnIdle](#onidle)|응용 프로그램별 유휴 시간 처리를 수행 하려면 재정의 합니다.|  
|[CWinApp::OpenDocumentFile](#opendocumentfile)|문서를 열려면 파일에서 프레임 워크에 의해 호출 됩니다.|  
|[CWinApp::ParseCommandLine](#parsecommandline)|개별 매개 변수 및 명령줄에 플래그를 구문 분석합니다.|  
|[경우](#pretranslatemessage)|Windows 함수에 디스패치 되기 전에 메시지를 필터링 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934)합니다.|  
|[CWinApp::ProcessMessageFilter](#processmessagefilter)|응용 프로그램에 도달 하기 전에 특정 메시지를 차단 합니다.|  
|[CWinApp::ProcessShellCommand](#processshellcommand)|명령줄 인수 및 플래그를 처리합니다.|  
|[CWinApp::ProcessWndProcException](#processwndprocexception)|응용 프로그램의 메시지 및 명령 처리기에 의해 throw 되는 모든 처리 되지 않은 예외를 가로챕니다.|  
|[CWinApp::Register](#register)|사용자 지정 된 등록을 수행 합니다.|  
|[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)|다시 시작 관리자를 응용 프로그램을 등록합니다.|  
|[CWinApp::ReopenPreviousFilesAtRestart](#reopenpreviousfilesatrestart)|다시 시작 관리자 응용 프로그램이 예기치 않게 종료 될 때 열려 있던 파일이 닫았다가 다시 열거나 있는지 여부를 결정 합니다.|  
|[CWinApp::RestartInstance](#restartinstance)|다시 시작 관리자에 의해 시작 되는 응용 프로그램 다시 시작을 처리 합니다.|  
|[CWinApp::RestoreAutosavedFilesAtRestart](#restoreautosavedfilesatrestart)|응용 프로그램을 다시 시작 될 때 다시 시작 관리자 자동 저장 된 파일을 복원할지 여부를 결정 합니다.|  
|[Cwinapp:: Run](#run)|기본 메시지 루프를 실행합니다. 메시지 루프를 사용자 지정 하려면 재정의 합니다.|  
|[CWinApp::RunAutomated](#runautomated)|응용 프로그램의 명령줄에 대 한 테스트는 **/Automation** 옵션입니다. 사용되지 않습니다. 대신,의 값을 사용 하 여 [CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated) 호출한 후 [ParseCommandLine](#parsecommandline)합니다.|  
|[CWinApp::RunEmbedded](#runembedded)|응용 프로그램의 명령줄에 대 한 테스트는 **포함/** 옵션입니다. 사용되지 않습니다. 대신,의 값을 사용 하 여 [CCommandLineInfo::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded) 호출한 후 [ParseCommandLine](#parsecommandline)합니다.|  
|[CWinApp::SaveAllModified](#saveallmodified)|수정 된 모든 문서를 저장 하 라는 메시지입니다.|  
|[CWinApp::SelectPrinter](#selectprinter)|인쇄 대화 상자를 통해 사용자가 이전에 표시 된 프린터를 선택 합니다.|  
|[CWinApp::SetHelpMode](#sethelpmode)|설정 하 고 응용 프로그램에서 사용 하는 도움말 유형을 초기화 합니다.|  
|[CWinApp::SupportsApplicationRecovery](#supportsapplicationrecovery)|다시 시작 관리자가 예기치 않게 종료 되는 응용 프로그램 복구 되는지 확인 합니다.|  
|[CWinApp::SupportsAutosaveAtInterval](#supportsautosaveatinterval)|일정 한 간격으로 다시 시작 관리자에서 열려 있는 문서 있는지 여부를 결정 합니다.|  
|[CWinApp::SupportsAutosaveAtRestart](#supportsautosaveatrestart)|결정 있는지 여부를 다시 시작 관리자에서 응용 프로그램 다시 시작 될 때 모든 열린 문서입니다.|  
|[CWinApp::SupportsRestartManager](#supportsrestartmanager)|응용 프로그램이 다시 시작 관리자를 지원 하는지 여부를 결정 합니다.|  
|[CWinApp::Unregister](#unregister)|등록을 취소 하 여 등록할 수에 알려진 모든 항목은 `CWinApp` 개체입니다.|  
|[CWinApp::WinHelp](#winhelp)|호출 된 `WinHelp` Windows 함수입니다.|  
|[CWinApp::WriteProfileBinary](#writeprofilebinary)|응용 프로그램의 항목에 이진 데이터를 씁니다. INI 파일입니다.|  
|[Cwinapp:: Writeprofileint](#writeprofileint)|응용 프로그램의 항목에 정수를 씁니다. INI 파일입니다.|  
|[CWinApp::WriteProfileString](#writeprofilestring)|응용 프로그램의 항목에는 문자열을 씁니다. INI 파일입니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CWinApp::EnableShellOpen](#enableshellopen)|Windows 파일 관리자에서 데이터 파일을 열 수 있습니다.|  
|[CWinApp::LoadStdProfileSettings](#loadstdprofilesettings)|로드 표준입니다. INI 파일 설정을 사용 하면 MRU 목록 기능을 파일입니다.|  
|[CWinApp::OnContextHelp](#oncontexthelp)|응용 프로그램 내에서 SHIFT + F1 도움말을 처리합니다.|  
|[CWinApp::OnFileNew](#onfilenew)|구현 하는 `ID_FILE_NEW` 명령입니다.|  
|[CWinApp::OnFileOpen](#onfileopen)|구현 하는 `ID_FILE_OPEN` 명령입니다.|  
|[CWinApp::OnFilePrintSetup](#onfileprintsetup)|구현 하는 `ID_FILE_PRINT_SETUP` 명령입니다.|  
|[CWinApp::OnHelp](#onhelp)|현재 컨텍스트를 사용하여 응용 프로그램 내에서 F1 도움말을 처리합니다.|  
|[CWinApp::OnHelpFinder](#onhelpfinder)|`ID_HELP_FINDER` 및 `ID_DEFAULT_HELP` 명령을 처리합니다.|  
|[CWinApp::OnHelpIndex](#onhelpindex)|`ID_HELP_INDEX` 명령을 처리하고 기본 도움말 항목을 제공합니다.|  
|[CWinApp::OnHelpUsing](#onhelpusing)|`ID_HELP_USING` 명령을 처리합니다.|  
|[CWinApp::RegisterShellFileTypes](#registershellfiletypes)|응용 프로그램의 모든 문서 형식을 Windows 파일 관리자에 등록합니다.|  
|[CWinApp::SetAppID](#setappid)|응용 프로그램에 대 한 응용 프로그램 사용자 모델 ID를 명시적으로 설정합니다. 모든 사용자 인터페이스 (가장 좋은 위치는 응용 프로그램 생성자는) 사용자에 게 표시 하기 전에이 메서드를 호출 해야 합니다.|  
|[CWinApp::SetRegistryKey](#setregistrykey)|에서는 응용 프로그램 설정을 대신 레지스트리에 저장 하도록 지정 합니다. INI 파일입니다.|  
|[CWinApp::UnregisterShellFileTypes](#unregistershellfiletypes)|응용 프로그램의 모든 문서 유형에 Windows 파일 관리자에 등록을 취소합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CWinApp::m_bHelpMode](#m_bhelpmode)|사용자 (일반적으로 SHIFT + f&1;을 사용 하 여 호출) 도움말 컨텍스트 모드에서 인지 여부를 나타냅니다.|  
|[CWinApp::m_eHelpType](#m_ehelptype)|응용 프로그램에서 사용 하는 도움말의 유형을 지정 합니다.|  
|[CWinApp::m_hInstance](#m_hinstance)|응용 프로그램의 현재 인스턴스를 식별합니다.|  
|[CWinApp::m_lpCmdLine](#m_lpcmdline)|응용 프로그램에 대 한 명령줄을 지정 하는 null로 끝나는 문자열을 가리킵니다.|  
|[CWinApp::m_nCmdShow](#m_ncmdshow)|창을 처음 표시 방법을 지정 합니다.|  
|[CWinApp::m_pActiveWnd](#m_pactivewnd)|OLE 서버에 내부 활성화 되 면 컨테이너 응용 프로그램의 주 창에 대 한 포인터입니다.|  
|[CWinApp::m_pszAppID](#m_pszappid)|응용 프로그램 사용자 모델 id입니다.|  
|[CWinApp::m_pszAppName](#m_pszappname)|응용 프로그램의 이름을 지정합니다.|  
|[CWinApp::m_pszExeName](#m_pszexename)|응용 프로그램의 모듈 이름입니다.|  
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|응용 프로그램의 도움말 파일의 경로입니다.|  
|[CWinApp::m_pszProfileName](#m_pszprofilename)|응용 프로그램의 합니다. INI 파일 이름입니다.|  
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|응용 프로그램 프로필 설정을 저장 하기 위한 전체 레지스트리 키를 확인 하는 데 사용 합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|다시 시작 관리자가 동작 하는 방식을 결정 하는 플래그입니다.|  
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|시간 (밀리초) 간에 자동으로 저장 길이입니다.|  
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|응용 프로그램에 대 한 데이터 복구 처리기에 대 한 포인터입니다.|  
  
## <a name="remarks"></a>주의  
 응용 프로그램 개체는 응용 프로그램 (및 각 인스턴스의)을 초기화 하는 데 및 응용 프로그램을 실행 하기 위한 멤버 함수를 제공 합니다.  
  
 Microsoft Foundation 클래스를 사용 하는 각 응용 프로그램에서 파생 된 개체를 하나 포함할 수 있습니다 `CWinApp`합니다. 이 개체 다른 c + +의 전역 개체 생성 될 때 생성 되 고 이미 제공 되는 Windows를 호출 하는 경우는 `WinMain` Microsoft Foundation 클래스 라이브러리에서 제공 하는 함수입니다. 파생 된 선언 `CWinApp` 전역 수준에서 개체입니다.  
  
 응용 프로그램에서 클래스를 파생 시키는 경우 `CWinApp`, 재정의 [InitInstance](#initinstance) 멤버 함수를 응용 프로그램의 주 창 개체를 만듭니다.  
  
 이외에 `CWinApp` 멤버 함수는 Microsoft Foundation 클래스 라이브러리에 액세스 하려면 다음 전역 함수를 제공 합니다 프로그램 `CWinApp` 개체 및 기타 전역 정보:  
  
- [AfxGetApp](application-information-and-management.md#afxgetapp) 에 포인터를 가져옵니다는 `CWinApp` 개체입니다.  
  
- [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle) 현재 응용 프로그램 인스턴스에 대 한 핸들을 가져옵니다.  
  
- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle) 응용 프로그램의 리소스에 대 한 핸들을 가져옵니다.  
  
- [AfxGetAppName](application-information-and-management.md#afxgetappname) 응용 프로그램의 이름을 포함 하는 문자열에 포인터를 가져옵니다. 또는에 대 한 포인터가 있는 경우는 `CWinApp` 개체를 사용 하 여 `m_pszExeName` 응용 프로그램의 이름을 가져옵니다.  
  
 참조 [CWinApp: 응용 프로그램 클래스](../../mfc/cwinapp-the-application-class.md) 에 대 한 자세한는 `CWinApp` 클래스를 다음의 개요를 포함 합니다.  
  
- `CWinApp`-응용 프로그램 마법사에서 작성 된 코드를 파생 합니다.  
  
- `CWinApp`응용 프로그램의 실행 순서에서의 역할입니다.  
  
- `CWinApp`기본 멤버 함수 구현입니다.  
  
- `CWinApp`키 / / 재정의 가능 합니다.  
  
 **m_hPrevInstance** 데이터 멤버를 더 이상 존재 합니다. 검색의 이전 인스턴스에 대 한 자세한 내용은 `CWinApp`에서 기술 자료 문서 "방법 식별는 이전 인스턴스의 응용 프로그램" (KB106385)을 참조 하십시오. [http://support.microsoft.com/default.aspxscid=kb;en-us;106385](http://support.microsoft.com/default.aspxscid=kb;en-us;106385)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 `CWinApp`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="adddoctemplate"></a>CWinApp::AddDocTemplate  
 응용 프로그램 유지 관리 하는 사용 가능한 문서 서식 파일의 목록에 문서 서식 파일을 추가 하려면이 멤버 함수를 호출 합니다.  
  
```  
void AddDocTemplate(CDocTemplate* pTemplate);
```  
  
### <a name="parameters"></a>매개 변수  
 `pTemplate`  
 에 대 한 포인터는 `CDocTemplate` 추가할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 호출 하기 전에 모든 문서 응용 프로그램에 템플릿을 추가 해야 [RegisterShellFileTypes](#registershellfiletypes)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&35;](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]  
  
##  <a name="addtorecentfilelist"></a>CWinApp::AddToRecentFileList  
 이 멤버 함수를 추가 하려면 호출 `lpszPathName` 최근에 사용한 파일 목록에 있습니다.  
  
```  
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszPathName`  
 파일의 경로입니다.  
  
### <a name="remarks"></a>주의  
 호출 해야는 [LoadStdProfileSettings](#loadstdprofilesettings) 멤버 함수를이 멤버 함수를 사용 하기 전에 현재 최근에 사용한 파일 목록을 로드 합니다.  
  
 프레임 워크 파일을 열거나 새 이름으로 파일을 저장 하는 다른 이름으로 저장 명령을 실행 하는 경우이 멤버 함수를 호출 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&36;](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]  
  
##  <a name="applicationrecoverycallback"></a>CWinApp::ApplicationRecoveryCallback  
 응용 프로그램이 예기치 않게 종료 될 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpvParam`  
 나중에 사용하기 위해 예약되어 있습니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공 하면&0; 이 속성을&0;이 아닌 오류가 발생 합니다.  
  
### <a name="remarks"></a>주의  
 응용 프로그램 다시 시작 관리자를 지 원하는 경우 프레임 워크는 응용 프로그램에서 예기치 않게 종료 될 때이 함수를 호출 합니다.  
  
 기본 구현은 `ApplicationRecoveryCallback` 사용 하 여는 `CDataRecoveryHandler` 현재 열려 있는 문서의 목록을 레지스트리에 저장할 수 있습니다. 이 메서드는 파일을 모두 자동으로 저장 되지 않습니다.  
  
 동작을 사용자 지정 하려면이 함수는 파생에 재정의 [CWinApp 클래스](../../mfc/reference/cwinapp-class.md) 하거나 사용자 고유의 응용 프로그램 복구 방법에 대 한 매개 변수로 전달 [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)합니다.  
  
##  <a name="closealldocuments"></a>CWinApp::CloseAllDocuments  
 이 멤버 함수를 종료 하기 전에 열린 문서 모두 닫기를 호출 합니다.  
  
```  
void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>매개 변수  
 `bEndSession`  
 Windows 세션을 종료 되 고 있는지 여부를 지정 합니다. **TRUE** 종료 하 고, 그렇지 않으면 세션 되 고 있으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 호출 [HideApplication](#hideapplication) 호출 하기 전에 `CloseAllDocuments`합니다.  
  
##  <a name="createprinterdc"></a>CWinApp::CreatePrinterDC  
 선택한 프린터에서 프린터 장치 컨텍스트 (DC)를 만들려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL CreatePrinterDC(CDC& dc);
```  
  
### <a name="parameters"></a>매개 변수  
 `dc`  
 프린터 장치 컨텍스트에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 프린터 장치 컨텍스트의 성공적으로 만들어지면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 `CreatePrinterDC`전달 참조에 의해 인쇄에 사용할 수 있도록 장치 컨텍스트를 초기화 합니다.  
  
 인쇄 했으면 함수가 성공할 경우 장치 컨텍스트를 파기 해야 합니다. 소멸자를 하도록 할 수는 [CDC](../../mfc/reference/cdc-class.md) 개체, 작업을 수행 하거나 호출 하 여 명시적으로 수행할 수 있습니다 [CDC::DeleteDC](../../mfc/reference/cdc-class.md#deletedc)합니다.  
  
##  <a name="cwinapp"></a>CWinApp::CWinApp  
 생성 된 `CWinApp` 개체 및 패스 `lpszAppName` 응용 프로그램 이름으로 저장 됩니다.  
  
```  
CWinApp(LPCTSTR lpszAppName = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszAppName`  
 Windows에서 사용 하는 응용 프로그램 이름을 포함 하는 null로 끝나는 문자열입니다. 이 인수가 제공 되지 않으면 아니거나 면 **NULL**, `CWinApp` 리소스 문자열을 사용 하 여 **AFX_IDS_APP_TITLE** 또는 실행 파일의 파일 이름입니다.  
  
### <a name="remarks"></a>주의  
 전역 개체를 생성 해야 하면 `CWinApp`-클래스를 파생 합니다. 하나씩만 있을 수 `CWinApp` 응용 프로그램의 개체입니다. 에 대 한 포인터를 저장 하는 생성자는 `CWinApp` 개체 있도록 `WinMain` 초기화 하 고 응용 프로그램을 실행 하는 함수 개체의 멤버를 호출할 수 있습니다.  
  
##  <a name="delregtree"></a>CWinApp::DelRegTree  
 특정 레지스트리 키와 모든 하위 키를 삭제합니다.  
  
```  
LONG DelRegTree(
    HKEY hParentKey,  
    const CString& strKeyName);

 
LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName,
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *hParentKey*  
 레지스트리 키를 처리 합니다.  
  
 *strKeyName*  
 삭제할 레지스트리 키의 이름입니다.  
  
 *pTM*  
 CAtlTransactionManager 개체에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 반환 값은 error_success가 있습니다. 함수가 실패 한 경우 반환 값은 Winerror.h에 정의 되어 있는&0;이 아닌 오류 코드입니다.  
  
### <a name="remarks"></a>주의  
 지정된 된 키와 해당 하위 키를 삭제 하려면이 함수를 호출 합니다.  
  
##  <a name="domessagebox"></a>CWinApp::DoMessageBox  
 전역 함수에 대 한 메시지 상자를 구현 하려면이 멤버 함수를 호출 하는 프레임 워크 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)합니다.  
  
```  
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,  
    UINT nType,  
    UINT nIDPrompt);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszPrompt*  
 메시지 상자에 텍스트의 주소입니다.  
  
 `nType`  
 메시지 상자 [스타일](../../mfc/reference/message-box-styles.md)합니다.  
  
 `nIDPrompt`  
 도움말 컨텍스트 문자열에는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 동일한 값으로 반환 `AfxMessageBox`합니다.  
  
### <a name="remarks"></a>주의  
 메시지 상자;를 열려면이 멤버 함수를 호출 하지 마십시오 사용 하 여 `AfxMessageBox` 대신 합니다.  
  
 전체 응용 프로그램 처리를 사용자 지정 하려면이 멤버 함수를 재정의 `AfxMessageBox` 호출 합니다.  
  
##  <a name="dowaitcursor"></a>CWinApp::DoWaitCursor  
 이 멤버 함수를 구현 하는 프레임 워크에서 호출 [CWaitCursor](../../mfc/reference/cwaitcursor-class.md), [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), 및 [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)합니다.  
  
```  
virtual void DoWaitCursor(int nCode);
```  
  
### <a name="parameters"></a>매개 변수  
 `nCode`  
 이 매개 변수가 1 이면 대기 커서를 나타납니다. 0 인 경우, 대기 커서 참조 횟수가 증가 하지 않고 복원 됩니다. –&1;, waitcursor 종료 됩니다.  
  
### <a name="remarks"></a>주의  
 기본 모래 시계 커서를 구현합니다. `DoWaitCursor`참조 횟수를 유지 관리합니다. 양수, 모래 시계 커서 표시 됩니다.  
  
 일반적으로 호출 하지 않기 동안 `DoWaitCursor` 대기 커서를 변경 하거나 대기 커서가 표시 되는 동안에 추가 처리를 수행 하려면이 멤버 함수를 직접 재정의할 수 있습니다.  
  
 대기 커서를 구현 하는 보다 쉽게, 더 효율적인 방법으로 사용 하 여 `CWaitCursor`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&37;](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]  
  
##  <a name="enabled2dsupport"></a>CWinApp::EnableD2DSupport  
 [!INCLUDE[dev10_sp1required](../../mfc/reference/includes/dev10_sp1required_md.md)]  
  
 응용 프로그램 D2D 지원할을 수 있습니다. 주 창이 초기화되기 전에 이 메서드를 호출합니다.  
  
```  
BOOL EnableD2DSupport(
D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
### <a name="parameters"></a>매개 변수  
 `d2dFactoryType`  
 D2d 및 리소스의 스레딩 모델을 만듭니다.  
  
 `writeFactoryType`  
 쓰기 팩터리 개체를 공유 하거나 격리 됩니다 있는지 여부를 지정 하는 값  
  
### <a name="return-value"></a>반환 값  
 D2D 지원을 했는지 사용, FALSE-그렇지 않은 경우 TRUE를 반환합니다  
  
##  <a name="enablehtmlhelp"></a>CWinApp::EnableHtmlHelp  
 생성자 내에서이 멤버 함수를 호출 하면 `CWinApp`-응용 프로그램의 도움말에 대 한 HTMLHelp를 사용 하 여 클래스를 파생 합니다.  
  
```  
void EnableHtmlHelp();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="enableshellopen"></a>CWinApp::EnableShellOpen  
 일반적으로이 함수를 호출 하면 `InitInstance` 재정의 시, 응용 프로그램의 사용자가 파일을 Windows 파일 관리자 내에서 두 번 클릭 될 때 데이터 파일을 열 수 있도록 합니다.  
  
```  
void EnableShellOpen();
```  
  
### <a name="remarks"></a>주의  
 호출의 `RegisterShellFileTypes` 멤버 함수를 통해이 함께에서 작동 하거나 제공 된 합니다. 문서 형식의 수동 등록에 대 한 응용 프로그램과 함께 REG 파일입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&38;](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]  
  
##  <a name="enabletaskbarinteraction"></a>CWinApp::EnableTaskbarInteraction  
 작업 표시줄으로 상호 작용할을 수 있습니다.  
  
```  
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bEnable`  
 Windows 7 작업 표시줄의 상호 작용을 활성화 해야 하는지 여부를 지정 합니다 ( `TRUE`)를 사용 하지 않도록 설정 하거나 ( `FALSE`).  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 경우 작업 표시줄의 상호 작용을 설정 하거나 해제할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 주 창의 만들기 전에이 메서드를 호출 해야, 어설션 및 반환 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="exitinstance"></a>CWinApp::ExitInstance  
 프레임 워크 내에서 호출의 **실행** 멤버 함수를 응용 프로그램의이 인스턴스를 종료 합니다.  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>반환 값  
 응용 프로그램의 종료 코드입니다. 0은 오류를 나타내며 0 보다 큰 값에 오류가 발생 합니다. 이 값에서 반환 된 값으로 사용 됩니다 `WinMain`합니다.  
  
### <a name="remarks"></a>주의  
 호출 하지 마십시오이 멤버 함수 어디에서 나 하지만 내는 **실행** 멤버 함수입니다.  
  
 기본 구현은이 함수는 응용 프로그램의 프레임 워크 옵션을 씁니다. INI 파일입니다. 응용 프로그램이 종료 될 때 정리를 수행 하려면이 함수를 재정의 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&39;](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]  
  
##  <a name="getapplicationrecoveryparameter"></a>CWinApp::GetApplicationRecoveryParameter  
 응용 프로그램 복구 방법에 대 한 입력된 매개 변수를 검색합니다.  
  
```  
virtual LPVOID GetApplicationRecoveryParameter();
```  
  
### <a name="return-value"></a>반환 값  
 기본 입력된 매개 변수는 응용 프로그램 복구 방법입니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 동작은 반환 `NULL`합니다.  
  
 자세한 내용은 참조 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)합니다.  
  
##  <a name="getapplicationrecoverypinginterval"></a>CWinApp::GetApplicationRecoveryPingInterval  
 다시 시작 관리자를 반환 하는 복구 콜백 함수에 대 한 대기 시간의 길이 반환 합니다.  
  
```  
virtual DWORD GetApplicationRecoveryPingInterval();
```  
  
### <a name="return-value"></a>반환 값  
 길이 시간 (밀리초)입니다.  
  
### <a name="remarks"></a>주의  
 예기치 않게 다시 시작 관리자가 종료를 통해 등록 된 응용 프로그램 복구 콜백 함수를 호출 하는 응용 프로그램이 열려 있는 문서를 저장 하 려 합니다. 기본 복구 콜백 함수는 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)합니다.  
  
 프레임 워크를 반환 하는 복구 콜백 함수에 대 한 대기 시간의 길이가 ping 간격입니다. Ping 간격을 재정의 하 여 사용자 지정할 수 있습니다 `CWinApp::GetApplicationRecoveryPingInterval` 또는 사용자 지정 값을 제공 하 여 `RegisterWithRestartManager`합니다.  
  
##  <a name="getapplicationrestartflags"></a>CWinApp::GetApplicationRestartFlags  
 다시 시작 관리자에 대 한 플래그를 반환 합니다.  
  
```  
virtual DWORD GetApplicationRestartFlags();
```  
  
### <a name="return-value"></a>반환 값  
 다시 시작 관리자에 대 한 플래그입니다. 기본 구현에서는 0을 반환합니다.  
  
### <a name="remarks"></a>주의  
 다시 시작 관리자에 대 한 플래그 기본 구현으로 효과가 없습니다. 나중에 사용할 제공 됩니다.  
  
 에 등록할 때 응용 프로그램 다시 시작 관리자를 사용 하 여 플래그를 설정할 [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)합니다.  
  
 다시 시작 관리자 플래그에 대 한 가능한 값은 다음과 같습니다.  
  
- `RESTART_NO_CRASH`  
  
- `RESTART_NO_HANG`  
  
- `RESTART_NO_PATCH`  
  
- `RESTART_NO_REBOOT`  
  
##  <a name="getappregistrykey"></a>CWinApp::GetAppRegistryKey  
 HKEY_CURRENT_USER에 대 한 키를 반환 합니다.\\"소프트웨어" \RegistryKey\ProfileName 합니다.  
  
```  
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pTM`  
 `CAtlTransactionManager` 개체에 대한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 응용 프로그램 키 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getdatarecoveryhandler"></a>CWinApp::GetDataRecoveryHandler  
 응용 프로그램의이 인스턴스에 대 한 데이터 복구 처리기를 가져옵니다.  
  
```  
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```  
  
### <a name="return-value"></a>반환 값  
 데이터 복구는 응용 프로그램의이 인스턴스에 대 한 처리기입니다.  
  
### <a name="remarks"></a>주의  
 다시 시작 관리자를 사용 하는 각 응용 프로그램의 인스턴스 하나가 있어야 합니다.는 [CDataRecoveryHandler 클래스](../../mfc/reference/cdatarecoveryhandler-class.md)합니다. 이 클래스는 열려 있는 문서 및 자동 저장 파일을 모니터링 합니다. 동작은 `CDataRecoveryHandler` 다시 시작 관리자의 구성에 따라 달라 집니다. 자세한 내용은 참조 [CDataRecoveryHandler 클래스](../../mfc/reference/cdatarecoveryhandler-class.md)합니다.  
  
 이 메서드가 반환 `NULL` 운영 체제에서 이전의 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]합니다. 다시 시작 관리자는 운영 체제에서 지원 되지 않습니다 이전의 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]합니다.  
  
 응용 프로그램에 현재 없는 경우 데이터 복구 처리기,이 메서드가 하나 만들고에 대 한 포인터를 반환 합니다.  
  
##  <a name="getfirstdoctemplateposition"></a>CWinApp::GetFirstDocTemplatePosition  
 응용 프로그램에서 첫 번째 문서 서식 파일의 위치를 가져옵니다.  
  
```  
POSITION GetFirstDocTemplatePosition() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **위치** 반복 또는 개체 포인터 검색;에 사용할 수 있는 값 **NULL** 목록이 비어 있는 경우.  
  
### <a name="remarks"></a>주의  
 사용 하는 **위치** 값에 대 한 호출에서 반환 된 [GetNextDocTemplate](#getnextdoctemplate) 는 처음에 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 개체입니다.  
  
##  <a name="gethelpmode"></a>CWinApp::GetHelpMode  
 응용 프로그램에서 사용 하는 도움말의 유형을 검색 합니다.  
  
```  
AFX_HELP_TYPE GetHelpMode();
```  
  
### <a name="return-value"></a>반환 값  
 응용 프로그램에서 사용 하는 도움말 형식입니다. 참조 [CWinApp::m_eHelpType](#m_ehelptype) 에 대 한 자세한 내용은 합니다.  
  
##  <a name="getnextdoctemplate"></a>CWinApp::GetNextDocTemplate  
 로 식별 되는 문서 템플릿을 가져옵니다 `pos`, 다음 설정 `pos` 에 **위치** 값입니다.  
  
```  
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 에 대 한 참조는 **위치** 에 대 한 이전 호출에서 반환 된 값 `GetNextDocTemplate` 또는 [GetFirstDocTemplatePosition](#getfirstdoctemplateposition)합니다. 값은 다음 위치에이 호출으로 업데이트 됩니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 사용할 수 있습니다 `GetNextDocTemplate` 정방향 반복 루프를 호출 하 여 초기 위치를 설정 하는 경우에 `GetFirstDocTemplatePosition`합니다.  
  
 확인 해야 하면 **위치** 값이 유효 합니다. 올바르지 않을 경우 Microsoft Foundation 클래스 라이브러리의 디버그 버전 어설션 합니다.  
  
 검색 된 문서 서식 파일은 마지막 하는 경우를 사용할 수의 새 값이 다음 `pos` 로 설정 된 **NULL**합니다.  
  
##  <a name="getprinterdevicedefaults"></a>CWinApp::GetPrinterDeviceDefaults  
 인쇄를 위한 프린터 장치 컨텍스트를 준비 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```  
  
### <a name="parameters"></a>매개 변수  
 *pPrintDlg*  
 에 대 한 포인터는 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 Windows에서 현재 프린터 기본값을 검색합니다. 필요한 경우, 또는 사용 하 여 인쇄 설정에서 사용자가 마지막 프린터 구성 설정으로 INI 파일입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&40;](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]  
  
##  <a name="getprofilebinary"></a>CWinApp::GetProfileBinary  
 지정된 된 응용 프로그램의 레지스트리 섹션 내에 있는 항목에서 이진 데이터를 검색 하려면이 멤버 함수를 호출 하거나. INI 파일입니다.  
  
```  
BOOL GetProfileBinary(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszSection*  
 항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다.  
  
 *lpszEntry*  
 값을 검색할 항목이 포함된 null로 끝나는 문자열을 가리킵니다.  
  
 *ppData*  
 데이터의 주소를 수신 하는 포인터를 가리킵니다.  
  
 *pBytes*  
 크기 (바이트)의 데이터를 수신할 UINT 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 없으므로 대/소문자 구분 하지에서 문자열의 *lpszSection* 및 *lpszEntry* 경우에서 매개 변수 다를 수 있습니다.  
  
> [!NOTE]
> **GetProfileBinary** 버퍼 할당에 해당 주소를 반환 하 고 \* *ppData*합니다. 호출자는 사용 하 여 버퍼를 해제 하기 위한 **delete**합니다.  
  
> [!IMPORTANT]
>  이 함수에서 반환된 데이터는 NULL로 끝나지 않아도 되며 호출자는 유효성 검사를 수행해야 합니다. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&41;](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]  
  
 추가 예제를 참조 하십시오. [CWinApp::WriteProfileBinary](#writeprofilebinary)합니다.  
  
##  <a name="getprofileint"></a>CWinApp::GetProfileInt  
 .INI 파일 또는 응용 프로그램 레지스트리의 지정된 섹션 내에 있는 항목으로 정수 값을 검색하려면 이 멤버 함수를 호출합니다.  
  
```  
UINT GetProfileInt(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    int nDefault);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszSection`  
 항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다.  
  
 `lpszEntry`  
 값을 검색할 항목이 포함된 null로 끝나는 문자열을 가리킵니다.  
  
 `nDefault`  
 프레임워크에서 항목을 찾을 수 없는 경우 반환할 기본값을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 문자열의 정수 값은 지정된 항목 다음에 오게 됩니다. 항목을 찾지 못한 경우 반환 값은 `nDefault` 매개 변수의 값입니다. 지정한 항목에 해당하는 값이 정수가 아닌 경우 반환 값은 0입니다.  
  
 이 멤버 함수는 .INI 파일에서 값에 대한&16; 진수 표기법을 지원합니다. 부호 있는 정수를 검색할 경우 값을 `int`로 캐스팅해야 합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 대소문자를 구분하지 않으므로 `lpszSection` 및 `lpszEntry` 매개 변수의 문자열 대소문자가 다를 수 있습니다.  
  
> [!IMPORTANT]
>  이 함수에서 반환된 데이터는 NULL로 끝나지 않아도 되며 호출자는 유효성 검사를 수행해야 합니다. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&42;](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]  
  
 추가 예제를 참조 하십시오. [cwinapp:: Writeprofileint](#writeprofileint)합니다.  
  
##  <a name="getprofilestring"></a>CWinApp::GetProfileString  
 응용 프로그램의 레지스트리에 지정된 된 섹션 내에 있는 항목에 대 한 연결 문자열을 검색 하려면이 함수를 호출 하거나. INI 파일입니다.  
  
```  
CString GetProfileString(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszDefault = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszSection`  
 항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다.  
  
 `lpszEntry`  
 해당 문자열을 검색할 항목이 포함 된 null로 끝나는 문자열을 가리킵니다. 이 값이 아니어야 **NULL**합니다.  
  
 `lpszDefault`  
 초기화 파일의 항목을 찾을 수 없는 경우 지정 된 항목에 대 한 기본 문자열 값을 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값은 응용 프로그램의 문자열입니다. INI 파일 또는 `lpszDefault` 문자열을 찾을 수 없는 경우. 프레임 워크에서 지 원하는 최대 문자열 길이 `_MAX_PATH`합니다. 경우 `lpszDefault` 는 **NULL**, 반환 값은 빈 문자열입니다.  
  
### <a name="remarks"></a>주의  
  
> [!IMPORTANT]
>  이 함수에서 반환된 데이터는 NULL로 끝나지 않아도 되며 호출자는 유효성 검사를 수행해야 합니다. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&43;](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 다른 예에 대 한 예제를 참조 하십시오. [CWinApp::GetProfileInt](#getprofileint)합니다.  
  
##  <a name="getsectionkey"></a>CWinApp::GetSectionKey  
 HKEY_CURRENT_USER에 대 한 키를 반환 합니다.\\"소프트웨어" \RegistryKey\AppName\lpszSection 합니다.  
  
```  
HKEY GetSectionKey(
LPCTSTR lpszSection,  
CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszSection`  
 가져올 키의 이름입니다.  
  
 `pTM`  
 `CAtlTransactionManager` 개체에 대한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 섹션 키 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="hideapplication"></a>CWinApp::HideApplication  
 열려 있는 문서를 닫기 전에 응용 프로그램을 숨기려면이 멤버 함수를 호출 합니다.  
  
```  
void HideApplication();
```  
  
##  <a name="htmlhelp"></a>CWinApp::HtmlHelp  
 HTMLHelp 응용 프로그램을 호출 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual void HtmlHelp(
    DWORD_PTR dwData,  
    UINT nCmd = 0x000F);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwData`  
 추가 데이터를 지정합니다. 값에 따라 사용 되는 값은 `nCmd` 매개 변수입니다.  
  
 `nCmd`  
 요청한 도움말의 형식을 지정합니다. 가능한 값 목록과 미치는 영향에 대 한는 `dwData` 매개 변수를 참조는 `uCommand` 에 대 한 the HTMLHelp API에서 함수에 설명 된 매개 변수는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 또한 HTMLHelp 응용 프로그램을 호출 하려면이 함수를 호출 합니다.  
  
 프레임 워크 때 자동으로 닫힙니다 HTMLHelp 응용 프로그램 응용 프로그램을 종료 합니다.  
  
##  <a name="initinstance"></a>CWinApp::InitInstance  
 Windows에서는 동시에 실행 되도록 같은 프로그램의 복사본이 여러 개 있습니다.  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>반환 값  
 초기화에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 응용 프로그램 초기화는 개념적으로 두 섹션으로 구분 됩니다: 첫 번째 이루어집니다 일회성 응용 프로그램 초기화 시간 프로그램 실행 시간과 각 실행 인스턴스 초기화를 처음으로 포함 하 여 프로그램 실행의 복사본입니다. 프레임 워크의 구현 `WinMain` 이 함수를 호출 합니다.  
  
 재정의 `InitInstance` Windows에서 실행 중인 응용 프로그램의 각 새 인스턴스를 초기화 합니다. 재정의 하는 일반적으로 `InitInstance` 주 창의 개체를 생성 하 고 설정 하는 `CWinThread::m_pMainWnd` 해당 창을 가리키도록 데이터 멤버입니다. 이 멤버 함수 재정의에 대 한 자세한 내용은 참조 하십시오. [CWinApp: 응용 프로그램 클래스](../../mfc/cwinapp-the-application-class.md)합니다.  
  
> [!NOTE]
>  MFC 응용 프로그램은 단일 스레드 아파트 (STA)으로 초기화 되어야 합니다. 호출 하는 경우 [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) 에 프로그램 `InitInstance` 재정의 지정 `COINIT_APARTMENTTHREADED` (대신 `COINIT_MULTITHREADED`). 자세한 내용은 참조 PRB: MFC 응용 프로그램이 다른 형식으로 다중 스레드 아파트 (828643)에서 응용 프로그램을 초기화 하는 경우 응답 하지 [http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCListView #&9;](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]  
  
##  <a name="istaskbarinteractionenabled"></a>CWinApp::IsTaskbarInteractionEnabled  
 Windows 7 작업 표시줄의 상호 작용 사용 되는지 여부를 알려 줍니다.  
  
```  
virtual BOOL IsTaskbarInteractionEnabled();
```  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 경우 `EnableTaskbarInteraction` 가 호출 된 운영 체제는 Windows 7 이상.  
  
### <a name="remarks"></a>주의  
 작업 표시줄의 상호 작용 MDI 응용 프로그램 마우스 포인터를 응용 프로그램 작업 표시줄 단추 위로 가져갈 때 표시 되는 별도 탭 형식의 미리 보기에 MDI 자식 폼의 콘텐츠를 표시 하는 것을 의미 합니다.  
  
##  <a name="loadcursor"></a>CWinApp::LoadCursor  
 로 명명 된 커서 리소스 로드 `lpszResourceName` 에 지정 된 또는 `nIDResource` 현재 실행 파일에서.  
  
```  
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;  ```  
  
### Parameters  
 `lpszResourceName`  
 Points to a null-terminated string that contains the name of the cursor resource. You can use a `CString` for this argument.  
  
 `nIDResource`  
 ID of the cursor resource. For a list of resources, see [LoadCursor](http://msdn.microsoft.com/library/windows/desktop/ms648391) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 A handle to a cursor if successful; otherwise **NULL**.  
  
### Remarks  
 `LoadCursor` loads the cursor into memory only if it has not been previously loaded; otherwise, it retrieves a handle of the existing resource.  
  
 Use the [LoadStandardCursor](#loadstandardcursor) or [LoadOEMCursor](#loadoemcursor) member function to access the predefined Windows cursors.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]  
  
##  <a name="loadicon"></a>  CWinApp::LoadIcon  
 Loads the icon resource named by `lpszResourceName` or specified by `nIDResource` from the executable file.  
  
```  
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;  ```  
  
### <a name="parameters"></a>매개 변수  
 `lpszResourceName`  
 아이콘 리소스의 이름을 포함 하는 null로 끝나는 문자열을 가리킵니다. 사용할 수도 있습니다는 `CString` 이 인수에 대 한 합니다.  
  
 `nIDResource`  
 아이콘 리소스의 ID.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 아이콘에 대 한 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 `LoadIcon`이 로드 되지 않은 이전에; 하는 경우에 아이콘을 로드 합니다. 그렇지 않으면 기존 리소스 핸들을 검색합니다.  
  
 사용할 수는 [LoadStandardIcon](#loadstandardicon) 또는 [LoadOEMIcon](#loadoemicon) 미리 정의 된 Windows 아이콘에 액세스 하는 멤버 함수입니다.  
  
> [!NOTE]
>  이 멤버 함수는 Win32 API 함수를 호출 [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072), 크기가 준수 하는 아이콘을 로드 하기만 하는 **SM_CXICON** 및 **SM_CYICON** 시스템 메트릭 값입니다.  
  
##  <a name="loadoemcursor"></a>CWinApp::LoadOEMCursor  
 창을 로드로 지정 된 커서 리소스 미리 정의 된 `nIDCursor`합니다.  
  
```  
HCURSOR LoadOEMCursor(UINT nIDCursor) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDCursor`  
 **OCR_** 매니페스트는 미리 정의 된 Windows 커서를 지정 하는 상수 식별자입니다. 있어야 **#define OEMRESOURCE** 전에 **#include \<afxwin.h >** 에 액세스 하는 **OCR_** WINDOWS에서 상수입니다.&8;.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 커서에 대 한 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 사용 된 `LoadOEMCursor` 또는 [LoadStandardCursor](#loadstandardcursor) 미리 정의 된 Windows 커서에 액세스 하는 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&45;](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]  
  
 [!code-cpp[NVC_MFCWindowing #&46;](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]  
  
##  <a name="loadoemicon"></a>CWinApp::LoadOEMIcon  
 창을 로드로 지정 된 아이콘 리소스를 미리 정의 된 `nIDIcon`합니다.  
  
```  
HICON LoadOEMIcon(UINT nIDIcon) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDIcon`  
 **OIC_** 매니페스트 미리 정의 된 Windows 아이콘을 지정 하는 상수 식별자입니다. 있어야 **#define OEMRESOURCE** 하기 전에 **#include \<afxwin.h >** 액세스 하는 **OIC_** WINDOWS에서 상수입니다.&8;.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 아이콘에 대 한 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 사용 된 `LoadOEMIcon` 또는 [LoadStandardIcon](#loadstandardicon) 미리 정의 된 Windows 아이콘에 액세스 하는 멤버 함수입니다.  
  
##  <a name="loadstandardcursor"></a>CWinApp::LoadStandardCursor  
 미리 정의 된 커서 리소스는 Windows를 로드 하는 `lpszCursorName` 지정 합니다.  
  
```  
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszCursorName`  
 **IDC_** 매니페스트는 미리 정의 된 Windows 커서를 지정 하는 상수 식별자입니다. 이러한 식별자는 WINDOWS에서 정의 됩니다.&8;. 다음 목록은 가능한 미리 정의 된 값과 의미에 대 한 `lpszCursorName`:  
  
- **IDC_ARROW** 표준 화살표 커서  
  
- **IDC_IBEAM** 커서 표준 텍스트 삽입  
  
- **IDC_WAIT** Windows에는 시간이 많이 걸리는 작업을 수행 하는 경우에 사용 되는 모래 시계 커서  
  
- **IDC_CROSS** 선택에 대 한 십자 모양 커서  
  
- **IDC_UPARROW** 위로 화살표  
  
- **IDC_SIZE** Obsolete를 지원 합니다; 사용 **IDC_SIZEALL**  
  
- **IDC_SIZEALL**&4; 방향 화살표가 있습니다. 창 크기를 조정 하는 데 커서입니다.  
  
- **IDC_ICON** Obsolete 되거나 지원 되지 않는 합니다. 사용 하 여 **IDC_ARROW**합니다.  
  
- **IDC_SIZENWSE** 왼쪽 위 및 오른쪽 아래 끝이 있는 양방향 화살표  
  
- **IDC_SIZENESW** 상단 오른쪽 및 왼쪽 아래에서 끝나는와 양방향 화살표  
  
- **IDC_SIZEWE** 가로 양방향 화살표  
  
- **IDC_SIZENS** 세로 양방향 화살표  
  
### <a name="return-value"></a>반환 값  
 성공 하면 커서에 대 한 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 사용 된 `LoadStandardCursor` 또는 [LoadOEMCursor](#loadoemcursor) 미리 정의 된 Windows 커서에 액세스 하는 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&47;](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]  
  
##  <a name="loadstandardicon"></a>CWinApp::LoadStandardIcon  
 미리 정의 된 아이콘 리소스는 Windows를 로드 하는 `lpszIconName` 지정 합니다.  
  
```  
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszIconName`  
 미리 정의 된 Windows 아이콘을 지정 하는 매니페스트 상수 식별자입니다. 이러한 식별자는 WINDOWS에서 정의 됩니다.&8;. 사용할 수 있는 미리 정의 된 값 및 해당 설명 목록을 참조는 *lpIconName* 매개 변수 [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 아이콘에 대 한 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 사용 된 `LoadStandardIcon` 또는 [LoadOEMIcon](#loadoemicon) 미리 정의 된 Windows 아이콘에 액세스 하는 멤버 함수입니다.  
  
##  <a name="loadstdprofilesettings"></a>CWinApp::LoadStdProfileSettings  
 이 멤버 함수 내에서 호출 된 [InitInstance](#initinstance) 멤버 함수를 사용 하도록 설정 하 고 가장 최근에 사용한 (MRU) 파일의 목록을 로드 하 고, 마지막 상태 미리 보기.  
  
```  
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```  
  
### <a name="parameters"></a>매개 변수  
 `nMaxMRU`  
 추적을 최근 사용한 파일의 수입니다.  
  
### <a name="remarks"></a>주의  
 경우 `nMaxMRU` 가 0 이므로 MRU 목록이 없는 유지 관리 됩니다.  
  
##  <a name="m_bhelpmode"></a>CWinApp::m_bHelpMode  
 **True 이면** 응용 프로그램 (일반적으로 사용 하 여 호출 SHIFT + F1); 도움말 컨텍스트 모드 이면 그렇지 않은 경우 **FALSE**합니다.  
  
```  
BOOL m_bHelpMode;  
```  
  
### <a name="remarks"></a>주의  
 도움말 컨텍스트 모드 커서 물음표 되며 사용자는 화면에 대 한 이동할 수 있습니다. 도움말 모드에 있을 때 특수 한 처리를 구현 하려는 경우이 플래그를 검사 합니다. `m_bHelpMode`형식의 공용 변수 **BOOL**합니다.  
  
##  <a name="m_dwrestartmanagersupportflags"></a>CWinApp::m_dwRestartManagerSupportFlags  
 다시 시작 관리자가 동작 하는 방식을 결정 하는 플래그입니다.  
  
```  
DWORD m_dwRestartManagerSupportFlags;  
```  
  
### <a name="remarks"></a>주의  
 다시 시작 관리자를 사용 하려면 설정 `m_dwRestartManagerSupportFlags` 원하는 동작을 합니다. 다음 표에서 사용할 수 있는 플래그를 표시 합니다.  
  
|||  
|-|-|  
|플래그|설명|  
|`AFX_RESTART_MANAGER_SUPPORT_RESTART`|사용 하 여 등록 되는 응용 프로그램 [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)합니다. 다시 시작 관리자는 예기치 않게 종료 되는 경우 응용 프로그램을 다시 시작 하는 일을 담당 합니다.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RECOVERY`|응용 프로그램은 다시 시작 관리자에 등록 하 고 다시 시작 관리자는 응용 프로그램을 다시 시작 될 때 복구 콜백 함수를 호출 합니다. 기본 복구 콜백 함수는 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)합니다.|  
|- `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`|자동 저장을 사용 하 고 다시 시작 관리자에서 응용 프로그램 다시 시작 될 때 모든 열린 문서입니다.|  
|- `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`|자동 저장을 사용 하 고 다시 시작 관리자에서 일정 한 간격으로 모든 열린 문서입니다. 간격 정의한 [CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)합니다.|  
|- `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`|다시 시작 관리자는 예기치 않은 종료에서 응용 프로그램을 다시 시작한 후 이전에 열려 있는 문서를 엽니다. [CDataRecoveryHandler 클래스](../../mfc/reference/cdatarecoveryhandler-class.md) 열려 있는 문서의 목록을 저장 하 고 복원 처리 합니다.|  
|- `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`|응용 프로그램을 다시 시작한 후 자동 저장 된 파일을 복원 하 라는 메시지를 표시 하는 다시 시작 관리자입니다. `CDataRecoveryHandler` 클래스는 사용자를 쿼리 합니다.|  
|- `AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE`|합집합 `AFX_RESTART_MANAGER_SUPPORT_RESTART`, `AFX_RESTART_MANAGER_SUPPORT_RECOVER`, 및 `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`합니다.|  
|- `AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS`|The union of `AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`, and `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS`|The union of `AFX_RESTART_MANAGER_SUPPORT_RESTART`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`, `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`, and `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS`|The union of `AFX_RESTART_MANAGER_SUPPORT_RECOVERY`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`, `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`, and `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
  
##  <a name="m_ehelptype"></a>CWinApp::m_eHelpType  
 이 데이터 멤버의 형식은 열거 형식 **AFX_HELP_TYPE**, 내에서 정의 되는 `CWinApp` 클래스입니다.  
  
```  
AFX_HELP_TYPE m_eHelpType;  
```  
  
### <a name="remarks"></a>주의  
 **AFX_HELP_TYPE** 열거형은 다음과 같이 정의 합니다.  
  
 `enum AFX_HELP_TYPE`  
  
 `{`  
  
 `afxWinHelp = 0,`  
  
 `afxHTMLHelp = 1`  
  
 `};`  
  
-   HTML 도움말에는 응용 프로그램의 도움말을 설정 하려면 호출 [SetHelpMode](#sethelpmode) 지정 **afxHTMLHelp**합니다.  
  
-   WinHelp 응용 프로그램의 도움말을 설정 하려면 호출 `SetHelpMode` 지정 **afxWinHelp**합니다.  
  
##  <a name="m_hinstance"></a>CWinApp::m_hInstance  
 에 해당 하는 `hInstance` 매개 변수를 Windows로 전달 `WinMain`합니다.  
  
```  
HINSTANCE m_hInstance;  
```  
  
### <a name="remarks"></a>주의  
 `m_hInstance` 데이터 멤버는 Windows에서 실행 되는 응용 프로그램의 현재 인스턴스에 대 한 핸들입니다. 전역 함수에 의해이 값이 반환 [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle)합니다. `m_hInstance`형식의 공용 변수 `HINSTANCE`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&55;](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]  
  
##  <a name="m_lpcmdline"></a>CWinApp::m_lpCmdLine  
 에 해당 하는 `lpCmdLine` 매개 변수를 Windows로 전달 `WinMain`합니다.  
  
```  
LPTSTR m_lpCmdLine;  
```  
  
### <a name="remarks"></a>주의  
 응용 프로그램에 대 한 명령줄을 지정 하는 null로 끝나는 문자열을 가리킵니다. 사용 하 여 `m_lpCmdLine` 사용자가 응용 프로그램이 시작 될 때 입력 한 모든 명령줄 인수에 액세스할 수 있습니다. `m_lpCmdLine`형식의 공용 변수 `LPTSTR`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&52;](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="m_nautosaveinterval"></a>CWinApp::m_nAutosaveInterval  
 시간 (밀리초) 간에 자동으로 저장 길이입니다.  
  
```  
int m_nAutosaveInterval;  
```  
  
### <a name="remarks"></a>주의  
 지정한 간격으로 자동 저장 열려 있는 문서를 다시 시작 관리자를 구성할 수 있습니다. 응용 프로그램에 자동 저장 파일 하지 않으면이 매개 변수는 영향을 주지 않습니다.  
  
##  <a name="m_ncmdshow"></a>CWinApp::m_nCmdShow  
 에 해당 하는 `nCmdShow` 매개 변수를 Windows로 전달 `WinMain`합니다.  
  
```  
int m_nCmdShow;  
```  
  
### <a name="remarks"></a>주의  
 전달 해야 `m_nCmdShow` 를 호출할 때 인수로 [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) 응용 프로그램의 주 창에 대 한 합니다. `m_nCmdShow`형식의 공용 변수 `int`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&56;](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]  
  
##  <a name="m_pactivewnd"></a>CWinApp::m_pActiveWnd  
 이 데이터 멤버를 사용 하 여 프로그램 OLE 서버 응용 프로그램 내부 활성화 된 OLE 컨테이너 응용 프로그램의 주 창에 대 한 포인터를 저장 합니다.  
  
### <a name="remarks"></a>주의  
 이 데이터 멤버는 경우 **NULL**, 응용 프로그램은에 내부 활성화 되지 않습니다.  
  
 프레임 워크는 프레임 창을 OLE 컨테이너 응용 프로그램에 의해 활성화 될 때이 멤버 변수를 설정 합니다.  
  
##  <a name="m_pdatarecoveryhandler"></a>CWinApp::m_pDataRecoveryHandler  
 응용 프로그램에 대 한 데이터 복구 처리기에 대 한 포인터입니다.  
  
```  
CDataRecoveryHandler* m_pDataRecoveryHandler;  
```  
  
### <a name="remarks"></a>주의  
 열려 있는 문서와 자동으로 저장을 모니터링 하는 응용 프로그램의 데이터 복구 처리기에 있습니다. 응용 프로그램이 예기치 않게 종료 후 다시 시작 될 때 자동 저장 된 파일을 복원 하는 데이터 복구 처리기를 사용 하는 프레임 워크입니다. 자세한 내용은 참조 [CDataRecoveryHandler 클래스](../../mfc/reference/cdatarecoveryhandler-class.md)합니다.  
  
##  <a name="m_pszappname"></a>CWinApp::m_pszAppName  
 응용 프로그램의 이름을 지정합니다.  
  
```  
LPCTSTR m_pszAppName;  
```  
  
### <a name="remarks"></a>주의  
 응용 프로그램 이름에 전달 된 매개 변수에서 가져올 수 있습니다는 [CWinApp](#cwinapp) 생성자를 지정 하지 않으면 리소스 문자열의 ID와 또는 **AFX_IDS_APP_TITLE**합니다. 리소스에서 응용 프로그램 이름이 없으면 프로그램의에서 제공 됩니다. EXE 파일 이름입니다.  
  
 전역 함수에서 반환 된 [AfxGetAppName](application-information-and-management.md#afxgetappname)합니다. `m_pszAppName`형식의 공용 변수 **const char\***합니다.  
  
> [!NOTE]
>  값을 할당 하는 경우 `m_pszAppName`, 힙에 동적으로 할당 해야 합니다. `CWinApp` 소멸자 호출 **무료**이 포인터와 함께 (). 사용 하려면 많은 `_tcsdup`() 런타임 라이브러리 함수는 할당 작업을 수행 하 합니다. 또한 새 값을 할당 하기 전에 현재 포인터와 연결 된 메모리를 해제 합니다. 예:  
  
 [!code-cpp[NVC_MFCWindowing #&57;](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&65;](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]  
  
##  <a name="m_pszexename"></a>CWinApp::m_pszExeName  
 확장명 없이 응용 프로그램의 실행 파일의 이름을 포함합니다.  
  
```  
LPCTSTR m_pszExeName;  
```  
  
### <a name="remarks"></a>주의  
 와 달리 [m_pszAppName](#m_pszappname),이 이름은 공백을 포함할 수 없습니다. `m_pszExeName`형식의 공용 변수 **const char\***합니다.  
  
> [!NOTE]
>  값을 할당 하는 경우 `m_pszExeName`, 힙에 동적으로 할당 해야 합니다. `CWinApp` 소멸자 호출 **무료**이 포인터와 함께 (). 사용 하려면 많은 `_tcsdup`() 런타임 라이브러리 함수는 할당 작업을 수행 하 합니다. 또한 새 값을 할당 하기 전에 현재 포인터와 연결 된 메모리를 해제 합니다. 예:  
  
 [!code-cpp[NVC_MFCWindowing #&58;](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]  
  
##  <a name="m_pszhelpfilepath"></a>CWinApp::m_pszHelpFilePath  
 응용 프로그램의 도움말 파일의 경로를 포함합니다.  
  
```  
LPCTSTR m_pszHelpFilePath;  
```  
  
### <a name="remarks"></a>주의  
 기본적으로 프레임 워크를 초기화 `m_pszHelpFilePath` 응용 프로그램의 이름에 ". HLP "추가 됩니다. 도움말 파일의 이름을 변경 하려면 설정 `m_pszHelpFilePath` 원하는 도움말 파일의 전체 이름을 포함 하는 문자열을 가리키도록 합니다. 이 작업을 수행 하는 데 편리한 위치는 응용 프로그램의 [InitInstance](#initinstance) 함수입니다. `m_pszHelpFilePath`형식의 공용 변수 **const char\***합니다.  
  
> [!NOTE]
>  값을 할당 하는 경우 `m_pszHelpFilePath`, 힙에 동적으로 할당 해야 합니다. `CWinApp` 소멸자 호출 **무료**이 포인터와 함께 (). 사용 하려면 많은 `_tcsdup`() 런타임 라이브러리 함수는 할당 작업을 수행 하 합니다. 또한 새 값을 할당 하기 전에 현재 포인터와 연결 된 메모리를 해제 합니다. 예:  
  
 [!code-cpp[NVC_MFCWindowing #&59;](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]  
  
##  <a name="m_pszprofilename"></a>CWinApp::m_pszProfileName  
 응용 프로그램의 이름을 포함합니다. INI 파일입니다.  
  
```  
LPCTSTR m_pszProfileName;  
```  
  
### <a name="remarks"></a>주의  
 `m_pszProfileName`형식의 공용 변수 **const char\***합니다.  
  
> [!NOTE]
>  값을 할당 하는 경우 `m_pszProfileName`, 힙에 동적으로 할당 해야 합니다. `CWinApp` 소멸자 호출 **무료**이 포인터와 함께 (). 사용 하려면 많은 `_tcsdup`() 런타임 라이브러리 함수는 할당 작업을 수행 하 합니다. 또한 새 값을 할당 하기 전에 현재 포인터와 연결 된 메모리를 해제 합니다. 예:  
  
 [!code-cpp[NVC_MFCWindowing #&60;](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]  
  
##  <a name="m_pszregistrykey"></a>CWinApp::m_pszRegistryKey  
 사용, 레지스트리 또는 INI 파일에서 응용 프로그램 프로필 설정이 저장 되는 위치를 결정 합니다.  
  
```  
LPCTSTR m_pszRegistryKey;  
```  
  
### <a name="remarks"></a>주의  
 일반적으로이 데이터 멤버는 읽기 전용으로 처리 됩니다.  
  
-   값은 레지스트리 키에 저장 됩니다. 응용 프로그램 프로필 설정에 대 한 이름이 다음 레지스트리 키에 추가 됩니다: HKEY_CURRENT_USER/소프트웨어/LocalAppWizard 생성 /.  
  
 값을 할당 하는 경우 `m_pszRegistryKey`, 힙에 동적으로 할당 해야 합니다. `CWinApp` 소멸자 호출 **무료**이 포인터와 함께 (). 사용 하려면 많은 `_tcsdup`() 런타임 라이브러리 함수는 할당 작업을 수행 하 합니다. 또한 새 값을 할당 하기 전에 현재 포인터와 연결 된 메모리를 해제 합니다. 예:  
  
 [!code-cpp[NVC_MFCWindowing #&61;](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]  
  
##  <a name="m_pszappid"></a>CWinApp::m_pszAppID  
 응용 프로그램 사용자 모델 id입니다.  
  
```  
LPCTSTR m_pszAppID;  
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="oncontexthelp"></a>CWinApp::OnContextHelp  
 응용 프로그램 내에서 SHIFT + F1 도움말을 처리합니다.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>주의  
 추가 해야는 `ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )` 문을 여 `CWinApp` 메시지 맵을 클래스 및 일반적으로 SHIFT + f&1;을이 멤버 함수를 사용 하도록 설정 하는 액셀러레이터 키 테이블 항목을 추가할 수도 있습니다.  
  
 `OnContextHelp`응용 프로그램을 도움말 모드로 전환합니다. 그런 다음 화살표 및 매개 변수 및 사용자 커서 변경 사항 마우스 포인터를 이동 하 고 대화 상자, 창, 메뉴 또는 명령 단추를 선택 하 고 마우스 왼쪽된 단추 수 있습니다. 이 멤버 함수는 커서 아래에 있는 개체의 도움말 컨텍스트를 검색 하 고 해당 도움말 컨텍스트와 WinHelp Windows 함수를 호출 합니다.  
  
##  <a name="onddecommand"></a>CWinApp::OnDDECommand  
 주 프레임 창 DDE를 받을 때 프레임 워크에서 호출 메시지를 실행 합니다.  
  
```  
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszCommand*  
 응용 프로그램에서 받은 DDE 명령 문자열을 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 명령이 처리 되는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 인지 확인 명령은 문서를 요청, 그럴 경우 지정 된 문서를 엽니다. 일반적으로 Windows 파일 관리자는 데이터 파일을 두 번 클릭할 때 이러한 DDE 명령 문자열을 보냅니다. 재정의 다른 DDE 처리 하려면이 함수를 인쇄 하는 명령 같은 명령을 실행 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&48;](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]  
  
##  <a name="onfilenew"></a>CWinApp::OnFileNew  
 구현 하는 `ID_FILE_NEW` 명령입니다.  
  
```  
afx_msg void OnFileNew();
```  
  
### <a name="remarks"></a>주의  
 추가 해야는 `ON_COMMAND( ID_FILE_NEW, OnFileNew )` 문을 여 `CWinApp` 이 멤버 함수를 사용 하도록 설정 하는 클래스 메시지 맵. 설정 된 경우이 함수는 새 파일 명령 실행을 처리 합니다.  
  
 참조 [Technical Note 22](../../mfc/tn022-standard-commands-implementation.md) 기본 동작에 대 한 지침은이 멤버 함수를 재정의 하는 방법에 대 한 내용은 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&49;](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing #&50;](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onfileopen"></a>CWinApp::OnFileOpen  
 구현 하는 `ID_FILE_OPEN` 명령입니다.  
  
```  
afx_msg void OnFileOpen();
```  
  
### <a name="remarks"></a>주의  
 추가 해야는 `ON_COMMAND( ID_FILE_OPEN, OnFileOpen )` 문을 여 `CWinApp` 이 멤버 함수를 사용 하도록 설정 하는 클래스 메시지 맵. 설정 된 경우이 함수는 파일 열기 명령 실행을 처리 합니다.  
  
 기본 동작에 대 한 정보 및이 멤버 함수를 재정의 하는 방법에 대 한 지침에 대 한 참조 [Technical Note 22](../../mfc/tn022-standard-commands-implementation.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&49;](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing #&50;](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onfileprintsetup"></a>CWinApp::OnFilePrintSetup  
 구현 하는 **ID_FILE_PRINT_SETUP** 명령입니다.  
  
```  
afx_msg void OnFilePrintSetup();
```  
  
### <a name="remarks"></a>주의  
 추가 해야는 `ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )` 문을 여 `CWinApp` 이 멤버 함수를 사용 하도록 설정 하는 클래스 메시지 맵. 설정 된 경우이 함수는 파일 인쇄 명령 실행을 처리 합니다.  
  
 기본 동작에 대 한 정보 및이 멤버 함수를 재정의 하는 방법에 대 한 지침에 대 한 참조 [Technical Note 22](../../mfc/tn022-standard-commands-implementation.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&49;](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing #&50;](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onhelp"></a>CWinApp::OnHelp  
 현재 컨텍스트를 사용하여 응용 프로그램 내에서 F1 도움말을 처리합니다.  
  
```  
afx_msg void OnHelp();
```  
  
### <a name="remarks"></a>주의  
 일반적으로 F1 키에 대 한 바로 가기 키 항목 또한 추가 합니다. 요구 사항이 아니라 규칙만은 F1 키를 사용 하도록 설정 합니다.  
  
 추가 해야는 `ON_COMMAND( ID_HELP, OnHelp )` 문을 여 `CWinApp` 이 멤버 함수를 사용 하도록 설정 하는 클래스 메시지 맵. F1 키를 누를 때 프레임 워크에 의해 설정 된 경우 호출 합니다.  
  
 이 메시지-처리기 함수의 기본 구현은 현재 창, 대화 상자 또는 메뉴 항목에 해당 하며 다음 WINHELP를 호출 하는 도움말 컨텍스트를 결정 합니다. EXE 수 있습니다. 현재 사용할 수 있는 컨텍스트가 없는 경우 함수는 기본 컨텍스트를 사용 합니다.  
  
 창, 대화 상자, 메뉴 항목 또는 현재 포커스가 있는 도구 모음 단추 이외의 값으로 도움말 컨텍스트를 설정 하려면이 멤버 함수를 재정의 합니다. 호출 `WinHelp` 원하는 도움말 컨텍스트 id입니다.  
  
##  <a name="onhelpfinder"></a>CWinApp::OnHelpFinder  
 처리는 **ID_HELP_FINDER** 및 **ID_DEFAULT_HELP** 명령입니다.  
  
```  
afx_msg void OnHelpFinder();
```  
  
### <a name="remarks"></a>주의  
 추가 해야는 `ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )` 문을 여 `CWinApp` 이 멤버 함수를 사용 하도록 설정 하는 클래스 메시지 맵. 응용 프로그램의 사용자가 호출할 Finder 도움말 명령을 선택할 때 프레임 워크가 메시지 처리기 함수를 호출을 사용 하는 경우 `WinHelp` 표준 **HELP_FINDER** 항목입니다.  
  
##  <a name="onhelpindex"></a>CWinApp::OnHelpIndex  
 처리는 **ID_HELP_INDEX** 명령 하 고 기본 도움말 항목을 제공 합니다.  
  
```  
afx_msg void OnHelpIndex();
```  
  
### <a name="remarks"></a>주의  
 추가 해야는 `ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )` 문을 여 `CWinApp` 이 멤버 함수를 사용 하도록 설정 하는 클래스 메시지 맵. 응용 프로그램의 사용자가 호출할 도움말 색인 명령을 선택할 때 프레임 워크가 메시지 처리기 함수를 호출을 사용 하는 경우 `WinHelp` 표준 **HELP_INDEX** 항목입니다.  
  
##  <a name="onhelpusing"></a>CWinApp::OnHelpUsing  
 처리는 **ID_HELP_USING** 명령입니다.  
  
```  
afx_msg void OnHelpUsing();
```  
  
### <a name="remarks"></a>주의  
 추가 해야는 `ON_COMMAND( ID_HELP_USING, OnHelpUsing )` 문을 여 `CWinApp` 이 멤버 함수를 사용 하도록 설정 하는 클래스 메시지 맵. 응용 프로그램의 호출을 사용 하 여 도움말 명령을 선택 하면 프레임 워크에이 메시지 처리기 함수 호출의 `WinHelp` 표준 응용 프로그램 **HELP_HELPONHELP** 항목입니다.  
  
##  <a name="onidle"></a>CWinApp::OnIdle  
 유휴 시간 처리를 수행 하려면이 멤버 함수를 재정의 합니다.  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>매개 변수  
 `lCount`  
 카운터 될 때마다 증가 `OnIdle` 응용 프로그램의 메시지 큐가 비어 있을 경우 호출 됩니다. 이 횟수가 새 메시지가 처리 될 때마다 0으로 재설정 됩니다. 사용할 수는 `lCount` 매개 변수에 지정 된 상대적 기간 동안 메시지를 처리 하지 않고 응용 프로그램이 유휴 상태 였습니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아니면 받을 더 유휴 처리 시간입니다. 유휴 시간을 더 이상 필요한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 `OnIdle`응용 프로그램의 메시지 큐가 비어 있을 경우 기본 메시지 루프에서 호출 됩니다. 재정의 사용 하 여 사용자 고유의 배경 유휴 처리기 작업을 호출.  
  
 `OnIdle`유휴 처리 시간이 필요한 임을 나타내려면 0을 반환 해야 합니다. `lCount` 매개 변수는 각 시간 증가 `OnIdle` 메시지 큐가 비어 있고 새 메시지가 처리 될 때마다 0으로 다시 설정 될 때 호출 됩니다. 이 수를 기반으로 하 여 다른 유휴 루틴을 호출할 수 있습니다.  
  
 유휴 루프 처리를 요약는 다음과 같습니다.  
  
1.  Microsoft Foundation 클래스 라이브러리에서 메시지 루프는 메시지 큐를 검사 하 고 더 보류 중인 메시지를 찾을 경우 호출 `OnIdle` 응용 프로그램 개체 및 0으로 공급 장치에는 `lCount` 인수입니다.  
  
2. `OnIdle`일부 처리를 수행 하 고 작업을 수행 하는&0;이 아닌 값을 나타내기 위해 다시 호출 해야 반환 추가 처리 합니다.  
  
3.  메시지 루프를 메시지 큐를 다시 확인합니다. 보류 중인 메시지가 없는 경우 호출 `OnIdle` 다시 증가 하는 `lCount` 인수입니다.  
  
4.  결국 `OnIdle` 모든 유휴 작업 처리를 완료 하 고 0을 반환 합니다. 이 코드 호출을 중지 하는 메시지 루프를 통해 `OnIdle` 다음 메시지를 메시지 큐에서 받을 때까지 지점도 유휴 주기를 다시 시작 인수를 0으로 설정 합니다.  
  
 중에 시간이 오래 걸리는 작업을 수행 하지 마십시오 `OnIdle` 응용 프로그램에서 사용자 입력 될 때까지 처리할 수 없습니다 때문에 `OnIdle` 반환 합니다.  
  
> [!NOTE]
>  기본 구현은 `OnIdle` 업데이트 명령 메뉴 항목 및 도구 모음 단추와 같은 사용자 인터페이스 개체 및 내부 데이터 구조 정리를 수행 합니다. 따라서 재정의 하는 경우 `OnIdle`를 호출 해야 `CWinApp::OnIdle` 와 `lCount` 재정의 된 버전에서. 먼저 모든 기본 클래스 유휴 프로세스를 호출 (즉, 기본 클래스까지 `OnIdle` 0을 반환). 기본 클래스 처리가 완료 되기 전에 작업을 수행 해야 하는 경우 적절 한 선택 하는 기본 클래스 구현을 검토 `lCount` 작업을 수행 하는 중입니다.  
  
 원하지 않는 경우 `OnIdle` 메시지 큐에서 메시지를 가져올 때마다 호출을 재정의할 수는 [CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage)합니다. 응용 프로그램에 매우 짧은 타이머를 설정 하는 경우 또는 시스템에서 보내는 경우는 **WM_SYSTIMER** 메시지, 다음 `OnIdle` 이 반복적으로 호출 되 고 성능이 저하 될 합니다.  
  
### <a name="example"></a>예제  
 다음 두 가지 예에 사용 하는 방법을 보여 줍니다 `OnIdle`합니다. 사용 하 여 두 개의 유휴 작업을 처리 하는 첫 번째 예제는 `lCount` 인수 작업 우선 순위를 지정 합니다. 첫 번째 작업은 매우 중요 하 고 가능한 경우 항상 수행 해야 합니다. 두 번째 작업은 그다지 중요 하 고 사용자 입력에 있는 오래 지연 된 경우에 수행 해야 합니다. 호출의 기본 클래스 버전을 `OnIdle`합니다. 두 번째 예제에서는 우선 순위가 서로 다른 유휴 작업 그룹을 관리합니다.  
  
 [!code-cpp[NVC_MFCWindowing #&51;](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]  
  
##  <a name="opendocumentfile"></a>CWinApp::OpenDocumentFile  
 명명 된 열에이 메서드를 호출 하는 프레임 워크 [CDocument](../../mfc/reference/cdocument-class.md) 응용 프로그램에 대 한 파일입니다.  
  
```  
virtual CDocument* OpenDocumentFile(
LPCTSTR lpszFileName  
BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszFileName`  
 열 파일의 이름입니다.  
  
 [in] `bAddToMRU`  
 `TRUE`문서는 가장 최근의 파일 중 하나를 나타냅니다. `FALSE` 문서가 아닌 가장 최근에 사용한 파일 중 하나를 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CDocument` 성공 하 고 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 해당 이름의 문서 이미 열려 있으면 해당 문서를 포함 하는 첫 번째 프레임 창 포커스를 받습니다. 응용 프로그램에서 여러 문서 서식 파일을 지 원하는 경우 프레임 워크 파일 이름 확장명을 사용 하 여 문서를 로드 하려고 하는 적절 한 문서 서식 파일을 찾습니다. 성공 하면 프레임 창 및 문서에 대 한 보기가 다음 문서 서식 파일에 만듭니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&52;](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="parsecommandline"></a>CWinApp::ParseCommandLine  
 이 멤버 함수를 명령줄 구문 분석 하 고 매개 변수를 한 번에 하나씩 보낼 호출 [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam)합니다.  
  
```  
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `rCmdInfo`  
 에 대 한 참조는 [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 응용 프로그램 마법사의 로컬 인스턴스를 만듭니다 응용 프로그램 마법사를 사용 하 여 새 MFC 프로젝트를 시작 하면 `CCommandLineInfo`, 다음 호출 `ProcessShellCommand` 및 `ParseCommandLine` 에 [InitInstance](#initinstance) 멤버 함수입니다. 명령줄을 사용 하는 아래에 설명 된 경로 따릅니다.  
  
1.  생성 되 고 후 `InitInstance`, `CCommandLineInfo` 개체는 전달 `ParseCommandLine`합니다.  
  
2. `ParseCommandLine`그런 다음 호출 `CCommandLineInfo::ParseParam` 반복 해 서, 각 매개 변수에 대해 한 번씩 합니다.  
  
3. `ParseParam`채우기는 `CCommandLineInfo` 개체에 전달 되는 [ProcessShellCommand](#processshellcommand)합니다.  
  
4. `ProcessShellCommand`명령줄 인수 및 플래그를 처리합니다.  
  
 호출할 수 있는 참고 `ParseCommandLine` 필요에 따라 직접.  
  
 명령줄 플래그에 대 한 참조 [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)합니다.  
  
##  <a name="pretranslatemessage"></a>경우  
 Windows 함수에 디스패치 되기 전에 필터 창 메시지에이 함수를 재정의 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) 기본 구현에서는 호출 해야 하므로 액셀러레이터 키 변환 수행에서 `CWinApp::PreTranslateMessage` 재정의 된 버전에 있는 멤버 함수입니다.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>매개 변수  
 `pMsg`  
 에 대 한 포인터는 [MSG](../../mfc/reference/msg-structure1.md) 처리할 메시지를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 메시지에서 완전히 처리 된 경우&0;이 아닌 `PreTranslateMessage` 하며 추가로 처리할 수 없습니다. 일반적인 방법으로 메시지를 처리 해야 하면&0;입니다.  
  
##  <a name="processmessagefilter"></a>CWinApp::ProcessMessageFilter  
 프레임 워크의 후크 함수는 필터링 하 고 특정 Windows 메시지에 응답 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>매개 변수  
 `code`  
 후크 코드가 지정합니다. 이 멤버 함수는 코드를 사용 하 여 처리 하는 방법을 확인 하려면`lpMsg.`  
  
 `lpMsg`  
 Windows에 대 한 포인터 [MSG](../../mfc/reference/msg-structure1.md) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 메시지를 처리 합니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 응용 프로그램의 일반 메시지를 보내기 전에 이벤트를 처리 하는 후크 함수를 처리 합니다.  
  
 이 고급 기능을 재정의 하는 경우 사용할 프레임 워크의 유지 관리 하는 기본 클래스 버전을 호출 해야 처리를 연결 합니다.  
  
##  <a name="processshellcommand"></a>CWinApp::ProcessShellCommand  
 이 멤버 함수를 호출 하 [InitInstance](#initinstance) 에서 전달 된 매개 변수를 허용 하는 `CCommandLineInfo` 로 식별 된 개체 `rCmdInfo`, 표시 된 작업을 수행 합니다.  
  
```  
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `rCmdInfo`  
 에 대 한 참조는 [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 셸 명령을 성공적으로 처리 하는 경우에&0;이 아닌 합니다. 0 인 경우, 반환 **FALSE** 에서 [InitInstance](#initinstance)합니다.  
  
### <a name="remarks"></a>주의  
 응용 프로그램 마법사의 로컬 인스턴스를 만듭니다 응용 프로그램 마법사를 사용 하 여 새 MFC 프로젝트를 시작 하면 `CCommandLineInfo`, 다음 호출 `ProcessShellCommand` 및 [ParseCommandLine](#parsecommandline) 에 `InitInstance` 멤버 함수입니다. 명령줄을 사용 하는 아래에 설명 된 경로 따릅니다.  
  
1.  생성 되 고 후 `InitInstance`, `CCommandLineInfo` 개체는 전달 `ParseCommandLine`합니다.  
  
2. `ParseCommandLine`그런 다음 호출 [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam) 반복 해 서, 각 매개 변수에 대해 한 번씩 합니다.  
  
3. `ParseParam`채우기는 `CCommandLineInfo` 개체에 전달 되는 `ProcessShellCommand`합니다.  
  
4. `ProcessShellCommand`명령줄 인수 및 플래그를 처리합니다.  
  
 데이터 멤버는 `CCommandLineInfo` 로 식별 된 개체 [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand), 내에 정의 된 다음 열거 유형을 가지는 `CCommandLineInfo` 클래스입니다.  
  
 `enum {`  
  
 `FileNew,`  
  
 `FileOpen,`  
  
 `FilePrint,`  
  
 `FilePrintTo,`  
  
 `FileDDE,`  
  
 `};`  
  
 이러한 각 값의 간략 한 설명을 참조 하십시오. `CCommandLineInfo::m_nShellCommand`합니다.  
  
##  <a name="processwndprocexception"></a>CWinApp::ProcessWndProcException  
 처리기는 응용 프로그램의 메시지 또는 명령 처리기 중 하나에서 throw 된 예외를 catch 하지 않습니다 될 때마다이 멤버 함수를 호출 하는 프레임 워크입니다.  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>매개 변수  
 *e*  
 확인할 수 없는 예외에 대 한 포인터입니다.  
  
 `pMsg`  
 A [MSG](../../mfc/reference/msg-structure1.md) 프레임 워크에 예외를 발생 시킨 windows 메시지에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 Windows로 반환 되는 값입니다. Windows 메시지를 1 L 0 L이는 일반적으로 ( **TRUE**) 명령 메시지에 대 한 합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수를 직접 호출 하지 마십시오.  
  
 이 멤버 함수의 기본 구현은 메시지 상자를 만듭니다. 확인할 수 없는 예외 시작 메뉴, 도구 모음 또는 엑셀 러 레이 터 명령 실패, 메시지 상자를 표시 "명령이 실패 했습니다."; 그렇지 않으면 "내부 응용 프로그램 오류" 메시지가 표시 됩니다.  
  
 글로벌 사용자 예외 처리를 제공 하려면이 멤버 함수를 재정의 합니다. 메시지 상자를 표시 하려는 경우에 기본 기능을 호출 합니다.  
  
##  <a name="register"></a>CWinApp::Register  
 처리 되지 않는 모든 등록 작업을 수행 `RegisterShellFileTypes`합니다.  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아닌 값이고, 실패하면 0입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 단순히 TRUE를 반환합니다. 모든 사용자 지정 된 등록 단계를 제공 하려면이 함수를 재정의 합니다.  
  
##  <a name="registershellfiletypes"></a>CWinApp::RegisterShellFileTypes  
 모든 응용 프로그램의 문서 유형에 Windows 파일 관리자에 등록 하려면이 멤버 함수를 호출 합니다.  
  
```  
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bCompat`  
 `TRUE`인쇄 및 인쇄에, 사용자가 파일을 인쇄 하려면 셸에서 직접 또는 프린터 개체에는 파일을 끌어 셸 명령에 대 한 등록 항목을 추가 합니다. 또한 DefaultIcon 키를 추가합니다. 이 매개 변수는 기본적으로 `FALSE` 이전 버전과 호환성에 대 한 합니다.  
  
### <a name="remarks"></a>주의  
 이 파일 관리자 내에서 두 번 클릭 하 여 응용 프로그램에서 만든 데이터 파일을 열 수 있습니다. 호출 `RegisterShellFileTypes` 호출한 후 [AddDocTemplate](#adddoctemplate) 각 응용 프로그램에서 문서 서식 파일에 대 한 합니다. 또한 호출의 [EnableShellOpen](#enableshellopen) 멤버 함수를 호출할 때 `RegisterShellFileTypes`합니다.  
  
 `RegisterShellFileTypes`목록에서 반복 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 개체는 응용 프로그램 유지 관리 하 고, 각 문서 서식 파일에 대 한 Windows에서 파일 연결에 대 한 유지 관리 하는 등록 데이터베이스에 항목을 추가 합니다. 파일 관리자 이러한 항목을 사용 하 여 사용자가 데이터 파일을 엽니다. 이렇게 하지 않아도 배송을 합니다. 응용 프로그램과 함께 REG 파일입니다.  
  
> [!NOTE]
> `RegisterShellFileTypes`사용자가 관리자 권한으로 프로그램을 실행 하는 경우에 작동 합니다. 프로그램에 대 한 관리자 권한이 없는 경우에 레지스트리 키를 변경해 수 없습니다.  
  
 등록 데이터베이스는 이미 다른 파일 형식으로 지정 된 파일 이름 확장명을 연결 하면 없는 새 연결이 만들어집니다. 참조는 `CDocTemplate` 이 정보를 등록 하는 데 필요한 문자열의 형식에 대 한 클래스입니다.  
  
##  <a name="registerwithrestartmanager"></a>CWinApp::RegisterWithRestartManager  
 다시 시작 관리자를 응용 프로그램을 등록합니다.  
  
```  
virtual HRESULT RegisterWithRestartManager(
BOOL bRegisterRecoveryCallback,  
const CString& strRestartIdentifier);

 
virtual HRESULT RegisterWithRestartManager(
LPCWSTR pwzCommandLineArgs,  
DWORD dwRestartFlags,  
APPLICATION_RECOVERY_CALLBACK pRecoveryCallback,  
LPVOID lpvParam,  
DWORD dwPingInterval,  
DWORD dwCallbackFlags);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `bRegisterRecoveryCallback`|`TRUE`응용 프로그램의이 인스턴스는 복구 콜백 함수를 사용 함을 나타냅니다. `FALSE` 되지 않은 것을 나타냅니다. 응용 프로그램이 예기치 않게 종료 될 때 복구 콜백 함수를 호출 하는 프레임 워크입니다. 자세한 내용은 참조 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)합니다.|  
|[in] `strRestartIdentifier`|다시 시작 관리자의이 인스턴스를 식별 하는 고유 문자열입니다. 다시 시작 관리자 식별자는 응용 프로그램의 각 인스턴스에 대해 고유 합니다.|  
|[in] `pwzCommandLineArgs`|명령줄에서 추가 인수를 포함 하는 문자열입니다.|  
|[in] `dwRestartFlags`|다시 시작 관리자에 대 한 선택적 플래그입니다. 자세한 내용은 설명 섹션을 참조하세요.|  
|[in] `pRecoveryCallback`|복구 콜백 함수입니다. 이 함수를 사용 해야는 `LPVOID` 입력 및 반환 매개 변수는 `DWORD`합니다. 기본 복구 콜백 함수는 `CWinApp::ApplicationRecoveryCallback`합니다.|  
|[in] `lpvParam`|복구 콜백 함수에 대 한 입력된 매개 변수입니다. 자세한 내용은 참조 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)합니다.|  
|[in] `dwPingInterval`|길이 반환 하는 복구 콜백 함수에 대 한 다시 시작 관리자를 대기 하는 시간입니다. 이 매개 변수는 밀리초에서입니다.|  
|[in] `dwCallbackFlags`|플래그는 복구 콜백 함수에 전달 합니다. 나중에 사용하기 위해 예약되어 있습니다.|  
  
### <a name="return-value"></a>반환 값  
 `S_OK`메서드가 성공 하면 그렇지 않으면 오류 코드가 있습니다.  
  
### <a name="remarks"></a>주의  
 간단한 버전의를 사용 해야 하는 경우 자동 저장 파일에 대 한 기본 MFC 구현을 사용 하는 응용 프로그램을 `RegisterWithRestartManager`합니다. 복잡 한 버전을 사용 하 여 `RegisterWithRestartManager` 응용 프로그램의 자동 저장 동작을 사용자 지정 하려는 경우.  
  
 빈 문자열을이 메서드를 호출 하는 경우 `strRestartIdentifier`, `RegisterWithRestartManager` 관리자 다시 시작이이 인스턴스에 대 한 고유 식별자 문자열을 만듭니다.  
  
 응용 프로그램이 예기치 않게 종료 되 면 다시 시작 관리자는 명령줄에서 응용 프로그램을 다시 시작 하 고 고유 식별자는 선택적 인수를 다시 시작을 제공 합니다. 이 시나리오에서는 프레임 워크 호출 `RegisterWithRestartManager` 두 배입니다. 첫 번째 호출에서 가져온 [CWinApp::InitInstance](#initinstance) 문자열 식별자에 대 한 빈 문자열을 사용 합니다. 그런 다음 메서드 [CWinApp::ProcessShellCommand](#processshellcommand) 호출 `RegisterWithRestartManager` 다시 시작 고유 식별자를 사용 합니다.  
  
 응용 프로그램에 다시 시작 관리자를 등록 한 후 다시 시작 관리자는 응용 프로그램을 모니터링 합니다. 응용 프로그램이 예기치 않게 종료 되 면 다시 시작 관리자 종료 프로세스 중 복구 콜백 함수를 호출 합니다. 다시 시작 관리자 대기는 `dwPingInterval` 복구 콜백 함수에서 응답 합니다. 이 시간 내에 복구 콜백 함수가 응답 하지 않을 경우 응용 프로그램 복구 콜백 함수를 실행 하지 않고 종료 됩니다.  
  
 기본적으로는 dwRestartFlags는 지원 되지 않지만 나중을 위해 제공 됩니다. 가능한 값은 `dwRestartFlags` 는 다음과 같습니다.  
  
- `RESTART_NO_CRASH`  
  
- `RESTART_NO_HANG`  
  
- `RESTART_NO_PATCH`  
  
- `RESTART_NO_REBOOT`  
  
##  <a name="reopenpreviousfilesatrestart"></a>CWinApp::ReopenPreviousFilesAtRestart  
 다시 시작 관리자 응용 프로그램이 예기치 않게 종료 될 때 열려 있던 파일이 닫았다가 다시 열거나 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL ReopenPreviousFilesAtRestart() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`다시 시작 관리자 다시 열립니다; 이전에 열려 있는 파일을 나타냅니다. `FALSE` 없는 다시 시작 관리자를 나타냅니다.  
  
##  <a name="restartinstance"></a>CWinApp::RestartInstance  
 다시 시작 관리자에 의해 시작 되는 응용 프로그램 다시 시작을 처리 합니다.  
  
```  
virtual BOOL CWinApp::RestartInstance();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`데이터 복구 처리기는 경우 이전에 열려 있는 문서입니다. `FALSE` 데이터 복구 처리기에 오류가 발생 하는 경우 또는 이전에 열린 문서가 없는 경우.  
  
### <a name="remarks"></a>주의  
 다시 시작 관리자는 응용 프로그램을 다시 시작할 때 프레임 워크는이 메서드를 호출 합니다. 이 메서드는 데이터 복구 처리기를 검색 하 고 자동 저장 된 파일을 복원 합니다. 이 메서드는 호출 [CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments) 자동 저장 된 파일을 복원 하는 사용자가 있는지 여부를 확인 하려면.  
  
 이 메서드가 반환 `FALSE` 경우는 [CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md) 이 열려 있는 문서를 결정 합니다. 열려 있는 문서가 있는 경우 응용 프로그램이 일반적으로 시작 합니다.  
  
##  <a name="restoreautosavedfilesatrestart"></a>CWinApp::RestoreAutosavedFilesAtRestart  
 응용 프로그램을 다시 시작 될 때 다시 시작 관리자 자동 저장 된 파일을 복원할지 여부를 결정 합니다.  
  
```  
virtual BOOL RestoreAutosavedFilesAtRestart() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`다시 시작 관리자 복원 자동 저장 된 파일; 나타냅니다. `FALSE` 없는 다시 시작 관리자를 나타냅니다.  
  
##  <a name="run"></a>Cwinapp:: Run  
 기본 메시지 루프를 제공합니다.  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>반환 값  
 `int` 에서 반환 되는 값 `WinMain`합니다.  
  
### <a name="remarks"></a>주의  
 **실행** 획득 및 응용 프로그램을 받을 때까지 Windows 메시지를 디스패치는 **WM_QUIT** 메시지입니다. 응용 프로그램의 메시지 큐에 현재 없는 메시지를 포함 하는 경우 **실행** 호출 [OnIdle](#onidle) 유휴 시간 처리를 수행 합니다. 들어오는 메시지 이동는 [PreTranslateMessage](#pretranslatemessage) 특수 한 처리 한 후 Windows 함수에 멤버 함수 **TranslateMessage** 표준 키보드 번역;에 대 한 마지막으로 **DispatchMessage** Windows 함수를 호출 합니다.  
  
 **실행** 대부분 재정의 하지만 특별 한 동작을 제공 하도록 재정의할 수 있습니다.  
  
##  <a name="runautomated"></a>CWinApp::RunAutomated  
 확인 하려면이 함수를 호출 여부는 " **/Automation**"또는" **-자동화**" 옵션은, 클라이언트 응용 프로그램이 서버 응용 프로그램이 시작 하는지 여부를 나타냅니다.  
  
```  
BOOL RunAutomated();
```  
  
### <a name="return-value"></a>반환 값  
 옵션을 찾은 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 있는 경우 옵션은 명령줄에서 제거 됩니다. OLE 자동화에 대 한 자세한 내용은 문서를 참조 하십시오. [자동화 서버](../../mfc/automation-servers.md)합니다.  
  
##  <a name="runembedded"></a>CWinApp::RunEmbedded  
 확인 하려면이 함수를 호출 여부는 " **포함/**"또는" **-포함**" 옵션은, 클라이언트 응용 프로그램이 서버 응용 프로그램이 시작 하는지 여부를 나타냅니다.  
  
```  
BOOL RunEmbedded();
```  
  
### <a name="return-value"></a>반환 값  
 옵션을 찾은 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 있는 경우 옵션은 명령줄에서 제거 됩니다. 포함에 대 한 자세한 내용은 문서를 참조 하십시오. [서버: 서버 구현](../../mfc/servers-implementing-a-server.md)합니다.  
  
##  <a name="saveallmodified"></a>CWinApp::SaveAllModified  
 프레임 워크에서 호출을 통해 또는 응용 프로그램의 주 프레임 창 닫아야 할 때 모든 문서 저장 한 `WM_QUERYENDSESSION` 메시지입니다.  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>반환 값  
 안전한 응용 프로그램을 종료 하면 0이 아니고 응용 프로그램을 종료 하는 안전 하지 않은 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수의 기본 구현에서는 호출 하는 [CDocument::SaveModified](../../mfc/reference/cdocument-class.md#savemodified) 다시 응용 프로그램 내의 모든 수정 된 문서에 대 한 멤버 함수입니다.  
  
##  <a name="selectprinter"></a>CWinApp::SelectPrinter  
 특정 프린터를 선택 하려면이 멤버 함수를 호출 하 고 이전에 선택한 인쇄 대화 상자에서 프린터를 해제 합니다.  
  
```  
void SelectPrinter(
    HANDLE hDevNames,  
    HANDLE hDevMode,  
    BOOL bFreeOld = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `hDevNames`  
 에 대 한 핸들을 [DEVNAMES](../../mfc/reference/devnames-structure.md) 드라이버, 장치 및 특정 프린터의 출력 포트 이름을 식별 하는 구조입니다.  
  
 `hDevMode`  
 에 대 한 핸들을 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) 장치 초기화 및 프린터의 환경에 대 한 정보를 지정 하는 구조입니다.  
  
 *bFreeOld*  
 이전에 선택한 프린터를 해제합니다.  
  
### <a name="remarks"></a>주의  
 모두 `hDevMode` 및 `hDevNames` 는 **NULL**, `SelectPrinter` 현재 기본 프린터를 사용 합니다.  
  
##  <a name="sethelpmode"></a>CWinApp::SetHelpMode  
 응용 프로그램의 도움말 형식을 설정합니다.  
  
```  
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```  
  
### <a name="parameters"></a>매개 변수  
 `eHelpType`  
 사용 하도록 도움말의 유형을 지정 합니다. 참조 [CWinApp::m_eHelpType](#m_ehelptype) 에 대 한 자세한 내용은 합니다.  
  
### <a name="remarks"></a>주의  
 응용 프로그램의 도움말 유형을 설정합니다.  
  
 응용 프로그램의 도움말 형식 HTMLHelp을 설정 하려면 [EnableHTMLHelp](#enablehtmlhelp)합니다. 호출 되 면 `EnableHTMLHelp`, 응용 프로그램의 도움말 응용 프로그램으로 HTMLHelp를 사용 해야 합니다. WinHelp를 사용 하 여 변경 하려는 경우에 호출 하면 `SetHelpMode` 설정 `eHelpType` 를 **afxWinHelp**합니다.  
  
##  <a name="setregistrykey"></a>CWinApp::SetRegistryKey  
 에서는 응용 프로그램 설정을 INI 파일 대신 레지스트리에 저장 하도록 지정 합니다.  
  
```  
void SetRegistryKey(LPCTSTR lpszRegistryKey);  
void SetRegistryKey(UINT nIDRegistryKey);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszRegistryKey*  
 키의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 *nIDRegistryKey*  
 레지스트리 키의 이름을 포함 하는 문자열 리소스의 ID입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 설정 *m_pszRegistryKey*, 다음 사용 되는 `GetProfileInt`, `GetProfileString`, `WriteProfileInt`, 및 `WriteProfileString` 의 멤버 함수 `CWinApp`. 이 함수를 호출 (MRU) 가장 최근에 사용한 파일 목록도 레지스트리에 저장 됩니다. 레지스트리 키가 일반적으로 회사의 이름을 표시 합니다. 다음과 같은 형식의 키에 저장 됩니다: 주의 하십시오\\<company></company>\>\\<application></application>\>\\<section></section>\>\\<value></value>\>합니다.  
  
##  <a name="supportsapplicationrecovery"></a>CWinApp::SupportsApplicationRecovery  
 다시 시작 관리자가 예기치 않게 종료 되는 응용 프로그램 복구 되는지 확인 합니다.  
  
```  
virtual BOOL SupportsApplicationRecovery() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`응용 프로그램에 다시 시작 관리자 복구를 나타냅니다. `FALSE` 없는 다시 시작 관리자를 나타냅니다.  
  
##  <a name="supportsautosaveatinterval"></a>CWinApp::SupportsAutosaveAtInterval  
 일정 한 간격으로 다시 시작 관리자에서 열려 있는 문서 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL SupportsAutosaveAtInterval() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`다시 시작 관리자에서 열려 있는 문서; 나타냅니다. `FALSE` 없는 다시 시작 관리자를 나타냅니다.  
  
##  <a name="supportsautosaveatrestart"></a>CWinApp::SupportsAutosaveAtRestart  
 결정 있는지 여부를 다시 시작 관리자에서 응용 프로그램 다시 시작 될 때 모든 열린 문서입니다.  
  
```  
virtual BOOL SupportsAutosaveAtRestart() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`응용 프로그램 다시 시작 되 고, 다시 시작 관리자에서 열려 있는 문서를 나타냅니다. `FALSE` 없는 다시 시작 관리자를 나타냅니다.  
  
##  <a name="supportsrestartmanager"></a>CWinApp::SupportsRestartManager  
 응용 프로그램이 다시 시작 관리자를 지원 하는지 여부를 결정 합니다.  
  
```  
virtual BOOL SupportsRestartManager() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`응용 프로그램에서 다시 시작 관리자;를 지원함을 나타냅니다. `FALSE` 없는 응용 프로그램을 나타냅니다.  
  
##  <a name="unregister"></a>CWinApp::Unregister  
 응용 프로그램 개체에 의해 등록 된 모든 파일을 등록 취소 합니다.  
  
```  
virtual BOOL Unregister();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아닌 값이고, 실패하면 0입니다.  
  
### <a name="remarks"></a>주의  
 `Unregister` 응용 프로그램 개체에서 수행 하는 등록을 취소 하는 함수 및 [등록](#register) 함수입니다. 일반적으로 두 함수는 MFC에서 암시적으로 이라고 하며 코드에 표시 되지 않습니다.  
  
 사용자 지정 등록 취소 단계를 수행 하려면이 함수를 재정의 합니다.  
  
##  <a name="unregistershellfiletypes"></a>CWinApp::UnregisterShellFileTypes  
 모든 응용 프로그램의 문서 유형을 Windows 파일 관리자에 등록을 취소 하려면이 멤버 함수를 호출 합니다.  
  
```  
void UnregisterShellFileTypes();
```  
  
##  <a name="winhelp"></a>CWinApp::WinHelp  
 WinHelp 응용 프로그램을 호출 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual void WinHelp(
    DWORD_PTR dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwData`  
 추가 데이터를 지정합니다. 값에 따라 사용 되는 값은 `nCmd` 매개 변수입니다.  
  
 `nCmd`  
 요청한 도움말의 형식을 지정합니다. 가능한 값 목록과 미치는 영향에 대 한는 `dwData` 매개 변수 참조는 [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267) Windows 함수.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 또한 WinHelp 응용 프로그램을 호출 하려면이 함수를 호출 합니다.  
  
 프레임 워크 때 자동으로 닫힙니다 WinHelp 응용 프로그램 응용 프로그램을 종료 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&53;](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]  
  
##  <a name="writeprofilebinary"></a>CWinApp::WriteProfileBinary  
 이 응용 프로그램의 레지스트리의 지정된 된 섹션에 이진 데이터를 쓸 함수를 호출 하거나. INI 파일입니다.  
  
```  
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszSection`  
 항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다. 섹션 없으면 자동으로 만들어집니다. 섹션의 이름은 사례 독립적입니다. 문자열에는 모든 조합의 대문자 및 소문자 수 있습니다.  
  
 `lpszEntry`  
 대상 값이 쓰여질 항목을 포함 하는 null로 끝나는 문자열을 가리킵니다. 지정된 된 섹션에 항목이 없으면 자동으로 만들어집니다.  
  
 `pData`  
 쓸 데이터를 가리킵니다.  
  
 `nBytes`  
 쓸 바이트 수를 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 이 예에서는 `CWinApp* pApp = AfxGetApp();` 하는 방법을 보여 주는 CWinApp 클래스는 `WriteProfileBinary` 및 `GetProfileBinary` MFC 응용 프로그램의 모든 함수에서 사용할 수 있습니다.  
  
 [!code-cpp[NVC_MFCWindowing #&54;](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]  
  
 다른 예에 대 한 예제를 참조 하십시오. [CWinApp::GetProfileBinary](#getprofilebinary)합니다.  
  
##  <a name="writeprofileint"></a>Cwinapp:: Writeprofileint  
 이 응용 프로그램의 레지스트리의 지정된 된 섹션에 지정된 된 값을 쓸 함수를 호출 하거나. INI 파일입니다.  
  
```  
BOOL WriteProfileInt(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszSection`  
 항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다. 섹션 없으면 자동으로 만들어집니다. 섹션의 이름은 사례 독립적입니다. 문자열에는 모든 조합의 대문자 및 소문자 수 있습니다.  
  
 `lpszEntry`  
 대상 값이 쓰여질 항목을 포함 하는 null로 끝나는 문자열을 가리킵니다. 지정된 된 섹션에 항목이 없으면 자동으로 만들어집니다.  
  
 `nValue`  
 쓸 값을 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 이 예에서는 `CWinApp* pApp = AfxGetApp();` 하는 방법을 보여 주는 CWinApp 클래스는 `WriteProfileString`, `WriteProfileInt`, `GetProfileString`, 및 `GetProfileInt` MFC 응용 프로그램의 모든 함수에서 사용할 수 있습니다.  
  
 [!code-cpp[NVC_MFCWindowing #&43;](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 다른 예에 대 한 예제를 참조 하십시오. [CWinApp::GetProfileInt](#getprofileint)합니다.  
  
##  <a name="writeprofilestring"></a>CWinApp::WriteProfileString  
 지정된 된 응용 프로그램의 레지스트리 섹션에 지정된 된 문자열을 작성 하려면이 멤버 함수를 호출 하거나. INI 파일입니다.  
  
```  
BOOL WriteProfileString(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszSection`  
 항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다. 섹션 없으면 자동으로 만들어집니다. 섹션의 이름은 사례 독립적입니다. 문자열에는 모든 조합의 대문자 및 소문자 수 있습니다.  
  
 `lpszEntry`  
 대상 값이 쓰여질 항목을 포함 하는 null로 끝나는 문자열을 가리킵니다. 지정된 된 섹션에 항목이 없으면 자동으로 만들어집니다. 이 매개 변수가 `NULL`, 지정 된 `lpszSection` 삭제 됩니다.  
  
 `lpszValue`  
 쓸 문자열을 가리킵니다. 이 매개 변수가 `NULL`, 변수로 지정 된 항목은 `lpszEntry` 매개 변수를 삭제 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&43;](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 다른 예에 대 한 예제를 참조 하십시오. [CWinApp::GetProfileInt](#getprofileint)합니다.  
  
##  <a name="setappid"></a>CWinApp::SetAppID  
 응용 프로그램에 대 한 응용 프로그램 사용자 모델 ID를 명시적으로 설정합니다. 모든 사용자 인터페이스 (가장 좋은 위치는 응용 프로그램 생성자는) 사용자에 게 표시 하기 전에이 메서드를 호출 해야 합니다.  
  
```  
void SetAppID(LPCTSTR lpcszAppID);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpcszAppID`  
 응용 프로그램 사용자 모델 ID를 지정 합니다.  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [CWinThread 클래스](../../mfc/reference/cwinthread-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [방법: 다시 시작 관리자 지원 추가](../../mfc/how-to-add-restart-manager-support.md)




