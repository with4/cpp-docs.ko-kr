---
title: 인터페이스 요소 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- architecture [MFC], MFC Feature Pack
- MFC Feature Pack, architecture
ms.assetid: eead6827-9602-40a3-8038-8986e8207385
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25f9de4ab5f7d12d240625e0fdf5f857563e8ce2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="interface-elements"></a>인터페이스 요소
이 문서에서 도입 된 인터페이스 요소에 설명 [!INCLUDE[vs_orcas_long](../atl/reference/includes/vs_orcas_long_md.md)] s p 1에서는 라이브러리의 이전 버전으로 차이 설명 합니다.  
  
 다음 그림에서는 새로운 인터페이스 요소를 사용 하 여 작성 하는 응용 프로그램을 보여 줍니다.  
  
 ![MFC 기능 팩 예제 응용 프로그램](../mfc/media/mfc_featurepack.png "mfc_featurepack")  
  
## <a name="window-docking"></a>창 도킹  
 창 도킹 기능 하는 도킹 창 유사한는 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 그래픽 사용자 인터페이스를 사용 합니다.  
  
## <a name="control-bars-are-now-panes"></a>컨트롤 막대는 이제 창  
 컨트롤 막대 창으로 현재 알려진 및에서 [CBasePane 클래스](../mfc/reference/cbasepane-class.md)합니다. 컨트롤 막대의 기본 클래스를 이전 버전의 MFC에서 `CControlBar`합니다.  
  
 응용 프로그램 주 프레임 창 일반적으로 표시 되는 [CFrameWndEx 클래스](../mfc/reference/cframewndex-class.md) 또는 [CMDIFrameWndEx 클래스](../mfc/reference/cmdiframewndex-class.md)합니다. 주 프레임 라고는 *도킹 사이트*합니다. 창 부모의 세 가지 유형 중 하나일 수 있습니다: 도킹 사이트, 도킹 가로 막대형 또는 미니 프레임 창.  
  
 창에 두 가지: 크기 조정이 불가능 하 고 크기를 조정할 수 있습니다. 상태 표시줄 및 도구 모음 같은 크기 조정 가능한 창 분할 창 또는 슬라이더를 사용 하 여 조정할 수 있습니다. 크기 조정 가능한 창 (하나의 창 간에 분할을 만드는 다른 창으로 도킹 될 수 있습니다) 컨테이너를 구성할 수 있습니다. 그러나 창 크기를 조정할 수 (고정) 막대를 도킹 하려면 연결할 수 없습니다.  
  
 파생 될 응용 프로그램 사용 크기 조정이 불가능 창, [CPane 클래스](../mfc/reference/cpane-class.md)합니다.  창 크기를 조정할 수을 사용 하 여 응용 프로그램에서 파생 [CDockablePane 클래스](../mfc/reference/cdockablepane-class.md)  
  
## <a name="dock-site"></a>도킹 사이트  
 도킹 사이트 (또는 주 프레임 창)에 모든 창 및 응용 프로그램에서 미니 프레임 창을 소유합니다. 도킹 사이트에는 [CDockingManager](../mfc/reference/cdockingmanager-class.md) 멤버입니다. 이 멤버는 도킹 사이트에 속하는 모든 창 목록을 유지 관리 합니다. 도크 사이트의 외부 가장자리에서 생성 하는 창이 목록의 시작 부분에 배치 됩니다 되도록 목록 정렬 되어 있습니다. 프레임 워크는 도킹 사이트를 다시 그립니다,이 목록을 반복 하 고 도킹 사이트의 현재 경계 사각형을 포함 하도록 각 창 레이아웃을 조정 합니다. 호출할 수 있습니다 `AdjustDockingLayout` 또는 `RecalcLayout` 도킹 레이아웃을 조정 해야 할 시점과 프레임 워크 도킹 관리자에 게이 호출을 리디렉션합니다.  
  
## <a name="dock-bars"></a>도킹 막대  
 각 주 프레임 창 위치를 지정할 수 *막대 도킹* 테두리를 따라 합니다. 도킹 막대는 속해 있는 창은 [CDockSite 클래스](../mfc/reference/cdocksite-class.md)합니다. 도킹 막대에서 파생 된 개체를 허용할 수 [CPane](../mfc/reference/cpane-class.md), 예: 도구 모음입니다. 도킹 막대를 만들려면 주 프레임 창이 초기화 될 때 호출 `EnableDocking`합니다. 자동 숨기기 막대를 사용 하도록 설정 하려면 호출 `EnableAutoHideBars`합니다. `EnableAutoHideBars` 만듭니다 [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md) 개체, 및 각 도킹 표시줄 옆에 있는 워크시트입니다.  
  
 각 도킹 막대 도킹 행으로 구분 됩니다. 도킹 행으로 표시 됩니다는 [CDockingPanesRow 클래스](../mfc/reference/cdockingpanesrow-class.md)합니다. 각 도킹 행에는 도구 모음 목록이 포함 되어 있습니다. 사용자는 도구 모음을 도킹 하거나 도구 모음을 한 행에서 동일한 도킹 가로 막대 내의 다른 위치로 이동, 프레임 워크 중 하나 새 행을 만들고 적절 하 게 도킹 막대의 크기를 조정 하거나 기존 행에 도구 모음을 배치 합니다.  
  
