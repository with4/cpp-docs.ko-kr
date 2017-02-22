---
title: "CBasePane Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CBasePane::get_accKeyboardShortcut"
  - "CBasePane.get_accKeyboardShortcut"
  - "CBasePane.accSelect"
  - "get_accDefaultAction"
  - "accSelect"
  - "CBasePane.accHitTest"
  - "CBasePane.get_accRole"
  - "get_accKeyboardShortcut"
  - "CBasePane::Serialize"
  - "CBasePane"
  - "CBasePane::get_accDefaultAction"
  - "get_accParent"
  - "CBasePane::accSelect"
  - "accLocation"
  - "CBasePane.get_accDescription"
  - "get_accName"
  - "CBasePane::get_accChildCount"
  - "CBasePane.get_accChild"
  - "CBasePane::accHitTest"
  - "accHitTest"
  - "get_accHelp"
  - "CBasePane.get_accChildCount"
  - "CBasePane.get_accValue"
  - "CBasePane::get_accDescription"
  - "get_accChildCount"
  - "CBasePane.accLocation"
  - "CBasePane.PreTranslateMessage"
  - "CBasePane.get_accName"
  - "PreTranslateMessage"
  - "CBasePane::get_accFocus"
  - "get_accDescription"
  - "CBasePane::get_accRole"
  - "get_accValue"
  - "CBasePane.Serialize"
  - "CBasePane::accLocation"
  - "get_accRole"
  - "CBasePane::get_accChild"
  - "get_accFocus"
  - "CBasePane::get_accHelp"
  - "CBasePane.get_accDefaultAction"
  - "CBasePane.get_accHelp"
  - "CBasePane::PreTranslateMessage"
  - "CBasePane::get_accState"
  - "CBasePane.get_accParent"
  - "CBasePane::get_accParent"
  - "get_accChild"
  - "CBasePane::get_accValue"
  - "Serialize"
  - "get_accState"
  - "CBasePane.get_accState"
  - "CBasePane.get_accFocus"
  - "CBasePane::get_accName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accHitTest method"
  - "accLocation method"
  - "accSelect method"
  - "CBasePane class"
  - "get_accChild method"
  - "get_accChildCount method"
  - "get_accDefaultAction method"
  - "get_accDescription method"
  - "get_accFocus method"
  - "get_accHelp method"
  - "get_accKeyboardShortcut method"
  - "get_accName method"
  - "get_accParent method"
  - "get_accRole method"
  - "get_accState method"
  - "get_accValue method"
  - "PreTranslateMessage method"
  - "Serialize method"
ms.assetid: 8163dd51-d7c7-4def-9c74-61f8ecdfad82
caps.latest.revision: 43
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 44
---
# CBasePane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC의 모든 창에 대 한 기본 클래스입니다.  
  
## 구문  
  
