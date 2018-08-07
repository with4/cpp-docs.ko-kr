---
title: CView 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CView
- AFXWIN/CView
- AFXWIN/CView::CView
- AFXWIN/CView::DoPreparePrinting
- AFXWIN/CView::GetDocument
- AFXWIN/CView::IsSelected
- AFXWIN/CView::OnDragEnter
- AFXWIN/CView::OnDragLeave
- AFXWIN/CView::OnDragOver
- AFXWIN/CView::OnDragScroll
- AFXWIN/CView::OnDrop
- AFXWIN/CView::OnDropEx
- AFXWIN/CView::OnInitialUpdate
- AFXWIN/CView::OnPrepareDC
- AFXWIN/CView::OnScroll
- AFXWIN/CView::OnScrollBy
- AFXWIN/CView::OnActivateFrame
- AFXWIN/CView::OnActivateView
- AFXWIN/CView::OnBeginPrinting
- AFXWIN/CView::OnDraw
- AFXWIN/CView::OnEndPrinting
- AFXWIN/CView::OnEndPrintPreview
- AFXWIN/CView::OnPreparePrinting
- AFXWIN/CView::OnPrint
- AFXWIN/CView::OnUpdate
dev_langs:
- C++
helpviewer_keywords:
- CView [MFC], CView
- CView [MFC], DoPreparePrinting
- CView [MFC], GetDocument
- CView [MFC], IsSelected
- CView [MFC], OnDragEnter
- CView [MFC], OnDragLeave
- CView [MFC], OnDragOver
- CView [MFC], OnDragScroll
- CView [MFC], OnDrop
- CView [MFC], OnDropEx
- CView [MFC], OnInitialUpdate
- CView [MFC], OnPrepareDC
- CView [MFC], OnScroll
- CView [MFC], OnScrollBy
- CView [MFC], OnActivateFrame
- CView [MFC], OnActivateView
- CView [MFC], OnBeginPrinting
- CView [MFC], OnDraw
- CView [MFC], OnEndPrinting
- CView [MFC], OnEndPrintPreview
- CView [MFC], OnPreparePrinting
- CView [MFC], OnPrint
- CView [MFC], OnUpdate
ms.assetid: 9cff3c56-7564-416b-b9a4-71a9254ed755
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7ff4e48bd7006c3706909d1791b82aa8cda2658
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123125"
---
# <a name="cview-class"></a>CView 클래스
사용자 정의 뷰 클래스에 대한 기본 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class AFX_NOVTABLE CView : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CView::CView](#cview)|`CView` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CView::DoPreparePrinting](#doprepareprinting)|인쇄 대화 상자를 표시 하 고 프린터 장치 컨텍스트의; 만듭니다. 재정의 하는 경우 호출 된 `OnPreparePrinting` 멤버 함수입니다.|  
|[CView::GetDocument](#getdocument)|보기와 관련 된 문서를 반환 합니다.|  
|[CView::IsSelected](#isselected)|문서 항목이 선택 되어 있는지 테스트 합니다. OLE 지원에 필요합니다.|  
|[CView::OnDragEnter](#ondragenter)|항목을 먼저 보기의 끌어 놓기 영역으로 끌 때 호출 됩니다.|  
|[CView::OnDragLeave](#ondragleave)|끌어 온된 항목 보기의 끌어 놓기 영역을 벗어나면 호출 됩니다.|  
|[CView::OnDragOver](#ondragover)|항목을 끌어 놓기 영역 보기의 위로 끌 때 호출 됩니다.|  
|[CView::OnDragScroll](#ondragscroll)|커서는 창의 스크롤 영역으로 끌어서 놓은 있는지 여부를 결정 하기 위해 호출 합니다.|  
|[CView::OnDrop](#ondrop)|뷰를 기본 처리기의 끌어 놓기 영역으로 항목 삭제 되었습니다 때 호출 됩니다.|  
|[CView::OnDropEx](#ondropex)|뷰를 기본 처리기의 끌어 놓기 영역으로 항목 삭제 되었습니다 때 호출 됩니다.|  
|[Cview:: Oninitialupdate](#oninitialupdate)|뷰 먼저 문서에 연결 된 후 호출 됩니다.|  
|[CView::OnPrepareDC](#onpreparedc)|이전에 호출의 `OnDraw` 화면 표시에 대 한 멤버 함수를 호출 또는 `OnPrint` 인쇄 또는 인쇄 미리 보기에 대 한 멤버 함수를 호출 합니다.|  
|[CView::OnScroll](#onscroll)|OLE 항목 보기의 경계를 벗어난 놓을 때 호출 됩니다.|  
|[CView::OnScrollBy](#onscrollby)|활성 내부 OLE 항목을 포함 하는 뷰를 스크롤할 때 호출 됩니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CView::OnActivateFrame](#onactivateframe)|뷰를 포함 하는 프레임 창을 활성화 되거나 비활성화 될 때 호출 됩니다.|  
|[CView::OnActivateView](#onactivateview)|뷰가 활성화 될 때 호출 됩니다.|  
|[CView::OnBeginPrinting](#onbeginprinting)|인쇄 작업 시작; 될 때 호출 리소스를 할당할 그래픽 장치 인터페이스 GDI ()를 재정의 합니다.|  
|[Cview:: Ondraw](#ondraw)|화면 디스플레이, 인쇄 또는 인쇄 미리 보기에 대 한 문서의 이미지를 렌더링 하기 위해 호출 합니다. 필요한 구현입니다.|  
|[CView::OnEndPrinting](#onendprinting)|인쇄 작업이 끝나면; 호출 GDI 리소스 할당을 취소 하려면 재정의 합니다.|  
|[CView::OnEndPrintPreview](#onendprintpreview)|미리 보기 모드 종료 될 때 호출 됩니다.|  
|[CView::OnPreparePrinting](#onprepareprinting)|문서를 인쇄 하거나 미리 볼; 호출 인쇄 대화 상자를 초기화를 재정의 합니다.|  
|[CView::OnPrint](#onprint)|인쇄 문서 페이지를 미리 볼 하거나 호출 됩니다.|  
|[CView::OnUpdate](#onupdate)|에 문서가 해당 하는 보기를 알리기 위해 호출 수정 합니다.|  
  
## <a name="remarks"></a>설명  
 뷰는 문서에 연결 하 고 문서와 사용자 간의 중개자로 작동: 보기 화면이 나 프린터에서 문서의 이미지를 렌더링 하 고 문서에 대 한 작업으로 사용자 입력 해석 합니다.  
  
 뷰에 프레임 창의 자식입니다. 둘 이상의 보기 창에의 경우 처럼 프레임 창에 공유할 수 있습니다. 뷰 클래스, 프레임 창 클래스 및 문서 클래스 간의 관계가 의해 설정 되는 `CDocTemplate` 개체입니다. 사용자의 새 창을 엽니다. 또는 기존의 분할 하는 경우 하나는 프레임 워크 새 뷰를 생성 하 고 문서에 연결 합니다.  
  
 보기를 하나의 문서에 연결할 수 있지만 문서 한 번에 연결 된 여러 뷰를 가질 수 있습니다-예를 들어 문서는 다중 문서 MDI (인터페이스) 응용 프로그램에서 여러 자식 창 또는 분할자 창에 표시 됩니다. 응용 프로그램이 지정 된 문서 유형;에 대 한 다양 한 유형의 보기를 지원할 수 있습니다. 예를 들어 워드 프로세서 프로그램 문서의 전체 텍스트 보기와 섹션 제목만 표시 하는 개요 보기를 제공할 수 있습니다. 이러한 여러 유형의 보기 창에 사용 하는 경우 단일 한 프레임 창의 별도 창 또는 별도 프레임 창에 배치할 수 있습니다.  
  
 뷰는 몇 가지 유형의 키보드 입력, 마우스 입력 또는 메뉴, 도구 모음 또는 스크롤 막대에서 끌어서 놓기, 뿐만 아니라 명령을 통해 입력 등의 입력 처리를 담당 수 있습니다. 보기는 프레임 창을 의해 전달 되는 명령을 받습니다. 뷰가 지정된 된 명령을 처리 하지는 관련된 문서에 명령을 전달 합니다. 모든 명령 대상에 같은 보기는 메시지 맵을 통해 메시지를 처리합니다.  
  
 뷰는 저장 하지 않습니다을 표시 하 고 문서의 데이터를 수정 합니다. 문서는 데이터에 대 한 필요한 세부 정보를 사용 하 여 뷰를 제공합니다. 문서의 데이터 멤버를 직접 제공 멤버 함수를 호출 하는 뷰 클래스에 대 한 문서 클래스에 보기 액세스 하도록 할 수 있습니다.  
  
 문서의 데이터가 변경 될 때 변경 내용에 대 한 책임 보기 일반적으로 호출 하는 [CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) 호출 하 여 다른 보기를 알리는 문서에 대 한 함수는 `OnUpdate` 에 대 한 멤버 함수 각 합니다. 기본 구현은 `OnUpdate` 보기의 전체 클라이언트 영역을 무효화 합니다. 문서의 수정된 부분에 매핑되는 클라이언트 영역의 영역에만 무효화 하 여 재정의할 수 있습니다.  
  
 사용 하도록 `CView`를 여기에서 클래스를 파생 하 고 구현에서 `OnDraw` 화면 표시를 수행 하는 멤버 함수입니다. 사용할 수도 있습니다 `OnDraw` 인쇄 및 인쇄 미리 보기를 수행 하려면. 프레임 워크에는 인쇄 및 문서 미리 보기에 대 한 인쇄 루프에서 처리 합니다.  
  
 스크롤 막대 메시지를 처리 하는 뷰는 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) 및 [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) 멤버 함수입니다. 스크롤 막대에서에서 메시지 처리 이러한 함수를 구현 하거나 사용할 수 있습니다는 `CView` 파생 클래스 [CScrollView](../../mfc/reference/cscrollview-class.md) 스크롤을 처리할 수 있습니다.  
  
 외에 `CScrollView`에서 파생 된 다른 9 개의 클래스를 제공 하는 Microsoft Foundation Class 라이브러리 `CView`:  
  
- [CCtrlView](../../mfc/reference/cctrlview-class.md), 문서 뷰 아키텍처 트리, 목록 및 rich edit 컨트롤의 사용을 허용 하는 뷰입니다.  
  
- [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md), 대화 상자 컨트롤에 데이터베이스 레코드를 표시 하는 뷰입니다.  
  
- [CEditView](../../mfc/reference/ceditview-class.md), 간단한 여러 줄 텍스트 편집기를 제공 하는 보기입니다. 사용할 수는 `CEditView` 문서에 대 한 뷰를 비롯 하 여 대화 상자에 컨트롤로 개체입니다.  
  
- [CFormView](../../mfc/reference/cformview-class.md), 대화 상자 컨트롤을 포함 하 고 대화 상자 템플릿 리소스를 기반으로 하는 스크롤 가능한 뷰입니다.  
  
- [CListView](../../mfc/reference/clistview-class.md), 문서-목록 컨트롤과 뷰 아키텍처의 사용을 허용 하는 뷰입니다.  
  
- [CRecordView](../../mfc/reference/crecordview-class.md), 대화 상자 컨트롤에 데이터베이스 레코드를 표시 하는 뷰입니다.  
  
- [CRichEditView](../../mfc/reference/cricheditview-class.md), 문서 뷰 아키텍처를 서식 있는 편집 컨트롤의 사용을 허용 하는 뷰입니다.  
  
- [CScrollView](../../mfc/reference/cscrollview-class.md), 자동으로 스크롤 지원을 제공 하는 뷰입니다.  
  
- [CTreeView](../../mfc/reference/ctreeview-class.md), 문서-트리 컨트롤과 뷰 아키텍처의 사용을 허용 하는 뷰입니다.  
  
 `CView` 클래스 라는 파생된 구현 클래스에 `CPreviewView`, 인쇄 미리 보기를 수행 하는 프레임 워크에서 사용 되는 합니다. 이 클래스는 단일 또는 이중 페이지 미리 보기 도구 모음과 같은 인쇄 미리 보기 창에 고유한 기능에 대 한 지원 및 확대/축소를 미리 보기 이미지 확대,입니다. 호출 하거나를 재정의할 필요가 없습니다 `CPreviewView`의 멤버 함수 (예를 들어 경우 인쇄 미리 보기 모드에서 편집을 지원 하려면) 인쇄 미리 보기에 대 한 고유한 인터페이스를 구현 하는 경우가 있습니다. 사용 하 여 대 한 자세한 내용은 `CView`, 참조 [문서/뷰 아키텍처](../../mfc/document-view-architecture.md) 및 [인쇄](../../mfc/printing.md)합니다. 또한 참조 [기술 참고 30](../../mfc/tn030-customizing-printing-and-print-preview.md) 에 대 한 자세한 내용은 인쇄 미리 보기를 사용자 지정 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CView`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="cview"></a>  CView::CView  
 `CView` 개체를 생성합니다.  
  
```  
CView();
```  
  
### <a name="remarks"></a>설명  
 새 프레임 창 개체를 만들거나 창이 분할 되어 때 프레임 워크에서는 생성자를 호출 합니다. 재정의 [OnInitialUpdate](#oninitialupdate) 멤버 함수는 문서에 연결 된 후에 뷰를 초기화할 수 있습니다.  
  
##  <a name="doprepareprinting"></a>  CView::DoPreparePrinting  
 재정의에서이 함수를 호출 [OnPreparePrinting](#onprepareprinting) 인쇄 대화 상자를 호출 하는 프린터 장치 컨텍스트를 만듭니다.  
  
```  
BOOL DoPreparePrinting(CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 *pInfo*  
 가리키는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 현재 인쇄 작업을 설명 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 인쇄 또는 인쇄 미리 보기를 시작할 수 있습니다. 0이 아닌 작업이 취소 된 경우 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 동작은 인쇄 또는 인쇄 미리 보기에 대 한 호출 되 고 되었는지 여부에 따라 다릅니다 (지정 된는 `m_bPreview` 의 멤버는 *pInfo* 매개 변수). 파일을 인쇄 하는 경우이 함수에 값을 사용 하 여 인쇄 대화 상자를 호출 하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체입니다 *pInfo* 가리키는; 함수를 만듭니다 사용자가 대화 상자를 닫은 후에 프린터 장치 컨텍스트 대화 상자에 지정 된 사용자 설정에 따라 하 고이 장치 컨텍스트를 통해 반환 된 *pInfo* 매개 변수입니다. 이 장치 컨텍스트를 사용 하 여 문서를 인쇄 합니다.  
  
 이 함수 현재 프린터 설정을;를 사용 하 여 프린터 장치 컨텍스트를 만듭니다. 파일을 미리 보려는 경우 이 장치 컨텍스트는 미리 보기 중 프린터를 시뮬레이션 하는 데 사용 됩니다.  
  
##  <a name="getdocument"></a>  CView::GetDocument  
 보기의 문서에 대 한 포인터를 가져오려면이 함수를 호출 합니다.  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CDocument](../../mfc/reference/cdocument-class.md) 보기와 연결 된 개체입니다. 뷰가 문서에 연결 되어 있지 않으면 NULL입니다.  
  
### <a name="remarks"></a>설명  
 이 문서의 멤버 함수를 호출할 수 있습니다.  
  
##  <a name="isselected"></a>  CView::IsSelected  
 지정한 문서 항목이 선택 되어 있는지 여부를 확인 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *pDocItem*  
 테스트 중인 문서 항목을 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 문서 항목이 선택 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현은 FALSE를 반환합니다. 이 함수를 사용 하 여 구현 하는 경우 재정의 [CDocItem](../../mfc/reference/cdocitem-class.md) 개체입니다. 보기 OLE 항목을 포함 하는 경우이 함수를 재정의 해야 합니다.  
  
##  <a name="onactivateframe"></a>  CView::OnActivateFrame  
 뷰를 포함 하는 프레임 창이 활성화 또는 비활성화 하는 경우 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnActivateFrame(
    UINT nState,  
    CFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 *nState*  
 프레임 창 되 고 있는지 여부를 지정 합니다. 활성화 또는 비활성화 합니다. 다음 값 중 하나일 수 있습니다.  
  
- 프레임 창 WA_INACTIVE는 비활성화 하는 중입니다.  
  
- 예를 들어 (키보드 인터페이스 창을 선택의 사용) 하 여 마우스 이외의 다른 몇 가지 메서드를 통해 프레임 창이 활성화 되 WA_ACTIVE 클릭 합니다.  
  
- 마우스 클릭 하 여 WA_CLICKACTIVE 프레임 창이 활성화 되 고  
  
 *pFrameWnd*  
 활성화할 수 있는 프레임 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 뷰와 연결 된 프레임 창이 활성화 또는 비활성화 될 때 특수 한 처리를 수행 하려는 경우이 멤버 함수를 재정의 합니다. 예를 들어 [CFormView](../../mfc/reference/cformview-class.md) 저장 하 고 포커스가 있는 컨트롤을 복원 하는 경우이 재정의 수행 합니다.  
  
##  <a name="onactivateview"></a>  CView::OnActivateView  
 뷰 활성화 되거나 비활성화 될 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnActivateView(
    BOOL bActivate,  
    CView* pActivateView,  
    CView* pDeactiveView);
```  
  
### <a name="parameters"></a>매개 변수  
 *bActivate*  
 보기를 새로 있는지 여부를 나타냅니다. 활성화 또는 비활성화 합니다.  
  
 *pActivateView*  
 활성화 되 고 view 개체를 가리킵니다.  
  
 *pDeactiveView*  
 다음은 비활성화 된 view 개체를 가리킵니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현은 활성화 되 고 보기에 포커스를 설정 합니다. 뷰 활성화 되거나 비활성화 될 때 특수 한 처리를 수행 하려는 경우이 함수를 재정의 합니다. 예를 들어 비활성 뷰에서 활성 뷰를 구별 하는 특수 한 시각적 큐를 제공 하려는 경우는 검사할는 *bActivate* 매개 변수 및 그에 따라 보기의 모양을 업데이트 합니다.  
  
 *pActivateView* 및 *pDeactiveView* 현재 보기에서 변경 되지 않은 응용 프로그램의 주 프레임 창이 활성화 될 경우 매개 변수 같은 뷰 가리키도록-예를 들어, 포커스 되는 경우 MDI 자식 창 간에 전환 하는 경우 응용 프로그램 내에서 또는 다른 뷰 대신이 하나에 다른 응용 프로그램에서 전송 합니다. 이렇게 하면 필요한 경우 다시에서 팔레트를 나타내려고 하는 데 사용할 뷰가 있습니다.  
  
 이러한 매개 변수의 차이로 때 [CFrameWnd::SetActiveView](../../mfc/reference/cframewnd-class.md#setactiveview) 무엇과 다른 보기와 라고 [CFrameWnd::GetActiveView](../../mfc/reference/cframewnd-class.md#getactiveview) 를 반환 합니다. 이 분할 창에서 가장 자주 발생합니다.  
  
##  <a name="onbeginprinting"></a>  CView::OnBeginPrinting  
 `OnPreparePrinting` 이 호출된 후 인쇄 또는 인쇄 미리 보기 작업을 시작할 때 프레임워크에서 호출됩니다.  
  
```  
virtual void OnBeginPrinting(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 *pDC*  
 프린터 장치 컨텍스트를 가리킵니다.  
  
 *pInfo*  
 가리키는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 현재 인쇄 작업을 설명 하는 구조입니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 인쇄용으로 특별히 필요한 GDI 리소스(예: 펜 또는 글꼴)를 할당하려면 이 함수를 재정의합니다. 내에서 장치 컨텍스트로 GDI 개체를 선택는 [OnPrint](#onprint) 메트릭을 사용 하는 각 페이지에 대 한 멤버 함수입니다. 동일한 view 개체를 사용하여 화면 표시와 인쇄를 모두 수행하는 경우 각 화면 표시에 필요한 GDI 리소스에 별도의 변수를 사용합니다. 이렇게 하면 인쇄하는 동안 화면을 업데이트할 수 있습니다.  
  
 또한 이 함수를 사용하여 프린터 장치 컨텍스트의 속성에 따라 초기화를 수행할 수 있습니다. 예를 들어 문서를 인쇄하는 데 필요한 페이지 수는 사용자가 인쇄 대화 상자에서 지정한 설정(예: 페이지 길이)에 따라 다를 수 있습니다. 이러한 상황에서 문서 길이 지정할 수 없습니다는 [OnPreparePrinting](#onprepareprinting) 멤버 함수의 경우에 일반적으로 이렇게 하면; 프린터 장치 컨텍스트의 만든 대화 상자 설정에 따라 때까지 기다려야 합니다. [OnBeginPrinting](#onbeginprinting) 가 제공 하는 첫 번째 재정의 가능 함수에 대 한 액세스는 [CDC](../../mfc/reference/cdc-class.md) 이 함수에서 문서 길이 설정할 수 있는 프린터 장치 컨텍스트를 나타내는 개체입니다. 이때까지 문서 길이를 지정하지 않으면 인쇄 미리 보기 중에 스크롤 막대가 표시되지 않습니다.  
  
##  <a name="ondragenter"></a>  CView::OnDragEnter  
 마우스 놓기 대상 창 영역을 스크롤할 수 없는 처음 전달 될 때 프레임 워크에서 호출 합니다.  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 *pDataObject*  
 가리키는 [COleDataObject](../../mfc/reference/coledataobject-class.md) 보기의 끌어 놓기 영역으로 끌고 있습니다.  
  
 *dwKeyState*  
 보조 키의 상태가 포함 됩니다. 이 개수에 관계 없이 다음의 조합을: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, 및 MK_RBUTTON 합니다.  
  
 *지점*  
 마우스의 현재 위치 클라이언트 영역을 기준으로 보기.  
  
### <a name="return-value"></a>반환 값  
 DROPEFFECT에서 값을 열거 형식 발생 하는 사용자는이 위치에서 개체를 삭제 하면 drop의 형식을 나타냅니다. Drop 유형의 일반적으로 가리키는 현재 키 상태에 따라 달라 집니다 *dwKeyState*합니다. Keystates DROPEFFECT 값으로의 표준 매핑을입니다.  
  
- 이 창에 DROPEFFECT_NONE 데이터 개체를 삭제할 수 없습니다.  
  
- MK_CONTROL에 대 한 DROPEFFECT_LINK &#124; MK_SHIFT 개체 및 해당 서버 간의 연결을 만듭니다.  
  
- DROPEFFECT_COPY MK_CONTROL에 대 한 삭제 된 개체의 복사본을 만듭니다.  
  
- DROPEFFECT_MOVE MK_ALT에 대 한 원본 개체를 삭제 하 고 삭제 된 개체의 복사본을 만듭니다. 이것이 일반적으로 기본 놓기 효과 보기는이 데이터 개체를 받아들일 수입니다.  
  
 자세한 내용은 MFC 고급 개념 샘플을 참조 하십시오. [OCLIENT](../../visual-cpp-samples.md)합니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 아무 작업도 수행 하지 DROPEFFECT_NONE 반환 하는 것입니다.  
  
 이후 호출을 위해 준비 하려면이 함수를 재정의 [OnDragOver](#ondragover) 멤버 함수입니다. 나중에 사용할이 이번에 데이터 개체에서 필요한 모든 데이터를 검색할는 `OnDragOver` 멤버 함수입니다. 보기는 사용자 시각적 피드백을 제공 하 여이 이번에도 업데이트 되어야 합니다. 자세한 내용은 문서 참조 [끌어서 놓기: 놓기 대상 구현](../../mfc/drag-and-drop-implementing-a-drop-target.md)합니다.  
  
##  <a name="ondragleave"></a>  CView::OnDragLeave  
 해당 창에 대 한 유효한 놓기 영역 밖으로 마우스를 이동할 때 프레임 워크에서 끌기 작업 중 호출 합니다.  
  
```  
virtual void OnDragLeave();
```  
  
### <a name="remarks"></a>설명  
 현재 보기 동안 수행 된 모든 작업을 정리 하는 경우이 함수를 재정의 [OnDragEnter](#ondragenter) 또는 [OnDragOver](#ondragover) 개체를 끌어서 놓을 때 시각적 사용자 피드백을 제거 하는 등 .  
  
##  <a name="ondragover"></a>  CView::OnDragOver  
 놓기 대상 창 위로 마우스를 이동할 때 프레임 워크에서 끌기 작업 중 호출 합니다.  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 *pDataObject*  
 가리키는 [COleDataObject](../../mfc/reference/coledataobject-class.md) 놓기 대상 위로 끄는 합니다.  
  
 *dwKeyState*  
 보조 키의 상태가 포함 됩니다. 이 개수에 관계 없이 다음의 조합을: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, 및 MK_RBUTTON 합니다.  
  
 *지점*  
 보기 클라이언트 영역을 기준으로 현재 마우스 위치를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 DROPEFFECT에서 값을 열거 형식 발생 하는 사용자는이 위치에서 개체를 삭제 하면 drop의 형식을 나타냅니다. Drop 유형의 현재 키 상태에 표시 된 대로 종종 따라 *dwKeyState*합니다. Keystates DROPEFFECT 값으로의 표준 매핑을입니다.  
  
- 이 창에 DROPEFFECT_NONE 데이터 개체를 삭제할 수 없습니다.  
  
- MK_CONTROL에 대 한 DROPEFFECT_LINK &#124; MK_SHIFT 개체 및 해당 서버 간의 연결을 만듭니다.  
  
- DROPEFFECT_COPY MK_CONTROL에 대 한 삭제 된 개체의 복사본을 만듭니다.  
  
- DROPEFFECT_MOVE MK_ALT에 대 한 원본 개체를 삭제 하 고 삭제 된 개체의 복사본을 만듭니다. 이 일반적으로 기본 놓기 효과 뷰 데이터 개체를 수용할 수 합니다.  
  
 자세한 내용은 MFC 고급 개념 샘플을 참조 하십시오. [OCLIENT](../../visual-cpp-samples.md)합니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 아무 작업도 수행 하지 DROPEFFECT_NONE 반환 하는 것입니다.  
  
 끌기 작업 중 사용자 시각적 피드백을 제공 하려면이 함수를 재정의 합니다. 이 함수를 호출 지속적으로, 이후 그 안에 포함 된 모든 코드 최적화 해야 최대한 많이 있습니다. 자세한 내용은 문서 참조 [끌어서 놓기: 놓기 대상 구현](../../mfc/drag-and-drop-implementing-a-drop-target.md)합니다.  
  
##  <a name="ondragscroll"></a>  CView::OnDragScroll  
 호출 하기 전에 프레임 워크에서 호출 [OnDragEnter](#ondragenter) 또는 [OnDragOver](#ondragover) 스크롤 영역에 점이 있는지 여부를 확인 하려면.  
  
```  
virtual DROPEFFECT OnDragScroll(
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwKeyState*  
 보조 키의 상태가 포함 됩니다. 이 개수에 관계 없이 다음의 조합을: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, 및 MK_RBUTTON 합니다.  
  
 *지점*  
 화면에 대해를 픽셀 단위로 커서의 위치를 포함합니다.  
  
### <a name="return-value"></a>반환 값  
 DROPEFFECT에서 값을 열거 형식 발생 하는 사용자는이 위치에서 개체를 삭제 하면 drop의 형식을 나타냅니다. Drop 유형의 일반적으로 가리키는 현재 키 상태에 따라 달라 집니다 *dwKeyState*합니다. Keystates DROPEFFECT 값으로의 표준 매핑을입니다.  
  
- 이 창에 DROPEFFECT_NONE 데이터 개체를 삭제할 수 없습니다.  
  
- MK_CONTROL에 대 한 DROPEFFECT_LINK &#124; MK_SHIFT 개체 및 해당 서버 간의 연결을 만듭니다.  
  
- DROPEFFECT_COPY MK_CONTROL에 대 한 삭제 된 개체의 복사본을 만듭니다.  
  
- DROPEFFECT_MOVE MK_ALT에 대 한 원본 개체를 삭제 하 고 삭제 된 개체의 복사본을 만듭니다.  
  
- DROPEFFECT_SCROLL 끌기 스크롤 작업이 수행 되려고 또는 대상 보기에서 발생 했음을 나타냅니다.  
  
 자세한 내용은 MFC 고급 개념 샘플을 참조 하십시오. [OCLIENT](../../visual-cpp-samples.md)합니다.  
  
### <a name="remarks"></a>설명  
 이 이벤트에 대 한 특별 한 동작을 제공 하려는 경우이 함수를 재정의 합니다. 기본 구현은 각 창의 테두리 내 기본 스크롤 영역으로 커서를 끌 때 windows를 자동으로 스크롤됩니다. 자세한 내용은 문서 참조 [끌어서 놓기: 놓기 대상 구현](../../mfc/drag-and-drop-implementing-a-drop-target.md)합니다.  
  
##  <a name="ondraw"></a>  Cview:: Ondraw  
 문서의 이미지를 렌더링 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDraw(CDC* pDC) = 0;  
```  
  
### <a name="parameters"></a>매개 변수  
 *pDC*  
 문서의 이미지 렌더링에 사용할 장치 컨텍스트를 가리킵니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크는 화면 표시, 인쇄 및 인쇄 미리 보기를 수행 하려면이 함수를 호출 하 고 각각의 경우에는 다른 장치 컨텍스트를 전달 합니다. 기본 구현은 없습니다.  
  
 문서 뷰를 표시 하려면이 함수를 재정의 해야 합니다. 사용 하 여 그래픽 장치 인터페이스 (GDI) 호출을 만들 수 있습니다는 [CDC](../../mfc/reference/cdc-class.md) 가리키는 개체는 *pDC* 매개 변수입니다. 그리기 전에 장치 컨텍스트로 GDI 리소스 예: 펜 또는 글꼴을 선택할 수 있으며 다음 나중에 해제 수 있습니다. 종종 그리기 코드가 장치 독립적인; 수 있습니다. 즉, 해당 장치의 종류 표시 이미지에 대 한 정보가 필요 하지 않습니다.  
  
 을 최적화 하기 위해 그리기 호출의 [RectVisible](../../mfc/reference/cdc-class.md#rectvisible) 지정 된 사각형을 그릴 것인지 여부를 알아보려면 장치 컨텍스트의 멤버 함수입니다. 일반적인 화면 표시 및 인쇄와 구분 하기 위해 해야 할 경우 호출 된 [IsPrinting](../../mfc/reference/cdc-class.md#isprinting) 장치 컨텍스트의 멤버 함수입니다.  
  
##  <a name="ondrop"></a>  CView::OnDrop  
 데이터 개체를 유효한 놓기 대상 위에 놓을 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnDrop(
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 ' pDataObject *  
 가리키는 [COleDataObject](../../mfc/reference/coledataobject-class.md) 놓기 대상으로 끌어입니다.  
  
 *dropEffect*  
 사용자가 요청 하는 놓기 효과입니다.  
  
- DROPEFFECT_COPY 삭제 되는 데이터 개체의 복사본을 만듭니다.  
  
- DROPEFFECT_MOVE 현재 마우스 위치에 데이터 개체를 이동합니다.  
  
- DROPEFFECT_LINK은 데이터 개체와 해당 서버 간의 링크를 만듭니다.  
  
 *지점*  
 보기 클라이언트 영역을 기준으로 현재 마우스 위치를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 드롭다운에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 아무 작업도 수행 하 고 FALSE를 반환 합니다.  
  
 보기의 클라이언트 영역으로 OLE 놓기 효과 구현 하려면이 함수를 재정의 합니다. 데이터 개체를 통해 검사할 수 있습니다 *pDataObject* 클립보드 데이터에 대 한 형식 및 데이터 삭제 지정된 된 지점에 있습니다.  
  
> [!NOTE]
>  프레임 워크를 재정의 하는 경우이 함수를 호출 하지 않습니다 [OnDropEx](#ondropex) 이 뷰 클래스에 있습니다.  
  
##  <a name="ondropex"></a>  CView::OnDropEx  
 데이터 개체를 유효한 놓기 대상 위에 놓을 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual DROPEFFECT OnDropEx(
    COleDataObject* pDataObject,  
    DROPEFFECT dropDefault,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 *pDataObject*  
 가리키는 [COleDataObject](../../mfc/reference/coledataobject-class.md) 놓기 대상으로 끌어입니다.  
  
 *dropDefault*  
 현재 키 상태에 따라 기본 놓기 작업에 대 한 사용자를 선택 하는 효과입니다. DROPEFFECT_NONE 수도 있습니다. 끌어서 놓기 작업 결과 주의 섹션에 설명 되어 있습니다.  
  
 *드롭다운 목록*  
 목록에서 지 원하는 놓기 소스 끌어서 놓기 작업 결과입니다. 비트 OR를 사용 하 여 놓기 효과 값을 결합할 수 있습니다 ( **&#124;**) 작업입니다. 끌어서 놓기 작업 결과 주의 섹션에 설명 되어 있습니다.  
  
 *지점*  
 보기 클라이언트 영역을 기준으로 현재 마우스 위치를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 위치에서 삭제 시도에서 발생 하는 놓기 효과 *가리킨*합니다. 이 가리키는 값 중 하나 여야 합니다 *dropEffectList*합니다. 끌어서 놓기 작업 결과 주의 섹션에 설명 되어 있습니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 더미 (-1)를 나타내는 값을 프레임 워크에서 호출 하는 다음 다시 돌아와 아무 작업도 수행 하는 것은 [OnDrop](#ondrop) 처리기입니다.  
  
 오른쪽 마우스 단추 끌어서 놓기 효과 구현 하려면이 함수를 재정의 합니다. 오른쪽 마우스 단추 끌어서 놓기 마우스 오른쪽 단추를 놓을 때 선택 항목의 메뉴를 표시 일반적으로 합니다.  
  
 재정의가 `OnDropEx` 오른쪽 마우스 단추에 대해 쿼리해야 합니다. 호출할 수 있습니다 [GetKeyState](http://msdn.microsoft.com/library/windows/desktop/ms646301) 에서 오른쪽 마우스 단추 상태를 저장 하거나 프로그램 [OnDragEnter](#ondragenter) 처리기입니다.  
  
-   마우스 오른쪽 단추 다운 된 경우 재정의 놓기 소스에서 지 원하는 놓기 효과 제공 하는 팝업 메뉴가 표시 됩니다.  
  
    -   검사 *드롭 목록* 놓기 소스에서 지 원하는 끌어서 놓기 작업 결과 확인 하려면. 팝업 메뉴에서 이러한 작업에만 사용 하도록 설정 합니다.  
  
    -   사용 하 여 [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996) 에 따라 기본 동작을 설정 하려면 *dropDefault*합니다.  
  
    -   마지막으로, 팝업 메뉴에서 사용자 선택 항목으로 표시 된 작업을 수행 합니다.  
  
-   마우스 오른쪽 단추를 아래쪽 없으면 재정의 처리 해야이 표준 삭제 요청으로 합니다. 에 지정 된 놓기 효과 사용 하 여 *dropDefault*합니다. 재정의 나타내기 위해 더미 값 (-1)를 반환할 수 있습니다 또는 `OnDrop` 이 놓기 작업을 처리 합니다.  
  
 사용 하 여 *pDataObject* 를 검사 하 여 `COleDataObject` 지정된 된 지점에서 삭제 클립보드 데이터 형식 및 데이터입니다.  
  
 끌어서 놓기 작업 결과 놓기 작업과 관련 된 동작에 설명 합니다. 끌어서 놓기 작업 결과의 다음 목록을 참조 하세요.  
  
- DROPEFFECT_NONE A 놓기 것은 허용 되지 않습니다.  
  
- DROPEFFECT_COPY 복사 작업을 수행 합니다.  
  
- DROPEFFECT_MOVE 이동 작업이 수행 됩니다.  
  
- 원래 데이터를 전송 된 데이터에서 DROPEFFECT_LINK A 링크를 설정할 수 합니다.  
  
- DROPEFFECT_SCROLL 끌기 스크롤 작업이 수행 되려고 하거나 대상에서 발생 했음을 나타냅니다.  
  
 기본 메뉴 명령을 설정에 대 한 자세한 내용은 참조 하십시오. [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996) Windows sdk에서 및 [CMenu::GetSafeHmenu](../../mfc/reference/cmenu-class.md#getsafehmenu) 이 볼륨에 있습니다.  
  
##  <a name="onendprinting"></a>  CView::OnEndPrinting  
 문서가 인쇄 하거나 미리 볼 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnEndPrinting(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 *pDC*  
 프린터 장치 컨텍스트를 가리킵니다.  
  
 *pInfo*  
 가리키는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 현재 인쇄 작업을 설명 하는 구조입니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 이 함수에 할당 된 GDI 리소스를 재정의 하는 [OnBeginPrinting](#onbeginprinting) 멤버 함수입니다.  
  
##  <a name="onendprintpreview"></a>  CView::OnEndPrintPreview  
 사용자가 인쇄 미리 보기 모드를 종료할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnEndPrintPreview(
    CDC* pDC,  
    CPrintInfo* pInfo,  
    POINT point,  
    CPreviewView* pView);
```  
  
### <a name="parameters"></a>매개 변수  
 *pDC*  
 프린터 장치 컨텍스트를 가리킵니다.  
  
 *pInfo*  
 가리키는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 현재 인쇄 작업을 설명 하는 구조입니다.  
  
 *지점*  
 미리 보기 모드에 마지막 표시 된 페이지에 위치를 지정 합니다.  
  
 *pView*  
 미리 보기에 사용 되는 뷰 개체를 가리킵니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현에서는 호출 하 여 [OnEndPrinting](#onendprinting) 주 프레임 창을 인쇄 미리 보기 이전 상태로 시작 된 멤버 함수 및 복원 합니다. 미리 보기 모드 종료 될 때 특수 한 처리를 수행 하려면이 함수를 재정의 합니다. 예를 들어 일반적인 표시 모드를 전환 하려면 미리 보기 모드에서 문서에 사용자의 위치를 유지 하려는 경우 스크롤할 수 있습니다에 설명 된 위치는 *가리킨* 매개 변수 및 `m_nCurPage` 는 의구성원`CPrintInfo` 구조체는 *pInfo* 매개 변수를 가리킵니다.  
  
 기본 클래스 버전을 항상 호출 `OnEndPrintPreview` 에서 함수의 끝에 일반적으로 재정의 합니다.  
  
##  <a name="oninitialupdate"></a>  Cview:: Oninitialupdate  
 보기에는 문서에 처음 연결 되었으나 처음 표시 되는 보기 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현에서는 호출 하는 [OnUpdate](#onupdate) 힌트 정보 없이 멤버 함수 (즉, 0에 대 한 기본값을 사용 하는 *lHint* 매개 변수 및 NULL에 대 한는  *pHint* 매개 변수). 문서에 대 한 정보를 필요로 하는 한 번만 초기화를 수행 하려면이 함수를 재정의 합니다. 예를 들어 응용 프로그램에 문서 고정 크기의 경우 보기의 스크롤 제한 되는 문서 크기에 따라 초기화를이 함수를 사용할 수 있습니다. 사용 하 여 응용 프로그램의 가변 크기 문서를 지 원하는 경우 [OnUpdate](#onupdate) 하기 위해 스크롤 업데이트 제한 될 때마다 변경 내용을 문서화 합니다.  
  
##  <a name="onpreparedc"></a>  CView::OnPrepareDC  
 전에 프레임 워크에서 호출는 [OnDraw](#ondraw) 화면 표시 및 하기 전에 멤버 함수가 호출 되는 [OnPrint](#onprint) 인쇄 또는 인쇄 미리 보기 기간 동안 각 페이지에 대 한 멤버 함수를 호출 합니다.  
  
```  
virtual void OnPrepareDC(
    CDC* pDC,  
    CPrintInfo* pInfo = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *pDC*  
 문서의 이미지 렌더링에 사용할 장치 컨텍스트를 가리킵니다.  
  
 *pInfo*  
 가리키는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 경우 현재 인쇄 작업을 설명 하는 구조 `OnPrepareDC` 인쇄 또는 인쇄 미리 보기;에 대 한 호출 되는 `m_nCurPage` 멤버 인쇄할 페이지를 지정 합니다. 이 매개 변수는 NULL 경우 `OnPrepareDC` 화면 표시에 대 한 호출 되 고 있습니다.  
  
### <a name="remarks"></a>설명  
 화면 표시에 대 한 함수를 호출 하는 경우이 함수의 기본 구현은 아무 작업도 수행 합니다. 그러나이 함수는 파생된 클래스에서 재정의와 같은 [CScrollView](../../mfc/reference/cscrollview-class.md), 장치 컨텍스트의 특성을 조정 하려면 재정의 맨 앞에 기본 클래스 구현을 항상 호출 해야 따라서 합니다.  
  
 기본 구현은 검사에 저장 된 페이지 정보를 인쇄에 대 한 함수를 호출 하면는 *pInfo* 매개 변수입니다. 문서 길이 지정 하지 `OnPrepareDC` 문서 1 페이지 짜리를 따르며 한 페이지를 인쇄 후 인쇄 루프를 중지 합니다. 설정 하 여 인쇄 루프를 중지 하는 함수는 `m_bContinuePrinting` FALSE로는 구조체의 멤버입니다.  
  
 재정의 `OnPrepareDC` 다음과 같은 원인에 대 한 합니다.  
  
-   지정된 된 페이지에 대 한 필요에 따라 장치 컨텍스트의 특성을 조정 합니다. 예를 들어 매핑 모드 또는 기타 장치 컨텍스트의 특성을 설정 해야 할 경우이 함수에서 수행할.  
  
-   인쇄 때 페이지 번호 매기기를 수행 합니다. 사용 하 여 인쇄를 시작할 때 문서 길이 지정 하는 일반적으로 [OnPreparePrinting](#onprepareprinting) 멤버 함수입니다. 그러나 알 수 없는 경우 사전에 시간 문서 (예를 들어 경우 데이터베이스에서 레코드 수를 지정 하지 않은 인쇄)를 재정의 `OnPrepareDC` 를 인쇄 하는 동안 문서 끝에 대 한 테스트 합니다. 가 더 이상 문서를 인쇄 하는 경우 설정의 `m_bContinuePrinting` 의 멤버는 `CPrintInfo` 구조를 FALSE로 합니다.  
  
-   이스케이프 코드에서 페이지 단위로 프린터로 보냅니다. 이스케이프 코드에서 보낼 `OnPrepareDC`, 호출의 `Escape` 의 멤버 함수는 *pDC* 매개 변수입니다.  
  
 기본 클래스 버전을 호출 `OnPrepareDC` 재정의의 시작 부분에 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#183](../../mfc/codesnippet/cpp/cview-class_1.cpp)]  
  
##  <a name="onprepareprinting"></a>  CView::OnPreparePrinting  
 문서는 인쇄 하거나 미리 보기 전에 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnPreparePrinting(CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 *pInfo*  
 가리키는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 현재 인쇄 작업을 설명 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 인쇄를 시작 하려면 0이 아닌 인쇄 작업이 취소 된 경우 0입니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 아무 작업도 수행하지 않습니다.  
  
 인쇄 및 인쇄 미리 보기를 사용 하도록 설정 하려면이 함수를 재정의 해야 합니다. 호출 된 [DoPreparePrinting](#doprepareprinting) 전달 되는 멤버 함수는 *pInfo* 매개 변수를 다음; 반환 값을 반환 `DoPreparePrinting` 인쇄 대화 상자를 표시 하 고 프린터 장치 컨텍스트를 만듭니다. 기본값 이외의 값이 포함 된 인쇄 대화 상자를 초기화 하려는 경우의 멤버에 값을 할당 *pInfo*합니다. 예를 들어 문서 길이 알고 있는 경우 값을 전달는 [SetMaxPage](../../mfc/reference/cprintinfo-structure.md#setmaxpage) 의 멤버 함수 *pInfo* 호출 하기 전에 `DoPreparePrinting`합니다. 이 값에에서 표시 됩니다: 인쇄 대화 상자에서 범위 부분의 상자입니다.  
  
 `DoPreparePrinting` 미리 보기 작업에 대 한 인쇄 대화 상자를 표시 하지 않습니다. 인쇄 작업에 대 한 인쇄 대화 상자를 무시 하려는 경우를 확인 하는 `m_bPreview` 의 구성원 *pInfo* FALSE이 고 전달 하기 전에 TRUE로 설정 `DoPreparePrinting`; 나중에 FALSE로 다시 설정 합니다.  
  
 에 대 한 액세스를 필요로 하는 초기화를 수행 해야 하는 경우는 `CDC` (예를 들어 문서 길이 지정 하기 전에 페이지 크기를 알고 있어야 하는 경우), 프린터 장치 컨텍스트를 나타내는 개체를 재정의 `OnBeginPrinting` 멤버 함수입니다.  
  
 값을 설정 하려는 경우는 `m_nNumPreviewPages` 또는 `m_strPageDesc` 의 멤버는 *pInfo* 매개 변수를 호출한 후 이렇게 `DoPreparePrinting`합니다. `DoPreparePrinting` 멤버 함수 집합 `m_nNumPreviewPages` 는 응용 프로그램에서 찾을 값입니다. INI 파일을 설정 하 고 `m_strPageDesc` 기본값으로 합니다.  
  
### <a name="example"></a>예  
  재정의 `OnPreparePrinting` 호출 `DoPreparePrinting` 재정의에서 프레임 워크는 인쇄 대화 상자를 표시 하 고 프린터 DC를 만듭니다.  
  
 [!code-cpp[NVC_MFCDocView#184](../../mfc/codesnippet/cpp/cview-class_2.cpp)]  
  
 문서를 포함 하는 페이지 수를 알고 있는 경우 최대 페이지에서 설정할 `OnPreparePrinting` 호출 하기 전에 `DoPreparePrinting`합니다. 프레임 워크의 인쇄 대화 상자 "to" 상자에 최대 페이지 수를 표시 됩니다.  
  
 [!code-cpp[NVC_MFCDocView#185](../../mfc/codesnippet/cpp/cview-class_3.cpp)]  
  
##  <a name="onprint"></a>  CView::OnPrint  
 인쇄 문서 페이지를 미리 볼 또는 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnPrint(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 *pDC*  
 프린터 장치 컨텍스트를 가리킵니다.  
  
 *pInfo*  
 가리키는 `CPrintInfo` 현재 인쇄 작업을 설명 하는 구조입니다.  
  
### <a name="remarks"></a>설명  
 이 함수 호출 직후 프레임 워크 인쇄 하려는 각 페이지에 대 한 호출에서 [OnPrepareDC](#onpreparedc) 멤버 함수입니다. 인쇄 페이지 지정는 `m_nCurPage` 의 멤버는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체입니다 *pInfo* 를 가리킵니다. 기본 구현 호출은 [OnDraw](#ondraw) 멤버 함수 프린터 장치 컨텍스트를 전달 합니다.  
  
 다음과 같은 이유로 인해이 함수를 재정의 합니다.  
  
-   다중 페이지 문서 인쇄 수 있도록 합니다. 현재 인쇄 중인 페이지에 해당 하는 문서의 부분만을 렌더링 합니다. 사용 중인 경우 `OnDraw` 렌더링을 수행 하려면 조정할 수 문서의 적절 한 부분만 인쇄 되도록 뷰포트 원본입니다.  
  
-   인쇄 된 이미지 (즉, 응용 프로그램이 아닌 경우 WYSIWYG) 화면 이미지에서 다르게 보일 수 있습니다. 프린터 장치 컨텍스트를 전달 하는 대신 `OnDraw`, 화면에 표시 되지 않음 특성을 사용 하 여 이미지를 렌더링 하는 장치 컨텍스트를 사용 합니다.  
  
     GDI 리소스를 화면 표시에 사용 하지 않는 인쇄 해야 그리기 전에 장치 컨텍스트로 선택 하 고 나중에 선택 취소 합니다. 이러한 GDI 리소스에 할당 되는 [OnBeginPrinting](#onbeginprinting) 에 출시 및 [OnEndPrinting](#onendprinting)합니다.  
  
-   머리글 또는 바닥글을 구현 하 합니다. 계속 사용할 수 있습니다 `OnDraw` 에 인쇄할 수 있는 영역을 제한 하 여 렌더링 작업을 수행 하 합니다.  
  
 `m_rectDraw` 의 멤버는 *pInfo* 논리 단위에 있는 페이지의 인쇄 가능한 영역을 설명 하는 매개 변수입니다.  
  
 호출 하지 마십시오 `OnPrepareDC` 의 재정의에서 `OnPrint`; 프레임 워크 호출 `OnPrepareDC` 호출 하기 전에 자동으로 `OnPrint`합니다.  
  
### <a name="example"></a>예  
 다음은 재정의 된에 대 한 스 켈 레 톤 `OnPrint` 함수:  
  
 [!code-cpp[NVC_MFCDocView#186](../../mfc/codesnippet/cpp/cview-class_4.cpp)]  
  
 또 다른 예에 대 한 참조 [CRichEditView::PrintInsideRect](../../mfc/reference/cricheditview-class.md#printinsiderect)합니다.  
  
##  <a name="onscroll"></a>  CView::OnScroll  
 스크롤 여부를 확인 하기 위해 프레임 워크에서 호출 하는 것은 가능 합니다.  
  
```  
virtual BOOL OnScroll(
    UINT nScrollCode,  
    UINT nPos,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *nScrollCode*  
 사용자 지정 하는 스크롤 막대 코드 요청을 스크롤의입니다. 이 매개 변수는 두 부분으로 구성 됩니다: 가로 스크롤 발생 유형의 결정 하는 낮은 순서 바이트 및 세로 스크롤 발생의 유형을 결정 하는 상위 바이트:  
  
- SB_BOTTOM를 아래쪽으로 스크롤.  
  
- 한 줄 아래로 SB_LINEDOWN 스크롤합니다.  
  
- 한 줄 위로 SB_LINEUP 스크롤합니다.  
  
- 한 페이지 아래로 SB_PAGEDOWN 스크롤합니다.  
  
- 한 페이지 위로 SB_PAGEUP 스크롤합니다.  
  
- SB_THUMBTRACK 끌기 상자 지정 된 위치로 스크롤합니다. 현재 위치에 지정 된 *nPos*합니다.  
  
- 맨 위로 이동 SB_TOP 스크롤입니다.  
  
 *nPos*  
 스크롤 막대 코드가 SB_THUMBTRACK; 이면 현재 스크롤 상자 위치를 포함 합니다. 그렇지 않으면 사용 되지 않습니다. 초기 스크롤 범위에 따라 *nPos* 음수가 될 수 있습니다 및로 캐스팅 해야는 **int** 필요한 경우.  
  
 *bDoScroll*  
 실제로 지정 된 스크롤 동작을 수행 해야 하는지 여부를 결정 합니다. True 인 경우, 다음 스크롤 언로드할지; false 인 경우, 다음 스크롤 발생 하지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 경우 *bDoScroll* 은 TRUE이 고 보기를 실제로 스크롤한, 돌아 오세요 0이 아니고, 그렇지 않으면 0입니다. 경우 *bDoScroll* FALSE, 다음을 반환 하는 경우 반환 값은 *bDoScroll* 실제로 두면 스크롤 하는 경우에 TRUE 되었습니다.  
  
### <a name="remarks"></a>설명  
 한 가지 경우가이 함수를 프레임 워크에서 호출 *bDoScroll* 뷰 스크롤 막대 메시지를 받을 때 TRUE로 설정 합니다. 이 경우 보기를 스크롤하여 실제로 채워야 합니다. 다른 경우에서이 함수를 호출 *bDoScroll* 스크롤 실제로 수행 하기 전에 놓기 대상의 자동 스크롤 영역에 처음 OLE 항목을 끌 때 FALSE로 설정 합니다. 이 경우 하지 실제로 스크롤하여 채워야 보기.  
  
##  <a name="onscrollby"></a>  CView::OnScrollBy  
 사용자 보기의 현재 테두리에 대해 OLE 항목을 끌어 또는 세로 또는 가로 스크롤 막대를 조작 하 여 문서의 현재 보기는 다음 영역을 볼 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnScrollBy(
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *sizeScroll*  
 가로 및 세로로 스크롤의 픽셀 수입니다.  
  
 *bDoScroll*  
 보기의 스크롤 발생 하는지 여부를 결정 합니다. TRUE 이면 다음 스크롤 수행이 됩니다. false 인 경우, 다음 스크롤 발생 하지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 보기; 스크롤할 수 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 파생된 클래스에서 보기를 사용자 요청 하 고 필요에 따라 새 영역을 업데이트 한 다음 방향으로 스크롤할 수 있는지 여부를 확인 합니다. 이 함수는 자동으로 호출 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) 및 [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) 스크롤 실제 요청을 수행할 수 있습니다.  
  
 이 메서드의 기본 구현 보기를 변경 되지 않지만 뷰에 호출 되지 않으면에서 움직이지 것입니다는 `CScrollView`-클래스를 파생 합니다.  
  
 문서 너비 또는 높이가 32767 픽셀을 초과 하기 때문에 실패 합니다 32767 스크롤할 `OnScrollBy` 으로 잘못 된 호출 *sizeScroll* 인수입니다.  
  
##  <a name="onupdate"></a>  CView::OnUpdate  
 보기의 문서가 수정 되었습니다; 후에 프레임 워크에서 호출 합니다. 이 함수를 호출 하 [CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) 하 고 이러한 수정 내용을 반영 하도록 표시를 업데이트 보기를 허용 합니다.  
  
```  
virtual void OnUpdate(
    CView* pSender,  
    LPARAM lHint,  
    CObject* pHint);
```  
  
### <a name="parameters"></a>매개 변수  
 *pSender*  
 문서를 수정 하는 뷰를 가리키는 모든 뷰는 업데이트할 경우 null입니다.  
  
 *lHint*  
 수정 작업에 대 한 정보를 포함합니다.  
  
 *pHint*  
 수정 작업에 대 한 정보를 저장 하는 개체를 가리킵니다.  
  
### <a name="remarks"></a>설명  
 기본 구현에 의해 호출 또한은 [OnInitialUpdate](#oninitialupdate)합니다. 기본 구현은 다음 WM_PAINT 메시지를 받을 때 그리기에 대 한 표시 전체 클라이언트 영역을 무효화 합니다. 문서의 수정된 부분에 매핑되는 해당 영역을 업데이트 하려는 경우이 함수를 재정의 합니다. 이 작업을 수행 하려면 힌트 매개 변수를 사용 하 여 수정 하는 방법에 대 한 정보를 전달 해야 합니다.  
  
 사용 하도록 *lHint*, 특별 한 힌트 값, 일반적으로 비트 마스크 또는 열거 형식을 정의 하 고 문서를 다음이 값 중 하나를 전달 합니다. 사용 하도록 *pHint*에서 힌트 클래스를 파생 [CObject](../../mfc/reference/cobject-class.md) 문서를 재정의 하는 경우 힌트 개체;에 대 한 포인터를 전달 하 고 `OnUpdate`를 사용 하 여는 [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) 힌트 개체의 런타임 형식을 확인 하려면 멤버 함수입니다.  
  
 일반적으로 수행 하지 말아야에서 직접 그리는 모든 `OnUpdate`합니다. 대신, 업데이트 해야 하는 영역 장치 좌표를 설명 하는 사각형을 결정 이 사각형을 전달 [CWnd::InvalidateRect](../../mfc/reference/cwnd-class.md#invalidaterect)합니다. 이 인해 다음에 적용 되려면 그리기는 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) 메시지를 수신 합니다.  
  
 경우 *lHint* 0 및 *pHint* 가 NULL 인 문서 제네릭 업데이트 알림을 보냈습니다. 뷰는 일반 업데이트 알림을 수신 하는 경우 또는 힌트 디코딩할 수 없는 경우 전체 클라이언트 영역을 무효화 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 MDIDOCVW](../../visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)   
 [CSplitterWnd 클래스](../../mfc/reference/csplitterwnd-class.md)   
 [CDC 클래스](../../mfc/reference/cdc-class.md)   
 [CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument 클래스](../../mfc/reference/cdocument-class.md)
