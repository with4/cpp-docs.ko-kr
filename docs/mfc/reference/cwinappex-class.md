---
title: "CWinAppEx Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinAppEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinAppEx class"
ms.assetid: a3d3e053-3e22-463f-9444-c73abb1bb9d7
caps.latest.revision: 37
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinAppEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CWinAppEx`응용 프로그램 상태 처리 상태를 레지스트리에 저장 상태를 레지스트리에서 로드 응용 프로그램 관리자를 초기화 및 이러한 동일한 응용 프로그램 관리자에 대 한 링크를 제공 합니다.  
  
## 구문  
  
```  
class CWinAppEx : public CWinApp  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CWinAppEx::CWinAppEx](../Topic/CWinAppEx::CWinAppEx.md)|`CWinAppEx` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CWinAppEx::CleanState](../Topic/CWinAppEx::CleanState.md)|응용 프로그램에 대 한 정보는 Windows 레지스트리에서 제거합니다.|  
|[CWinAppEx::EnableLoadWindowPlacement](../Topic/CWinAppEx::EnableLoadWindowPlacement.md)|응용 프로그램의 초기 크기 및 위치를 주 프레임 창 레지스트리에서 로드 여부를 지정 합니다.|  
|[CWinAppEx::EnableTearOffMenus](../Topic/CWinAppEx::EnableTearOffMenus.md)|수 있도록 분리 된 메뉴는 응용 프로그램에 대 한입니다.|  
|[CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md)|응용 프로그램에서 사용자 지정 메뉴 명령을 만들 수 있습니다.|  
|[CWinAppEx::ExitInstance](../Topic/CWinAppEx::ExitInstance.md)|프레임 워크에 의해 호출 된 `Run` 멤버 함수를이 응용 프로그램의이 인스턴스를 종료 합니다.  \(재정의 [CWinApp::ExitInstance](../Topic/CWinApp::ExitInstance.md).\)|  
|[CWinAppEx::GetBinary](../Topic/CWinAppEx::GetBinary.md)|지정 된 레지스트리 값에 연결 된 이진 데이터를 읽습니다.|  
|[CWinAppEx::GetContextMenuManager](../Topic/CWinAppEx::GetContextMenuManager.md)|전역 하는 포인터를 반환 합니다.  [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) 개체입니다.|  
|[CWinAppEx::GetDataVersion](../Topic/CWinAppEx::GetDataVersion.md)||  
|[CWinAppEx::GetDataVersionMajor](../Topic/CWinAppEx::GetDataVersionMajor.md)|Windows 레지스트리에 저장 된 응용 프로그램의 주 버전을 반환 합니다.|  
|[CWinAppEx::GetDataVersionMinor](../Topic/CWinAppEx::GetDataVersionMinor.md)|Windows 레지스트리에 저장 된 응용 프로그램의 부 버전을 반환 합니다.|  
|[CWinAppEx::GetInt](../Topic/CWinAppEx::GetInt.md)|지정 된 레지스트리 값에 연결 된 숫자 데이터를 읽습니다.|  
|[CWinAppEx::GetKeyboardManager](../Topic/CWinAppEx::GetKeyboardManager.md)|전역 하는 포인터를 반환 합니다.  [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) 개체입니다.|  
|[CWinAppEx::GetMouseManager](../Topic/CWinAppEx::GetMouseManager.md)|전역 하는 포인터를 반환 합니다.  [CMouseManager](../../mfc/reference/cmousemanager-class.md) 개체입니다.|  
|[CWinAppEx::GetObject](../Topic/CWinAppEx::GetObject.md)|읽어 `CObject`\-지정한 레지스트리 값이 연결 된 데이터를 파생 합니다.|  
|[CWinAppEx::GetRegSectionPath](../Topic/CWinAppEx::GetRegSectionPath.md)|레지스트리 키의 경로 나타내는 문자열을 반환 합니다.  제공 된 상대 경로 응용 프로그램 경로와이 경로 연결합니다.|  
|[CWinAppEx::GetRegistryBase](../Topic/CWinAppEx::GetRegistryBase.md)|응용 프로그램에 대 한 레지스트리 경로 반환합니다.|  
|[CWinAppEx::GetSectionBinary](../Topic/CWinAppEx::GetSectionBinary.md)|지정 된 키와 값을 레지스트리와 연관 된 이진 데이터를 읽습니다.|  
|[CWinAppEx::GetSectionInt](../Topic/CWinAppEx::GetSectionInt.md)|숫자 데이터에서 지정 된 키와 값에 관련 된 레지스트리를 읽습니다.|  
|[CWinAppEx::GetSectionObject](../Topic/CWinAppEx::GetSectionObject.md)|읽어 `CObject` 값을 레지스트리에서 지정 된 키와 연결 된 데이터입니다.|  
|[CWinAppEx::GetSectionString](../Topic/CWinAppEx::GetSectionString.md)|지정 된 키와 값을 레지스트리에서 연결 된 문자열 데이터를 읽습니다.|  
|[CWinAppEx::GetShellManager](../Topic/CWinAppEx::GetShellManager.md)|전역 하는 포인터를 반환 합니다.  [CShellManager](../../mfc/reference/cshellmanager-class.md) 개체입니다.|  
|[CWinAppEx::GetString](../Topic/CWinAppEx::GetString.md)|지정 된 레지스트리 값에 연결 된 문자열 데이터를 읽습니다.|  
|[CWinAppEx::GetTooltipManager](../Topic/CWinAppEx::GetTooltipManager.md)|전역 하는 포인터를 반환 합니다.  [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) 개체입니다.|  
|[CWinAppEx::GetUserToolsManager](../Topic/CWinAppEx::GetUserToolsManager.md)|전역 하는 포인터를 반환 합니다.  [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) 개체입니다.|  
|[CWinAppEx::InitContextMenuManager](../Topic/CWinAppEx::InitContextMenuManager.md)|`CContextMenuManager` 개체를 초기화합니다.|  
|[CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md)|`CKeyboardManager` 개체를 초기화합니다.|  
|[CWinAppEx::InitMouseManager](../Topic/CWinAppEx::InitMouseManager.md)|`CMouseManager` 개체를 초기화합니다.|  
|[CWinAppEx::InitShellManager](../Topic/CWinAppEx::InitShellManager.md)|초기화는 `CShellManager` 클래스|  
|[CWinAppEx::InitTooltipManager](../Topic/CWinAppEx::InitTooltipManager.md)|`CTooltipManager` 클래스를 초기화합니다.|  
|[CWinAppEx::IsResourceSmartUpdate](../Topic/CWinAppEx::IsResourceSmartUpdate.md)||  
|[CWinAppEx::IsStateExists](../Topic/CWinAppEx::IsStateExists.md)|지정 된 키를 레지스트리에서 있는지 여부를 나타냅니다.|  
|[CWinAppEx::LoadState](../Topic/CWinAppEx::LoadState.md)|레지스트리에서 응용 프로그램 상태를 로드합니다.|  
|[CWinAppEx::OnAppContextHelp](../Topic/CWinAppEx::OnAppContextHelp.md)|상황에 맞는 도움말을 사용자가 요청할 때 프레임 워크에 의해 호출 된  **사용자 지정** 대화 상자.|  
|[CWinAppEx::OnViewDoubleClick](../Topic/CWinAppEx::OnViewDoubleClick.md)|사용자 응용 프로그램에서 아무 곳 이나 두 번 클릭 하면 사용자 정의 명령을 호출 합니다.|  
|[CWinAppEx::OnWorkspaceIdle](../Topic/CWinAppEx::OnWorkspaceIdle.md)||  
|[CWinAppEx::SaveState](../Topic/CWinAppEx::SaveState.md)|응용 프로그램 프레임 워크의 상태는 Windows 레지스트리에 씁니다.|  
|[CWinAppEx::SetRegistryBase](../Topic/CWinAppEx::SetRegistryBase.md)|기본 레지스트리 키의 경로 설정합니다.  이 키에 대 한 모든 후속 레지스트리 호출 루트로 활용할 수 있습니다.|  
|[CWinAppEx::ShowPopupMenu](../Topic/CWinAppEx::ShowPopupMenu.md)|팝업 메뉴를 표시합니다.|  
|[CWinAppEx::WriteBinary](../Topic/CWinAppEx::WriteBinary.md)|이진 데이터는 지정 된 레지스트리 값을 씁니다.|  
|[CWinAppEx::WriteInt](../Topic/CWinAppEx::WriteInt.md)|숫자 데이터에 지정 된 레지스트리 값을 씁니다.|  
|[CWinAppEx::WriteObject](../Topic/CWinAppEx::WriteObject.md)|기록 데이터에서 파생 되는 [CObject Class](../../mfc/reference/cobject-class.md) 지정 된 레지스트리 값을.|  
|[CWinAppEx::WriteSectionBinary](../Topic/CWinAppEx::WriteSectionBinary.md)|이진 데이터에 지정 된 레지스트리 키의 값을 씁니다.|  
|[CWinAppEx::WriteSectionInt](../Topic/CWinAppEx::WriteSectionInt.md)|숫자 데이터 값의 지정 된 레지스트리 키에 씁니다.|  
|[CWinAppEx::WriteSectionObject](../Topic/CWinAppEx::WriteSectionObject.md)|기록 데이터에서 파생 된 `CObject` 값 클래스의 지정 된 레지스트리 키.|  
|[CWinAppEx::WriteSectionString](../Topic/CWinAppEx::WriteSectionString.md)|지정 된 레지스트리 키의 값을 문자열 데이터를 씁니다.|  
|[CWinAppEx::WriteString](../Topic/CWinAppEx::WriteString.md)|지정 된 레지스트리 값에 문자열 데이터를 씁니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CWinAppEx::LoadCustomState](../Topic/CWinAppEx::LoadCustomState.md)|응용 프로그램 상태가 로드 되지 않은 경우 프레임 워크에서 호출 됩니다.|  
|[CWinAppEx::LoadWindowPlacement](../Topic/CWinAppEx::LoadWindowPlacement.md)|크기 및 위치를 응용 프로그램의 레지스트리를 로드할 때 프레임 워크에 의해 호출 됩니다.  로드 된 데이터의 크기와 위치는 주 프레임의 마지막으로 응용 프로그램을 닫을 때 포함 되어 있습니다.|  
|[CWinAppEx::OnClosingMainFrame](../Topic/CWinAppEx::OnClosingMainFrame.md)|주 프레임 창을 처리할 때 프레임 워크에 의해 호출 `WM_CLOSE`.|  
|[CWinAppEx::PreLoadState](../Topic/CWinAppEx::PreLoadState.md)|바로 전에 프레임 워크에서 호출 응용 프로그램의 상태를 로드 됩니다.|  
|[CWinAppEx::PreSaveState](../Topic/CWinAppEx::PreSaveState.md)|바로 전에 프레임 워크에서 호출 응용 프로그램 상태에 저장 됩니다.|  
|[CWinAppEx::ReloadWindowPlacement](../Topic/CWinAppEx::ReloadWindowPlacement.md)|크기와 위치를 제공 된 창에서 레지스트리를 다시 로드|  
|[CWinAppEx::SaveCustomState](../Topic/CWinAppEx::SaveCustomState.md)|응용 프로그램 상태를 레지스트리에 씁니다. 그 후 프레임 워크에 의해 호출 됩니다.|  
|[CWinAppEx::StoreWindowPlacement](../Topic/CWinAppEx::StoreWindowPlacement.md)|주 프레임의 위치와 크기를 레지스트리에 쓸 프레임 워크에서 호출 합니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CWinAppEx::m\_bForceImageReset](../Topic/CWinAppEx::m_bForceImageReset.md)|프레임 워크는 프레임 창 도구 모음에서 로드 될 때 모든 도구 모음 이미지 다시 여부를 지정 합니다.|  
  
