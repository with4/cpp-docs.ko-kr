---
title: "CControlBar Class | Microsoft Docs"
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
  - "CControlBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CControlBar class"
  - "control bars [C++], 기본 클래스"
  - "dialog bars, 기본 클래스"
  - "OLE resize bars"
  - "OLE resize bars, 기본 클래스"
  - "상태 표시줄, 기본 클래스"
  - "도구 모음[C++], 기본 클래스"
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
caps.latest.revision: 22
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CControlBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컨트롤 막대 클래스의 기본 클래스  [프로그램](../../mfc/reference/cstatusbar-class.md),  [CToolBar](../../mfc/reference/ctoolbar-class.md),  [CDialogBar](../../mfc/reference/cdialogbar-class.md),  [CReBar](../../mfc/reference/crebar-class.md), 및  [COleResizeBar](../../mfc/reference/coleresizebar-class.md).  
  
## 구문  
  
```  
class CControlBar : public CWnd  
```  
  
## Members  
  
### Protected 생성자  
  
|이름|설명|  
|--------|--------|  
|[CControlBar::CControlBar](../Topic/CControlBar::CControlBar.md)|`CControlBar` 개체를 생성합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CControlBar::CalcDynamicLayout](../Topic/CControlBar::CalcDynamicLayout.md)|[CSize](../../atl-mfc-shared/reference/csize-class.md) 개체와 같은 동적 컨트롤 막대의 크기를 반환합니다.|  
|[CControlBar::CalcFixedLayout](../Topic/CControlBar::CalcFixedLayout.md)|[CSize](../../atl-mfc-shared/reference/csize-class.md) 개체같은 컨트롤 막대의 크기를 반환합니다.|  
|[CControlBar::CalcInsideRect](../Topic/CControlBar::CalcInsideRect.md)|테두리를 포함하여 컨트롤 막대 영역의 현재 크기를 반환합니다.|  
|[CControlBar::DoPaint](../Topic/CControlBar::DoPaint.md)|테두리 및 컨트롤 막대의 그리퍼를 렌더링합니다.|  
|[CControlBar::DrawBorders](../Topic/CControlBar::DrawBorders.md)|컨트롤 막대의 테두리를 렌더링합니다.|  
|[CControlBar::DrawGripper](../Topic/CControlBar::DrawGripper.md)|컨트롤 막대의 그리퍼를 렌더링합니다.|  
|[CControlBar::EnableDocking](../Topic/CControlBar::EnableDocking.md)|도킹 또는 부동된 컨트롤 막대가 있습니다.|  
|[CControlBar::GetBarStyle](../Topic/CControlBar::GetBarStyle.md)|컨트롤 막대 스타일 설정을 검색합니다.|  
|[CControlBar::GetBorders](../Topic/CControlBar::GetBorders.md)|컨트롤 막대의 테두리 값을 검색합니다.|  
|[CControlBar::GetCount](../Topic/CControlBar::GetCount.md)|컨트롤 막대에 있는  `HWND` 가 아닌 요소의 수를 반환합니다.|  
|[CControlBar::GetDockingFrame](../Topic/CControlBar::GetDockingFrame.md)|컨트롤 막대 도킹 프레임에 대한 포인터를 반환합니다.|  
|[CControlBar::IsFloating](../Topic/CControlBar::IsFloating.md)|문제가 컨트롤 막대가 부동 컨트롤 막대이면 0이 아닌 값을 반환합니다.|  
|[CControlBar::OnUpdateCmdUI](../Topic/CControlBar::OnUpdateCmdUI.md)|UI 명령 처리기를 호출합니다.|  
|[CControlBar::SetBarStyle](../Topic/CControlBar::SetBarStyle.md)|컨트롤 막대 스타일 설정을 수정합니다.|  
|[CControlBar::SetBorders](../Topic/CControlBar::SetBorders.md)|컨트롤 막대의 테두리 값을 설정합니다.|  
|[CControlBar::SetInPlaceOwner](../Topic/CControlBar::SetInPlaceOwner.md)|컨트롤 막대의 위치에 소유자를 변경합니다.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CControlBar::m\_bAutoDelete](../Topic/CControlBar::m_bAutoDelete.md)|0이 아니면 Windows 컨트롤 막대가 소멸될 때 해당  `CControlBar` 개체를 삭제합니다.|  
|[CControlBar::m\_pInPlaceOwner](../Topic/CControlBar::m_pInPlaceOwner.md)|컨트롤 막대의 위치에 소유자입니다.|  
  
## 설명  
 컨트롤 막대는 대개 프레임 창의 왼쪽이나 오른쪽 정렬을 하는 창입니다.  Windows 메시지에 응답 하고, 생성된 창인  `HWND` 기반 컨트롤 또는 창이 아니고 응용프로그램 코드와 프레임워크 코드에 의해 관리되는 `HWND`기반 항목 같은 자식 항목 중 하나를 포함할 수 있습니다.  목록 상자 및 편집 컨트롤은  `HWND` \-기반 제어의 예입니다; 상태 표시줄 창 및 비트맵 단추는`HWND`가 아닌\-컨트롤을 기반으로 합니다.  
  
 컨트롤 막대 창은 대개 부모 프레임 창의 자식 창이고, 일반적으로 클라이언트 뷰 또는 프레임 창의 MDI 클라이언트입니다.   `CControlBar`  개체는 부모 창의 클라이언트 영역에 대한 정보를 사용하여 배치합니다.  그런 다음 부모 창의 클라이언트 영역에 공간 할당되지 않은 유지에 대한 부모 창을 알립니다.  
  
 `CControlBar`에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [컨트롤 막대](../../mfc/control-bars.md)  
  
-   [기술 참고 31: 컨트롤 막대](../../mfc/tn031-control-bars.md).  
  
-   기술 자료 문서 Q242577: PRB: 대화 상자에 연결 된 메뉴에 대해 작동하지 않는 명령 UI 처리기 업데이트  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CControlBar`  
  
## 요구 사항  
 **헤더:**  afxext.h  
  
## 참고 항목  
 [MFC Sample CTRLBARS](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CToolBar Class](../../mfc/reference/ctoolbar-class.md)   
 [CDialogBar Class](../../mfc/reference/cdialogbar-class.md)   
 [CStatusBar Class](../../mfc/reference/cstatusbar-class.md)   
 [CReBar Class](../../mfc/reference/crebar-class.md)