---
title: "CView Class | Microsoft Docs"
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
  - "CView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "자식 창, 뷰"
  - "CView class"
  - "document/view architecture"
  - "frame windows [C++], 뷰"
  - "입력, and view class"
  - "MDI[C++], view windows"
  - "다중 뷰"
  - "인쇄 미리 보기, view windows"
  - "user input [C++], interpreting through view class"
  - "뷰[C++], view classes"
  - "windows [C++], 뷰"
ms.assetid: 9cff3c56-7564-416b-b9a4-71a9254ed755
caps.latest.revision: 25
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자 정의 뷰 클래스의 기본 기능을 제공 합니다.  
  
## 구문  
  
```  
class AFX_NOVTABLE CView : public CWnd  
```  
  
## 멤버  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CView::CView](../Topic/CView::CView.md)|`CView` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CView::DoPreparePrinting](../Topic/CView::DoPreparePrinting.md)|인쇄 대화 상자를 표시 하 고 프린터 디바이스 컨텍스트를 만듭니다. 재정의 하는 경우 호출을 `OnPreparePrinting` 멤버 함수입니다.|  
|[CView::GetDocument](../Topic/CView::GetDocument.md)|뷰와 연결 된 문서를 반환 합니다.|  
|[CView::IsSelected](../Topic/CView::IsSelected.md)|문서 항목이 선택 되어 있는지 여부를 테스트 합니다.  OLE 지원입니다.|  
|[CView::OnDragEnter](../Topic/CView::OnDragEnter.md)|먼저 항목 보기의 끌어 놓기 영역으로 끌 때 호출 됩니다.|  
|[CView::OnDragLeave](../Topic/CView::OnDragLeave.md)|끌어 온된 항목은 보기의 끌어 놓기 영역을 벗어나면 호출 됩니다.|  
|[CView::OnDragOver](../Topic/CView::OnDragOver.md)|보기의 끌어 놓기 영역 위로 항목을 끌 때 호출 됩니다.|  
|[CView::OnDragScroll](../Topic/CView::OnDragScroll.md)|호출 창 스크롤 영역에 커서를 끌 여부를 확인 합니다.|  
|[CView::OnDrop](../Topic/CView::OnDrop.md)|기본 처리기 보기의 끌어 놓기 영역에 있는 항목이 삭제 된 경우 호출 됩니다.|  
|[CView::OnDropEx](../Topic/CView::OnDropEx.md)|기본 처리기 보기의 끌어 놓기 영역에 있는 항목이 삭제 된 경우 호출 됩니다.|  
|[CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md)|보기는 문서에 처음 연결 된 후에 호출 됩니다.|  
|[CView::OnPrepareDC](../Topic/CView::OnPrepareDC.md)|호출 하기 전에 `OnDraw` 화면 표시에 대 한 멤버 함수를 호출 또는 `OnPrint` 인쇄 또는 인쇄 미리 보기에 대 한 멤버 함수를 호출 합니다.|  
|[CView::OnScroll](../Topic/CView::OnScroll.md)|보기의 테두리를 벗어나는 OLE 항목을 놓을 때 호출 됩니다.|  
|[CView::OnScrollBy](../Topic/CView::OnScrollBy.md)|현재 위치에서 OLE 항목을 포함 하는 보기를 스크롤할 때 호출 됩니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CView::OnActivateFrame](../Topic/CView::OnActivateFrame.md)|뷰를 포함 하는 프레임 창이 활성화 또는 비활성화 되 면 호출 됩니다.|  
|[CView::OnActivateView](../Topic/CView::OnActivateView.md)|뷰가 활성화 될 때 호출 됩니다.|  
|[CView::OnBeginPrinting](../Topic/CView::OnBeginPrinting.md)|인쇄 작업이 시작 될 때 호출 됩니다. 그래픽 장치 인터페이스 \(GDI\) 리소스 할당을 재정의 합니다.|  
|[CView::OnDraw](../Topic/CView::OnDraw.md)|문서의 화면 표시, 인쇄 또는 인쇄 미리 보기에 대 한 이미지를 렌더링 하기 위해 호출 됩니다.  구현이 필요 합니다.|  
|[CView::OnEndPrinting](../Topic/CView::OnEndPrinting.md)|인쇄 작업이 끝날 때 호출 됩니다. GDI 리소스 할당을 재정의 합니다.|  
|[CView::OnEndPrintPreview](../Topic/CView::OnEndPrintPreview.md)|미리 보기 모드를 종료 하면 호출 됩니다.|  
|[CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md)|문서를 인쇄 하거나 미리 보기 전에 호출 됩니다. 인쇄 대화 상자를 초기화 하는 무시 합니다.|  
|[CView::OnPrint](../Topic/CView::OnPrint.md)|인쇄 또는 문서의 페이지 미리 보기를 호출 합니다.|  
|[CView::OnUpdate](../Topic/CView::OnUpdate.md)|해당 문서가 보기에 알리기 위해 호출 수정 합니다.|  
  
