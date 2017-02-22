---
title: "CReBarCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CReBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBarCtrl class"
  - "rebar controls, control bar"
  - "rebar controls, CReBarCtrl class"
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CReBarCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

자식 창에 대 한 컨테이너 rebar 컨트롤의 기능을 캡슐화 합니다.  
  
## 구문  
  
```  
class CReBarCtrl : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CReBarCtrl::CReBarCtrl](../Topic/CReBarCtrl::CReBarCtrl.md)|`CReBarCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CReBarCtrl::BeginDrag](../Topic/CReBarCtrl::BeginDrag.md)|Rebar 컨트롤 드래그 앤 드롭 모드로 설정합니다.|  
|[CReBarCtrl::Create](../Topic/CReBarCtrl::Create.md)|Rebar 컨트롤을 만들고이에 연결 된 `CReBarCtrl` 개체입니다.|  
|[CReBarCtrl::CreateEx](../Topic/CReBarCtrl::CreateEx.md)|지정한 Windows 확장된 스타일 rebar 컨트롤을 만들고이에 연결 된 `CReBarCtrl` 개체입니다.|  
|[CReBarCtrl::DeleteBand](../Topic/CReBarCtrl::DeleteBand.md)|Rebar 컨트롤에서 밴드를 삭제합니다.|  
|[CReBarCtrl::DragMove](../Topic/CReBarCtrl::DragMove.md)|Rebar 컨트롤에서 끌어서 위치를 호출한 후 업데이트 `BeginDrag`.|  
|[CReBarCtrl::EndDrag](../Topic/CReBarCtrl::EndDrag.md)|Rebar 컨트롤의 끌어서 놓기 작업을 종료합니다.|  
|[CReBarCtrl::GetBandBorders](../Topic/CReBarCtrl::GetBandBorders.md)|밴드의 테두리를 검색합니다.|  
|[CReBarCtrl::GetBandCount](../Topic/CReBarCtrl::GetBandCount.md)|현재는 rebar 컨트롤에서에서 밴드의 수를 검색합니다.|  
|[CReBarCtrl::GetBandInfo](../Topic/CReBarCtrl::GetBandInfo.md)|Rebar 컨트롤에서 지정 된 밴드에 대 한 정보를 검색합니다.|  
|[CReBarCtrl::GetBandMargins](../Topic/CReBarCtrl::GetBandMargins.md)|밴드의 여백을 가져옵니다.|  
|[CReBarCtrl::GetBarHeight](../Topic/CReBarCtrl::GetBarHeight.md)|Rebar 컨트롤의 높이 검색합니다.|  
|[CReBarCtrl::GetBarInfo](../Topic/CReBarCtrl::GetBarInfo.md)|Rebar 컨트롤 및이 사용 하는 이미지 목록에 대 한 정보를 검색 합니다.|  
|[CReBarCtrl::GetBkColor](../Topic/CReBarCtrl::GetBkColor.md)|Rebar 컨트롤의 기본 배경 색을 검색합니다.|  
|[CReBarCtrl::GetColorScheme](../Topic/CReBarCtrl::GetColorScheme.md)|검색은  [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) 구조 rebar 컨트롤에 연결 합니다.|  
|[CReBarCtrl::GetDropTarget](../Topic/CReBarCtrl::GetDropTarget.md)|Rebar 컨트롤은 검색 `IDropTarget` 인터페이스 포인터입니다.|  
|[CReBarCtrl::GetExtendedStyle](../Topic/CReBarCtrl::GetExtendedStyle.md)|현재 rebar 컨트롤의 확장된 된 스타일을 가져옵니다.|  
|[CReBarCtrl::GetImageList](../Topic/CReBarCtrl::GetImageList.md)|Rebar 컨트롤에 연결 된 이미지 목록을 검색 합니다.|  
|[CReBarCtrl::GetPalette](../Topic/CReBarCtrl::GetPalette.md)|Rebar 컨트롤의 현재 색상표를 검색 합니다.|  
|[CReBarCtrl::GetRect](../Topic/CReBarCtrl::GetRect.md)|Rebar 컨트롤에서 지정 된 밴드에 대 한 경계 사각형을 검색합니다.|  
|[CReBarCtrl::GetRowCount](../Topic/CReBarCtrl::GetRowCount.md)|Rebar 컨트롤에서 밴드 행 개수를 검색합니다.|  
|[CReBarCtrl::GetRowHeight](../Topic/CReBarCtrl::GetRowHeight.md)|Rebar 컨트롤에서 지정 된 행의 높이 검색합니다.|  
|[CReBarCtrl::GetTextColor](../Topic/CReBarCtrl::GetTextColor.md)|Rebar 컨트롤의 기본 텍스트 색을 검색합니다.|  
|[CReBarCtrl::GetToolTips](../Topic/CReBarCtrl::GetToolTips.md)|Rebar 컨트롤에 연결 된 모든 도구 설명 컨트롤에 대 한 핸들을 검색 합니다.|  
|[CReBarCtrl::HitTest](../Topic/CReBarCtrl::HitTest.md)|Rebar 밴드에 있으면 화면에서 특정 지점의 rebar 밴드의 어떤 부분 인지 확인 합니다.|  
|[CReBarCtrl::IDToIndex](../Topic/CReBarCtrl::IDToIndex.md)|Rebar 컨트롤에서 밴드 인덱스 밴드 식별자 \(ID\)를 변환합니다.|  
|[CReBarCtrl::InsertBand](../Topic/CReBarCtrl::InsertBand.md)|새 밴드를 rebar 컨트롤에 삽입합니다.|  
|[CReBarCtrl::MaximizeBand](../Topic/CReBarCtrl::MaximizeBand.md)|최대 크기로 rebar 컨트롤에서 밴드의 크기를 조정 합니다.|  
|[CReBarCtrl::MinimizeBand](../Topic/CReBarCtrl::MinimizeBand.md)|작은 크기로 rebar 컨트롤에서 밴드의 크기를 조정 합니다.|  
|[CReBarCtrl::MoveBand](../Topic/CReBarCtrl::MoveBand.md)|밴드 하나 인덱스에서 다른 위치로 이동합니다.|  
|[CReBarCtrl::PushChevron](../Topic/CReBarCtrl::PushChevron.md)|프로그래밍 방식으로 갈매기를 푸시합니다.|  
|[CReBarCtrl::RestoreBand](../Topic/CReBarCtrl::RestoreBand.md)|이상적인 크기로 rebar 컨트롤에서 밴드의 크기를 조정 합니다.|  
|[CReBarCtrl::SetBandInfo](../Topic/CReBarCtrl::SetBandInfo.md)|Rebar 컨트롤에는 기존 밴드의 특성을 설정합니다.|  
|[CReBarCtrl::SetBandWidth](../Topic/CReBarCtrl::SetBandWidth.md)|현재 rebar 컨트롤에서 지정한 고정 된 밴드의 너비를 설정합니다.|  
|[CReBarCtrl::SetBarInfo](../Topic/CReBarCtrl::SetBarInfo.md)|Rebar 컨트롤의 특성을 설정합니다.|  
|[CReBarCtrl::SetBkColor](../Topic/CReBarCtrl::SetBkColor.md)|Rebar 컨트롤의 기본 배경색을 설정합니다.|  
|[CReBarCtrl::SetColorScheme](../Topic/CReBarCtrl::SetColorScheme.md)|Rebar 컨트롤에서 단추에 색 구성표를 설정합니다.|  
|[CReBarCtrl::SetExtendedStyle](../Topic/CReBarCtrl::SetExtendedStyle.md)|현재 rebar 컨트롤을 위한 확장된 스타일을 설정합니다.|  
|[CReBarCtrl::SetImageList](../Topic/CReBarCtrl::SetImageList.md)|Rebar 컨트롤은 이미지 목록을 설정합니다.|  
|[CReBarCtrl::SetOwner](../Topic/CReBarCtrl::SetOwner.md)|Rebar 컨트롤의 소유자 창으로 설정합니다.|  
|[CReBarCtrl::SetPalette](../Topic/CReBarCtrl::SetPalette.md)|Rebar 컨트롤의 현재 색상표를 설정합니다.|  
|[CReBarCtrl::SetTextColor](../Topic/CReBarCtrl::SetTextColor.md)|Rebar 컨트롤의 기본 텍스트 색을 설정합니다.|  
|[CReBarCtrl::SetToolTips](../Topic/CReBarCtrl::SetToolTips.md)|도구 설명 컨트롤에 rebar 컨트롤에 연결합니다.|  
|[CReBarCtrl::SetWindowTheme](../Topic/CReBarCtrl::SetWindowTheme.md)|Rebar 컨트롤의 시각적 스타일을 설정합니다.|  
|[CReBarCtrl::ShowBand](../Topic/CReBarCtrl::ShowBand.md)|표시 하거나 특정된 rebar 컨트롤에서 밴드를 숨깁니다.|  
|[CReBarCtrl::SizeToRect](../Topic/CReBarCtrl::SizeToRect.md)|Rebar 컨트롤에 지정 된 사각형에 적합 합니다.|  
  
