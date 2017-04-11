---
title: "CFrameWnd 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFrameWnd
- AFXWIN/CFrameWnd
- AFXWIN/CFrameWnd::CFrameWnd
- AFXWIN/CFrameWnd::ActivateFrame
- AFXWIN/CFrameWnd::BeginModalState
- AFXWIN/CFrameWnd::Create
- AFXWIN/CFrameWnd::CreateView
- AFXWIN/CFrameWnd::DockControlBar
- AFXWIN/CFrameWnd::EnableDocking
- AFXWIN/CFrameWnd::EndModalState
- AFXWIN/CFrameWnd::FloatControlBar
- AFXWIN/CFrameWnd::GetActiveDocument
- AFXWIN/CFrameWnd::GetActiveFrame
- AFXWIN/CFrameWnd::GetActiveView
- AFXWIN/CFrameWnd::GetControlBar
- AFXWIN/CFrameWnd::GetDockState
- AFXWIN/CFrameWnd::GetMenuBarState
- AFXWIN/CFrameWnd::GetMenuBarVisibility
- AFXWIN/CFrameWnd::GetMessageBar
- AFXWIN/CFrameWnd::GetMessageString
- AFXWIN/CFrameWnd::GetTitle
- AFXWIN/CFrameWnd::InitialUpdateFrame
- AFXWIN/CFrameWnd::InModalState
- AFXWIN/CFrameWnd::IsTracking
- AFXWIN/CFrameWnd::LoadAccelTable
- AFXWIN/CFrameWnd::LoadBarState
- AFXWIN/CFrameWnd::LoadFrame
- AFXWIN/CFrameWnd::NegotiateBorderSpace
- AFXWIN/CFrameWnd::OnBarCheck
- AFXWIN/CFrameWnd::OnContextHelp
- AFXWIN/CFrameWnd::OnSetPreviewMode
- AFXWIN/CFrameWnd::OnUpdateControlBarMenu
- AFXWIN/CFrameWnd::RecalcLayout
- AFXWIN/CFrameWnd::SaveBarState
- AFXWIN/CFrameWnd::SetActivePreviewView
- AFXWIN/CFrameWnd::SetActiveView
- AFXWIN/CFrameWnd::SetDockState
- AFXWIN/CFrameWnd::SetMenuBarState
- AFXWIN/CFrameWnd::SetMenuBarVisibility
- AFXWIN/CFrameWnd::SetMessageText
- AFXWIN/CFrameWnd::SetProgressBarPosition
- AFXWIN/CFrameWnd::SetProgressBarRange
- AFXWIN/CFrameWnd::SetProgressBarState
- AFXWIN/CFrameWnd::SetTaskbarOverlayIcon
- AFXWIN/CFrameWnd::SetTitle
- AFXWIN/CFrameWnd::ShowControlBar
- AFXWIN/CFrameWnd::ShowOwnedWindows
- AFXWIN/CFrameWnd::OnCreateClient
- AFXWIN/CFrameWnd::OnHideMenuBar
- AFXWIN/CFrameWnd::OnShowMenuBar
- AFXWIN/CFrameWnd::m_bAutoMenuEnable
- AFXWIN/CFrameWnd::rectDefault
dev_langs:
- C++
helpviewer_keywords:
- frame window classes, base class
- single document interface (SDI), frame windows
- frame windows, creating
- CFrameWnd class
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 06becdd593028e02d45ed68fb8fa5687e1e2dbd1
ms.lasthandoff: 04/04/2017

