---
title: "CRecentDockSiteInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRecentDockSiteInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRecentDockSiteInfo class"
ms.assetid: 2dd14f95-d5a2-4461-a7a5-2c6c36a3a165
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CRecentDockSiteInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CRecentDockSiteInfo` 클래스는 [CPane Class](../../mfc/reference/cpane-class.md)에 대한 최신 상태 정보를 저장하는 도우미 클래스입니다.  
  
## 구문  
  
```  
class CRecentDockSiteInfo : public CObject  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|`CRecentDockSiteInfo::CRecentDockSiteInfo`|기본 생성자입니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CRecentDockSiteInfo::CleanUp](../Topic/CRecentDockSiteInfo::CleanUp.md)||  
|[CRecentDockSiteInfo::GetRecentDefaultPaneDivider](../Topic/CRecentDockSiteInfo::GetRecentDefaultPaneDivider.md)||  
|[CRecentDockSiteInfo::GetRecentDockedPercent](../Topic/CRecentDockSiteInfo::GetRecentDockedPercent.md)||  
|[CRecentDockSiteInfo::GetRecentDockedRect](../Topic/CRecentDockSiteInfo::GetRecentDockedRect.md)||  
|[CRecentDockSiteInfo::GetRecentListOfPanes](../Topic/CRecentDockSiteInfo::GetRecentListOfPanes.md)||  
|[CRecentDockSiteInfo::GetRecentPaneContainer](../Topic/CRecentDockSiteInfo::GetRecentPaneContainer.md)||  
|[CRecentDockSiteInfo::GetRecentTabContainer](../Topic/CRecentDockSiteInfo::GetRecentTabContainer.md)||  
|[CRecentDockSiteInfo::Init](../Topic/CRecentDockSiteInfo::Init.md)||  
|[CRecentDockSiteInfo::IsRecentLeftPane](../Topic/CRecentDockSiteInfo::IsRecentLeftPane.md)||  
|[CRecentDockSiteInfo::operator \=](../Topic/CRecentDockSiteInfo::operator%20=.md)||  
|[CRecentDockSiteInfo::SaveListOfRecentPanes](../Topic/CRecentDockSiteInfo::SaveListOfRecentPanes.md)||  
|[CRecentDockSiteInfo::SetInfo](../Topic/CRecentDockSiteInfo::SetInfo.md)||  
|[CRecentDockSiteInfo::StoreDockInfo](../Topic/CRecentDockSiteInfo::StoreDockInfo.md)||  
  
## 설명  
 `CRecentDockSiteInfo` 클래스는 데이터 관리 클래스입니다.  이 클래스는 도킹과 부동 간에 전환될 때 `CPane`의 마지막 상태를 추적합니다.  사용자가 도킹 가능한 부동 창을 두 번 클릭하면 도킹됩니다.  도킹된 창을 두 번 클릭하면 이전 위치, 크기 및 상태로 돌아갑니다.  마찬가지로 창이 다시 도킹되면 이전 도킹 위치로 돌아갑니다.  이 데이터 클래스를 통해 이 작업을 수행할 수 있습니다.  이 클래스의 멤버는 도킹된 창에 대한 상태 정보를 저장하므로 응용 프로그램에서 직접 수정할 수 없습니다.  
  
 `CRecentDockSiteInfo` 개체는 창을 만들 때마다 생성됩니다.  각 `CPane` 개체에는 멤버 변수 [CPane::m\_recentDockInfo](../Topic/CPane::m_recentDockInfo.md)가 있어 이 정보를 저장합니다.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md)  
  
## 요구 사항  
 **헤더:** afxrecentDockSiteInfo.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CDockSite Class](../../mfc/reference/cdocksite-class.md)