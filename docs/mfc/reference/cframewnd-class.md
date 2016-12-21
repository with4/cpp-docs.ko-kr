---
title: "CFrameWnd Class | Microsoft Docs"
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
  - "CFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFrameWnd class"
  - "frame window classes, 기본 클래스"
  - "frame windows, 만들기"
  - "SDI(단일 문서 인터페이스), frame windows"
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

겹쳐진 Windows 단일 문서 인터페이스 \(SDI\) 또는 팝업 프레임 창에서 멤버 창 관리 기능을 제공 합니다.  
  
## 구문  
  
```  
class CFrameWnd : public CWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CFrameWnd::CFrameWnd](../Topic/CFrameWnd::CFrameWnd.md)|`CFrameWnd` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFrameWnd::ActivateFrame](../Topic/CFrameWnd::ActivateFrame.md)|프레임을 표시 하 고 사용할 수 있는 사용자에 게 있습니다.|  
|[CFrameWnd::BeginModalState](../Topic/CFrameWnd::BeginModalState.md)|프레임 창은 모달을 설정합니다.|  
|[CFrameWnd::Create](../Topic/CFrameWnd::Create.md)|호출을 만들고 연결 된 Windows 프레임 창의 초기화 하는 `CFrameWnd` 개체입니다.|  
|[CFrameWnd::CreateView](../Topic/CFrameWnd::CreateView.md)|보기에서 파생 된 프레임 안에서 만듭니다 `CView`.|  
|[CFrameWnd::DockControlBar](../Topic/CFrameWnd::DockControlBar.md)|컨트롤 막대를 도킹합니다.|  
|[CFrameWnd::EnableDocking](../Topic/CFrameWnd::EnableDocking.md)|컨트롤 막대를 도킹 될 수 있습니다.|  
|[CFrameWnd::EndModalState](../Topic/CFrameWnd::EndModalState.md)|프레임 창은 모달 상태를 종료합니다.  모든 창에서 사용할 수 있도록 `BeginModalState`.|  
|[CFrameWnd::FloatControlBar](../Topic/CFrameWnd::FloatControlBar.md)|컨트롤 막대가 부동.|  
|[CFrameWnd::GetActiveDocument](../Topic/CFrameWnd::GetActiveDocument.md)|현재 반환  **CDocument** 개체입니다.|  
|[CFrameWnd::GetActiveFrame](../Topic/CFrameWnd::GetActiveFrame.md)|현재 반환 `CFrameWnd` 개체입니다.|  
|[CFrameWnd::GetActiveView](../Topic/CFrameWnd::GetActiveView.md)|현재 반환 `CView` 개체입니다.|  
|[CFrameWnd::GetControlBar](../Topic/CFrameWnd::GetControlBar.md)|컨트롤 막대를 검색합니다.|  
|[CFrameWnd::GetDockState](../Topic/CFrameWnd::GetDockState.md)|프레임 창의 도킹 상태를 검색합니다.|  
|[CFrameWnd::GetMenuBarState](../Topic/CFrameWnd::GetMenuBarState.md)|현재 MFC 응용 프로그램에서 메뉴의 디스플레이 상태를 검색합니다.|  
|[CFrameWnd::GetMenuBarVisibility](../Topic/CFrameWnd::GetMenuBarVisibility.md)|메뉴에서 현재 MFC 응용 프로그램의 기본 동작을 표시 또는 숨김 여부를 나타냅니다.|  
|[CFrameWnd::GetMessageBar](../Topic/CFrameWnd::GetMessageBar.md)|상태 표시줄 프레임 창에 속하는 포인터를 반환 합니다.|  
|[CFrameWnd::GetMessageString](../Topic/CFrameWnd::GetMessageString.md)|명령 ID에 해당 하는 메시지를 검색 합니다.|  
|[CFrameWnd::GetTitle](../Topic/CFrameWnd::GetTitle.md)|관련된 컨트롤 막대의 제목을 검색합니다.|  
|[CFrameWnd::InitialUpdateFrame](../Topic/CFrameWnd::InitialUpdateFrame.md)|발생의 `OnInitialUpdate` 멤버 함수를 호출 하는 프레임 창에서 모든 보기에 속하는.|  
|[CFrameWnd::InModalState](../Topic/CFrameWnd::InModalState.md)|프레임 창은 모달 상태에 있는지 여부를 나타내는 값을 반환 합니다.|  
|[CFrameWnd::IsTracking](../Topic/CFrameWnd::IsTracking.md)|분할 막대 현재 이동 하는 경우를 결정 합니다.|  
|[CFrameWnd::LoadAccelTable](../Topic/CFrameWnd::LoadAccelTable.md)|액셀러레이터 키 테이블을 로드 하려면 호출 합니다.|  
|[CFrameWnd::LoadBarState](../Topic/CFrameWnd::LoadBarState.md)|컨트롤 도구 모음 설정을 복원 하려면 다음과 같이 호출 합니다.|  
|[CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md)|프레임 창에서 리소스 정보를 동적으로 만들려면 다음을 호출 합니다.|  
|[CFrameWnd::NegotiateBorderSpace](../Topic/CFrameWnd::NegotiateBorderSpace.md)|프레임 창에서 테두리 공간을 협상합니다.|  
|[CFrameWnd::OnBarCheck](../Topic/CFrameWnd::OnBarCheck.md)|지정 된 컨트롤 막대에 작업을 수행할 때마다 호출 됩니다.|  
|[CFrameWnd::OnContextHelp](../Topic/CFrameWnd::OnContextHelp.md)|SHIFT \+ F1 도움말 전체 항목을 처리합니다.|  
|[CFrameWnd::OnSetPreviewMode](../Topic/CFrameWnd::OnSetPreviewMode.md)|응용 프로그램의 주 프레임 창 및 인쇄 미리 보기 모드를 설정합니다.|  
|[CFrameWnd::OnUpdateControlBarMenu](../Topic/CFrameWnd::OnUpdateControlBarMenu.md)|연결된 메뉴에서 업데이트 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CFrameWnd::RecalcLayout](../Topic/CFrameWnd::RecalcLayout.md)|컨트롤 막대의 재배치는 `CFrameWnd` 개체입니다.|  
|[CFrameWnd::SaveBarState](../Topic/CFrameWnd::SaveBarState.md)|호출 제어 표시줄 설정을 저장 합니다.|  
|[CFrameWnd::SetActivePreviewView](../Topic/CFrameWnd::SetActivePreviewView.md)|고급 미리 보기에 대 한 현재 보기에 지정 된 보기를 지정 합니다.|  
|[CFrameWnd::SetActiveView](../Topic/CFrameWnd::SetActiveView.md)|활성 설정 `CView` 개체입니다.|  
|[CFrameWnd::SetDockState](../Topic/CFrameWnd::SetDockState.md)|주 창에서 프레임 창을 도킹 하려면 호출 합니다.|  
|[CFrameWnd::SetMenuBarState](../Topic/CFrameWnd::SetMenuBarState.md)|현재 MFC 응용 프로그램에 숨겨지거나 표시 된 메뉴의 표시 상태를 설정합니다.|  
|[CFrameWnd::SetMenuBarVisibility](../Topic/CFrameWnd::SetMenuBarVisibility.md)|숨겨져 있거나 표시 되도록 현재 MFC 응용 프로그램에서 메뉴의 기본 동작을 설정 합니다.|  
|[CFrameWnd::SetMessageText](../Topic/CFrameWnd::SetMessageText.md)|표준 상태 표시줄 텍스트를 설정합니다.|  
|[CFrameWnd::SetProgressBarPosition](../Topic/CFrameWnd::SetProgressBarPosition.md)|작업 표시줄에 표시 되는 Windows 7 진행률 표시줄의 현재 위치를 설정 합니다.|  
|[CFrameWnd::SetProgressBarRange](../Topic/CFrameWnd::SetProgressBarRange.md)|작업 표시줄에 표시 되는 Windows 7 진행률 표시줄의 범위를 설정 합니다.|  
|[CFrameWnd::SetProgressBarState](../Topic/CFrameWnd::SetProgressBarState.md)|유형 및 작업 표시줄 단추에 표시 되는 진행률 표시기의 상태를 설정 합니다.|  
|[CFrameWnd::SetTaskbarOverlayIcon](../Topic/CFrameWnd::SetTaskbarOverlayIcon.md)|오버로드.  오버레이 응용 프로그램 상태나 사용자를 나타내는 작업 표시줄 단추에 적용 됩니다.|  
|[CFrameWnd::SetTitle](../Topic/CFrameWnd::SetTitle.md)|관련된 컨트롤 막대의 제목을 설정합니다.|  
|[CFrameWnd::ShowControlBar](../Topic/CFrameWnd::ShowControlBar.md)|호출 컨트롤 막대를 표시 합니다.|  
|[CFrameWnd::ShowOwnedWindows](../Topic/CFrameWnd::ShowOwnedWindows.md)|하위 항목인 모든 windows 표시는 `CFrameWnd` 개체입니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFrameWnd::OnCreateClient](../Topic/CFrameWnd::OnCreateClient.md)|프레임의 클라이언트 창을 만듭니다.|  
|[CFrameWnd::OnHideMenuBar](../Topic/CFrameWnd::OnHideMenuBar.md)|현재 MFC 응용 프로그램에서 메뉴를 숨기기 전에 호출 됩니다.|  
|[CFrameWnd::OnShowMenuBar](../Topic/CFrameWnd::OnShowMenuBar.md)|현재 MFC 응용 프로그램에는 메뉴가 표시 되기 전에 호출 됩니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CFrameWnd::m\_bAutoMenuEnable](../Topic/CFrameWnd::m_bAutoMenuEnable.md)|자동 컨트롤 사용 및 기능에 대 한 메뉴 항목 사용 안 함.|  
|[CFrameWnd::rectDefault](../Topic/CFrameWnd::rectDefault.md)|이 정적 전달 `CRect` 를 만들 때 매개 변수로 `CFrameWnd` Windows 창의 초기 크기 및 위치를 선택할 수 있도록 하는 개체입니다.|  
  
## 설명  
 유용한 프레임 창에 대 한 응용 프로그램을 만들려면이 클래스에서 파생 `CFrameWnd`.  응용 프로그램에 데이터를 저장 하는 파생된 클래스에 멤버 변수를 추가 합니다.  메시지 창으로 전달 되는 경우 수행할 작업을 지정할 수 있는 파생된 클래스의 메시지 처리기 멤버 함수를 구현 하 고 메시지를 매핑합니다.  
  
 구성 프레임 창에는 다음 세 가지가 있습니다.  
  
-   직접 사용 하 여 만드는  [만들기](../Topic/CFrameWnd::Create.md).  
  
-   직접 사용 하 여 만드는  [LoadFrame](../Topic/CFrameWnd::LoadFrame.md).  
  
-   직접는 문서 서식 파일을 사용 하 여 만들 없습니다.  
  
 하나를 호출 하기 전에  **만들기** 또는 `LoadFrame`, C\+\+를 사용 하 여 힙에 프레임 창 개체를 생성 해야  **새** 연산자.  호출 하기 전에  **만들기**를 사용 하 여 창 클래스를 등록할 수도 있습니다는  [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) 아이콘과 클래스 스타일 프레임을 설정 하는 전역 함수.  
  
 사용 된  **만들기** 프레임 생성 매개 변수는 즉시 인수를 전달 하려면 함수.  
  
 `LoadFrame`보다 적은 인수가 필요  **만들기**, 대신 프레임의 캡션, 아이콘, 액셀러레이터 테이블 및 메뉴를 비롯 하 여 리소스에서 대부분의 기본값을 검색 합니다.  에 액세스할 수 `LoadFrame`, 이러한 리소스는 동일한 리소스 ID에 있어야 합니다 \(예를 들어,  **IDR\_MAINFRAME**\).  
  
 경우는 `CFrameWnd` 개체 보기 및 문서를 포함, 직접 대신 프레임 워크는 프로그래머에 의해 직접 만들어진 없습니다.  `CDocTemplate` 개체 총괄 프레임의 작성, 포함 하는 뷰를 만들고 뷰의 해당 문서에 연결 합니다.  매개 변수는 `CDocTemplate` 생성자를 지정 하는 `CRuntimeClass` \(문서, 프레임 및 보기\)의 세 가지 클래스와 관련.  A `CRuntimeClass` 개체 \(예를 들어, 새 파일 명령 또는 다중 문서 인터페이스 \(MDI\) 새 창 명령을 사용 하 여\) 사용자가 지정 된 경우 새 프레임을 동적으로 만드는 프레임 워크에서 사용 됩니다.  
  
 프레임 창 클래스에서 파생 된 `CFrameWnd` 를 선언 합니다. `DECLARE_DYNCREATE` 위를 `RUNTIME_CLASS` 메커니즘이 제대로 작동 하려면.  
  
 A `CFrameWnd` Windows에 대 한 일반적인 응용 프로그램에서는 주 창의 다음 함수를 수행 하는 기본 구현을 포함 합니다.  
  
-   A `CFrameWnd` 프레임 창 독립적인 Windows 활성 창 또는 현재 입력된 포커스를 현재 활성 뷰를 추적 합니다.  프레임을 다시 활성화 될 때 현재 보기를 호출 하 여 알림을입니다 `CView::OnActivateView`.  
  
-   명령 처리 포함 한 많은 일반적인 프레임 알림 메시지와 메시지는 `OnSetFocus`, `OnHScroll`, 및 `OnVScroll` 함수를 `CWnd`을 위임 하는 `CFrameWnd` 프레임 창이 현재 활성 보기에.  
  
-   프레임 창의 캡션을 현재 활성 뷰 \(또는 현재 활성 MDI 자식 프레임 창에서 MDI 프레임의 경우\)에 확인할 수 있습니다.  이 기능을 해제 하 여 비활성화할 수 있습니다는  **FWS\_ADDTOTITLE** 의 프레임 창 스타일 비트.  
  
-   A `CFrameWnd` 프레임 창 관리 컨트롤 막대, 뷰 및 기타 자식 창 프레임 창의 클라이언트 영역 내에 배치 합니다.  프레임 창에 도구 모음 및 다른 컨트롤 막대 단추의 유휴 시간 업데이트도 하지 않습니다.  A `CFrameWnd` 프레임 창에 명령 켜고 끌 도구 모음과 상태 표시줄의 기본 구현도 있습니다.  
  
-   A `CFrameWnd` 프레임 창이 주 메뉴 모음을 관리 합니다.  팝업 메뉴가 표시 되 면 프레임 창에 사용 하는  **UPDATE\_COMMAND\_UI** 메뉴 항목 활성화, 비활성화 되거나 되어야 체크를 확인 하는 메커니즘입니다.  사용자가 메뉴 항목을 선택할 때 프레임 창 상태 표시줄 명령에 대 한 메시지 문자열을 업데이트 합니다.  
  
-   A `CFrameWnd` 프레임 창 액셀러레이터 키를 자동으로 변환 하는 옵션 액셀러레이터 테이블에 있습니다.  
  
-   A `CFrameWnd` 프레임 창 설정 옵션 도움말 ID가 `LoadFrame` 상황에 맞는 도움말을 사용 합니다.  프레임 창 주 조정자의 상황에 맞는 도움말 \(SHIFT \+ F1\) 및 인쇄 미리 보기 모드 등의 부분 모달 상태입니다.  
  
-   A `CFrameWnd` 프레임 창 파일 파일 관리자에서 끌어서 놓을 프레임 창에 열립니다.  파일 확장명이 등록 되어 연결 된 경우 프레임 창 파일 관리자의 데이터 파일을 열 때 발생 하는 동적 데이터 교환 \(DDE\) 열기 요청에 응답 하는  **ShellExecute** Windows 함수를 호출 합니다.  
  
-   주 응용 프로그램 창이 프레임 창인 경우 \(즉, `CWinThread::m_pMainWnd`\), 사용자, 응용 프로그램을 닫으면 프레임 창 수정 된 문서를 저장 하 라는 \(에 대 한 `OnClose` 및 `OnQueryEndSession`\).  
  
-   주 응용 프로그램 창이 프레임 창인 경우 프레임 창 WinHelp 실행 컨텍스트입니다.  프레임 창을 닫는 WINHELP를 종료 합니다.EXE이 응용 프로그램을 실행 한 경우.  
  
 C \+ \+를 사용 하지 않는  **삭제** 프레임 창을 소멸 하는 연산자입니다.  대신 `CWnd::DestroyWindow`를 사용하십시오.  `CFrameWnd` 구현 `PostNcDestroy` 창이 소멸 될 때 C\+\+ 개체를 삭제 합니다.  사용자는 기본 프레임 창의 닫을 때 `OnClose` 처리기를 호출 하는 `DestroyWindow`.  
  
 에 대 한 자세한 내용은 `CFrameWnd`를 참조 하십시오  [프레임 Windows](../../mfc/frame-windows.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CFrameWnd`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd Class](../../mfc/reference/cmdiframewnd-class.md)   
 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CRuntimeClass Structure](../../mfc/reference/cruntimeclass-structure.md)