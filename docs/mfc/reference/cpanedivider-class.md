---
title: "CPaneDivider Class | Microsoft Docs"
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
  - "CPaneDivider"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneDivider class"
ms.assetid: 8e828a5d-232f-4127-b8e3-7fa45a7a476e
caps.latest.revision: 25
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPaneDivider Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 `CPaneDivider` 클래스 두 창을 나누는 분할 창에서 두 그룹 또는 그룹 창에서 주 프레임 창의 클라이언트 영역을 구분 합니다.  
  
## 구문  
  
```  
class CPaneDivider : public CBasePane  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CPaneDivider::CPaneDivider](../Topic/CPaneDivider::CPaneDivider.md)||  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPaneDivider::AddPaneContainer](../Topic/CPaneDivider::AddPaneContainer.md)||  
|[CPaneDivider::AddPane](../Topic/CPaneDivider::AddPane.md)||  
|[CPaneDivider::AddRecentPane](../Topic/CPaneDivider::AddRecentPane.md)||  
|[CPaneDivider::CalcExpectedDockedRect](../Topic/CPaneDivider::CalcExpectedDockedRect.md)||  
|[CPaneDivider::CalcFixedLayout](../Topic/CPaneDivider::CalcFixedLayout.md)|\(재정의 [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CPaneDivider::CheckVisibility](../Topic/CPaneDivider::CheckVisibility.md)||  
|[CPaneDivider::CreateEx](../Topic/CPaneDivider::CreateEx.md)|\(재정의 [CBasePane::CreateEx](../Topic/CBasePane::CreateEx.md).\)|  
|[CPaneDivider::DoesAllowDynInsertBefore](../Topic/CPaneDivider::DoesAllowDynInsertBefore.md)|\(재정의 [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md).\)|  
|[CPaneDivider::DoesContainFloatingPane](../Topic/CPaneDivider::DoesContainFloatingPane.md)||  
|[CPaneDivider::FindPaneContainer](../Topic/CPaneDivider::FindPaneContainer.md)||  
|[CPaneDivider::FindTabbedPane](../Topic/CPaneDivider::FindTabbedPane.md)||  
|[CPaneDivider::GetDefaultWidth](../Topic/CPaneDivider::GetDefaultWidth.md)||  
|[CPaneDivider::GetFirstPane](../Topic/CPaneDivider::GetFirstPane.md)||  
|[CPaneDivider::GetPaneDividerStyle](../Topic/CPaneDivider::GetPaneDividerStyle.md)||  
|[CPaneDivider::GetRootContainerRect](../Topic/CPaneDivider::GetRootContainerRect.md)||  
|[CPaneDivider::GetWidth](../Topic/CPaneDivider::GetWidth.md)||  
|[CPaneDivider::Init](../Topic/CPaneDivider::Init.md)||  
|[CPaneDivider::InsertPane](../Topic/CPaneDivider::InsertPane.md)||  
|[CPaneDivider::IsAutoHideMode](../Topic/CPaneDivider::IsAutoHideMode.md)|\(재정의 [CBasePane::IsAutoHideMode](../Topic/CBasePane::IsAutoHideMode.md).\)|  
|[CPaneDivider::IsDefault](../Topic/CPaneDivider::IsDefault.md)||  
|[CPaneDivider::IsHorizontal](../Topic/CPaneDivider::IsHorizontal.md)|\(재정의 [CBasePane::IsHorizontal](../Topic/CBasePane::IsHorizontal.md).\)|  
|[CPaneDivider::Move](../Topic/CPaneDivider::Move.md)||  
|[CPaneDivider::NotifyAboutRelease](../Topic/CPaneDivider::NotifyAboutRelease.md)||  
|[CPaneDivider::OnShowPane](../Topic/CPaneDivider::OnShowPane.md)||  
|[CPaneDivider::ReleaseEmptyPaneContainers](../Topic/CPaneDivider::ReleaseEmptyPaneContainers.md)||  
|[CPaneDivider::RemovePane](../Topic/CPaneDivider::RemovePane.md)||  
|[CPaneDivider::ReplacePane](../Topic/CPaneDivider::ReplacePane.md)||  
|[CPaneDivider::RepositionPanes](../Topic/CPaneDivider::RepositionPanes.md)||  
|[CPaneDivider::Serialize](../Topic/CPaneDivider::Serialize.md)|\(재정의 `CBasePane::Serialize`.\)|  
|[CPaneDivider::SetAutoHideMode](../Topic/CPaneDivider::SetAutoHideMode.md)||  
|[CPaneDivider::SetPaneContainerManager](../Topic/CPaneDivider::SetPaneContainerManager.md)||  
|[CPaneDivider::ShowWindow](../Topic/CPaneDivider::ShowWindow.md)||  
|[CPaneDivider::StoreRecentDockSiteInfo](../Topic/CPaneDivider::StoreRecentDockSiteInfo.md)||  
|[CPaneDivider::StoreRecentTabRelatedInfo](../Topic/CPaneDivider::StoreRecentTabRelatedInfo.md)||  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPaneDivider::GetPanes](../Topic/CPaneDivider::GetPanes.md)|창에 있는 목록을 반환 된 [CPaneContainer Class](../../mfc/reference/cpanecontainer-class.md).  기본 창 구분선에만이 메서드를 호출 해야 합니다.|  
|[CPaneDivider::GetPaneDividers](../Topic/CPaneDivider::GetPaneDividers.md)|목록에 있는 창 분할자의 반환 된 [CPaneContainer Class](../../mfc/reference/cpanecontainer-class.md).  기본 창 구분선에만이 메서드를 호출 해야 합니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CPaneDivider::m\_nDefaultWidth](../Topic/CPaneDivider::m_nDefaultWidth.md)|응용 프로그램의 모든 창 분할자의 픽셀에서 기본 너비를 지정합니다.|  
|[CPaneDivider::m\_pSliderRTC](../Topic/CPaneDivider::m_pSliderRTC.md)|에 대 한 런타임 클래스 정보를 저장 하는 포인터는 `CPaneDivider`\-개체를 파생 합니다.|  
  
## 설명  
 프레임 워크는 `CPaneDivider` 는 창에 도킹 되어 있을 때 개체를 자동으로.  
  
 분할자 창에는  
  
-   그룹 틀의 주 프레임 창의 측면에 도킹 되어 있을 때 기본 틀이 만들어집니다.  기본 틀에 대 한 포인터를 보유는 [CPaneContainerManager Class](../../mfc/reference/cpanecontainermanager-class.md) 및 그룹 창에서 대부분의 작업을 리디렉션합니다 \(의 창 크기 조정 또는 다른 도킹 창 또는 컨테이너\) 컨테이너 관리자.  각 도킹 창 틀의 기본에 대 한 포인터를 유지합니다.  
  
-   일반 창 분할선을 방금 컨테이너에 있는 두 개의 창 나눕니다.  자세한 내용은 [CPaneContainer Class](../../mfc/reference/cpanecontainer-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 가져오기는 `CPaneDivider` 개체에서 `CWorkspaceBar` 개체.  이 코드 조각에 속해 있는  [MDI 탭 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#5](../../mfc/reference/codesnippet/CPP/cpanedivider-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPaneDivider](../../mfc/reference/cpanedivider-class.md)  
  
## 요구 사항  
 **헤더:** afxPaneDivider.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPaneContainerManager Class](../../mfc/reference/cpanecontainermanager-class.md)   
 [CPaneContainer Class](../../mfc/reference/cpanecontainer-class.md)   
 [CDockingManager Class](../../mfc/reference/cdockingmanager-class.md)   
 [CBasePane Class](../../mfc/reference/cbasepane-class.md)