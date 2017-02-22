---
title: "CMFCTabCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTabCtrl class"
  - "CMFCTabCtrl constructor"
  - "CMFCTabCtrl::GetTabFromPoint method"
  - "CMFCTabCtrl::IsPtInTabArea method"
  - "CMFCTabCtrl::MoveTab method"
  - "CMFCTabCtrl::PreTranslateMessage method"
  - "CMFCTabCtrl::RecalcLayout method"
  - "CMFCTabCtrl::SwapTabs method"
ms.assetid: d441385d-2c72-4203-96fa-deae2273da35
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCTabCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCTabCtrl` 클래스 탭 컨트롤에 대 한 기능을 제공 합니다.  탭 컨트롤의 위쪽 이나 아래쪽에 도킹 가능한 창을 평면 또는 3 차원 탭을 표시합니다.  탭 텍스트와 이미지를 표시 하 고 활성화 된 경우 색을 변경할 수 있습니다.  
  
## 구문  
  
```  
class CMFCTabCtrl : public CMFCBaseTabCtrl  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CMFCTabCtrl::CMFCTabCtrl`|기본 생성자입니다.|  
|`CMFCTabCtrl::~CMFCTabCtrl`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCTabCtrl::ActivateMDITab](../Topic/CMFCTabCtrl::ActivateMDITab.md)|지정 된 탭을 현재 탭 컨트롤의 표시 및 해당 탭에 포커스를 설정 합니다.|  
|[CMFCTabCtrl::AllowDestroyEmptyTabbedPane](../Topic/CMFCTabCtrl::AllowDestroyEmptyTabbedPane.md)||  
|[CMFCTabCtrl::AutoSizeWindow](../Topic/CMFCTabCtrl::AutoSizeWindow.md)|프레임 워크 사용자 인터페이스 요소의 탭 컨트롤 변경 하면 모든 탭 컨트롤 창의 클라이언트 영역 크기를 조정할 수 있는지 여부를 지정 합니다.|  
|[CMFCTabCtrl::CalcRectEdit](../Topic/CMFCTabCtrl::CalcRectEdit.md)|지정 된 탭 영역의 크기를 수축 시킵니다.  \(재정의 `CMFCBaseTabCtrl::CalcRectEdit`.\)|  
|[CMFCTabCtrl::Create](../Topic/CMFCTabCtrl::Create.md)|탭 컨트롤을 만들고이에 연결 된 `CMFCTabCtrl` 개체입니다.|  
|`CMFCTabCtrl::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|[CMFCTabCtrl::EnableActiveTabCloseButton](../Topic/CMFCTabCtrl::EnableActiveTabCloseButton.md)|표시 하거나 숨깁니다. 닫기 단추 \(**X**\) 활성 탭.|  
|[CMFCTabCtrl::EnableInPlaceEdit](../Topic/CMFCTabCtrl::EnableInPlaceEdit.md)|편집 가능한 탭 레이블을 사용할 수 있거나.  \(재정의 [CMFCBaseTabCtrl::EnableInPlaceEdit](../Topic/CMFCBaseTabCtrl::EnableInPlaceEdit.md).\)|  
|[CMFCTabCtrl::EnableTabDocumentsMenu](../Topic/CMFCTabCtrl::EnableTabDocumentsMenu.md)|창 탭 탭된 창에는 메뉴를 여는 단추와 스크롤 두 단추를 대체 합니다.|  
|[CMFCTabCtrl::EnsureVisible](../Topic/CMFCTabCtrl::EnsureVisible.md)|탭에 표시 됩니다.|  
|[CMFCTabCtrl::GetDocumentIcon](../Topic/CMFCTabCtrl::GetDocumentIcon.md)|탭 팝업 메뉴를 탭된 창에 연결 된 기호를 검색 합니다.|  
|[CMFCTabCtrl::GetFirstVisibleTabNum](../Topic/CMFCTabCtrl::GetFirstVisibleTabNum.md)|탭 컨트롤에 현재 표시 된 첫 번째 탭의 인덱스를 검색 합니다.|  
|[CMFCTabCtrl::GetResizeMode](../Topic/CMFCTabCtrl::GetResizeMode.md)|현재 탭 컨트롤 크기를 조정할 수는 지정 하는 값을 검색 합니다.|  
|[CMFCTabCtrl::GetScrollBar](../Topic/CMFCTabCtrl::GetScrollBar.md)|탭 컨트롤에 연결 된 스크롤 막대 개체에 대 한 포인터를 검색 합니다.|  
|[CMFCTabCtrl::GetTabArea](../Topic/CMFCTabCtrl::GetTabArea.md)|탭 레이블 영역 위쪽 이나 아래쪽에 탭 컨트롤의 경계 사각형을 검색합니다.  \(재정의 [CMFCBaseTabCtrl::GetTabArea](../Topic/CMFCBaseTabCtrl::GetTabArea.md).\)|  
|`CMFCTabCtrl::GetTabFromPoint`|지정 된 위치에 있는 탭을 검색 합니다.  \(재정의 [CMFCBaseTabCtrl::GetTabFromPoint](../Topic/CMFCBaseTabCtrl::GetTabFromPoint.md).\)|  
|[CMFCTabCtrl::GetTabMaxWidth](../Topic/CMFCTabCtrl::GetTabMaxWidth.md)|탭의 최대 너비를 검색합니다.|  
|[CMFCTabCtrl::GetTabsHeight](../Topic/CMFCTabCtrl::GetTabsHeight.md)|현재 탭 컨트롤의 탭 영역 높이 검색합니다.|  
|[CMFCTabCtrl::GetTabsRect](../Topic/CMFCTabCtrl::GetTabsRect.md)|현재 탭 컨트롤의 탭 영역을 바인딩하는 사각형을 검색 합니다.  \(재정의 [CMFCBaseTabCtrl::GetTabsRect](../Topic/CMFCBaseTabCtrl::GetTabsRect.md).\)|  
|`CMFCTabCtrl::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCTabCtrl::GetWndArea](../Topic/CMFCTabCtrl::GetWndArea.md)|현재 탭 컨트롤 클라이언트 영역의 경계를 검색합니다.|  
|[CMFCTabCtrl::HideActiveWindowHorzScrollBar](../Topic/CMFCTabCtrl::HideActiveWindowHorzScrollBar.md)|활성 창에 있는 경우 가로 스크롤 막대를 숨깁니다.|  
|[CMFCTabCtrl::HideInactiveWindow](../Topic/CMFCTabCtrl::HideInactiveWindow.md)|프레임 워크는 비활성 탭 컨트롤 창을 표시할 수 있는지 여부를 지정 합니다.|  
|[CMFCTabCtrl::HideNoTabs](../Topic/CMFCTabCtrl::HideNoTabs.md)|표시 탭이 있으면 탭 영역 그리기를 사용할 수 있거나.|  
|[CMFCTabCtrl::HideSingleTab](../Topic/CMFCTabCtrl::HideSingleTab.md)|있을 때 단일 탭된 창 탭 그리기를 사용할 수 있거나.  \(재정의 [CMFCBaseTabCtrl::HideSingleTab](../Topic/CMFCBaseTabCtrl::HideSingleTab.md).\)|  
|[CMFCTabCtrl::IsActiveInMDITabGroup](../Topic/CMFCTabCtrl::IsActiveInMDITabGroup.md)|탭 컨트롤의 현재 탭 활성 탭 다중 문서 인터페이스 탭 그룹에 있는지 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsActiveTabBoldFont](../Topic/CMFCTabCtrl::IsActiveTabBoldFont.md)|활성 탭의 텍스트를 굵게 표시할지 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsActiveTabCloseButton](../Topic/CMFCTabCtrl::IsActiveTabCloseButton.md)|나타냅니다 여부 닫기 단추 \(**X**\)는 현재 탭 또는 탭 영역의 오른쪽 위 모서리에 표시 됩니다.|  
|[CMFCTabCtrl::IsDrawFrame](../Topic/CMFCTabCtrl::IsDrawFrame.md)|탭된 창이 포함 된 창 프레임 사각형을 그릴지 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsFlatFrame](../Topic/CMFCTabCtrl::IsFlatFrame.md)|탭 영역 주위의 프레임 평면 또는 3D 인지 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsFlatTab](../Topic/CMFCTabCtrl::IsFlatTab.md)|현재 탭 컨트롤에서 탭의 모양을 플랫 인지 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsLeftRightRounded](../Topic/CMFCTabCtrl::IsLeftRightRounded.md)|모양 탭에서 현재 탭 컨트롤의 오른쪽 및 왼쪽의 반올림 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsMDITabGroup](../Topic/CMFCTabCtrl::IsMDITabGroup.md)|다중 문서 인터페이스 창의 클라이언트 영역에서 현재 탭 컨트롤이 포함 되어 있는지 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsOneNoteStyle](../Topic/CMFCTabCtrl::IsOneNoteStyle.md)|Microsoft Onenote의 스타일에 현재 탭 컨트롤을 표시할지 여부를 나타냅니다.|  
|`CMFCTabCtrl::IsPtInTabArea`|포인트 탭 영역 내부에 있는지 확인 합니다.  \(재정의 [CMFCBaseTabCtrl::IsPtInTabArea](../Topic/CMFCBaseTabCtrl::IsPtInTabArea.md).\)|  
|[CMFCTabCtrl::IsSharedScroll](../Topic/CMFCTabCtrl::IsSharedScroll.md)|현재 탭 컨트롤의 탭 그룹으로 스크롤할 수 있는 스크롤 막대가 있는지 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsTabDocumentsMenu](../Topic/CMFCTabCtrl::IsTabDocumentsMenu.md)|탭 컨트롤 스크롤 단추 또는 탭된 창 메뉴를 표시 하는 단추를 표시할지 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsVS2005Style](../Topic/CMFCTabCtrl::IsVS2005Style.md)|Visual Studio.net 2005의 스타일에 탭이 표시 되는지 여부를 나타냅니다.|  
|[CMFCTabCtrl::ModifyTabStyle](../Topic/CMFCTabCtrl::ModifyTabStyle.md)|모양 탭을 현재 탭 컨트롤에 지정합니다.|  
|`CMFCTabCtrl::MoveTab`|탭은 다른 탭 위치로 이동합니다.  \(재정의 [CMFCBaseTabCtrl::MoveTab](../Topic/CMFCBaseTabCtrl::MoveTab.md).\)|  
|[CMFCTabCtrl::OnDragEnter](../Topic/CMFCTabCtrl::OnDragEnter.md)|먼저 커서가 탭 컨트롤 창으로 드래그 하면 프레임 워크에서 호출 됩니다.|  
|[CMFCTabCtrl::OnDragOver](../Topic/CMFCTabCtrl::OnDragOver.md)|놓기 대상 창 위로 마우스를 이동할 때 프레임 워크에서 끌기 작업 중 이라고 합니다.  \(재정의 [CMFCBaseTabCtrl::OnDragOver](../Topic/CMFCBaseTabCtrl::OnDragOver.md).\)|  
|[CMFCTabCtrl::OnShowTabDocumentsMenu](../Topic/CMFCTabCtrl::OnShowTabDocumentsMenu.md)|팝업 메뉴의 탭된 창 표시, 사용자 탭을 선택 하 고 선택한 탭을 현재 탭으로 설정 될 때까지 대기 합니다.|  
|`CMFCTabCtrl::PreTranslateMessage`|창 메시지를 디스패치하기 전에 변환의  [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및  [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 기능입니다.  \(재정의 [CMFCBaseTabCtrl::PreTranslateMessage](../Topic/CMFCBaseTabCtrl::PreTranslateMessage.md).\)|  
|`CMFCTabCtrl::RecalcLayout`|탭 컨트롤의 내부 레이아웃을 다시 계산합니다.  \(재정의 [CMFCBaseTabCtrl::RecalcLayout](../Topic/CMFCBaseTabCtrl::RecalcLayout.md).\)|  
|[CMFCTabCtrl::SetActiveInMDITabGroup](../Topic/CMFCTabCtrl::SetActiveInMDITabGroup.md)|탭 컨트롤의 현재 탭 다중 문서 인터페이스 탭 그룹에서 현재 탭으로 설정합니다.|  
|[CMFCTabCtrl::SetActiveTab](../Topic/CMFCTabCtrl::SetActiveTab.md)|탭을 활성화합니다.  \(재정의 [CMFCBaseTabCtrl::SetActiveTab](../Topic/CMFCBaseTabCtrl::SetActiveTab.md).\)|  
|[CMFCTabCtrl::SetActiveTabBoldFont](../Topic/CMFCTabCtrl::SetActiveTabBoldFont.md)|활성 탭에서 굵은 글꼴을 사용할 수 있습니다.|  
|[CMFCTabCtrl::SetDrawFrame](../Topic/CMFCTabCtrl::SetDrawFrame.md)|Drawinga 프레임 사각형에 포함 된 도구 모음을 사용할 수 있거나.|  
|[CMFCTabCtrl::SetFlatFrame](../Topic/CMFCTabCtrl::SetFlatFrame.md)|탭 영역 주위로 평면 또는 3D 프레임을 그릴지 여부를 지정 합니다.|  
|[CMFCTabCtrl::SetImageList](../Topic/CMFCTabCtrl::SetImageList.md)|이미지 목록을 지정합니다.  \(재정의 [CMFCBaseTabCtrl::SetImageList](../Topic/CMFCBaseTabCtrl::SetImageList.md).\)|  
|[CMFCTabCtrl::SetResizeMode](../Topic/CMFCTabCtrl::SetResizeMode.md)|현재 탭 컨트롤 크기를 조정할 수는 지정 하 고 컨트롤을 다시 표시 합니다.|  
|[CMFCTabCtrl::SetTabMaxWidth](../Topic/CMFCTabCtrl::SetTabMaxWidth.md)|탭된 창에 최대 탭 너비를 지정합니다.|  
|[CMFCTabCtrl::StopResize](../Topic/CMFCTabCtrl::StopResize.md)|탭 컨트롤에는 현재 크기 조정 작업을 종료합니다.|  
|`CMFCTabCtrl::SwapTabs`|쌍 탭을 바꿉니다.  \(재정의 [CMFCBaseTabCtrl::SwapTabs](../Topic/CMFCBaseTabCtrl::SwapTabs.md).\)|  
|[CMFCTabCtrl::SynchronizeScrollBar](../Topic/CMFCTabCtrl::SynchronizeScrollBar.md)|기본 탭 표시 탭 컨트롤에 가로 스크롤 막대를 그립니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCTabCtrl::m\_bEnableActivate](../Topic/CMFCTabCtrl::m_bEnableActivate.md)|현재 보기가 새 탭 삽입 되 고 활성화 된 경우 포커스 잃지.|  
  
## 설명  
 `CMFCTabCtrl` 지원 클래스:  
  
-   3D, 플랫, 플랫 공유 가로 스크롤 막대를 포함 하는 컨트롤 스타일을 탭.  
  
-   위쪽 또는 아래쪽 창에 있는 탭입니다.  
  
-   텍스트, 이미지 또는 텍스트 및 이미지 표시 탭을 선택 합니다.  
  
-   탭이 활성화 되어 있는 경우에 색을 변경 하는 탭  
  
-   테두리 크기를 조정할 수 있는 탭에 대 한 변경.  
  
-   분리 가능한 탭된 창입니다.  
  
 `CMFCTabCtrl` 클래스는 대화 상자를 사용할 수 있지만 같은 막대 도킹을 사용 하는 응용 프로그램 제어를 위한 것입니다 [!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)] 및 [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  자세한 내용은 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)를 참조하십시오.  
  
 응용 프로그램에서 탭 컨트롤을 도킹 크기 조정, 추가 하려면 다음이 단계를 수행 하십시오.  
  
1.  [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md)의 인스턴스를 만듭니다.  
  
2.  [CDockablePane::Create](../Topic/CDockablePane::Create.md)를 호출합니다.  
  
3.  사용 [CBaseTabbedPane::AddTab](../Topic/CBaseTabbedPane::AddTab.md) 또는 [CMFCBaseTabCtrl::InsertTab](../Topic/CMFCBaseTabCtrl::InsertTab.md) 새 탭을 추가 합니다.  
  
4.  호출 [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md) 현재 도킹 탭 컨트롤의 주 프레임 창에 도킹 될 수 있도록 합니다.  
  
5.  호출 [CFrameWndEx::DockPane](../Topic/CFrameWndEx::DockPane.md) 탭된 창을 주 프레임에 고정 합니다.  
  
 탭된 창으로 도킹 컨트롤 막대를 만드는 방법의 예제를 참조 하십시오. [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md).  사용 `CMFCTabCtrl` 도킹 되지 않은 컨트롤로 만들는 `CMFCTabCtrl` 개체와 호출 하 고 [CMFCTabCtrl::Create](../Topic/CMFCTabCtrl::Create.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)  
  
## 예제  
 다음 예제에서는 다양 한 메서드를 사용 하는 방법의 `CMFCTabCtrl` 클래스를 구성 하는 `CMFCTabCtrl` 개체입니다.  탭을 추가, 닫기 단추를 활성 탭에 표시, 편집 가능한 탭 레이블을 사용 탭된 창 레이블 팝업 메뉴를 표시 하는 예제를 설명 합니다.  이 이때의 일부인의  [상태 컬렉션 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection#1](../../mfc/reference/codesnippet/CPP/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection#3](../../mfc/reference/codesnippet/CPP/cmfctabctrl-class_2.cpp)]  
  
## 요구 사항  
 **헤더:** afxtabctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)   
 [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md)