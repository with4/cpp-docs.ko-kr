---
title: "CMultiPaneFrameWnd Class | Microsoft Docs"
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
  - "CMultiPaneFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiPaneFrameWnd class"
ms.assetid: 989a548e-0d70-46b7-a513-8cf740e1be3e
caps.latest.revision: 36
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMultiPaneFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMultiPaneFrameWnd` 클래스를 확장 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md).  다중 창 지원 수 있습니다.  컨트롤 막대에서 포함 된 단일 핸들 대신 `CMultiPaneFrameWnd` 포함는 [CPaneContainerManager Class](../../mfc/reference/cpanecontainermanager-class.md) 하나를 고정할 수 있도록 개체 `CMultiPaneFrameWnd` 및 동적으로 다른 여러 부동, 탭 창을 만듭니다.  
  
## 구문  
  
```  
class CMultiPaneFrameWnd : public CPaneFrameWnd  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMultiPaneFrameWnd::AddPane](../Topic/CMultiPaneFrameWnd::AddPane.md)|창에 추가합니다.  \(재정의 [CPaneFrameWnd::AddPane](../Topic/CPaneFrameWnd::AddPane.md).\)|  
|[CMultiPaneFrameWnd::AddRecentPane](../Topic/CMultiPaneFrameWnd::AddRecentPane.md)||  
|[CMultiPaneFrameWnd::AdjustLayout](../Topic/CMultiPaneFrameWnd::AdjustLayout.md)|미니 프레임 창의 레이아웃을 조정합니다.  \(재정의 [CPaneFrameWnd::AdjustLayout](../Topic/CPaneFrameWnd::AdjustLayout.md).\)|  
|[CMultiPaneFrameWnd::AdjustPaneFrames](../Topic/CMultiPaneFrameWnd::AdjustPaneFrames.md)|\(재정의 [CPaneFrameWnd::AdjustPaneFrames](../Topic/CPaneFrameWnd::AdjustPaneFrames.md).\)|  
|[CMultiPaneFrameWnd::CalcExpectedDockedRect](../Topic/CMultiPaneFrameWnd::CalcExpectedDockedRect.md)|도킹 된 창의 예상된 사각형을 계산합니다.  \(재정의 [CPaneFrameWnd::CalcExpectedDockedRect](../Topic/CPaneFrameWnd::CalcExpectedDockedRect.md).\)|  
|[CMultiPaneFrameWnd::CanBeAttached](../Topic/CMultiPaneFrameWnd::CanBeAttached.md)|현재 창 다른 창 또는 프레임 창에 고정할 수 있는지 여부를 결정 합니다.  \(재정의 [CPaneFrameWnd::CanBeAttached](../Topic/CPaneFrameWnd::CanBeAttached.md).\)|  
|[CMultiPaneFrameWnd::CanBeDockedToPane](../Topic/CMultiPaneFrameWnd::CanBeDockedToPane.md)|미니 프레임 창 창에 고정할 수 있는지 여부를 결정 합니다.  \(재정의 [CPaneFrameWnd::CanBeDockedToPane](../Topic/CPaneFrameWnd::CanBeDockedToPane.md).\)|  
|[CMultiPaneFrameWnd::CheckGripperVisibility](../Topic/CMultiPaneFrameWnd::CheckGripperVisibility.md)|\(재정의 [CPaneFrameWnd::CheckGripperVisibility](../Topic/CPaneFrameWnd::CheckGripperVisibility.md).\)|  
|[CMultiPaneFrameWnd::CloseMiniFrame](../Topic/CMultiPaneFrameWnd::CloseMiniFrame.md)|\(재정의 `CPaneFrameWnd::CloseMiniFrame`.\)|  
|[CMultiPaneFrameWnd::ConvertToTabbedDocument](../Topic/CMultiPaneFrameWnd::ConvertToTabbedDocument.md)|창 탭된 문서로 변환합니다.  \(재정의 [CPaneFrameWnd::ConvertToTabbedDocument](../Topic/CPaneFrameWnd::ConvertToTabbedDocument.md).\)|  
|[CMultiPaneFrameWnd::DockFrame](../Topic/CMultiPaneFrameWnd::DockFrame.md)||  
|[CMultiPaneFrameWnd::DockPane](../Topic/CMultiPaneFrameWnd::DockPane.md)|창에 도킹합니다.  \(재정의 [CPaneFrameWnd::DockPane](../Topic/CPaneFrameWnd::DockPane.md).\)|  
|[CMultiPaneFrameWnd::DockRecentPaneToMainFrame](../Topic/CMultiPaneFrameWnd::DockRecentPaneToMainFrame.md)||  
|[CMultiPaneFrameWnd::GetCaptionText](../Topic/CMultiPaneFrameWnd::GetCaptionText.md)|캡션 텍스트를 반환합니다.  \(재정의 [CPaneFrameWnd::GetCaptionText](../Topic/CPaneFrameWnd::GetCaptionText.md).\)|  
|[CMultiPaneFrameWnd::GetPaneContainerManager](../Topic/CMultiPaneFrameWnd::GetPaneContainerManager.md)|내부 컨테이너 관리자 개체에 대 한 참조를 반환합니다.|  
|[CMultiPaneFrameWnd::GetFirstVisiblePane](../Topic/CMultiPaneFrameWnd::GetFirstVisiblePane.md)|미니 프레임 창에 포함 되어 있는 첫 번째 표시 창을 반환 합니다.  \(재정의 [CPaneFrameWnd::GetFirstVisiblePane](../Topic/CPaneFrameWnd::GetFirstVisiblePane.md).\)|  
|[CMultiPaneFrameWnd::GetPane](../Topic/CMultiPaneFrameWnd::GetPane.md)|미니 프레임 창에 포함 된 창을 반환 합니다.  \(재정의 [CPaneFrameWnd::GetPane](../Topic/CPaneFrameWnd::GetPane.md).\)|  
|[CMultiPaneFrameWnd::GetPaneCount](../Topic/CMultiPaneFrameWnd::GetPaneCount.md)|미니 프레임 창에 있는 창의 개수를 반환 합니다.  \(재정의 [CPaneFrameWnd::GetPaneCount](../Topic/CPaneFrameWnd::GetPaneCount.md).\)|  
|[CMultiPaneFrameWnd::GetVisiblePaneCount](../Topic/CMultiPaneFrameWnd::GetVisiblePaneCount.md)|미니 프레임 창에 포함 된 표시 창의 개수를 반환 합니다.  \(재정의 [CPaneFrameWnd::GetVisiblePaneCount](../Topic/CPaneFrameWnd::GetVisiblePaneCount.md).\)|  
|[CMultiPaneFrameWnd::InsertPane](../Topic/CMultiPaneFrameWnd::InsertPane.md)||  
|[CMultiPaneFrameWnd::LoadState](../Topic/CMultiPaneFrameWnd::LoadState.md)|창의 상태를 로드합니다.  \(재정의 [CPaneFrameWnd::LoadState](../Topic/CPaneFrameWnd::LoadState.md).\)|  
|[CMultiPaneFrameWnd::OnDockToRecentPos](../Topic/CMultiPaneFrameWnd::OnDockToRecentPos.md)|가장 최근의 위치가 미니 프레임 창에 도킹합니다.  \(재정의 [CPaneFrameWnd::OnDockToRecentPos](../Topic/CPaneFrameWnd::OnDockToRecentPos.md).\)|  
|[CMultiPaneFrameWnd::OnKillRollUpTimer](../Topic/CMultiPaneFrameWnd::OnKillRollUpTimer.md)|롤업 타이머를 중지합니다.  \(재정의 [CPaneFrameWnd::OnKillRollUpTimer](../Topic/CPaneFrameWnd::OnKillRollUpTimer.md).\)|  
|[CMultiPaneFrameWnd::OnPaneRecalcLayout](../Topic/CMultiPaneFrameWnd::OnPaneRecalcLayout.md)|미니 프레임 창 안에 있는 창 레이아웃을 조정합니다.  \(재정의 [CPaneFrameWnd::OnPaneRecalcLayout](../Topic/CPaneFrameWnd::OnPaneRecalcLayout.md).\)|  
|[CMultiPaneFrameWnd::OnSetRollUpTimer](../Topic/CMultiPaneFrameWnd::OnSetRollUpTimer.md)|롤업 타이머를 설정합니다.  \(재정의 [CPaneFrameWnd::OnSetRollUpTimer](../Topic/CPaneFrameWnd::OnSetRollUpTimer.md).\)|  
|[CMultiPaneFrameWnd::OnShowPane](../Topic/CMultiPaneFrameWnd::OnShowPane.md)|미니 프레임 창에는 창 숨겨지거나 표시 될 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CPaneFrameWnd::OnShowPane](../Topic/CPaneFrameWnd::OnShowPane.md).\)|  
|[CMultiPaneFrameWnd::PaneFromPoint](../Topic/CMultiPaneFrameWnd::PaneFromPoint.md)|사용자가 제공한 점 미니 프레임 창 안에 포함 되어 있는 경우는 창을 반환 합니다.  \(재정의 [CPaneFrameWnd::PaneFromPoint](../Topic/CPaneFrameWnd::PaneFromPoint.md).\)|  
|[CMultiPaneFrameWnd::RemoveNonValidPanes](../Topic/CMultiPaneFrameWnd::RemoveNonValidPanes.md)|유효 하지 않은 틀을 제거 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CPaneFrameWnd::RemoveNonValidPanes](../Topic/CPaneFrameWnd::RemoveNonValidPanes.md).\)|  
|[CMultiPaneFrameWnd::RemovePane](../Topic/CMultiPaneFrameWnd::RemovePane.md)|한 창 미니 프레임 창에서 제거 됩니다.  \(재정의 [CPaneFrameWnd::RemovePane](../Topic/CPaneFrameWnd::RemovePane.md).\)|  
|[CMultiPaneFrameWnd::ReplacePane](../Topic/CMultiPaneFrameWnd::ReplacePane.md)|한 창 다른 대체합니다.  \(재정의 [CPaneFrameWnd::ReplacePane](../Topic/CPaneFrameWnd::ReplacePane.md).\)|  
|[CMultiPaneFrameWnd::SaveState](../Topic/CMultiPaneFrameWnd::SaveState.md)|창의 상태를 레지스트리에 저장합니다.  \(재정의 [CPaneFrameWnd::SaveState](../Topic/CPaneFrameWnd::SaveState.md).\)|  
|[CMultiPaneFrameWnd::Serialize](../Topic/CMultiPaneFrameWnd::Serialize.md)|\(재정의 `CPaneFrameWnd::Serialize`.\)|  
|[CMultiPaneFrameWnd::SetDockState](../Topic/CMultiPaneFrameWnd::SetDockState.md)|도킹 상태를 설정합니다.  \(재정의 [CPaneFrameWnd::SetDockState](../Topic/CPaneFrameWnd::SetDockState.md).\)|  
|[CMultiPaneFrameWnd::SetLastFocusedPane](../Topic/CMultiPaneFrameWnd::SetLastFocusedPane.md)||  
|[CMultiPaneFrameWnd::SetPreDockState](../Topic/CMultiPaneFrameWnd::SetPreDockState.md)|Predocking 상태를 설정합니다.  \(재정의 [CPaneFrameWnd::SetPreDockState](../Topic/CPaneFrameWnd::SetPreDockState.md).\)|  
|[CMultiPaneFrameWnd::StoreRecentDockSiteInfo](../Topic/CMultiPaneFrameWnd::StoreRecentDockSiteInfo.md)|\(재정의 [CPaneFrameWnd::StoreRecentDockSiteInfo](../Topic/CPaneFrameWnd::StoreRecentDockSiteInfo.md).\)|  
|[CMultiPaneFrameWnd::StoreRecentTabRelatedInfo](../Topic/CMultiPaneFrameWnd::StoreRecentTabRelatedInfo.md)|\(재정의 [CPaneFrameWnd::StoreRecentTabRelatedInfo](../Topic/CPaneFrameWnd::StoreRecentTabRelatedInfo.md).\)|  
  
## 설명  
 대부분이이 클래스의 메서드 재정의 메서드에서 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md) 클래스입니다.  
  
 창을 사용 하는 경우는 `AFX_CBRS_AUTO_ROLLUP` 스타일과 사용자가 도킹 창 다중 창 프레임 창으로, 사용자가 창을 도킹 된 창 스타일 설정에 관계 없이 롤백할 수 있습니다.  
  
 프레임 워크를 자동으로 만듭니다를 `CMultiPaneFrameWnd` 사용 하는 창 사용자 부동 개체는 `CBRS_FLOAT_MULTI` 스타일.  
  
 클래스에서 파생 하는 방법에 대 한 정보는 `CPaneFrameWnd` 클래스와 동적으로 만들기를 참조 하십시오.  [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).  
  
## 예제  
 다음에 대 한 포인터를 검색 하는 예제는 `CMultiPaneFrameWnd` 개체.  이 코드 조각에 속해 있는  [창 크기 설정 예제](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize#4](../../mfc/reference/codesnippet/CPP/cmultipaneframewnd-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)  
  
 [CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md)  
  
## 요구 사항  
 **헤더:** afxMultiPaneFrameWnd.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md)