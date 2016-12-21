---
title: "CSplitterWnd Class | Microsoft Docs"
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
  - "CSplitterWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSplitterWnd class"
  - "dynamic splitter windows"
  - "다중 뷰"
  - "분할 창"
  - "static splitter windows"
  - "뷰, 프레임당 다중"
ms.assetid: fd0de258-6dbe-4552-9e47-a39de0471d51
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSplitterWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

분할자 창의 창을 여러 개의 창으로 구성 하는 기능을 제공 합니다.  
  
## 구문  
  
```  
class CSplitterWnd : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSplitterWnd::CSplitterWnd](../Topic/CSplitterWnd::CSplitterWnd.md)|호출을 생성 하는 `CSplitterWnd` 개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSplitterWnd::ActivateNext](../Topic/CSplitterWnd::ActivateNext.md)|\[다음 창\] 또는 \[이전 창\] 명령을 수행합니다.|  
|[CSplitterWnd::CanActivateNext](../Topic/CSplitterWnd::CanActivateNext.md)|\[다음 창\] 또는 \[이전 창\] 명령을 현재 가능한 지 확인 합니다.|  
|[CSplitterWnd::Create](../Topic/CSplitterWnd::Create.md)|동적 분할자 창을 만들고 연결할 수 있는 호출을 `CSplitterWnd` 개체입니다.|  
|[CSplitterWnd::CreateScrollBarCtrl](../Topic/CSplitterWnd::CreateScrollBarCtrl.md)|공유 스크롤 막대 컨트롤을 만듭니다.|  
|[CSplitterWnd::CreateStatic](../Topic/CSplitterWnd::CreateStatic.md)|정적 분할 창에 연결 하는 호출을 `CSplitterWnd` 개체입니다.|  
|[CSplitterWnd::CreateView](../Topic/CSplitterWnd::CreateView.md)|분할자 창에는 창 만들기를 호출 합니다.|  
|[CSplitterWnd::DeleteColumn](../Topic/CSplitterWnd::DeleteColumn.md)|분할 창에서 열을 삭제합니다.|  
|[CSplitterWnd::DeleteRow](../Topic/CSplitterWnd::DeleteRow.md)|분할 창에서 행을 삭제합니다.|  
|[CSplitterWnd::DeleteView](../Topic/CSplitterWnd::DeleteView.md)|분할 창에서 뷰를 삭제합니다.|  
|[CSplitterWnd::DoKeyboardSplit](../Topic/CSplitterWnd::DoKeyboardSplit.md)|키보드 명령, 일반적으로 "창 나누기" 분할을 수행 합니다.|  
|[CSplitterWnd::DoScroll](../Topic/CSplitterWnd::DoScroll.md)|분할 창 스크롤을 동기화를 수행 합니다.|  
|[CSplitterWnd::DoScrollBy](../Topic/CSplitterWnd::DoScrollBy.md)|스크롤 windows는 지정 된 픽셀 수 만큼 분할 합니다.|  
|[CSplitterWnd::GetActivePane](../Topic/CSplitterWnd::GetActivePane.md)|현재 창에서 포커스 또는 활성 뷰에서 프레임을 결정합니다.|  
|[CSplitterWnd::GetColumnCount](../Topic/CSplitterWnd::GetColumnCount.md)|현재 창을 열 수를 반환합니다.|  
|[CSplitterWnd::GetColumnInfo](../Topic/CSplitterWnd::GetColumnInfo.md)|지정 된 열에 정보를 반환합니다.|  
|[CSplitterWnd::GetPane](../Topic/CSplitterWnd::GetPane.md)|창에 지정 된 행과 열을 반환합니다.|  
|[CSplitterWnd::GetRowCount](../Topic/CSplitterWnd::GetRowCount.md)|현재 창의 행 개수를 반환합니다.|  
|[CSplitterWnd::GetRowInfo](../Topic/CSplitterWnd::GetRowInfo.md)|정보에서 지정 된 행을 반환합니다.|  
|[CSplitterWnd::GetScrollStyle](../Topic/CSplitterWnd::GetScrollStyle.md)|공유 스크롤 막대 스타일을 반환합니다.|  
|[CSplitterWnd::IdFromRowCol](../Topic/CSplitterWnd::IdFromRowCol.md)|자식 창 ID 창에서 지정 된 행과 열을 반환합니다.|  
|[CSplitterWnd::IsChildPane](../Topic/CSplitterWnd::IsChildPane.md)|현재 창에이 분할자 창의 자식 창 적용 되는지 확인 하려면 호출 합니다.|  
|[CSplitterWnd::IsTracking](../Topic/CSplitterWnd::IsTracking.md)|분할 막대 현재 이동 하는 경우를 결정 합니다.|  
|[CSplitterWnd::RecalcLayout](../Topic/CSplitterWnd::RecalcLayout.md)|분할 창에서 행 또는 열 크기를 조정한 후 다시 표시 하려면 다음과 같이 호출 합니다.|  
|[CSplitterWnd::SetActivePane](../Topic/CSplitterWnd::SetActivePane.md)|활성화 한 프레임에서 창을 설정 합니다.|  
|[CSplitterWnd::SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md)|지정 된 열 정보를 설정 하려면 호출 합니다.|  
|[CSplitterWnd::SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md)|지정 된 행 정보를 설정 하려면 호출 합니다.|  
|[CSplitterWnd::SetScrollStyle](../Topic/CSplitterWnd::SetScrollStyle.md)|새 스크롤 막대 스타일 분할자 창의 스크롤 막대 지원 공유를 지정 합니다.|  
|[CSplitterWnd::SplitColumn](../Topic/CSplitterWnd::SplitColumn.md)|프레임 창이 세로로 분할 되는 지점을 나타냅니다.|  
|[CSplitterWnd::SplitRow](../Topic/CSplitterWnd::SplitRow.md)|프레임 창이 가로로 분할 되는 지점을 나타냅니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSplitterWnd::OnDraw](../Topic/CSplitterWnd::OnDraw.md)|분할 창 그리려면 프레임 워크에서 호출 됩니다.|  
|[CSplitterWnd::OnDrawSplitter](../Topic/CSplitterWnd::OnDrawSplitter.md)|분할 창의 이미지를 렌더링합니다.|  
|[CSplitterWnd::OnInvertTracker](../Topic/CSplitterWnd::OnInvertTracker.md)|같은 크기와 모양으로 프레임 창으로 분할 창의 이미지를 렌더링 합니다.|  
  
## 설명  
 창 일반적으로 응용 프로그램 관련 개체에서 파생 됩니다.  [CView](../../mfc/reference/cview-class.md), 모든 수  [CWnd](../../mfc/reference/cwnd-class.md) 해당 자식 창 ID를 가진 개체  
  
 A `CSplitterWnd` 부모에 일반적으로 포함 된  [CFrameWnd](../../mfc/reference/cframewnd-class.md) 또는  [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) 개체입니다.  생성 된 `CSplitterWnd` 다음 단계를 사용 하 여 개체:  
  
1.  포함 된 `CSplitterWnd` 부모 프레임에서 멤버 변수.  
  
2.  상위 프레임의 재정의  [CFrameWnd::OnCreateClient](../Topic/CFrameWnd::OnCreateClient.md) 멤버 함수입니다.  
  
3.  재정의 내 `OnCreateClient`, 호출 된  [만들기](../Topic/CSplitterWnd::Create.md) 또는  [CreateStatic](../Topic/CSplitterWnd::CreateStatic.md) 멤버 함수를 `CSplitterWnd`.  
  
 호출을  **만들기** 동적 분할자 창을 만드는 멤버 함수입니다.  동적 분할자 창 만들기 여러 개의 개별 창 또는 동일한 문서 보기를 스크롤할 때 일반적으로 사용 됩니다.  프레임 워크는 초기 분할자 창을 자동으로 만듭니다. 다음 프레임 워크, 크기 조정, 만들고 추가 창으로 사용자는 분할 창 컨트롤을 삭제 합니다.  
  
 호출 하면  **만들기**, 창이 너무 작아 표시할 시기를 결정 하는 최소 행 높이 열 너비를 지정 합니다.  호출한 후  **만들기**를 호출 하 여 이러한 최소값을 조정할 수 있습니다는  [SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md) 및  [SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md) 멤버 함수입니다.  
  
 또한 사용의 `SetColumnInfo` 및 `SetRowInfo` 멤버 함수는 "이상적" 열 너비와 행 높이 "이상적"를 설정 합니다.  프레임 워크는 분할자 창이 표시 되 면 먼저 분할자 창의 부모 프레임을 표시 합니다.  다음 프레임 워크 틀 분할자 창 클라이언트 영역의 오른쪽 아래 모서리에 왼쪽에서 작업의 이상적인 크기에 따라 행과 열에 배치 합니다.  
  
 동적 분할자 창의 창을 모두 동일한 클래스에 있어야 합니다.  Microsoft Word 및 Microsoft Excel 동적 분할 창을 지 원하는 친숙 한 응용 프로그램을 포함 합니다.  
  
 사용 된 `CreateStatic` 멤버 함수는 정적 분할 창을 만듭니다.  사용자 창에서 정적 분할자의 번호 또는 순서 없는 창 크기를 변경할 수 있습니다.  
  
 특히 정적 분할자를 만들 때 정적 분할자의 모든를 만들어야 합니다.  이전 프레임의 모든 틀을 만들 해야 `OnCreateClient` 멤버 함수 반환 값, 또는 창에 제대로 표시 되지 않는 프레임 워크 됩니다.  
  
 `CreateStatic` 멤버 함수를 자동으로 정적 분할자 최소 행 높이 열 너비를 0으로 초기화 합니다.  호출한 후  **만들기**를 호출 하 여 이러한 최소 조정의  [SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md) 및  [SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md) 멤버 함수.  또한 사용 `SetColumnInfo` 및 `SetRowInfo` 를 호출한 후 `CreateStatic` 이상적인 창 크기를 나타내려면 원하는.  
  
 정적 분할자의 개별 창에는 종종 다른 클래스에 속합니다.  정적 분할 창에 대 한 예제 그래픽 편집기 및 Windows 파일 관리자를 참조 하십시오.  
  
 분할 창 틀 스크롤 막대\) \(외 특별 한 스크롤 막대를 지원 합니다.  이 스크롤 막대의 자식인의 `CSplitterWnd` 및 개체 창에서 공유 됩니다.  
  
 분할자 창을 만들 때이 특별 한 스크롤 막대를 만듭니다.  예를 들어,는 `CSplitterWnd` 가 두 개의 열, 행 및  **WS\_VSCROLL** 스타일을 공유 하는 두 개의 창에 세로 스크롤 막대가 표시 됩니다.  사용자가 스크롤 막대를 이동 하면 `WM_VSCROLL` 두 창에 메시지를 보냅니다.  창 스크롤 막대의 위치를 설정 하면 공유 스크롤 막대가 설정 됩니다.  
  
 분할 창에 자세한 내용은 참조 하십시오.  
  
-   [기술 참고 29](../../mfc/tn029-splitter-windows.md)  
  
-   기술 자료 문서 Q262024: 방법: 사용 Cpropertysheet는 자식 Csplitterwnd의로  
  
 동적 분할자 창을 만드는 방법에 대 한 자세한 내용은 참조 하십시오.  
  
-   MFC 샘플  [낙서](../../top/visual-cpp-samples.md)  
  
-   MFC 샘플  [VIEWEX](../../top/visual-cpp-samples.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSplitterWnd`  
  
## 요구 사항  
 **헤더:**  afxext.h  
  
## 참고 항목  
 [VIEWEX MFC 샘플](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)