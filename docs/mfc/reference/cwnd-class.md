---
title: "CWnd 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWnd 클래스"
  - "window objects [C++]"
  - "windows [C++]"
ms.assetid: 49a832ee-bc34-4126-88b3-bc1d9974f6c4
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CWnd 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC 라이브러리의 모든 창 클래스의 기본 기능을 제공합니다.  
  
## 구문  
  
```  
class CWnd : public CCmdTarget  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CWnd::CWnd](../Topic/CWnd::CWnd.md)|`CWnd` 개체를 생성합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CWnd::accDoDefaultAction](../Topic/CWnd::accDoDefaultAction.md)|개체의 기본 동작을 수행하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::accHitTest](../Topic/CWnd::accHitTest.md)|화면의 지정된 지점에서 자식 요소나 자식 개체를 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::accLocation](../Topic/CWnd::accLocation.md)|지정된 개체의 현재 화면 위치를 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::accNavigate](../Topic/CWnd::accNavigate.md)|컨테이너 내에서 다른 사용자 인터페이스 요소로 트래버스하고 가능할 경우 개체를 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::accSelect](../Topic/CWnd::accSelect.md)|선택 영역을 수정하거나 지정된 개체의 키보드 포커스를 이동하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::AnimateWindow](../Topic/CWnd::AnimateWindow.md)|연결된 창 개체를 애니메이션합니다.|  
|[CWnd::ArrangeIconicWindows](../Topic/CWnd::ArrangeIconicWindows.md)|모든 최소화된\(아이콘\) 자식 창을 정렬합니다.|  
|[CWnd::Attach](../Topic/CWnd::Attach.md)|Windows 핸들을 `CWnd` 개체에 연결합니다.|  
|[CWnd::BeginModalState](../Topic/CWnd::BeginModalState.md)|프레임 창을 모달로 만들기 위해 이 멤버 함수를 호출합니다.|  
|[CWnd::BeginPaint](../Topic/CWnd::BeginPaint.md)|그리기를 위해 `CWnd`를 준비합니다.|  
|[CWnd::BindDefaultProperty](../Topic/CWnd::BindDefaultProperty.md)|형식 라이브러리에 표시된 대로 호출하는 개체의 바인딩된 기본 단순 속성을 데이터 소스 컨트롤과 연결된 커서에 바인딩합니다.|  
|[CWnd::BindProperty](../Topic/CWnd::BindProperty.md)|데이터 바인딩된 컨트롤의 커서 바인딩된 속성을 데이터 소스 컨트롤에 바인딩하고 MFC 바인딩 관리자에 해당 관계를 등록합니다.|  
|[CWnd::BringWindowToTop](../Topic/CWnd::BringWindowToTop.md)|`CWnd`를 겹치는 창 스택의 맨 위로 이동합니다.|  
|[CWnd::CalcWindowRect](../Topic/CWnd::CalcWindowRect.md)|클라이언트 사각형에서 창 사각형을 계산하기 위해 호출됩니다.|  
|[CWnd::CancelToolTips](../Topic/CWnd::CancelToolTips.md)|도구 설명 컨트롤을 사용하지 않도록 설정합니다.|  
|[CWnd::CenterWindow](../Topic/CWnd::CenterWindow.md)|부모를 기준으로 창을 가운데 맞춤합니다.|  
|[CWnd::ChangeClipboardChain](../Topic/CWnd::ChangeClipboardChain.md)|클립보드 뷰어 체인에서 `CWnd`를 제거합니다.|  
|[CWnd::CheckDlgButton](../Topic/CWnd::CheckDlgButton.md)|단추 컨트롤 옆에 확인 표시를 배치하거나 이 컨트롤에서 확인 표시를 제거합니다.|  
|[CWnd::CheckRadioButton](../Topic/CWnd::CheckRadioButton.md)|지정된 라디오 단추를 선택하고 지정된 단추 그룹의 다른 모든 라디오 단추에서 확인 표시를 제거합니다.|  
|[CWnd::ChildWindowFromPoint](../Topic/CWnd::ChildWindowFromPoint.md)|자식 창 중에서 지정된 점이 있는 창\(있는 경우\)을 확인합니다.|  
|[CWnd::ClientToScreen](../Topic/CWnd::ClientToScreen.md)|디스플레이에서 지정된 점이나 사각형의 클라이언트 좌표를 화면 좌표로 변환합니다.|  
|[CWnd::CloseWindow](../Topic/CWnd::CloseWindow.md)|창을 최소화합니다.|  
|[CWnd::ContinueModal](../Topic/CWnd::ContinueModal.md)|창의 모달 상태를 계속 유지합니다.|  
|[CWnd::Create](../Topic/CWnd::Create.md)|`CWnd` 개체와 연결된 자식 창을 만들고 초기화합니다.|  
|[CWnd::CreateAccessibleProxy](../Topic/CWnd::CreateAccessibleProxy.md)|지정된 개체에 대해 Active Accessibility 프록시를 만듭니다.|  
|[CWnd::CreateCaret](../Topic/CWnd::CreateCaret.md)|시스템 캐럿에 대한 새 셰이프를 만들고 캐럿의 소유권을 가져옵니다.|  
|[CWnd::CreateControl](../Topic/CWnd::CreateControl.md)|MFC 프로그램에서 `CWnd` 개체로 표현될 ActiveX 컨트롤을 만듭니다.|  
|[CWnd::CreateEx](../Topic/CWnd::CreateEx.md)|겹친 Windows 팝업 또는 자식 창을 만들고 `CWnd` 개체에 연결합니다.|  
|[CWnd::CreateGrayCaret](../Topic/CWnd::CreateGrayCaret.md)|시스템 캐럿에 대한 회색 블록을 만들고 캐럿의 소유권을 가져옵니다.|  
|[CWnd::CreateSolidCaret](../Topic/CWnd::CreateSolidCaret.md)|시스템 캐럿에 대한 단색 블록을 만들고 캐럿의 소유권을 가져옵니다.|  
|[CWnd::DeleteTempMap](../Topic/CWnd::DeleteTempMap.md)|`CWinApp` 유휴 시간 처리기에서 자동으로 호출되고 `FromHandle`에서 만든 임시 `CWnd` 개체를 삭제합니다.|  
|[CWnd::DestroyWindow](../Topic/CWnd::DestroyWindow.md)|연결된 Windows 창을 제거합니다.|  
|[CWnd::Detach](../Topic/CWnd::Detach.md)|`CWnd` 개체에서 Windows 핸들을 분리하고 핸들을 반환합니다.|  
|[CWnd::DlgDirList](../Topic/CWnd::DlgDirList.md)|파일 또는 디렉터리 목록으로 목록 상자를 채웁니다.|  
|[CWnd::DlgDirListComboBox](../Topic/CWnd::DlgDirListComboBox.md)|파일 또는 디렉터리 목록으로 콤보 상자의 목록 상자를 채웁니다.|  
|[CWnd::DlgDirSelect](../Topic/CWnd::DlgDirSelect.md)|목록 상자에서 현재 선택 영역을 검색합니다.|  
|[CWnd::DlgDirSelectComboBox](../Topic/CWnd::DlgDirSelectComboBox.md)|콤보 상자의 목록 상자에서 현재 선택 영역을 검색합니다.|  
|[CWnd::DragAcceptFiles](../Topic/CWnd::DragAcceptFiles.md)|창에서 끌어온 파일을 수락할지를 나타냅니다.|  
|[CWnd::DragDetect](../Topic/CWnd::DragDetect.md)|마우스를 캡처하고 사용자가 왼쪽 단추를 놓거나, Esc 키를 누르거나, 지정된 점 주위의 끌기 사각형 밖으로 마우스를 이동할 때까지 이동을 추적합니다.|  
|[CWnd::DrawAnimatedRects](../Topic/CWnd::DrawAnimatedRects.md)|와이어프레임 사각형을 그리고 애니메이션하여 아이콘 열기 또는 창의 최소화나 최대화를 나타냅니다.|  
|[CWnd::DrawCaption](../Topic/CWnd::DrawCaption.md)|캡션을 그립니다.|  
|[CWnd::DrawMenuBar](../Topic/CWnd::DrawMenuBar.md)|메뉴 모음을 다시 그립니다.|  
|[CWnd::EnableActiveAccessibility](../Topic/CWnd::EnableActiveAccessibility.md)|사용자 정의 `Active Accessibility` 함수를 사용하도록 설정합니다.|  
|[CWnd::EnableDynamicLayout](../Topic/CWnd::EnableDynamicLayout.md)|사용자가 창의 크기를 조정하면 자식 창의 위치 및 크기가 동적으로 조정되도록 합니다.|  
|[CWnd::EnableD2DSupport](../Topic/CWnd::EnableD2DSupport.md)|창 `D2D` 지원을 사용하거나 사용하지 않도록 설정합니다.  주 창이 초기화되기 전에 이 메서드를 호출합니다.|  
|[CWnd::EnableScrollBar](../Topic/CWnd::EnableScrollBar.md)|스크롤 막대의 화살표 하나 또는 둘 다를 사용하거나 사용하지 않도록 설정합니다.|  
|[CWnd::EnableScrollBarCtrl](../Topic/CWnd::EnableScrollBarCtrl.md)|형제 스크롤 막대 컨트롤을 사용하거나 사용하지 않도록 설정합니다.|  
|[CWnd::EnableToolTips](../Topic/CWnd::EnableToolTips.md)|도구 설명 컨트롤을 사용하도록 설정합니다.|  
|[CWnd::EnableTrackingToolTips](../Topic/CWnd::EnableTrackingToolTips.md)|추적 모드에서 도구 설명 컨트롤을 사용하도록 설정합니다.|  
|[CWnd::EnableWindow](../Topic/CWnd::EnableWindow.md)|마우스 및 키보드 입력을 사용하거나 사용하지 않도록 설정합니다.|  
|[CWnd::EndModalLoop](../Topic/CWnd::EndModalLoop.md)|창의 모달 상태를 종료합니다.|  
|[CWnd::EndModalState](../Topic/CWnd::EndModalState.md)|프레임 창을 모달에서 모덜리스로 변경하려면 이 멤버 함수를 호출합니다.|  
|[CWnd::EndPaint](../Topic/CWnd::EndPaint.md)|그리기의 끝을 표시합니다.|  
|[CWnd::ExecuteDlgInit](../Topic/CWnd::ExecuteDlgInit.md)|대화 상자 리소스를 시작합니다.|  
|[CWnd::FilterToolTipMessage](../Topic/CWnd::FilterToolTipMessage.md)|대화 상자에서 컨트롤과 연결된 제목 또는 텍스트를 검색합니다.|  
|[CWnd::FindWindow](../Topic/CWnd::FindWindow.md)|창 이름 및 창 클래스로 식별되는 창의 핸들을 반환합니다.|  
|[CWnd::FindWindowEx](../Topic/CWnd::FindWindowEx.md)|창 이름 및 창 클래스로 식별되는 창의 핸들을 반환합니다.|  
|[CWnd::FlashWindow](../Topic/CWnd::FlashWindow.md)|창을 한 번 깜박입니다.|  
|[CWnd::FlashWindowEx](../Topic/CWnd::FlashWindowEx.md)|추가 기능으로 창을 깜박입니다.|  
|[CWnd::FromHandle](../Topic/CWnd::FromHandle.md)|창에 핸들을 지정한 경우 `CWnd` 개체에 대한 포인터를 반환합니다.  `CWnd` 개체가 핸들에 연결되지 않은 경우 임시 `CWnd` 개체를 만들어 연결합니다.|  
|[CWnd::FromHandlePermanent](../Topic/CWnd::FromHandlePermanent.md)|창에 핸들을 지정한 경우 `CWnd` 개체에 대한 포인터를 반환합니다.  `CWnd` 개체가 핸들에 연결되지 않은 경우 임시 `CWnd` 개체를 만들어 연결합니다.|  
|[CWnd::get\_accChild](../Topic/CWnd::get_accChild.md)|지정된 자식의 `IDispatch` 인터페이스 주소를 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::get\_accChildCount](../Topic/CWnd::get_accChildCount.md)|이 개체에 속하는 자식 수를 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::get\_accDefaultAction](../Topic/CWnd::get_accDefaultAction.md)|개체의 기본 작업을 설명하는 문자열을 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::get\_accDescription](../Topic/CWnd::get_accDescription.md)|지정한 개체의 모양을 설명하는 문자열을 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::get\_accFocus](../Topic/CWnd::get_accFocus.md)|키보드 포커스가 있는 개체를 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::get\_accHelp](../Topic/CWnd::get_accHelp.md)|개체의 **도움말** 속성 문자열을 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::get\_accHelpTopic](../Topic/CWnd::get_accHelpTopic.md)|지정된 개체와 연결된 `WinHelp` 파일의 전체 경로와 해당 파일 내의 해당 항목의 식별자를 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::get\_accKeyboardShortcut](../Topic/CWnd::get_accKeyboardShortcut.md)|지정된 개체의 바로 가기 키 또는 선택키를 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::get\_accName](../Topic/CWnd::get_accName.md)|지정된 개체의 이름을 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::get\_accParent](../Topic/CWnd::get_accParent.md)|개체 부모의 `IDispatch` 인터페이스를 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::get\_accRole](../Topic/CWnd::get_accRole.md)|지정된 개체의 역할을 설명하는 정보를 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::get\_accSelection](../Topic/CWnd::get_accSelection.md)|이 개체의 선택된 자식 개체를 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::get\_accState](../Topic/CWnd::get_accState.md)|지정된 개체의 현재 상태를 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::get\_accValue](../Topic/CWnd::get_accValue.md)|지정된 개체의 값을 검색하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::GetActiveWindow](../Topic/CWnd::GetActiveWindow.md)|활성 창을 검색합니다.|  
|[CWnd::GetAncestor](../Topic/CWnd::GetAncestor.md)|지정된 창의 상위 창 개체를 검색합니다.|  
|[CWnd::GetCapture](../Topic/CWnd::GetCapture.md)|마우스 캡처가 있는 `CWnd`를 검색합니다.|  
|[CWnd::GetCaretPos](../Topic/CWnd::GetCaretPos.md)|캐럿 현재 위치의 클라이언트 좌표를 검색합니다.|  
|[CWnd::GetCheckedRadioButton](../Topic/CWnd::GetCheckedRadioButton.md)|단추 그룹에서 현재 선택된 라디오 단추의 ID를 반환합니다.|  
|[CWnd::GetClientRect](../Topic/CWnd::GetClientRect.md)|`CWnd` 클라이언트 영역의 차원을 가져옵니다.|  
|[CWnd::GetClipboardOwner](../Topic/CWnd::GetClipboardOwner.md)|클립보드의 현재 소유자에 대한 포인터를 검색합니다.|  
|[CWnd::GetClipboardViewer](../Topic/CWnd::GetClipboardViewer.md)|클립보드 뷰어 체인에서 첫 번째 창에 대한 포인터를 검색합니다.|  
|[CWnd::GetControlUnknown](../Topic/CWnd::GetControlUnknown.md)|알 수 없는 ActiveX 컨트롤에 대한 포인터를 검색합니다.|  
|[CWnd::GetDC](../Topic/CWnd::GetDC.md)|클라이언트 영역에 대한 디스플레이 컨텍스트를 검색합니다.|  
|[CWnd::GetDCEx](../Topic/CWnd::GetDCEx.md)|클라이언트 영역에 대한 디스플레이 컨텍스트를 검색하고 그리는 동안 클리핑을 사용하도록 설정합니다.|  
|[CWnd::GetDCRenderTarget](../Topic/CWnd::GetDCRenderTarget.md)|`CWnd` 창에 대한 DC\(디바이스 컨텍스트\) 렌더링 대상을 검색합니다.|  
|[CWnd::GetDescendantWindow](../Topic/CWnd::GetDescendantWindow.md)|모든 하위 창을 검색하고 지정된 ID를 사용하는 창을 반환합니다.|  
|[CWnd::GetDesktopWindow](../Topic/CWnd::GetDesktopWindow.md)|Windows 바탕 화면 창을 검색합니다.|  
|[CWnd::GetDlgCtrlID](../Topic/CWnd::GetDlgCtrlID.md)|`CWnd`가 자식 창인 경우 이 함수를 호출하면 해당 ID 값이 반환됩니다.|  
|[CWnd::GetDlgItem](../Topic/CWnd::GetDlgItem.md)|지정된 대화 상자에서 지정된 ID를 사용하여 컨트롤을 검색합니다.|  
|[CWnd::GetDlgItemInt](../Topic/CWnd::GetDlgItemInt.md)|지정된 대화 상자에서 컨트롤의 텍스트를 정수 값으로 변환합니다.|  
|[CWnd::GetDlgItemText](../Topic/CWnd::GetDlgItemText.md)|컨트롤에 연결된 텍스트 또는 캡션을 검색합니다.|  
|[CWnd::GetDSCCursor](../Topic/CWnd::GetDSCCursor.md)|데이터 소스 컨트롤의 데이터 소스, 사용자 이름, 암호 및 SQL 속성으로 정의된 기본 커서에 대한 포인터를 검색합니다.|  
|[CWnd::GetDynamicLayout](../Topic/CWnd::GetDynamicLayout.md)|동적 레이아웃 관리자 개체에 대한 포인터를 검색합니다.|  
|[CWnd::GetExStyle](../Topic/CWnd::GetExStyle.md)|창의 확장된 스타일을 반환합니다.|  
|[CWnd::GetFocus](../Topic/CWnd::GetFocus.md)|현재 입력 포커스가 있는 `CWnd`를 검색합니다.|  
|[CWnd::GetFont](../Topic/CWnd::GetFont.md)|현재 글꼴을 검색합니다.|  
|[CWnd::GetForegroundWindow](../Topic/CWnd::GetForegroundWindow.md)|전경 창\(사용자가 현재 작업 중인 최상위 창\)에 대한 포인터를 반환합니다.|  
|[CWnd::GetIcon](../Topic/CWnd::GetIcon.md)|아이콘에 대한 핸들을 검색합니다.|  
|[CWnd::GetLastActivePopup](../Topic/CWnd::GetLastActivePopup.md)|`CWnd`가 소유한 팝업 창이 가장 최근에 활성화되었는지 확인합니다.|  
|[CWnd::GetLayeredWindowAttributes](../Topic/CWnd::GetLayeredWindowAttributes.md)|계층적 창의 불투명도 및 투명도 색상 키를 검색합니다.|  
|[CWnd::GetMenu](../Topic/CWnd::GetMenu.md)|지정된 메뉴에 대한 포인터를 검색합니다.|  
|[CWnd::GetNextDlgGroupItem](../Topic/CWnd::GetNextDlgGroupItem.md)|컨트롤 그룹 내에서 다음\(또는 이전\) 컨트롤을 검색합니다.|  
|[CWnd::GetNextDlgTabItem](../Topic/CWnd::GetNextDlgTabItem.md)|지정된 컨트롤 다음\(또는 앞\)에 오는, [WS\_TABSTOP](../../mfc/reference/window-styles.md) 스타일이 지정된 첫 번째 컨트롤을 검색합니다.|  
|[CWnd::GetNextWindow](../Topic/CWnd::GetNextWindow.md)|창 관리자의 목록에서 다음\(또는 이전\) 창을 반환합니다.|  
|[CWnd::GetOleControlSite](../Topic/CWnd::GetOleControlSite.md)|지정된 ActiveX 컨트롤에 대한 사용자 지정 사이트를 검색합니다.|  
|[CWnd::GetOpenClipboardWindow](../Topic/CWnd::GetOpenClipboardWindow.md)|현재 클립보드가 열려 있는 창에 대한 포인터를 검색합니다.|  
|[CWnd::GetOwner](../Topic/CWnd::GetOwner.md)|`CWnd`의 소유자에 대한 포인터를 검색합니다.|  
|[CWnd::GetParent](../Topic/CWnd::GetParent.md)|`CWnd`의 부모 창\(있는 경우\)을 검색합니다.|  
|[CWnd::GetParentFrame](../Topic/CWnd::GetParentFrame.md)|`CWnd` 개체의 부모 프레임 창을 검색합니다.|  
|[CWnd::GetParentOwner](../Topic/CWnd::GetParentOwner.md)|자식 창의 부모 창에 대한 포인터를 반환합니다.|  
|[CWnd::GetProperty](../Topic/CWnd::GetProperty.md)|ActiveX 컨트롤 속성을 검색합니다.|  
|[CWnd::GetRenderTarget](../Topic/CWnd::GetRenderTarget.md)|이 창에 연결된 렌더링 대상을 가져옵니다.|  
|[CWnd::GetSafeHwnd](../Topic/CWnd::GetSafeHwnd.md)|`m_hWnd`를 반환하거나, `this` 포인터가 `NULL`인 경우 `NULL`을 반환합니다.|  
|[CWnd::GetSafeOwner](../Topic/CWnd::GetSafeOwner.md)|지정된 창에 대한 안전한 소유자를 검색합니다.|  
|[CWnd::GetScrollBarCtrl](../Topic/CWnd::GetScrollBarCtrl.md)|형제 스크롤 막대 컨트롤을 반환합니다.|  
|[CWnd::GetScrollBarInfo](../Topic/CWnd::GetScrollBarInfo.md)|지정한 스크롤 막대에 대한 정보를 검색합니다.|  
|[CWnd::GetScrollInfo](../Topic/CWnd::GetScrollInfo.md)|`SCROLLINFO` 구조체에서 스크롤 막대에 대해 유지 관리하는 정보를 검색합니다.|  
|[CWnd::GetScrollLimit](../Topic/CWnd::GetScrollLimit.md)|스크롤 막대의 한계를 검색합니다.|  
|[CWnd::GetScrollPos](../Topic/CWnd::GetScrollPos.md)|스크롤 상자의 현재 위치를 검색합니다.|  
|[CWnd::GetScrollRange](../Topic/CWnd::GetScrollRange.md)|지정된 스크롤 막대에 대해 현재 최소 및 최대 스크롤 막대 위치를 복사합니다.|  
|[CWnd::GetStyle](../Topic/CWnd::GetStyle.md)|현재 창 스타일을 반환합니다.|  
|[CWnd::GetSystemMenu](../Topic/CWnd::GetSystemMenu.md)|응용 프로그램에서 복사 및 수정을 위해 컨트롤 메뉴에 액세스할 수 있도록 합니다.|  
|[CWnd::GetTitleBarInfo](../Topic/CWnd::GetTitleBarInfo.md)|지정된 제목 표시줄에 대한 정보를 검색합니다.|  
|[CWnd::GetTopLevelFrame](../Topic/CWnd::GetTopLevelFrame.md)|창의 최상위 프레임 창을 검색합니다.|  
|[CWnd::GetTopLevelOwner](../Topic/CWnd::GetTopLevelOwner.md)|최상위 창을 검색합니다.|  
|[CWnd::GetTopLevelParent](../Topic/CWnd::GetTopLevelParent.md)|창의 최상위 부모를 검색합니다.|  
|[CWnd::GetTopWindow](../Topic/CWnd::GetTopWindow.md)|`CWnd`에 속하는 첫 번째 자식 창을 반환합니다.|  
|[CWnd::GetUpdateRect](../Topic/CWnd::GetUpdateRect.md)|`CWnd` 업데이트 영역을 완전히 둘러싸는 가장 작은 사각형의 좌표를 검색합니다.|  
|[CWnd::GetUpdateRgn](../Topic/CWnd::GetUpdateRgn.md)|`CWnd` 업데이트 영역을 검색합니다.|  
|[CWnd::GetWindow](../Topic/CWnd::GetWindow.md)|이 창에 대해 지정된 관계를 갖는 창을 반환합니다.|  
|[CWnd::GetWindowContextHelpId](../Topic/CWnd::GetWindowContextHelpId.md)|도움말 컨텍스트 식별자를 검색합니다.|  
|[CWnd::GetWindowDC](../Topic/CWnd::GetWindowDC.md)|캡션 표시줄, 메뉴 및 스크롤 막대를 포함하여 전체 창에 대한 디스플레이 컨텍스트를 검색합니다.|  
|[CWnd::GetWindowedChildCount](../Topic/CWnd::GetWindowedChildCount.md)|연결된 자식 창의 수를 반환합니다.|  
|[CWnd::GetWindowInfo](../Topic/CWnd::GetWindowInfo.md)|창에 대한 정보를 반환합니다.|  
|[CWnd::GetWindowlessChildCount](../Topic/CWnd::GetWindowlessChildCount.md)|연결된 창 없는 자식 창의 수를 반환합니다.|  
|[CWnd::GetWindowPlacement](../Topic/CWnd::GetWindowPlacement.md)|창의 표시 상태와 일반\(복원됨\), 최소화 및 최대화 위치를 검색합니다.|  
|[CWnd::GetWindowRect](../Topic/CWnd::GetWindowRect.md)|`CWnd`의 화면 좌표를 가져옵니다.|  
|[CWnd::GetWindowRgn](../Topic/CWnd::GetWindowRgn.md)|창의 창 영역에 대한 복사본을 검색합니다.|  
|[CWnd::GetWindowText](../Topic/CWnd::GetWindowText.md)|창 텍스트 또는 캡션 제목\(있는 경우\)을 반환합니다.|  
|[CWnd::GetWindowTextLength](../Topic/CWnd::GetWindowTextLength.md)|창의 텍스트 또는 캡션 제목의 길이를 반환합니다.|  
|[CWnd::HideCaret](../Topic/CWnd::HideCaret.md)|디스플레이 화면에서 제거하여 캐럿을 숨깁니다.|  
|[CWnd::HiliteMenuItem](../Topic/CWnd::HiliteMenuItem.md)|최상위\(메뉴 모음\) 메뉴 항목에서 강조 표시하거나 강조 표시를 제거합니다.|  
|[CWnd::HtmlHelp](../Topic/CWnd::HtmlHelp.md)|HTMLHelp 응용 프로그램을 시작하기 위해 호출됩니다.|  
|[CWnd::Invalidate](../Topic/CWnd::Invalidate.md)|전체 클라이언트 영역을 무효화합니다.|  
|[CWnd::InvalidateRect](../Topic/CWnd::InvalidateRect.md)|현재 업데이트 영역에 지정된 사각형을 추가하여 해당 사각형 내에서 클라이언트 영역을 무효화합니다.|  
|[CWnd::InvalidateRgn](../Topic/CWnd::InvalidateRgn.md)|현재 업데이트 영역에 지정된 영역을 추가하여 해당 영역 내에서 클라이언트 영역을 무효화합니다.|  
|[CWnd::InvokeHelper](../Topic/CWnd::InvokeHelper.md)|ActiveX 컨트롤 메서드나 속성을 호출합니다.|  
|[CWnd::IsChild](../Topic/CWnd::IsChild.md)|`CWnd`가 자식 창인지 지정된 창의 다른 직계 하위 항목인지를 나타냅니다.|  
|[CWnd::IsD2DSupportEnabled](../Topic/CWnd::IsD2DSupportEnabled.md)|`D2D` 지원이 사용되는지 여부를 확인합니다.|  
|[CWnd::IsDialogMessage](../Topic/CWnd::IsDialogMessage.md)|지정된 메시지가 모덜리스 대화 상자용인지 확인하고 그럴 경우 처리합니다.|  
|[CWnd::IsDlgButtonChecked](../Topic/CWnd::IsDlgButtonChecked.md)|단추 컨트롤이 선택되어 있는지 여부를 확인합니다.|  
|[CWnd::IsDynamicLayoutEnabled](../Topic/CWnd::IsDynamicLayoutEnabled.md)|이 창에서 동적 레이아웃이 사용되는지 여부를 확인합니다.  동적 레이아웃이 사용되는 경우 사용자가 부모 창의 크기를 조정하면 자식 창의 위치 및 크기가 변경될 수 있습니다.|  
|[CWnd::IsIconic](../Topic/CWnd::IsIconic.md)|`CWnd`가 최소화\(아이콘\)되었는지 여부를 확인합니다.|  
|[CWnd::IsTouchWindow](../Topic/CWnd::IsTouchWindow.md)|`CWnd`가 터치를 지원하는지 여부를 지정합니다.|  
|[CWnd::IsWindowEnabled](../Topic/CWnd::IsWindowEnabled.md)|마우스 및 키보드 입력에 창을 사용할 수 있는지 여부를 확인합니다.|  
|[CWnd::IsWindowVisible](../Topic/CWnd::IsWindowVisible.md)|창이 표시되는지 여부를 확인합니다.|  
|[CWnd::IsZoomed](../Topic/CWnd::IsZoomed.md)|`CWnd`이 최대화되었는지 여부를 확인합니다.|  
|[CWnd::KillTimer](../Topic/CWnd::KillTimer.md)|시스템 타이머를 중지합니다.|  
|[CWnd::LockWindowUpdate](../Topic/CWnd::LockWindowUpdate.md)|지정된 창에서 그리기를 사용하지 않거나 다시 사용하도록 설정합니다.|  
|[CWnd::MapWindowPoints](../Topic/CWnd::MapWindowPoints.md)|`CWnd`의 좌표 공간에서 다른 창의 좌표 공간으로 점 집합\(맵\)을 변환합니다.|  
|[CWnd::MessageBox](../Topic/CWnd::MessageBox.md)|응용 프로그램에서 제공하는 메시지 및 캡션을 포함하는 창을 만들고 표시합니다.|  
|[CWnd::ModifyStyle](../Topic/CWnd::ModifyStyle.md)|현재 창 스타일을 수정합니다.|  
|[CWnd::ModifyStyleEx](../Topic/CWnd::ModifyStyleEx.md)|창의 확장된 스타일을 수정합니다.|  
|[CWnd::MoveWindow](../Topic/CWnd::MoveWindow.md)|`CWnd`의 위치 및 크기를 변경합니다.|  
|[CWnd::NotifyWinEvent](../Topic/CWnd::NotifyWinEvent.md)|미리 정의된 이벤트가 발생한 시스템에 신호를 보냅니다.|  
|[CWnd::OnAmbientProperty](../Topic/CWnd::OnAmbientProperty.md)|앰비언트 속성 값을 구현합니다.|  
|[CWnd::OnDrawIconicThumbnailOrLivePreview](../Topic/CWnd::OnDrawIconicThumbnailOrLivePreview.md)|Windows 7 탭 미리 보기 또는 응용 프로그램 피킹\(Peeking\)용 클라이언트에 표시할 비트맵을 가져와야 하는 경우 프레임워크에서 호출됩니다.|  
|[CWnd::OnHelp](../Topic/CWnd::OnHelp.md)|현재 컨텍스트를 사용하여 응용 프로그램 내에서 F1 도움말을 처리합니다.|  
|[CWnd::OnHelpFinder](../Topic/CWnd::OnHelpFinder.md)|`ID_HELP_FINDER` 및 `ID_DEFAULT_HELP` 명령을 처리합니다.|  
|[CWnd::OnHelpIndex](../Topic/CWnd::OnHelpIndex.md)|`ID_HELP_INDEX` 명령을 처리하고 기본 도움말 항목을 제공합니다.|  
|[CWnd::OnHelpUsing](../Topic/CWnd::OnHelpUsing.md)|`ID_HELP_USING` 명령을 처리합니다.|  
|[CWnd::OnToolHitTest](../Topic/CWnd::OnToolHitTest.md)|점이 지정된 도구의 경계 사각형에 있는지 여부를 확인하고 도구에 대한 정보를 검색합니다.|  
|[CWnd::OpenClipboard](../Topic/CWnd::OpenClipboard.md)|클립보드를 엽니다.  다른 응용 프로그램은 Windows [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) 함수가 호출될 때까지 클립보드를 수정할 수 없습니다.|  
|[CWnd::PaintWindowlessControls](../Topic/CWnd::PaintWindowlessControls.md)|컨트롤 컨테이너에서 창 없는 컨트롤을 그립니다.|  
|[CWnd::PostMessage](../Topic/CWnd::PostMessage.md)|응용 프로그램 큐에 메시지를 배치한 다음 창에서 메시지를 처리할 때까지 기다리지 않고 반환합니다.|  
|[CWnd::PreCreateWindow](../Topic/CWnd::PreCreateWindow.md)|이 `CWnd` 개체에 연결된 Windows 창을 만들기 전에 호출됩니다.|  
|[CWnd::PreSubclassWindow](../Topic/CWnd::PreSubclassWindow.md)|[SubclassWindow](../Topic/CWnd::SubclassWindow.md)가 호출되기 전에 필요한 다른 하위 클래스화가 수행되도록 허용합니다.|  
|[CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md)|`TranslateMessage` 및 `DispatchMessage` Windows 함수로 디스패치되기 전에 `CWinApp`에서 창 메시지를 필터링하는 데 사용됩니다.|  
|[CWnd::Print](../Topic/CWnd::Print.md)|지정된 디바이스 컨텍스트에서 현재 창을 그립니다.|  
|[CWnd::PrintClient](../Topic/CWnd::PrintClient.md)|지정된 디바이스 컨텍스트\(일반적으로 프린터 디바이스 컨텍스트\)에서 창을 그립니다.|  
|[CWnd::PrintWindow](../Topic/CWnd::PrintWindow.md)|지정된 디바이스 컨텍스트\(일반적으로 프린터 DC\)에 시각적 창을 복사합니다.|  
|[CWnd::RedrawWindow](../Topic/CWnd::RedrawWindow.md)|클라이언트 영역에서 지정된 사각형 또는 영역을 업데이트합니다.|  
|[CWnd::RegisterTouchWindow](../Topic/CWnd::RegisterTouchWindow.md)|창 Windows Touch 지원을 등록\/등록 취소합니다.|  
|[CWnd::ReleaseDC](../Topic/CWnd::ReleaseDC.md)|클라이언트 및 창 디바이스 컨텍스트를 해제하여 다른 응용 프로그램에서 사용하도록 확보합니다.|  
|[CWnd::RepositionBars](../Topic/CWnd::RepositionBars.md)|클라이언트 영역에서 컨트롤 막대의 위치를 변경합니다.|  
|[CWnd::RunModalLoop](../Topic/CWnd::RunModalLoop.md)|모달 상태에 있는 창에 대한 메시지를 검색, 변환 또는 디스패치합니다.|  
|[CWnd::ScreenToClient](../Topic/CWnd::ScreenToClient.md)|디스플레이에 있는 지정된 점 또는 사각형의 화면 좌표를 클라이언트 좌표로 변환합니다.|  
|[CWnd::ScrollWindow](../Topic/CWnd::ScrollWindow.md)|클라이언트 영역의 내용을 스크롤합니다.|  
|[CWnd::ScrollWindowEx](../Topic/CWnd::ScrollWindowEx.md)|클라이언트 영역의 내용을 스크롤합니다.  `ScrollWindow`와 유사하며 추가 기능을 제공합니다.|  
|[CWnd::SendChildNotifyLastMsg](../Topic/CWnd::SendChildNotifyLastMsg.md)|부모 창에서 자식 창에 알림 메시지를 제공하여 자식 창에서 작업을 처리할 수 있도록 합니다.|  
|[CWnd::SendDlgItemMessage](../Topic/CWnd::SendDlgItemMessage.md)|지정된 컨트롤에 메시지를 보냅니다.|  
|[CWnd::SendMessage](../Topic/CWnd::SendMessage.md)|`CWnd` 개체에 메시지를 보내고 메시지를 처리할 때까지 반환하지 않습니다.|  
|[CWnd::SendMessageToDescendants](../Topic/CWnd::SendMessageToDescendants.md)|창의 모든 하위 창에 메시지를 보냅니다.|  
|[CWnd::SendNotifyMessage](../Topic/CWnd::SendNotifyMessage.md)|호출 스레드에서 창을 만들었는지 여부에 따라 지정된 메시지를 창에 보내고 최대한 빨리 반환합니다.|  
|[CWnd::SetActiveWindow](../Topic/CWnd::SetActiveWindow.md)|창을 활성화합니다.|  
|[CWnd::SetCapture](../Topic/CWnd::SetCapture.md)|모든 후속 마우스 입력을 `CWnd`로 보내도록 합니다.|  
|[CWnd::SetCaretPos](../Topic/CWnd::SetCaretPos.md)|지정된 위치로 캐럿을 이동합니다.|  
|[CWnd::SetClipboardViewer](../Topic/CWnd::SetClipboardViewer.md)|클립보드의 내용이 변경될 때마다 알림을 받는 창 체인에 `CWnd`를 추가합니다.|  
|[CWnd::SetDlgCtrlID](../Topic/CWnd::SetDlgCtrlID.md)|창\(대화 상자의 컨트롤만이 아니라 모든 자식 창이 될 수 있음\)에 대해 창 또는 컨트롤 ID를 설정합니다.|  
|[CWnd::SetDlgItemInt](../Topic/CWnd::SetDlgItemInt.md)|컨트롤의 텍스트를 정수 값을 나타내는 문자열로 설정합니다.|  
|[CWnd::SetDlgItemText](../Topic/CWnd::SetDlgItemText.md)|지정된 대화 상자에서 컨트롤의 캡션 또는 텍스트를 설정합니다.|  
|[CWnd::SetFocus](../Topic/CWnd::SetFocus.md)|입력 포커스를 클레임합니다.|  
|[CWnd::SetFont](../Topic/CWnd::SetFont.md)|현재 글꼴을 설정합니다.|  
|[CWnd::SetForegroundWindow](../Topic/CWnd::SetForegroundWindow.md)|창을 만든 스레드를 전경으로 전환하고 창을 활성화합니다.|  
|[CWnd::SetIcon](../Topic/CWnd::SetIcon.md)|핸들을 특정 아이콘으로 설정합니다.|  
|[CWnd::SetLayeredWindowAttributes](../Topic/CWnd::SetLayeredWindowAttributes.md)|계층적 창의 불투명도 및 투명도 색상 키를 설정합니다.|  
|[CWnd::SetMenu](../Topic/CWnd::SetMenu.md)|메뉴를 지정된 메뉴로 설정합니다.|  
|[CWnd::SetOwner](../Topic/CWnd::SetOwner.md)|`CWnd`의 소유자를 변경합니다.|  
|[CWnd::SetParent](../Topic/CWnd::SetParent.md)|부모 창을 변경합니다.|  
|[CWnd::SetProperty](../Topic/CWnd::SetProperty.md)|ActiveX 컨트롤 속성을 설정합니다.|  
|[CWnd::SetRedraw](../Topic/CWnd::SetRedraw.md)|`CWnd`의 변경 내용을 다시 그리도록 허용하거나 변경 내용을 다시 그릴 수 없도록 방지합니다.|  
|[CWnd::SetScrollInfo](../Topic/CWnd::SetScrollInfo.md)|스크롤 막대에 대한 정보를 설정합니다.|  
|[CWnd::SetScrollPos](../Topic/CWnd::SetScrollPos.md)|스크롤 상자의 현재 위치를 설정하고, 지정된 경우 새 위치를 반영하도록 스크롤 막대를 다시 그립니다.|  
|[CWnd::SetScrollRange](../Topic/CWnd::SetScrollRange.md)|지정된 스크롤 막대에 대한 최소 및 최대 위치 값을 설정합니다.|  
|[CWnd::SetTimer](../Topic/CWnd::SetTimer.md)|트리거될 때 [WM\_TIMER](../Topic/CWnd::OnTimer.md) 메시지를 보내는 시스템 타이머를 설치합니다.|  
|[CWnd::SetWindowContextHelpId](../Topic/CWnd::SetWindowContextHelpId.md)|도움말 컨텍스트 식별자를 설정합니다.|  
|[CWnd::SetWindowPlacement](../Topic/CWnd::SetWindowPlacement.md)|창의 표시 상태와 일반\(복원됨\), 최소화 및 최대화 위치를 설정합니다.|  
|[CWnd::SetWindowPos](../Topic/CWnd::SetWindowPos.md)|자식, 팝업 및 최상위 창의 크기, 위치 및 순서를 변경합니다.|  
|[CWnd::SetWindowRgn](../Topic/CWnd::SetWindowRgn.md)|창의 영역을 설정합니다.|  
|[CWnd::SetWindowText](../Topic/CWnd::SetWindowText.md)|창 텍스트 또는 캡션 제목\(있는 경우\)을 지정된 텍스트로 설정합니다.|  
|[CWnd::ShowCaret](../Topic/CWnd::ShowCaret.md)|캐럿의 현재 위치에서 디스플레이의 캐럿을 표시합니다.  표시되면 캐럿이 자동으로 깜박이기 시작합니다.|  
|[CWnd::ShowOwnedPopups](../Topic/CWnd::ShowOwnedPopups.md)|창이 소유한 모든 팝업 창을 표시하거나 숨깁니다.|  
|[CWnd::ShowScrollBar](../Topic/CWnd::ShowScrollBar.md)|스크롤 막대를 표시하거나 숨깁니다.|  
|[CWnd::ShowWindow](../Topic/CWnd::ShowWindow.md)|창을 표시하거나 숨깁니다.|  
|[CWnd::SubclassDlgItem](../Topic/CWnd::SubclassDlgItem.md)|Windows 컨트롤을 `CWnd` 개체에 연결하고 `CWnd`의 메시지 맵을 통해 메시지를 라우팅하도록 합니다.|  
|[CWnd::SubclassWindow](../Topic/CWnd::SubclassWindow.md)|창을 `CWnd` 개체에 연결하고 `CWnd`의 메시지 맵을 통해 메시지를 라우팅하도록 합니다.|  
|[CWnd::UnlockWindowUpdate](../Topic/CWnd::UnlockWindowUpdate.md)|`CWnd::LockWindowUpdate`로 잠긴 창의 잠금을 해제합니다.|  
|[CWnd::UnsubclassWindow](../Topic/CWnd::UnsubclassWindow.md)|`CWnd`  개체에서 창을 분리합니다.|  
|[CWnd::UpdateData](../Topic/CWnd::UpdateData.md)|대화 상자에서 데이터를 초기화하거나 검색합니다.|  
|[CWnd::UpdateDialogControls](../Topic/CWnd::UpdateDialogControls.md)|대화 상자 단추 및 다른 컨트롤의 상태를 업데이트하기 위해 호출합니다.|  
|[CWnd::UpdateLayeredWindow](../Topic/CWnd::UpdateLayeredWindow.md)|계층적 창의 위치, 크기, 모양, 내용 및 투명도를 업데이트합니다.|  
|[CWnd::UpdateWindow](../Topic/CWnd::UpdateWindow.md)|클라이언트 영역을 업데이트합니다.|  
|[CWnd::ValidateRect](../Topic/CWnd::ValidateRect.md)|현재 업데이트 영역에서 사각형을 제거하여 지정된 사각형 내에서 클라이언트 영역의 유효성을 검색합니다.|  
|[CWnd::ValidateRgn](../Topic/CWnd::ValidateRgn.md)|현재 업데이트 영역에서 영역을 제거하여 지정된 영역 내에서 클라이언트 영역의 유효성을 검사합니다.|  
|[CWnd::WindowFromPoint](../Topic/CWnd::WindowFromPoint.md)|지정된 점을 포함하는 창을 식별합니다.|  
|[CWnd::WinHelp](../Topic/CWnd::WinHelp.md)|WinHelp 응용 프로그램을 시작하기 위해 호출됩니다.|  
  
### Protected 메서드  
  
|이름|설명|  
|--------|--------|  
|[CWnd::Default](../Topic/CWnd::Default.md)|기본 창 프로시저를 호출하여 응용 프로그램에서 처리하지 않는 모든 창 메시지에 대해 기본 처리를 제공합니다.|  
|[CWnd::DefWindowProc](../Topic/CWnd::DefWindowProc.md)|기본 창 프로시저를 호출하여 응용 프로그램에서 처리하지 않는 모든 창 메시지에 대해 기본 처리를 제공합니다.|  
|[CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md)|대화 상자 데이터 교환 및 유효성 검사용입니다.  `UpdateData`에 의해 호출됩니다.|  
|[CWnd::GetCurrentMessage](../Topic/CWnd::GetCurrentMessage.md)|이 창에서 현재 처리 중인 메시지에 대한 포인터를 반환합니다.  `On`*Message* 메시지 처리기 멤버 함수에서만 호출되어야 합니다.|  
|[CWnd::InitDynamicLayout](../Topic/CWnd::InitDynamicLayout.md)|창에 대한 동적 레이아웃을 초기화하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::LoadDynamicLayoutResource](../Topic/CWnd::LoadDynamicLayoutResource.md)|리소스 파일에서 동적 레이아웃 정보를 로드합니다.|  
|[CWnd::OnActivate](../Topic/CWnd::OnActivate.md)|`CWnd`가 활성화되거나 비활성화되고 있을 때 호출됩니다.|  
|[CWnd::OnActivateApp](../Topic/CWnd::OnActivateApp.md)|응용 프로그램이 활성화되거나 비활성화되려고 할 때 호출됩니다.|  
|[CWnd::OnAppCommand](../Topic/CWnd::OnAppCommand.md)|사용자가 응용 프로그램 명령 이벤트를 생성할 때 호출됩니다.|  
|[CWnd::OnAskCbFormatName](../Topic/CWnd::OnAskCbFormatName.md)|클립보드 소유자가 클립보드 내용을 표시할 때 클립보드 뷰어 응용 프로그램에서 호출됩니다.|  
|[CWnd::OnCancelMode](../Topic/CWnd::OnCancelMode.md)|`CWnd`에서 마우스 캡처와 같은 내부 모드를 취소할 수 있도록 허용하기 위해 호출됩니다.|  
|[CWnd::OnCaptureChanged](../Topic/CWnd::OnCaptureChanged.md)|마우스 캡처가 손실되고 있는 창에 메시지를 보냅니다.|  
|[CWnd::OnChangeCbChain](../Topic/CWnd::OnChangeCbChain.md)|지정된 창이 체인에서 제거됨을 알립니다.|  
|[CWnd::OnChangeUIState](../Topic/CWnd::OnChangeUIState.md)|UI\(사용자 인터페이스\) 상태를 변경해야 할 때 호출됩니다.|  
|[CWnd::OnChar](../Topic/CWnd::OnChar.md)|키 입력이 시스템 문자 이외의 문자로 변환될 때 호출됩니다.|  
|[CWnd::OnCharToItem](../Topic/CWnd::OnCharToItem.md)|[WM\_CHAR](../Topic/CWnd::OnChar.md) 메시지에 대한 응답으로 [LBS\_WANTKEYBOARDINPUT](../../mfc/reference/list-box-styles.md) 스타일을 사용하는 자식 목록 상자에서 호출됩니다.|  
|[CWnd::OnChildActivate](../Topic/CWnd::OnChildActivate.md)|`CWnd`의 크기 또는 위치가 변경되거나 `CWnd`가 활성화될 때마다 MDI\(다중 문서 인터페이스\) 자식 창에 대해 호출됩니다.|  
|[CWnd::OnChildNotify](../Topic/CWnd::OnChildNotify.md)|알림 컨트롤이 컨트롤 알림에 응답할 수 있는 기회를 제공하기 위해 부모 창에서 호출됩니다.|  
|[CWnd::OnClipboardUpdate](../Topic/CWnd::OnClipboardUpdate.md)|클립보드의 내용이 변경될 때 호출됩니다.|  
|[CWnd::OnClose](../Topic/CWnd::OnClose.md)|`CWnd`를 닫아야 한다는 신호로 호출됩니다.|  
|[CWnd::OnColorizationColorChanged](../Topic/CWnd::OnColorizationColorChanged.md)|비클라이언트 영역에 대한 렌더링 정책이 변경된 경우 호출됩니다.|  
|[CWnd::OnCommand](../Topic/CWnd::OnCommand.md)|사용자가 명령을 선택할 때 호출됩니다.|  
|[CWnd::OnCompacting](../Topic/CWnd::OnCompacting.md)|Windows에서 시스템 메모리 부족을 감지할 때 호출됩니다.|  
|[CWnd::OnCompareItem](../Topic/CWnd::OnCompareItem.md)|정렬된 소유자 그리기 자식 콤보 상자 또는 목록 상자에서 새 항목의 상대 위치를 확인하기 위해 호출됩니다.|  
|[CWnd::OnCompositionChanged](../Topic/CWnd::OnCompositionChanged.md)|DWM\(바탕 화면 창 관리자\) 컴퍼지션을 사용하거나 사용하지 않도록 설정할 때 모든 최상위 창에 대해 호출됩니다.|  
|[CWnd::OnContextMenu](../Topic/CWnd::OnContextMenu.md)|사용자가 창에서 오른쪽 마우스 단추를 클릭할 때 호출됩니다.|  
|[CWnd::OnCopyData](../Topic/CWnd::OnCopyData.md)|응용 프로그램 간에 데이터를 복사합니다.|  
|[CWnd::OnCreate](../Topic/CWnd::OnCreate.md)|창 만들기의 일부로 호출됩니다.|  
|[CWnd::OnCtlColor](../Topic/CWnd::OnCtlColor.md)|컨트롤을 그리려고 할 때 `CWnd`가 컨트롤의 부모인 경우 호출됩니다.|  
|[CWnd::OnDeadChar](../Topic/CWnd::OnDeadChar.md)|키 입력이 비시스템 데드 문자\(예: 악센트 문자\)로 변환될 때 호출됩니다.|  
|[CWnd::OnDeleteItem](../Topic/CWnd::OnDeleteItem.md)|소유자 그리기 자식 목록 상자 또는 콤보 상자가 제거되거나 컨트롤에서 항목이 제거될 때 호출됩니다.|  
|[CWnd::OnDestroy](../Topic/CWnd::OnDestroy.md)|`CWnd`가 제거되고 있을 때 호출됩니다.|  
|[CWnd::OnDestroyClipboard](../Topic/CWnd::OnDestroyClipboard.md)|Windows [EmptyClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649037) 함수를 호출하여 클립보드를 비울 때 호출됩니다.|  
|[CWnd::OnDeviceChange](../Topic/CWnd::OnDeviceChange.md)|장치 또는 컴퓨터의 하드웨어 구성 변경을 응용 프로그램 또는 장치 드라이버에 알립니다.|  
|[CWnd::OnDevModeChange](../Topic/CWnd::OnDevModeChange.md)|사용자가 장치 모드 설정을 변경할 때 모든 최상위 창에 대해 호출됩니다.|  
|[CWnd::OnDrawClipboard](../Topic/CWnd::OnDrawClipboard.md)|클립보드의 내용이 변경될 때 호출됩니다.|  
|[CWnd::OnDrawItem](../Topic/CWnd::OnDrawItem.md)|소유자 그리기 자식 단추 컨트롤, 콤보 상자 컨트롤, 목록 상자 컨트롤 또는 메뉴의 시각적 측면을 그려야 할 때 호출됩니다.|  
|[CWnd::OnDropFiles](../Topic/CWnd::OnDropFiles.md)|삭제된 파일의 수신자로 자신을 등록한 창에 대해 사용자가 왼쪽 마우스 단추를 놓을 때 호출됩니다.|  
|[CWnd::OnEnable](../Topic/CWnd::OnEnable.md)|`CWnd`가 사용하거나 사용하지 않도록 설정될 때 호출됩니다.|  
|[CWnd::OnEndSession](../Topic/CWnd::OnEndSession.md)|세션이 종료되고 있을 때 호출됩니다.|  
|[CWnd::OnEnterIdle](../Topic/CWnd::OnEnterIdle.md)|모달 대화 상자 또는 메뉴가 유휴 상태로 전환하고 있음을 응용 프로그램의 주 창 프로시저에 알리기 위해 호출됩니다.|  
|[CWnd::OnEnterMenuLoop](../Topic/CWnd::OnEnterMenuLoop.md)|메뉴 모달 루프가 시작된 경우 호출됩니다.|  
|[CWnd::OnEnterSizeMove](../Topic/CWnd::OnEnterSizeMove.md)|영향을 받는 창이 모달 루프의 이동 또는 크기 조정을 시작한 후 호출됩니다.|  
|[CWnd::OnEraseBkgnd](../Topic/CWnd::OnEraseBkgnd.md)|창 배경을 지워야 하는 경우 호출됩니다.|  
|[CWnd::OnExitMenuLoop](../Topic/CWnd::OnExitMenuLoop.md)|메뉴 모달 루프가 종료된 경우 호출됩니다.|  
|[CWnd::OnExitSizeMove](../Topic/CWnd::OnExitSizeMove.md)|영향을 받는 창이 모달 루프의 이동 또는 코기 조정을 종료한 후 호출됩니다.|  
|[CWnd::OnFontChange](../Topic/CWnd::OnFontChange.md)|글꼴 리소스 풀이 변경될 때 호출됩니다.|  
|[CWnd::OnGetDlgCode](../Topic/CWnd::OnGetDlgCode.md)|컨트롤에서 화살표 키 및 Tab 키 입력 자체를 처리할 수 있도록 컨트롤에 대해 호출됩니다.|  
|[CWnd::OnGetMinMaxInfo](../Topic/CWnd::OnGetMinMaxInfo.md)|Windows에서 최대화된 위치 또는 크기, 최소 또는 최대 추적 크기를 알고 있어야 할 때마다 호출됩니다.|  
|[CWnd::OnHelpInfo](../Topic/CWnd::OnHelpInfo.md)|사용자가 F1 키를 누를 때 프레임워크에서 호출됩니다.|  
|[CWnd::OnHotKey](../Topic/CWnd::OnHotKey.md)|사용자가 시스템 차원 바로 가기 키를 누를 때 호출됩니다.|  
|[CWnd::OnHScroll](../Topic/CWnd::OnHScroll.md)|사용자가 `CWnd`의 가로 스크롤 막대를 클릭할 때 호출됩니다.|  
|[CWnd::OnHScrollClipboard](../Topic/CWnd::OnHScrollClipboard.md)|클립보드 소유자가 클립보드 이미지를 스크롤하고, 적절한 섹션을 무효화하고, 스크롤 막대 값을 업데이트해야 하는 경우 호출됩니다.|  
|[CWnd::OnIconEraseBkgnd](../Topic/CWnd::OnIconEraseBkgnd.md)|`CWnd`가 최소화\(아이콘\)되고 아이콘을 그리기 전에 아이콘의 배경을 채워야 하는 경우 호출됩니다.|  
|[CWnd::OnInitMenu](../Topic/CWnd::OnInitMenu.md)|메뉴가 활성화되려고 할 때 호출됩니다.|  
|[CWnd::OnInitMenuPopup](../Topic/CWnd::OnInitMenuPopup.md)|팝업 메뉴가 활성화되려고 할 때 호출됩니다.|  
|[CWnd::OnInputDeviceChange](../Topic/CWnd::OnInputDeviceChange.md)|시스템에서 I\/O 장치를 추가하거나 제거할 때 호출됩니다.|  
|[CWnd::OnInputLangChange](../Topic/CWnd::OnInputLangChange.md)|응용 프로그램의 입력 언어가 변경된 후 호출됩니다.|  
|[CWnd::OnInputLangChangeRequest](../Topic/CWnd::OnInputLangChangeRequest.md)|사용자가 새 입력 언어를 선택할 때 호출됩니다.|  
|[CWnd::OnKeyDown](../Topic/CWnd::OnKeyDown.md)|시스템 키 이외의 키를 누를 때 호출됩니다.|  
|[CWnd::OnKeyUp](../Topic/CWnd::OnKeyUp.md)|시스템 키 이외의 키를 놓을 때 호출됩니다.|  
|[CWnd::OnKillFocus](../Topic/CWnd::OnKillFocus.md)|`CWnd`가 입력 포커스를 잃기 직전에 호출됩니다.|  
|[CWnd::OnLButtonDblClk](../Topic/CWnd::OnLButtonDblClk.md)|사용자가 왼쪽 마우스 단추를 두 번 클릭할 때 호출됩니다.|  
|[CWnd::OnLButtonDown](../Topic/CWnd::OnLButtonDown.md)|사용자가 왼쪽 마우스 단추를 누를 때 호출됩니다.|  
|[CWnd::OnLButtonUp](../Topic/CWnd::OnLButtonUp.md)|사용자가 왼쪽 마우스 단추를 놓을 때 호출됩니다.|  
|[CWnd::OnMButtonDblClk](../Topic/CWnd::OnMButtonDblClk.md)|사용자가 마우스 가운데 단추를 두 번 클릭할 때 호출됩니다.|  
|[CWnd::OnMButtonDown](../Topic/CWnd::OnMButtonDown.md)|사용자가 마우스 가운데 단추를 누를 때 호출됩니다.|  
|[CWnd::OnMButtonUp](../Topic/CWnd::OnMButtonUp.md)|사용자가 마우스 가운데 단추를 놓을 때 호출됩니다.|  
|[CWnd::OnMDIActivate](../Topic/CWnd::OnMDIActivate.md)|MDI 자식 창이 활성화되거나 비활성화될 때 호출됩니다.|  
|[CWnd::OnMeasureItem](../Topic/CWnd::OnMeasureItem.md)|컨트롤을 만들 때 소유자 그리기 자식 콤보 상자, 목록 상자 또는 메뉴 항목에 대해 호출됩니다.  `CWnd`가 Windows에 컨트롤의 크기를 알립니다.|  
|[CWnd::OnMenuChar](../Topic/CWnd::OnMenuChar.md)|사용자가 현재 메뉴의 미리 정의된 니모닉과 일치하지 않는 메뉴 니모닉 문자를 누를 때 호출됩니다.|  
|[CWnd::OnMenuDrag](../Topic/CWnd::OnMenuDrag.md)|사용자가 메뉴 항목을 끌기 시작하면 호출됩니다.|  
|[CWnd::OnMenuGetObject](../Topic/CWnd::OnMenuGetObject.md)|마우스 커서를 메뉴 항목으로 가져가거나 항목의 가운데에서 항목의 위 또는 아래로 이동할 때 호출됩니다.|  
|[CWnd::OnMenuRButtonUp](../Topic/CWnd::OnMenuRButtonUp.md)|커서가 메뉴 항목 위에 있는 동안 사용자가 마우스 오른쪽 단추를 놓을 때 호출됩니다.|  
|[CWnd::OnMenuSelect](../Topic/CWnd::OnMenuSelect.md)|사용자가 메뉴 항목을 선택할 때 호출됩니다.|  
|[CWnd::OnMouseActivate](../Topic/CWnd::OnMouseActivate.md)|커서가 비활성 창에 있을 때 사용자가 마우스 단추를 누르면 호출됩니다.|  
|[CWnd::OnMouseHover](../Topic/CWnd::OnMouseHover.md)|이전 [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265) 호출에서 지정된 기간 동안 커서로 창의 클라이언트 영역을 가리킬 때 호출됩니다.|  
|[CWnd::OnMouseHWheel](../Topic/CWnd::OnMouseHWheel.md)|현재 창이 DWM\(바탕 화면 창 관리자\)에 의해 구성되고 해당 창이 최대화되면 호출됩니다.|  
|[CWnd::OnMouseLeave](../Topic/CWnd::OnMouseLeave.md)|커서가 이전 [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265) 호출에서 지정된 창의 클라이언트 영역에서 벗어날 때 호출됩니다.|  
|[CWnd::OnMouseMove](../Topic/CWnd::OnMouseMove.md)|마우스 커서가 이동할 때 호출됩니다.|  
|[CWnd::OnMouseWheel](../Topic/CWnd::OnMouseWheel.md)|사용자가 마우스 휠을 회전할 때 호출됩니다.  Windows NT 4.0 메시지 처리를 사용합니다.|  
|[CWnd::OnMove](../Topic/CWnd::OnMove.md)|`CWnd`의 위치가 변경된 후 호출됩니다.|  
|[CWnd::OnMoving](../Topic/CWnd::OnMoving.md)|사용자가 `CWnd` 개체를 이동하고 있음을 나타냅니다.|  
|[CWnd::OnNcActivate](../Topic/CWnd::OnNcActivate.md)|활성 또는 비활성 상태를 나타내려면 비클라이언트 영역을 변경해야 하는 경우 호출됩니다.|  
|[CWnd::OnNcCalcSize](../Topic/CWnd::OnNcCalcSize.md)|클라이언트 영역의 크기 및 위치를 계산해야 하는 경우 호출됩니다.|  
|[CWnd::OnNcCreate](../Topic/CWnd::OnNcCreate.md)|비클라이언트 영역을 만들 때 [OnCreate](../Topic/CWnd::OnCreate.md) 이전에 호출됩니다.|  
|[CWnd::OnNcDestroy](../Topic/CWnd::OnNcDestroy.md)|비클라이언트 영역을 제거할 때 호출됩니다.|  
|[CWnd::OnNcHitTest](../Topic/CWnd::OnNcHitTest.md)|`CWnd`가 커서를 포함하거나 `SetCapture`를 사용하여 마우스 입력을 캡처한 경우 마우스가 이동할 때마다 Windows에서 호출됩니다.|  
|[CWnd::OnNcLButtonDblClk](../Topic/CWnd::OnNcLButtonDblClk.md)|커서가 `CWnd`의 비클라이언트 영역 내에 있는 동안 사용자가 왼쪽 마우스 단추를 두 번 클릭하면 호출됩니다.|  
|[CWnd::OnNcLButtonDown](../Topic/CWnd::OnNcLButtonDown.md)|커서가 `CWnd`의 비클라이언트 영역 내에 있는 동안 사용자가 왼쪽 마우스 단추를 누르면 호출됩니다.|  
|[CWnd::OnNcLButtonUp](../Topic/CWnd::OnNcLButtonUp.md)|커서가 `CWnd`의 비클라이언트 영역 내에 있는 동안 사용자가 왼쪽 마우스 단추를 놓으면 호출됩니다.|  
|[CWnd::OnNcMButtonDblClk](../Topic/CWnd::OnNcMButtonDblClk.md)|커서가 `CWnd`의 비클라이언트 영역 내에 있는 동안 사용자가 가운데 마우스 단추를 두 번 클릭하면 호출됩니다.|  
|[CWnd::OnNcMButtonDown](../Topic/CWnd::OnNcMButtonDown.md)|커서가 `CWnd`의 비클라이언트 영역 내에 있는 동안 사용자가 가운데 마우스 단추를 누르면 호출됩니다.|  
|[CWnd::OnNcMButtonUp](../Topic/CWnd::OnNcMButtonUp.md)|커서가 `CWnd`의 비클라이언트 영역 내에 있는 동안 사용자가 가운데 마우스 단추를 놓으면 호출됩니다.|  
|[CWnd::OnNcMouseHover](../Topic/CWnd::OnNcMouseHover.md)|이전 [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265) 호출에서 지정된 기간 동안 커서로 창의 비클라이언트 영역을 가리킬 때 호출됩니다.|  
|[CWnd::OnNcMouseLeave](../Topic/CWnd::OnNcMouseLeave.md)|커서가 이전 [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265) 호출에서 지정된 창의 비클라이언트 영역에서 벗어날 때 프레임워크에서 이 멤버 함수를 호출합니다.|  
|[CWnd::OnNcMouseMove](../Topic/CWnd::OnNcMouseMove.md)|커서가 `CWnd`의 비클라이언트 영역 내에서 이동할 때 호출됩니다.|  
|[CWnd::OnNcPaint](../Topic/CWnd::OnNcPaint.md)|비클라이언트 영역을 그려야 하는 경우 호출됩니다.|  
|[CWnd::OnNcRButtonDblClk](../Topic/CWnd::OnNcRButtonDblClk.md)|커서가 `CWnd`의 비클라이언트 영역 내에 있는 동안 사용자가 오른쪽 마우스 단추를 두 번 클릭하면 호출됩니다.|  
|[CWnd::OnNcRButtonDown](../Topic/CWnd::OnNcRButtonDown.md)|커서가 `CWnd`의 비클라이언트 영역 내에 있는 동안 사용자가 오른쪽 마우스 단추를 누르면 호출됩니다.|  
|[CWnd::OnNcRButtonUp](../Topic/CWnd::OnNcRButtonUp.md)|커서가 `CWnd`의 비클라이언트 영역 내에 있는 동안 사용자가 오른쪽 마우스 단추를 놓으면 호출됩니다.|  
|[CWnd::OnNcRenderingChanged](../Topic/CWnd::OnNcRenderingChanged.md)|비클라이언트 영역에 대한 렌더링 정책이 변경된 경우 호출됩니다.|  
|[CWnd::OnNcXButtonDblClk](../Topic/CWnd::OnNcXButtonDblClk.md)|커서가 창의 비클라이언트 영역에 있는 동안 사용자가 XBUTTON1 또는 XBUTTON2를 두 번 클릭하면 호출됩니다.|  
|[CWnd::OnNcXButtonDown](../Topic/CWnd::OnNcXButtonDown.md)|커서가 창의 비클라이언트 영역에 있는 동안 사용자가 마우스의 XBUTTON1 또는 XBUTTON2를 누르면 호출됩니다.|  
|[CWnd::OnNcXButtonUp](../Topic/CWnd::OnNcXButtonUp.md)|커서가 창의 비클라이언트 영역에 있는 동안 사용자가 XBUTTON1 또는 XBUTTON2를 놓으면 호출됩니다.|  
|[CWnd::OnNextMenu](../Topic/CWnd::OnNextMenu.md)|오른쪽 또는 왼쪽 화살표 키를 사용하여 메뉴 모음과 시스템 메뉴 간을 전환할 때 호출됩니다.|  
|[CWnd::OnNotify](../Topic/CWnd::OnNotify.md)|해당 컨트롤 중 하나에서 이벤트가 발생했거나 컨트롤에 정보가 필요함을 부모 창에 알리기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::OnNotifyFormat](../Topic/CWnd::OnNotifyFormat.md)|현재 창에서 WM\_NOTIFY 알림 메시지의 ANSI 또는 유니코드 구조를 허용할지 여부를 결정하기 위해 호출됩니다.|  
|[CWnd::OnPaint](../Topic/CWnd::OnPaint.md)|창의 일부를 다시 그리기 위해 호출됩니다.|  
|[CWnd::OnPaintClipboard](../Topic/CWnd::OnPaintClipboard.md)|클립보드 뷰어의 클라이언트 영역을 다시 그려야 할 때 호출됩니다.|  
|[CWnd::OnPaletteChanged](../Topic/CWnd::OnPaletteChanged.md)|색상표를 사용하는 창에서 논리 팔레트를 나타내고 해당 클라이언트 영역을 업데이트하도록 허용하기 위해 호출됩니다.|  
|[CWnd::OnPaletteIsChanging](../Topic/CWnd::OnPaletteIsChanging.md)|응용 프로그램에서 논리 팔레트를 나타내려고 하는 경우 다른 응용 프로그램에 알립니다.|  
|[CWnd::OnParentNotify](../Topic/CWnd::OnParentNotify.md)|자식 창을 만들거나 제거할 때 또는 커서가 자식 창 위에 있는 동안 사용자가 마우스 단추를 클릭할 때 호출됩니다.|  
|[CWnd::OnPowerBroadcast](../Topic/CWnd::OnPowerBroadcast.md)|전원 관리 이벤트가 발생할 때 호출됩니다.|  
|[CWnd::OnQueryDragIcon](../Topic/CWnd::OnQueryDragIcon.md)|사용자가 최소화\(아이콘\)된 `CWnd`를 끌려고 할 때 호출됩니다.|  
|[CWnd::OnQueryEndSession](../Topic/CWnd::OnQueryEndSession.md)|사용자가 Windows 세션을 종료하도록 선택할 때 호출됩니다.|  
|[CWnd::OnQueryNewPalette](../Topic/CWnd::OnQueryNewPalette.md)|입력 포커스를 수신하려고 함을 `CWnd`에 알립니다.|  
|[CWnd::OnQueryOpen](../Topic/CWnd::OnQueryOpen.md)|`CWnd`가 아이콘이고 사용자가 아이콘을 열도록 요청할 때 호출됩니다.|  
|[CWnd::OnQueryUIState](../Topic/CWnd::OnQueryUIState.md)|창에 대한 UI\(사용자 인터페이스\) 상태를 검색 하기 위해 호출됩니다.|  
|[CWnd::OnRawInput](../Topic/CWnd::OnRawInput.md)|현재 창에서 원시 입력을 가져올 때 호출됩니다.|  
|[CWnd::OnRButtonDblClk](../Topic/CWnd::OnRButtonDblClk.md)|사용자가 오른쪽 마우스 단추를 두 번 클릭할 때 호출됩니다.|  
|[CWnd::OnRButtonDown](../Topic/CWnd::OnRButtonDown.md)|사용자가 오른쪽 마우스 단추를 누를 때 호출됩니다.|  
|[CWnd::OnRButtonUp](../Topic/CWnd::OnRButtonUp.md)|사용자가 오른쪽 마우스 단추를 놓을 때 호출됩니다.|  
|[CWnd::OnRenderAllFormats](../Topic/CWnd::OnRenderAllFormats.md)|소유자 응용 프로그램이 제거되고 있고 모든 형식을 렌더링해야 하는 경우 호출됩니다.|  
|[CWnd::OnRenderFormat](../Topic/CWnd::OnRenderFormat.md)|렌더링이 지연된 특정 형식을 렌더링해야 하는 경우 클립보드 소유자에 대해 호출됩니다.|  
|[CWnd::OnSessionChange](../Topic/CWnd::OnSessionChange.md)|세션 상태의 변경을 응용 프로그램에 알리기 위해 호출됩니다.|  
|[CWnd::OnSetCursor](../Topic/CWnd::OnSetCursor.md)|마우스 입력이 캡처되지 않고 마우스로 창 내에서 커서를 이동하는 경우 호출됩니다.|  
|[CWnd::OnSetFocus](../Topic/CWnd::OnSetFocus.md)|`CWnd`가 입력 포커스를 얻은 후 호출됩니다.|  
|[CWnd::OnSettingChange](../Topic/CWnd::OnSettingChange.md)|Win32 `SystemParametersInfo` 함수가 시스템 차원 설정을 변경할 때 호출됩니다.|  
|[CWnd::OnShowWindow](../Topic/CWnd::OnShowWindow.md)|`CWnd`을 숨기거나 표시해야 할 때 호출됩니다.|  
|[CWnd::OnSize](../Topic/CWnd::OnSize.md)|`CWnd`의 크기가 변경된 후 호출됩니다.|  
|[CWnd::OnSizeClipboard](../Topic/CWnd::OnSizeClipboard.md)|클립보드 뷰어 창의 클라이언트 영역 크기가 변경된 경우 호출됩니다.|  
|[CWnd::OnSizing](../Topic/CWnd::OnSizing.md)|사용자가 사각형의 크기를 조정하고 있음을 나타냅니다.|  
|[CWnd::OnSpoolerStatus](../Topic/CWnd::OnSpoolerStatus.md)|인쇄 관리자 큐에서 작업이 추가되거나 제거될 때마다 인쇄 관리자에서 호출됩니다.|  
|[CWnd::OnStyleChanged](../Topic/CWnd::OnStyleChanged.md)|[SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) Windows 함수에서 하나 이상의 창 스타일을 변경했음을 나타냅니다.|  
|[CWnd::OnStyleChanging](../Topic/CWnd::OnStyleChanging.md)|[SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) Windows 함수에서 하나 이상의 창 스타일을 변경하려고 함을 나타냅니다.|  
|[CWnd::OnSysChar](../Topic/CWnd::OnSysChar.md)|키 입력이 시스템 문자로 변환될 때 호출됩니다.|  
|[CWnd::OnSysColorChange](../Topic/CWnd::OnSysColorChange.md)|시스템 색 설정이 변경될 때 모든 최상위 창에 대해 호출됩니다.|  
|[CWnd::OnSysCommand](../Topic/CWnd::OnSysCommand.md)|사용자가 컨트롤 메뉴에서 명령을 선택할 때 또는 사용자가 최대화 또는 최소화 단추를 선택할 때 호출됩니다.|  
|[CWnd::OnSysDeadChar](../Topic/CWnd::OnSysDeadChar.md)|키 입력이 시스템 데드 문자\(예: 악센트 문자\)로 변환될 때 호출됩니다.|  
|[CWnd::OnSysKeyDown](../Topic/CWnd::OnSysKeyDown.md)|사용자가 Alt 키를 누르고 있다가 다른 키를 누를 때 호출됩니다.|  
|[CWnd::OnSysKeyUp](../Topic/CWnd::OnSysKeyUp.md)|사용자가 Alt 키를 누른 상태에서 눌렀던 키를 놓을 때 호출됩니다.|  
|[CWnd::OnTCard](../Topic/CWnd::OnTCard.md)|사용자가 만들 수 있는 단추를 클릭하면 호출됩니다.|  
|[CWnd::OnTimeChange](../Topic/CWnd::OnTimeChange.md)|시스템 시간이 변경된 후 모든 최상위 창에 대해 호출됩니다.|  
|[CWnd::OnTimer](../Topic/CWnd::OnTimer.md)|[SetTimer](../Topic/CWnd::SetTimer.md)에 지정된 각 간격 후에 호출됩니다.|  
|[CWnd::OnTouchInput](../Topic/CWnd::OnTouchInput.md)|Windows Touch에서 단일 입력을 처리합니다.|  
|[CWnd::OnTouchInputs](../Topic/CWnd::OnTouchInputs.md)|Windows Touch에서 입력을 처리합니다.|  
|[CWnd::OnUniChar](../Topic/CWnd::OnUniChar.md)|키를 누를 때 호출됩니다.  즉, 현재 창에 키보드 포커스가 있고 [WM\_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280) 메시지가 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 함수에 의해 변환됩니다.|  
|[CWnd::OnUnInitMenuPopup](../Topic/CWnd::OnUnInitMenuPopup.md)|드롭다운 메뉴나 하위 메뉴가 제거될 때 호출됩니다.|  
|[CWnd::OnUpdateUIState](../Topic/CWnd::OnUpdateUIState.md)|지정된 창 및 모든 자식 창에 대한 UI\(사용자 인터페이스\) 상태를 변경하기 위해 호출됩니다.|  
|[CWnd::OnUserChanged](../Topic/CWnd::OnUserChanged.md)|사용자가 로그온하거나 로드오프한 후에 호출됩니다.|  
|[CWnd::OnVKeyToItem](../Topic/CWnd::OnVKeyToItem.md)|`CWnd`가 소유한 목록 상자에 의해 [WM\_KEYDOWN](../Topic/CWnd::OnKeyDown.md) 메시지에 대한 응답으로 호출됩니다.|  
|[CWnd::OnVScroll](../Topic/CWnd::OnVScroll.md)|사용자가 창의 세로 스크롤 막대를 클릭할 때 호출됩니다.|  
|[CWnd::OnVScrollClipboard](../Topic/CWnd::OnVScrollClipboard.md)|소유자가 클립보드 이미지를 스크롤하고, 적절한 섹션을 무효화하고, 스크롤 막대 값을 업데이트해야 하는 경우 호출됩니다.|  
|[CWnd::OnWindowPosChanged](../Topic/CWnd::OnWindowPosChanged.md)|[SetWindowPos](../Topic/CWnd::SetWindowPos.md) 또는 다른 창 관리 함수 호출의 결과로 크기, 위치 또는 Z 순서가 변경된 경우 호출됩니다.|  
|[CWnd::OnWindowPosChanging](../Topic/CWnd::OnWindowPosChanging.md)|[SetWindowPos](../Topic/CWnd::SetWindowPos.md) 또는 다른 창 관리 함수 호출의 결과로 크기, 위치 또는 Z 순서가 변경되려고 할 때 호출됩니다.|  
|[CWnd::OnWinIniChange](../Topic/CWnd::OnWinIniChange.md)|Windows 초기화 파일 WIN.INI가 변경된 후 모든 최상위 창에 대해 호출됩니다.|  
|[CWnd::OnWndMsg](../Topic/CWnd::OnWndMsg.md)|Windows 메시지가 처리되었는지를 나타냅니다.|  
|[CWnd::OnXButtonDblClk](../Topic/CWnd::OnXButtonDblClk.md)|커서가 창의 클라이언트 영역에 있는 동안 사용자가 XBUTTON1 또는 XBUTTON2를 두 번 클릭하면 호출됩니다.|  
|[CWnd::OnXButtonDown](../Topic/CWnd::OnXButtonDown.md)|커서가 창의 클라이언트 영역에 있는 동안 사용자가 XBUTTON1 또는 XBUTTON2를 누르면 호출됩니다.|  
|[CWnd::OnXButtonUp](../Topic/CWnd::OnXButtonUp.md)|커서가 창의 클라이언트 영역에 있는 동안 사용자가 XBUTTON1 또는 XBUTTON2를 놓으면 호출됩니다.|  
|[CWnd::PostNcDestroy](../Topic/CWnd::PostNcDestroy.md)|이 가상 함수는 창이 제거된 후 기본 [OnNcDestroy](../Topic/CWnd::OnNcDestroy.md) 함수에 의해 호출됩니다.|  
|[CWnd::ReflectChildNotify](../Topic/CWnd::ReflectChildNotify.md)|소스에 대한 메시지를 반영하는 도우미 함수입니다.|  
|[CWnd::ReflectLastMsg](../Topic/CWnd::ReflectLastMsg.md)|자식 창에 대한 마지막 메시지를 반영합니다.|  
|[CWnd::ResizeDynamicLayout](../Topic/CWnd::ResizeDynamicLayout.md)|창에 대해 동적 레이아웃을 사용하도록 설정한 경우 창 크기가 변경되면 자식 창의 레이아웃을 조정하기 위해 프레임워크에서 호출됩니다.|  
|[CWnd::WindowProc](../Topic/CWnd::WindowProc.md)|`CWnd`에 창 프로시저를 제공합니다.  기본값은 메시지 맵을 통해 메시지를 디스패치합니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CWnd::operator HWND](../Topic/CWnd::operator%20HWND.md)|창에 대한 핸들을 가져오려면 호출합니다.|  
|[CWnd::operator \!\=](../Topic/CWnd::operator%20!=.md)|창이 핸들이 [m\_hWnd](../Topic/CWnd::m_hWnd.md)인 창과 동일한지 않은지를 확인합니다.|  
|[CWnd::operator \=\=](../Topic/CWnd::operator%20==.md)|창이 핸들이 [m\_hWnd](../Topic/CWnd::m_hWnd.md)인 창과 동일한지를 확인합니다.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CWnd::m\_hWnd](../Topic/CWnd::m_hWnd.md)|`HWND`가 이 `CWnd`에 연결되었음을 나타냅니다.|  
  
## 설명  
 `CWnd` 개체는 Windows 창과 다르지만 둘이 밀접하게 연결되어 있습니다.  `CWnd` 개체는 `CWnd` 생성자 및 소멸자로 만들거나 제거합니다.  그러나 Windows 창은 **Create** 멤버 함수로 만들고 `CWnd` 가상 소멸자로 제거하는 Windows 내부의 데이터 구조입니다.  [DestroyWindow](../Topic/CWnd::DestroyWindow.md) 함수는 개체를 제거하지 않고 Windows 창을 제거합니다.  
  
 `CWnd` 클래스 및 메시지 맵 메커니즘은 **WndProc** 함수를 숨깁니다.  들어오는 Windows 알림 메시지는 메시지 맵을 통해 적절한 **On***Message* `CWnd` 멤버 함수로 자동으로 라우팅됩니다.  파생 클래스에서 멤버의 특정 메시지를 처리하려면 **On***Message* 멤버 함수를 재정의합니다.  
  
 또한 `CWnd` 클래스를 사용하여 응용 프로그램에 대한 Windows 자식 창을 만들 수 있습니다.  `CWnd`에서 클래스를 파생시킨 다음 파생 클래스에 멤버 변수를 추가하여 응용 프로그램 관련 데이터를 저장합니다.  파생 클래스에서 메시지 처리기 멤버 함수 및 메시지 맵을 구현하여 메시지가 창에 전달될 때 수행되는 작업을 지정합니다.  
  
 자식 창은 두 단계로 만듭니다.  먼저 생성자 `CWnd`를 호출하여 `CWnd` 개체를 생성한 다음 [Create](../Topic/CWnd::Create.md) 멤버 함수를 호출하여 자식 창을 만들고 `CWnd` 개체에 연결합니다.  
  
 사용자가 자식 창을 종료하면 `CWnd` 개체를 제거하거나 `DestroyWindow` 멤버 함수를 호출하여 창을 제거하고 해당 데이터 구조를 제거합니다.  
  
 Microsoft Foundation Class 라이브러리 내에서 추가 클래스를 `CWnd`에서 파생시켜 특정 창 형식을 제공합니다.  [CFrameWnd](../../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md), [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md), [CView](../../mfc/reference/cview-class.md) 및 [CDialog](../../mfc/reference/cdialog-class.md)를 포함하여 이러한 클래스 대부분은 추가 파생을 위해 설계되었습니다.  [CButton](../../mfc/reference/cbutton-class.md)과 같이 `CWnd`에서 파생된 컨트롤 클래스는 직접 사용하거나 추가 클래스 파생에 사용할 수 있습니다.  
  
 `CWnd` 사용에 대한 자세한 내용은 [프레임 창](../../mfc/frame-windows.md) 및 [창 개체](../../mfc/window-objects.md)를 참조하세요.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWnd`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)