## 설명  
 뷰는 문서에 첨부 된 및 문서와 사용자 사이 중개 역할: 보기 이미지 화면 또는 프린터에 문서를 렌더링 하 고 사용자 입력에는 문서 작업으로 해석 합니다.  
  
 뷰는 프레임 창의 자식입니다.  둘 이상의 뷰는 프레임 창의 경우 분할자 창의 공유할 수 있습니다.  클래스 뷰, 프레임 창 클래스를 문서 클래스 사이의 관계에서 설정 되는 `CDocTemplate` 개체입니다.  때 사용자 새 창을 열거나 기존 분할 프레임 워크 새 보기를 생성 한 문서를 첨부 합니다.  
  
 하나의 문서에 보기를 연결 될 수 있지만 문서의 여러 보기를 한 번에 연결 되어 있을 수 있습니다\-예를 들어, 문서 또는 다중 문서 인터페이스 \(MDI\) 응용 프로그램에 여러 개의 자식 창을 분할자 창에서 표시 됩니다.  응용 프로그램 특정된 문서 형식에 대 한 다른 유형의 보기를 제공할 수 있습니다. 예를 들어, 워드 프로세서 프로그램 문서의 전체 텍스트 보기와 섹션 제목을 표시 합니다. 개요 보기를 제공할 수 있습니다.  분할자 창을 사용 하는 경우 서로 다른 뷰를 개별 프레임 창 또는 단일 프레임 창의 별도 창에 배치할 수 있습니다.  
  
 보기는 여러 가지 메뉴나 도구 모음, 스크롤 막대에서 명령 뿐 아니라 드래그 앤 드롭 기능을 통해 입력, 마우스 입력 이나 키보드 입력 등 입력 처리를 담당할 수 있습니다.  보기의 프레임 창에 전달 하는 명령을 받습니다.  보기 지정한 명령을 처리 하지 않는 경우 명령 관련된 문서에 전달 합니다.  모든 명령 대상 처럼 보기 메시지 맵을 통해 메시지를 처리합니다.  
  
 보기 담당 표시 한 문서의 데이터를 수정 하지만 저장 하기 않습니다.  문서 데이터에 대 한 필요한 정보를 보기를 제공합니다.  보기 액세스 하거나 문서의 데이터 멤버를 직접 호출 하는 뷰 클래스에 대 한 문서 클래스의 멤버 함수를 제공할 수 있습니다 수 있습니다.  
  
 문서의 데이터가 변경 되 면 일반적으로 보기 변경에 대 한 책임을 호출을  [CDocument::UpdateAllViews](../Topic/CDocument::UpdateAllViews.md) 함수를 호출 하 여 다른 뷰에 알립니다 문서는 `OnUpdate` 멤버 함수에 대 한 각.  기본 구현 된 `OnUpdate` 뷰의 전체 클라이언트 영역을 무효화 합니다.  문서의 수정 된 부분을 매핑할 클라이언트 영역의 영역에만 무효화를 재정의할 수 있습니다.  
  
 사용 `CView`, 클래스에서 파생 하 여 구현 된 `OnDraw` 화면 수행 하는 멤버 함수.  또한 수 `OnDraw` 인쇄 및 인쇄 미리 보기를 수행 합니다.  프레임 워크는 인쇄 및 문서 미리 보기에 대해 인쇄 루프를 처리 합니다.  
  
 뷰 스크롤 막대 메시지를 처리 하는  [CWnd::OnHScroll](../Topic/CWnd::OnHScroll.md) 및  [CWnd::OnVScroll](../Topic/CWnd::OnVScroll.md) 멤버 함수입니다.  스크롤 막대 메시지 처리이 함수를 구현할 수 있습니다 또는 사용할 수 있는 `CView` 파생 클래스  [CScrollView](../../mfc/reference/cscrollview-class.md) 스크롤을 처리 하.  
  
 뿐만 아니라 `CScrollView`, Mfc 라이브러리에서 파생 된 다른 9 개의 클래스를 제공 합니다. `CView`.  
  
