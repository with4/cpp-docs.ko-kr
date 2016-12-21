---
title: "CScrollView Class | Microsoft Docs"
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
  - "CScrollView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CScrollView class"
  - "scrolling views"
  - "뷰, 스크롤"
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CScrollView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

A  [CView](../../mfc/reference/cview-class.md) 스크롤 기능을 합니다.  
  
## 구문  
  
```  
class CScrollView : public CView  
```  
  
## 멤버  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CScrollView::CScrollView](../Topic/CScrollView::CScrollView.md)|`CScrollView` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CScrollView::CheckScrollBars](../Topic/CScrollView::CheckScrollBars.md)|스크롤 뷰 가로 및 세로 스크롤 막대가 있는지 여부를 나타냅니다.|  
|[CScrollView::FillOutsideRect](../Topic/CScrollView::FillOutsideRect.md)|보기 스크롤 영역 외부의 영역을 채웁니다.|  
|[CScrollView::GetDeviceScrollPosition](../Topic/CScrollView::GetDeviceScrollPosition.md)|장치 단위 현재 스크롤 위치를 가져옵니다.|  
|[CScrollView::GetDeviceScrollSizes](../Topic/CScrollView::GetDeviceScrollSizes.md)|현재 매핑 모드, 전체 크기 및 줄 및 페이지 크기의 스크롤할 수 있는 뷰를 가져옵니다.  크기는 장치 단위입니다.|  
|[CScrollView::GetScrollPosition](../Topic/CScrollView::GetScrollPosition.md)|논리 단위에서를 현재 스크롤 위치를 가져옵니다.|  
|[CScrollView::GetTotalSize](../Topic/CScrollView::GetTotalSize.md)|논리 단위 스크롤 뷰의 전체 크기를 가져옵니다.|  
|[CScrollView::ResizeParentToFit](../Topic/CScrollView::ResizeParentToFit.md)|프레임의 크기를 결정 하는 보기의 크기를 발생 합니다.|  
|[CScrollView::ScrollToPosition](../Topic/CScrollView::ScrollToPosition.md)|뷰 논리 단위로 지정 된 특정 지점으로 스크롤합니다.|  
|[CScrollView::SetScaleToFitSize](../Topic/CScrollView::SetScaleToFitSize.md)|스크롤 뷰 배율\-맞춤 모드로 설정합니다.|  
|[CScrollView::SetScrollSizes](../Topic/CScrollView::SetScrollSizes.md)|스크롤 뷰 매핑 모드, 전체 크기 및 가로 및 세로 스크롤 양을 설정합니다.|  
  
## 설명  
 표준에서 파생 된 클래스에 자신을 스크롤을 처리할 수 있는 `CView` 메시지 매핑 재정의  [OnHScroll](../Topic/CWnd::OnHScroll.md) 및  [OnVScroll](../Topic/CWnd::OnVScroll.md) 멤버 함수입니다.  하지만 `CScrollView` 추가 기능에는 `CView` 기능:  
  
-   창과 뷰포트 크기 및 매핑 모드를 관리합니다.  
  
-   스크롤 막대 메시지에 자동으로 스크롤합니다.  
  