## <a name="mini-frame-windows"></a>미니 프레임 창  
 부동 창 미니 프레임 창에 상주합니다. 미니 프레임 창을 두 클래스로 표현 됩니다: [CMDITabInfo 클래스](../mfc/reference/cmditabinfo-class.md) (창 하나만 포함할 수 있음) 및 [CMultiPaneFrameWnd 클래스](../mfc/reference/cmultipaneframewnd-class.md) (여러 개의 창이 포함할 수 있음). 호출 코드에서 창을 고정 해제, [CBasePane::FloatPane](../mfc/reference/cbasepane-class.md#floatpane)합니다. 창을 부동 후 프레임 워크 자동으로 미니 프레임 창을 만들고 그 미니 프레임 창이 부동 창 부모 됩니다. 부동 창 도킹 프레임 워크, 부모를 다시 설정 되 고 부동 창 (도구 모음)에 대 한 dock 막대나 도킹 사이트 (창에 대 한 크기 조정 가능한) 됩니다.  
  
## <a name="pane-dividers"></a>창 구분선  
 창 구분선 (슬라이더나 분할자 라고도 함)으로 표시 됩니다는 [CPaneDivider 클래스](../mfc/reference/cpanedivider-class.md)합니다. 창을 도킹 하는 사용자, 프레임 워크의 창 도킹 사이트 또는 다른 창에서 도킹 여부에 관계 없이 창 구분선을 만듭니다. 창을 도킹 사이트에 도킹, 창 구분선 호출 됩니다는 *창 구분선 기본*합니다. 기본 창 구분선은 도킹 사이트에 대 한 모든 도킹 창 레이아웃 담당 합니다. 도킹 관리자 기본 창 구분선 목록과 창 목록을 유지 관리합니다. 도킹 관리자는 모든 도킹 창 레이아웃을 담당 합니다.  
  
## <a name="containers"></a>컨테이너  
 모든 크기 조정 가능한 창, 도킹 한 경우 컨테이너에 유지 됩니다. 컨테이너도 표시 됩니다는 [CPaneContainer 클래스](../mfc/reference/cpanecontainer-class.md)합니다. 각 컨테이너는 해당 왼쪽된 창, 오른쪽 창, 하위 컨테이너가 왼쪽된, 오른쪽 하위 컨테이너가 및 분할자에 대 한 포인터 왼쪽 및 오른쪽 부분 사이 있습니다. (*왼쪽* 및 *오른쪽* 물리적 면을 참조 하지 않는 하지만 대신 분기 트리 구조를 식별 합니다.) 이런이 방식에서는 창 및 분할 창을 트리를 만들 고 따라서 함께 조정할 수 있는 창 복잡 한 레이아웃을 얻을 수 있습니다. `CPaneContainer` 클래스는 컨테이너의 트리를 유지 관리 합니다; 창 및 이러한 노드 트리에 상주 하는 슬라이더의 두 목록을 유지 관리 합니다. 창 컨테이너 관리자는 일반적으로 기본 슬라이더 및 여러 개의 창이 수행 하는 미니 프레임 창에 포함 됩니다.  
  
## <a name="auto-hide-control-bars"></a>자동 숨기기 컨트롤 막대  
 기본적으로 각 `CDockablePane` 자동 숨기기 기능을 지원 합니다. 캡션에서 핀 단추를 클릭할 때는 `CDockablePane`, 프레임 워크의 창 자동 숨기기 모드로 전환 합니다. 프레임 워크 클릭을 처리 하려면 만듭니다는 [CMFCAutoHideBar 클래스](../mfc/reference/cmfcautohidebar-class.md) 및 [CMFCAutoHideButton 클래스](../mfc/reference/cmfcautohidebutton-class.md) 와 관련 된는 `CMFCAutoHideBar` 개체입니다. 프레임 워크에서는 새 `CMFCAutoHideBar` 에 [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md)합니다. 프레임 워크 또한 연결 된 `CMFCAutoHideButton` 도구 모음에 있습니다. [CDockingManager 클래스](../mfc/reference/cdockingmanager-class.md) 유지 관리는 `CDockablePane`합니다.  
  
## <a name="tabbed-control-bars-and-outlook-bars"></a>탭된 컨트롤 막대 및 Outlook 표시줄  
 [CMFCBaseTabCtrl 클래스](../mfc/reference/cmfcbasetabctrl-class.md) 분리 가능한 탭이 포함 된 탭 창의 기본 기능을 구현 합니다. 사용 하는 `CMFCBaseTabCtrl` 개체, 초기화는 [CBaseTabbedPane 클래스](../mfc/reference/cbasetabbedpane-class.md) 응용 프로그램에서 합니다. `CBaseTabbedPane` 파생 된 `CDockablePane` 포인터를 관리 하 고는 `CMFCBaseTabCtrl` 개체입니다. `CBaseTabbedPane` 도킹 하 고 탭된 컨트롤 막대의 크기를 조정할 수 있습니다. 사용 하 여 [CDockablePane::AttachToTabWnd](../mfc/reference/cdockablepane-class.md#attachtotabwnd) 도킹 되 고 탭 컨트롤 막대를 동적으로 만들려고 합니다.  
  
 Outlook 표시줄 컨트롤은 또한 탭된 막대 기반으로 합니다. [CMFCOutlookBar 클래스](../mfc/reference/cmfcoutlookbar-class.md) 에서 파생 된 `CBaseTabbedPane`합니다. Outlook 표시줄을 사용 하는 방법에 대 한 자세한 내용은 참조 [CMFCOutlookBar 클래스](../mfc/reference/cmfcoutlookbar-class.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념](../mfc/mfc-concepts.md)

