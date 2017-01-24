---
title: "CWindow Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CWindow"
  - "ATL::CWindow"
  - "CWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWindow class"
ms.assetid: fefa00c8-f053-4bcf-87bc-dc84f5386683
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWindow Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 창을 조작 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CWindow  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CWindow::CWindow](../Topic/CWindow::CWindow.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CWindow::ArrangeIconicWindows](../Topic/CWindow::ArrangeIconicWindows.md)|모든 최소화 된 자식 창을 정렬합니다.|  
|[CWindow::Attach](../Topic/CWindow::Attach.md)|창에 연결 된 `CWindow` 개체입니다.|  
|[CWindow::BeginPaint](../Topic/CWindow::BeginPaint.md)|창에 페인팅을 준비합니다.|  
|[CWindow::BringWindowToTop](../Topic/CWindow::BringWindowToTop.md)|창의 Z 순서 맨 아래에 나타납니다.|  
|[CWindow::CenterWindow](../Topic/CWindow::CenterWindow.md)|창을 지정 된 창에 맞춥니다.|  
|[CWindow::ChangeClipboardChain](../Topic/CWindow::ChangeClipboardChain.md)|창의 클립보드 뷰어 체인에서 제거합니다.|  
|[CWindow::CheckDlgButton](../Topic/CWindow::CheckDlgButton.md)|지정한 단추의 선택 상태를 변경합니다.|  
|[CWindow::CheckRadioButton](../Topic/CWindow::CheckRadioButton.md)|지정 된 라디오 단추를 확인합니다.|  
|[CWindow::ChildWindowFromPoint](../Topic/CWindow::ChildWindowFromPoint.md)|지정 된 지점을 포함 하는 자식 창을 검색 합니다.|  
|[CWindow::ChildWindowFromPointEx](../Topic/CWindow::ChildWindowFromPointEx.md)|특정 종류의 지정 된 위치에 포함 된 자식 창 검색 합니다.|  
|[CWindow::ClientToScreen](../Topic/CWindow::ClientToScreen.md)|클라이언트 좌표를 화면 좌표로 변환 합니다.|  
|[CWindow::Create](../Topic/CWindow::Create.md)|창을 만듭니다.|  
|[CWindow::CreateCaret](../Topic/CWindow::CreateCaret.md)|시스템 캐럿에 새 셰이프를 만듭니다.|  
|[CWindow::CreateGrayCaret](../Topic/CWindow::CreateGrayCaret.md)|시스템 캐럿에 회색 사각형을 만듭니다.|  
|[CWindow::CreateSolidCaret](../Topic/CWindow::CreateSolidCaret.md)|단색 사각형 시스템 캐럿을 만듭니다.|  
|[CWindow::DeferWindowPos](../Topic/CWindow::DeferWindowPos.md)|지정한 창에 대 한 지정 된 다중 창 위치 구조를 업데이트합니다.|  
|[CWindow::DestroyWindow](../Topic/CWindow::DestroyWindow.md)|관련 창을 소멸의 `CWindow` 개체입니다.|  
|[CWindow::Detach](../Topic/CWindow::Detach.md)|창에서 분리 된 `CWindow` 개체입니다.|  
|[CWindow::DlgDirList](../Topic/CWindow::DlgDirList.md)|지정 된 경로 또는 파일 이름에 일치 하는 모든 파일의 이름으로 목록 상자를 채웁니다.|  
|[CWindow::DlgDirListComboBox](../Topic/CWindow::DlgDirListComboBox.md)|콤보 상자에 지정 된 경로 또는 파일 이름에 일치 하는 모든 파일 이름으로 채웁니다.|  
|[CWindow::DlgDirSelect](../Topic/CWindow::DlgDirSelect.md)|목록 상자에서 현재 선택 영역을 검색합니다.|  
|[CWindow::DlgDirSelectComboBox](../Topic/CWindow::DlgDirSelectComboBox.md)|콤보 상자에서 현재 선택 영역을 검색합니다.|  
|[CWindow::DragAcceptFiles](../Topic/CWindow::DragAcceptFiles.md)|창 허용 여부 레지스터 파일 드래그 합니다.|  
|[CWindow::DrawMenuBar](../Topic/CWindow::DrawMenuBar.md)|창의 메뉴 표시줄을 다시 그립니다.|  
|[CWindow::EnableScrollBar](../Topic/CWindow::EnableScrollBar.md)|스크롤 막대 화살표를 사용할 수 있거나.|  
|[CWindow::EnableWindow](../Topic/CWindow::EnableWindow.md)|입력을 사용할 수 있거나.|  
|[CWindow::EndPaint](../Topic/CWindow::EndPaint.md)|페인트의 끝을 표시 합니다.|  
|[CWindow::FlashWindow](../Topic/CWindow::FlashWindow.md)|창을 한 번 깜박입니다.|  
|[CWindow::GetClientRect](../Topic/CWindow::GetClientRect.md)|클라이언트 영역 좌표를 검색합니다.|  
|[CWindow::GetDC](../Topic/CWindow::GetDC.md)|클라이언트 영역에 대 한 장치 컨텍스트를 검색합니다.|  
|[CWindow::GetDCEx](../Topic/CWindow::GetDCEx.md)|클라이언트 영역에 대 한 장치 컨텍스트를 검색 하 고 클리핑 옵션이 있습니다.|  
|[CWindow::GetDescendantWindow](../Topic/CWindow::GetDescendantWindow.md)|지정 된 하위 창을 검색합니다.|  
|[CWindow::GetDlgControl](../Topic/CWindow::GetDlgControl.md)|지정 된 컨트롤에 인터페이스를 검색합니다.|  
|[CWindow::GetDlgCtrlID](../Topic/CWindow::GetDlgCtrlID.md)|\(자식 windows만 해당\)에 대 한 윈도우의 식별자를 검색합니다.|  
|[CWindow::GetDlgHost](../Topic/CWindow::GetDlgHost.md)|ATL 컨트롤 호스팅 컨테이너 인터페이스에 대 한 포인터를 검색 합니다.|  
|[CWindow::GetDlgItem](../Topic/CWindow::GetDlgItem.md)|지정 된 자식 창을 검색합니다.|  
|[CWindow::GetDlgItemInt](../Topic/CWindow::GetDlgItemInt.md)|컨트롤의 텍스트를 정수로 변환합니다.|  
|[CWindow::GetDlgItemText](../Topic/CWindow::GetDlgItemText.md)|컨트롤의 텍스트를 검색합니다.|  
|[CWindow::GetExStyle](../Topic/CWindow::GetExStyle.md)|확장된 창 스타일을 검색합니다.|  
|[CWindow::GetFont](../Topic/CWindow::GetFont.md)|현재 창의 글꼴을 검색합니다.|  
|[CWindow::GetHotKey](../Topic/CWindow::GetHotKey.md)|창과 관련 된 바로 가기 키를 확인 합니다.|  
|[CWindow::GetIcon](../Topic/CWindow::GetIcon.md)|크고 작은 창의 아이콘을 검색합니다.|  
|[CWindow::GetLastActivePopup](../Topic/CWindow::GetLastActivePopup.md)|가장 최근에 활성 팝업 창을 검색합니다.|  
|[CWindow::GetMenu](../Topic/CWindow::GetMenu.md)|창의 메뉴를 검색합니다.|  
|[CWindow::GetNextDlgGroupItem](../Topic/CWindow::GetNextDlgGroupItem.md)|컨트롤 그룹에서 이전 또는 다음 컨트롤을 검색합니다.|  
|[CWindow::GetNextDlgTabItem](../Topic/CWindow::GetNextDlgTabItem.md)|이전 또는 다음 컨트롤 문제가 검색 된  **WS\_TABSTOP** 스타일.|  
|[CWindow::GetParent](../Topic/CWindow::GetParent.md)|부모 창을 검색합니다.|  
|[CWindow::GetScrollInfo](../Topic/CWindow::GetScrollInfo.md)|스크롤 막대의 매개 변수를 검색합니다.|  
|[CWindow::GetScrollPos](../Topic/CWindow::GetScrollPos.md)|스크롤 상자의 위치를 검색합니다.|  
|[CWindow::GetScrollRange](../Topic/CWindow::GetScrollRange.md)|스크롤 막대 범위를 검색합니다.|  
|[CWindow::GetStyle](../Topic/CWindow::GetStyle.md)|창 스타일을 검색합니다.|  
|[CWindow::GetSystemMenu](../Topic/CWindow::GetSystemMenu.md)|시스템 메뉴 수정에 대 한 복사본을 만듭니다.|  
|[CWindow::GetTopLevelParent](../Topic/CWindow::GetTopLevelParent.md)|최상위 부모 또는 소유자 창을 검색합니다.|  
|[CWindow::GetTopLevelWindow](../Topic/CWindow::GetTopLevelWindow.md)|최상위 소유자 창을 검색합니다.|  
|[CWindow::GetTopWindow](../Topic/CWindow::GetTopWindow.md)|최상위 수준의 하위 창을 검색합니다.|  
|[CWindow::GetUpdateRect](../Topic/CWindow::GetUpdateRect.md)|완전히 업데이트 영역을 둘러싸는 가장 작은 사각형의 좌표를 검색 합니다.|  
|[CWindow::GetUpdateRgn](../Topic/CWindow::GetUpdateRgn.md)|업데이트 영역 검색 하 고 지정한 영역에 복사 합니다.|  
|[CWindow::GetWindow](../Topic/CWindow::GetWindow.md)|지정 된 창을 검색합니다.|  
|[CWindow::GetWindowContextHelpId](../Topic/CWindow::GetWindowContextHelpId.md)|윈도우의 도움말 컨텍스트 식별자를 검색합니다.|  
|[CWindow::GetWindowDC](../Topic/CWindow::GetWindowDC.md)|전체 창에 대 한 장치 컨텍스트를 검색합니다.|  
|[CWindow::GetWindowLong](../Topic/CWindow::GetWindowLong.md)|추가 창 메모리에 지정 된 오프셋에서 32 비트 값을 검색합니다.|  
|[CWindow::GetWindowLongPtr](../Topic/CWindow::GetWindowLongPtr.md)|추가 창 메모리에 지정 된 오프셋 값을 포함 하 여 지정한 창에 대 한 정보를 검색 합니다.|  
|[CWindow::GetWindowPlacement](../Topic/CWindow::GetWindowPlacement.md)|표시 상태와 위치를 검색합니다.|  
|[CWindow::GetWindowProcessID](../Topic/CWindow::GetWindowProcessID.md)|창을 생성 프로세스의 식별자를 검색 합니다.|  
|[CWindow::GetWindowRect](../Topic/CWindow::GetWindowRect.md)|창 테두리 크기를 검색합니다.|  
|[CWindow::GetWindowRgn](../Topic/CWindow::GetWindowRgn.md)|창의 창 영역의 복사본을 가져옵니다.|  
|[CWindow::GetWindowText](../Topic/CWindow::GetWindowText.md)|윈도우의 텍스트를 검색합니다.|  
|[CWindow::GetWindowTextLength](../Topic/CWindow::GetWindowTextLength.md)|윈도우의 텍스트를 검색합니다.|  
|[CWindow::GetWindowThreadID](../Topic/CWindow::GetWindowThreadID.md)|지정한 창을 만든 스레드의 식별자를 검색 합니다.|  
|[CWindow::GetWindowWord](../Topic/CWindow::GetWindowWord.md)|추가 창 메모리에 지정 된 오프셋에서 16 비트 값을 검색합니다.|  
|[CWindow::GotoDlgCtrl](../Topic/CWindow::GotoDlgCtrl.md)|키보드 포커스를 컨트롤 대화 상자에서 설정합니다.|  
|[CWindow::HideCaret](../Topic/CWindow::HideCaret.md)|시스템 캐럿을 숨깁니다.|  
|[CWindow::HiliteMenuItem](../Topic/CWindow::HiliteMenuItem.md)|최상위 메뉴 항목에서 강조 표시 제거 강조 표시 됩니다.|  
|[CWindow::Invalidate](../Topic/CWindow::Invalidate.md)|전체 클라이언트 영역을 무효화합니다.|  
|[CWindow::InvalidateRect](../Topic/CWindow::InvalidateRect.md)|지정한 사각형 안에서 클라이언트 영역을 무효화합니다.|  
|[CWindow::InvalidateRgn](../Topic/CWindow::InvalidateRgn.md)|지정 된 영역 안에서 클라이언트 영역을 무효화합니다.|  
|[CWindow::IsChild](../Topic/CWindow::IsChild.md)|지정한 창의 자식 창에 있는지 확인 합니다.|  
|[CWindow::IsDialogMessage](../Topic/CWindow::IsDialogMessage.md)|메시지에서 지정 된 대화 상자를 사용할 것인지를 결정 합니다.|  
|[CWindow::IsDlgButtonChecked](../Topic/CWindow::IsDlgButtonChecked.md)|단추의 선택 상태를 결정합니다.|  
|[CWindow::IsIconic](../Topic/CWindow::IsIconic.md)|창이 최소화 되 고 있는지 여부를 결정 합니다.|  
|[CWindow::IsParentDialog](../Topic/CWindow::IsParentDialog.md)|컨트롤의 부모 창 대화 창이 있는지 확인 합니다.|  
|[CWindow::IsWindow](../Topic/CWindow::IsWindow.md)|지정 된 창 핸들에서 기존 창을 식별 하는지 여부를 결정 합니다.|  
|[CWindow::IsWindowEnabled](../Topic/CWindow::IsWindowEnabled.md)|창 입력에 사용할 수 있는지 여부를 결정 합니다.|  
|[CWindow::IsWindowUnicode](../Topic/CWindow::IsWindowUnicode.md)|지정한 창의 네이티브 유니코드 창이 있는지 확인 합니다.|  
|[CWindow::IsWindowVisible](../Topic/CWindow::IsWindowVisible.md)|창의 표시 상태를 결정합니다.|  
|[CWindow::IsZoomed](../Topic/CWindow::IsZoomed.md)|창이 최대화 되어 있는지 여부를 결정 합니다.|  
|[CWindow::KillTimer](../Topic/CWindow::KillTimer.md)|타이머 이벤트를 소멸 시킵니다.|  
|[CWindow::LockWindowUpdate](../Topic/CWindow::LockWindowUpdate.md)|선택 하거나 드로잉 창에서.|  
|[CWindow::MapWindowPoints](../Topic/CWindow::MapWindowPoints.md)|점의 집합 창 좌표 공간에서 다른 창 좌표 공간으로 변환합니다.|  
|[CWindow::MessageBox](../Topic/CWindow::MessageBox.md)|메시지 상자를 표시합니다.|  
|[CWindow::ModifyStyle](../Topic/CWindow::ModifyStyle.md)|창 스타일을 수정합니다.|  
|[CWindow::ModifyStyleEx](../Topic/CWindow::ModifyStyleEx.md)|확장된 창 스타일을 수정합니다.|  
|[CWindow::MoveWindow](../Topic/CWindow::MoveWindow.md)|창의 크기와 위치를 변경합니다.|  
|[CWindow::NextDlgCtrl](../Topic/CWindow::NextDlgCtrl.md)|키보드 포커스를 다음 컨트롤로 대화 상자에서 설정합니다.|  
|[CWindow::OpenClipboard](../Topic/CWindow::OpenClipboard.md)|클립보드를 엽니다.|  
|[CWindow::PostMessage](../Topic/CWindow::PostMessage.md)|메시지 창을 만든 스레드와 연관 된 메시지 큐에 배치 됩니다.  메시지를 처리 하는 스레드에 대 한 대기 하지 않고 반환 합니다.|  
|[CWindow::PrevDlgCtrl](../Topic/CWindow::PrevDlgCtrl.md)|키보드 포커스를 대화 상자에서 이전 컨트롤을 설정합니다.|  
|[CWindow::Print](../Topic/CWindow::Print.md)|요청 창에는 지정 된 디바이스 컨텍스트를 그릴 수 있습니다.|  
|[CWindow::PrintClient](../Topic/CWindow::PrintClient.md)|요청 창의 클라이언트 영역에 지정 된 디바이스 컨텍스트를 그릴 수 있습니다.|  
|[CWindow::RedrawWindow](../Topic/CWindow::RedrawWindow.md)|지정 된 사각형이 나 영역에서 클라이언트 영역을 업데이트합니다.|  
|[CWindow::ReleaseDC](../Topic/CWindow::ReleaseDC.md)|장치 컨텍스트를 해제합니다.|  
|[CWindow::ResizeClient](../Topic/CWindow::ResizeClient.md)|창 크기를 조정 합니다.|  
|[CWindow::ScreenToClient](../Topic/CWindow::ScreenToClient.md)|화면 좌표를 클라이언트 좌표로 변환 합니다.|  
|[CWindow::ScrollWindow](../Topic/CWindow::ScrollWindow.md)|지정 된 클라이언트 영역을 스크롤합니다.|  
|[CWindow::ScrollWindowEx](../Topic/CWindow::ScrollWindowEx.md)|추가 기능 사용 하 여 지정 된 클라이언트 영역을 스크롤합니다.|  
|[CWindow::SendDlgItemMessage](../Topic/CWindow::SendDlgItemMessage.md)|메시지를 컨트롤에 보냅니다.|  
|[CWindow::SendMessage](../Topic/CWindow::SendMessage.md)|창에는 메시지를 보내고 창 프로시저에서 메시지를 처리할 때까지 반환 하지 않습니다.|  
|[CWindow::SendMessageToDescendants](../Topic/CWindow::SendMessageToDescendants.md)|지정 된 하위 창에 메시지를 보냅니다.|  
|[CWindow::SendNotifyMessage](../Topic/CWindow::SendNotifyMessage.md)|창에 메시지를 보냅니다.  창 호출 스레드에 의해 작성 된 경우 `SendNotifyMessage` 창 프로시저에서 메시지를 처리할 때까지 반환 하지 않습니다.  그렇지 않으면 즉시 반환 합니다.|  
|[CWindow::SetActiveWindow](../Topic/CWindow::SetActiveWindow.md)|창을 활성화합니다.|  
|[CWindow::SetCapture](../Topic/CWindow::SetCapture.md)|모든 후속 마우스 입력을 창에 보냅니다.|  
|[CWindow::SetClipboardViewer](../Topic/CWindow::SetClipboardViewer.md)|창의 클립보드 뷰어 체인에 추가합니다.|  
|[CWindow::SetDlgCtrlID](../Topic/CWindow::SetDlgCtrlID.md)|윈도우의 식별자를 변경합니다.|  
|[CWindow::SetDlgItemInt](../Topic/CWindow::SetDlgItemInt.md)|컨트롤의 텍스트를 정수 값의 문자열 표현으로 바뀝니다.|  
|[CWindow::SetDlgItemText](../Topic/CWindow::SetDlgItemText.md)|컨트롤의 텍스트를 변경합니다.|  
|[CWindow::SetFocus](../Topic/CWindow::SetFocus.md)|창에 입력된 포커스를 설정합니다.|  
|[CWindow::SetFont](../Topic/CWindow::SetFont.md)|현재 윈도우의 글꼴을 변경합니다.|  
|[CWindow::SetHotKey](../Topic/CWindow::SetHotKey.md)|창에 바로 가기 키를 연결합니다.|  
|[CWindow::SetIcon](../Topic/CWindow::SetIcon.md)|크고 작은 창의 아이콘을 변경합니다.|  
|[CWindow::SetMenu](../Topic/CWindow::SetMenu.md)|현재 윈도우의 메뉴를 변경합니다.|  
|[CWindow::SetParent](../Topic/CWindow::SetParent.md)|부모 창으로 변경 됩니다.|  
|[CWindow::SetRedraw](../Topic/CWindow::SetRedraw.md)|설정 하거나 다시 그리기 플래그를 지웁니다.|  
|[CWindow::SetScrollInfo](../Topic/CWindow::SetScrollInfo.md)|스크롤 막대의 매개 변수를 설정합니다.|  
|[CWindow::SetScrollPos](../Topic/CWindow::SetScrollPos.md)|스크롤 상자 위치가 변경 됩니다.|  
|[CWindow::SetScrollRange](../Topic/CWindow::SetScrollRange.md)|스크롤 막대 범위가 변경 됩니다.|  
|[CWindow::SetTimer](../Topic/CWindow::SetTimer.md)|타이머 이벤트를 만듭니다.|  
|[CWindow::SetWindowContextHelpId](../Topic/CWindow::SetWindowContextHelpId.md)|윈도우의 도움말 컨텍스트 식별자를 설정합니다.|  
|[CWindow::SetWindowLong](../Topic/CWindow::SetWindowLong.md)|32 비트 값 추가 창 메모리에 지정 된 오프셋을 설정합니다.|  
|[CWindow::SetWindowLongPtr](../Topic/CWindow::SetWindowLongPtr.md)|지정한 창의 특성을 변경 하 고 또한 메모리 추가 창에서에서 지정 된 오프셋 값을 설정.|  
|[CWindow::SetWindowPlacement](../Topic/CWindow::SetWindowPlacement.md)|표시 상태와 위치를 설정합니다.|  
|[CWindow::SetWindowPos](../Topic/CWindow::SetWindowPos.md)|크기, 위치 및 Z 순서를 설정합니다.|  
|[CWindow::SetWindowRgn](../Topic/CWindow::SetWindowRgn.md)|창의 창 영역을 설정합니다.|  
|[CWindow::SetWindowText](../Topic/CWindow::SetWindowText.md)|윈도우의 텍스트를 변경합니다.|  
|[CWindow::SetWindowWord](../Topic/CWindow::SetWindowWord.md)|16 비트 값 추가 창 메모리에 지정 된 오프셋을 설정합니다.|  
|[CWindow::ShowCaret](../Topic/CWindow::ShowCaret.md)|시스템 캐럿을 표시합니다.|  
|[CWindow::ShowOwnedPopups](../Topic/CWindow::ShowOwnedPopups.md)|표시 하거나 창에 소유 된 팝업 창을 숨깁니다.|  
|[CWindow::ShowScrollBar](../Topic/CWindow::ShowScrollBar.md)|표시 하거나 스크롤 막대를 숨깁니다.|  
|[CWindow::ShowWindow](../Topic/CWindow::ShowWindow.md)|창의 표시 상태를 설정합니다.|  
|[CWindow::ShowWindowAsync](../Topic/CWindow::ShowWindowAsync.md)|다른 스레드가 만든 창의 표시 상태를 설정 합니다.|  
|[CWindow::UpdateWindow](../Topic/CWindow::UpdateWindow.md)|클라이언트 영역을 업데이트합니다.|  
|[CWindow::ValidateRect](../Topic/CWindow::ValidateRect.md)|지정한 사각형 안에서 클라이언트 영역을 확인합니다.|  
|[CWindow::ValidateRgn](../Topic/CWindow::ValidateRgn.md)|지정 된 영역 안에서 클라이언트 영역을 확인합니다.|  
|[CWindow::WinHelp](../Topic/CWindow::WinHelp.md)|Windows 도움말을 시작 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CWindow::operator HWND](../Topic/CWindow::operator%20HWND.md)|변환 된 `CWindow` 개체는 `HWND`.|  
|[CWindow::operator \=](../Topic/CWindow::operator%20=.md)|할당 된 `HWND` 에 `CWindow` 개체.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CWindow::m\_hWnd](../Topic/CWindow::m_hWnd.md)|연결 된 창 핸들은 `CWindow` 개체입니다.|  
|[CWindow::rcDefault](../Topic/CWindow::rcDefault.md)|기본 창 크기를 포함 합니다.|  
  
