---
title: 'TN029: 분할 창 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.windows.splitter
dev_langs:
- C++
helpviewer_keywords:
- TN029
- splitter windows [MFC], about splitter windows
ms.assetid: 2c57ce99-2a3c-4eff-9cea-baccb13af075
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f0419e8f8aea141c3aaa54e320200160dae877f
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957226"
---
# <a name="tn029-splitter-windows"></a>TN029: 분할 창
이 노트에서는 MFC 설명 [CSplitterWnd 클래스](../mfc/reference/csplitterwnd-class.md), 창 분할 및 다른 창 창 크기를 조정 관리를 제공 합니다.  
  
## <a name="splitter-styles"></a>분할자 스타일  
 A `CSplitterWnd` windows 분할의 두 가지 다른 스타일을 지원 합니다.  
  
 "정적 분할 창 에서는" 분할 창 생성 될 때 창을 만듭니다. 순서 및 창 수 변하지 않습니다. 분할 막대는 서로 다른 창 크기 조정 하는 데 사용 됩니다. 각 창에는 서로 다른 뷰 클래스를 표시 하려면이 스타일을 사용할 수 있습니다. Visual c + + 그래픽 편집기 및 Windows 파일 관리자는이 분할자 스타일을 사용 하는 프로그램에 속합니다. 이 스타일의 분할 창에서 분할자 상자를 사용 하지 않습니다.  
  
 "동적 분할 창 에서는" 추가 창이 생성 되 고 사용자 분할 및 취소 분할 새 보기도 삭제 합니다. 이 분할 단일 보기로 시작 하 고 사용자가을 시작할 분할에 대 한 분할 상자를 제공 합니다. 분할 창 보기는 한 방향으로 분할 될 때 동적으로 새 뷰 개체를 만듭니다. 이 새 뷰 개체의 새 창을 나타냅니다. 분할 창 두 방향에서 키보드 인터페이스를 사용 하 여 뷰를 분할 하는 경우 세 개의 새 창에 대 한 3 개의 새로운 뷰 개체를 만듭니다. 분할 활성 상태인 동안 Windows 창 사이는 분할줄으로 분할 상자를 표시 합니다. Windows는 사용자는 분할 제거할 수 있지만 분할자 창 자체 될 때까지 원래 보기 남아는 손상 추가 뷰 개체를 제거 합니다. Microsoft Excel 및 Microsoft Word은 동적 분할 스타일을 사용 하는 응용 프로그램의 예입니다.  
  
 두 종류의 분할 창 만들 때의 행과 열 분할자를 관리 하는 최대 수를 지정 해야 합니다. 정적 분할 창 모든 행과 열을 채울 만들어집니다. 동적 분할 하면 첫 번째 창만 만듭니다 때는 `CSplitterWnd` 만들어집니다.  
  
 정적 분할 창에 지정할 수 있는 창의 최대 개수는 16 열 수가 16 행 있습니다. 권장된 구성은 다음과 같습니다.  
  
-   1 개 행 x 2 열: 일반적으로 서로 다른 창이 있는  
  
-   2 개 행 x 1 열: 일반적으로 서로 다른 창이 있는  
  
-   2 개 행 x 2 열: 일반적으로 유사한 창이 있는  
  
 동적 분할 창을에 지정할 수 있는 창의 최대 수는 2 개의 열 2 행 있습니다. 권장된 구성은 다음과 같습니다.  
  
-   1 개 행 x 2 열: 칼럼 형식 데이터에 대 한  
  
-   2 개 행 x 1 열: 텍스트 또는 기타 데이터에 대 한  
  
-   2 개 행 x 2 열: 표 또는 테이블에 대 한 데이터 지향  
  
## <a name="splitter-examples"></a>분할자 예제  
 MFC 샘플 프로그램의 많은 직접 또는 간접적으로 분할 창을 사용합니다. MFC 일반 샘플 [VIEWEX](../visual-cpp-samples.md) 분할자에 분할자를 배치 하는 방법을 포함 하 여 정적 분할 창에서는의 몇 가지 사용 방법을 보여 줍니다.  
  
 클래스를 만드는 새 여러 문서 MDI (인터페이스) 자식 프레임 창을 창에 포함 된 클래스 마법사를 사용할 수도 있습니다. 분할 창에 대 한 자세한 내용은 참조 하십시오. [여러 문서 형식, 뷰 및 프레임 창](../mfc/multiple-document-types-views-and-frame-windows.md)합니다.  
  