-   자동으로 메시지에 응답 하는 키보드, 스크롤 아닌 마우스 또는 IntelliMouse 휠을 스크롤합니다.  
  
 자동으로 메시지에 응답 하는 키보드에서 이동 하려면 WM\_KEYDOWN 메시지를 추가 하 고 VK\_DOWN, VK\_PREV 및 호출에 대 한 테스트  [SetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787597).  
  
 마우스 휠 메시지 매핑을 재정의 하 여 사용자가 직접 스크롤을 처리할 수 있는  [OnMouseWheel](../Topic/CWnd::OnMouseWheel.md) 및  [OnRegisteredMouseWheel](../Topic/CWnd::OnRegisteredMouseWheel.md) 멤버 함수입니다.  그대로 `CScrollView`, 권장 되는 동작에 대 한 이러한 멤버 함수를 지 원하는  [WM\_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617), 휠 회전 메시지.  
  
 자동 스크롤을 이용 하려면 뷰 클래스에서 파생 `CScrollView` 대신에서 `CView`.  보기는 처음 만들 때, 호출 문서의 크기에 따라 스크롤 뷰의 크기를 계산 하려면는 `SetScrollSizes` 멤버 함수를 재정의 중에서  [CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) 또는  [CView::OnUpdate](../Topic/CView::OnUpdate.md).  \(문서의 크기를 쿼리 하는 코드를 직접 작성 해야 합니다.  예를 들어, 참조는  [샘플 낙서](../../top/visual-cpp-samples.md).\)  
  
 호출 하는 `SetScrollSizes` 멤버 함수 매핑 모드는 뷰, 스크롤 뷰 및 가로 세로 방향으로 스크롤 하는 금액의 총 크기를 설정 합니다.  모든 크기의 논리 단위입니다.  보기의 논리적 크기 일반적으로 문서에 저장 된 데이터에서 계산 되 있지만 경우에 따라 고정 된 크기를 지정할 수 있습니다.  두 가지 예제를 보려면  [CScrollView::SetScrollSizes](../Topic/CScrollView::SetScrollSizes.md).  
  
 가로 및 세로로 논리 단위로 스크롤할 양을 지정 합니다.  기본적으로 사용자가 스크롤 막대 스크롤 상자 외부에서 샤프트를 누르면 `CScrollView` 는 "페이지"를 스크롤합니다. 스크롤 막대의 양쪽 끝에 있는 스크롤 화살표를 클릭할 경우 `CScrollView` 는 "줄" 스크롤합니다. 기본적으로 페이지 보기의 전체 크기의 1\/10입니다. 선은 페이지 크기의 1\/10입니다.  사용자 지정 크기를 전달 하 여이 기본값을 재정의 하 여 `SetScrollSizes` 멤버 함수.  예를 들어, 경우 가로 크기 일부 전체 크기와 세로 크기는 줄의 높이 너비의 분수를 현재 글꼴의 설정할 수 있습니다.  
  
 스크롤 하는 대신 `CScrollView` 보기 현재 창 크기를 자동으로 확장할 수 있습니다.  이 모드에서 보기를 스크롤 막대가 없습니다 및 논리 보기 늘어나거나 창의 클라이언트 영역 축소.  이 눈금에 맞춤 기능을 사용 하려면 호출  [CScrollView::SetScaleToFitSize](../Topic/CScrollView::SetScaleToFitSize.md).  \(프로시저 호출 `SetScaleToFitSize` 또는 `SetScrollSizes`, 하지만 둘 다.\)  
  
 전에 `OnDraw` 파생된 뷰 클래스의 멤버 함수 호출 `CScrollView` 뷰포트 원점에 대 한 자동 조정의 `CPaintDC` 전달 디바이스 컨텍스트 개체 `OnDraw`.  
  
 스크롤 창의 뷰포트를 조정 하려면 `CScrollView` 재정의  [CView::OnPrepareDC](../Topic/CView::OnPrepareDC.md).  이 조정에 대해 자동으로 `CPaintDC` 장치 컨텍스트는 `CScrollView` 전달 `OnDraw`, 하지만 호출 해야  **CScrollView::OnPrepareDC** 자신에 대 한 장치 컨텍스트를 같이 사용을 `CClientDC`.  재정의 하 여  **CScrollView::OnPrepareDC** 펜, 배경 색 및 기타 드로잉 특성을 설정할 수 있지만 확장 작업을 수행 하는 기본 클래스를 호출 합니다.  
  
 스크롤 막대 보기를 기준으로 세 위치에 다음과 같은 경우에 같이 나타날 수 있습니다.  
  
-   보기 사용에 대 한 표준 스타일 창 스크롤 막대를 설정할 수 있는  **WS\_HSCROLL** 및  **WS\_VSCROLL**[Windows 스타일](../../mfc/reference/window-styles.md).  
  
-   스크롤 막대 컨트롤 경우 프레임 워크에 전달 하는 보기를 포함 하는 프레임에 추가할 수 있습니다 또한 `WM_HSCROLL` 및 `WM_VSCROLL` 메시지 프레임 창에서 현재 보기를.  
  
-   또한 프레임 워크를 전달 스크롤 메시지는 `CSplitterWnd` splitter 컨트롤 현재 분할자 창 \(보기\).  에 추가 하는  [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) 공유 스크롤 막대와는 `CScrollView` 자체적으로 만들기 보다는 공유 된 개체를 사용 합니다.  
  
 사용에 대 한 자세한 내용은 `CScrollView`를 참조 하십시오  [문서\/뷰 아키텍처](../../mfc/document-view-architecture.md) 및  [파생 뷰 클래스에서에서 사용할 수 있는 MFC](../../mfc/derived-view-classes-available-in-mfc.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CScrollView`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [Diblook에서는 MFC 샘플](../../top/visual-cpp-samples.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CSplitterWnd Class](../../mfc/reference/csplitterwnd-class.md)