## 설명  
 `CWindow`atl에서 창 조작 하기 위한 기본 기능을 제공 합니다.  많은 `CWindow` 방법을 간단 하 게 배치 Win32 API 함수 중 하나입니다.  프로토타입에 대 한 예를 들어 비교 `CWindow::ShowWindow` 및 `ShowWindow`.  
  
|CWindow 메서드|Win32 함수|  
|-----------------|--------------|  
|**BOOL ShowWindow \(int**  `nCmdShow` **\);**|**BOOL ShowWindow\( HWND**  `hWnd` **, int**  `nCmdShow` **\);**|  
  
 `CWindow::ShowWindow`Win32 함수 호출 `ShowWindow` 전달 하 여 `CWindow::m_hWnd` 첫 번째 매개 변수로.  모든 `CWindow` 전달 직접 Win32 함수를 래핑하는 메서드는 `m_hWnd` 멤버입니다. 따라서 대부분의 `CWindow` 설명서를 참조 합니다의 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  모든 창의 관련 Win32 함수에서 래핑됩니다 `CWindow`, 및 모든 `CWindow` 메서드는 Win32 함수를 래핑합니다.  
  
 `CWindow::m_hWnd`저장 된 `HWND` 창을 식별 하는 것입니다.  `HWND` 개체에 연결 된 경우 사용자:  
  
-   지정 된 `HWND` 에서 `CWindow`의 생성자입니다.  
  
-   `CWindow::Attach`를 호출합니다.  
  
-   Use `CWindow`'s **operator \=**.  
  
-   만들거나 하위 클래스는 다음 클래스 중 하나를 사용 하는 창에서 파생 `CWindow`.  
  
     [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 기존 창을 새 창 또는 하위 클래스를 만들 수 있습니다.  
  
     [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 다른 개체에 포함 된 창을 구현 합니다.  기존 창을 새 창 또는 하위 클래스를 만들 수 있습니다.  
  
     [CDialogImpl](../../atl/reference/cdialogimpl-class.md) 모달 또는 모덜리스 대화 상자를 만들 수 있습니다.  
  
 Windows에 대 한 자세한 내용은  [Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595) 및 다음 항목에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  ATL에 대 한 windows 사용에 대 한 자세한 내용은  [ATL 창 클래스](../../atl/atl-window-classes.md).  
  
## 요구 사항  
 **헤더:**  atlwin.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)