---
title: "CMFCMenuBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCMenuBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCMenuBar class"
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 38
---
# CMFCMenuBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

메뉴 모음 도킹을 구현 합니다.  
  
## 구문  
  
```  
class CMFCMenuBar : public CMFCToolbar  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCMenuBar::AdjustLocations](../Topic/CMFCMenuBar::AdjustLocations.md)|\(재정의 `CMFCToolBar::AdjustLocations`.\)|  
|[CMFCMenuBar::AllowChangeTextLabels](../Topic/CMFCMenuBar::AllowChangeTextLabels.md)|이미지 도구 모음 단추에 텍스트 레이블을 표시할 수 있습니다 여부를 지정 합니다.  \(재정의 [CMFCToolBar::AllowChangeTextLabels](../Topic/CMFCToolBar::AllowChangeTextLabels.md).\)|  
|[CMFCMenuBar::AllowShowOnPaneMenu](../Topic/CMFCMenuBar::AllowShowOnPaneMenu.md)|\(재정의 `CPane::AllowShowOnPaneMenu`.\)|  
|[CMFCMenuBar::CalcFixedLayout](../Topic/CMFCMenuBar::CalcFixedLayout.md)|도구 모음의 가로 크기를 계산합니다.  \(재정의 [CMFCToolBar::CalcFixedLayout](../Topic/CMFCToolBar::CalcFixedLayout.md).\)|  
|[CMFCMenuBar::CalcLayout](../Topic/CMFCMenuBar::CalcLayout.md)|\(재정의 `CMFCToolBar::CalcLayout`.\)|  
|[CMFCMenuBar::CalcMaxButtonHeight](../Topic/CMFCMenuBar::CalcMaxButtonHeight.md)|도구 모음에서 단추의 최대 높이 계산합니다.  \(재정의 [CMFCToolBar::CalcMaxButtonHeight](../Topic/CMFCToolBar::CalcMaxButtonHeight.md).\)|  
|[CMFCMenuBar::CanBeClosed](../Topic/CMFCMenuBar::CanBeClosed.md)|사용자가 도구 모음을 닫을 수 있습니다 여부를 지정 합니다.  \(재정의 [CMFCToolBar::CanBeClosed](../Topic/CMFCToolBar::CanBeClosed.md).\)|  
|[CMFCMenuBar::CanBeRestored](../Topic/CMFCMenuBar::CanBeRestored.md)|시스템 도구 모음을 원래 상태로 사용자 지정 후 복원할 수 여부를 결정 합니다.  \(재정의 [CMFCToolBar::CanBeRestored](../Topic/CMFCToolBar::CanBeRestored.md).\)|  
|[CMFCMenuBar::Create](../Topic/CMFCMenuBar::Create.md)|Menu 컨트롤을 만들고이에 연결 된 `CMFCMenuBar` 개체입니다.|  
|[CMFCMenuBar::CreateEx](../Topic/CMFCMenuBar::CreateEx.md)|만듭니다는 `CMFCMenuBar` 개체 추가 스타일 옵션을 사용 합니다.|  
|[CMFCMenuBar::CreateFromMenu](../Topic/CMFCMenuBar::CreateFromMenu.md)|`CMFCMenuBar` 개체를 초기화합니다.  허용 된 `HMENU` 는 채워진된 템플릿을 역할 매개 변수 `CMFCMenuBar`.|  
|[CMFCMenuBar::EnableHelpCombobox](../Topic/CMFCMenuBar::EnableHelpCombobox.md)|활성화는  **도움말** 메뉴 막대의 오른쪽에 있는 콤보 상자.|  
|[CMFCMenuBar::EnableMenuShadows](../Topic/CMFCMenuBar::EnableMenuShadows.md)|그림자에 대 한 팝업 메뉴를 표시할지 여부를 지정 합니다.|  
|[CMFCMenuBar::GetAvailableExpandSize](../Topic/CMFCMenuBar::GetAvailableExpandSize.md)|\(재정의 [CPane::GetAvailableExpandSize](../Topic/CPane::GetAvailableExpandSize.md).\)|  
|[CMFCMenuBar::GetColumnWidth](../Topic/CMFCMenuBar::GetColumnWidth.md)|도구 모음 단추의 너비를 반환합니다.  \(재정의 [CMFCToolBar::GetColumnWidth](../Topic/CMFCToolBar::GetColumnWidth.md).\)|  
|[CMFCMenuBar::GetDefaultMenu](../Topic/CMFCMenuBar::GetDefaultMenu.md)|원래 메뉴 리소스 파일에서 핸들을 반환합니다.|  
|[CMFCMenuBar::GetDefaultMenuResId](../Topic/CMFCMenuBar::GetDefaultMenuResId.md)|리소스 파일에 원래 메뉴에 대 한 리소스 식별자를 반환합니다.|  
|[CMFCMenuBar::GetFloatPopupDirection](../Topic/CMFCMenuBar::GetFloatPopupDirection.md)||  
|[CMFCMenuBar::GetForceDownArrows](../Topic/CMFCMenuBar::GetForceDownArrows.md)||  
|[CMFCMenuBar::GetHelpCombobox](../Topic/CMFCMenuBar::GetHelpCombobox.md)|반환에 대 한 포인터는  **도움말** 콤보 상자.|  
|[CMFCMenuBar::GetHMenu](../Topic/CMFCMenuBar::GetHMenu.md)|연결 된 메뉴의 핸들을 반환 된 `CMFCMenuBar` 개체입니다.|  
|[CMFCMenuBar::GetMenuFont](../Topic/CMFCMenuBar::GetMenuFont.md)|현재 글로벌 메뉴 개체에 대 한 글꼴을 반환합니다.|  
|[CMFCMenuBar::GetMenuItem](../Topic/CMFCMenuBar::GetMenuItem.md)|제공 된 항목 인덱스와 연결 된 도구 모음 단추를 반환 합니다.|  
|[CMFCMenuBar::GetRowHeight](../Topic/CMFCMenuBar::GetRowHeight.md)|도구 모음 단추의 높이 반환합니다.  \(재정의 [CMFCToolBar::GetRowHeight](../Topic/CMFCToolBar::GetRowHeight.md).\)|  
|[CMFCMenuBar::GetSystemButton](../Topic/CMFCMenuBar::GetSystemButton.md)||  
|[CMFCMenuBar::GetSystemButtonsCount](../Topic/CMFCMenuBar::GetSystemButtonsCount.md)||  
|[CMFCMenuBar::GetSystemMenu](../Topic/CMFCMenuBar::GetSystemMenu.md)||  
|[CMFCMenuBar::HighlightDisabledItems](../Topic/CMFCMenuBar::HighlightDisabledItems.md)|사용할 수 없는 메뉴 항목을 강조 표시할지 여부를 나타냅니다.|  
|[CMFCMenuBar::IsButtonExtraSizeAvailable](../Topic/CMFCMenuBar::IsButtonExtraSizeAvailable.md)|도구 모음 테두리 확장 된 단추를 표시할 수 있는지 여부를 결정 합니다.  \(재정의 [CMFCToolBar::IsButtonExtraSizeAvailable](../Topic/CMFCToolBar::IsButtonExtraSizeAvailable.md).\)|  
|[CMFCMenuBar::IsHighlightDisabledItems](../Topic/CMFCMenuBar::IsHighlightDisabledItems.md)|사용할 수 없는 항목을 강조 표시할지 여부를 나타냅니다.|  
|[CMFCMenuBar::IsMenuShadows](../Topic/CMFCMenuBar::IsMenuShadows.md)|팝업 메뉴의 그림자 표시 되는지 여부를 나타냅니다.|  
|[CMFCMenuBar::IsRecentlyUsedMenus](../Topic/CMFCMenuBar::IsRecentlyUsedMenus.md)|최근 사용한 메뉴 명령이 메뉴 모음에 표시 되는지 여부를 나타냅니다.|  
|[CMFCMenuBar::IsShowAllCommands](../Topic/CMFCMenuBar::IsShowAllCommands.md)|팝업 메뉴에 모든 명령 표시 여부를 나타냅니다.|  
|[CMFCMenuBar::IsShowAllCommandsDelay](../Topic/CMFCMenuBar::IsShowAllCommandsDelay.md)|메뉴 잠시 후 모든 명령 표시 여부를 나타냅니다.|  
|[CMFCMenuBar::LoadState](../Topic/CMFCMenuBar::LoadState.md)|로드 상태는 `CMFCMenuBar` 개체를 모두 제거에서 합니다.|  
|[CMFCMenuBar::OnChangeHot](../Topic/CMFCMenuBar::OnChangeHot.md)|도구 모음에서 단추를 선택할 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CMFCToolBar::OnChangeHot](../Topic/CMFCToolBar::OnChangeHot.md).\)|  
|[CMFCMenuBar::OnDefaultMenuLoaded](../Topic/CMFCMenuBar::OnDefaultMenuLoaded.md)|프레임 창의 기본 메뉴 리소스 파일에서 로드 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCMenuBar::OnSendCommand](../Topic/CMFCMenuBar::OnSendCommand.md)|\(재정의 `CMFCToolBar::OnSendCommand`.\)|  
|[CMFCMenuBar::OnSetDefaultButtonText](../Topic/CMFCMenuBar::OnSetDefaultButtonText.md)|프레임 워크에서 메뉴 사용자 지정 모드에서 사용자가 메뉴 항목의 텍스트를 변경 하면 호출 됩니다.|  
|[CMFCMenuBar::OnToolHitTest](../Topic/CMFCMenuBar::OnToolHitTest.md)|\(재정의 `CMFCToolBar::OnToolHitTest`.\)|  
|[CMFCMenuBar::PreTranslateMessage](../Topic/CMFCMenuBar::PreTranslateMessage.md)|\(재정의 `CMFCToolBar::PreTranslateMessage`.\)|  
|[CMFCMenuBar::RestoreOriginalstate](../Topic/CMFCMenuBar::RestoreOriginalstate.md)|메뉴 사용자 지정 모드에 있고 사용자가 선택 하면 프레임 워크에서 호출  **재설정** 메뉴 모음.|  
|[CMFCMenuBar::SaveState](../Topic/CMFCMenuBar::SaveState.md)|상태 저장은 `CMFCMenuBar` 레지스트리 개체.|  
|[CMFCMenuBar::SetDefaultMenuResId](../Topic/CMFCMenuBar::SetDefaultMenuResId.md)|원래 메뉴에서 리소스 파일을 설정합니다.|  
|[CMFCMenuBar::SetForceDownArrows](../Topic/CMFCMenuBar::SetForceDownArrows.md)||  
|[CMFCMenuBar::SetMaximizeMode](../Topic/CMFCMenuBar::SetMaximizeMode.md)|MDI 자식 창에서 디스플레이 모드가 변경 될 때 프레임 워크에 의해 호출 됩니다.  새로 최대화 된 MDI 자식 창 최대화 되어 더 이상 경우이 메서드는 메뉴 모음을 업데이트 합니다.|  
|[CMFCMenuBar::SetMenuButtonRTC](../Topic/CMFCMenuBar::SetMenuButtonRTC.md)|사용자 메뉴 단추를 동적으로 만드는 경우 생성 되는 런타임 클래스 정보를 설정 합니다.|  
|[CMFCMenuBar::SetMenuFont](../Topic/CMFCMenuBar::SetMenuFont.md)|응용 프로그램에서 모든 메뉴의 글꼴을 설정합니다.|  
|[CMFCMenuBar::SetRecentlyUsedMenus](../Topic/CMFCMenuBar::SetRecentlyUsedMenus.md)|메뉴 모음 최근 사용한 메뉴 명령을 표시할지 여부를 지정 합니다.|  
|[CMFCMenuBar::SetShowAllCommands](../Topic/CMFCMenuBar::SetShowAllCommands.md)|메뉴 모음에서 모든 명령을 지정 합니다.|  
  
## 설명  
 `CMFCMenuBar` 클래스는 도킹 기능을 구현 하는 메뉴 모음입니다.  이 도구 모음을 유사한 닫을 수 없습니다\-항상 표시 되어 있지만.  
  
 `CMFCMenuBar`최근에 사용 되는 메뉴 항목 개체를 표시 하는 옵션을 지원 합니다.  이 옵션을 사용 하는 경우는 `CMFCMenuBar` 첫 번째 보기에서 사용할 수 있는 명령 중 일부만 표시 합니다.  이후부터 최근에 사용된 된 명령 명령 원본 하위 집합을 함께 표시 됩니다.  또한 사용자가 항상 사용 가능한 모든 명령을 표시 하려면 메뉴를 확장할 수 있습니다.  따라서 각 사용 가능한 명령은 지속적으로 표시 하거나 표시만 최근에 선택한 경우 구성 됩니다.  
  
 사용 하는 `CMFCMenuBar` 개체, 주 창 프레임에 개체를 포함 합니다.  처리 하는 `WM_CREATE` 메시지, 호출 `CMFCMenuBar::Create` 또는 `CMFCMenuBar::CreateEx`.  만들 함수에 관계 없이 사용, 주 프레임 창으로 포인터를 전달 합니다.  다음 호출 하 여 도킹을 사용 [CFrameWndEx::EnableDocking](../Topic/CFrameWndEx::EnableDocking.md).  이 메뉴를 호출 하 여 고정 [CFrameWndEx::DockPane](../Topic/CFrameWndEx::DockPane.md).  
  
## 예제  
 다음 예제에서는 다양 한 방법에 있는 `CMFCMenuBar` 클래스입니다.  이 예제에서는 창 스타일을 설정, 사용자 지정 단추를 사용, 도움말 상자 그림자에 대 한 팝업 메뉴를 사용 및 메뉴 모음이 업데이트 방법을 보여 줍니다.  이 코드 조각에 속해 있는  [IE 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/CPP/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo#3](../../mfc/reference/codesnippet/CPP/cmfcmenubar-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)  
  
## 요구 사항  
 **헤더:** afxmenubar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)