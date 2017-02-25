---
title: "CPaneContainerManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPaneContainerManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneContainerManager class"
ms.assetid: 3d974c15-a62f-4648-bb5b-cc31ab7950af
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CPaneContainerManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CPaneContainerManager` 클래스는 관리 저장 및 현재 도킹 레이아웃을 표시 합니다.  
  
## 구문  
  
```  
class CPaneContainerManager : public CObject  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPaneContainerManager::AddPane](../Topic/CPaneContainerManager::AddPane.md)||  
|[CPaneContainerManager::AddPaneContainerManager](../Topic/CPaneContainerManager::AddPaneContainerManager.md)||  
|[CPaneContainerManager::AddPaneContainerManagerToDockablePane](../Topic/CPaneContainerManager::AddPaneContainerManagerToDockablePane.md)||  
|[CPaneContainerManager::AddPanesToList](../Topic/CPaneContainerManager::AddPanesToList.md)||  
|[CPaneContainerManager::AddPaneToList](../Topic/CPaneContainerManager::AddPaneToList.md)||  
|[CPaneContainerManager::AddPaneToRecentPaneContainer](../Topic/CPaneContainerManager::AddPaneToRecentPaneContainer.md)||  
|[CPaneContainerManager::CalcRects](../Topic/CPaneContainerManager::CalcRects.md)||  
|[CPaneContainerManager::CanBeAttached](../Topic/CPaneContainerManager::CanBeAttached.md)||  
|[CPaneContainerManager::CheckAndRemoveNonValidPane](../Topic/CPaneContainerManager::CheckAndRemoveNonValidPane.md)||  
|[CPaneContainerManager::CheckForMiniFrameAndCaption](../Topic/CPaneContainerManager::CheckForMiniFrameAndCaption.md)||  
|[CPaneContainerManager::Create](../Topic/CPaneContainerManager::Create.md)||  
|[CPaneContainerManager::DoesAllowDynInsertBefore](../Topic/CPaneContainerManager::DoesAllowDynInsertBefore.md)||  
|[CPaneContainerManager::DoesContainFloatingPane](../Topic/CPaneContainerManager::DoesContainFloatingPane.md)||  
|[CPaneContainerManager::EnableGrippers](../Topic/CPaneContainerManager::EnableGrippers.md)||  
|[CPaneContainerManager::FindPaneContainer](../Topic/CPaneContainerManager::FindPaneContainer.md)||  
|[CPaneContainerManager::FindTabbedPane](../Topic/CPaneContainerManager::FindTabbedPane.md)||  
|[CPaneContainerManager::GetAvailableSpace](../Topic/CPaneContainerManager::GetAvailableSpace.md)||  
|[CPaneContainerManager::GetDefaultPaneDivider](../Topic/CPaneContainerManager::GetDefaultPaneDivider.md)||  
|[CPaneContainerManager::GetDockSiteFrameWnd](../Topic/CPaneContainerManager::GetDockSiteFrameWnd.md)||  
|[CPaneContainerManager::GetFirstPane](../Topic/CPaneContainerManager::GetFirstPane.md)||  
|[CPaneContainerManager::GetFirstVisiblePane](../Topic/CPaneContainerManager::GetFirstVisiblePane.md)||  
|[CPaneContainerManager::GetMinMaxOffset](../Topic/CPaneContainerManager::GetMinMaxOffset.md)||  
|[CPaneContainerManager::GetMinSize](../Topic/CPaneContainerManager::GetMinSize.md)||  
|[CPaneContainerManager::GetNodeCount](../Topic/CPaneContainerManager::GetNodeCount.md)||  
|[CPaneContainerManager::GetPaneContainerRTC](../Topic/CPaneContainerManager::GetPaneContainerRTC.md)||  
|[CPaneContainerManager::GetPaneCount](../Topic/CPaneContainerManager::GetPaneCount.md)||  
|[CPaneContainerManager::GetTotalRefCount](../Topic/CPaneContainerManager::GetTotalRefCount.md)||  
|[CPaneContainerManager::GetVisiblePaneCount](../Topic/CPaneContainerManager::GetVisiblePaneCount.md)||  
|[CPaneContainerManager::GetWindowRect](../Topic/CPaneContainerManager::GetWindowRect.md)||  
|[CPaneContainerManager::HideAll](../Topic/CPaneContainerManager::HideAll.md)||  
|[CPaneContainerManager::InsertPane](../Topic/CPaneContainerManager::InsertPane.md)||  
|[CPaneContainerManager::IsAutoHideMode](../Topic/CPaneContainerManager::IsAutoHideMode.md)||  
|[CPaneContainerManager::IsEmpty](../Topic/CPaneContainerManager::IsEmpty.md)||  
|[CPaneContainerManager::IsRootPaneContainerVisible](../Topic/CPaneContainerManager::IsRootPaneContainerVisible.md)||  
|[CPaneContainerManager::NotifyPaneDivider](../Topic/CPaneContainerManager::NotifyPaneDivider.md)||  
|[CPaneContainerManager::OnPaneDividerMove](../Topic/CPaneContainerManager::OnPaneDividerMove.md)||  
|[CPaneContainerManager::OnShowPane](../Topic/CPaneContainerManager::OnShowPane.md)||  
|[CPaneContainerManager::PaneFromPoint](../Topic/CPaneContainerManager::PaneFromPoint.md)||  
|[CPaneContainerManager::ReleaseEmptyPaneContainers](../Topic/CPaneContainerManager::ReleaseEmptyPaneContainers.md)||  
|[CPaneContainerManager::RemoveAllPanesAndPaneDividers](../Topic/CPaneContainerManager::RemoveAllPanesAndPaneDividers.md)||  
|[CPaneContainerManager::RemoveNonValidPanes](../Topic/CPaneContainerManager::RemoveNonValidPanes.md)||  
|[CPaneContainerManager::RemovePaneDivider](../Topic/CPaneContainerManager::RemovePaneDivider.md)||  
|[CPaneContainerManager::RemovePaneFromPaneContainer](../Topic/CPaneContainerManager::RemovePaneFromPaneContainer.md)||  
|[CPaneContainerManager::ReplacePane](../Topic/CPaneContainerManager::ReplacePane.md)||  
|[CPaneContainerManager::ResizePaneContainers](../Topic/CPaneContainerManager::ResizePaneContainers.md)||  
|[CPaneContainerManager::Serialize](../Topic/CPaneContainerManager::Serialize.md)|읽거나 또는 보관 파일에이 개체를 씁니다.  \(재정의 [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CPaneContainerManager::SetDefaultPaneDividerForPanes](../Topic/CPaneContainerManager::SetDefaultPaneDividerForPanes.md)||  
|[CPaneContainerManager::SetPaneContainerRTC](../Topic/CPaneContainerManager::SetPaneContainerRTC.md)||  
|[CPaneContainerManager::SetResizeMode](../Topic/CPaneContainerManager::SetResizeMode.md)||  
|[CPaneContainerManager::StoreRecentDockSiteInfo](../Topic/CPaneContainerManager::StoreRecentDockSiteInfo.md)||  
  
### 설명  
 프레임 워크의 인스턴스를 자동으로 만듭니다 `CPaneContainerManager` 개체와 중 하나에 포함에 [CPaneDivider Class](../../mfc/reference/cpanedivider-class.md) 개체에 [CMultiPaneFrameWnd Class](../../mfc/reference/cmultipaneframewnd-class.md) 개체.  
  
 `CPaneContainerManager` 클래스에서 빌드된 이진 트리의 루트에 대 한 포인터를 저장 합니다.  [CPaneContainer](../../mfc/reference/cpanecontainer-class.md) 개체입니다.  
  
## 예제  
 다음 예제에서는 참조 하는 `CPaneContainerManager` 개체입니다.  이 코드 조각에 속해 있는  [창 크기 설정 예제](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize#5](../../mfc/reference/codesnippet/CPP/cpanecontainermanager-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CPaneContainerManager](../../mfc/reference/cpanecontainermanager-class.md)  
  
## 요구 사항  
 **헤더:** afxpanecontainermanager.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [CPaneContainer Class](../../mfc/reference/cpanecontainer-class.md)   
 [CPaneDivider Class](../../mfc/reference/cpanedivider-class.md)