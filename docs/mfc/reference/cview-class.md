---
title: "CView 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- views [C++], view classes
- multiple views
- CView class
- document/view architecture
- input, and view class
- MDI [C++], view windows
- print preview, view windows
- windows [C++], views
- child windows, views
- frame windows [C++], views
- user input [C++], interpreting through view class
ms.assetid: 9cff3c56-7564-416b-b9a4-71a9254ed755
caps.latest.revision: 25
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ce5100a9ee4a1c20df04f79f0c8cd645ae3afce7
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

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
|[CView::DoPreparePrinting](#doprepareprinting)|인쇄 대화 상자를 표시 하 고 프린터 장치 컨텍스트를 만듭니다. 재정의 하는 경우 호출 된 `OnPreparePrinting` 멤버 함수입니다.|  
|[CView::GetDocument](#getdocument)|보기와 관련 된 문서를 반환 합니다.|  
|[CView::IsSelected](#isselected)|문서 항목이 선택 되어 있는지 테스트 합니다. OLE 지원에 필요합니다.|  
|[CView::OnDragEnter](#ondragenter)|항목을 먼저 보기의 끌어 놓기 영역으로 끌 때 호출 됩니다.|  
|[CView::OnDragLeave](#ondragleave)|끌어 온된 항목 보기의 끌어 놓기 영역을 벗어나면 호출 됩니다.|  
|[CView::OnDragOver](#ondragover)|보기의 끌어 놓기 영역 위로 항목을 끌 때 호출 됩니다.|  
|[CView::OnDragScroll](#ondragscroll)|커서를 창 스크롤 영역으로 끌 있는지 여부를 확인 하려면 호출 됩니다.|  
|[CView::OnDrop](#ondrop)|기본 처리기 보기의 끌어 놓기 영역에는 항목이 삭제 되었습니다 때 호출 됩니다.|  
|[CView::OnDropEx](#ondropex)|기본 처리기 보기의 끌어 놓기 영역에는 항목이 삭제 되었습니다 때 호출 됩니다.|  
|[Cview:: Oninitialupdate](#oninitialupdate)|뷰는 문서에 먼저 연결 된 후 호출 됩니다.|  
|[CView::OnPrepareDC](#onpreparedc)|호출 하기 전에 `OnDraw` 화면 표시에 대 한 멤버 함수를 호출 또는 `OnPrint` 인쇄 또는 인쇄 미리 보기에 대 한 멤버 함수를 호출 합니다.|  
|[CView::OnScroll](#onscroll)|OLE 항목 보기의 경계 초과 놓을 때 호출 됩니다.|  
|[CView::OnScrollBy](#onscrollby)|활성 내부 OLE 항목을 포함 하는 뷰가 스크롤될 때 호출 됩니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CView::OnActivateFrame](#onactivateframe)|뷰를 포함 하는 프레임 창 활성화 되거나 비활성화 될 때 호출 됩니다.|  
|[CView::OnActivateView](#onactivateview)|뷰가 활성화 될 때 호출 됩니다.|  
|[CView::OnBeginPrinting](#onbeginprinting)|는 인쇄 작업을 시작 될 때 호출 리소스를 할당 그래픽 장치 인터페이스 (GDI) 재정의 합니다.|  
|[Cview:: Ondraw](#ondraw)|화면 표시, 인쇄 또는 인쇄 미리 보기에 대 한 문서의 이미지를 렌더링 하기 위해 호출. 필요한 구현입니다.|  
|[CView::OnEndPrinting](#onendprinting)|인쇄 작업이 끝나면; 호출 GDI 리소스 할당을 취소 하려면 재정의 합니다.|  
|[CView::OnEndPrintPreview](#onendprintpreview)|미리 보기 모드 종료 될 때 호출 됩니다.|  
|[CView::OnPreparePrinting](#onprepareprinting)|문서는 인쇄 하거나 미리 볼; 전에 호출 합니다. 인쇄 대화 상자를 초기화 하려면 재정의 합니다.|  
|[CView::OnPrint](#onprint)|인쇄 문서 페이지를 미리 하거나 호출 됩니다.|  
|[CView::OnUpdate](#onupdate)|문서가 해당 하는 보기에 알리기 위해 호출 수정 합니다.|  
  
## <a name="remarks"></a>주의  
 뷰는 문서에 연결 되어 있고 문서와 사용자 간의 중개자 역할을: 보기 화면이 나 프린터에서 문서의 이미지를 렌더링 하 고 사용자 입력은 문서에 대 한 작업으로 해석 합니다.  
  
 뷰는 프레임 창의 자식. 둘 이상의 보기가 프레임 창 분할자 창의 경우 처럼를 공유할 수 있습니다. 뷰 클래스, 프레임 창 클래스를 및 문서 클래스 간의 관계에서 설정 되는 `CDocTemplate` 개체입니다. 사용자는 새 창이 표시 하거나 기존의 분할 때, 프레임 워크 새 뷰를 생성 한 문서에 연결 합니다.  
  
 뷰 하나의 문서에 연결할 수 있지만 문서는 한 번에 연결 된 뷰를 여러 개 있을 수 있습니다-예를 들어 문서 분할자 창에서 또는 다중 문서 MDI (인터페이스) 응용 프로그램에서 여러 자식 창에 표시 됩니다. 응용 프로그램이 지정된 된 문서 유형;에 대 한 여러 유형의 보기를 지원할 수 있습니다. 예를 들어 워드 프로세서 프로그램 문서의 전체 텍스트 보기와 섹션 제목에만 표시 하는 개요 보기를 제공 될 수 있습니다. 이러한 여러 유형의 보기 분할자 창을 사용 하는 경우 별도 창이 단일 프레임 창 또는 별도 프레임 창에 배치할 수 있습니다.  
  
 뷰는 여러 종류의 키보드 입력, 마우스 입력 또는 메뉴나 도구 모음, 스크롤 막대의 입력을 통해 명령 뿐 아니라 끌어서 놓기, 같은 입력을 처리 하는 일을 담당 수 있습니다. 보기의 프레임 창에 의해 전달 되는 명령을 수신 합니다. 뷰의 지정된 된 명령을 처리 하지는 관련된 문서에 명령을 전달 합니다. 마찬가지로 모든 명령은 대상 보기 메시지 맵을 통해 메시지를 처리합니다.  
  
 뷰는 저장 하지 않는를 표시 하 고 문서의 데이터를 수정 합니다. 문서는 데이터에 대 한 필요한 세부 정보를 사용 하 여 뷰를 제공합니다. 문서 데이터 멤버를 직접 제공 멤버 함수를 호출 하는 뷰 클래스에 대 한 문서 클래스에 보기 액세스 하도록 할 수 있습니다.  
  
 문서 데이터 변경 될 때 변경 내용을 담당 보기 일반적으로 호출 하는 [CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) 함수를 호출 하 여 다른 모든 보기를 알리는 문서에 대 한는 `OnUpdate` 각각에 대해 멤버 함수입니다. 기본 구현은 `OnUpdate` 보기의 전체 클라이언트 영역을 무효화 합니다. 문서의 수정 된 부분에 매핑되는 클라이언트 영역의 영역에만 무효화 하는 것을 재정의할 수 있습니다.  
  
 사용 하 여 `CView`에서 클래스를 파생 하 고 구현 된 `OnDraw` 화면 표시를 수행 하는 멤버 함수입니다. 사용할 수도 있습니다 `OnDraw` 인쇄 및 인쇄 미리 보기를 수행 하 합니다. 프레임 워크는 인쇄 및 문서 미리 보기에 대 한 인쇄 루프를 처리 합니다.  
  
 스크롤 막대 메시지를 처리 하는 뷰는 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) 및 [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) 멤버 함수입니다. 스크롤 막대에서에서 메시지 처리 이러한 함수를 구현할 수도 있고 사용할 수 있습니다는 `CView` 파생 클래스 [CScrollView](../../mfc/reference/cscrollview-class.md) 스크롤을 처리할 수 있습니다.  
  
 외에 `CScrollView`에서 파생 된 다른&9; 개 클래스를 제공 하는 Microsoft Foundation Class 라이브러리 `CView`:  
  
- [CCtrlView](../../mfc/reference/cctrlview-class.md), 문서 뷰 아키텍처 트리, 목록 및 rich edit 컨트롤의 사용을 허용 하는 보기입니다.  
  
- [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md), 대화 상자 컨트롤에 데이터베이스 레코드를 표시 하는 보기입니다.  
  
- [CEditView](../../mfc/reference/ceditview-class.md), 여러 줄로 된 간단한 텍스트 편집기를 제공 하는 보기입니다. 사용할 수는 `CEditView` 문서에 대 한 뷰를 비롯 하 여 대화 상자에 컨트롤 개체입니다.  
  
- [CFormView](../../mfc/reference/cformview-class.md), 대화 상자 컨트롤을 포함 하 고 대화 상자 템플릿 리소스에 따라는 스크롤 가능한 뷰입니다.  
  
- [CListView](../../mfc/reference/clistview-class.md), 문서-목록 컨트롤과 뷰 아키텍처의 사용을 허용 하는 보기입니다.  
  
- [CRecordView](../../mfc/reference/crecordview-class.md), 대화 상자 컨트롤에 데이터베이스 레코드를 표시 하는 보기입니다.  
  
- [CRichEditView](../../mfc/reference/cricheditview-class.md), 문서 뷰 아키텍처를 서식 있는 편집 컨트롤의 사용을 허용 하는 보기입니다.  
  
- [CScrollView](../../mfc/reference/cscrollview-class.md), 자동으로 스크롤 지원을 제공 하는 보기입니다.  
  
- [CTreeView](../../mfc/reference/ctreeview-class.md), 문서 뷰 아키텍처 트리 컨트롤의 사용을 허용 하는 보기입니다.  
  
 `CView` 클래스 라는 파생 된 구현 클래스에 **CPreviewView**, 인쇄 미리 보기를 수행 하는 프레임 워크에서 사용 되는 합니다. 이 클래스는 단일 또는 이중 페이지 미리 보기 도구 모음과 같은 인쇄 미리 보기 창에 고유한 기능에 대 한 지원 및 확대/축소, 미리 보기 이미지를 확대,입니다. 호출 하거나 재정의할 필요가 없습니다 **CPreviewView**의 멤버 함수 (예를 들어 하려는 경우 인쇄 미리 보기 모드에서 편집을 지원 하기 위해) 인쇄 미리 보기에 대 한 자체 인터페이스를 구현 하는 경우가 있습니다. 사용 하 여 대 한 자세한 내용은 `CView`, 참조 [문서/뷰 아키텍처](../../mfc/document-view-architecture.md) 및 [인쇄](../../mfc/printing.md)합니다. 또한 참조 [기술 참고 30](../../mfc/tn030-customizing-printing-and-print-preview.md) 에 대 한 자세한 내용은 인쇄 미리 보기 사용자 지정 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CView`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="cview"></a>CView::CView  
 `CView` 개체를 생성합니다.  
  
```  
CView();
```  
  
### <a name="remarks"></a>주의  
 새로운 프레임 창을 만들거나 창이 분할 되어 때 생성자를 호출 하는 프레임 워크. 재정의 [OnInitialUpdate](#oninitialupdate) 멤버 함수를 문서에 연결 된 후에 뷰를 초기화 합니다.  
  
##  <a name="doprepareprinting"></a>CView::DoPreparePrinting  
 재정의에서이 함수를 호출 [OnPreparePrinting](#onprepareprinting) 인쇄 대화 상자를 호출 하 여 프린터 장치 컨텍스트를 만듭니다.  
  
```  
BOOL DoPreparePrinting(CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `pInfo`  
 가리키는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 현재 인쇄 작업을 설명 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 인쇄 또는 인쇄 미리 보기를 시작할 수 하면 0이 아니고 작업이 취소 된 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 동작은 인쇄 또는 인쇄 미리 보기에 대 한 호출 되는 여부에 따라 다릅니다 (지정 된는 **m_bPreview** 의 멤버는 `pInfo` 매개 변수). 파일을 인쇄 하는 경우이 함수에서 값을 사용 하 여 인쇄 대화 상자를 호출 하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체 `pInfo` 가리키는; 함수를 사용자 지정 대화 상자에서 및를 통해이 장치 컨텍스트를 반환 하는 설정에 따라 프린터 장치 컨텍스트에 만듭니다 사용자가 대화 상자를 닫은 후에 `pInfo` 매개 변수입니다. 이 장치 컨텍스트를 사용 하 여 문서를 인쇄 합니다.  
  
 이 함수를 현재 프린터 설정을;를 사용 하 여 프린터 장치 컨텍스트에 만듭니다 파일은 미리 보는 경우 이 장치 컨텍스트는 미리 보기 중에 프린터를 시뮬레이션 하는 데 사용 됩니다.  
  
##  <a name="getdocument"></a>CView::GetDocument  
 보기의 문서에 대 한 포인터를 가져오려면이 함수를 호출 합니다.  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CDocument](../../mfc/reference/cdocument-class.md) 보기와 연결 된 개체입니다. **NULL** 뷰는 문서에 연결 되지 않은 경우.  
  
### <a name="remarks"></a>주의  
 이 문서의 멤버 함수를 호출할 수 있습니다.  
  
##  <a name="isselected"></a>CView::IsSelected  
 지정된 된 문서 항목 선택 되어 있는지 확인 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDocItem`  
 테스트 중인 문서 항목을 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 문서 항목을 선택 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현에서는이 함수의 반환 **FALSE**합니다. 이 함수를 사용 하 여 선택을 구현 하는 경우 재정의 [CDocItem](../../mfc/reference/cdocitem-class.md) 개체입니다. 보기 OLE 항목을 포함 하는 경우이 함수를 재정의 해야 합니다.  
  
##  <a name="onactivateframe"></a>CView::OnActivateFrame  
 프레임 창 보기를 포함 하는 활성화 또는 비활성화 하는 경우에 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnActivateFrame(
    UINT nState,  
    CFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `nState`  
 프레임 창 되 고 있는지 여부를 지정 합니다. 활성화 또는 비활성화 합니다. 다음 값 중 하나일 수 있습니다.  
  
- **WA_INACTIVE** 프레임 창은 비활성화 하는 중입니다.  
  
- **WA_ACTIVE** 프레임 창은 예를 들어 (창을 선택 하는 키보드 인터페이스 사용) 하 여 마우스 클릭 아닌 다른 몇 가지 메서드를 통해 활성화 되 고 있습니다.  
  
- **WA_CLICKACTIVE** 프레임 창은 마우스 클릭으로 활성화 되 고  
  
 `pFrameWnd`  
 활성화할 수 있는 프레임 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 프레임 창 보기와 관련 된 활성화 되거나 비활성화 될 때 특수 처리를 수행 하려는 경우이 멤버 함수를 재정의 합니다. 예를 들어 [CFormView](../../mfc/reference/cformview-class.md) 저장 하 고 포커스가 있는 컨트롤을 복원 하는 경우이 재정의 수행 합니다.  
  
##  <a name="onactivateview"></a>CView::OnActivateView  
 뷰는 활성화 또는 비활성화 하는 경우 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnActivateView(
    BOOL bActivate,  
    CView* pActivateView,  
    CView* pDeactiveView);
```  
  
### <a name="parameters"></a>매개 변수  
 `bActivate`  
 보기를 새로 있는지 여부를 나타냅니다. 활성화 또는 비활성화 합니다.  
  
 `pActivateView`  
 활성화 되 고 view 개체를 가리킵니다.  
  
 `pDeactiveView`  
 다음은 비활성화 된 view 개체를 가리킵니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현은 활성화 되 고 보기에 포커스를 설정 합니다. 뷰 활성화 되거나 비활성화 될 때 특수 처리를 수행 하려는 경우이 함수를 재정의 합니다. 예를 들어 비활성 보기에서 현재 보기를 구분 하는 특수 한 시각적 큐를 제공 하려는 경우 사용자는 검사는 `bActivate` 매개 변수 및 그에 따라 보기의 모양을 업데이트 합니다.  
  
 `pActivateView` 및 `pDeactiveView` 응용 프로그램의 주 프레임 창의 현재 보기에서 변경 되지 않고 활성화 된 경우 매개 변수는 동일한 보기를 가리킨-예를 들어 MDI 자식 창 사이에서 전환 하는 경우 응용 프로그램 내에서 또는 다른 뷰 대신이 엔터티는 다른 응용 프로그램에서 포커스가 전송 되 고 있습니다. 따라서 필요한 경우 다시 해당 팔레트를 실현 하는 뷰를 수 있습니다.  
  
 이러한 매개 변수 다를 때 [CFrameWnd::SetActiveView](../../mfc/reference/cframewnd-class.md#setactiveview) 어떤 다른 보기를 사용 하 여 호출 됩니다 [CFrameWnd::GetActiveView](../../mfc/reference/cframewnd-class.md#getactiveview) 를 반환 합니다. 이 분할 창에서 가장 자주 발생합니다.  
  
##  <a name="onbeginprinting"></a>CView::OnBeginPrinting  
 `OnPreparePrinting` 이 호출된 후 인쇄 또는 인쇄 미리 보기 작업을 시작할 때 프레임워크에서 호출됩니다.  
  
```  
virtual void OnBeginPrinting(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 프린터 장치 컨텍스트를 가리킵니다.  
  
 `pInfo`  
 가리키는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 현재 인쇄 작업을 설명 하는 구조입니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 인쇄용으로 특별히 필요한 GDI 리소스(예: 펜 또는 글꼴)를 할당하려면 이 함수를 재정의합니다. 내에서 해당 장치 컨텍스트에 GDI 개체를 선택 된 [OnPrint](#onprint) 를 사용 하는 각 페이지에 대 한 멤버 함수입니다. 동일한 view 개체를 사용하여 화면 표시와 인쇄를 모두 수행하는 경우 각 화면 표시에 필요한 GDI 리소스에 별도의 변수를 사용합니다. 이렇게 하면 인쇄하는 동안 화면을 업데이트할 수 있습니다.  
  
 또한 이 함수를 사용하여 프린터 장치 컨텍스트의 속성에 따라 초기화를 수행할 수 있습니다. 예를 들어 문서를 인쇄하는 데 필요한 페이지 수는 사용자가 인쇄 대화 상자에서 지정한 설정(예: 페이지 길이)에 따라 다를 수 있습니다. 이러한 상황에서 문서 길이 지정할 수 없습니다는 [OnPreparePrinting](#onprepareprinting) 멤버 함수에 있는 경우 일반적으로 필요 하 고 프린터 장치 컨텍스트의 만든 대화 상자 설정에 따라 될 때까지 대기 해야 합니다. [OnBeginPrinting](#onbeginprinting) 가 제공 하는 첫 번째 재정의 가능 함수에 대 한 액세스는 [CDC](../../mfc/reference/cdc-class.md) 이 함수에서 문서 길이 설정할 수 있는 프린터 장치 컨텍스트를 나타내는 개체입니다. 이때까지 문서 길이를 지정하지 않으면 인쇄 미리 보기 중에 스크롤 막대가 표시되지 않습니다.  
  
##  <a name="ondragenter"></a>CView::OnDragEnter  
 마우스 놓기 대상 창의 스크롤할 수 없는 영역을 처음 실행 하는 경우 프레임 워크에서 호출 합니다.  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDataObject`  
 가리키는 [COleDataObject](../../mfc/reference/coledataobject-class.md) 보기의 끌어 놓기 영역으로 끌어 온 합니다.  
  
 `dwKeyState`  
 보조 키의 상태를 포함합니다. 다음 수 만큼의 조합입니다.: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, 및 **MK_RBUTTON**합니다.  
  
 `point`  
 마우스의 현재 위치는 클라이언트 영역을 기준으로 보기.  
  
### <a name="return-value"></a>반환 값  
 값은 `DROPEFFECT` 열거 형식으로, 사용자는이 위치에서 개체를 삭제 하는 경우 발생 하는 drop의 유형을 나타냅니다. Drop 유형의 일반적으로 나타낸 현재 키 상태에 따라 달라 집니다 `dwKeyState`합니다. 표준에 keystates 매핑을 `DROPEFFECT` 값:  
  
- `DROPEFFECT_NONE`이 창에서 데이터 개체를 삭제할 수 없습니다.  
  
- `DROPEFFECT_LINK`에 대 한 **MK_CONTROL | MK_SHIFT** 개체 및 해당 서버 간의 연결을 만듭니다.  
  
- `DROPEFFECT_COPY`에 대 한 **MK_CONTROL** 삭제 된 개체의 복사본을 만듭니다.  
  
- `DROPEFFECT_MOVE`에 대 한 **MK_ALT** 삭제 된 개체의 복사본을 만들고 원래 개체를 삭제 합니다. 이 일반적으로 기본 놓기 효과 경우 뷰는이 데이터 개체를 사용할 수 있습니다.  
  
 자세한 내용은 MFC 고급 개념 샘플을 참조 하십시오. [OCLIENT](../../visual-cpp-samples.md)합니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 아무 작업도 수행 하 고 반환 하는 것 `DROPEFFECT_NONE`합니다.  
  
 재정의에 대 한 이후 호출을 준비 하려면이 함수는 [OnDragOver](#ondragover) 멤버 함수입니다. 이 이번에는 나중에 사용할 수 있는 데이터 개체에서 필요한 모든 데이터를 검색할는 `OnDragOver` 멤버 함수입니다. 보기는 사용자 시각적 피드백을 제공할이 이번에도 업데이트 되어야 합니다. 자세한 내용은 문서를 참조 하십시오. [끌어서 놓기: 놓기 대상 구현](../../mfc/drag-and-drop-implementing-a-drop-target.md)합니다.  
  
##  <a name="ondragleave"></a>CView::OnDragLeave  
 해당 창에 대 한 유효한 놓기 영역 밖으로 마우스를 이동할 때 프레임 워크에서 끌기 작업 중 호출 합니다.  
  
```  
virtual void OnDragLeave();
```  
  
### <a name="remarks"></a>주의  
 현재 보기 중 수행 된 모든 작업을 정리 해야 할 경우이 함수를 재정의 [OnDragEnter](#ondragenter) 또는 [OnDragOver](#ondragover) 개체를 끌어서 놓을 때 시각적 사용자 피드백을 제거 하는 등 호출 합니다.  
  
##  <a name="ondragover"></a>CView::OnDragOver  
 놓기 대상 창 위로 마우스를 이동할 때 프레임 워크에서 끌기 작업 중 호출.  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDataObject`  
 가리키는 [COleDataObject](../../mfc/reference/coledataobject-class.md) 놓기 대상 위로 끄는 합니다.  
  
 `dwKeyState`  
 보조 키의 상태를 포함합니다. 다음 수 만큼의 조합입니다.: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, 및 **MK_RBUTTON**합니다.  
  
 `point`  
 보기 클라이언트 영역을 기준으로 현재 마우스 위치를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 값은 `DROPEFFECT` 열거 형식으로, 사용자는이 위치에서 개체를 삭제 하는 경우 발생 하는 drop의 유형을 나타냅니다. Drop 유형의 종종에 따라 달라 집니다 현재 키 상태에 표시 된 대로 `dwKeyState`합니다. 표준에 keystates 매핑을 `DROPEFFECT` 값:  
  
- `DROPEFFECT_NONE`이 창에서 데이터 개체를 삭제할 수 없습니다.  
  
- `DROPEFFECT_LINK`에 대 한 **MK_CONTROL | MK_SHIFT** 개체 및 해당 서버 간의 연결을 만듭니다.  
  
- `DROPEFFECT_COPY`에 대 한 **MK_CONTROL** 삭제 된 개체의 복사본을 만듭니다.  
  
- `DROPEFFECT_MOVE`에 대 한 **MK_ALT** 삭제 된 개체의 복사본을 만들고 원래 개체를 삭제 합니다. 이 일반적으로 기본 놓기 효과 경우 뷰는 데이터 개체를 사용할 수 있습니다.  
  
 자세한 내용은 MFC 고급 개념 샘플을 참조 하십시오. [OCLIENT](../../visual-cpp-samples.md)합니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 아무 작업도 수행 하 고 반환 하는 것 `DROPEFFECT_NONE`합니다.  
  
 끌기 작업 중 사용자 시각적 피드백을 제공 하려면이 함수를 재정의 합니다. 이 함수는 계속 해 서 호출 됩니다, 이후 내에 포함 된 모든 코드 최적화 해야 최대한 많이 있습니다. 자세한 내용은 문서를 참조 하십시오. [끌어서 놓기: 놓기 대상 구현](../../mfc/drag-and-drop-implementing-a-drop-target.md)합니다.  
  
##  <a name="ondragscroll"></a>CView::OnDragScroll  
 호출 하기 전에 프레임 워크에서 호출 [OnDragEnter](#ondragenter) 또는 [OnDragOver](#ondragover) 스크롤 영역에는 지점 인지 여부를 확인 합니다.  
  
```  
virtual DROPEFFECT OnDragScroll(
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwKeyState`  
 보조 키의 상태를 포함합니다. 다음 수 만큼의 조합입니다.: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, 및 **MK_RBUTTON**합니다.  
  
 `point`  
 화면을 기준으로 픽셀 단위로 커서의 위치를 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 값은 `DROPEFFECT` 열거 형식으로, 사용자는이 위치에서 개체를 삭제 하는 경우 발생 하는 drop의 유형을 나타냅니다. Drop 유형의 일반적으로 나타낸 현재 키 상태에 따라 달라 집니다 `dwKeyState`합니다. 표준에 keystates 매핑을 `DROPEFFECT` 값:  
  
- `DROPEFFECT_NONE`이 창에서 데이터 개체를 삭제할 수 없습니다.  
  
- `DROPEFFECT_LINK`에 대 한 **MK_CONTROL | MK_SHIFT** 개체 및 해당 서버 간의 연결을 만듭니다.  
  
- `DROPEFFECT_COPY`에 대 한 **MK_CONTROL** 삭제 된 개체의 복사본을 만듭니다.  
  
- `DROPEFFECT_MOVE`에 대 한 **MK_ALT** 삭제 된 개체의 복사본을 만들고 원래 개체를 삭제 합니다.  
  
- `DROPEFFECT_SCROLL`끌기 스크롤 발생 하려고 하거나 대상 보기에서 수행 되지 않는 나타냅니다.  
  
 자세한 내용은 MFC 고급 개념 샘플을 참조 하십시오. [OCLIENT](../../visual-cpp-samples.md)합니다.  
  
### <a name="remarks"></a>주의  
 이 이벤트에 대 한 특별 한 동작을 제공 하려는 경우이 함수를 재정의 합니다. 기본 구현에서는 커서의 각 창 테두리 내부에 기본 스크롤 영역 안으로 끌 때 자동으로 windows를 스크롤합니다. 자세한 내용은 문서를 참조 하십시오. [끌어서 놓기: 놓기 대상 구현](../../mfc/drag-and-drop-implementing-a-drop-target.md)합니다.  
  
##  <a name="ondraw"></a>Cview:: Ondraw  
 문서의 이미지를 렌더링 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDraw(CDC* pDC) = 0;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 문서의 이미지를 렌더링 하는 데 사용할 장치 컨텍스트를 가리킵니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크에는 화면 표시, 인쇄 및 인쇄 미리 보기를 수행 하려면이 함수를 호출 하 고 각각의 경우에서 다른 장치 컨텍스트를 전달 합니다. 기본 구현은 없습니다.  
  
 문서 보기를 표시 하려면이 함수를 재정의 해야 합니다. 사용 하 여 그래픽 장치 인터페이스 (GDI) 호출을 수행할 수 있습니다는 [CDC](../../mfc/reference/cdc-class.md) 가리키는 개체는 `pDC` 매개 변수입니다. 그리기 전에 장치 컨텍스트에 GDI 리소스의 예: 펜 또는 글꼴을 선택할 수 있으며 다음 나중에 해제. 종종 그리기 코드가 장치 독립적인; 수 있습니다. 즉, 클래스 장치 종류에 이미지를 표시 하는 방법에 대 한 정보가 필요 하지 않습니다.  
  
 호출 그리기를 최적화 하는 [RectVisible](../../mfc/reference/cdc-class.md#rectvisible) 지정 된 사각형을 그릴 것인지 여부를 확인 하려면 장치 컨텍스트의 멤버 함수입니다. 일반적인 화면 표시 및 인쇄를 구분 해야 하는 경우 호출 된 [IsPrinting](../../mfc/reference/cdc-class.md#isprinting) 장치 컨텍스트의 멤버 함수입니다.  
  
##  <a name="ondrop"></a>CView::OnDrop  
 유효한 놓기 대상 위에 데이터 개체를 놓을 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual BOOL OnDrop(
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDataObject`  
 가리키는 [COleDataObject](../../mfc/reference/coledataobject-class.md) 를 놓기 대상으로 끌어 놓으면입니다.  
  
 `dropEffect`  
 사용자가 요청한 놓기 효과입니다.  
  
- `DROPEFFECT_COPY`삭제 되는 데이터 개체의 복사본을 만듭니다.  
  
- `DROPEFFECT_MOVE`현재 마우스 위치에 데이터 개체를 이동합니다.  
  
- `DROPEFFECT_LINK`데이터 개체와 해당 서버 간의 링크를 만듭니다.  
  
 `point`  
 보기 클라이언트 영역을 기준으로 현재 마우스 위치를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 드롭다운에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 없으며 반환 **FALSE**합니다.  
  
 보기의 클라이언트 영역으로 OLE 놓기의 효과 구현 하려면이 함수를 재정의 합니다. 데이터 개체를 통해 검사할 수 `pDataObject` 클립보드 데이터에 대 한 형식 및 데이터 삭제 지정된 된 지점에 있습니다.  
  
> [!NOTE]
>  프레임 워크를 재정의 하는 경우이 함수를 호출 하지 않습니다 [OnDropEx](#ondropex) 이 뷰 클래스에 있습니다.  
  
##  <a name="ondropex"></a>CView::OnDropEx  
 유효한 놓기 대상 위에 데이터 개체를 놓을 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual DROPEFFECT OnDropEx(
    COleDataObject* pDataObject,  
    DROPEFFECT dropDefault,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDataObject`  
 가리키는 [COleDataObject](../../mfc/reference/coledataobject-class.md) 를 놓기 대상으로 끌어 놓으면입니다.  
  
 `dropDefault`  
 현재 키 상태를 기반으로 기본 놓기 작업에 대 한 사용자가 선택 하는 효과입니다. 수도 `DROPEFFECT_NONE`합니다. 끌어서 놓기 작업 결과 주의 섹션에 설명 되어 있습니다.  
  
 `dropList`  
 목록 놓기 원본에서 지 원하는 끌어서 놓기 작업 결과입니다. 비트 OR를 사용 하 여 놓기 효과 값을 결합할 수 있습니다 ( **|**) 작업입니다. 끌어서 놓기 작업 결과 주의 섹션에 설명 되어 있습니다.  
  
 `point`  
 보기 클라이언트 영역을 기준으로 현재 마우스 위치를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 위치에서 삭제 시도가에서 발생 하는 놓기 효과 `point`합니다. 로 표시 된 값 중 하나 이어야 합니다 *dropEffectList*합니다. 끌어서 놓기 작업 결과 주의 섹션에 설명 되어 있습니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 아무 작업도 수행 하 고 dummy (-1)를 나타내는 값을 프레임 워크 호출 하는 반환 하는 것은 [OnDrop](#ondrop) 처리기입니다.  
  
 오른쪽 마우스 단추로 끌어서 놓기 효과 구현 하려면이 함수를 재정의 합니다. 오른쪽 마우스 단추로 끌어서 놓기 마우스 오른쪽 단추를 놓을 때 선택 항목의 메뉴를 표시 일반적으로 합니다.  
  
 재정의 `OnDropEx` 마우스 오른쪽 단추를 쿼리해야 합니다. 호출할 수 있습니다 [GetKeyState](http://msdn.microsoft.com/library/windows/desktop/ms646301) 에서 오른쪽 마우스 단추 상태를 저장 하거나 프로그램 [OnDragEnter](#ondragenter) 처리기입니다.  
  
-   마우스 오른쪽 단추 다운 된 경우 재정의 놓기 소스에서 지 원하는 끌어서 놓기 작업 결과 제공 하는 팝업 메뉴가 표시 되어야 합니다.  
  
    -   검사 `dropList` 놓기 소스에서 지 원하는 끌어서 놓기 작업 결과 확인 하려면. 팝업 메뉴에서 이러한 작업에만 사용 하도록 설정 합니다.  
  
    -   사용 하 여 [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996) 에 따라 기본 동작을 설정 하려면 `dropDefault`합니다.  
  
    -   마지막으로, 팝업 메뉴에서 사용자 선택에 의해 표시 된 작업을 수행 합니다.  
  
-   마우스 오른쪽 단추를 아래쪽 없으면 재정의 처리 해야이 표준 삭제 요청으로 합니다. 에 지정 된 놓기 효과 사용 하 여 `dropDefault`합니다. 재정의 함을 나타내려면 더미 값 (-1)을 반환할 수 또는 `OnDrop` 이 놓기 작업을 처리 합니다.  
  
 사용 하 여 `pDataObject` 검사 하는 `COleDataObject` 클립보드 데이터에 대 한 형식 및 데이터 삭제 지정된 된 지점에 있습니다.  
  
 끌어서 놓기 작업 결과 놓기 작업과 관련 된 작업에 설명 합니다. 끌어서 놓기 작업 결과의 다음 목록을 참조 합니다.  
  
- `DROPEFFECT_NONE`감소 하는 것은 허용 되지 않습니다.  
  
- `DROPEFFECT_COPY`복사 작업이 수행 됩니다.  
  
- `DROPEFFECT_MOVE`이동 작업이 수행 됩니다.  
  
- `DROPEFFECT_LINK`원래 데이터를 삭제 된 데이터에서 링크를 설정할 수 합니다.  
  
- `DROPEFFECT_SCROLL`끌기 스크롤 이루어진다는 것 또는 대상에서 발생을 나타냅니다.  
  
 기본 메뉴 명령을 설정에 대 한 자세한 내용은 참조 하십시오. [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 및 [CMenu::GetSafeHmenu](../../mfc/reference/cmenu-class.md#getsafehmenu) 이 볼륨에 있습니다.  
  
##  <a name="onendprinting"></a>CView::OnEndPrinting  
 문서 인쇄 했거나 미리 후 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnEndPrinting(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 프린터 장치 컨텍스트를 가리킵니다.  
  
 `pInfo`  
 가리키는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 현재 인쇄 작업을 설명 하는 구조입니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 에 할당 된 GDI 리소스를 해제 하려면이 함수를 재정의 하는 [OnBeginPrinting](#onbeginprinting) 멤버 함수입니다.  
  
##  <a name="onendprintpreview"></a>CView::OnEndPrintPreview  
 사용자가 인쇄 미리 보기 모드를 벗어나면 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnEndPrintPreview(
    CDC* pDC,  
    CPrintInfo* pInfo,  
    POINT point,  
    CPreviewView* pView);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 프린터 장치 컨텍스트를 가리킵니다.  
  
 `pInfo`  
 가리키는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 현재 인쇄 작업을 설명 하는 구조입니다.  
  
 `point`  
 마지막 미리 보기 모드에 표시 된 페이지에 지정 합니다.  
  
 `pView`  
 미리 보기에 사용 되는 뷰 개체를 가리킵니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현에서는 호출 하는 [OnEndPrinting](#onendprinting) 인쇄 미리 보기 이전 상태로 주 프레임 창에 시작 된 멤버 함수에 복원 합니다. 미리 보기 모드 종료 될 때 특수 한 처리를 수행 하려면이 함수를 재정의 합니다. 예를 들어, 미리 보기 모드에서 일반적인 표시 모드를 전환 하는 경우 문서에서 사용자의 위치를 유지 하려는 경우 스크롤할 수 있습니다에서 설명 하는 위치는 `point` 매개 변수 및 `m_nCurPage` 의 멤버는 `CPrintInfo` 구조체는 `pInfo` 매개 변수를 가리킵니다.  
  
 항상 기본 클래스 버전을 호출한 `OnEndPrintPreview` 에서 함수의 끝에서 일반적으로 재정의 합니다.  
  
##  <a name="oninitialupdate"></a>Cview:: Oninitialupdate  
 프레임 워크에서 뷰를 먼저 문서에 연결한 후 전에 호출 처음 표시 되는 보기.  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현에서는 호출 하는 [OnUpdate](#onupdate) 힌트 정보가 없는 멤버 함수 (즉, 0에 대 한 기본값을 사용 하는 `lHint` 매개 변수 및 **NULL** 에 대 한는 `pHint` 매개 변수). 문서에 대 한 정보를 필요로 하는 일회 초기화를 수행 하려면이 함수를 재정의 합니다. 예를 들어 응용 프로그램에 고정 크기의 문서 경우 보기의 스크롤 제한 되는 문서 크기에 따라 초기화 하이 함수를 사용할 수 있습니다. 사용 하 여 응용 프로그램에서 가변 크기의 문서를 지 원하는 경우 [OnUpdate](#onupdate) 스크롤 업데이트할 경우 때마다 문서 변경 합니다.  
  
##  <a name="onpreparedc"></a>CView::OnPrepareDC  
 이전 프레임 워크에서 호출는 [OnDraw](#ondraw) 전에 및 화면 디스플레이 대 한 멤버 함수를 호출는 [OnPrint](#onprint) 인쇄 또는 인쇄 미리 보기 중에 각 페이지에 대 한 멤버 함수를 호출 합니다.  
  
```  
virtual void OnPrepareDC(
    CDC* pDC,  
    CPrintInfo* pInfo = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 문서의 이미지를 렌더링 하는 데 사용할 장치 컨텍스트를 가리킵니다.  
  
 `pInfo`  
 가리키는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 경우 현재 인쇄 작업을 설명 하는 구조 `OnPrepareDC` 인쇄 또는 인쇄 미리 보기;에 대 한 호출 되는 `m_nCurPage` 멤버 인쇄할 페이지를 지정 합니다. 이 매개 변수는 **NULL** 경우 `OnPrepareDC` 화면 표시를 위해 호출 되 고 있습니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현은 화면 표시에 대 한 함수를 호출 하는 경우는 없습니다. 그러나이 함수는 파생된 클래스에서 재정의와 같은 [CScrollView](../../mfc/reference/cscrollview-class.md), 장치 컨텍스트의 특성을 조정 하 따라서 호출 해야 기본 클래스 구현을 재정의의 시작 부분에 있습니다.  
  
 기본 구현은 검사에 저장 된 페이지 정보를 인쇄에 대 한 함수를 호출 하면는 `pInfo` 매개 변수입니다. 문서 길이 지정 하지 `OnPrepareDC` 문서&1; 페이지 짜리를 가정 하 고 한 페이지를 인쇄 후 인쇄 루프를 중지 합니다. 설정 하 여 인쇄 루프를 중지 하는 함수는 `m_bContinuePrinting` 구조체의 멤버 **FALSE**합니다.  
  
 재정의 `OnPrepareDC` 다음과 같은 이유 때문에:  
  
-   지정된 된 페이지에 대 한 필요에 따라 장치 컨텍스트의 특성을 조정 합니다. 예를 들어 매핑 모드 또는 기타 장치 컨텍스트의 특성을 설정 해야 할 경우이 함수에서 수행 합니다.  
  
-   인쇄 하면서 페이지 매김을 수행 합니다. 사용 하 여 인쇄를 시작할 때 문서 길이 지정 일반적으로 [OnPreparePrinting](#onprepareprinting) 멤버 함수입니다. 그러나 사전에 시간 문서 (예를 들어에서 인쇄할 때 알 수 있는 레코드 수가 데이터베이스)는 알 수 없는 경우, 재정의 `OnPrepareDC` 인쇄 되 고 있지만 문서의 끝에 대 한 테스트 합니다. 가 더 이상 문서를 인쇄 하는 경우 설정의 `m_bContinuePrinting` 의 멤버는 `CPrintInfo` 구조체를 **FALSE**합니다.  
  
-   이스케이프 코드에서 페이지 단위로 프린터로 보냅니다. 이스케이프 코드를 보내도록 `OnPrepareDC`, 호출의 **이스케이프** 의 멤버 함수는 `pDC` 매개 변수입니다.  
  
 기본 클래스 버전을 호출 `OnPrepareDC` 재정의의 시작 부분에 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&183;](../../mfc/codesnippet/cpp/cview-class_1.cpp)]  
  
##  <a name="onprepareprinting"></a>CView::OnPreparePrinting  
 문서는 인쇄 하거나 미리 보기 전에 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnPreparePrinting(CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `pInfo`  
 가리키는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 현재 인쇄 작업을 설명 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 인쇄를 시작 하려면 0이 아닌 인쇄 작업이 취소 된 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 아무 작업도 수행하지 않습니다.  
  
 인쇄 및 인쇄 미리 보기를 사용 하도록 설정 하려면이 함수를 재정의 해야 합니다. 호출의 [DoPreparePrinting](#doprepareprinting) 멤버 함수에 전달 된 `pInfo` 매개 변수를 다음 해당 반환 값을 반환 `DoPreparePrinting` 인쇄 대화 상자를 표시 하 고 프린터 장치 컨텍스트를 만듭니다. 기본값 이외의 값으로 인쇄 대화 상자를 초기화 하려는 경우의 멤버에 값을 할당 `pInfo`합니다. 예를 들어 문서 길이 알고 있는 경우 값을 전달 된 [SetMaxPage](../../mfc/reference/cprintinfo-structure.md#setmaxpage) 의 멤버 함수 `pInfo` 호출 하기 전에 `DoPreparePrinting`합니다. 이 값에에서 표시 됩니다: 인쇄 대화 상자에서 범위 부분의 상자입니다.  
  
 `DoPreparePrinting`미리 보기 작업에 대 한 인쇄 대화 상자를 표시 하지 않습니다. 인쇄 작업에 대 한 인쇄 대화 상자를 무시 하려는 경우를 확인 하는 **m_bPreview** 소속 `pInfo` 는 **FALSE** 설정한 다음 **TRUE** 전달 하기 전에 `DoPreparePrinting`; 재설정 하 **FALSE** 나중에 합니다.  
  
 에 대 한 액세스를 필요로 하는 초기화를 수행 해야 하는 경우는 `CDC` (예를 들어 페이지 크기 문서 길이 지정 하기 전에 알아야 할 경우), 프린터 장치 컨텍스트를 나타내는 개체를 재정의 `OnBeginPrinting` 멤버 함수입니다.  
  
 값을 설정 하려는 경우는 **m_nNumPreviewPages** 또는 **m_strPageDesc** 의 멤버는 `pInfo` 매개 변수를 호출한 후 이렇게 `DoPreparePrinting`합니다. `DoPreparePrinting` 멤버 함수 집합 **m_nNumPreviewPages** 는 응용 프로그램에서 찾을 값입니다. INI 파일을 설정 하 고 **m_strPageDesc** 를 기본값으로 합니다.  
  
### <a name="example"></a>예제  
  재정의 `OnPreparePrinting` 호출 `DoPreparePrinting` 재정의에서 프레임 워크는 인쇄 대화 상자를 표시 하 고 프린터 DC를 만들 수 있도록 합니다.  
  
 [!code-cpp[NVC_MFCDocView #&184;](../../mfc/codesnippet/cpp/cview-class_2.cpp)]  
  
 문서를 포함 하는 페이지 수를 알고 있는 경우 최대 페이지에서 설정할 `OnPreparePrinting` 호출 하기 전에 `DoPreparePrinting`합니다. 프레임 워크는 인쇄 대화 상자 "to" 상자에 최대 페이지 수를 표시 됩니다.  
  
 [!code-cpp[NVC_MFCDocView #&185;](../../mfc/codesnippet/cpp/cview-class_3.cpp)]  
  
##  <a name="onprint"></a>CView::OnPrint  
 인쇄 문서 페이지를 미리 하거나 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnPrint(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 프린터 장치 컨텍스트를 가리킵니다.  
  
 `pInfo`  
 가리키는 `CPrintInfo` 현재 인쇄 작업을 설명 하는 구조입니다.  
  
### <a name="remarks"></a>주의  
 인쇄 하 고 각 페이지에 대 한 프레임 워크 호출한 후 즉시이 함수를 호출의 [OnPrepareDC](#onpreparedc) 멤버 함수입니다. 인쇄 페이지는 `m_nCurPage` 의 멤버는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체 `pInfo` 를 가리킵니다. 기본 구현 호출 하 여는 [OnDraw](#ondraw) 멤버 함수 프린터 장치 컨텍스트를 전달 합니다.  
  
 다음과 같은 이유 때문에이 함수를 재정의 합니다.  
  
-   다중 페이지 문서 인쇄를 허용 합니다. 현재 인쇄 중인 페이지에 해당 하는 문서 부분에만 렌더링 합니다. 사용 하는 경우 `OnDraw` 렌더링을 수행 하려면 조정할 수 있습니다 뷰포트 원본 문서의 적절 한 부분에만 인쇄 되도록 합니다.  
  
-   인쇄 된 이미지 (즉, 응용 프로그램이 아닌 경우 WYSIWYG) 화면 이미지와 다르게 보일 수 있습니다. 프린터 장치 컨텍스트를 전달 하는 대신 `OnDraw`, 장치 컨텍스트를 사용 하 여 화면에 표시 되지 않음 특성을 사용 하 여 이미지를 렌더링 합니다.  
  
     GDI 리소스를 화면 표시를 위해 사용 하지 않는 인쇄 해야 그리기 전에 장치 컨텍스트에서 선택 하 고 나중에 선택 취소 합니다. 이러한 GDI 리소스에 할당 되는 [OnBeginPrinting](#onbeginprinting) 에서 릴리스 [OnEndPrinting](#onendprinting)합니다.  
  
-   에 머리글 또는 바닥글을 구현 합니다. 사용할 수 있습니다 `OnDraw` 에 인쇄할 수 있는 영역을 제한 하 여 렌더링 작업을 수행 하 합니다.  
  
 **m_rectDraw** 의 멤버는 `pInfo` 논리 단위에 있는 페이지의 인쇄 가능한 영역을 설명 하는 매개 변수입니다.  
  
 호출 하지 마십시오 `OnPrepareDC` 의 재정의에서 `OnPrint`이며, 프레임 워크 호출 `OnPrepareDC` 호출 하기 전에 자동으로 `OnPrint`합니다.  
  
### <a name="example"></a>예제  
 다음은 재정의 된 항목에 대 한 스 켈 레 톤 `OnPrint` 함수:  
  
 [!code-cpp[NVC_MFCDocView #&186;](../../mfc/codesnippet/cpp/cview-class_4.cpp)]  
  
 또 다른 예제를 보려면 [CRichEditView::PrintInsideRect](../../mfc/reference/cricheditview-class.md#printinsiderect)합니다.  
  
##  <a name="onscroll"></a>CView::OnScroll  
 스크롤 여부를 확인 하려면 프레임 워크에서 호출 되었을 수 있습니다.  
  
```  
virtual BOOL OnScroll(
    UINT nScrollCode,  
    UINT nPos,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `nScrollCode`  
 사용자를 나타내는 스크롤 막대 코드 요청을 스크롤의입니다. 이 매개 변수는 두 부분으로 구성 됩니다: 가로 스크롤 발생의 종류를 결정 하는 하위 바이트 및 세로로 스크롤 발생의 형식을 결정 하는 상위 바이트:  
  
- **SB_BOTTOM** 아래로 스크롤합니다.  
  
- **SB_LINEDOWN** 한 줄 아래로 스크롤합니다.  
  
- **SB_LINEUP** 한 줄 위로 스크롤합니다.  
  
- **SB_PAGEDOWN** 한 페이지 아래로 스크롤합니다.  
  
- **SB_PAGEUP** 한 페이지 위로 스크롤합니다.  
  
- **SB_THUMBTRACK** 끌기 스크롤 상자에 지정 된 위치입니다. 현재 위치에 지정 된 `nPos`합니다.  
  
- **SB_TOP** 맨 위로 스크롤합니다.  
  
 `nPos`  
 스크롤 막대 코드가 현재 스크롤 상자 위치를 포함 **SB_THUMBTRACK**; 그렇지 않으면이 사용 되지 않습니다. 초기 스크롤 범위에 따라 `nPos` 음수가 될 수 있습니다 및으로 캐스팅 해야는 `int` 필요한 경우.  
  
 `bDoScroll`  
 지정한 스크롤 동작을 실제로 수행 해야 하는지 여부를 결정 합니다. 경우 **TRUE 이면** 스크롤 언로드할지; 하는 경우 다음 **FALSE**, 스크롤 발생 하지 않아야 합니다.  
  
### <a name="return-value"></a>반환 값  
 경우 `bDoScroll` 는 **TRUE** 보기를 스크롤한 실제로, 다음 0이 아니고, 그렇지 않으면 반환 하 고 0입니다. 경우 `bDoScroll` 는 **FALSE**, 하는 경우 반환 값을 반환 하는 다음 `bDoScroll` 된 **TRUE**스크롤를 실제로 필요 하지 않더라도 합니다.  
  
### <a name="remarks"></a>주의  
 한 가지 경우에 사용 하는 프레임 워크에서이 함수를 호출 `bDoScroll` 로 설정 **TRUE** 보기 scrollbar 메시지를 수신 하는 경우. 이 경우 보기를 스크롤하여 실제로 채워야 합니다. 다른 경우에서이 함수를 호출 `bDoScroll` 로 설정 **FALSE** 때 OLE 항목을 처음 끄는 놓기 대상의 자동 스크롤 영역으로 스크롤 실제로 발생 하기 전에 합니다. 이 경우 하지 실제로 스크롤하여 채워야 보기.  
  
##  <a name="onscrollby"></a>CView::OnScrollBy  
 사용자 보기의 현재 테두리에 대해 OLE 항목을 끌어 또는 세로 또는 가로 스크롤 막대를 조작 하 여 문서의 현재 보기 이외의 영역을 볼 때 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnScrollBy(
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `sizeScroll`  
 가로 및 세로로 스크롤의 픽셀 수입니다.  
  
 `bDoScroll`  
 스크롤 보기의 발생 여부를 결정 합니다. 경우 **TRUE 이면** 스크롤 작업 발생 하는 경우, 다음 **FALSE**, 다음 스크롤 발생 하지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 보기; 스크롤할 수 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 파생된 클래스에서 보기를 사용자 요청 되 고 필요한 경우 새 영역을 업데이트 한 다음 방향으로 스크롤할 수 있는지 여부를 확인 합니다. 이 함수는 자동으로 호출 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) 및 [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) 스크롤 실제 요청을 수행할 수 있습니다.  
  
 이 메서드의 기본 구현은 보기를 변경 되지 않지만 보기 호출 하지 않는 경우에 움직이지 것입니다는 `CScrollView`-클래스를 파생 합니다.  
  
 문서 너비 또는 높이 32767 픽셀을 초과 하는 경우 32767 스크롤할 못하여 `OnScrollBy` 잘못 된 라고 `sizeScroll` 인수입니다.  
  
##  <a name="onupdate"></a>CView::OnUpdate  
 보기의 문서가 수정 되었습니다; 한 후에 프레임 워크에서 호출 합니다. 이 함수를 호출 하 [CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) 이러한 수정 사항을 반영 하도록 표시를 업데이트 보기를 허용 합니다.  
  
```  
virtual void OnUpdate(
    CView* pSender,  
    LPARAM lHint,  
    CObject* pHint);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSender`  
 문서를 수정 하는 보기를 가리키는 또는 **NULL** 모든 뷰는 업데이트 해야 하는 경우.  
  
 `lHint`  
 수정 작업에 대 한 정보를 포함합니다.  
  
 `pHint`  
 수정 작업에 대 한 정보를 저장 하는 개체를 가리킵니다.  
  
### <a name="remarks"></a>주의  
 기본 구현 에서도 호출 됩니다 [OnInitialUpdate](#oninitialupdate)합니다. 그려야 하는 경우 표시 하는 전체 클라이언트 영역을 무효화 하는 기본 구현에서는 다음 `WM_PAINT` 메시지가 수신 됩니다. 문서의 수정 된 부분에 매핑되는 해당 영역을 업데이트 하려는 경우이 함수를 재정의 합니다. 이렇게 하려면 힌트 매개 변수를 사용 하 여 수정 하는 방법에 대 한 정보를 전달 해야 합니다.  
  
 사용 하 여 `lHint`, 특별 한 힌트 값, 일반적으로 비트 마스크 또는 열거 형식을 정의 하 고 다음이 값 중 하나를 전달 하는 문서입니다. 사용 하 여 `pHint`, 힌트 클래스를 파생 [CObject](../../mfc/reference/cobject-class.md) 있고 재정의 하는 경우 힌트 개체;에 대 한 포인터를 전달 하는 문서 `OnUpdate`를 사용 하 여는 [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) 힌트 개체의 런타임 형식을 결정 하는 멤버 함수입니다.  
  
 일반적으로 수행 하지 말아야 그리기에서 직접 모든 `OnUpdate`합니다. 대신, 업데이트 해야 하는 영역 장치 좌표를 설명 하는 사각형을 결정 이 사각형을 전달 [CWnd::InvalidateRect](../../mfc/reference/cwnd-class.md#invalidaterect)합니다. 이 인해 다음에 발생 하는 그리기는 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) 메시지가 수신 됩니다.  
  
 경우 `lHint` 0 및 `pHint` 는 **NULL**, 문서 제네릭 업데이트 알림을 보냈습니다. 뷰는 일반 업데이트 알림의 받았을 또는 힌트 디코딩할 수 없는 경우 전체 클라이언트 영역을 무효화 합니다.  
  
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

