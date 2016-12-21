---
title: "CBaseTabbedPane 클래스 | Microsoft Docs"
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
  - "CBaseTabbedPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBaseTabbedPane 클래스"
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
caps.latest.revision: 26
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBaseTabbedPane 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기능을 확장은 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) 탭된 창 작성을 지원 합니다.  
  
## 구문  
  
```  
class CBaseTabbedPane : public CDockablePane  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|`CBaseTabbedPane::CBaseTabbedPane`|기본 생성자입니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CBaseTabbedPane::AddTab](../Topic/CBaseTabbedPane::AddTab.md)|탭된 창에 새 탭을 추가합니다.|  
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../Topic/CBaseTabbedPane::AllowDestroyEmptyTabbedPane.md)|탭된, 빈 창이 소멸 될 수 있는지 여부를 지정 합니다.|  
|[CBaseTabbedPane::ApplyRestoredTabInfo](../Topic/CBaseTabbedPane::ApplyRestoredTabInfo.md)|레지스트리에서 탭된 창에 로드 하는 탭 설정을 적용 합니다.|  
|[CBaseTabbedPane::CanFloat](../Topic/CBaseTabbedPane::CanFloat.md)|창 부동 상태로 있을 수 있는지 여부를 결정 합니다.  \(재정의 [CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md).\)|  
|[CBaseTabbedPane::CanSetCaptionTextToTabName](../Topic/CBaseTabbedPane::CanSetCaptionTextToTabName.md)|탭된 창에 대 한 캡션 같은 텍스트를 활성 탭으로 표시할지 여부를 결정 합니다.|  
|[CBaseTabbedPane::ConvertToTabbedDocument](../Topic/CBaseTabbedPane::ConvertToTabbedDocument.md)|\(재정의 [CDockablePane::ConvertToTabbedDocument](../Topic/CDockablePane::ConvertToTabbedDocument.md).\)|  
|[CBaseTabbedPane::DetachPane](../Topic/CBaseTabbedPane::DetachPane.md)|도킹 가능한 창을 하나 이상 탭 MDI 문서를 변환합니다.|  
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](../Topic/CBaseTabbedPane::EnableSetCaptionTextToTabName.md)|사용 하거나 창의 탭 활성 탭 레이블 텍스트와 캡션 텍스트를 동기화 할 수 없습니다.|  
|[CBaseTabbedPane::FillDefaultTabsOrderArray](../Topic/CBaseTabbedPane::FillDefaultTabsOrderArray.md)|내부 탭 순서를 기본 상태로 복원합니다.|  
|[CBaseTabbedPane::FindBarByTabNumber](../Topic/CBaseTabbedPane::FindBarByTabNumber.md)|탭에 있는 탭부터 탭 인덱스로 식별 되는 경우는 창을 반환 합니다.|  
|||  
|[CBaseTabbedPane::FindPaneByID](../Topic/CBaseTabbedPane::FindPaneByID.md)|창 ID로 식별 되는 창을 반환 합니다.|  
|[CBaseTabbedPane::FloatTab](../Topic/CBaseTabbedPane::FloatTab.md)|분리 탭에서 현재 창 있으면만 창을 입력판이 놓입니다.|  
|[CBaseTabbedPane::GetDefaultTabsOrder](../Topic/CBaseTabbedPane::GetDefaultTabsOrder.md)|창에서 탭의 기본 순서를 반환합니다.|  
|[CBaseTabbedPane::GetFirstVisibleTab](../Topic/CBaseTabbedPane::GetFirstVisibleTab.md)|표시 된 첫 번째 탭에 대 한 포인터를 검색합니다.|  
|[CBaseTabbedPane::GetMinSize](../Topic/CBaseTabbedPane::GetMinSize.md)|창의 크기를 허용 되는 최소값을 검색 합니다.  \(재정의 [CPane::GetMinSize](../Topic/CPane::GetMinSize.md).\)|  
|[CBaseTabbedPane::GetPaneIcon](../Topic/CBaseTabbedPane::GetPaneIcon.md)|창을 아이콘으로 핸들을 반환합니다.  \(재정의 [CBasePane::GetPaneIcon](../Topic/CBasePane::GetPaneIcon.md).\)|  
|[CBaseTabbedPane::GetPaneList](../Topic/CBaseTabbedPane::GetPaneList.md)|목록 창에 포함 된 탭된 창에 반환 합니다.|  
|[CBaseTabbedPane::GetTabArea](../Topic/CBaseTabbedPane::GetTabArea.md)|위쪽 및 아래쪽 탭 영역에 대 한 경계 사각형을 반환합니다.|  
|[CBaseTabbedPane::GetTabsNum](../Topic/CBaseTabbedPane::GetTabsNum.md)|탭 창에 탭 개수를 반환 합니다.|  
|[CBaseTabbedPane::GetUnderlyingWindow](../Topic/CBaseTabbedPane::GetUnderlyingWindow.md)|기본 \(래핑된\) 탭 창을 가져옵니다.|  
|[CBaseTabbedPane::GetVisibleTabsNum](../Topic/CBaseTabbedPane::GetVisibleTabsNum.md)|표시 되는 탭의 개수를 반환 합니다.|  
|[CBaseTabbedPane::HasAutoHideMode](../Topic/CBaseTabbedPane::HasAutoHideMode.md)|탭된 창에 자동 숨기기 모드로 전환할 수 있습니다 여부를 결정 합니다.|  
|[CBaseTabbedPane::IsHideSingleTab](../Topic/CBaseTabbedPane::IsHideSingleTab.md)|하나의 탭에 표시 됩니다 경우에 탭된 창에 숨겨져 있는지 여부를 결정 합니다.|  
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Serialize 하는 동안 내부적으로 사용 합니다.|  
|[CBaseTabbedPane::RecalcLayout](../Topic/CBaseTabbedPane::RecalcLayout.md)|창 레이아웃 정보가 다시 계산 됩니다.  \(재정의 [CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md).\)|  
|[CBaseTabbedPane::RemovePane](../Topic/CBaseTabbedPane::RemovePane.md)|창이 탭된 창에서 제거 됩니다.|  
|`CBaseTabbedPane::SaveSiblingBarIDs`|Serialize 하는 동안 내부적으로 사용 합니다.|  
|`CBaseTabbedPane::Serialize`|\(재정의 [CDockablePane::Serialize](http://msdn.microsoft.com/ko-kr/09787e59-e446-4e76-894b-206d303dcfd6).\)|  
|`CBaseTabbedPane::SerializeTabWindow`|Serialize 하는 동안 내부적으로 사용 합니다.|  
|[CBaseTabbedPane::SetAutoDestroy](../Topic/CBaseTabbedPane::SetAutoDestroy.md)|탭된 컨트롤 막대에 자동으로 소멸 됩니다 여부를 결정 합니다.|  
|[CBaseTabbedPane::SetAutoHideMode](../Topic/CBaseTabbedPane::SetAutoHideMode.md)|자동 숨기기 모드로 하 고 사이 도킹 창을 표시 하거나 숨깁니다.  \(재정의 [CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md).\)|  
|[CBaseTabbedPane::ShowTab](../Topic/CBaseTabbedPane::ShowTab.md)|표시 하거나 탭을 숨깁니다.|  
  
## 설명  
 이 클래스는 추상 클래스 이며 인스턴스화할 수 없습니다.  모든 종류의 탭된 창에 공통으로 적용 되는 서비스를 구현 합니다.  
  
 현재 두 개의 탭된 창 파생된 클래스 라이브러리를 포함: [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md) 및 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 A `CBaseTabbedPane` 개체에 대 한 포인터를 래핑하는 [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md) 개체입니다.  [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md)그러면 탭 창의 자식 창이 됩니다.  
  
 탭된 창을 만드는 방법에 대 한 자세한 내용은 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md), [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md), 및 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
## 요구 사항  
 **헤더:** afxBaseTabbedPane.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)