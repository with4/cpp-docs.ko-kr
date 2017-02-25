---
title: "CMFCTasksPane Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTasksPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTasksPane class"
ms.assetid: b456328e-2525-4642-b78b-9edd1a1a7d3f
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMFCTasksPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 `CMFCTasksPane` 클래스는 클릭할 수 있는 항목\(작업\) 목록을 구현합니다.  
  
## 구문  
  
```  
class CMFCTasksPane : public CDockablePane  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CMFCTasksPane::CMFCTasksPane](../Topic/CMFCTasksPane::CMFCTasksPane.md)|`CMFCTasksPane` 개체를 생성합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCTasksPane::AddGroup](../Topic/CMFCTasksPane::AddGroup.md)|작업 창 컨트롤에 새 작업 그룹을 추가합니다.|  
|[CMFCTasksPane::AddLabel](../Topic/CMFCTasksPane::AddLabel.md)|지정된 작업 그룹에 새 정적 레이블을 추가합니다.|  
|[CMFCTasksPane::AddMRUFilesList](../Topic/CMFCTasksPane::AddMRUFilesList.md)|MRU\(가장 최근에 사용됨\) 파일 목록으로 지정된 작업일 그룹에 추가합니다.|  
|[CMFCTasksPane::AddPage](../Topic/CMFCTasksPane::AddPage.md)|작업 창에 새 페이지를 추가합니다.|  
|[CMFCTasksPane::AddSeparator](../Topic/CMFCTasksPane::AddSeparator.md)||  
|[CMFCTasksPane::AddTask](../Topic/CMFCTasksPane::AddTask.md)|지정된 작업 그룹에 새 작업을 추가합니다.|  
|[CMFCTasksPane::AddWindow](../Topic/CMFCTasksPane::AddWindow.md)|작업 창에 자식 창을 추가합니다.|  
|[CMFCTasksPane::CollapseAllGroups](../Topic/CMFCTasksPane::CollapseAllGroups.md)||  
|[CMFCTasksPane::CollapseGroup](../Topic/CMFCTasksPane::CollapseGroup.md)|프로그래밍 방식으로 그룹을 축소합니다.|  
|[CMFCTasksPane::CreateDefaultMiniframe](../Topic/CMFCTasksPane::CreateDefaultMiniframe.md)|\([CPane::CreateDefaultMiniframe](../Topic/CPane::CreateDefaultMiniframe.md)을 재정의합니다.\)|  
|[CMFCTasksPane::CreateMenu](../Topic/CMFCTasksPane::CreateMenu.md)|프레임워크에서 호출되어 **다른 작업 창** 메뉴 단추에 대한 메뉴를 만듭니다.|  
|[CMFCTasksPane::EnableAnimation](../Topic/CMFCTasksPane::EnableAnimation.md)|작업 그룹을 축소 또는 확장하는 동안 애니메이션을 사용하거나 사용하지 않도록 설정합니다.|  
|[CMFCTasksPane::EnableGroupCollapse](../Topic/CMFCTasksPane::EnableGroupCollapse.md)|작업 그룹을 축소할 수 있는지를 지정합니다.|  
|[CMFCTasksPane::EnableHistoryMenuButtons](../Topic/CMFCTasksPane::EnableHistoryMenuButtons.md)|**다음** 및 **이전** 탐색 단추에서 드롭다운 메뉴를 사용하거나 사용하지 않도록 설정합니다.|  
|[CMFCTasksPane::EnableNavigationToolbar](../Topic/CMFCTasksPane::EnableNavigationToolbar.md)|탐색 도구 모음을 사용하거나 사용하지 않도록 설정합니다.|  
|[CMFCTasksPane::EnableOffsetCustomControls](../Topic/CMFCTasksPane::EnableOffsetCustomControls.md)||  
|[CMFCTasksPane::EnableScrollButtons](../Topic/CMFCTasksPane::EnableScrollButtons.md)|스크롤 막대 대신 스크롤 단추를 사용하도록 설정합니다.|  
|[CMFCTasksPane::EnableWrapLabels](../Topic/CMFCTasksPane::EnableWrapLabels.md)|레이블에 대한 자동 줄 바꿈을 사용하거나 사용하지 않도록 설정합니다.|  
|[CMFCTasksPane::EnableWrapTasks](../Topic/CMFCTasksPane::EnableWrapTasks.md)|작업에 대한 자동 줄 바꿈을 사용하거나 사용하지 않도록 설정합니다.|  
|[CMFCTasksPane::GetActivePage](../Topic/CMFCTasksPane::GetActivePage.md)|활성 페이지에 대한 0부터 시작하는 인덱스를 반환합니다.|  
|[CMFCTasksPane::GetGroupCaptionHeight](../Topic/CMFCTasksPane::GetGroupCaptionHeight.md)|그룹 캡션의 높이를 반환합니다.|  
|[CMFCTasksPane::GetGroupCaptionHorzOffset](../Topic/CMFCTasksPane::GetGroupCaptionHorzOffset.md)|작업 창의 왼쪽 및 오른쪽 가장자리에서 그룹 캡션의 현재 오프셋을 반환합니다.|  
|[CMFCTasksPane::GetGroupCaptionVertOffset](../Topic/CMFCTasksPane::GetGroupCaptionVertOffset.md)|작업 창의 위쪽 및 아래쪽 가장자리에서 그룹 캡션의 현재 오프셋을 반환합니다.|  
|[CMFCTasksPane::GetGroupCount](../Topic/CMFCTasksPane::GetGroupCount.md)|총 그룹 수를 반환합니다.|  
|[CMFCTasksPane::GetGroupLocation](../Topic/CMFCTasksPane::GetGroupLocation.md)|지정된 그룹에 대한 내부 그룹 인덱스를 반환합니다.|  
|[CMFCTasksPane::GetGroupVertOffset](../Topic/CMFCTasksPane::GetGroupVertOffset.md)|그룹의 세로 오프셋을 반환합니다.|  
|[CMFCTasksPane::GetHorzMargin](../Topic/CMFCTasksPane::GetHorzMargin.md)|작업 창과 클라이언트 영역 가장자리 사이의 가로 간격을 반환합니다.|  
|[CMFCTasksPane::GetNextPages](../Topic/CMFCTasksPane::GetNextPages.md)||  
|[CMFCTasksPane::GetPageByGroup](../Topic/CMFCTasksPane::GetPageByGroup.md)|지정된 그룹에 대한 페이지 인덱스를 검색합니다.|  
|[CMFCTasksPane::GetPagesCount](../Topic/CMFCTasksPane::GetPagesCount.md)|페이지 수를 반환합니다.|  
|[CMFCTasksPane::GetPreviousPages](../Topic/CMFCTasksPane::GetPreviousPages.md)||  
|[CMFCTasksPane::GetScrollBarCtrl](../Topic/CMFCTasksPane::GetScrollBarCtrl.md)|\([CWnd::GetScrollBarCtrl](../Topic/CWnd::GetScrollBarCtrl.md)을 재정의합니다.\)|  
|[CMFCTasksPane::GetTask](../Topic/CMFCTasksPane::GetTask.md)|작업을 검색합니다.|  
|[CMFCTasksPane::GetTaskCount](../Topic/CMFCTasksPane::GetTaskCount.md)|지정된 그룹의 작업 항목 수를 반환합니다.|  
|[CMFCTasksPane::GetTaskGroup](../Topic/CMFCTasksPane::GetTaskGroup.md)|지정된 그룹 인덱스에 대한 작업 그룹을 반환합니다.|  
|[CMFCTasksPane::GetTaskLocation](../Topic/CMFCTasksPane::GetTaskLocation.md)|지정된 작업에 대한 그룹 및 인덱스를 반환합니다.|  
|[CMFCTasksPane::GetTasksHorzOffset](../Topic/CMFCTasksPane::GetTasksHorzOffset.md)|해당 부모 그룹의 왼쪽 및 오른쪽 가장자리부터 작업의 가로 오프셋을 반환합니다.|  
|[CMFCTasksPane::GetTasksIconHorzOffset](../Topic/CMFCTasksPane::GetTasksIconHorzOffset.md)||  
|[CMFCTasksPane::GetTasksIconVertOffset](../Topic/CMFCTasksPane::GetTasksIconVertOffset.md)||  
|[CMFCTasksPane::GetVertMargin](../Topic/CMFCTasksPane::GetVertMargin.md)|작업 창과 클라이언트 영역 가장자리 사이의 세로 간격을 반환합니다.|  
|[CMFCTasksPane::IsAccessibilityCompatible](../Topic/CMFCTasksPane::IsAccessibilityCompatible.md)|\(`CDockablePane::IsAccessibilityCompatible`을 재정의합니다.\)|  
|[CMFCTasksPane::IsAnimationEnabled](../Topic/CMFCTasksPane::IsAnimationEnabled.md)|애니메이션의 사용 여부를 나타냅니다.|  
|[CMFCTasksPane::IsBackButtonEnabled](../Topic/CMFCTasksPane::IsBackButtonEnabled.md)|뒤로 단추의 사용 여부를 나타냅니다.|  
|[CMFCTasksPane::IsForwardButtonEnabled](../Topic/CMFCTasksPane::IsForwardButtonEnabled.md)|앞으로 단추의 사용 여부를 나타냅니다.|  
|[CMFCTasksPane::IsGroupCollapseEnabled](../Topic/CMFCTasksPane::IsGroupCollapseEnabled.md)||  
|[CMFCTasksPane::IsHistoryMenuButtonsEnabled](../Topic/CMFCTasksPane::IsHistoryMenuButtonsEnabled.md)|**다음** 및 **이전** 탐색 단추에 드롭다운 메뉴를 포함하는지를 나타냅니다.|  
|[CMFCTasksPane::IsNavigationToolbarEnabled](../Topic/CMFCTasksPane::IsNavigationToolbarEnabled.md)|탐색 도구 모음이 사용되는지를 나타냅니다.|  
|[CMFCTasksPane::IsToolBox](../Topic/CMFCTasksPane::IsToolBox.md)||  
|[CMFCTasksPane::IsWrapLabelsEnabled](../Topic/CMFCTasksPane::IsWrapLabelsEnabled.md)|작업 창의 레이블이 자동 줄 바꿈되는지를 나타냅니다.|  
|[CMFCTasksPane::IsWrapTasksEnabled](../Topic/CMFCTasksPane::IsWrapTasksEnabled.md)|작업 창의 작업이 자동 줄 바꿈되는지를 나타냅니다.|  
|[CMFCTasksPane::LoadState](../Topic/CMFCTasksPane::LoadState.md)|\([CDockablePane::LoadState](http://msdn.microsoft.com/ko-kr/96110136-4f46-4764-8a76-3b4abaf77917)를 재정의합니다.\)|  
|[CMFCTasksPane::OnCancel](../Topic/CMFCTasksPane::OnCancel.md)||  
|[CMFCTasksPane::OnClickTask](../Topic/CMFCTasksPane::OnClickTask.md)|사용자가 작업 창에서 항목을 클릭하면 프레임워크에서 호출됩니다.|  
|[CMFCTasksPane::OnOK](../Topic/CMFCTasksPane::OnOK.md)||  
|[CMFCTasksPane::OnPressBackButton](../Topic/CMFCTasksPane::OnPressBackButton.md)|사용자가 뒤로 단추를 클릭하면 프레임워크에서 호출됩니다.|  
|[CMFCTasksPane::OnPressForwardButton](../Topic/CMFCTasksPane::OnPressForwardButton.md)|사용자가 앞으로 탐색 단추를 클릭하면 프레임워크에서 호출됩니다.|  
|[CMFCTasksPane::OnPressHomeButton](../Topic/CMFCTasksPane::OnPressHomeButton.md)|사용자가 홈 탐색 단추를 클릭하면 프레임워크에서 호출됩니다.|  
|[CMFCTasksPane::OnPressOtherButton](../Topic/CMFCTasksPane::OnPressOtherButton.md)||  
|[CMFCTasksPane::OnSetAccData](../Topic/CMFCTasksPane::OnSetAccData.md)|\([CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md)를 재정의합니다.\)|  
|[CMFCTasksPane::OnUpdateCmdUI](../Topic/CMFCTasksPane::OnUpdateCmdUI.md)|\([CDockablePane::OnUpdateCmdUI](http://msdn.microsoft.com/ko-kr/5dd61606-1c12-40d4-b024-f3839aa5e2e0)를 재정의합니다.\)|  
|[CMFCTasksPane::PreTranslateMessage](../Topic/CMFCTasksPane::PreTranslateMessage.md)|\([CDockablePane::PreTranslateMessage](http://msdn.microsoft.com/ko-kr/49a242cc-b158-400e-9e01-0345ec9c3ffd)를 재정의합니다.\)|  
|[CMFCTasksPane::RecalcLayout](../Topic/CMFCTasksPane::RecalcLayout.md)|\([CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md)을 재정의합니다.\)|  
|[CMFCTasksPane::RemoveAllGroups](../Topic/CMFCTasksPane::RemoveAllGroups.md)|지정된 페이지에서 모든 그룹을 제거합니다.|  
|[CMFCTasksPane::RemoveAllPages](../Topic/CMFCTasksPane::RemoveAllPages.md)|기본\(첫 번째\) 페이지를 제외한 모든 페이지를 작업 창에서 제거합니다.|  
|[CMFCTasksPane::RemoveAllTasks](../Topic/CMFCTasksPane::RemoveAllTasks.md)|그룹에서 모든 작업을 제거합니다.|  
|[CMFCTasksPane::RemoveGroup](../Topic/CMFCTasksPane::RemoveGroup.md)|그룹을 제거합니다.|  
|[CMFCTasksPane::RemovePage](../Topic/CMFCTasksPane::RemovePage.md)|작업 창에서 지정된 페이지를 제거합니다.|  
|[CMFCTasksPane::RemoveTask](../Topic/CMFCTasksPane::RemoveTask.md)|작업 그룹에서 작업을 제거합니다.|  
|[CMFCTasksPane::SaveState](../Topic/CMFCTasksPane::SaveState.md)|\([CDockablePane::SaveState](http://msdn.microsoft.com/ko-kr/c5c24249-8d0d-46cb-96d9-9f5c6dc191db)를 재정의합니다.\)|  
|[CMFCTasksPane::Serialize](../Topic/CMFCTasksPane::Serialize.md)|\([CDockablePane::Serialize](http://msdn.microsoft.com/ko-kr/09787e59-e446-4e76-894b-206d303dcfd6)를 재정의합니다.\)|  
|[CMFCTasksPane::SetActivePage](../Topic/CMFCTasksPane::SetActivePage.md)|작업 창에서 지정된 페이지를 활성화합니다.|  
|[CMFCTasksPane::SetCaption](../Topic/CMFCTasksPane::SetCaption.md)|작업 창의 캡션 이름을 설정합니다.|  
|[CMFCTasksPane::SetGroupCaptionHeight](../Topic/CMFCTasksPane::SetGroupCaptionHeight.md)|그룹 캡션의 높이를 설정합니다.|  
|[CMFCTasksPane::SetGroupCaptionHorzOffset](../Topic/CMFCTasksPane::SetGroupCaptionHorzOffset.md)|그룹 캡션의 가로 오프셋을 설정합니다.|  
|[CMFCTasksPane::SetGroupCaptionVertOffset](../Topic/CMFCTasksPane::SetGroupCaptionVertOffset.md)|그룹 캡션의 세로 오프셋을 설정합니다.|  
|[CMFCTasksPane::SetGroupName](../Topic/CMFCTasksPane::SetGroupName.md)|그룹 이름을 설정합니다.|  
|[CMFCTasksPane::SetGroupTextColor](../Topic/CMFCTasksPane::SetGroupTextColor.md)|그룹 캡션에 대한 텍스트 색을 설정합니다.|  
|[CMFCTasksPane::SetGroupVertOffset](../Topic/CMFCTasksPane::SetGroupVertOffset.md)|그룹에 대한 세로 오프셋을 설정합니다.|  
|[CMFCTasksPane::SetHorzMargin](../Topic/CMFCTasksPane::SetHorzMargin.md)|작업 창과 클라이언트 영역 가장자리 사이의 가로 간격을 설정합니다.|  
|[CMFCTasksPane::SetIconsList](../Topic/CMFCTasksPane::SetIconsList.md)|작업과 연결된 이미지 목록을 설정합니다.|  
|[CMFCTasksPane::SetPageCaption](../Topic/CMFCTasksPane::SetPageCaption.md)|작업 창 페이지에 대한 캡션 텍스트를 설정합니다.|  
|[CMFCTasksPane::SetTaskName](../Topic/CMFCTasksPane::SetTaskName.md)|작업에 대한 이름을 설정합니다.|  
|[CMFCTasksPane::SetTasksIconHorzOffset](../Topic/CMFCTasksPane::SetTasksIconHorzOffset.md)||  
|[CMFCTasksPane::SetTasksIconVertOffset](../Topic/CMFCTasksPane::SetTasksIconVertOffset.md)||  
|[CMFCTasksPane::SetTaskTextColor](../Topic/CMFCTasksPane::SetTaskTextColor.md)|작업에 대한 텍스트 색을 설정합니다.|  
|[CMFCTasksPane::SetTasksHorzOffset](../Topic/CMFCTasksPane::SetTasksHorzOffset.md)|해당 부모 그룹의 왼쪽 및 오른쪽 가장자리부터 작업의 가로 오프셋을 설정합니다.|  
|[CMFCTasksPane::SetVertMargin](../Topic/CMFCTasksPane::SetVertMargin.md)|작업 창과 클라이언트 영역 가장자리 사이의 세로 간격을 설정합니다.|  
|[CMFCTasksPane::SetWindowHeight](../Topic/CMFCTasksPane::SetWindowHeight.md)|창의 높이 설정합니다.|  
|[CMFCTasksPane::ShowCommandMessageString](../Topic/CMFCTasksPane::ShowCommandMessageString.md)||  
|[CMFCTasksPane::ShowTask](../Topic/CMFCTasksPane::ShowTask.md)|작업을 표시하거나 숨깁니다.|  
|[CMFCTasksPane::ShowTaskByCmdId](../Topic/CMFCTasksPane::ShowTaskByCmdId.md)|명령 ID를 기준으로 작업을 표시하거나 숨깁니다.|  
|[CMFCTasksPane::Update](../Topic/CMFCTasksPane::Update.md)|작업 창에 속하는 GUI 요소를 업데이트합니다.|  
  
### Protected 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCTasksPane::OnActivateTasksPanePage](../Topic/CMFCTasksPane::OnActivateTasksPanePage.md)|새 작업 창 페이지가 활성화될 때 프레임워크에서 호출됩니다.|  
  
## 설명  
 `CMFCTasksPane` 클래스는 다음 기능을 구현합니다.  
  
-   항목을 그룹화할 수 있고 각 항목 그룹에는 연결된 캡션이 포함될 수 있습니다.  
  
-   항목 그룹을 축소하거나 확장할 수 있습니다.  
  
-   작업 창에서 각 항목에 아이콘을 할당할 수 있습니다.  
  
-   개별 항목은 사용자가 항목을 클릭할 때 실행되는 명령 ID와 연결될 수 있습니다.  클릭이 발생하면 `WM_COMMAND` 메시지가 작업 창 컨트롤의 소유자에게 전송됩니다.  
  
 응용 프로그램에서 `CMFCTasksPane` 컨트롤을 사용하려면 다음 단계를 수행합니다.  
  
1.  `CMFCTasksPane` 개체를 주 프레임 창 클래스에 포함합니다.  
  
2.  `WM_CREATE` 메시지를 처리할 때 `Create` 메서드를 호출합니다.  일반 [CControlBar](../../mfc/reference/ccontrolbar-class.md) 스타일을 사용할 수 있습니다.  자세한 내용은 `CControlBar::Create`을 참조하세요.  
  
3.  [CMFCTasksPane::AddGroup](../Topic/CMFCTasksPane::AddGroup.md) 메서드를 호출하여 다양한 그룹을 추가합니다.  
  
4.  [CMFCTasksPane::AddTask](../Topic/CMFCTasksPane::AddTask.md), [CMFCTasksPane::AddLabel](../Topic/CMFCTasksPane::AddLabel.md) 또는 [CMFCTasksPane::AddMRUFilesList](../Topic/CMFCTasksPane::AddMRUFilesList.md) 멤버 함수를 호출하여 새 항목\(작업\)을 각 그룹에 추가합니다.  
  
5.  [CMFCTasksPane::EnableGroupCollapse](../Topic/CMFCTasksPane::EnableGroupCollapse.md)를 호출하여 항목 그룹을 축소할 수 있는지를 지정합니다.  
  
 다음 그림에서는 일반적인 작업 창 컨트롤을 보여 줍니다.  첫 번째 그룹은 *특수* 그룹이고 해당 캡션은 더 진한 색입니다.  세 번째 그룹이 축소됩니다.  마지막 그룹은 작업 창의 아래쪽에 맞춰지고 캡션을 포함하지 않고, 그룹의 마지막 작업은 단순한 레이블입니다.  
  
 ![작업 창 예제](../../mfc/reference/media/nexttaskpane.png "NextTaskPane")  
  
 다양한 여백 및 오프셋을 조정하여 작업 창의 모양을 사용자 지정할 수 있습니다.  다음 그림에서는 이들 변수의 의미를 분명히 설명합니다.  
  
 ![사용자 지정 작업 그룹](../../mfc/reference/media/nexttaskgrpcustom.png "NextTaskGrpCustom")  
  
## 예제  
 다음 예제에서는 `CMFCTasksPane` 개체를 생성하고 `CMFCTasksPane` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다.  예제에서는 작업 그룹 축소를 사용하도록 설정하고, **다음** 및 **이전** 탐색 단추에서 드롭다운 메뉴를 사용하도록 설정하고, 스크롤 막대 대신 스크롤 단추를 사용하도록 설정하고, 레이블 텍스트에서 자동 줄 바꿈을 사용하도록 설정하고, 작업 창의 캡션 이름을 설정하고, 그룹 캡션에 대한 텍스트 색을 설정하고, 가로 및 세로 여백을 설정하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#28](../../mfc/reference/codesnippet/CPP/cmfctaskspane-class_1.cpp)]  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)  
  
## 요구 사항  
 **헤더:** afxTasksPane.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCTasksPaneTaskGroup Class](../../mfc/reference/cmfctaskspanetaskgroup-class.md)   
 [CMFCTasksPaneTask Class](../../mfc/reference/cmfctaskspanetask-class.md)   
 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)