## 설명  
 Rebar 밴드를 rebar 컨트롤에 포함 된 자식 창 rebar 컨트롤이 있는 응용 프로그램을 할당 합니다.  자식 창에 일반적으로 다른 일반적인 컨트롤입니다.  
  
 Rebar 컨트롤 밴드를 하나 이상 포함 되어 있습니다.  각 밴드는 그리퍼 막대, 비트맵, 텍스트 레이블 및 자식 창이 조합 포함 될 수 있습니다.  밴드 각이 항목 중 하나만 포함할 수 있습니다.  
  
 Rebar 컨트롤 배경 비트맵 위에 자식 창을 표시할 수 있습니다.  모든 rebar 컨트롤 밴드를 사용 하는 제외 하 고 조정할 수 있습니다의  **RBBS\_FIXEDSIZE** 스타일입니다.  위치를 변경 하거나 rebar 컨트롤 밴드 크기를 조정할 때 크기와 위치를 해당 밴드에 할당 된 자식 창의 rebar 컨트롤을 관리 합니다.  크기를 조정 하거나 컨트롤에서 밴드의 순서를 변경 하려면 클릭 한 밴드의 그리퍼 막대를 드래그 합니다.  
  
 다음 그림에서는 세 밴드가 있는 rebar 컨트롤을 보여 줍니다.  
  
-   0 밴드 플랫, 투명 한 도구 모음 컨트롤을 포함 되어 있습니다.  
  
-   1 밴드 모두 투명 하 게 투명 한 표준 드롭다운 단추가 있습니다.  
  
-   밴드 2 4 표준 단추 및 콤보 상자를 포함합니다.  
  
     ![Rebar 메뉴의 예](../../mfc/reference/media/vc4scc1.png "vc4SCC1")  
  
## Rebar 컨트롤  
 지 원하는 컨트롤 크기 조정 막대:  
  
-   이미지를 나열합니다.  
  
-   메시지 처리 합니다.  
  
-   사용자 지정 그리기 기능을 합니다.  
  
-   컨트롤 스타일 표준 창 스타일 외에도 다양 합니다.  이러한 스타일 목록을 참조 하십시오.  [Rebar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb774377) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 자세한 내용은  [CReBarCtrl 사용](../../mfc/using-crebarctrl.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CReBarCtrl`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)