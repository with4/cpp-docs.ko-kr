---
title: "CMFCPopupMenu Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPopupMenu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPopupMenu class"
ms.assetid: 9555dca1-8c9c-44c9-af72-0659ddad128e
caps.latest.revision: 40
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 42
---
# CMFCPopupMenu Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 팝업 메뉴 기능을 구현 하 고 분리 된 메뉴 및 도구 설명 기능을 추가 하 여 확장 합니다.  
  
## 구문  
  
```  
class CMFCPopupMenu : public CMiniFrameWnd  
```  
  
## Members  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCPopupMenu::CMFCPopupMenu](../Topic/CMFCPopupMenu::CMFCPopupMenu.md)|`CMFCPopupMenu` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCPopupMenu::ActivatePopupMenu](../Topic/CMFCPopupMenu::ActivatePopupMenu.md)||  
|[CMFCPopupMenu::AlwaysShowEmptyToolsEntry](../Topic/CMFCPopupMenu::AlwaysShowEmptyToolsEntry.md)|사용자 정의 도구에 대해 빈 항목을 표시 하는 팝업 메뉴 사용 가능 여부를 설정 합니다.|  
|[CMFCPopupMenu::AreAllCommandsShown](../Topic/CMFCPopupMenu::AreAllCommandsShown.md)||  
|[CMFCPopupMenu::CheckArea](../Topic/CMFCPopupMenu::CheckArea.md)|팝업 메뉴에 상대적인 점의 위치를 결정합니다.|  
|[CMFCPopupMenu::CloseMenu](../Topic/CMFCPopupMenu::CloseMenu.md)||  
|[CMFCPopupMenu::Create](../Topic/CMFCPopupMenu::Create.md)|팝업 메뉴를 만들고이에 연결 된 `CMFCPopupMenu` 개체입니다.|  
|[CMFCPopupMenu::DefaultMouseClickOnClose](../Topic/CMFCPopupMenu::DefaultMouseClickOnClose.md)||  
|[CMFCPopupMenu::EnableMenuLogo](../Topic/CMFCPopupMenu::EnableMenuLogo.md)|팝업 메뉴에 대 한 로고를 초기화합니다.|  
|[CMFCPopupMenu::EnableMenuSound](../Topic/CMFCPopupMenu::EnableMenuSound.md)|소리를 메뉴 있습니다.|  
|[CMFCPopupMenu::EnableResize](../Topic/CMFCPopupMenu::EnableResize.md)||  
|[CMFCPopupMenu::EnableScrolling](../Topic/CMFCPopupMenu::EnableScrolling.md)||  
|[CMFCPopupMenu::EnableVertResize](../Topic/CMFCPopupMenu::EnableVertResize.md)||  
|[CMFCPopupMenu::FindSubItemByCommand](../Topic/CMFCPopupMenu::FindSubItemByCommand.md)||  
|[CMFCPopupMenu::GetActiveMenu](../Topic/CMFCPopupMenu::GetActiveMenu.md)|현재 활성 메뉴를 반환합니다.|  
|[CMFCPopupMenu::GetAnimationSpeed](../Topic/CMFCPopupMenu::GetAnimationSpeed.md)|애니메이션 속도 팝업 메뉴를 반환합니다.|  
|[CMFCPopupMenu::GetAnimationType](../Topic/CMFCPopupMenu::GetAnimationType.md)|현재 팝업 메뉴 애니메이션 유형을 반환합니다.|  
|[CMFCPopupMenu::GetDropDirection](../Topic/CMFCPopupMenu::GetDropDirection.md)||  
|[CMFCPopupMenu::GetForceMenuFocus](../Topic/CMFCPopupMenu::GetForceMenuFocus.md)|팝업 메뉴가 표시 될 때 도구 모음 메뉴에 포커스를 반환 하는지 여부를 나타냅니다.|  
|[CMFCPopupMenu::GetForceShadow](../Topic/CMFCPopupMenu::GetForceShadow.md)||  
|[CMFCPopupMenu::GetHMenu](../Topic/CMFCPopupMenu::GetHMenu.md)|핸들에 연결 된 메뉴 리소스를 반환합니다.|  
|[CMFCPopupMenu::GetMenuBar](../Topic/CMFCPopupMenu::GetMenuBar.md)|반환 된  [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) 팝업 메뉴 안에 포함 됩니다.|  
|[CMFCPopupMenu::GetMenuItem](../Topic/CMFCPopupMenu::GetMenuItem.md)|메뉴 항목의 지정 된 인덱스에 대 한 포인터를 반환합니다.|  
|[CMFCPopupMenu::GetMenuItemCount](../Topic/CMFCPopupMenu::GetMenuItemCount.md)|팝업 메뉴에서 항목 수를 반환합니다.|  
|[CMFCPopupMenu::GetMessageWnd](../Topic/CMFCPopupMenu::GetMessageWnd.md)|위치 프레임 워크 팝업 메뉴 메시지를 라우트 창으로 포인터를 반환 합니다.|  
|[CMFCPopupMenu::GetParentArea](../Topic/CMFCPopupMenu::GetParentArea.md)||  
|[CMFCPopupMenu::GetParentButton](../Topic/CMFCPopupMenu::GetParentButton.md)|상위 도구 모음 단추에 포인터를 반환 합니다.|  
|[CMFCPopupMenu::GetParentPopupMenu](../Topic/CMFCPopupMenu::GetParentPopupMenu.md)|부모 팝업 메뉴에 대 한 포인터를 반환합니다.|  
|[CMFCPopupMenu::GetParentRibbonElement](../Topic/CMFCPopupMenu::GetParentRibbonElement.md)||  
|[CMFCPopupMenu::GetParentToolBar](../Topic/CMFCPopupMenu::GetParentToolBar.md)|부모 도구 모음에 포인터를 반환 합니다.|  
|[CMFCPopupMenu::GetQuickCustomizeType](../Topic/CMFCPopupMenu::GetQuickCustomizeType.md)||  
|[CMFCPopupMenu::GetSelItem](../Topic/CMFCPopupMenu::GetSelItem.md)|현재 선택한 메뉴 명령에 대 한 포인터를 반환합니다.|  
|[CMFCPopupMenu::HasBeenResized](../Topic/CMFCPopupMenu::HasBeenResized.md)||  
|[CMFCPopupMenu::HideRarelyUsedCommands](../Topic/CMFCPopupMenu::HideRarelyUsedCommands.md)|거의 사용된 되지 않는 명령 팝업 메뉴 숨길 수 있는지 여부를 나타냅니다.|  
|[CMFCPopupMenu::InCommand](../Topic/CMFCPopupMenu::InCommand.md)||  
|[CMFCPopupMenu::InsertItem](../Topic/CMFCPopupMenu::InsertItem.md)|지정한 위치에 팝업 메뉴에 새 항목을 삽입합니다.|  
|[CMFCPopupMenu::InsertSeparator](../Topic/CMFCPopupMenu::InsertSeparator.md)|지정 된 위치에 팝업 메뉴 구분 기호를 삽입합니다.|  
|[CMFCPopupMenu::IsAlwaysClose](../Topic/CMFCPopupMenu::IsAlwaysClose.md)||  
|[CMFCPopupMenu::IsAlwaysShowEmptyToolsEntry](../Topic/CMFCPopupMenu::IsAlwaysShowEmptyToolsEntry.md)||  
|[CMFCPopupMenu::IsCustomizePane](../Topic/CMFCPopupMenu::IsCustomizePane.md)|팝업 메뉴 다음으로 작동 하는지 여부를 나타내는 한  **QuickCustomizePane**.|  
|[CMFCPopupMenu::IsEscClose](../Topic/CMFCPopupMenu::IsEscClose.md)||  
|[CMFCPopupMenu::IsIdle](../Topic/CMFCPopupMenu::IsIdle.md)|팝업 메뉴는 현재 유휴 상태 인지 여부를 나타냅니다.|  
|[CMFCPopupMenu::IsMenuSound](../Topic/CMFCPopupMenu::IsMenuSound.md)||  
|[CMFCPopupMenu::IsQuickCustomize](../Topic/CMFCPopupMenu::IsQuickCustomize.md)|결정 여부는 관련 [CMFCToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md) QuickCustomize 모드에 있습니다.|  
|[CMFCPopupMenu::IsResizeble](../Topic/CMFCPopupMenu::IsResizeble.md)||  
|[CMFCPopupMenu::IsRightAlign](../Topic/CMFCPopupMenu::IsRightAlign.md)|메뉴의 오른쪽 맞춤 또는 왼쪽 맞춤 여부를 나타냅니다.|  
|[CMFCPopupMenu::IsScrollable](../Topic/CMFCPopupMenu::IsScrollable.md)||  
|[CMFCPopupMenu::IsSendMenuSelectMsg](../Topic/CMFCPopupMenu::IsSendMenuSelectMsg.md)|팝업 메뉴에서 명령을 선택할 때 상위 프레임의 프레임 워크에 알립니다 여부를 나타냅니다.|  
|[CMFCPopupMenu::IsShown](../Topic/CMFCPopupMenu::IsShown.md)|팝업 메뉴를 현재 표시 되는지 여부를 나타냅니다.|  
|[CMFCPopupMenu::MoveTo](../Topic/CMFCPopupMenu::MoveTo.md)||  
|[CMFCPopupMenu::OnCmdMsg](../Topic/CMFCPopupMenu::OnCmdMsg.md)|\(재정의 `CFrameWnd::OnCmdMsg`.\)|  
|[CMFCPopupMenu::PostCommand](../Topic/CMFCPopupMenu::PostCommand.md)||  
|[CMFCPopupMenu::PreTranslateMessage](../Topic/CMFCPopupMenu::PreTranslateMessage.md)|\(재정의 `CFrameWnd::PreTranslateMessage`.\)|  
|[CMFCPopupMenu::RecalcLayout](../Topic/CMFCPopupMenu::RecalcLayout.md)|프레임 워크에서 프레임 창 크기를 조정할 때 또는 표준 컨트롤 막대를 설정 \/ 해제할 때 호출 됩니다.  \(재정의 [CFrameWnd::RecalcLayout](../Topic/CFrameWnd::RecalcLayout.md).\)|  
|[CMFCPopupMenu::RemoveAllItems](../Topic/CMFCPopupMenu::RemoveAllItems.md)|팝업 메뉴에서 모든 항목을 지웁니다.|  
|[CMFCPopupMenu::RemoveItem](../Topic/CMFCPopupMenu::RemoveItem.md)|팝업 메뉴에서 지정 된 항목을 제거합니다.|  
|[CMFCPopupMenu::SaveState](../Topic/CMFCPopupMenu::SaveState.md)||  
|[CMFCPopupMenu::SetAnimationSpeed](../Topic/CMFCPopupMenu::SetAnimationSpeed.md)|팝업 메뉴에 대 한 애니메이션 속도 설정합니다.|  
|[CMFCPopupMenu::SetAnimationType](../Topic/CMFCPopupMenu::SetAnimationType.md)|팝업 메뉴는 애니메이션 형식을 설정합니다.|  
|[CMFCPopupMenu::SetAutoDestroy](../Topic/CMFCPopupMenu::SetAutoDestroy.md)||  
|[CMFCPopupMenu::SetDefaultItem](../Topic/CMFCPopupMenu::SetDefaultItem.md)|팝업 메뉴의 기본 명령을 설정합니다.|  
|[CMFCPopupMenu::SetForceMenuFocus](../Topic/CMFCPopupMenu::SetForceMenuFocus.md)|표시줄 팝업 메뉴가 표시 될 때 메뉴를 반환 하는 입력된 포커스를 강제로.|  
|[CMFCPopupMenu::SetForceShadow](../Topic/CMFCPopupMenu::SetForceShadow.md)|외부 주 프레임 팝업 메뉴를 표시 하면 메뉴 그림자를 그리려면 프레임 워크를 강제로.|  
|[CMFCPopupMenu::SetMaxWidth](../Topic/CMFCPopupMenu::SetMaxWidth.md)|팝업 메뉴에 대 한 최대 너비를 설정 합니다.|  
|[CMFCPopupMenu::SetMessageWnd](../Topic/CMFCPopupMenu::SetMessageWnd.md)||  
|[CMFCPopupMenu::SetParentRibbonElement](../Topic/CMFCPopupMenu::SetParentRibbonElement.md)||  
|[CMFCPopupMenu::SetQuickCustomizeType](../Topic/CMFCPopupMenu::SetQuickCustomizeType.md)||  
|[CMFCPopupMenu::SetQuickMode](../Topic/CMFCPopupMenu::SetQuickMode.md)||  
|[CMFCPopupMenu::SetRightAlign](../Topic/CMFCPopupMenu::SetRightAlign.md)|메뉴 팝업 메뉴의 맞춤을 설정합니다.|  
|[CMFCPopupMenu::SetSendMenuSelectMsg](../Topic/CMFCPopupMenu::SetSendMenuSelectMsg.md)|사용자가 명령을 선택 하면 팝업 메뉴의 상위 프레임 알립니다 여부를 제어 하는 플래그를 설정 합니다.|  
|[CMFCPopupMenu::ShowAllCommands](../Topic/CMFCPopupMenu::ShowAllCommands.md)|팝업 메뉴에 모든 명령 표시 됩니다.|  
|[CMFCPopupMenu::TriggerResize](../Topic/CMFCPopupMenu::TriggerResize.md)||  
|[CMFCPopupMenu::UpdateAllShadows](../Topic/CMFCPopupMenu::UpdateAllShadows.md)|그림자의 모든 열린된 팝업 메뉴를 업데이트합니다.|  
|[CMFCPopupMenu::UpdateShadow](../Topic/CMFCPopupMenu::UpdateShadow.md)|팝업 메뉴에 대 한 그림자를 업데이트합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCPopupMenu::CreateTearOffBar](../Topic/CMFCPopupMenu::CreateTearOffBar.md)||  
|[CMFCPopupMenu::OnChangeHot](../Topic/CMFCPopupMenu::OnChangeHot.md)||  
|[CMFCPopupMenu::OnChooseItem](../Topic/CMFCPopupMenu::OnChooseItem.md)||  
  
### 설명  
 일반적으로 MFC는 팝업 메뉴를 자동으로 만듭니다.  원하는 경우는 `CMFCPopupMenu` 수동으로 개체, 하나는 힙에 할당 하 고 호출 [CMFCPopupMenu::Create](../Topic/CMFCPopupMenu::Create.md).  
  
## 예제  
 다음 예제에서는 팝업 메뉴 개체를 구성 하는 방법을 보여 줍니다.  예제 로고 및 팝업 메뉴의 사운드 설정, 애니메이션 속도 및 유형을 설정, 외부 주 프레임 팝업 메뉴 표시 될 때 메뉴 그림자, 최대 너비를 설정 합니다. 그리고 오른쪽 메뉴 팝업 메뉴의 맞춤을 설정 하는 방법을 보여 줍니다.  이 코드 조각에 속하지는  [샘플 사용자 지정 페이지](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#2](../../mfc/reference/codesnippet/CPP/cmfcpopupmenu-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
## 요구 사항  
 **헤더:** afxpopupmenu.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenuBar 클래스](../../mfc/reference/cmfcpopupmenubar-class.md)