-   [CCtrlView](../../mfc/reference/cctrlview-class.md), 보기 문서 보기 아키텍처와 트리, 목록 및 서식 있는 편집 컨트롤을 사용할 수 있게 합니다.  
  
-   [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md), 대화 상자 컨트롤에서 데이터베이스 레코드를 표시 하는 보기입니다.  
  
-   [CEditView](../../mfc/reference/ceditview-class.md), 여러 줄로 된 간단한 텍스트 편집기를 제공 하는 보기입니다.  사용할 수 있는 `CEditView` 대화 상자 뿐만 아니라 문서에 대 한 뷰 컨트롤 개체.  
  
-   [CFormView](../../mfc/reference/cformview-class.md), 스크롤할 수 있는 뷰 대화 상자 컨트롤을 포함 하는 대화 상자 템플릿 리소스를 기반으로 합니다.  
  
-   [CListView](../../mfc/reference/clistview-class.md), 뷰 문서\-뷰 아키텍처를 이용한 목록 컨트롤을 사용할 수 있게 합니다.  
  
-   [CRecordView](../../mfc/reference/crecordview-class.md), 대화 상자 컨트롤에서 데이터베이스 레코드를 표시 하는 보기입니다.  
  
-   [CRichEditView](../../mfc/reference/cricheditview-class.md), 보기 문서 보기 아키텍처와 풍부한 편집 컨트롤을 사용할 수 있게 합니다.  
  
-   [CScrollView](../../mfc/reference/cscrollview-class.md)을 자동으로 스크롤 지원 보기.  
  
-   [CTreeView](../../mfc/reference/ctreeview-class.md), 뷰 문서\-뷰 아키텍처를 이용한 트리 컨트롤을 사용할 수 있게 합니다.  
  
 `CView` 클래스 라는 파생된 되는 구현 클래스도 있습니다.  **CPreviewView**를 사용 프레임 워크에서 인쇄 미리 보기를 수행 합니다.  이 클래스는 같은 단일 또는 이중 페이지 미리 보기 도구 모음에서 인쇄 미리 보기 창에 고유한 기능을 지원 하 고 확대\/축소 된 미리 보기 이미지 확대.  호출 또는 재정의할 필요가  **CPreviewView**의 멤버 함수 \(예를 들어, 인쇄 미리 보기 모드에서 편집을 지원 하려는 경우\) 인쇄 미리 보기에 대 한 자신의 인터페이스를 구현 하지 않는 경우.  사용에 대 한 자세한 내용은 `CView`를 참조 하십시오  [문서\/뷰 아키텍처](../../mfc/document-view-architecture.md) 및  [인쇄](../../mfc/printing.md).  또한 볼  [기술 참고 30](../../mfc/tn030-customizing-printing-and-print-preview.md) 인쇄 미리 보기 사용자 지정에 대 한 자세한 내용은.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CView`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [MDIDOCVW MFC 샘플](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [CSplitterWnd Class](../../mfc/reference/csplitterwnd-class.md)   
 [CDC 클래스](../../mfc/reference/cdc-class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)