```  
class CBasePane : public CWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CBasePane::CBasePane`|기본 생성자입니다.|  
|`CBasePane::~CBasePane`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|`CBasePane::accHitTest`|자식 요소나 자식 개체를 화면에 특정 시점을 검색 하는 프레임 워크에서 호출 합니다.  \(재정의 [CWnd::accHitTest](../Topic/CWnd::accHitTest.md).\)|  
|`CBasePane::accLocation`|지정한 개체의 현재 화면 위치를 검색 하는 프레임 워크에서 호출 합니다.  \(재정의 [CWnd::accLocation](../Topic/CWnd::accLocation.md).\)|  
|[CBasePane::AccNotifyObjectFocusEvent](../Topic/CBasePane::AccNotifyObjectFocusEvent.md)|`CBasePane`이 메서드를 사용 하지 않습니다.|  
|`CBasePane::accSelect`|선택 영역을 수정 하거나 지정한 개체의 키보드 포커스를 이동 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::accSelect](../Topic/CWnd::accSelect.md).\)|  
|[CBasePane::AddPane](../Topic/CBasePane::AddPane.md)|창을 도킹 관리자에 추가합니다.|  
|[CBasePane::AdjustDockingLayout](../Topic/CBasePane::AdjustDockingLayout.md)|도킹 레이아웃을 조정 하려면 도킹 관리자 호출을 리디렉션합니다.|  
|[CBasePane::AdjustLayout](../Topic/CBasePane::AdjustLayout.md)|창 내부 레이아웃을 조정 해야 하는 경우 프레임 워크에서 호출 됩니다.|  
|[CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md)|컨트롤 막대의 가로 크기를 계산합니다.|  
|[CBasePane::CanAcceptPane](../Topic/CBasePane::CanAcceptPane.md)|다른 창 창에 도킹 될 수 있는지 여부를 결정 합니다.|  
|[CBasePane::CanAutoHide](../Topic/CBasePane::CanAutoHide.md)|창 자동 숨기기 모드를 지원 하는지 여부를 결정 합니다.|  
|[CBasePane::CanBeAttached](../Topic/CBasePane::CanBeAttached.md)|다른 창으로 창에 도킹 될 수 있는지 여부를 결정 합니다.|  
|[CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md)|창 닫을 수 있는지 여부를 결정 합니다.|  
|[CBasePane::CanBeDocked](../Topic/CBasePane::CanBeDocked.md)|다른 창으로 창에 도킹 될 수 있는지 여부를 결정 합니다.|  
|[CBasePane::CanBeResized](../Topic/CBasePane::CanBeResized.md)|창 크기를 조정할 수 있는지 여부를 결정 합니다.|  
|[CBasePane::CanBeTabbedDocument](../Topic/CBasePane::CanBeTabbedDocument.md)|창 MDI 탭된 문서로 변환할 수 있는지 지정 합니다.|  
|[CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md)|창 배치할 수 있는지 여부를 결정 합니다.|  
|[CBasePane::CanFocus](../Topic/CBasePane::CanFocus.md)|창 포커스를 받을 수 있는지 여부를 지정 합니다.|  
|[CBasePane::CopyState](../Topic/CBasePane::CopyState.md)|주어진 창의 상태를 복사합니다.|  
|[CBasePane::CreateDefaultMiniframe](../Topic/CBasePane::CreateDefaultMiniframe.md)|미니 프레임 창을 창 배치할 수 있는 경우에 만듭니다.|  
|[CBasePane::CreateEx](../Topic/CBasePane::CreateEx.md)|창 컨트롤을 만듭니다.|  
|[CBasePane::DockPane](../Topic/CBasePane::DockPane.md)|창을 다른 창 또는 프레임 창에 도킹합니다.|  
|[CBasePane::DockPaneUsingRTTI](../Topic/CBasePane::DockPaneUsingRTTI.md)|창 런타임 형식 정보를 사용 하 여 도킹 합니다.|  
|[CBasePane::DockToFrameWindow](../Topic/CBasePane::DockToFrameWindow.md)|도킹 가능한 창 프레임에 도킹합니다.|  
|[CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md)|다른 창 동적이 창과 부모 프레임 삽입 가능 여부를 결정 합니다.|  
|[CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md)|사용의 창 주 프레임에 도킹 합니다.|  
|[CBasePane::EnableGripper](../Topic/CBasePane::EnableGripper.md)|그리퍼를 사용할 수 있거나.  그리퍼를 사용 하는 경우 사용자의 창 위치를 끌 수 있습니다.|  
|`CBasePane::FillWindowRect`|내부적으로 사용됩니다.|  
|[CBasePane::FloatPane](../Topic/CBasePane::FloatPane.md)|창에 표시 됩니다.|  
|`CBasePane::get_accChild`|주소를 검색 하는 프레임 워크에서 호출 된 `IDispatch` 지정 된 자식에 대 한 인터페이스.  \(재정의 [CWnd::get\_accChild](../Topic/CWnd::get_accChild.md).\)|  
|`CBasePane::get_accChildCount`|이 개체에 속한 자식의 수를 검색 하는 프레임 워크에서 호출 합니다.  \(재정의 [CWnd::get\_accChildCount](../Topic/CWnd::get_accChildCount.md).\)|  
|`CBasePane::get_accDefaultAction`|개체에 대 한 기본 동작을 설명 하는 문자열을 검색 하는 프레임 워크에서 호출 합니다.  \(재정의 [CWnd::get\_accDefaultAction](../Topic/CWnd::get_accDefaultAction.md).\)|  
|`CBasePane::get_accDescription`|지정한 개체의 시각적 모양을 설명 하는 문자열을 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accDescription](../Topic/CWnd::get_accDescription.md).\)|  
|`CBasePane::get_accFocus`|키보드 포커스를 갖는 개체를 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accFocus](../Topic/CWnd::get_accFocus.md).\)|  
|`CBasePane::get_accHelp`|프레임 워크는 Help 속성 문자열 개체를 검색 하 여 호출 됩니다.  \(재정의 [CWnd::get\_accHelp](../Topic/CWnd::get_accHelp.md).\)|  
|[CBasePane::get\_accHelpTopic](../Topic/CBasePane::get_accHelpTopic.md)|WinHelp의 전체 경로 검색 하는 프레임 워크에서 호출파일에서 해당 항목의 식별자를 지정 된 개체와 연결 된 파일입니다.  \(재정의 [CWnd::get\_accHelpTopic](../Topic/CWnd::get_accHelpTopic.md).\)|  
|`CBasePane::get_accKeyboardShortcut`|지정 된 바로 가기 키 개체를 검색 하는 프레임 워크에서 호출 합니다.  \(재정의 [CWnd::get\_accKeyboardShortcut](../Topic/CWnd::get_accKeyboardShortcut.md).\)|  
|`CBasePane::get_accName`|지정한 개체의 이름을 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accName](../Topic/CWnd::get_accName.md).\)|  
|`CBasePane::get_accParent`|검색 하는 프레임 워크에서 호출을 `IDispatch` 개체의 부모에 대 한 인터페이스.  \(재정의 [CWnd::get\_accParent](../Topic/CWnd::get_accParent.md).\)|  
|`CBasePane::get_accRole`|지정 된 개체의 역할을 설명 하는 정보를 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accRole](../Topic/CWnd::get_accRole.md).\)|  
|[CBasePane::get\_accSelection](../Topic/CBasePane::get_accSelection.md)|이 개체의 선택된 된 자식 개체를 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accSelection](../Topic/CWnd::get_accSelection.md).\)|  
|`CBasePane::get_accState`|지정한 개체의 현재 상태를 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accState](../Topic/CWnd::get_accState.md).\)|  
|`CBasePane::get_accValue`|지정 된 개체의 값을 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accValue](../Topic/CWnd::get_accValue.md).\)|  
|[CBasePane::GetCaptionHeight](../Topic/CBasePane::GetCaptionHeight.md)|캡션 높이 반환합니다.|  
|[CBasePane::GetControlBarStyle](../Topic/CBasePane::GetControlBarStyle.md)|컨트롤 막대 스타일을 반환합니다.|  
|[CBasePane::GetCurrentAlignment](../Topic/CBasePane::GetCurrentAlignment.md)|현재 창 맞춤을 반환합니다.|  
|[CBasePane::GetDockingMode](../Topic/CBasePane::GetDockingMode.md)|현재 창의 도킹 모드를 반환합니다.|  
|[CBasePane::GetDockSiteFrameWnd](../Topic/CBasePane::GetDockSiteFrameWnd.md)|사이트 창의 도킹 창에 포인터를 반환 합니다.|  
|[CBasePane::GetEnabledAlignment](../Topic/CBasePane::GetEnabledAlignment.md)|창에 적용 되는 CBRS\_ALIGN\_ 스타일을 반환 합니다.|  
|[CBasePane::GetMFCStyle](../Topic/CBasePane::GetMFCStyle.md)|MFC에 특정 창 스타일을 반환합니다.|  
|[CBasePane::GetPaneIcon](../Topic/CBasePane::GetPaneIcon.md)|창을 아이콘으로 핸들을 반환합니다.|  
|`CBasePane::GetPaneRect`|내부적으로 사용됩니다.|  
|[CBasePane::GetPaneRow](../Topic/CBasePane::GetPaneRow.md)|반환에 대 한 포인터는  [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)개체 창에 도킹 합니다.|  
|[CBasePane::GetPaneStyle](../Topic/CBasePane::GetPaneStyle.md)|창의 스타일을 반환합니다.|  
|[CBasePane::GetParentDockSite](../Topic/CBasePane::GetParentDockSite.md)|항구 상위 사이트에 포인터를 반환 합니다.|  
|[CBasePane::GetParentMiniFrame](../Topic/CBasePane::GetParentMiniFrame.md)|부모 미니 프레임 창에 대 한 포인터를 반환합니다.|  
|[CBasePane::GetParentTabbedPane](../Topic/CBasePane::GetParentTabbedPane.md)|상위 탭된 창에 포인터를 반환 합니다.|  
|[CBasePane::GetParentTabWnd](../Topic/CBasePane::GetParentTabWnd.md)|탭 안에 있는 부모 창에 대 한 포인터를 반환 합니다.|  
|[CBasePane::GetRecentVisibleState](../Topic/CBasePane::GetRecentVisibleState.md)|프레임 워크는 창에서 아카이브를 복원 하는 경우이 메서드를 호출 합니다.|  
|[CBasePane::HideInPrintPreviewMode](../Topic/CBasePane::HideInPrintPreviewMode.md)|인쇄 미리 보기 창 숨김 여부를 지정 합니다.|  
|[CBasePane::InsertPane](../Topic/CBasePane::InsertPane.md)|지정한 창을 도킹 관리자에 등록합니다.|  
|[CBasePane::IsAccessibilityCompatible](../Topic/CBasePane::IsAccessibilityCompatible.md)|창 Active Accessibility를 지원 하는지 여부를 지정 합니다.|  
|[CBasePane::IsAutoHideMode](../Topic/CBasePane::IsAutoHideMode.md)|창 자동 숨기기 모드에 있는지 여부를 결정 합니다.|  
|[CBasePane::IsDialogControl](../Topic/CBasePane::IsDialogControl.md)|창 대화 상자 컨트롤 인지 여부를 지정 합니다.|  
|[CBasePane::IsDocked](../Topic/CBasePane::IsDocked.md)|창 도킹 여부를 결정 합니다.|  
|[CBasePane::IsFloating](../Topic/CBasePane::IsFloating.md)|창 부동 여부를 결정 합니다.|  
|[CBasePane::IsHorizontal](../Topic/CBasePane::IsHorizontal.md)|창에 가로로 도킹 여부를 결정 합니다.|  
|[CBasePane::IsInFloatingMultiPaneFrameWnd](../Topic/CBasePane::IsInFloatingMultiPaneFrameWnd.md)|다중 창 프레임 창에 창인지 여부를 지정 합니다.|  
|[CBasePane::IsMDITabbed](../Topic/CBasePane::IsMDITabbed.md)|창 탭 문서로 MDI 자식 창에 추가 되었는지 여부를 결정 합니다.|  
|[CBasePane::IsPaneVisible](../Topic/CBasePane::IsPaneVisible.md)|지정 여부는 `WS_VISIBLE` 창에 대 한 플래그를 설정 합니다.|  
|[CBasePane::IsPointNearDockSite](../Topic/CBasePane::IsPointNearDockSite.md)|지정 된 지점을 근처 항구 사이트 인지 확인 합니다.|  
|[CBasePane::IsResizable](../Topic/CBasePane::IsResizable.md)|창 크기를 조정할 수 있는지 여부를 결정 합니다.|  
|[CBasePane::IsRestoredFromRegistry](../Topic/CBasePane::IsRestoredFromRegistry.md)|창에서 레지스트리 복원 여부를 결정 합니다.|  
|[CBasePane::IsTabbed](../Topic/CBasePane::IsTabbed.md)|창 탭 컨트롤의 탭된 창에 삽입 된 여부를 결정 합니다.|  
|`CBasePane::IsTooltipTopmost`|내부적으로 사용됩니다.|  
|[CBasePane::IsVisible](../Topic/CBasePane::IsVisible.md)|창에 표시 되는지 여부를 결정 합니다.|  
|[CBasePane::LoadState](../Topic/CBasePane::LoadState.md)|창 상태를 로드합니다.|  
|[CBasePane::MoveWindow](../Topic/CBasePane::MoveWindow.md)|창으로 이동합니다.|  
|[CBasePane::OnAfterChangeParent](../Topic/CBasePane::OnAfterChangeParent.md)|창의 부모 변경 되었을 때 프레임 워크에 의해 호출 됩니다.|  
|[CBasePane::OnBeforeChangeParent](../Topic/CBasePane::OnBeforeChangeParent.md)|부모 창의 창을 바로 변경 하기 전에 프레임 워크에서 호출 됩니다.|  
|[CBasePane::OnDrawCaption](../Topic/CBasePane::OnDrawCaption.md)|프레임 워크는 캡션 그릴 때이 메서드를 호출 합니다.|  
|[CBasePane::OnMovePaneDivider](../Topic/CBasePane::OnMovePaneDivider.md)|이 메서드는 현재 사용 되지 않습니다.|  
|[CBasePane::OnPaneContextMenu](../Topic/CBasePane::OnPaneContextMenu.md)|목록 창에 있는 메뉴를 만들 때 프레임 워크에 의해 호출 됩니다.|  
|[CBasePane::OnRemoveFromMiniFrame](../Topic/CBasePane::OnRemoveFromMiniFrame.md)|한 창 부모 미니 프레임 창에서 제거 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md)|`CBasePane`이 메서드를 사용 하지 않습니다.|  
|`CBasePane::OnUpdateCmdUI`|내부적으로 사용됩니다.|  
|[CBasePane::PaneFromPoint](../Topic/CBasePane::PaneFromPoint.md)|지정 된 지점에 있는 창을 반환 합니다.|  
|`CBasePane::PreTranslateMessage`|클래스에 의해 사용 되는  [CWinApp](../../mfc/reference/cwinapp-class.md) 창 메시지를 디스패치하기 전에 변환 하는  [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및  [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 기능.  \(재정의 [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CBasePane::RecalcLayout](../Topic/CBasePane::RecalcLayout.md)|`CBasePane`이 메서드를 사용 하지 않습니다.|  
|[CBasePane::RemovePaneFromDockManager](../Topic/CBasePane::RemovePaneFromDockManager.md)|창에 등록을 취소 하 고 도킹 관리자에서 목록에서 제거.|  
|[CBasePane::SaveState](../Topic/CBasePane::SaveState.md)|창의 상태를 레지스트리에 저장합니다.|  
|[CBasePane::SelectDefaultFont](../Topic/CBasePane::SelectDefaultFont.md)|지정 된 장치 컨텍스트에 대 한 기본 글꼴을 선택 합니다.|  
|`CBasePane::Serialize`|읽거나 또는 보관 파일에이 개체를 씁니다.  \(재정의 [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CBasePane::SetControlBarStyle](../Topic/CBasePane::SetControlBarStyle.md)|컨트롤 막대 스타일을 설정합니다.|  
|[CBasePane::SetDockingMode](../Topic/CBasePane::SetDockingMode.md)|창의 도킹 모드를 설정합니다.|  
|`CBasePane::SetMDITabbed`|내부적으로 사용됩니다.|  
|[CBasePane::SetPaneAlignment](../Topic/CBasePane::SetPaneAlignment.md)|창에 맞춤을 설정합니다.|  
|`CBasePane::SetPaneRect`|내부적으로 사용됩니다.|  
|[CBasePane::SetPaneStyle](../Topic/CBasePane::SetPaneStyle.md)|창 스타일을 설정합니다.|  
|`CBasePane::SetRestoredFromRegistry`|내부적으로 사용됩니다.|  
|[CBasePane::SetWindowPos](../Topic/CBasePane::SetWindowPos.md)|크기, 위치 및 창의 Z 순서를 변경합니다.|  
|[CBasePane::ShowPane](../Topic/CBasePane::ShowPane.md)|표시 하거나 창에서 숨깁니다.|  
|[CBasePane::StretchPane](../Topic/CBasePane::StretchPane.md)|창을 세로 또는 가로로 늘어납니다.|  
|[CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md)|창 도킹 사이트, 기본 슬라이더 또는 미니 프레임 창의 도킹 된 현재에서 제거 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CBasePane::DoPaint](../Topic/CBasePane::DoPaint.md)|창 배경을 채웁니다.|  
  
## 설명  
 MFC에서 사용할 수 있는 확장된 도킹 기능을 지 원하는 창 클래스를 작성 하려는 경우를 추출 해야 `CBasePane` 또는 [CPane Class](../../mfc/reference/cpane-class.md).  
  
## 사용자 지정 팁  
 다음 사용자 지정 팁 관련 된 [CBasePane Class](../../mfc/reference/cbasepane-class.md) 및 상속 된 클래스:  
  
-   창을 만들 때 몇 가지 새 스타일을 적용할 수 있습니다.  
  
    -   `AFX_CBRS_FLOAT`창을 부동 소수점을 수 있습니다.  
  
    -   `AFX_CBRS_AUTOHIDE`자동 숨김 모드 수 있습니다.  
  
    -   `AFX_CBRS_CLOSE`창을 \(숨겨진\) 닫을 수 있습니다.  
  
     이러한 플래그의 비트 OR 연산에 결합할 수 있습니다.  
  
     `CBasePane`이러한 플래그를 반영 하도록 다음 가상 부울 메서드를 구현 합니다. [CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md), [CBasePane::CanAutoHide](../Topic/CBasePane::CanAutoHide.md), [CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md).  파생된 클래스에서 해당 동작을 사용자 지정 하 여를 재정의할 수 있습니다.  
  
-   도킹 동작을 재정의 하 여 사용자 지정할 수 있습니다 [CBasePane::CanAcceptPane](../Topic/CBasePane::CanAcceptPane.md).  창을 반환 해야 합니다. `FALSE` 에서이 메서드는 다른 창에 고정 하지 못하게 합니다.  
  
-   배치할 수 없음 고는 하지 않도록 모든 다른 창 전에 도킹에서 고정 창 \(Outlook 표시줄에 OutlookDemo 예제와 유사\), 비 부동으로 만들 만들고 재정의 하려는 경우 [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md) 반환 합니다 `FALSE`.  기본 구현을 반환 합니다. `FALSE` 의 창 없이 만들어지는 경우는 `AFX_CBRS_FLOAT` 스타일.  
  
-   모든 창 Id로\-1 이외의 만듭니다.  
  
-   창의 표시 여부를 확인 하려면 사용 [CBasePane::IsVisible](../Topic/CBasePane::IsVisible.md).  가시성 상태를 올바르게 처리에서 탭 및 자동 숨기기 모드.  
  
-   움직이지 않는 크기 조정 가능한 창에서 만들려는 경우 없이 만들기는 `AFX_CBRS_FLOAT` 스타일과 호출 [CFrameWnd::DockControlBar](../Topic/CFrameWnd::DockControlBar.md).  
  
-   창을 도킹 레이아웃에서 제외 하거나 해당 도킹 도구 모음에서 도구 모음을 제거 하려면 호출 [CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md).  창 자동 숨기기 모드에서 또는 탭 창의 탭에 있는 창에 대해이 메서드를 호출 하지 마십시오.  
  
-   Float 또는 도킹 창 자동 숨기기 모드일 경우 호출 해야 [CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md) 와 `FALSE` 를 호출 하기 전에 첫 번째 인수와 [CBasePane::FloatPane](../Topic/CBasePane::FloatPane.md) 또는 [CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md).  
  
## 예제  
 다음 예제에서는 다양 한 방법에 있는 `CBasePane` 클래스입니다.  예제 창에서 검색 하는 방법을 보여 줍니다.을 `CFrameWndEx` 클래스 및 도킹 모드, 창 맞춤 및 창 스타일을 설정 하는 방법.  코드에서 되는  [워드 패드 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#2](../../mfc/reference/codesnippet/CPP/cbasepane-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
## 요구 사항  
 **헤더:** afxbasepane.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPane](../../mfc/reference/cbasepane-class.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)