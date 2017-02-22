---
title: "CWinApp Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinApp"
  - "hInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "application objects [C++]"
  - "CWinApp class"
  - "HINSTANCE"
  - "main object"
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CWinApp Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 응용 프로그램 개체에서 파생 되는 기본 클래스입니다.  
  
## 구문  
  
```  
class CWinApp : public CWinThread  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CWinApp::CWinApp](../Topic/CWinApp::CWinApp.md)|`CWinApp` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CWinApp::AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md)|문서 템플릿은 응용 프로그램의 사용 가능한 문서 서식 파일 목록에 추가합니다.|  
|[CWinApp::AddToRecentFileList](../Topic/CWinApp::AddToRecentFileList.md)|파일 이름 가장 최근에 사용한 \(MRU\) 파일 목록에 추가합니다.|  
|[CWinApp::ApplicationRecoveryCallback](../Topic/CWinApp::ApplicationRecoveryCallback.md)|응용 프로그램이 예기치 않게 종료 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CWinApp::CloseAllDocuments](../Topic/CWinApp::CloseAllDocuments.md)|열려 있는 모든 문서를 닫습니다.|  
|[CWinApp::CreatePrinterDC](../Topic/CWinApp::CreatePrinterDC.md)|프린터 장치 컨텍스트를 만듭니다.|  
|[CWinApp::DelRegTree](../Topic/CWinApp::DelRegTree.md)|지정 된 키와 모든 하위 키를 삭제합니다.|  
|[CWinApp::DoMessageBox](../Topic/CWinApp::DoMessageBox.md)|Implements  [AfxMessageBox](../Topic/AfxMessageBox.md) 응용 프로그램.|  
|[CWinApp::DoWaitCursor](../Topic/CWinApp::DoWaitCursor.md)|대기 커서를 켜고 끕니다.|  
|[CWinApp::EnableD2DSupport](../Topic/CWinApp::EnableD2DSupport.md)|응용 프로그램 `D2D` 를 지원 합니다.  이 메서드는 주 창이 초기화되기 전에 호출합니다.|  
|[CWinApp::EnableHtmlHelp](../Topic/CWinApp::EnableHtmlHelp.md)|WinHelp 대신 응용 프로그램에서 Htmlhelp를 구현.|  
|[CWinApp::EnableTaskbarInteraction](../Topic/CWinApp::EnableTaskbarInteraction.md)|작업 표시줄의 상호 작용을 수 있습니다.|  
|[CWinApp::ExitInstance](../Topic/CWinApp::ExitInstance.md)|응용 프로그램이 종료 되 면 정리 하도록 재정의 하십시오입니다.|  
|[CWinApp::GetApplicationRecoveryParameter](../Topic/CWinApp::GetApplicationRecoveryParameter.md)|응용 프로그램 복구 방법에 대 한 입력된 매개 변수를 검색합니다.|  
|[CWinApp::GetApplicationRecoveryPingInterval](../Topic/CWinApp::GetApplicationRecoveryPingInterval.md)|다시 시작 관리자 복구 콜백 함수에 반환 될 때까지 기다리는 시간을 반환 합니다.|  
|[CWinApp::GetApplicationRestartFlags](../Topic/CWinApp::GetApplicationRestartFlags.md)|다시 시작 관리자에 대 한 플래그를 반환합니다.|  
|[CWinApp::GetAppRegistryKey](../Topic/CWinApp::GetAppRegistryKey.md)|HKEY\_CURRENT\_USER\\ "소프트웨어"에 대 한 반환 키를 \\RegistryKey\\ProfileName.|  
|[CWinApp::GetDataRecoveryHandler](../Topic/CWinApp::GetDataRecoveryHandler.md)|이 응용 프로그램이 인스턴스에 대 한 데이터 복구 처리기를 가져옵니다.|  
|[CWinApp::GetFirstDocTemplatePosition](../Topic/CWinApp::GetFirstDocTemplatePosition.md)|첫 번째 문서 서식 파일의 위치를 검색합니다.|  
|[CWinApp::GetHelpMode](../Topic/CWinApp::GetHelpMode.md)|응용 프로그램에서 사용 하는 도움말의 형식을 검색 합니다.|  
|[CWinApp::GetNextDocTemplate](../Topic/CWinApp::GetNextDocTemplate.md)|문서 서식 파일의 위치를 검색합니다.  재귀적으로 사용된 될 수 있습니다.|  
|[CWinApp::GetPrinterDeviceDefaults](../Topic/CWinApp::GetPrinterDeviceDefaults.md)|프린터 장치 기본값을 검색합니다.|  
|[CWinApp::GetProfileBinary](../Topic/CWinApp::GetProfileBinary.md)|항목에는 응용 프로그램에서 이진 데이터를 검색합니다.INI 파일입니다.|  
|[CWinApp::GetProfileInt](../Topic/CWinApp::GetProfileInt.md)|정수는 응용 프로그램에서 항목을 검색합니다.INI 파일입니다.|  
|[CWinApp::GetProfileString](../Topic/CWinApp::GetProfileString.md)|항목에는 응용 프로그램에서 문자열을 검색합니다.INI 파일입니다.|  
|[CWinApp::GetSectionKey](../Topic/CWinApp::GetSectionKey.md)|HKEY\_CURRENT\_USER\\ "소프트웨어"에 대 한 반환 키를 \\RegistryKey\\AppName\\lpszSection.|  
|[CWinApp::HideApplication](../Topic/CWinApp::HideApplication.md)|모든 문서를 닫기 전에 응용 프로그램을 숨깁니다.|  
|[CWinApp::HtmlHelp](../Topic/CWinApp::HtmlHelp.md)|호출 된 `HTMLHelp` Windows 함수.|  
|[CWinApp::InitInstance](../Topic/CWinApp::InitInstance.md)|창 개체를 만들 때 처럼 Windows 인스턴스 초기화를 수행 하도록 재정의 하십시오.|  
|[CWinApp::IsTaskbarInteractionEnabled](../Topic/CWinApp::IsTaskbarInteractionEnabled.md)|Windows 7 작업 표시줄의 상호 작용을 사용할 수 있는지 여부를 알려 줍니다.|  
|[CWinApp::LoadCursor](../Topic/CWinApp::LoadCursor.md)|커서 리소스를 로드합니다.|  
|[CWinApp::LoadIcon](../Topic/CWinApp::LoadIcon.md)|아이콘 리소스를 로드합니다.|  
|[CWinApp::LoadOEMCursor](../Topic/CWinApp::LoadOEMCursor.md)|로드 Windows OEM 미리 정의 된 커서는는  **OCR\_** WINDOWS에서 상수를 지정 합니다.H.|  
|[CWinApp::LoadOEMIcon](../Topic/CWinApp::LoadOEMIcon.md)|OEM Windows 미리 정의 된 아이콘을 로드 하는  **OIC\_** 상수에서 지정.H.|  
|[CWinApp::LoadStandardCursor](../Topic/CWinApp::LoadStandardCursor.md)|로드 Windows 미리 정의 된 커서는는  **IDC\_** WINDOWS에서 상수를 지정 합니다.H.|  
|[CWinApp::LoadStandardIcon](../Topic/CWinApp::LoadStandardIcon.md)|Windows의 미리 정의 된 아이콘을 로드 하는  **IDI\_** 상수에서 지정.H.|  
|[CWinApp::OnDDECommand](../Topic/CWinApp::OnDDECommand.md)|호출 프레임 워크에 대 한 응답으로 동적 데이터 교환 \(DDE\) 실행 명령입니다.|  
|[CWinApp::OnIdle](../Topic/CWinApp::OnIdle.md)|응용 프로그램별 유휴 시간 처리를 수행 하도록 재정의 됩니다.|  
|[CWinApp::OpenDocumentFile](../Topic/CWinApp::OpenDocumentFile.md)|문서를 열려면 파일에서 프레임 워크에서 호출 합니다.|  
|[CWinApp::ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md)|명령줄에서 플래그 및 개별 매개 변수를 구문 분석합니다.|  
|[CWinApp::PreTranslateMessage](../Topic/CWinApp::PreTranslateMessage.md)|메시지를 Windows 함수를 디스패치하기 전에 필터링  [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및  [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinApp::ProcessMessageFilter](../Topic/CWinApp::ProcessMessageFilter.md)|이러한 응용 프로그램에 도달 하기 전에 특정 메시지를 차단 합니다.|  
|[CWinApp::ProcessShellCommand](../Topic/CWinApp::ProcessShellCommand.md)|플래그 및 명령줄 인수를 처리합니다.|  
|[CWinApp::ProcessWndProcException](../Topic/CWinApp::ProcessWndProcException.md)|응용 프로그램의 메시지 및 명령 처리기에서 throw 된 모든 처리 되지 않은 예외를 차단 합니다.|  
|[CWinApp::Register](../Topic/CWinApp::Register.md)|사용자 지정된 등록을 수행합니다.|  
|[CWinApp::RegisterWithRestartManager](../Topic/CWinApp::RegisterWithRestartManager.md)|응용 프로그램이 다시 시작 관리자에 등록합니다.|  
|[CWinApp::ReopenPreviousFilesAtRestart](../Topic/CWinApp::ReopenPreviousFilesAtRestart.md)|다시 시작 관리자 응용 프로그램이 예기치 않게 종료할 때 열려 있던 파일을 다시 열 것인지를 결정 합니다.|  
|[CWinApp::RestartInstance](../Topic/CWinApp::RestartInstance.md)|다시 시작 관리자가 시작 하는 응용 프로그램 다시 시작을 처리 합니다.|  
|[CWinApp::RestoreAutosavedFilesAtRestart](../Topic/CWinApp::RestoreAutosavedFilesAtRestart.md)|응용 프로그램이 다시 시작 될 때 다시 시작 관리자 자동 저장 됨 파일 복원 여부를 결정 합니다.|  
|[CWinApp::Run](../Topic/CWinApp::Run.md)|기본 메시지 루프를 실행합니다.  사용자 메시지 루프를 재정의 합니다.|  
|[CWinApp::RunAutomated](../Topic/CWinApp::RunAutomated.md)|응용 프로그램의 명령줄에 대 한 테스트는 **\/Automation** 옵션.  사용되지 않습니다.  대신 값을 사용 하 여  [CCommandLineInfo::m\_bRunAutomated](../Topic/CCommandLineInfo::m_bRunAutomated.md) 호출  [ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md).|  
|[CWinApp::RunEmbedded](../Topic/CWinApp::RunEmbedded.md)|응용 프로그램의 명령줄에 대 한 테스트는 **\/Embedding** 옵션.  사용되지 않습니다.  대신 값을 사용 하 여  [CCommandLineInfo::m\_bRunEmbedded](../Topic/CCommandLineInfo::m_bRunEmbedded.md) 호출  [ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md).|  
|[CWinApp::SaveAllModified](../Topic/CWinApp::SaveAllModified.md)|사용자가 수정한 모든 문서를 저장할지 묻는 메시지가 나타납니다.|  
|[CWinApp::SelectPrinter](../Topic/CWinApp::SelectPrinter.md)|이전에 인쇄 대화 상자를 통해 사용자 지정 된 프린터를 선택 합니다.|  
|[CWinApp::SetHelpMode](../Topic/CWinApp::SetHelpMode.md)|설정 하 고 응용 프로그램에서 사용 되는 도움말 종류를 초기화 합니다.|  
|[CWinApp::SupportsApplicationRecovery](../Topic/CWinApp::SupportsApplicationRecovery.md)|다시 시작 관리자가 예기치 않게 종료 하는 응용 프로그램 복구 여부를 결정 합니다.|  
|[CWinApp::SupportsAutosaveAtInterval](../Topic/CWinApp::SupportsAutosaveAtInterval.md)|다시 시작 관리자 autosaves 정기적으로 문서를 열어 둘 것인지를 결정 합니다.|  
|[CWinApp::SupportsAutosaveAtRestart](../Topic/CWinApp::SupportsAutosaveAtRestart.md)|결정 여부 다시 시작 관리자 autosaves 응용 프로그램을 다시 시작할 때 문서 엽니다.|  
|[CWinApp::SupportsRestartManager](../Topic/CWinApp::SupportsRestartManager.md)|응용 프로그램이 다시 시작 관리자 지원 하는지 여부를 결정 합니다.|  
|[CWinApp::Unregister](../Topic/CWinApp::Unregister.md)|모두 정상으로 등록 취소를 `CWinApp` 개체입니다.|  
|[CWinApp::WinHelp](../Topic/CWinApp::WinHelp.md)|호출 된 `WinHelp` Windows 함수.|  
|[CWinApp::WriteProfileBinary](../Topic/CWinApp::WriteProfileBinary.md)|이진 데이터 항목에는 응용 프로그램을 씁니다.INI 파일입니다.|  
|[CWinApp::WriteProfileInt](../Topic/CWinApp::WriteProfileInt.md)|응용 프로그램의 진입점에 정수를 씁니다.INI 파일입니다.|  
|[CWinApp::WriteProfileString](../Topic/CWinApp::WriteProfileString.md)|응용 프로그램의 항목에 문자열을 씁니다.INI 파일입니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CWinApp::EnableShellOpen](../Topic/CWinApp::EnableShellOpen.md)|Windows 파일 관리자에서 데이터 파일을 열 수 있습니다.|  
|[CWinApp::LoadStdProfileSettings](../Topic/CWinApp::LoadStdProfileSettings.md)|표준 로드 합니다.INI 파일 설정 및 활성화는 MRU 파일 목록 기능|  
|[CWinApp::OnContextHelp](../Topic/CWinApp::OnContextHelp.md)|SHIFT \+ F1 도움말 응용 프로그램 내에서 처리합니다.|  
|[CWinApp::OnFileNew](../Topic/CWinApp::OnFileNew.md)|구현 된 `ID_FILE_NEW` 명령입니다.|  
|[CWinApp::OnFileOpen](../Topic/CWinApp::OnFileOpen.md)|구현 된 `ID_FILE_OPEN` 명령입니다.|  
|[CWinApp::OnFilePrintSetup](../Topic/CWinApp::OnFilePrintSetup.md)|구현 된 `ID_FILE_PRINT_SETUP` 명령입니다.|  
|[CWinApp::OnHelp](../Topic/CWinApp::OnHelp.md)|F1 도움말 \(현재 컨텍스트를 사용 하 여\) 응용 프로그램 내에서 처리 합니다.|  
|[CWinApp::OnHelpFinder](../Topic/CWinApp::OnHelpFinder.md)|처리는 `ID_HELP_FINDER` 및 `ID_DEFAULT_HELP` 명령입니다.|  
|[CWinApp::OnHelpIndex](../Topic/CWinApp::OnHelpIndex.md)|처리는 `ID_HELP_INDEX` 명령 및 기본 도움말 항목을 제공 합니다.|  
|[CWinApp::OnHelpUsing](../Topic/CWinApp::OnHelpUsing.md)|`ID_HELP_USING` 명령을 처리합니다.|  
|[CWinApp::RegisterShellFileTypes](../Topic/CWinApp::RegisterShellFileTypes.md)|응용 프로그램의 모든 문서 형식을 Windows 파일 관리자를 등록합니다.|  
|[CWinApp::SetAppID](../Topic/CWinApp::SetAppID.md)|명시적으로 응용 프로그램에 대 한 응용 프로그램 사용자 모델 ID를 설정합니다.  모든 사용자 인터페이스 \(응용 프로그램 생성자는 최상의 장소입니다\) 사용자에 게 표시 되기 전에이 메서드를 호출 해야 합니다.|  
|[CWinApp::SetRegistryKey](../Topic/CWinApp::SetRegistryKey.md)|응용 프로그램 설정이 아닌 레지스트리에 저장 됩니다.INI 파일입니다.|  
|[CWinApp::UnregisterShellFileTypes](../Topic/CWinApp::UnregisterShellFileTypes.md)|Windows 파일 관리자를 사용 하 여 응용 프로그램의 모든 문서 형식 등록을 취소 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CWinApp::m\_bHelpMode](../Topic/CWinApp::m_bHelpMode.md)|사용자 \(일반적으로 호출을 SHIFT \+ F1\) 도움말 컨텍스트 모드 인지를 나타냅니다.|  
|[CWinApp::m\_eHelpType](../Topic/CWinApp::m_eHelpType.md)|도움말 응용 프로그램에 사용 되는 형식을 지정 합니다.|  
|[CWinApp::m\_hInstance](../Topic/CWinApp::m_hInstance.md)|응용 프로그램의 현재 인스턴스를 식별합니다.|  
|[CWinApp::m\_lpCmdLine](../Topic/CWinApp::m_lpCmdLine.md)|응용 프로그램에 대 한 명령줄을 지정 하는 null로 끝나는 문자열을 가리킵니다.|  
|[CWinApp::m\_nCmdShow](../Topic/CWinApp::m_nCmdShow.md)|창이 처음 표시 될 방식을 지정 합니다.|  
|[CWinApp::m\_pActiveWnd](../Topic/CWinApp::m_pActiveWnd.md)|OLE 서버를 현재 위치에서 활성화 될 때 컨테이너 응용 프로그램의 주 창에 대 한 포인터입니다.|  
|[CWinApp::m\_pszAppID](../Topic/CWinApp::m_pszAppID.md)|응용 프로그램 사용자 모델 id|  
|[CWinApp::m\_pszAppName](../Topic/CWinApp::m_pszAppName.md)|응용 프로그램의 이름을 지정합니다.|  
|[CWinApp::m\_pszExeName](../Topic/CWinApp::m_pszExeName.md)|응용 프로그램의 모듈 이름입니다.|  
|[CWinApp::m\_pszHelpFilePath](../Topic/CWinApp::m_pszHelpFilePath.md)|응용 프로그램의 도움말 파일의 경로입니다.|  
|[CWinApp::m\_pszProfileName](../Topic/CWinApp::m_pszProfileName.md)|응용 프로그램의.INI 파일 이름입니다.|  
|[CWinApp::m\_pszRegistryKey](../Topic/CWinApp::m_pszRegistryKey.md)|응용 프로그램 프로 파일 설정을 저장 하기 위한 전체 레지스트리 키를 확인 하는 데 사용 합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CWinApp::m\_dwRestartManagerSupportFlags](../Topic/CWinApp::m_dwRestartManagerSupportFlags.md)|다시 시작 관리자의 동작 방식을 결정 하는 플래그입니다.|  
|[CWinApp::m\_nAutosaveInterval](../Topic/CWinApp::m_nAutosaveInterval.md)|Autosaves 사이의 밀리초 단위의 시간 길이입니다.|  
|[CWinApp::m\_pDataRecoveryHandler](../Topic/CWinApp::m_pDataRecoveryHandler.md)|데이터 복구 처리기는 응용 프로그램에 대 한 포인터입니다.|  
  
## 설명  
 응용 프로그램 개체 응용 프로그램 \(및 각 인스턴스의\) 초기화 하 고 응용 프로그램 실행에 대 한 멤버 함수를 제공 합니다.  
  
 Mfc 클래스를 사용 하 여 각 응용 프로그램에서 파생 한 개체는 포함할 수 있습니다 `CWinApp`.  이 개체 다른 C\+\+ 전역 개체를 만들 때 생성 되며, Windows에서 호출 하는 경우는 이미 사용할 수 있는 `WinMain` Microsoft Foundation 클래스 라이브러리에서 제공 하는 함수.  선언 하면 파생 된 `CWinApp` 개체는 전역 수준에서.  
  
 응용 프로그램 클래스에서 파생 `CWinApp`, 재정의  [InitInstance](../Topic/CWinApp::InitInstance.md) 멤버 함수를 응용 프로그램의 주 창 개체를 만들 수 있습니다.  
  
 외에 `CWinApp` 멤버 함수를 제공 Mfc 라이브러리에 액세스 하려면 다음 전역 함수를 `CWinApp` 개체와 다른 글로벌 정보:  
  
-   [AfxGetApp](../Topic/AfxGetApp.md) 에 대 한 포인터를 가져옵니다는 `CWinApp` 개체입니다.  
  
-   [AfxGetInstanceHandle](../Topic/AfxGetInstanceHandle.md) 현재 응용 프로그램 인스턴스에 대 한 핸들을 가져옵니다.  
  
-   [AfxGetResourceHandle](../Topic/AfxGetResourceHandle.md) 응용 프로그램의 리소스 핸들을 가져옵니다.  
  
-   [AfxGetAppName](../Topic/AfxGetAppName.md) 응용 프로그램의 이름이 들어 있는 문자열에 대 한 포인터를 가져옵니다.  또는 경우에 대 한 포인터는 `CWinApp` 개체, 사용 `m_pszExeName` 응용 프로그램의 이름입니다.  
  
 참조  [CWinApp: 응용 프로그램 클래스의](../../mfc/cwinapp-the-application-class.md) 에 대 한 자세한는 `CWinApp` 다음의 개요를 포함 하 여 클래스:  
  
-   `CWinApp`\-응용 프로그램 마법사로 작성 된 코드를 파생 합니다.  
  
-   `CWinApp`역할에 일련의 응용 프로그램을 실행 합니다.  
  
-   `CWinApp`멤버 함수 구현은 기본의입니다.  
  
-   `CWinApp`주요 함수.  
  
 **M\_hPrevInstance** 데이터 멤버를 더 이상 없습니다.  이전 인스턴스를 검색 하는 방법에 대 한 `CWinApp`에서 기술 자료 문서 "어떻게에 식별는 이전 인스턴스를 있는 응용 프로그램" \(KB106385\)를 참조 하십시오 [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;106385](http://support.microsoft.com/default.aspx?scid=kb;en-us;106385).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 `CWinApp`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CWinThread Class](../../mfc/reference/cwinthread-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [방법: 다시 시작 관리자 지원 추가](../../mfc/how-to-add-restart-manager-support.md)