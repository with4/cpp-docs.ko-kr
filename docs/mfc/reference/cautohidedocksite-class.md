---
title: "CAutoHideDockSite Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAutoHideDockSite"
  - "AllowShowOnPaneMenu"
  - "CAutoHideDockSite::AllowShowOnPaneMenu"
  - "CAutoHideDockSite.AllowShowOnPaneMenu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AllowShowOnPaneMenu method"
  - "CAutoHideDockSite class"
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
caps.latest.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 33
---
# CAutoHideDockSite Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CAutoHideDockSite` 확장은 [CDockSite Class](../../mfc/reference/cdocksite-class.md) 자동 숨기기 도킹 창을 구현 합니다.  
  
## 구문  
  
```  
class CAutoHideDockSite : public CDockSite  
```  
  
## Members  
  
### Public 생성자  
  
|||  
|-|-|  
|Name|설명|  
|`CAutoHideDockSite::CAutoHideDockSite`|`CAutoHideDockSite` 개체를 생성합니다.|  
|`CAutoHideDockSite::~CAutoHideDockSite`|소멸자.|  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|`CAutoHideDockSite::AllowShowOnPaneMenu`|표시 여부는 `CAutoHideDockSite` \[창\] 메뉴에 표시 됩니다.|  
|[CAutoHideDockSite::CanAcceptPane](../Topic/CAutoHideDockSite::CanAcceptPane.md)|기본 창 개체에서 파생 되었는지 여부를 결정 하는 [CMFCAutoHideBar Class](../../mfc/reference/cmfcautohidebar-class.md).|  
|[CAutoHideDockSite::DockPane](../Topic/CAutoHideDockSite::DockPane.md)|창에이 도킹 `CAuotHideDockSite` 개체입니다.|  
|[CAutoHideDockSite::GetAlignRect](../Topic/CAutoHideDockSite::GetAlignRect.md)|화면 좌표에서 고정 사이트를 검색합니다.|  
|[CAutoHideDockSite::RepositionPanes](../Topic/CAutoHideDockSite::RepositionPanes.md)|창에서 다시는 `CAutoHideDockSite` 글로벌 여백 및 간격 단추.|  
|[CAutoHideDockSite::SetOffsetLeft](../Topic/CAutoHideDockSite::SetOffsetLeft.md)|도킹 도구 모음 왼쪽의 여백을 설정 하는 방법|  
|[CAutoHideDockSite::SetOffsetRight](../Topic/CAutoHideDockSite::SetOffsetRight.md)|도킹 도구 모음 오른쪽의 여백을 설정 하는 방법|  
|[CAutoHideDockSite::UnSetAutoHideMode](../Topic/CAutoHideDockSite::UnSetAutoHideMode.md)|호출 [CMFCAutoHideBar::UnSetAutoHideMode](../Topic/CMFCAutoHideBar::UnSetAutoHideMode.md) 개체에 `CAutoHideDockSite`.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|Name|설명|  
|[CAutoHideDockSite::m\_nExtraSpace](../Topic/CAutoHideDockSite::m_nExtraSpace.md)|도구 모음 및 도킹 도구 모음 가장자리 사이의 공간 크기를 정의합니다.  이 공간은 왼쪽된 가장자리 또는 dock 공간을 맞춤에 따라 위쪽 가장자리부터 측정 됩니다.|  
  
## 설명  
 호출 하면 [CFrameWndEx::EnableAutoHidePanes](../Topic/CFrameWndEx::EnableAutoHidePanes.md), 프레임 워크를 자동으로 생성 한 `CAutoHideDockSite` 개체.  대부분의 경우 설명 하거나이 클래스를 직접 사용할 수 없어야 합니다.  
  
 도킹 도구 모음 도킹 창 왼쪽의 왼쪽 사이의 간격이 되는 [CMFCAutoHideButton Class](../../mfc/reference/cmfcautohidebutton-class.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## 예제  
 검색 하는 다음 예제는 `CAutoHideDockSite` 에서 개체는 `CMFCAutoHideBar` 개체 및 도킹 막대의 왼쪽 및 오른쪽 여백을 설정 하는 방법.  
  
 [!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/CPP/cautohidedocksite-class_1.cpp)]  
  
## 요구 사항  
 **헤더:** afxautohidedocksite.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CDockSite Class](../../mfc/reference/cdocksite-class.md)