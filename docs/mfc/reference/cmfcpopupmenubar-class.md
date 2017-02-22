---
title: "CMFCPopupMenuBar 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPopupMenuBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPopupMenuBar 클래스"
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
caps.latest.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 34
---
# CMFCPopupMenuBar 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

팝업 메뉴에 메뉴 모음을 포함 합니다.  
  
## 구문  
  
```  
class CMFCPopupMenuBar : public CMFCToolBar  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCPopupMenuBar::AdjustSizeImmediate](../Topic/CMFCPopupMenuBar::AdjustSizeImmediate.md)|바로 창 레이아웃을 다시 계산합니다.  \(재정의 [CPane::AdjustSizeImmediate](../Topic/CPane::AdjustSizeImmediate.md).\)|  
|[CMFCPopupMenuBar::BuildOrigItems](../Topic/CMFCPopupMenuBar::BuildOrigItems.md)|팝업 메뉴 항목에 지정 된 메뉴 리소스를 로드합니다.|  
|[CMFCPopupMenuBar::CloseDelayedSubMenu](../Topic/CMFCPopupMenuBar::CloseDelayedSubMenu.md)|지연 된 팝업 메뉴 단추를 닫습니다.|  
|[CMFCPopupMenuBar::ExportToMenu](../Topic/CMFCPopupMenuBar::ExportToMenu.md)|메뉴에 있는 팝업 메뉴 단추에서를 만듭니다.|  
|[CMFCPopupMenuBar::FindDestintationToolBar](../Topic/CMFCPopupMenuBar::FindDestintationToolBar.md)|도구 모음을 위치 지정 된 점이 찾습니다.|  
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](../Topic/CMFCPopupMenuBar::GetCurrentMenuImageSize.md)|메뉴 단추 이미지의 크기를 나타냅니다.|  
|[CMFCPopupMenuBar::GetDefaultMenuId](../Topic/CMFCPopupMenuBar::GetDefaultMenuId.md)|기본 메뉴 항목의 식별자를 반환합니다.|  
|[CMFCPopupMenuBar::GetLastCommandIndex](../Topic/CMFCPopupMenuBar::GetLastCommandIndex.md)|가장 최근에 호출 메뉴 명령의 인덱스를 가져옵니다.|  
|[CMFCPopupMenuBar::GetOffset](../Topic/CMFCPopupMenuBar::GetOffset.md)|팝업 메뉴 모음의 행 오프셋을 가져옵니다.|  
|[CMFCPopupMenuBar::ImportFromMenu](../Topic/CMFCPopupMenuBar::ImportFromMenu.md)|지정 된 메뉴에서 팝업 메뉴 단추를 가져옵니다.|  
|[CMFCPopupMenuBar::IsDropDownListMode](../Topic/CMFCPopupMenuBar::IsDropDownListMode.md)|팝업 메뉴 모음의 드롭 다운 목록 모드 인지 여부를 나타냅니다.|  
|[CMFCPopupMenuBar::IsPaletteMode](../Topic/CMFCPopupMenuBar::IsPaletteMode.md)|팝업 메뉴 모음의 팔레트 모드 인지 여부를 나타냅니다.|  
|[CMFCPopupMenuBar::IsRibbonPanel](../Topic/CMFCPopupMenuBar::IsRibbonPanel.md)|리본 패널 여부를 나타냅니다 \(`FALSE` 기본적으로\).|  
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](../Topic/CMFCPopupMenuBar::IsRibbonPanelInRegularMode.md)|이 리본 패널 일반 모드에 있는지 여부를 나타냅니다 \(`FALSE` 기본적으로\).|  
|[CMFCPopupMenuBar::LoadFromHash](../Topic/CMFCPopupMenuBar::LoadFromHash.md)|에 보관 된 메뉴를 로드합니다.|  
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](../Topic/CMFCPopupMenuBar::RestoreDelayedSubMenu.md)|팝업 메뉴의 도구 모음을 닫아도 지연된 메뉴 단추를 복원 합니다.|  
|[CMFCPopupMenuBar::SetButtonStyle](../Topic/CMFCPopupMenuBar::SetButtonStyle.md)|지정한 인덱스에 도구 모음 단추의 스타일을 설정합니다.  \(재정의 [CMFCToolBar::SetButtonStyle](../Topic/CMFCToolBar::SetButtonStyle.md).\)|  
|[CMFCPopupMenuBar::SetOffset](../Topic/CMFCPopupMenuBar::SetOffset.md)|행 오프셋 팝업 메뉴 모음을 설정합니다.|  
|[CMFCPopupMenuBar::StartPopupMenuTimer](../Topic/CMFCPopupMenuBar::StartPopupMenuTimer.md)|지정 된 지연 된 팝업 메뉴 단추에 대 한 타이머를 시작 합니다.|  
  
### 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CMFCPopupMenuBar::m\_bDisableSideBarInXPMode](../Topic/CMFCPopupMenuBar::m_bDisableSideBarInXPMode.md)|응용 프로그램은 Windows XP 모양 일 때 회색 세로 막대를 표시할지 여부를 지정 합니다.|  
  
## 설명  
 `CMFCPopupMenuBar` 로 동시에 만든는 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) 및 그 안에 포함 된.  `CMFCPopupMenuBar` 의 전체 클라이언트 영역을 덮의 `CMFCPopupMenu` 개체입니다.  키보드 및 마우스 입력을 지원 합니다.  입력 하려면 통신의 `CMFCPopupMenu` 및 최상위 프레임 창입니다.  
  
## 예제  
 초기화 하는 다음 예제는 `CMFCPopupMenuBar` 개체는 `CMFCPopupMenu` 개체입니다.  이 코드의 일부인의  [그릴 클라이언트 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#7](../../mfc/reference/codesnippet/CPP/cmfcpopupmenubar-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
## 요구 사항  
 **헤더:** afxpopupmenubar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)