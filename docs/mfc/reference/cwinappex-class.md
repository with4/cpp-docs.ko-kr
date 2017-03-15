---
title: "CWinAppEx 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinAppEx
dev_langs:
- C++
helpviewer_keywords:
- CWinAppEx class
ms.assetid: a3d3e053-3e22-463f-9444-c73abb1bb9d7
caps.latest.revision: 37
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
ms.openlocfilehash: 6931f1e794116882722e402c9cb95acec1ebdfd5
ms.lasthandoff: 02/24/2017

---
# <a name="cwinappex-class"></a>CWinAppEx 클래스
`CWinAppEx`응용 프로그램 상태를 처리, 상태를 레지스트리에 저장, 레지스트리에서 상태를 로드, 응용 프로그램 관리자, 초기화 및 이러한 동일한 응용 프로그램 관리자에 대 한 링크를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CWinAppEx : public CWinApp  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CWinAppEx::CWinAppEx](#cwinappex)|`CWinAppEx` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CWinAppEx::CleanState](#cleanstate)|Windows 레지스트리에서 응용 프로그램에 대 한 정보를 제거합니다.|  
|[CWinAppEx::EnableLoadWindowPlacement](#enableloadwindowplacement)|여부를 응용 프로그램에서에서 로드 합니다 초기 크기와 위치는 주 프레임 창의 레지스트리를 지정 합니다.|  
|[CWinAppEx::EnableTearOffMenus](#enabletearoffmenus)|수 있도록 분리 메뉴는 응용 프로그램입니다.|  
|[CWinAppEx::EnableUserTools](#enableusertools)|응용 프로그램에서 사용자 지정 메뉴 명령을 만들 수 있습니다.|  
|[CWinAppEx::ExitInstance](#exitinstance)|프레임 워크 내에서 호출 된 `Run` 멤버 함수를 응용 프로그램의이 인스턴스를 종료 합니다. (재정의 [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).)|  
|[CWinAppEx::GetBinary](#getbinary)|지정 된 레지스트리 값과 연결 된 이진 데이터를 읽습니다.|  
|[CWinAppEx::GetContextMenuManager](#getcontextmenumanager)|전역에 대 한 포인터를 반환 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) 개체입니다.|  
|[CWinAppEx::GetDataVersion](#getdataversion)||  
|[CWinAppEx::GetDataVersionMajor](#getdataversionmajor)|Windows 레지스트리에 저장 하는 응용 프로그램의 주 버전을 반환 합니다.|  
|[CWinAppEx::GetDataVersionMinor](#getdataversionminor)|Windows 레지스트리에 저장 된 응용 프로그램의 부 버전을 반환 합니다.|  
|[CWinAppEx::GetInt](#getint)|레지스트리에서 지정된 된 값과 연관 된 숫자 데이터를 읽습니다.|  
|[CWinAppEx::GetKeyboardManager](#getkeyboardmanager)|전역에 대 한 포인터를 반환 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) 개체입니다.|  
|[CWinAppEx::GetMouseManager](#getmousemanager)|전역에 대 한 포인터를 반환 [CMouseManager](../../mfc/reference/cmousemanager-class.md) 개체입니다.|  
|[CWinAppEx::GetObject](#getobject)|읽고 `CObject`-레지스트리에서 지정 된 값과 연결 된 데이터를 파생 합니다.|  
|[CWinAppEx::GetRegSectionPath](#getregsectionpath)|레지스트리 키의 경로 나타내는 문자열을 반환 합니다. 이 경로 제공 된 상대 경로와 응용 프로그램 경로 연결합니다.|  
|[CWinAppEx::GetRegistryBase](#getregistrybase)|응용 프로그램에 대 한 레지스트리 경로 반환합니다.|  
|[CWinAppEx::GetSectionBinary](#getsectionbinary)|지정 된 키와 레지스트리 값에 연관 된 이진 데이터를 읽습니다.|  
|[CWinAppEx::GetSectionInt](#getsectionint)|지정한 키와 값와 관련 된 레지스트리에서 숫자 데이터를 읽습니다.|  
|[CWinAppEx::GetSectionObject](#getsectionobject)|읽고 `CObject` 값 레지스트리에서 지정 된 키와 연결 된 데이터를 합니다.|  
|[CWinAppEx::GetSectionString](#getsectionstring)|연결 된 지정한 키와 값의 레지스트리에서 문자열 데이터를 읽습니다.|  
|[CWinAppEx::GetShellManager](#getshellmanager)|전역에 대 한 포인터를 반환 [CShellManager](../../mfc/reference/cshellmanager-class.md) 개체입니다.|  
|[CWinAppEx::GetString](#getstring)|레지스트리에서 지정된 된 값과 연관 된 문자열 데이터를 읽습니다.|  
|[CWinAppEx::GetTooltipManager](#gettooltipmanager)|전역에 대 한 포인터를 반환 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) 개체입니다.|  
|[CWinAppEx::GetUserToolsManager](#getusertoolsmanager)|전역에 대 한 포인터를 반환 [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) 개체입니다.|  
|[CWinAppEx::InitContextMenuManager](#initcontextmenumanager)|초기화는 `CContextMenuManager` 개체입니다.|  
|[CWinAppEx::InitKeyboardManager](#initkeyboardmanager)|초기화는 `CKeyboardManager` 개체입니다.|  
|[CWinAppEx::InitMouseManager](#initmousemanager)|초기화는 `CMouseManager` 개체입니다.|  
|[CWinAppEx::InitShellManager](#initshellmanager)|초기화는 `CShellManager` 클래스|  
|[CWinAppEx::InitTooltipManager](#inittooltipmanager)|초기화는 `CTooltipManager` 클래스입니다.|  
|[CWinAppEx::IsResourceSmartUpdate](#isresourcesmartupdate)||  
|[CWinAppEx::IsStateExists](#isstateexists)|레지스트리에 지정된 된 키가 있는지 여부를 나타냅니다.|  
|[CWinAppEx::LoadState](#loadstate)|레지스트리에서 응용 프로그램 상태를 로드합니다.|  
|[CWinAppEx::OnAppContextHelp](#onappcontexthelp)|사용자에 대 한 상황에 맞는 도움말을 요청 하는 경우에 프레임 워크에서 호출 된 **사용자 지정** 대화 상자입니다.|  
|[CWinAppEx::OnViewDoubleClick](#onviewdoubleclick)|사용자가 응용 프로그램에서 아무 곳 이나 두 번 클릭할 때 사용자 정의 명령을 호출 합니다.|  
|[CWinAppEx::OnWorkspaceIdle](#onworkspaceidle)||  
|[CWinAppEx::SaveState](#savestate)|Windows 레지스트리에 응용 프로그램 프레임 워크의 상태를 씁니다.|  
|[CWinAppEx::SetRegistryBase](#setregistrybase)|기본 레지스트리 키의 경로 설정합니다. 이 키는 모든 후속 레지스트리 호출에 대 한 루트도 사용 합니다.|  
|[CWinAppEx::ShowPopupMenu](#showpopupmenu)|팝업 메뉴를 표시합니다.|  
|[CWinAppEx::WriteBinary](#writebinary)|지정된 된 레지스트리 값을 이진 데이터를 씁니다.|  
|[CWinAppEx::WriteInt](#writeint)|지정 된 레지스트리 값에 숫자 데이터를 씁니다.|  
|[CWinAppEx::WriteObject](#writeobject)|파생 된 데이터를 쓰는 [CObject 클래스](../../mfc/reference/cobject-class.md) 을 지정 된 레지스트리 값입니다.|  
|[CWinAppEx::WriteSectionBinary](#writesectionbinary)|지정된 된 레지스트리 키의 값에는 이진 데이터를 씁니다.|  
|[CWinAppEx::WriteSectionInt](#writesectionint)|지정된 된 레지스트리 키의 값에 숫자 데이터를 씁니다.|  
|[CWinAppEx::WriteSectionObject](#writesectionobject)|파생 된 데이터를 씁니다는 `CObject` 지정된 된 레지스트리 키의 값으로 클래스입니다.|  
|[CWinAppEx::WriteSectionString](#writesectionstring)|지정된 된 레지스트리 키의 값에 문자열 데이터를 씁니다.|  
|[CWinAppEx::WriteString](#writestring)|지정 된 레지스트리 값에 문자열 데이터를 씁니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CWinAppEx::LoadCustomState](#loadcustomstate)|응용 프로그램 상태를 로드 하는 경우에 프레임 워크에서 호출 합니다.|  
|[CWinAppEx::LoadWindowPlacement](#loadwindowplacement)|레지스트리에서 응용 프로그램의 위치와 크기를 로드할 때 프레임 워크에 의해 호출 됩니다. 로드 된 데이터 크기와 위치를 주 프레임의 마지막으로 닫은 응용 프로그램 시간을 포함 합니다.|  
|[CWinAppEx::OnClosingMainFrame](#onclosingmainframe)|주 프레임 창에서 처리 될 때 프레임 워크에서 호출 `WM_CLOSE`합니다.|  
|[CWinAppEx::PreLoadState](#preloadstate)|바로 전에 프레임 워크에서 호출 응용 프로그램 상태에 로드 됩니다.|  
|[CWinAppEx::PreSaveState](#presavestate)|바로 전에 프레임 워크에서 호출 응용 프로그램 상태에 저장 됩니다.|  
|[CWinAppEx::ReloadWindowPlacement](#reloadwindowplacement)|크기와 레지스트리에서 제공된 된 창 위치를 다시 로드|  
|[CWinAppEx::SaveCustomState](#savecustomstate)|응용 프로그램 상태를 레지스트리에 씁니다 후 프레임 워크에 의해 호출 됩니다.|  
|[CWinAppEx::StoreWindowPlacement](#storewindowplacement)|주 프레임의 위치와 크기를 레지스트리에 쓸 프레임 워크에서 호출 됩니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CWinAppEx::m_bForceImageReset](#m_bforceimagereset)|도구 모음을 포함 하는 프레임 창에 로드 될 때 프레임 워크에서 모든 도구 모음 이미지를 다시는 여부를 지정 합니다.|  
  
## <a name="remarks"></a>주의  
 대부분의 MFC 프레임 워크에서 제공 하는 기능에 따라 달라 집니다는 `CWinAppEx` 클래스입니다. 통합할 수는 `CWinAppEx` 두 가지 방법 중 하나에서 응용 프로그램에 클래스:  
  
-   생성 된 `CWinAppEx` 주 스레드의 클래스입니다.  
  
-   기본 응용 프로그램 클래스를 파생 `CWinAppEx`합니다.  
  
 통합 후 `CWinAppEx` 응용 프로그램에 응용 프로그램 관리자 중 하나를 초기화할 수 있습니다. 응용 프로그램 관리자를 사용 하기 전에 적절 한 initialize 메서드를 호출 하 여 초기화 해야 합니다. 특정 관리자에 대 한 포인터를 얻으려면 연결 된 get 메서드를 호출 합니다. `CWinAppEx` 클래스에 다음 응용 프로그램 관리자는 관리: [CMouseManager 클래스](../../mfc/reference/cmousemanager-class.md), [CContextMenuManager 클래스](../../mfc/reference/ccontextmenumanager-class.md), [CKeyboardManager 클래스](../../mfc/reference/ckeyboardmanager-class.md), [CUserToolsManager 클래스](../../mfc/reference/cusertoolsmanager-class.md), 및 [CMenuTearOffManager 클래스](../../mfc/reference/cmenutearoffmanager-class.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 [CWinAppEx](../../mfc/reference/cwinappex-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwinappex.h  
  
##  <a name="a-namecleanstatea--cwinappexcleanstate"></a><a name="cleanstate"></a>CWinAppEx::CleanState  
 Windows 레지스트리에서 응용 프로그램에 대 한 모든 정보를 제거합니다.  
  
```  
virtual BOOL CleanState(LPCTSTR lpszSectionName=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszSectionName`  
 레지스트리 키의 경로 포함 하는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 레지스트리의 특정 섹션에서 응용 프로그램 데이터를 지웁니다. 매개 변수를 사용 하 여 지울 섹션을 지정할 수 있습니다 `lpszSectionName`합니다. 경우 `lpszSectionName` 는 `NULL`,이 메서드는에 저장 된 기본 레지스트리 경로 사용 하 여는 `CWinAppEx` 개체입니다. 기본 레지스트리 경로 가져오려면 [CWinAppEx::GetRegistryBase](#getregistrybase)합니다.  
  
##  <a name="a-namecwinappexa--cwinappexcwinappex"></a><a name="cwinappex"></a>CWinAppEx::CWinAppEx  
 `CWinAppEx` 개체를 생성합니다.  
  
```  
CWinAppEx(BOOL bResourceSmartUpdate = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bResourceSmartUpdate`  
 Workspace 개체 검색 하 고 리소스 업데이트를 처리 해야 하는지 여부를 지정 하는 부울 매개 변수입니다.  
  
### <a name="remarks"></a>주의  
 `CWinAppEx` 클래스에 초기화 메서드가 저장 하 고 응용 프로그램 정보를 레지스트리에 로드에 대 한 기능을 제공 하 고 전역 응용 프로그램 설정을 제어 합니다. 전역 관리자와 같은을 사용할 수도 있습니다는 [CKeyboardManager 클래스](../../mfc/reference/ckeyboardmanager-class.md) 및 [CUserToolsManager 클래스](../../mfc/reference/cusertoolsmanager-class.md)합니다. 각 응용 프로그램의 인스턴스 하나만 가질 수는 `CWinAppEx` 클래스입니다.  
  
##  <a name="a-nameenableloadwindowplacementa--cwinappexenableloadwindowplacement"></a><a name="enableloadwindowplacement"></a>CWinAppEx::EnableLoadWindowPlacement  
 여부를 응용 프로그램에서에서 로드 합니다 초기 크기와 위치는 주 프레임 창의 레지스트리를 지정 합니다.  
  
```  
void EnableLoadWindowPlacement(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 응용 프로그램의 초기 크기와 주 프레임 창 위치 레지스트리에서 로드 하는지 여부를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 기본적으로 주 프레임의 위치와 크기는 다른 응용 프로그램 설정과 함께 레지스트리에서 로드 됩니다. 이 발생 하는 동안 [CWinAppEx::LoadState](#loadstate)합니다. 레지스트리에서 초기 창 배치를 로드 하지 않으려는 경우이 메서드를 호출 `bEnable` 로 설정 `false`합니다.  
  
##  <a name="a-nameenabletearoffmenusa--cwinappexenabletearoffmenus"></a><a name="enabletearoffmenus"></a>CWinAppEx::EnableTearOffMenus  
 만들고 초기화는 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) 개체입니다.  
  
```  
BOOL EnableTearOffMenus(
    LPCTSTR lpszRegEntry,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszRegEntry`  
 레지스트리 키의 경로 포함 하는 문자열입니다. 이 레지스트리 키를 사용 하 여 분리 메뉴에 대 한 정보를 저장 하는 응용 프로그램입니다.  
  
 [in] `uiCmdFirst`  
 메뉴의 첫 번째 떼어낼 id입니다.  
  
 [in] `uiCmdLast`  
 마지막 떼어낼 메뉴의 id입니다.  
  
### <a name="return-value"></a>반환 값  
 `True`하는 경우는 `CMenuTearOffManager` 만들어지고 초기화 되었습니다. `false` 오류가 발생 하거나는 `CMenuTearOffManager` 이미 있습니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 사용 하 여 응용 프로그램에서 분리 메뉴를 사용 하도록 설정 합니다. 이 함수를 호출 해야 `InitInstance`합니다.  
  
##  <a name="a-nameenableusertoolsa--cwinappexenableusertools"></a><a name="enableusertools"></a>CWinAppEx::EnableUserTools  
 응용 프로그램에서 키 입력을 줄일 하는 사용자 지정 메뉴 명령을 만들 수 있습니다. 이 메서드가 만드는 [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) 개체입니다.  
  
```  
BOOL EnableUserTools(
    const UINT uiCmdToolsDummy,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast,  
    CRuntimeClass* pToolRTC = RUNTIME_CLASS(CUserTool),  
    UINT uArgMenuID = 0,  
    UINT uInitDirMenuID = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmdToolsDummy`  
 부호 없는 정수 사용자 도구 메뉴의 명령 ID에 대 한 자리 표시자로 사용 하는 프레임 워크입니다.  
  
 [in] `uiCmdFirst`  
 첫 번째 사용자 도구 명령에 대 한 명령 ID입니다.  
  
 [in] `uiCmdLast`  
 마지막 사용자 도구 명령에 대 한 명령 ID입니다.  
  
 [in] `pToolRTC`  
 A는 클래스는 `CUserToolsManager` 개체가 사용 하 여 새 사용자 도구를 만듭니다.  
  
 [in] `uArgMenuID`  
 인수 메뉴 id입니다.  
  
 [in] `uInitDirMenuID`  
 초기 도구 디렉터리에 대 한 메뉴 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드를 만들고 초기화 하는 경우는 `CUserToolsManager` 개체입니다. `FALSE` 메서드가 실패 하거나 경우는 `CUserToolsManager` 개체가 이미 있습니다.  
  
### <a name="remarks"></a>주의  
 사용자 정의 도구를 사용 하면 프레임 워크는 자동으로 사용자 지정 하는 동안 확장 될 수 있는 동적 메뉴를 지원 합니다. 프레임 워크는 외부 명령을 사용 하 여 각 새 항목을 연결합니다. 프레임 워크에서 적절 한 항목을 선택 하면 이러한 명령을 호출 하는 **도구** 메뉴.  
  
 사용자가 새 항목에 추가할 때마다 프레임 워크에는 새 개체를 만듭니다. 새 개체에 대 한 클래스 형식으로 정의 된 `pToolRTC`합니다. `pToolRTC` 클래스 형식에서 파생 되어야 합니다는 [CUserTool 클래스](../../mfc/reference/cusertool-class.md)합니다.  
  
 사용자 도구와 응용 프로그램에 통합 하는 방법에 대 한 자세한 내용은 참조 [사용자 정의 형식](../../mfc/user-defined-tools.md)합니다.  
  
##  <a name="a-nameexitinstancea--cwinappexexitinstance"></a><a name="exitinstance"></a>CWinAppEx::ExitInstance  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetbinarya--cwinappexgetbinary"></a><a name="getbinary"></a>CWinAppEx::GetBinary  
 지정된 된 레지스트리 키에서 이진 데이터를 읽습니다.  
  
```  
BOOL GetBinary(
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszEntry`  
 레지스트리 키의 이름을 포함 하는 문자열입니다.  
  
 [out] `ppData`  
 메서드는 이진 데이터를 채우는 버퍼에 대 한 포인터입니다.  
  
 [out] `pBytes`  
 읽은 바이트 수를 작성 하는 메서드에서 사용 하는 부호 없는 정수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `True`성공 하면 `false` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 이 메서드는 레지스트리에 기록 된 이진 데이터를 읽습니다. 레지스트리 데이터를 작성 하려면 메서드를 사용 하 여 [CWinAppEx::WriteBinary](#writebinary) 및 [CWinAppEx::WriteSectionBinary](#writesectionbinary)합니다.  
  
 `lpszEntry` 매개 변수는 응용 프로그램에 대 한 기본 레지스트리 키 아래에 레지스트리 항목의 이름입니다. 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase) 각각.  
  
##  <a name="a-namegetcontextmenumanagera--cwinappexgetcontextmenumanager"></a><a name="getcontextmenumanager"></a>CWinAppEx::GetContextMenuManager  
 전역에 대 한 포인터를 반환 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) 개체입니다.  
  
```  
CContextMenuManager* GetContextMenuManager();
```  
  
### <a name="return-value"></a>반환 값  
 전역에 대 한 포인터 `CContextMenuManager` 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 호출 하는 CContextMenuManager 개체가 초기화 되지 않은 경우 [CWinAppEx::InitContextMenuManager](#initcontextmenumanager) 대 한 포인터를 반환 하기 전에 합니다.  
  
##  <a name="a-namegetdataversiona--cwinappexgetdataversion"></a><a name="getdataversion"></a>CWinAppEx::GetDataVersion  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetDataVersion() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetdataversionmajora--cwinappexgetdataversionmajor"></a><a name="getdataversionmajor"></a>CWinAppEx::GetDataVersionMajor  
 호출할 때 Windows 레지스트리에 저장 되는 응용 프로그램의 주 버전을 반환 [CWinAppEx::SaveState](#savestate)합니다.  
  
```  
int GetDataVersionMajor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 주 버전 번호를 포함 하는 정수 값입니다.  
  
##  <a name="a-namegetdataversionminora--cwinappexgetdataversionminor"></a><a name="getdataversionminor"></a>CWinAppEx::GetDataVersionMinor  
 호출할 때 Windows 레지스트리에 저장 되는 응용 프로그램의 부 버전을 반환 [CWinAppEx::SaveState](#savestate)합니다.  
  
```  
int GetDataVersionMinor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 부 버전 번호를 포함 하는 정수 값입니다.  
  
##  <a name="a-namegetinta--cwinappexgetint"></a><a name="getint"></a>CWinAppEx::GetInt  
 지정된 된 레지스트리 키에서 정수 데이터를 읽습니다.  
  
```  
int GetInt(
    LPCTSTR lpszEntry,  
    int nDefault = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszEntry`  
 레지스트리 항목의 이름을 포함 하는 문자열입니다.  
  
 [in] `nDefault`  
 지정 된 레지스트리 항목이 존재 하지 않는 경우 메서드가 반환 하는 기본 값입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 레지스트리 데이터 그렇지 않으면 `nDefault`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 레지스트리에서 정수 데이터를 읽습니다. 로 표시 된 레지스트리 키와 연결 된 정수 데이터가 없는 경우 `lpszEntry`,이 메서드는 반환 `nDefault`합니다. 레지스트리 데이터를 작성 하려면 메서드를 사용 하 여 [CWinAppEx::WriteSectionInt](#writesectionint) 및 [CWinAppEx::WriteInt](#writeint)합니다.  
  
 `lpszEntry` 매개 변수는 응용 프로그램에 대 한 기본 레지스트리 키 아래에 레지스트리 항목의 이름입니다. 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase) 각각.  
  
##  <a name="a-namegetkeyboardmanagera--cwinappexgetkeyboardmanager"></a><a name="getkeyboardmanager"></a>CWinAppEx::GetKeyboardManager  
 전역에 대 한 포인터를 반환 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) 개체입니다.  
  
```  
CKeyboardManager* GetKeyboardManager();
```  
  
### <a name="return-value"></a>반환 값  
 전역에 대 한 포인터 `CKeyboardManager` 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 호출 하는 키보드 관리자 초기화 되지 않은 경우 [CWinAppEx::InitKeyboardManager](#initkeyboardmanager) 대 한 포인터를 반환 하기 전에 합니다.  
  
##  <a name="a-namegetmousemanagera--cwinappexgetmousemanager"></a><a name="getmousemanager"></a>CWinAppEx::GetMouseManager  
 전역에 대 한 포인터를 반환 [CMouseManager](../../mfc/reference/cmousemanager-class.md) 개체입니다.  
  
```  
CMouseManager* GetMouseManager();
```  
  
### <a name="return-value"></a>반환 값  
 전역에 대 한 포인터 `CMouseManager` 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 호출 하는 마우스 관리자, 초기화 되지 않은 경우 [CWinAppEx::InitMouseManager](#initmousemanager) 대 한 포인터를 반환 하기 전에 합니다.  
  
##  <a name="a-namegetobjecta--cwinappexgetobject"></a><a name="getobject"></a>CWinAppEx::GetObject  
 읽고 [CObject](../../mfc/reference/cobject-class.md)레지스트리에서-dervied 데이터입니다.  
  
```  
BOOL GetObject(
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszEntry`  
 레지스트리 항목의 상대 경로 포함 하는 문자열입니다.  
  
 [out] `obj`  
 에 대 한 참조는 `CObject`합니다. 메서드는이 참조를 사용 하 여 레지스트리 데이터를 저장 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 레지스트리에 파생 된 데이터를 읽을 `CObject`합니다. 쓰려는 `CObject` 데이터를 레지스트리에 하나를 사용 합니다. [CWinAppEx::WriteObject](#writeobject) 또는 [CWinAppEx::WriteSectionObject](#writesectionobject)합니다.  
  
 `lpszEntry` 매개 변수는 응용 프로그램에 대 한 기본 레지스트리 키 아래에 있는 레지스트리 항목의 이름입니다. 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase) 각각.  
  
##  <a name="a-namegetregistrybasea--cwinappexgetregistrybase"></a><a name="getregistrybase"></a>CWinAppEx::GetRegistryBase  
 응용 프로그램에 대 한 기본 레지스트리 경로 검색합니다.  
  
```  
LPCTSTR GetRegistryBase();
```  
  
### <a name="return-value"></a>반환 값  
 기본 레지스트리 위치 경로 포함 하는 문자열입니다.  
  
### <a name="remarks"></a>주의  
 모든 메서드는 [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md) 레지스트리 시작 기본 위치에 액세스 하는 합니다. 이 메서드를 사용 하 여 기본 레지스트리 위치에 대 한 경로 검색 합니다. 사용 하 여 [CWinAppEx::SetRegistryBase](#setregistrybase) 기본 레지스트리 위치를 변경 합니다.  
  
##  <a name="a-namegetregsectionpatha--cwinappexgetregsectionpath"></a><a name="getregsectionpath"></a>CWinAppEx::GetRegSectionPath  
 만들고 레지스트리 키의 절대 경로 반환 합니다.  
  
```  
CString GetRegSectionPath(LPCTSTR szSectionAdd = _T(""));
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `szSectionAdd`  
 레지스트리 키의 상대 경로 포함 하는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 A `CString` 하는 레지스트리 키의 절대 경로 포함 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는의 상대 경로 추가 하 여 레지스트리 키의 절대 경로 정의 합니다. `szSectionAdd` 응용 프로그램에 대 한 기본 레지스트리 위치에 있습니다. 기본 레지스트리 키를 가져오려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase)합니다.  
  
##  <a name="a-namegetsectionbinarya--cwinappexgetsectionbinary"></a><a name="getsectionbinary"></a>CWinAppEx::GetSectionBinary  
 레지스트리에서 이진 데이터를 읽습니다.  
  
```  
BOOL GetSectionBinary(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszSubSection`  
 레지스트리 키의 상대 경로 포함 하는 문자열입니다.  
  
 [in] `lpszEntry`  
 읽을 값을 포함 하는 문자열입니다.  
  
 [out] `ppData`  
 메서드는 데이터를 저장 하는 위치는 버퍼에 대 한 포인터입니다.  
  
 [out] `pBytes`  
 부호 없는 정수에 대 한 포인터입니다. 이 메서드는 크기를 기록 `ppData` 이 매개 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 `True`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 메서드를 사용 하 여 레지스트리 작성 된 이진 데이터를 읽어 [CWinAppEx::WriteBinary](#writebinary) 및 [CWinAppEx::WriteSectionBinary](#writesectionbinary)합니다.  
  
 `lpszSubSection` 매개 변수가 레지스트리 항목에 대 한 절대 경로 않습니다. 것은 응용 프로그램에 대 한 기본 레지스트리 키의 끝에 추가 되는 상대 경로입니다. 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase) 각각.  
  
##  <a name="a-namegetsectioninta--cwinappexgetsectionint"></a><a name="getsectionint"></a>CWinAppEx::GetSectionInt  
 레지스트리에서 정수 데이터를 읽습니다.  
  
```  
int GetSectionInt(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    int nDefault = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszSubSection`  
 레지스트리 키의 상대 경로 포함 하는 문자열입니다.  
  
 [in] `lpszEntry`  
 읽을 값을 포함 하는 문자열입니다.  
  
 [in] `nDefault`  
 지정된 된 값이 없는 경우 반환할 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 레지스트리 값;에 저장 된 정수 데이터 `nDefault` 데이터가 존재 하지 않는 경우.  
  
### <a name="remarks"></a>주의  
 메서드를 사용 하 여 [CWinAppEx::WriteInt](#writeint) 및 [CWinAppEx::WriteSectionInt](#writesectionint) 정수 데이터를 레지스트리에 쓸 수 있습니다.  
  
 `lpszSubSection` 매개 변수가 레지스트리 항목의 절대 경로 않습니다. 응용 프로그램에 대 한 기본 레지스트리 키의 끝에 추가 하는 상대 경로 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase) 각각.  
  
##  <a name="a-namegetsectionobjecta--cwinappexgetsectionobject"></a><a name="getsectionobject"></a>CWinAppEx::GetSectionObject  
 읽고 [CObject](../../mfc/reference/cobject-class.md) 레지스트리에서 레지스트리 데이터입니다.  
  
```  
BOOL GetSectionObject(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszSubSection`  
 레지스트리 키의 상대 경로 포함 하는 문자열입니다.  
  
 [in] `lpszEntry`  
 읽을 값을 포함 하는 문자열입니다.  
  
 [out] `obj`  
 에 대 한 참조는 `CObject`합니다. 이 메서드가 사용 하 여 `CObject` 레지스트리 데이터를 저장 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 레지스트리에서 데이터를 읽습니다. 데이터 읽기는 `CObject` 데이터 또는 데이터에서 파생 된 클래스에 대 한 `CObject`합니다. 쓰려는 `CObject` 데이터를 레지스트리에 하나를 사용 합니다. [CWinAppEx::WriteObject](#writeobject) 또는 [CWinAppEx::WriteSectionObject](#writesectionobject)합니다.  
  
 `lpszSubSection` 매개 변수가 레지스트리 항목에 대 한 절대 경로 않습니다. 것은 응용 프로그램에 대 한 기본 레지스트리 키의 끝에 추가 되는 상대 경로입니다. 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase) 각각.  
  
##  <a name="a-namegetsectionstringa--cwinappexgetsectionstring"></a><a name="getsectionstring"></a>CWinAppEx::GetSectionString  
 읽기는 레지스트리에서 데이터 문자열입니다.  
  
```  
CString GetSectionString(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszDefault = _T(""));
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszSubSection`  
 레지스트리 키의 상대 경로 포함 하는 문자열입니다.  
  
 [in] `lpszEntry`  
 읽을 값을 포함 하는 문자열입니다.  
  
 [in] `lpszDefault`  
 지정된 된 값이 없는 경우 반환할 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 데이터가 있는; 지정 된 레지스트리 값에 저장 된 문자열 데이터 그렇지 않으면 `lpszDefault`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 레지스트리에 기록 하는 문자열 데이터를 읽습니다. 사용 하 여 [CWinAppEx::WriteString](#writestring) 및 [CWinAppEx::WriteSectionString](#writesectionstring) 문자열 데이터를 레지스트리에 쓸 수 있습니다.  
  
 `lpszSubSection` 매개 변수가 레지스트리 항목에 대 한 절대 경로 않습니다. 것은 응용 프로그램에 대 한 기본 레지스트리 키의 끝에 추가 되는 상대 경로입니다. 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase) 각각.  
  
##  <a name="a-namegetshellmanagera--cwinappexgetshellmanager"></a><a name="getshellmanager"></a>CWinAppEx::GetShellManager  
 전역에 대 한 포인터를 반환 [CShellManager](../../mfc/reference/cshellmanager-class.md) 개체입니다.  
  
```  
CShellManager* GetShellManager();
```  
  
### <a name="return-value"></a>반환 값  
 전역에 대 한 포인터 `CShellManager` 개체입니다.  
  
### <a name="remarks"></a>주의  
 하는 경우는 `CShellManager` 개체가 초기화 되지 않은,이 함수를 호출 [CWinAppEx::InitShellManager](#initshellmanager) 대 한 포인터를 반환 하기 전에 합니다.  
  
##  <a name="a-namegetstringa--cwinappexgetstring"></a><a name="getstring"></a>CWinAppEx::GetString  
 읽기는 지정된 된 레지스트리 키의 데이터 문자열입니다.  
  
```  
CString GetString(
    LPCTSTR lpszEntry,  
    LPCTSTR lpzDefault= _T(""));
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszEntry`  
 레지스트리 키의 이름을 포함 하는 문자열  
  
 [in] `lpzDefault`  
 지정 된 레지스트리 항목이 존재 하지 않는 경우 메서드가 반환 하는 기본 값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 레지스트리에 저장 된 문자열 데이터 `lpszDefault` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 이 메서드는 레지스트리에 기록 하는 문자열 데이터를 읽습니다. 레지스트리 데이터를 작성 하려면 메서드를 사용 하 여 [CWinAppEx::WriteString](#writestring) 또는 [CWinAppEx::WriteSectionString](#writesectionstring)합니다.  
  
 `lpszEntry` 매개 변수는 응용 프로그램에 대 한 기본 레지스트리 키 아래에 레지스트리 항목의 이름입니다. 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase) 각각.  
  
##  <a name="a-namegettooltipmanagera--cwinappexgettooltipmanager"></a><a name="gettooltipmanager"></a>CWinAppEx::GetTooltipManager  
 전역에 대 한 포인터를 반환 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) 개체입니다.  
  
```  
CTooltipManager* GetTooltipManager();
```  
  
### <a name="return-value"></a>반환 값  
 전역에 대 한 포인터 `CTooltipManager` 개체입니다.  
  
### <a name="remarks"></a>주의  
 하는 경우는 `CTooltipManager` 개체가 초기화 되지 않은,이 함수를 호출 [CWinAppEx::InitTooltipManager](#inittooltipmanager) 대 한 포인터를 반환 하기 전에 합니다.  
  
##  <a name="a-namegetusertoolsmanagera--cwinappexgetusertoolsmanager"></a><a name="getusertoolsmanager"></a>CWinAppEx::GetUserToolsManager  
 전역에 대 한 포인터를 반환 [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) 개체입니다.  
  
```  
CUserToolsManager* GetUserToolsManager();
```  
  
### <a name="return-value"></a>반환 값  
 전역에 대 한 포인터 `CUserToolsManager` 개체입니다. `NULL` 응용 프로그램에 대 한 사용자 도구 관리를 사용 하지 않는 경우.  
  
### <a name="remarks"></a>주의  
 에 대 한 포인터를 검색 하기 전에 `CUserToolsManager` 개체를 호출 하 여 관리자를 초기화 해야 [CWinAppEx::EnableUserTools](#enableusertools)합니다.  
  
##  <a name="a-nameinitcontextmenumanagera--cwinappexinitcontextmenumanager"></a><a name="initcontextmenumanager"></a>CWinAppEx::InitContextMenuManager  
 초기화는 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) 개체입니다.  
  
```  
BOOL InitContextMenuManager();
```  
  
### <a name="return-value"></a>반환 값  
 메서드가 만드는 CContextMenuManager 개체; 0이 아닌 인 경우 0은 `CContextMenuManager` 개체가 이미 있습니다.  
  
### <a name="remarks"></a>주의  
 호출 하는 경우 [CWinAppEx::GetContextMenuManager](#getcontextmenumanager), 해당 메서드의 기본 구현에서는 호출 `InitContextMenuManager`합니다.  
  
 경우에 상황에 맞는 메뉴 관리자가 이미 응용 프로그램을 호출 하면 `InitContextMenuManager`, 응용 프로그램을 갖습니다는 [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) 실패 합니다. 따라서 호출 하면 안 `InitContextMenuManager` 만들면는 `CContextMenuManager` 개체에 직접. 사용자 지정을 사용 하지 않는 경우 `CContextMenuManager`를 사용 해야 `GetContextMenuManager` 만들려는 `CContextMenuManager` 개체입니다.  
  
##  <a name="a-nameinitkeyboardmanagera--cwinappexinitkeyboardmanager"></a><a name="initkeyboardmanager"></a>CWinAppEx::InitKeyboardManager  
 초기화는 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) 개체입니다.  
  
```  
BOOL InitKeyboardManager();
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 만드는 경우 0이 아닌는 `CKeyboardManager` 개체; 인 경우 0은 `CKeyboardManager` 개체가 이미 있습니다.  
  
### <a name="remarks"></a>주의  
 호출 하는 경우 [CWinAppEx::GetKeyboardManager](#getkeyboardmanager), 해당 메서드의 기본 구현에서는 호출 `InitKeyboardManager`합니다.  
  
 경우에 키보드 관리자가 이미 응용 프로그램을 호출 하면 `InitKeyboardManager`, 응용 프로그램을 갖습니다는 [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) 실패 합니다. 따라서 호출 하면 안 `InitKeyboardManager` 만들면는 `CKeyboardManager` 개체에 직접. 사용자 지정을 사용 하지 않는 경우 `CKeyboardManager`를 사용 해야 `GetKeyboardManager` 만들려는 `CKeyboardManager` 개체입니다.  
  
##  <a name="a-nameinitmousemanagera--cwinappexinitmousemanager"></a><a name="initmousemanager"></a>CWinAppEx::InitMouseManager  
 초기화는 [CMouseManager](../../mfc/reference/cmousemanager-class.md) 개체입니다.  
  
```  
BOOL InitMouseManager();
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 만드는 경우 0이 아닌는 `CMouseManager` 개체; 인 경우 0은 `CMouseManager` 개체가 이미 있습니다.  
  
### <a name="remarks"></a>주의  
 호출 하는 경우 [CWinAppEx::GetMouseManager](#getmousemanager), 해당 메서드의 기본 구현에서는 호출 `InitMouseManager`합니다.  
  
 경우에 마우스 관리자가 이미 응용 프로그램을 호출 하면 `InitMouseManager`, 응용 프로그램을 갖습니다는 [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) 실패 합니다. 따라서 호출 하면 안 `InitMouseManager` 만들면는 `CMouseManager` 개체에 직접. 사용자 지정을 사용 하지 않는 경우 `CMouseManager`를 사용 해야 `GetMouseManager` 만들려는 `CMouseManager` 개체입니다.  
  
##  <a name="a-nameinitshellmanagera--cwinappexinitshellmanager"></a><a name="initshellmanager"></a>CWinAppEx::InitShellManager  
 초기화는 [CShellManager](../../mfc/reference/cshellmanager-class.md) 개체입니다.  
  
```  
BOOL InitShellManager();
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 만드는 경우 0이 아닌는 `CShellManager` 개체; 인 경우 0은 `CShellManager` 개체가 이미 있습니다.  
  
### <a name="remarks"></a>주의  
 호출 하는 경우 [CWinAppEx::GetShellManager](#getshellmanager), 해당 메서드의 기본 구현에서는 호출 `InitShellManager`합니다.  
  
 경우에 셸 관리자가 이미 응용 프로그램을 호출 하면 `InitShellManager`, 응용 프로그램 발생 한 [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) 실패 합니다. 따라서 호출 하지 않으면 `InitShellManager` 만들면는 `CShellManager` 개체에 직접. 사용자 지정을 사용 하지 않는 경우 `CShellManager`를 사용 하 여 `GetShellManager` 만들려는 `CShellManager` 개체입니다.  
  
##  <a name="a-nameinittooltipmanagera--cwinappexinittooltipmanager"></a><a name="inittooltipmanager"></a>CWinAppEx::InitTooltipManager  
 초기화는 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) 개체입니다.  
  
```  
BOOL InitTooltipManager();
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 만드는 경우 0이 아닌는 `CTooltipManager` 개체; 인 경우 0은 `CTooltipManager` 개체가 이미 있습니다.  
  
### <a name="remarks"></a>주의  
 호출 하는 경우 [CWinAppEx::GetTooltipManager](#gettooltipmanager), 해당 메서드의 기본 구현에서는 호출 `InitTooltipManager`합니다.  
  
 경우에 도구 설명 관리자가 이미 응용 프로그램을 호출 하면 `InitTooltipManager`, 응용 프로그램을 갖습니다는 [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) 실패 합니다. 따라서 호출 하면 안 `InitTooltipManager` 만들면는 `CTooltipManager` 개체에 직접. 사용자 지정을 사용 하지 않는 경우 `CTooltipManager`를 사용 해야 `GetTooltipManager` 만들려는 `CTooltipManager` 개체입니다.  
  
##  <a name="a-nameisresourcesmartupdatea--cwinappexisresourcesmartupdate"></a><a name="isresourcesmartupdate"></a>CWinAppEx::IsResourceSmartUpdate  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsResourceSmartUpdate() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameisstateexistsa--cwinappexisstateexists"></a><a name="isstateexists"></a>CWinAppEx::IsStateExists  
 레지스트리에 지정된 된 키가 있는지 여부를 나타냅니다.  
  
```  
BOOL IsStateExists(LPCTSTR lpszSectionName);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszSectionName`  
 레지스트리 키의 경로 포함 하는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 키가 레지스트리;에 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="a-nameloadcustomstatea--cwinappexloadcustomstate"></a><a name="loadcustomstate"></a>CWinAppEx::LoadCustomState  
 프레임 워크는 레지스트리에서 응용 프로그램의 상태를 로드 한 후이 메서드를 호출 합니다.  
  
```  
virtual void LoadCustomState();
```  
  
### <a name="remarks"></a>주의  
 응용 프로그램이 레지스트리에서 상태를 로드 한 후 모든 처리를 수행 하려는 경우이 메서드를 재정의 합니다. 기본적으로이 메서드는 아무 작업도 수행 합니다.  
  
 레지스트리에서 사용자 지정 상태 정보를 로드 하기 위해 정보 저장 해야를 사용 하 여 [CWinAppEx::SaveCustomState](#savecustomstate)합니다.  
  
##  <a name="a-nameloadstatea--cwinappexloadstate"></a><a name="loadstate"></a>CWinAppEx::LoadState  
 Windows 레지스트리에서 응용 프로그램 상태를 읽습니다.  
  
```  
BOOL LoadState(
    CMDIFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL LoadState(
    CFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL LoadState(
    COleIPFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
virtual BOOL LoadState(
    LPCTSTR lpszSectionName = NULL,  
    CFrameImpl* pFrameImpl = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pFrame`  
 프레임 창 개체에 대 한 포인터입니다. 메서드는이 프레임 창에 레지스트리에 상태 정보를 적용합니다.  
  
 [in] `lpszSectionName`  
 레지스트리 키의 상대 경로 포함 하는 문자열입니다.  
  
 [in] `pFrameImpl`  
 에 대 한 포인터는 `CFrameImpl` 개체입니다. 메서드는이 프레임 창에 레지스트리에 상태 정보를 적용합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 프레임 창에 대 한 상태 정보 및 응용 프로그램 상태를 로드합니다. 프레임 창에 대 한 로드 된 정보는 제공 된 프레임 창에 적용 됩니다. 프레임 창 정보를 제공 하지 않으면 응용 프로그램 상태 정보에만 로드 됩니다. 상태를 포함 하는 응용 프로그램 정보는 [CMouseManager 클래스](../../mfc/reference/cmousemanager-class.md), [CContextMenuManager 클래스](../../mfc/reference/ccontextmenumanager-class.md), [CKeyboardManager 클래스](../../mfc/reference/ckeyboardmanager-class.md), 및 [CUserToolsManager 클래스](../../mfc/reference/cusertoolsmanager-class.md)합니다.  
  
 기본 구현은 `CFrameImpl::OnLoadFrame` 호출 `LoadState`합니다.  
  
 `lpszSectionName` 매개 변수는 레지스트리 항목에 대 한 절대 경로가 아닙니다. 응용 프로그램에 대 한 기본 레지스트리 키의 끝에 추가 하는 상대 경로 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase) 각각.  
  
##  <a name="a-nameloadwindowplacementa--cwinappexloadwindowplacement"></a><a name="loadwindowplacement"></a>CWinAppEx::LoadWindowPlacement  
 레지스트리에서 주 프레임 창의 위치와 크기를 로드할 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual BOOL LoadWindowPlacement(
    CRect& rectNormalPosition,  
    int& nFlags,  
    int& nShowCmd);
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `rectNormalPosition`  
 복원 된 위치에 있을 때 주 프레임 창의 좌표를 포함 하는 사각형입니다.  
  
 [out] `nFlags`  
 최소화 된 창 및 운영 체제는 최소화 된 창을 복원 된 창 간에 전환 하는 방법의 위치를 제어 하는 플래그입니다.  
  
 [out] `nShowCmd`  
 창의 표시 상태를 지정 하는 정수입니다. 가능한 값에 대 한 자세한 내용은 참조 [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow)합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로 MFC 자동으로 로드 이전 위치 및 주 프레임 창의 상태 응용 프로그램을 시작 합니다. 이 정보는 레지스트리에 저장 방법에 대 한 자세한 내용은 참조 [CWinAppEx::StoreWindowPlacement](#storewindowplacement)합니다.  
  
 주 프레임 창에 대 한 추가 정보를 로드 하려는 경우이 메서드를 재정의 합니다.  
  
##  <a name="a-namembforceimagereseta--cwinappexmbforceimagereset"></a><a name="m_bforceimagereset"></a>CWinAppEx::m_bForceImageReset  
 다시 로드 되 면 도구 모음을 포함 하는 프레임 창 프레임 워크 다시 모든 도구 모음 이미지를 설정 하는지 여부를 지정 합니다.  
  
```  
BOOL m_bForceImageReset;  
```  
  
### <a name="remarks"></a>주의  
 `m_bForceImageReset` 데이터 멤버에 보호 된 변수입니다.  
  
##  <a name="a-nameonappcontexthelpa--cwinappexonappcontexthelp"></a><a name="onappcontexthelp"></a>CWinAppEx::OnAppContextHelp  
 프레임 워크는 사용자에 대 한 상황에 맞는 도움말을 요청 하는 경우이 메서드를 호출의 **사용자 지정** 대화 상자입니다.  
  
```  
virtual void OnAppContextHelp(
    CWnd* pWndControl,  
    const DWORD dwHelpIDArray[]);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndControl`  
 사용자는에 대 한 상황에 맞는 도움말을 호출 하는 창 개체에 대 한 포인터입니다.  
  
 [in] `dwHelpIDArray[]`  
 예약 된 값입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 나중에 사용할 현재 예약 되어 있습니다. 기본 구현은 없으며 현재 호출 되지 않기 프레임 워크에 의해 합니다.  
  
##  <a name="a-nameonclosingmainframea--cwinappexonclosingmainframe"></a><a name="onclosingmainframe"></a>CWinAppEx::OnClosingMainFrame  
 프레임 워크는 프레임 창에서 처리 하는 경우이 메서드를 호출 `WM_CLOSE`합니다.  
  
```  
virtual void OnClosingMainFrame(CFrameImpl* pFrameImpl);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pFrameImpl`  
 에 대 한 포인터는 `CFrameImpl` 개체입니다.  
  
### <a name="remarks"></a>주의  
 상태를 저장 하는이 메서드의 기본 구현은 `pFrameImpl`합니다.  
  
##  <a name="a-nameonviewdoubleclicka--cwinappexonviewdoubleclick"></a><a name="onviewdoubleclick"></a>CWinAppEx::OnViewDoubleClick  
 사용자가 해당 보기 내에서 아무 곳 이나 두 번 클릭할 때 보기와 연결 된 사용자 지정 명령을 호출 합니다.  
  
```  
virtual BOOL OnViewDoubleClick(
    CWnd* pWnd,  
    int iViewId);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 파생 된 개체에 대 한 포인터는 [CView 클래스](../../mfc/reference/cview-class.md)합니다.  
  
 [in] `iViewId`  
 보기 id입니다.  
  
### <a name="return-value"></a>반환 값  
 `True`프레임 워크 명령을; 발견 한 경우 그렇지 않으면 false입니다.  
  
### <a name="remarks"></a>주의  
 사용자 지정 마우스 동작을 지원 하기 위해 호출 해야 처리 하는 경우이 함수는 `WM_LBUTTONDBLCLK` 메시지입니다. 이 메서드는에서 제공 하는 뷰 ID와 연결 된 명령을 실행 합니다 `iViewId`합니다. 사용자 지정 마우스 동작에 대 한 자세한 내용은 참조 [키보드 및 마우스 사용자 지정](../../mfc/keyboard-and-mouse-customization.md)합니다.  
  
##  <a name="a-nameonworkspaceidlea--cwinappexonworkspaceidle"></a><a name="onworkspaceidle"></a>CWinAppEx::OnWorkspaceIdle  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnWorkspaceIdle(CWnd*);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `CWnd*`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namepreloadstatea--cwinappexpreloadstate"></a><a name="preloadstate"></a>CWinAppEx::PreLoadState  
 프레임 워크 바로 레지스트리에서 응용 프로그램의 상태를 로드 하기 전에이 메서드를 호출 합니다.  
  
```  
virtual void PreLoadState();
```  
  
### <a name="remarks"></a>주의  
 응용 프로그램 상태를 로드 하는 프레임 워크 직전 모든 처리를 수행 하려는 경우이 메서드를 재정의 합니다.  
  
##  <a name="a-namepresavestatea--cwinappexpresavestate"></a><a name="presavestate"></a>CWinAppEx::PreSaveState  
 응용 프로그램 상태를 저장 하기 바로 전에이 메서드를 호출 하는 프레임 워크입니다.  
  
```  
virtual void PreSaveState();
```  
  
### <a name="remarks"></a>주의  
 응용 프로그램 상태를 저장 하는 프레임 워크 직전 모든 처리를 수행 하려는 경우이 메서드를 재정의 합니다.  
  
##  <a name="a-namereloadwindowplacementa--cwinappexreloadwindowplacement"></a><a name="reloadwindowplacement"></a>CWinAppEx::ReloadWindowPlacement  
 레지스트리에서 창의 위치와 크기를 다시 로드합니다.  
  
```  
virtual BOOL ReloadWindowPlacement(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pFrame`  
 프레임 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 0이 아닌 실패 또는 여기 부하가 로드할 데이터가 없는 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 함수를 사용 하 여 [CWinAppEx::StoreWindowPlacement](#storewindowplacement) 크기와 창의 위치는 레지스트리에 쓸 수 있습니다.  
  
##  <a name="a-namesavecustomstatea--cwinappexsavecustomstate"></a><a name="savecustomstate"></a>CWinAppEx::SaveCustomState  
 프레임 워크를 레지스트리에 응용 프로그램의 상태를 저장 한 후이 메서드를 호출 합니다.  
  
```  
virtual void SaveCustomState();
```  
  
### <a name="remarks"></a>주의  
 응용 프로그램 상태를 레지스트리에 저장 한 후 모든 처리를 수행 하려는 경우이 메서드를 재정의 합니다. 기본적으로이 메서드는 아무 작업도 수행 합니다.  
  
##  <a name="a-namesavestatea--cwinappexsavestate"></a><a name="savestate"></a>CWinAppEx::SaveState  
 Windows 레지스트리에 응용 프로그램 상태를 씁니다.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszSectionName = NULL,  
    CFrameImpl* pFrameImpl = NULL);

 
BOOL SaveState(
    CMDIFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL SaveState(
    CFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL SaveState(
    COleIPFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszSectionName`  
 레지스트리 키의 상대 경로 포함 하는 문자열입니다.  
  
 [in] `pFrameImpl`  
 에 대 한 포인터는 `CFrameImpl` 개체입니다. 이 프레임은 Windows 레지스트리에 저장 됩니다.  
  
 [in] `pFrame`  
 프레임 창 개체에 대 한 포인터입니다. 이 프레임은 Windows 레지스트리에 저장 됩니다.  
  
### <a name="return-value"></a>반환 값  
 `True`성공 하면 `false` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 이 메서드는 제공 된 프레임 창에 대 한 상태 정보 및 응용 프로그램 상태를 저장 합니다. 프레임 창 정보를 제공 하지 않으면 메서드는 응용 프로그램 상태를 저장 합니다. 상태를 포함 하는 응용 프로그램 정보는 [CMouseManager 클래스](../../mfc/reference/cmousemanager-class.md), [CContextMenuManager 클래스](../../mfc/reference/ccontextmenumanager-class.md), [CKeyboardManager 클래스](../../mfc/reference/ckeyboardmanager-class.md), 및 [CUserToolsManager 클래스](../../mfc/reference/cusertoolsmanager-class.md)합니다.  
  
 `lpszSectionName` 매개 변수는 레지스트리 항목에 대 한 절대 경로가 아닙니다. 것은 응용 프로그램에 대 한 기본 레지스트리 키의 끝에 추가 되는 상대 경로입니다. 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase) 각각.  
  
##  <a name="a-namesetregistrybasea--cwinappexsetregistrybase"></a><a name="setregistrybase"></a>CWinAppEx::SetRegistryBase  
 응용 프로그램에 대 한 기본 레지스트리 경로 설정 합니다.  
  
```  
LPCTSTR SetRegistryBase(LPCTSTR lpszSectionName = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszSectionName`  
 레지스트리 키의 경로 포함 하는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 기본 레지스트리 위치 경로 포함 하는 문자열입니다.  
  
### <a name="remarks"></a>주의  
 모든 메서드는 [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md) 레지스트리 시작 기본 위치에 액세스 하는 합니다. 이 메서드를 사용 하 여 해당 기본 레지스트리 위치를 변경 합니다. 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 기본 레지스트리 위치를 검색할 수 있습니다.  
  
##  <a name="a-nameshowpopupmenua--cwinappexshowpopupmenu"></a><a name="showpopupmenu"></a>CWinAppEx::ShowPopupMenu  
 팝업 메뉴를 표시합니다.  
  
```  
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,  
    const CPoint& point,  
    CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiMenuResId`  
 메뉴 리소스 id입니다.  
  
 [in] `point`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 화면 좌표에서 메뉴의 위치를 지정 하는 합니다.  
  
 [in] `pWnd`  
 팝업 메뉴를 소유 하는 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 팝업 메뉴 성공적으로 표시 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 연결 된 메뉴 표시 `uiMenuResId`합니다.  
  
 팝업 메뉴를 지원 하기 위해 있어야는 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) 개체입니다. 초기화 되지 있을 경우는 `CContextMenuManager` 개체 `ShowPopupMenu` 실패 합니다.  
  
##  <a name="a-namestorewindowplacementa--cwinappexstorewindowplacement"></a><a name="storewindowplacement"></a>CWinAppEx::StoreWindowPlacement  
 프레임 워크의 주 프레임 창 위치와 크기를 레지스트리에 쓸에 의해 호출 됩니다.  
  
```  
virtual BOOL StoreWindowPlacement(
    const CRect& rectNormalPosition,  
    int nFlags,  
    int nShowCmd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nFlags`  
 최소화 된 창 및 운영 체제는 최소화 된 창을 복원 된 창 간에 전환 하는 방법의 위치를 제어 하는 플래그입니다.  
  
 [in] `nShowCmd`  
 창의 표시 상태를 지정 하는 정수입니다. 가능한 값에 대 한 자세한 내용은 참조 [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow)합니다.  
  
 [in] `rectNormalPosition`  
 복원 된 상태에 있을 때 주 프레임 창의 좌표를 포함 하는 사각형입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로 MFC 응용 프로그램 종료 되기 전에 주 프레임 창의 상태와 위치에 자동으로 저장합니다. 이 정보는 응용 프로그램에 대 한 기본 레지스트리 위치에 WindowPlacement 키 아래 Windows 레지스트리에 저장 됩니다. 응용 프로그램의 기본 레지스트리 위치에 대 한 자세한 내용은 참조 [CWinAppEx::GetRegistryBase](#getregistrybase)합니다.  
  
 주 프레임 창에 대 한 추가 정보를 저장 하려는 경우이 메서드를 재정의 합니다.  
  
##  <a name="a-namewritebinarya--cwinappexwritebinary"></a><a name="writebinary"></a>CWinAppEx::WriteBinary  
 이진 데이터를 레지스트리에 씁니다.  
  
```  
BOOL WriteBinary(
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszEntry`  
 레지스트리 키의 이름을 포함 하는 문자열입니다.  
  
 [in] `pData`  
 저장할 데이터입니다.  
  
 [in] `nBytes`  
 크기가 `pData` (바이트)에서입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드는 성공 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 `lpszEntry` 매개 변수는 응용 프로그램에 대 한 기본 레지스트리 키 아래에 있는 레지스트리 항목의 이름입니다. 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase) 각각.  
  
 지정 된 키의 경우 `lpszEntry` 가 없으면이 메서드를 만듭니다.  
  
##  <a name="a-namewriteinta--cwinappexwriteint"></a><a name="writeint"></a>CWinAppEx::WriteInt  
 레지스트리를 숫자 데이터를 씁니다.  
  
```  
BOOL WriteInt(
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszEntry`  
 레지스트리 키의 이름을 포함 하는 문자열입니다.  
  
 [in] `nValue`  
 저장할 데이터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드는 성공 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 `lpszEntry` 매개 변수는 응용 프로그램에 대 한 기본 레지스트리 키 아래에 레지스트리 항목의 이름입니다. 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase) 각각.  
  
 지정 된 키의 경우 `lpszEntry` 가 없으면이 메서드를 만듭니다.  
  
##  <a name="a-namewriteobjecta--cwinappexwriteobject"></a><a name="writeobject"></a>CWinAppEx::WriteObject  
 파생 된 데이터를 씁니다는 [CObject 클래스](../../mfc/reference/cobject-class.md) 레지스트리에 있습니다.  
  
```  
BOOL WriteObject(
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszEntry`  
 설정할 값을 포함 하는 문자열입니다.  
  
 [in] `obj`  
 에 대 한 참조 `CObject` 메서드를 저장할 데이터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드는 성공 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 작성 된 `obj` 기본 레지스트리 키에서 지정된 된 값으로는 데이터입니다. 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 현재 레지스트리 키를 확인 하려면.  
  
##  <a name="a-namewritesectionbinarya--cwinappexwritesectionbinary"></a><a name="writesectionbinary"></a>CWinAppEx::WriteSectionBinary  
 이진 데이터를 레지스트리에서 값을 씁니다.  
  
```  
BOOL WriteSectionBinary(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszSubSection`  
 레지스트리 키의 이름을 포함 하는 문자열  
  
 [in] `lpszEntry`  
 설정할 값을 포함 하는 문자열입니다.  
  
 [in] `pData`  
 데이터를 레지스트리에 쓸입니다.  
  
 [in] `nBytes`  
 크기가 `pData` (바이트)에서입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드는 성공 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 `lpszSubSection` 매개 변수는 레지스트리 항목에 대 한 절대 경로가 아닙니다. 것은 응용 프로그램에 대 한 기본 레지스트리 키의 끝에 추가 되는 상대 경로입니다. 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase) 각각.  
  
 지정 된 키의 경우 `lpszEntry` 가 없으면이 메서드를 만듭니다.  
  
##  <a name="a-namewritesectioninta--cwinappexwritesectionint"></a><a name="writesectionint"></a>CWinAppEx::WriteSectionInt  
 레지스트리를 숫자 데이터를 씁니다.  
  
```  
BOOL WriteSectionInt(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszSubSection`  
 레지스트리 키의 상대 경로 포함 하는 문자열입니다.  
  
 [in] `lpszEntry`  
 설정할 값을 포함 하는 문자열입니다.  
  
 [in] `nValue`  
 데이터를 레지스트리에 쓸입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드는 성공 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 `lpszSubSection` 매개 변수가 레지스트리 항목에 대 한 절대 경로 않습니다. 것은 응용 프로그램에 대 한 기본 레지스트리 키에 추가 되는 상대 경로입니다. 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase) 각각.  
  
 지정 된 키의 경우 `lpszEntry` 가 없으면이 메서드를 만듭니다.  
  
##  <a name="a-namewritesectionobjecta--cwinappexwritesectionobject"></a><a name="writesectionobject"></a>CWinAppEx::WriteSectionObject  
 파생 된 데이터를 씁니다는 [CObject 클래스](../../mfc/reference/cobject-class.md) 을 특정 레지스트리 값입니다.  
  
```  
BOOL WriteSectionObject(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszSubSection`  
 레지스트리 키의 이름을 포함 하는 문자열입니다.  
  
 [in] `lpszEntry`  
 설정할 값의 이름을 포함 하는 문자열입니다.  
  
 [in] `obj`  
 저장할 데이터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드는 성공 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 `lpszSubSection` 매개 변수가 레지스트리 항목에 대 한 절대 경로 않습니다. 것은 응용 프로그램에 대 한 기본 레지스트리 키의 끝에 추가 되는 상대 경로입니다. 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase)각각.  
  
 값은 지정 하는 경우 `lpszEntry` 로 지정 된 레지스트리 키가 없습니다 `lpszSubSection`,이 메서드는 해당 값을 만듭니다.  
  
##  <a name="a-namewritesectionstringa--cwinappexwritesectionstring"></a><a name="writesectionstring"></a>CWinAppEx::WriteSectionString  
 문자열 데이터의 레지스트리 값을 씁니다.  
  
```  
BOOL WriteSectionString(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszSubSection`  
 레지스트리 키의 이름을 포함 하는 문자열입니다.  
  
 [in] `lpszEntry`  
 설정할 값을 포함 하는 문자열입니다.  
  
 [in] `lpszValue`  
 문자열 데이터를 레지스트리에 쓸입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드는 성공 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 `lpszSubSection` 매개 변수가 레지스트리 항목에 대 한 절대 경로 않습니다. 것은 응용 프로그램에 대 한 기본 레지스트리 키의 끝에 추가 되는 상대 경로입니다. 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase)각각.  
  
 값은 지정 하는 경우 `lpszEntry` 에서 존재 하지 않는 `lpszSubSection`,이 메서드를 만듭니다.  
  
##  <a name="a-namewritestringa--cwinappexwritestring"></a><a name="writestring"></a>CWinAppEx::WriteString  
 문자열 데이터를 레지스트리에 씁니다.  
  
```  
BOOL WriteString(
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszEntry`  
 레지스트리 키의 이름을 포함 하는 문자열입니다.  
  
 [in] `lpszValue`  
 저장할 데이터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드는 성공 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 `lpszEntry` 매개 변수는 응용 프로그램에 대 한 기본 레지스트리 키 아래에 레지스트리 항목의 이름입니다. 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](#getregistrybase) 및 [CWinAppEx::SetRegistryBase](#setregistrybase) 각각.  
  
 지정 된 키의 경우 `lspzEntry` 가 없으면이 메서드를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinApp 클래스](../../mfc/reference/cwinapp-class.md)   
 [CMouseManager 클래스](../../mfc/reference/cmousemanager-class.md)   
 [CContextMenuManager 클래스](../../mfc/reference/ccontextmenumanager-class.md)   
 [CKeyboardManager 클래스](../../mfc/reference/ckeyboardmanager-class.md)   
 [CUserToolsManager 클래스](../../mfc/reference/cusertoolsmanager-class.md)