---
# <a name="cframewnd-class"></a>CFrameWnd 클래스
창 관리를 위한 멤버와 함께 겹쳐진 Windows SDI(단일 문서 인터페이스) 또는 팝업 프레임 창의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CFrameWnd : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CFrameWnd::CFrameWnd](#cframewnd)|`CFrameWnd` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFrameWnd::ActivateFrame](#activateframe)|사용자에 게 표시 되 고 사용할 수 있는 프레임을 만듭니다.|  
|[CFrameWnd::BeginModalState](#beginmodalstate)|프레임 창을 모달 설정합니다.|  
|[CFrameWnd::Create](#create)|호출을 생성 및 초기화와 연결 된 Windows 프레임 창을 `CFrameWnd` 개체입니다.|  
|[CFrameWnd::CreateView](#createview)|파생 되지 않은 프레임에 뷰를 만듭니다 `CView`합니다.|  
|[CFrameWnd::DockControlBar](#dockcontrolbar)|컨트롤 막대를 도킹합니다.|  
|[CFrameWnd::EnableDocking](#enabledocking)|도킹 컨트롤 막대를 허용 합니다.|  
|[CFrameWnd::EndModalState](#endmodalstate)|프레임 창의 모달 상태를 끝냅니다. 에서는 모든 사용 하지 않도록 설정 하는 windows의 `BeginModalState`합니다.|  
|[CFrameWnd::FloatControlBar](#floatcontrolbar)|컨트롤 막대를 배치 합니다.|  
|[CFrameWnd::GetActiveDocument](#getactivedocument)|활성 반환 **CDocument** 개체입니다.|  
|[CFrameWnd::GetActiveFrame](#getactiveframe)|활성 반환 `CFrameWnd` 개체입니다.|  
|[CFrameWnd::GetActiveView](#getactiveview)|활성 반환 `CView` 개체입니다.|  
|[CFrameWnd::GetControlBar](#getcontrolbar)|컨트롤 막대를 검색합니다.|  
|[CFrameWnd::GetDockState](#getdockstate)|프레임 창의 도킹 상태를 검색합니다.|  
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|현재 MFC 응용 프로그램에서 메뉴의 표시 상태를 검색합니다.|  
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|현재 MFC 응용 프로그램에서 메뉴의 기본 동작은 숨겨지거나 표시 여부를 나타냅니다.|  
|[CFrameWnd::GetMessageBar](#getmessagebar)|프레임 창에 속하는 막대 상태에 대 한 포인터를 반환 합니다.|  
|[CFrameWnd::GetMessageString](#getmessagestring)|검색 메시지에 해당 하는 명령 id입니다.|  
|[CFrameWnd::GetTitle](#gettitle)|관련된 컨트롤 막대의 제목을 검색합니다.|  
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|로 인해는 `OnInitialUpdate` 멤버 함수를 호출 하려면 프레임 창에서 모든 보기에 속하는 합니다.|  
|[CFrameWnd::InModalState](#inmodalstate)|프레임 창을 모달 상태에서 인지 여부를 나타내는 값을 반환 합니다.|  
|[CFrameWnd::IsTracking](#istracking)|분할 막대는 현재 이동 중인 경우를 결정 합니다.|  
|[CFrameWnd::LoadAccelTable](#loadacceltable)|액셀러레이터 키 테이블 로드를 호출 합니다.|  
|[CFrameWnd::LoadBarState](#loadbarstate)|제어 막대 설정을 복원 하는 호출 합니다.|  
|[CFrameWnd::LoadFrame](#loadframe)|동적으로 만드는 프레임 창에서 리소스 정보를 호출 합니다.|  
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|프레임 창의 테두리 공간을 협상합니다.|  
|[CFrameWnd::OnBarCheck](#onbarcheck)|지정 된 컨트롤 막대에는 동작이 수행 될 때마다 호출 됩니다.|  
|[CFrameWnd::OnContextHelp](#oncontexthelp)|내부 항목에 대 한 SHIFT + F1 도움말을 처리합니다.|  
|[CFrameWnd::OnSetPreviewMode](#onsetpreviewmode)|내부 / 외부로 인쇄 미리 보기 모드 응용 프로그램의 주 프레임 창을 설정합니다.|  
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|연결 된 메뉴를 업데이트할 때 프레임 워크에서 호출 합니다.|  
|[CFrameWnd::RecalcLayout](#recalclayout)|컨트롤 막대의 위치를 변경 하는 `CFrameWnd` 개체입니다.|  
|[CFrameWnd::SaveBarState](#savebarstate)|컨트롤 막대 설정을 저장 하려면 호출 합니다.|  
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|지정 된 뷰 풍부한 미리 보기에 대 한 활성 뷰를 지정 합니다.|  
|[CFrameWnd::SetActiveView](#setactiveview)|활성 설정 `CView` 개체입니다.|  
|[CFrameWnd::SetDockState](#setdockstate)|주 창에 프레임 창을 도킹 하려면 호출 합니다.|  
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|숨겨진 또는 표시 된 현재 MFC 응용 프로그램에서 메뉴의 표시 상태를 설정합니다.|  
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|숨겨지거나 표시 되도록 현재 MFC 응용 프로그램에서 메뉴의 기본 동작을 설정 합니다.|  
|[CFrameWnd::SetMessageText](#setmessagetext)|표준 상태 표시줄의 텍스트를 설정 합니다.|  
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|작업 표시줄에 표시 되는 Windows 7 진행률 표시줄에 대 한 현재 위치를 설정 합니다.|  
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|작업 표시줄에 표시 되는 Windows 7 진행률 표시줄에 대 한 범위를 설정 합니다.|  
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|유형 및 작업 표시줄 단추에 표시 되는 진행률 표시기의 상태를 설정 합니다.|  
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|오버로드됨. 사용자에 게 알림을 또는 응용 프로그램 상태를 나타내는 작업 표시줄 단추에 오버레이 적용 합니다.|  
|[CFrameWnd::SetTitle](#settitle)|관련된 컨트롤 막대의 제목을 설정합니다.|  
|[CFrameWnd::ShowControlBar](#showcontrolbar)|컨트롤 막대를 표시 하도록 호출 합니다.|  
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|하위 항목인 모든 창을 표시는 `CFrameWnd` 개체입니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFrameWnd::OnCreateClient](#oncreateclient)|프레임에 대 한 클라이언트 창을 만듭니다.|  
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|현재 MFC 응용 프로그램에서 메뉴 숨겨져 전에 호출 됩니다.|  
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|현재 MFC 응용 프로그램에서 메뉴가 표시 되기 전에 호출 됩니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|자동 활성화 컨트롤과 메뉴 항목에 대 한 기능을 사용 하지 않도록 설정 합니다.|  
|[CFrameWnd::rectDefault](#rectdefault)|이 정적 전달할 `CRect` 만들 때 매개 변수로 `CFrameWnd` Windows 창의 초기 크기와 위치를 선택 하도록 허용 하는 개체입니다.|  
  
## <a name="remarks"></a>설명  
 응용 프로그램에 대 한 유용한 프레임 창을 만들기 위해에서 클래스를 파생 `CFrameWnd`합니다. 응용 프로그램에 관련 데이터를 저장 하 고 파생된 클래스에 멤버 변수를 추가 합니다. 파생 클래스에서 메시지 처리기 멤버 함수 및 메시지 맵을 구현하여 메시지가 창에 전달될 때 수행되는 작업을 지정합니다.  
  
 프레임 창 생성 하는 방법은 세 가지가 있습니다.  
  
-   사용 하 여이 직접 생성할 [만들기](#create)합니다.  
  
-   사용 하 여이 직접 생성할 [LoadFrame](#loadframe)합니다.  
  
-   직접 생성 하지 문서 서식 파일을 사용 하 여 합니다.  
  
 중 하나를 호출 하기 전에 **만들기** 또는 `LoadFrame`, c + +를 사용 하 여 힙에 프레임 창 개체를 생성 해야 **새** 연산자입니다. 호출 하기 전에 **만들기**를 사용 하는 창 클래스를 등록할 수도 있습니다는 [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) 프레임에 대 한 아이콘 및 클래스 스타일을 설정 하려면 전역 함수입니다.  
  
 사용 하 여는 **만들기** 같이 즉시 인수 프레임의 생성 매개 변수를 전달 하는 멤버 함수입니다.  
  
 `LoadFrame`보다 적은 인수를 사용 해야 **만들기**, 대신 프레임의 캡션, 아이콘, 액셀러레이터 키 테이블 및 메뉴를 포함 하 여 리소스에서 대부분의 해당 기본 값을 검색 합니다. 액세스할 수 있도록 `LoadFrame`, 이러한 모든 리소스에는 동일한 리소스 ID를 사용 해야 합니다. (예를 들어 **IDR_MAINFRAME**).  
  
 경우는 `CFrameWnd` 만들어질 하지 직접은 프로그래머가 직접 대신 프레임 워크에서 보기 및 문서 개체에 포함 되어 있습니다. `CDocTemplate` 프레임의 만들기, 포함 하는 뷰를 만들고 적절 한 문서에 뷰 연결 개체를 조정 합니다. 매개 변수는 `CDocTemplate` 생성자 지정는 `CRuntimeClass` 세 개의 클래스 (문서, 프레임 및 보기)를 포함 합니다. A `CRuntimeClass` 개체를 동적으로 만드는 새 프레임 (예를 들어 사용 하 여 새 파일 명령이 나 여러 문서 MDI (인터페이스) 새 창 명령을)는 사용자가 지정한 경우 프레임 워크에서 사용 됩니다.  
  
 프레임 창 클래스에서 파생 된 `CFrameWnd` 로 선언 되어야 합니다 `DECLARE_DYNCREATE` 하려면 위의 `RUNTIME_CLASS` 제대로 작동 하는 메커니즘입니다.  
  
 A `CFrameWnd` 일반 응용 프로그램에서 Windows에 대 한 주 창의 다음 기능을 수행 하려면 기본 구현이 포함 되어 있습니다.  
  
-   A `CFrameWnd` 프레임 창이 Windows 활성 창 또는 현재 입력된 포커스와 무관 하는 현재 활성 보기의 추적입니다. 현재 보기 프레임, 다시 활성화 하는 경우 호출 하 여 알려집니다 `CView::OnActivateView`합니다.  
  
-   명령 메시지과 비롯 하 여 처리 하는 많은 일반적인 프레임 알림 메시지를는 `OnSetFocus`, `OnHScroll`, 및 `OnVScroll` 의 기능 `CWnd`에서 위임 되며는 `CFrameWnd` 현재 활성 보기 프레임 창.  
  
-   현재 활성 보기 (또는 MDI 프레임의 경우 현재 활성 MDI 자식 프레임 창) 프레임 창의 캡션을 확인할 수 있습니다. 이 기능은 해제 하 여 해제할 수 있습니다는 **FWS_ADDTOTITLE** 프레임 창의 스타일 비트입니다.  
  
-   A `CFrameWnd` 프레임 창은 컨트롤 막대, 뷰 및 프레임 창의 클라이언트 영역 내의 다른 자식 창의 위치를 관리 합니다. 프레임 창 도구 모음 및 다른 컨트롤 막대 단추 유휴 시간을 업데이트 합니다. 또한 수행 합니다. A `CFrameWnd` 프레임 창에는 역시 켜고 도구 모음 및 상태 표시줄 설정/해제에 대 한 명령의 기본 구현입니다.  
  
-   A `CFrameWnd` 프레임 창은 주 메뉴 모음을 관리 합니다. 프레임 창을 사용 하 여 팝업 메뉴가 표시 되 면는 **UPDATE_COMMAND_UI** 메뉴 항목을 활성화할지, 비활성화 또는 확인을 결정 하기 위한 메커니즘입니다. 사용자가 메뉴 항목을 선택 하면 프레임 창 해당 명령에 대 한 메시지 문자열을 사용 상태 표시줄을 업데이트 합니다.  
  
-   A `CFrameWnd` 프레임 창에 키보드 액셀러레이터 키를 자동으로 변환 하는 선택적 액셀러레이터 키 테이블입니다.  
  
-   A `CFrameWnd` 프레임 창에 사용 하 여 설정 된 선택적 도움말 ID `LoadFrame` 상황에 맞는 도움말에 사용 되는 합니다. 프레임 창 상황에 맞는 도움말 (SHIFT + f 1) 및 인쇄 미리 보기 모드와 같은 세미 모달 상태의 주요 orchestrator입니다.  
  
-   A `CFrameWnd` 프레임 창이 프레임 창에 끌어다 놓을 파일 관리자에서 파일이 열립니다. 프레임 창 되거나 사용자가 파일 관리자에서 데이터 파일을 열 때 발생 하는 동적 데이터 DDE (교환) 열기 요청에 응답 파일 확장명은 등록 되 고 응용 프로그램 연결을 하는 경우는 **ShellExecute** Windows 함수를 호출 합니다.  
  
-   기본 응용 프로그램 창에 프레임 창을 경우 (즉, `CWinThread::m_pMainWnd`), 사용자가 응용 프로그램을 닫으면 수정 된 문서를 모두 저장 하 라는 메시지를 프레임 창 (에 대 한 `OnClose` 및 `OnQueryEndSession`).  
  
-   기본 응용 프로그램 창 프레임 창의 사용 하는 경우 프레임 창은 WinHelp를 실행 하기 위한 컨텍스트로 사용 됩니다. WINHELP 프레임 창을 닫아 종료 합니다. 이 응용 프로그램에 대 한 도움말에 대 한 시작 된 exe를 실행 합니다.  
  
 C + +를 사용 하지 마십시오 **삭제** 연산자를 프레임 창을 삭제 합니다. 대신 `CWnd::DestroyWindow` 를 사용하세요. `CFrameWnd` 구현의 `PostNcDestroy` 창이 소멸 될 때에 c + + 개체를 삭제 합니다. 사용자 프레임 창에 기본값을 닫을 때 `OnClose` 처리기를 호출 하는 `DestroyWindow`합니다.  
  
 대 한 자세한 내용은 `CFrameWnd`, 참조 [프레임 창](../../mfc/frame-windows.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CFrameWnd`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="activateframe"></a>CFrameWnd::ActivateFrame  
 활성화 하 고 표시 되 고 사용할 수 있는 사용자에 게 되도록 프레임 창을 복원 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual void ActivateFrame(int nCmdShow = -1);
```  
  
### <a name="parameters"></a>매개 변수  
 `nCmdShow`  
 에 전달할 매개 변수 지정 [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow)합니다. 기본적으로 프레임 표시 하 고 올바르게 복원 됩니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 일반적으로 DDE 또는 OLE, 프레임 창 또는 해당 내용을 사용자에 게 표시할 수 있습니다 다른 이벤트와 같은 비 사용자 인터페이스 이벤트가 발생 한 후 호출 됩니다.  
  
 기본 구현은 활성화 프레임 및 Z 순서의 맨 위쪽에 표시 및, 필요한 경우 응용 프로그램의 주 프레임 창에 대 한 동일한 단계를 수행 합니다.  
  
 프레임을 활성화 하는 방법을 변경 하려면이 멤버 함수를 재정의 합니다. 예를 들어 MDI 자식 창이 최대화를 강제할 수 있습니다. 적절 한 기능을 추가한 다음 명시적으로 기본 클래스 버전을 호출 `nCmdShow`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing # 1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]  
  
##  <a name="beginmodalstate"></a>CFrameWnd::BeginModalState  
 프레임 창을 모달로 만들기 위해 이 멤버 함수를 호출합니다.  
  
```  
virtual void BeginModalState();
```  
  
##  <a name="cframewnd"></a>CFrameWnd::CFrameWnd  
 생성 된 `CFrameWnd` 개체, 하지만 표시 프레임 창을 만들지 않습니다.  
  
```  
CFrameWnd();
```  
  
### <a name="remarks"></a>주의  
 호출 **만들기** 표시 창을 만들 수 있습니다.  
  
##  <a name="create"></a>CFrameWnd::Create  
 호출을 생성 및 초기화와 연결 된 Windows 프레임 창을 `CFrameWnd` 개체입니다.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle = WS_OVERLAPPEDWINDOW,  
    const RECT& rect = rectDefault,  
    CWnd* pParentWnd = NULL,  
    LPCTSTR lpszMenuName = NULL,  
    DWORD dwExStyle = 0,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszClassName`  
 Windows 클래스의 이름을 지정 하는 null로 끝나는 문자열을 가리킵니다. 클래스 이름에 등록 된 모든 이름일 수 있습니다는 `AfxRegisterWndClass` 전역 함수 또는 **RegisterClass** Windows 함수입니다. 경우 **NULL**, 미리 정의 된 기본값을 사용 하 여 `CFrameWnd` 특성입니다.  
  
 `lpszWindowName`  
 창 이름을 나타내는 null로 끝나는 문자열을 가리킵니다. 제목 표시줄에 대 한 텍스트로 사용합니다.  
  
 `dwStyle`  
 창을 지정 [스타일](../../mfc/reference/window-styles.md) 특성입니다. 포함 된 **FWS_ADDTOTITLE** 창에에서 표시 되며 문서의 이름을 자동으로 표시 하려면 제목 표시줄을 원하는 경우 스타일입니다.  
  
 `rect`  
 크기와 창의 위치를 지정합니다. `rectDefault` 크기와 새 창의 위치를 지정 하려면 Windows를 허용 하는 값입니다.  
  
 `pParentWnd`  
 이 프레임 창의 부모 창을 지정합니다. 이 매개 변수 여야 **NULL** 최상위 프레임 창에 대 한 합니다.  
  
 *lpszMenuName*  
 창에서 사용 되는 메뉴 리소스의 이름을 식별 합니다. 사용 하 여 **MAKEINTRESOURCE** 메뉴에는 정수 ID 문자열 대신 합니다. 이 매개 변수 수 **NULL**합니다.  
  
 `dwExStyle`  
 확장 창 [스타일](../../mfc/reference/extended-window-styles.md) 특성입니다.  
  
 `pContext`  
 에 대 한 포인터를 지정 된 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) 구조입니다. 이 매개 변수 수 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 초기화에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 생성 된 `CFrameWnd` 두 단계를 수행에서 하는 개체입니다. 첫째, 생성 된 생성자를 호출는 `CFrameWnd` 개체를 호출 **만들기**, Windows 프레임 창을 만들고에 연결는 `CFrameWnd` 개체입니다. **만들** 창 클래스 이름 및 창 이름을 초기화 하 고 해당 스타일, 부모 및 연결 된 메뉴에 대 한 기본값을 등록 합니다.  
  
 사용 하 여 `LoadFrame` 대신 **만들기** 프레임 창은 해당 인수를 지정 하는 대신 리소스에서 로드할 수 있습니다.  
  
##  <a name="createview"></a>CFrameWnd::CreateView  
 호출 `CreateView` 프레임 내에서 보기를 만듭니다.  
  
```  
CWnd* CreateView(
    CCreateContext* pContext,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>매개 변수  
 `pContext`  
 보기 및 문서 유형을 지정합니다.  
  
 `nID`  
 보기의 ID.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CWnd` 성공 되지 않으면 개체 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 하지 않은 "뷰"를 만들려면이 멤버 함수를 사용 하 여 `CView`-프레임 내에서 파생 됩니다. 호출한 후 `CreateView`, 하 여 이러한 작업을 자동으로 수행 되지 않으면 수동으로 활성 뷰를 설정 하 고 표시 되도록 설정 해야 합니다 `CreateView`합니다.  
  
##  <a name="dockcontrolbar"></a>CFrameWnd::DockControlBar  
 프레임 창으로 도킹 컨트롤 막대를 하면 됩니다.  
  
```  
void DockControlBar(
    CControlBar* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pBar`  
 도킹 컨트롤 막대를 가리킵니다.  
  
 `nDockBarID`  
 프레임 창으로 도킹 고려해의 면을 결정 합니다. 0 또는 하나 이상의 다음 수 있습니다.  
  
- `AFX_IDW_DOCKBAR_TOP`프레임 창의 위쪽에 도킹 합니다.  
  
- **AFX_IDW_DOCKBAR_BOTTOM** 프레임 창의 아래쪽에 도킹 합니다.  
  
- `AFX_IDW_DOCKBAR_LEFT`프레임 창 왼쪽에 도킹 합니다.  
  
- `AFX_IDW_DOCKBAR_RIGHT`프레임 창의 오른쪽에 도킹 합니다.  
  
 0 인 경우, 컨트롤 막대 대상 프레임 창에서 도킹 가능한 모든 면에 도킹 될 수 있습니다.  
  
 `lpRect`  
 컨트롤 막대 대상 프레임 창의 비클라이언트 영역에 도킹 될 위치를 화면 좌표로 결정 합니다.  
  
### <a name="remarks"></a>설명  
 컨트롤 막대 둘 다에 대 한 호출에 지정 된 프레임 창의 어느 한쪽에 도킹 될 [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking) 및 [CFrameWnd::EnableDocking](#enabledocking)합니다. 선택한 측에 의해 결정 됩니다 `nDockBarID`합니다.  
  
##  <a name="enabledocking"></a>CFrameWnd::EnableDocking  
 프레임 창에서 도킹 가능한 컨트롤 막대를 사용 하도록 설정 하려면이 함수를 호출 합니다.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDockStyle`  
 프레임 창의 면 도킹 컨트롤 막대에 대 한 사이트로 사용 될 수를 지정 합니다. 다음 중 하나 이상을 수 있습니다.  
  
- `CBRS_ALIGN_TOP`클라이언트 영역의 위쪽에 도킹 수 있습니다.  
  
- `CBRS_ALIGN_BOTTOM`클라이언트 영역의 맨 아래에 도킹 수 있습니다.  
  
- `CBRS_ALIGN_LEFT`클라이언트 영역의 왼쪽에 도킹할 수 있습니다.  
  
- `CBRS_ALIGN_RIGHT`클라이언트 영역의 오른쪽에 도킹 수 있습니다.  
  
- `CBRS_ALIGN_ANY`클라이언트 영역의 한쪽에 도킹 수 있습니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 옆에 다음 순서 대로 프레임 창은 컨트롤 막대에 도킹할: 위쪽, 아래쪽, 왼쪽, 오른쪽입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CToolBar::Create](../../mfc/reference/ctoolbar-class.md#create)합니다.  
  
##  <a name="endmodalstate"></a>CFrameWnd::EndModalState  
 프레임 창을 모달에서 모덜리스로 변경하려면 이 멤버 함수를 호출합니다.  
  
```  
virtual void EndModalState();
```  
  
### <a name="remarks"></a>설명  
 `EndModalState`에서는 모든 사용 하지 않도록 설정 하는 windows의 [BeginModalState](#beginmodalstate)합니다.  
  
##  <a name="floatcontrolbar"></a>CFrameWnd::FloatControlBar  
 프레임 창으로 도킹 되지 않은에 있는 컨트롤 막대를이 함수를 호출 합니다.  
  
```  
void FloatControlBar(
    CControlBar* pBar,  
    CPoint point,  
    DWORD dwStyle = CBRS_ALIGN_TOP);
```  
  
### <a name="parameters"></a>매개 변수  
 `pBar`  
 컨트롤 막대 놓을지를 가리킵니다.  
  
 `point`  
 위치를 화면 좌표로 컨트롤 막대의 왼쪽된 위에 배치 될 위치입니다.  
  
 `dwStyle`  
 새 프레임 창 내에서 컨트롤 막대를 가로 또는 세로로 맞출지 여부를 지정 합니다. 다음 중 하나가 수 있습니다.  
  
- `CBRS_ALIGN_TOP`컨트롤 막대를 세로로 표시 합니다.  
  
- `CBRS_ALIGN_BOTTOM`컨트롤 막대를 세로로 표시 합니다.  
  
- `CBRS_ALIGN_LEFT`컨트롤 막대 가로 방향으로 진행 됩니다.  
  
- `CBRS_ALIGN_RIGHT`컨트롤 막대 가로 방향으로 진행 됩니다.  
  
 스타일을 전달 하는 가로 및 세로 방향을 지정 하는 경우 도구 모음이 됩니다 방향 가로로.  
  
### <a name="remarks"></a>주의  
 일반적으로 프로그램 실행 하 여 이전 설정을 복원 하는 경우 응용 프로그램 시작 시 수행 됩니다.  
  
 이 함수는 도킹에 사용할 수 있는 위치를 통해 컨트롤 막대를 끄는 동안 마우스 왼쪽된 단추를 해제 하 여 사용자 하면 drop 작업 때 프레임 워크에서 호출 됩니다.  
  
##  <a name="getactivedocument"></a>CFrameWnd::GetActiveDocument  
 현재에 대 한 포인터를 가져오려면이 함수를 호출 **CDocument** 현재 활성 보기에 연결 합니다.  
  
```  
virtual CDocument* GetActiveDocument();
```  
  
### <a name="return-value"></a>반환 값  
 현재에 대 한 포인터 [CDocument](../../mfc/reference/cdocument-class.md)합니다. 현재 문서가 없으면 반환 **NULL**합니다.  
  
##  <a name="getactiveframe"></a>CFrameWnd::GetActiveFrame  
 MDI 프레임 창의 다중 문서 MDI (인터페이스) 자식 창 활성에 대 한 포인터를 가져오려면이 함수를 호출 합니다.  
  
```  
virtual CFrameWnd* GetActiveFrame();
```  
  
### <a name="return-value"></a>반환 값  
 활성 MDI 자식 창에 대 한 포인터입니다. 응용 프로그램은 SDI 응용 프로그램 또는 MDI 프레임 창에는 암시적 활성 문서가 없는 경우 **이** 포인터가 반환 됩니다.  
  
### <a name="remarks"></a>주의  
 활성 MDI 자식이 없는 경우 또는 응용 프로그램은 암시적 단일 문서 인터페이스 (SDI) **이** 포인터가 반환 됩니다.  
  
##  <a name="getactiveview"></a>CFrameWnd::GetActiveView  
 프레임 창에 연결 된 현재 보기 (있는 경우)에 대 한 포인터를 가져오려면이 함수를 호출 ( `CFrameWnd`).  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재에 대 한 포인터 [CView](../../mfc/reference/cview-class.md)합니다. 현재 뷰가 없으면 반환 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 반환 **NULL** MDI 주 프레임 창에 대 한 호출 될 때 ( `CMDIFrameWnd`). MDI 주 프레임 창 MDI 응용 프로그램에서 연결 된 뷰를 사용할 수 없습니다. 대신 각 개별 자식 창 ( `CMDIChildWnd`)에 하나 이상의 연결 된 보기가 있습니다. 먼저 활성 MDI 자식 창 찾아서 다음 해당 자식 창에 대 한 활성 뷰를 검색 하 여 MDI 응용 프로그램에서 현재 보기를 얻을 수 있습니다. 활성 MDI 자식 창 함수를 호출 하 여 있습니다 `MDIGetActive` 또는 **GetActiveFrame** 다음에 표시 된 대로:  
  
 [!code-cpp[NVC_MFCWindowing # 2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]  
  
##  <a name="getcontrolbar"></a>CFrameWnd::GetControlBar  
 호출 `GetControlBar` ID와 연결 된 컨트롤 막대에 대 한 액세스 권한을 얻으려고  
  
```  
CControlBar* GetControlBar(UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `nID`  
 컨트롤 막대의 ID.  
  
### <a name="return-value"></a>반환 값  
 Id와 연결 된 컨트롤 막대에 대 한 포인터  
  
### <a name="remarks"></a>주의  
 `nID` 에 전달 된 고유 식별자로 매개 변수 참조는 **만들기** 컨트롤 막대의 메서드. 컨트롤 막대에 대 한 자세한 내용은 참조 항목을 [컨트롤 막대](../../mfc/control-bars.md)합니다.  
  
 `GetControlBar`경우에 마찬가지 부동 창인 따라서 현재 없는 자식 창 프레임의 컨트롤 막대를 반환 합니다.  
  
##  <a name="getdockstate"></a>CFrameWnd::GetDockState  
 호출에서 프레임 창은 컨트롤 막대에 대 한 상태 정보를 저장 하려면이 함수는 `CDockState` 개체입니다.  
  
```  
void GetDockState(CDockState& state) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `state`  
 반환 되 면 프레임 창은 컨트롤 막대의 현재 상태를 포함합니다.  
  
### <a name="remarks"></a>주의  
 콘텐츠를 작성할 수 있습니다 `CDockState` 사용 하 여 저장소를 `CDockState::SaveState` 또는 `Serialize`합니다. 나중에 컨트롤 막대를 이전 상태로 복원 하려면 로드 하 여 상태로 `CDockState::LoadState` 또는 `Serialize`, 호출 `SetDockState` 이전 상태로 프레임 창은 컨트롤 막대에 적용할 합니다.  
  
##  <a name="getmenubarstate"></a>CFrameWnd::GetMenuBarState  
 현재 MFC 응용 프로그램에서 메뉴의 표시 상태를 검색합니다.  
  
```  
virtual DWORD GetMenuBarState();
```  
  
### <a name="return-value"></a>반환 값  
 반환 값은 다음 값을 가질 수 있습니다.  
  
-   (0x01)-AFX_MBS_VISIBLE 메뉴 표시 됩니다.  
  
-   (0x02)-AFX_MBS_HIDDEN 메뉴 숨겨집니다.  
  
### <a name="remarks"></a>주의  
 런타임 오류가 발생 하는 경우이 디버그 모드에서 어설션을 메서드와에서 파생 된 예외를 발생 시키고는 [CException](../../mfc/reference/cexception-class.md) 클래스입니다.  
  
##  <a name="getmenubarvisibility"></a>CFrameWnd::GetMenuBarVisibility  
 현재 MFC 응용 프로그램에서 메뉴의 기본 상태 표시 하거나 숨길지 여부를 나타냅니다.  
  
```  
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 다음 값 중 하나를 반환합니다.  
  
-   (0x01)-AFX_MBV_KEEPVISIBLE 메뉴 및 표시 됩니다. 전혀 시간,으로 기본 포커스가 없습니다.  
  
-   (0x02)-AFX_MBV_DISPLAYONFOCUS 메뉴는 기본적으로 숨겨집니다. 메뉴를 숨길 경우 메뉴를 표시 하 고 포커스를 ALT 키를 누릅니다. 메뉴가 표시 되는 경우 숨기려면 alt 키 또는 ESC 키를 누릅니다.  
  
-   AFX_MBV_ DISPLAYONFOCUS (0X02) | (0x04) (비트 조합 (OR))-AFX_MBV_DISPLAYONF10 메뉴는 기본적으로 숨겨집니다. 메뉴를 숨길 경우 메뉴를 표시 하 고 포커스를 F10 키를 누릅니다. 메뉴가 표시 될 메뉴 켜거나 포커스를 전환 하려면 F10 키를 누릅니다. 메뉴 숨기려면 alt 키 또는 ESC 키를 누를 때까지 표시 됩니다.  
  
### <a name="remarks"></a>주의  
 런타임 오류가 발생 하는 경우이 디버그 모드에서 어설션을 메서드와에서 파생 된 예외를 발생 시키고는 [CException](../../mfc/reference/cexception-class.md) 클래스입니다.  
  
##  <a name="getmessagebar"></a>CFrameWnd::GetMessageBar  
 상태 표시줄에 대 한 단서를이 멤버 함수를 호출 합니다.  
  
```  
virtual CWnd* GetMessageBar();
```  
  
### <a name="return-value"></a>반환 값  
 상태 표시줄 창에 대 한 포인터입니다.  
  
##  <a name="getmessagestring"></a>CFrameWnd::GetMessageString  
 명령 Id에 대 한 사용자 지정 문자열을 제공 하려면이 함수를 재정의 합니다.  
  
```  
virtual void GetMessageString(
    UINT nID,  
    CString& rMessage) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nID`  
 원하는 메시지의 리소스 ID입니다.  
  
 `rMessage`  
 `CString`메시지를 배치할 수 있는 개체입니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 단순히 지정 된 문자열을 로드 `nID` 리소스 파일에서 합니다. 이 함수는 상태 표시줄에 메시지 문자열을 업데이트 해야 하는 경우 프레임 워크에서 호출 됩니다.  
  
##  <a name="gettitle"></a>CFrameWnd::GetTitle  
 창 개체의 제목을 검색합니다.  
  
```  
CString GetTitle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) window 개체의 현재 제목을 포함 하는 개체입니다.  
  
##  <a name="initialupdateframe"></a>CFrameWnd::InitialUpdateFrame  
 호출 **IntitialUpdateFrame** 새 프레임을 만든 후 **만들기**합니다.  
  
```  
void InitialUpdateFrame(
    CDocument* pDoc,  
    BOOL bMakeVisible);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDoc`  
 프레임 창이 연결 되는 문서를 가리킵니다. 수 **NULL**합니다.  
  
 `bMakeVisible`  
 경우 **TRUE**, 표시 되 고 활성 프레임 수 있는지를 나타냅니다. 경우 **FALSE**, 하위 항목이 없는 표시 이루어집니다.  
  
### <a name="remarks"></a>설명  
 이 모든 보기에서 수신 하도록 해당 프레임 창으로 인해 해당 `OnInitialUpdate` 호출 합니다.  
  
 또한 발생 한 경우 하지 이전에 활성 뷰, 프레임 창의 기본 보기 활성 이루어집니다. 기본 뷰는 자식 id가 **AFX_IDW_PANE_FIRST**합니다. 마지막으로, 프레임 창이 표시 되기 경우 `bMakeVisible` 0이 아닌 합니다. 경우 `bMakeVisible` 가 0 이면 현재 포커스 및 프레임 창의 표시 상태 변경 되지 것입니다. 새 파일 및 파일 열기의 프레임 워크의 구현을 사용 하는 경우이 함수를 호출할 필요는 없습니다.  
  
##  <a name="inmodalstate"></a>CFrameWnd::InModalState  
 프레임 창을 모달 인지 모덜리스 인지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL InModalState() const;  
```  
  
### <a name="return-value"></a>반환 값  
 그렇다면; 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="istracking"></a>CFrameWnd::IsTracking  
 이 창에는 분할 막대는 현재 이동 중인 경우를 확인 하려면 함수를 호출 합니다.  
  
```  
BOOL IsTracking() const;  
```  
  
### <a name="return-value"></a>반환 값  
 분할자 작업이 진행 중인 경우 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="loadacceltable"></a>CFrameWnd::LoadAccelTable  
 지정 된 액셀러레이터 키 테이블을 로드를 호출 합니다.  
  
```  
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszResourceName`  
 액셀러레이터 키 리소스 이름을 식별합니다. 사용 하 여 **MAKEINTRESOURCE** 리소스 정수 ID로 식별 되 면  
  
### <a name="return-value"></a>반환 값  
 액셀러레이터 키 테이블을 성공적으로 로드 되었습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 한 번에 하나의 테이블을 로드할 수 있습니다.  
  
 액셀러레이터 키 테이블 리소스에서 로드 된 응용 프로그램이 종료 될 때 자동으로 해제 됩니다.  
  
 호출 하는 경우 `LoadFrame` 프레임 창을 만들기 위해 프레임 워크는 액셀러레이터 키 테이블 메뉴 및 아이콘 리소스를 로드 하 고이 멤버 함수에 후속 호출은 다음 필요 하지 않습니다.  
  
##  <a name="loadbarstate"></a>CFrameWnd::LoadBarState  
 프레임 창에서 소유 하는 각 컨트롤 막대의 설정을 복원 하려면이 함수를 호출 합니다.  
  
```  
void LoadBarState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszProfileName`  
 상태 정보가 저장 되어 있는 Windows 레지스트리에서 키 또는 초기화 (INI) 파일의 섹션 이름입니다.  
  
### <a name="remarks"></a>주의  
 복원 정보에는 표시 유형, 가로/세로 방향, 도킹 상태 및 컨트롤 막대 위치 포함 됩니다.  
  
 복원 하려는 설정을 호출 하기 전에 레지스트리에 쓸 수 `LoadBarState`합니다. 호출 하 여 정보를 레지스트리에 기록 [CWinApp::SetRegistryKey](../../mfc/reference/cwinapp-class.md#setregistrykey)합니다. 호출 하 여 INI 파일에 정보를 쓸 [SaveBarState](#savebarstate)합니다.  
  
##  <a name="loadframe"></a>CFrameWnd::LoadFrame  
 동적으로 만드는 프레임 창에서 리소스 정보를 호출 합니다.  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDResource`  
 프레임 창에 연결 된 공유 리소스의 ID입니다.  
  
 *dwDefaultStyle*  
 프레임의 [스타일](../../mfc/reference/window-styles.md)합니다. 포함 된 **FWS_ADDTOTITLE** 창에에서 표시 되며 문서의 이름을 자동으로 표시 하려면 제목 표시줄을 원하는 경우 스타일입니다.  
  
 `pParentWnd`  
 프레임의 부모에 대 한 포인터입니다.  
  
 `pContext`  
 에 대 한 포인터는 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) 구조입니다. 이 매개 변수 수 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 생성 된 `CFrameWnd` 두 단계를 수행에서 하는 개체입니다. 첫째, 생성 된 생성자를 호출는 `CFrameWnd` 개체를 호출 `LoadFrame`, Windows 프레임 창 및 관련된 리소스를 로드 하 고 프레임 창에 연결 하는 `CFrameWnd` 개체입니다. `nIDResource` 메뉴, 액셀러레이터 키 테이블, 아이콘, 및 문자열 리소스의 프레임 창에 대 한 title 매개 변수를 지정 합니다.  
  
 사용 하 여는 **만들기** 멤버 함수 대신 `LoadFrame` 모든 프레임 창의 생성 매개 변수를 지정 하려는 경우.  
  
 프레임 워크를 호출 하 여 `LoadFrame` 문서 템플릿 개체를 사용 하 여 프레임 창을 만들 때.  
  
 프레임 워크를 사용 하 여는 `pContext` 포함 된 보기 개체 인수를 포함 하는 프레임 창에 연결 해야 하는 개체를 지정 합니다. 설정할 수 있습니다는 `pContext` 인수를 **NULL** 호출 하는 경우 `LoadFrame`합니다.  
  
##  <a name="m_bautomenuenable"></a>CFrameWnd::m_bAutoMenuEnable  
 메뉴 항목을이 데이터 멤버 (즉, 기본값)를 사용 하지 않은 `ON_UPDATE_COMMAND_UI` 또는 `ON_COMMAND` 사용자 메뉴 가져오며 때 처리기 자동으로 비활성화 됩니다.  
  
```  
BOOL m_bAutoMenuEnable;  
```  
  
### <a name="remarks"></a>주의  
 있는 메뉴 항목은 `ON_COMMAND` 아니지만 처리기 `ON_UPDATE_COMMAND_UI` 처리기 자동으로 활성화 됩니다.  
  
 이 데이터 멤버가 설정 되 면 메뉴 항목은 같은 방식으로 도구 모음 단추를 사용할 수 있는지 자동으로 활성화 됩니다.  
  
> [!NOTE]
> `m_bAutoMenuEnable`에 최상위 메뉴 항목에는 영향을 주지 않습니다.  
  
 이 데이터 멤버의 현재 선택을 기반으로 하는 선택적 명령 구현을 단순화 하 고 쓸 필요가 줄어 데이터 `ON_UPDATE_COMMAND_UI` 설정 및 해제 메뉴 항목에 대 한 처리기입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing # 3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]  
  
##  <a name="negotiateborderspace"></a>CFrameWnd::NegotiateBorderSpace  
 OLE 내부 활성화 하는 동안 프레임 창의 테두리 공간을 협상 하는 데이 함수를 호출 합니다.  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>매개 변수  
 *nBorderCmd*  
 다음 값 중 하나가 포함 된 **enum BorderCmd**:  
  
- **borderGet** = 1  
  
- **borderRequest** = 2  
  
- **borderSet** = 3  
  
 `lpRectBorder`  
 에 대 한 포인터는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 테두리의 좌표를 지정 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는는 **CFrameWnd** OLE 테두리 공간 협상의 구현입니다.  
  
##  <a name="onbarcheck"></a>CFrameWnd::OnBarCheck  
 지정 된 컨트롤 막대에는 동작이 수행 될 때마다 호출 됩니다.  
  
```  
afx_msg BOOL OnBarCheck(UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `nID`  
 표시 된 막대 컨트롤의 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 컨트롤 막대 있었으며, 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="oncontexthelp"></a>CFrameWnd::OnContextHelp  
 내부 항목에 대 한 SHIFT + F1 도움말을 처리합니다.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>주의  
 상황에 맞는 도움말을 사용 하려면 추가 해야 합니다는  
  
 [!code-cpp[NVC_MFCDocViewSDI # 16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]  
  
 문을 프로그램 `CFrameWnd` 메시지 맵을 클래스 및 일반적으로 SHIFT + f 1을이 멤버 함수를 사용 하도록 설정 하려면 액셀러레이터 키 테이블 항목을 추가할 수도 있습니다.  
  
 OLE 컨테이너 응용 프로그램이 경우 `OnContextHelp` 도움말 모드에는 프레임 창 개체 내에 포함 된 모든 내부 항목을 배치 합니다. 화살표와 물음표와 해당 사용자 커서 변경 사항 수 다음 마우스 포인터를 이동 하 고 마우스 왼쪽된 단추를 눌러 대화 상자, 창, 메뉴 또는 명령 단추를 선택 합니다. Windows 함수를 호출 하는이 멤버 함수 `WinHelp` 커서 아래에 있는 개체의 도움말 컨텍스트를 사용 합니다.  
  
##  <a name="oncreateclient"></a>CFrameWnd::OnCreateClient  
 실행 하는 동안에 프레임 워크에서 호출 `OnCreate`합니다.  
  
```  
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpcs`  
 Windows에 대 한 포인터 [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) 구조입니다.  
  
 `pContext`  
 에 대 한 포인터는 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 호출 하지 않습니다.  
  
 이 함수의 기본 구현을 만듭니다는 `CView` 개체에 제공 된 정보에서 `pContext`, 가능한 경우.  
  
 이 함수에 전달 된 값을 재정의 하려면 재정의 `CCreateContext` 개체 또는 변경 하려면 프레임 창의 기본 클라이언트 영역에서 방식으로 컨트롤 생성 됩니다. `CCreateContext` 에 설명 된 멤버를 재정의할 수 있습니다는 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) 클래스입니다.  
  
> [!NOTE]
>  전달 된 값을 대체 하지 않고는 `CREATESTRUCT` 구조입니다. 목적 으로만 사용 합니다. 예를 들어 재정의 초기 창 사각형을 재정의 하려는 경우는 `CWnd` 멤버 함수 [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow)합니다.  
  
##  <a name="onhidemenubar"></a>CFrameWnd::OnHideMenuBar  
 이 함수는 시스템 현재 MFC 응용 프로그램의 메뉴 모음을 숨기려면 되려고 할 때 호출 됩니다.  
  
```  
virtual void OnHideMenuBar();
```  
  
### <a name="remarks"></a>주의  
 이 이벤트 처리기에는 응용을 프로그램이 시스템 메뉴 숨기기 되려고 할 때 사용자 지정 작업을 수행할 수 있습니다. 숨겨진에서 메뉴를 방지할 수 있지만 메뉴 스타일 또는 상태를 검색 하는 다른 메서드를 호출할 예를 들어 수는 있습니다.  
  
##  <a name="onsetpreviewmode"></a>CFrameWnd::OnSetPreviewMode  
 응용 프로그램의 주 프레임 창을 인쇄 미리 보기 모드 내부 및 외부로 설정하려면 이 멤버 함수를 호출합니다.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>매개 변수  
 *bPreview*  
 인쇄 미리 보기 모드에서 응용 프로그램을 배치할 것인지 여부를 지정 합니다. 로 설정 **TRUE** 인쇄 미리 보기에 **FALSE** 미리 보기 모드를 취소 합니다.  
  
 `pState`  
 에 대 한 포인터는 **CPrintPreviewState** 구조입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현에서는 모든 표준 도구 모음을 사용 하지 않도록 설정 하 고 주 메뉴와 주 클라이언트 창을 숨깁니다. 이렇게 하면 임시 SDI 프레임 창에 MDI 프레임 창 꺼집니다.  
  
 숨기기 및 인쇄 미리 보기 중 다른 프레임 창 부분 컨트롤 막대의 표시를 사용자 지정 하려면이 멤버 함수를 재정의 합니다. 재정의 된 버전 내에서 기본 클래스 구현을 호출 합니다.  
  
##  <a name="onshowmenubar"></a>CFrameWnd::OnShowMenuBar  
 이 함수는 시스템 현재 MFC 응용 프로그램에서 메뉴 표시줄을 표시 하려고 할 때 호출 됩니다.  
  
```  
virtual void OnShowMenuBar();
```  
  
### <a name="remarks"></a>주의  
 이 이벤트 처리기에 응용을 프로그램의 메뉴를 표시 하려고 할 때 사용자 지정 작업을 수행할 수 있습니다. 표시 되지 않도록 메뉴를 방지할 수 있지만 메뉴 스타일 또는 상태를 검색 하는 다른 메서드를 호출할 예를 들어 수는 있습니다.  
  
##  <a name="onupdatecontrolbarmenu"></a>CFrameWnd::OnUpdateControlBarMenu  
 연결 된 메뉴를 업데이트할 때 프레임 워크에서 호출 합니다.  
  
```  
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCmdUI`  
 에 대 한 포인터는 [CCmdUI](../../mfc/reference/ccmdui-class.md) update 명령을 생성 하는 메뉴를 나타내는 개체입니다. 업데이트 처리기 호출의 [사용](../../mfc/reference/ccmdui-class.md#enable) 의 멤버 함수는 `CCmdUI` 개체를 통해 `pCmdUI` 사용자 인터페이스를 업데이트 하 합니다.  
  
##  <a name="recalclayout"></a>CFrameWnd::RecalcLayout  
 표준 컨트롤 막대가 설정 하거나 해제 설정/해제 하거나 프레임 창의 크기를 조정할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bNotify`  
 프레임 창에 대 한 활성 내부 항목 레이아웃 변경의 알림을 받을지 여부를 결정 합니다. 경우 **TRUE**, 항목 알려진 되지 않았으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수의 기본 구현을 호출 하는 `CWnd` 멤버 함수 `RepositionBars` 주 클라이언트 창에서와 같이 프레임에서는 모든 컨트롤 막대 위치 (일반적으로 `CView` 또는 **MDICLIENT**).  
  
 프레임 창의 레이아웃 변경 된 후 모양 및 컨트롤 막대의 동작을 제어 하려면이 멤버 함수를 재정의 합니다. 예를 들어 호출 컨트롤 막대 켜기 / 끄기 또는 다른 컨트롤 막대를 추가 하는 경우.  
  
##  <a name="rectdefault"></a>CFrameWnd::rectDefault  
 이 정적 전달할 `CRect` Windows 창의 초기 크기와 위치를 선택 하도록 허용 하려면 창을 만들 때 매개 변수로 합니다.  
  
```  
static AFX_DATA const CRect rectDefault;  
```  
  
##  <a name="savebarstate"></a>CFrameWnd::SaveBarState  
 프레임 창에서 소유 하는 각 컨트롤 막대에 대 한 정보를 저장 하려면이 함수를 호출 합니다.  
  
```  
void SaveBarState(LPCTSTR lpszProfileName) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszProfileName`  
 초기화 파일의 섹션 이나 상태 정보가 저장 되어 있는 Windows 레지스트리에서 키의 이름입니다.  
  
### <a name="remarks"></a>주의  
 이 정보를 사용 하 여 초기화 파일에서 읽을 수 [LoadBarState](#loadbarstate)합니다. 저장 된 정보에는 표시 여부, 도킹 상태 및 컨트롤 막대 위치 가로/세로 방향으로 포함 됩니다.  
  
##  <a name="setactivepreviewview"></a>CFrameWnd::SetActivePreviewView  
 지정 된 뷰 풍부한 미리 보기에 대 한 활성 뷰를 지정 합니다.  
  
```  
void SetActivePreviewView(CView* pViewNew);
```  
  
### <a name="parameters"></a>매개 변수  
 `pViewNew`  
 보기를 활성화할 수에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="setactiveview"></a>CFrameWnd::SetActiveView  
 현재 보기를 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetActiveView(
    CView* pViewNew,  
    BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *pViewNew*  
 에 대 한 포인터를 지정 합니다.는 [CView](../../mfc/reference/cview-class.md) 개체 또는 **NULL** 없는 현재 보기에 대 한 합니다.  
  
 `bNotify`  
 뷰는 활성화의 알림을 받을 수 있는지 여부를 지정 합니다. 경우 **TRUE**, `OnActivateView` 경우 새 보기;에 대 한 호출 **FALSE**, 없습니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크 사용자 포커스 프레임 창 내에서 보기를 변경 하는 대로이 함수를 자동으로 호출 합니다. 명시적으로 호출할 수 `SetActiveView` 지정된 된 보기에 포커스를 변경할 수 있습니다.  
  
##  <a name="setdockstate"></a>CFrameWnd::SetDockState  
 에 저장 된 상태 정보를 적용 하려면이 함수를 호출는 `CDockState` 개체 프레임 창은 컨트롤 막대입니다.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>매개 변수  
 `state`  
 프레임 창의 컨트롤 막대에 저장 된 상태를 적용 합니다.  
  
### <a name="remarks"></a>주의  
 컨트롤 막대의 이전 상태를 복원 하려면으로 저장된 된 상태를 로드할 수 있습니다 `CDockState::LoadState` 또는 `Serialize`를 사용 하 여 `SetDockState` 프레임 창은 컨트롤 막대에 적용할 수도 있습니다. 이전 상태에 저장 됩니다는 `CDockState` 개체`GetDockState`  
  
##  <a name="setmenubarstate"></a>CFrameWnd::SetMenuBarState  
 숨겨진 또는 표시 된 현재 MFC 응용 프로그램에서 메뉴의 표시 상태를 설정합니다.  
  
```  
virtual BOOL SetMenuBarState(DWORD nState);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `nState`|메뉴의 표시 여부를 지정 합니다. `nState` 매개 변수는 다음 값을 가질 수 있습니다.<br /><br /> -AFX_MBS_VISIBLE (0x01)-숨겨져 있지만 표시 된 경우 아무 효과가 메뉴를 표시 합니다.<br />-AFX_MBS_HIDDEN (0x02)-숨기는 메뉴는 표시 되지만 숨겨진 경우 효과가 없습니다 것입니다.|  
  
### <a name="return-value"></a>반환 값  
 `true`이 메서드가 성공적으로 메뉴 상태;으로 변경 하는 경우 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>주의  
 런타임 오류가 발생 하는 경우이 디버그 모드에서 어설션을 메서드와에서 파생 된 예외를 발생 시키고는 [CException](../../mfc/reference/cexception-class.md) 클래스입니다.  
  
##  <a name="setmenubarvisibility"></a>CFrameWnd::SetMenuBarVisibility  
 숨겨지거나 표시 되도록 현재 MFC 응용 프로그램에서 메뉴의 기본 동작을 설정 합니다.  
  
```  
virtual void SetMenuBarVisibility(DWORD nStyle);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `nStyle`|여부 메뉴는 숨겨져 있는 경우 기본적으로 또는 볼 수 있고 포커스가 지정 합니다. `nStyle` 매개 변수는 다음 값을 가질 수 있습니다.<br /><br /> -AFX_MBV_KEEPVISIBLE (0X01)-<br />     메뉴 항상 표시 되 고 기본적으로 포커스를 갖고 없습니다.<br />-AFX_MBV_DISPLAYONFOCUS (0X02)-<br />     메뉴는 기본적으로 숨겨집니다. 메뉴를 숨길 경우 메뉴를 표시 하 고 포커스를 ALT 키를 누릅니다. 메뉴가 표시 될 메뉴를 숨기 alt 키 또는 ESC 키를 누릅니다.<br />-AFX_MBV_ DISPLAYONFOCUS (0X02) | AFX_MBV_DISPLAYONF10 (0X04)<br />     (비트 조합 (OR))-메뉴는 기본적으로 숨겨집니다. 메뉴를 숨길 경우 메뉴를 표시 하 고 포커스를 F10 키를 누릅니다. 메뉴가 표시 될 메뉴 켜거나 포커스를 전환 하려면 F10 키를 누릅니다. 메뉴 숨기려면 alt 키 또는 ESC 키를 누를 때까지 표시 됩니다.|  
  
### <a name="remarks"></a>주의  
 하는 경우의 값은 `nStyle` 디버그 모드와 발생 어설션 매개 변수가 유효 하지 않으면이 메서드 [CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md) 릴리스 모드에서. 그 외 런타임 오류 발생 시이 디버그 모드에서 어설션을 메서드와에서 파생 된 예외를 발생 시킵니다.는 [CException](../../mfc/reference/cexception-class.md) 클래스입니다.  
  
 이 메서드 용으로 작성 된 응용 프로그램에서 메뉴의 상태에 영향을 줍니다 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] 이상.  
  
##  <a name="setmessagetext"></a>CFrameWnd::SetMessageText  
 0의 ID가 있는 상태 표시줄 창에서 문자열을 배치 하려면이 함수를 호출 합니다.  
  
```  
void SetMessageText(LPCTSTR lpszText);  
void SetMessageText(UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszText`  
 상태 표시줄에 배치할 수 있도록 문자열을 가리킵니다.  
  
 `nID`  
 상태 표시줄에 배치 하는 문자열의 리소스 ID는 문자열입니다.  
  
### <a name="remarks"></a>주의  
 이 일반적으로 상태 표시줄의 맨 왼쪽, 및 가장 늦은 창.  
  
##  <a name="setprogressbarposition"></a>CFrameWnd::SetProgressBarPosition  
 작업 표시줄에 표시 되는 Windows 7 진행률 표시줄에 대 한 현재 위치를 설정 합니다.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>매개 변수  
 `nProgressPos`  
 설정할 상대 위치를 지정 합니다. 가 설정한 범위 내에 있어야 `SetProgressBarRange`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="setprogressbarrange"></a>CFrameWnd::SetProgressBarRange  
 작업 표시줄에 표시 되는 Windows 7 진행률 표시줄에 대 한 범위를 설정 합니다.  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>매개 변수  
 `nRangeMin`  
 최소 값입니다.  
  
 `nRangeMax`  
 최대 값입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="setprogressbarstate"></a>CFrameWnd::SetProgressBarState  
 유형 및 작업 표시줄 단추에 표시 되는 진행률 표시기의 상태를 설정 합니다.  
  
```  
void SetProgressBarState(TBPFLAG tbpFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 `tbpFlags`  
 진행률 단추의 현재 상태를 제어 하는 플래그입니다. 모든 상태는 상호 배타적이 때문에 다음 중 하나에 플래그 지정: TBPF_NOPROGRESS, TBPF_INDETERMINATE, TBPF_NORMAL, TBPF_ERROR, TBPF_PAUSED 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="settaskbaroverlayicon"></a>CFrameWnd::SetTaskbarOverlayIcon  
 오버로드됨. 응용 프로그램 상태를 나타내는 또는 사용자에 게 알리도록 작업 표시줄 단추에 오버레이 적용 합니다.  
  
```  
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,  
    LPCTSTR lpcszDescr);

 
BOOL SetTaskbarOverlayIcon(
    HICON hIcon,  
    LPCTSTR lpcszDescr);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDResource`  
 오버레이으로 사용할 아이콘의 리소스 ID를 지정 합니다. 에 대 한 참조 `hIcon` 대 한 자세한 내용은 합니다.  
  
 `lpcszDescr`  
 대체 텍스트 버전의 편리한 액세스를 위해 오버레이 전달 되는 정보를 제공 하는 문자열에 대 한 포인터입니다.  
  
 `hIcon`  
 오버레이으로 사용할 아이콘의 핸들입니다. 이 작은 아이콘, 96 dpi ()에서 16 x 16 픽셀 측정 해야 합니다. 작업 표시줄 단추에 오버레이 아이콘이 이미 적용 되어 있으면 해당 기존 오버레이 대체 됩니다. 이 값은 `NULL`일 수 있습니다. 어떻게는 `NULL` 값 처리 작업 표시줄 단추가 단일 창 또는 windows 그룹이 나타냅니다 여부에 따라 달라 집니다. 무료을 호출 응용 프로그램 작업은 `hIcon` 더 이상 필요 없는 경우.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`성공 하면 `FALSE` OS 버전이 Windows 7 보다 작은 경우 또는 오류가 발생는 아이콘을 설정 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="settitle"></a>CFrameWnd::SetTitle  
 창 개체의 제목을 설정합니다.  
  
```  
void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszTitle`  
 창 개체의 제목을 포함 하는 문자열에 대 한 포인터입니다.  
  
##  <a name="showcontrolbar"></a>CFrameWnd::ShowControlBar  
 컨트롤 막대를 표시할지를이 멤버 함수를 호출 합니다.  
  
```  
void ShowControlBar(
    CControlBar* pBar,  
    BOOL bShow,  
    BOOL bDelay);
```  
  
### <a name="parameters"></a>매개 변수  
 `pBar`  
 컨트롤 막대를 표시 하거나 숨길 수에 대 한 포인터입니다.  
  
 `bShow`  
 경우 **TRUE**, 컨트롤 막대를 표시할 수를 지정 합니다. 경우 **FALSE**, 컨트롤 막대 숨겨져야 임을 지정 합니다.  
  
 *bDelay*  
 경우 **TRUE**, 지연 컨트롤 막대를 표시 합니다. 경우 **FALSE**, 즉시 막대 컨트롤을 표시 합니다.  
  
##  <a name="showownedwindows"></a>CFrameWnd::ShowOwnedWindows  
 하위 항목인 모든 창을 표시 하려면이 멤버 함수 호출의 `CFrameWnd` 개체입니다.  
  
```  
void ShowOwnedWindows(BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 `bShow`  
 소유 windows을 표시 하거나 숨길 수 있는지 여부를 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd 클래스](../../mfc/reference/cmdiframewnd-class.md)   
 [CMDIChildWnd 클래스](../../mfc/reference/cmdichildwnd-class.md)   
 [CView 클래스](../../mfc/reference/cview-class.md)   
 [CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)   
 [CRuntimeClass 구조체](../../mfc/reference/cruntimeclass-structure.md)