## <a name="terminology-used-by-implementation"></a>구현에서 사용 되는 용어  
 분할 창 관련 된 용어 목록은 다음과 같습니다.  
  
 `CSplitterWnd`:  
 창 분할 컨트롤 및 모든 창에 행 또는 열 간에 공유 되는 스크롤 막대를 제공 하는 창입니다. 0부터 시작 번호가 있는 행 및 열 지정 (첫 번째 창에 행이 = 0, 열 = 0).  
  
 창:  
 응용 프로그램별 창 하는 `CSplitterWnd` 를 관리 합니다. 하나의 창에서 파생 된 개체는 일반적으로 [CView 클래스](../mfc/reference/cview-class.md), 하나일 수 있습니다 하지만 [CWnd](../mfc/reference/cwnd-class.md) 적절 한 자식 창 ID를 가진 개체를  
  
 사용 하는 `CWnd`-파생 된 개체, 개체의 RUNTIME_CLASS 전달는 `CreateView` 을 사용한 경우와 마찬가지로 함수는 `CView`-파생 클래스입니다. 클래스는 프레임 워크 런타임 시 동적 생성을 사용 하기 때문에 DECLARE_DYNCREATE 및 IMPLEMENT_DYNCREATE 사용 해야 합니다. 많은 코드에는 없지만 `CSplitterWnd` 에 고유는 `CView` 클래스 [CObject::IsKindOf](../mfc/reference/cobject-class.md#iskindof) 이러한 작업을 수행 하기 전에 항상 사용 됩니다.  
  
 분할 막대:  
 컨트롤의 창 행과 열 사이 배치 된입니다. 창의 열 또는 행의 크기 조정에 사용할 수 있습니다.  
  
 분할자 상자:  
 동적 컨트롤 `CSplitterWnd` 작업창의 새 행 이나 열을 만드는 데 사용할 수 있는 합니다. 파일은 왼쪽의 가로 스크롤 막대 또는 세로 스크롤 막대의 맨 위에 있습니다.  
  
 분할자 교차 합니다.  
 가로 분할 막대와 세로 분할 막대 교차 합니다. 동시에 행 및 열 창 크기를 조정 하 여 끌 수 있습니다.  
  
## <a name="shared-scroll-bars"></a>공유 스크롤 막대  
 `CSplitterWnd` 클래스도 공유 스크롤 막대를 지원 합니다. 이러한 스크롤 막대 컨트롤에 자식 요소인는 `CSplitterWnd` 분할자의 여러 창을 공유 됩니다.  
  
 예를 들어 1 개 행 x 2 열 창에서 있습니다 WS_VSCROLL 만들 때 지정할 수는 `CSplitterWnd`합니다. Windows는 두 개의 창 간에 공유 되는 특별 한 스크롤 막대 컨트롤을 만듭니다.  
  
```  
[      ][      ][^]  
[pane00][pane01][|]  
[      ][      ][v]  
```  
  
 사용자가 스크롤 막대를 움직이면 WM_VSCROLL 메시지 모두 보기에 전송 됩니다. 스크롤 막대 위치를 설정 하는 두 보기 중 하나를 공유 스크롤 막대 설정 됩니다.  
  
 Note 공유 스크롤 막대는 유사한 보기 개체에 가장 유용 합니다. 분할자의 형식이 서로 다른 뷰를 함께 사용할 경우의 스크롤 위치를 조정 하는 특수 한 코드를 작성 해야 수 있습니다. 모든 `CView`-파생 클래스를 사용 하는 `CWnd` 스크롤 막대가 있는 경우 Api 공유 스크롤 막대를 위임 합니다. `CScrollView` 구현은의 한 예는 `CView` 지 원하는 클래스는 스크롤 막대를 공유 합니다. 클래스에서 파생 되지 않은 `CView`, 컨트롤이 아닌 스크롤 막대를 사용 하는 클래스 또는 표준 Windows 구현을 사용 하는 클래스 (예를 들어 `CEditView`)의 공유 스크롤 막대 기능을 통해 작동 하지 것입니다 `CSplitterWnd`합니다.  
  
## <a name="minimum-sizes"></a>최소 크기  
 각 행에 대해 최소 행 높이 않으며 각 열에는 최소 열 너비입니다. 이 최소는 창이 너무 작아 전체 정보에 표시 되는지 보장 합니다.  
  
 정적 분할 창 초기 최소 행 높이 및 열 너비는 0입니다. 동적 분할 창에 대 한 초기 최소 행 높이 및 열 너비 설정 됩니다는 *sizeMin* 의 매개 변수는 `CSplitterWnd::Create` 함수입니다.  
  
 사용 하 여 이러한 최소 크기를 변경할 수는 [CSplitterWnd::SetRowInfo](../mfc/reference/csplitterwnd-class.md#setrowinfo) 및 [CSplitterWnd::SetColumnInfo](../mfc/reference/csplitterwnd-class.md#setcolumninfo) 함수입니다.  
  
## <a name="actual-vs-ideal-sizes"></a>실제 vs입니다. 이상적인 크기  
 분할 창에서 창 레이아웃을 포함 하는 프레임의 크기에 따라 달라 집니다. 사용자가 포함 된 프레임 크기를 조정할 때의 `CSplitterWnd` 위치를 변경 하 고 최대한 저장할 수 있도록 창의 크기를 조절 합니다.  
  
 사용자는 수동으로 설정할 수 있는 행 높이 및 열 너비 크기 또는 프로그램이 사용 하 여 이상적인 크기를 설정할 수는 `CSplitterWnd` 클래스입니다. 실제 크기는 이상적인 보다 크거나 작을 수 있습니다. Windows 이상적인 크기를 표시 하는 공간이 충분 하지 않은 경우 또는 오른쪽 또는 분할자 창 아래쪽에 빈 공간이 너무 많은 경우 실제 크기를 조정 합니다.  
  
## <a name="custom-controls"></a>사용자 지정 컨트롤  
 사용자 지정 된 동작 및 사용자 지정 된 인터페이스를 제공 하기 위해 다양 한 함수를 재정의할 수 있습니다. 이 첫 번째 집합의 창에는 여러 그래픽 구성 요소에 대 한 대체 이미지를 제공 하기를 재정의할 수 있습니다.  
  
- `virtual void OnDrawSpltter(CDC* pDC, ESplitType nType, const CRect& rect);`  
  
- `virtual void OnInvertTracker(const CRect& rect);`  
  
 공유 scroll bar 컨트롤을 만들려면이 함수를 호출 합니다. 스크롤 막대 옆에 있는 여러 추가 컨트롤을 만들 수를 재정의할 수 있습니다.  
  
- `virtual BOOL CreateScrollBarCtrl(DWORD dwStyle, UINT nID);`  
  
 이러한 함수는 동적 분할 창의 논리를 구현합니다. 더 많은 고급 분할자 논리를 제공 하도록이 재정의할 수 있습니다.  
  
- `virtual void DeleteView(int row, int col);`  
  
- `virtual BOOL SplitRow(int cyBefore);`  
  
- `virtual BOOL SplitColumn(int cxBefore);`  
  
- `virtual void DeleteRow(int rowDelete);`  
  
- `virtual void DeleteColumn(int colDelete);`  
  
## <a name="cview-functionality"></a>CView 기능  
 `CView` 클래스에 위임 하기 위해 다음과 같은 개략적인 명령을 사용 하 여는 `CSplitterWnd` 구현 합니다. 이러한 명령은 virtual 이거나 있기 때문에 표준 `CView` 구현 전체 필요 하지 것입니다 `CSplitterWnd` 구현에 연결 되도록 합니다. 사용 하는 응용 프로그램에 대 한 `CView` 아닌 `CSplitterWnd`, `CSplitterWnd` 구현 응용 프로그램과 연결 되지 것입니다.  
  
 `virtual BOOL CanActivateNext(BOOL bPrev = FALSE);`  
 ID_NEXT_PANE 또는 ID_PREV_PANE 현재 가능한 지 여부를 확인 합니다.  
  
 `virtual void ActivateNext(BOOL bPrev = FALSE);`  
 "다음 창" 또는 "이전 창" 명령을 실행합니다.  
  
 `virtual BOOL DoKeyboardSplit();`  
 키보드 분할 명령을, 일반적으로 "창 분할"를 실행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