## 설명  
 대부분의 MFC 프레임 워크에서 제공 하는 기능에 따라 달라 집니다를 `CWinAppEx` 클래스입니다.  통합할 수 있는 `CWinAppEx` 두 가지 응용 프로그램 클래스:  
  
-   생성 된 `CWinAppEx` 주 스레드에서 클래스.  
  
-   주 응용 프로그램 클래스에서 파생 `CWinAppEx`.  
  
 통합 하 여 후 `CWinAppEx` 응용 프로그램에 응용 프로그램 관리자 중 하나를 초기화할 수 있습니다.  응용 프로그램 관리자를 사용 하기 전에 적절 한 초기화 메서드를 호출 하 여 초기화 해야 합니다.  특정 관리자에 대 한 포인터를 얻으려면 관련된 get 메서드를 호출 합니다.  The `CWinAppEx` class manages the following application managers: [CMouseManager Class](../../mfc/reference/cmousemanager-class.md), [CContextMenuManager Class](../../mfc/reference/ccontextmenumanager-class.md), [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md), [CUserToolsManager Class](../../mfc/reference/cusertoolsmanager-class.md), and [CMenuTearOffManager Class](../../mfc/reference/cmenutearoffmanager-class.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 [CWinAppEx](../../mfc/reference/cwinappex-class.md)  
  
## 요구 사항  
 **헤더:** afxwinappex.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)   
 [CMouseManager Class](../../mfc/reference/cmousemanager-class.md)   
 [CContextMenuManager Class](../../mfc/reference/ccontextmenumanager-class.md)   
 [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md)   
 [CUserToolsManager Class](../../mfc/reference/cusertoolsmanager-class.md)