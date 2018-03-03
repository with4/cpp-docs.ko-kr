---
title: "CRichEditView 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditView
- AFXRICH/CRichEditView
- AFXRICH/CRichEditView::CRichEditView
- AFXRICH/CRichEditView::AdjustDialogPosition
- AFXRICH/CRichEditView::CanPaste
- AFXRICH/CRichEditView::DoPaste
- AFXRICH/CRichEditView::FindText
- AFXRICH/CRichEditView::FindTextSimple
- AFXRICH/CRichEditView::GetCharFormatSelection
- AFXRICH/CRichEditView::GetDocument
- AFXRICH/CRichEditView::GetInPlaceActiveItem
- AFXRICH/CRichEditView::GetMargins
- AFXRICH/CRichEditView::GetPageRect
- AFXRICH/CRichEditView::GetPaperSize
- AFXRICH/CRichEditView::GetParaFormatSelection
- AFXRICH/CRichEditView::GetPrintRect
- AFXRICH/CRichEditView::GetPrintWidth
- AFXRICH/CRichEditView::GetRichEditCtrl
- AFXRICH/CRichEditView::GetSelectedItem
- AFXRICH/CRichEditView::GetTextLength
- AFXRICH/CRichEditView::GetTextLengthEx
- AFXRICH/CRichEditView::InsertFileAsObject
- AFXRICH/CRichEditView::InsertItem
- AFXRICH/CRichEditView::IsRichEditFormat
- AFXRICH/CRichEditView::OnCharEffect
- AFXRICH/CRichEditView::OnParaAlign
- AFXRICH/CRichEditView::OnUpdateCharEffect
- AFXRICH/CRichEditView::OnUpdateParaAlign
- AFXRICH/CRichEditView::PrintInsideRect
- AFXRICH/CRichEditView::PrintPage
- AFXRICH/CRichEditView::SetCharFormat
- AFXRICH/CRichEditView::SetMargins
- AFXRICH/CRichEditView::SetPaperSize
- AFXRICH/CRichEditView::SetParaFormat
- AFXRICH/CRichEditView::TextNotFound
- AFXRICH/CRichEditView::GetClipboardData
- AFXRICH/CRichEditView::GetContextMenu
- AFXRICH/CRichEditView::IsSelected
- AFXRICH/CRichEditView::OnFindNext
- AFXRICH/CRichEditView::OnInitialUpdate
- AFXRICH/CRichEditView::OnPasteNativeObject
- AFXRICH/CRichEditView::OnPrinterChanged
- AFXRICH/CRichEditView::OnReplaceAll
- AFXRICH/CRichEditView::OnReplaceSel
- AFXRICH/CRichEditView::OnTextNotFound
- AFXRICH/CRichEditView::QueryAcceptData
- AFXRICH/CRichEditView::WrapChanged
- AFXRICH/CRichEditView::m_nBulletIndent
- AFXRICH/CRichEditView::m_nWordWrap
dev_langs:
- C++
helpviewer_keywords:
- CRichEditView [MFC], CRichEditView
- CRichEditView [MFC], AdjustDialogPosition
- CRichEditView [MFC], CanPaste
- CRichEditView [MFC], DoPaste
- CRichEditView [MFC], FindText
- CRichEditView [MFC], FindTextSimple
- CRichEditView [MFC], GetCharFormatSelection
- CRichEditView [MFC], GetDocument
- CRichEditView [MFC], GetInPlaceActiveItem
- CRichEditView [MFC], GetMargins
- CRichEditView [MFC], GetPageRect
- CRichEditView [MFC], GetPaperSize
- CRichEditView [MFC], GetParaFormatSelection
- CRichEditView [MFC], GetPrintRect
- CRichEditView [MFC], GetPrintWidth
- CRichEditView [MFC], GetRichEditCtrl
- CRichEditView [MFC], GetSelectedItem
- CRichEditView [MFC], GetTextLength
- CRichEditView [MFC], GetTextLengthEx
- CRichEditView [MFC], InsertFileAsObject
- CRichEditView [MFC], InsertItem
- CRichEditView [MFC], IsRichEditFormat
- CRichEditView [MFC], OnCharEffect
- CRichEditView [MFC], OnParaAlign
- CRichEditView [MFC], OnUpdateCharEffect
- CRichEditView [MFC], OnUpdateParaAlign
- CRichEditView [MFC], PrintInsideRect
- CRichEditView [MFC], PrintPage
- CRichEditView [MFC], SetCharFormat
- CRichEditView [MFC], SetMargins
- CRichEditView [MFC], SetPaperSize
- CRichEditView [MFC], SetParaFormat
- CRichEditView [MFC], TextNotFound
- CRichEditView [MFC], GetClipboardData
- CRichEditView [MFC], GetContextMenu
- CRichEditView [MFC], IsSelected
- CRichEditView [MFC], OnFindNext
- CRichEditView [MFC], OnInitialUpdate
- CRichEditView [MFC], OnPasteNativeObject
- CRichEditView [MFC], OnPrinterChanged
- CRichEditView [MFC], OnReplaceAll
- CRichEditView [MFC], OnReplaceSel
- CRichEditView [MFC], OnTextNotFound
- CRichEditView [MFC], QueryAcceptData
- CRichEditView [MFC], WrapChanged
- CRichEditView [MFC], m_nBulletIndent
- CRichEditView [MFC], m_nWordWrap
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c9062e9cf781363b482c5ee77238d315044be7df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cricheditview-class"></a>CRichEditView 클래스
와 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) 및 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), MFC의 문서 뷰 아키텍처 컨텍스트 내에서 rich edit 컨트롤의 기능을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CRichEditView : public CCtrlView  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CRichEditView::CRichEditView](#cricheditview)|`CRichEditView` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRichEditView::AdjustDialogPosition](#adjustdialogposition)|현재 선택 영역을 모호 하지 않도록 대화 상자를 이동 합니다.|  
|[CRichEditView::CanPaste](#canpaste)|Rich edit 뷰의에 붙여 넣을 수 있는 데이터를 클립보드에 포함 되는지 여부를 알려 줍니다.|  
|[CRichEditView::DoPaste](#dopaste)|Rich edit 뷰의에 OLE 항목을 붙여 넣습니다.|  
|[CRichEditView::FindText](#findtext)|대기 커서를 호출 하는 지정 된 텍스트를 찾습니다.|  
|[CRichEditView::FindTextSimple](#findtextsimple)|지정된 된 텍스트를 찾습니다.|  
|[CRichEditView::GetCharFormatSelection](#getcharformatselection)|현재 선택 영역에 대 한 특성을 형식 지정 문자를 검색 합니다.|  
|[CRichEditView::GetDocument](#getdocument)|관련 된 항목에 대 한 포인터를 검색 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)합니다.|  
|[CRichEditView::GetInPlaceActiveItem](#getinplaceactiveitem)|서식 있는 편집 보기에서 현재 내부 활성화가 OLE 항목을 검색 합니다.|  
|[CRichEditView::GetMargins](#getmargins)|Rich edit 뷰의 여백을 검색합니다.|  
|[CRichEditView::GetPageRect](#getpagerect)|Rich edit 뷰의 대 한 페이지 사각형을 검색합니다.|  
|[CRichEditView::GetPaperSize](#getpapersize)|Rich edit 뷰의 대 한 용지 크기를 검색합니다.|  
|[CRichEditView::GetParaFormatSelection](#getparaformatselection)|단락 서식 현재 선택 영역에 대 한 특성을 검색 합니다.|  
|[CRichEditView::GetPrintRect](#getprintrect)|Rich edit 뷰의 대 한 인쇄 사각형을 검색합니다.|  
|[CRichEditView::GetPrintWidth](#getprintwidth)|Rich edit 뷰의 대 한 인쇄 너비를 검색합니다.|  
|[CRichEditView::GetRichEditCtrl](#getricheditctrl)|Rich edit 컨트롤을 검색합니다.|  
|[CRichEditView::GetSelectedItem](#getselecteditem)|서식 있는 편집 보기에서 선택한 항목을 검색합니다.|  
|[CRichEditView::GetTextLength](#gettextlength)|서식 있는 편집 보기에 있는 텍스트의 길이 검색합니다.|  
|[CRichEditView::GetTextLengthEx](#gettextlengthex)|문자 또는 서식 있는 편집 보기에서 바이트 수를 검색 합니다. 길이 결정 하는 방법에 대 한 확장 된 플래그 목록입니다.|  
|[CRichEditView::InsertFileAsObject](#insertfileasobject)|OLE 항목으로 파일을 삽입합니다.|  
|[CRichEditView::InsertItem](#insertitem)|OLE 항목으로 새 항목을 삽입합니다.|  
|[CRichEditView::IsRichEditFormat](#isricheditformat)|서식 있는 편집 또는 텍스트 형식의 데이터를 클립보드에 포함 되어 있는지 여부를 알려 줍니다.|  
|[CRichEditView::OnCharEffect](#onchareffect)|현재 선택 영역에 대 한 서식을 문자를 전환 합니다.|  
|[CRichEditView::OnParaAlign](#onparaalign)|단락 맞춤을 변경합니다.|  
|[CRichEditView::OnUpdateCharEffect](#onupdatechareffect)|문자 공용 멤버 함수에 대 한 명령 UI를 업데이트합니다.|  
|[CRichEditView::OnUpdateParaAlign](#onupdateparaalign)|단락 공용 멤버 함수에 대 한 명령 UI를 업데이트합니다.|  
|[CRichEditView::PrintInsideRect](#printinsiderect)|지정된 된 사각형 내에서 지정 된 텍스트의 서식을 지정 합니다.|  
|[CRichEditView::PrintPage](#printpage)|지정된 된 페이지 내에서 지정 된 텍스트의 서식을 지정 합니다.|  
|[CRichEditView::SetCharFormat](#setcharformat)|현재 선택 영역에 대 한 특성을 형식 지정 문자를 설정 합니다.|  
|[CRichEditView::SetMargins](#setmargins)|이 서식에 대 한 여백 설정 보기를 편집 합니다.|  
|[CRichEditView::SetPaperSize](#setpapersize)|Rich edit 뷰의 대 한 용지 크기를 설정합니다.|  
|[CRichEditView::SetParaFormat](#setparaformat)|단락 서식 현재 선택 영역에 대 한 특성을 설정 합니다.|  
|[CRichEditView::TextNotFound](#textnotfound)|컨트롤의 내부 검색 상태를 다시 설정합니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRichEditView::GetClipboardData](#getclipboarddata)|이 서식 있는 편집 보기에서 특정 범위에 대 한 클립보드 개체를 검색합니다.|  
|[CRichEditView::GetContextMenu](#getcontextmenu)|아래로 오른쪽 마우스 단추에서 사용 하는 상황에 맞는 메뉴를 검색 합니다.|  
|[CRichEditView::IsSelected](#isselected)|지정된 된 OLE 항목 선택 하는 경우를 나타냅니다.|  
|[CRichEditView::OnFindNext](#onfindnext)|부분 문자열의 다음 항목을 찾습니다.|  
|[CRichEditView::OnInitialUpdate](#oninitialupdate)|새로 고침 처음 보기는 문서에 연결 합니다.|  
|[CRichEditView::OnPasteNativeObject](#onpastenativeobject)|OLE 항목에서 원시 데이터를 검색합니다.|  
|[CRichEditView::OnPrinterChanged](#onprinterchanged)|지정된 된 장치에 인쇄 특성을 설정합니다.|  
|[CRichEditView::OnReplaceAll](#onreplaceall)|지정된 된 문자열의 모든 항목을 새 문자열을 바꿉니다.|  
|[CRichEditView::OnReplaceSel](#onreplacesel)|현재 선택 영역을 바꿉니다.|  
|[CRichEditView::OnTextNotFound](#ontextnotfound)|요청 된 텍스트를 찾을 수 없는 사용자 알림을 처리 합니다.|  
|[CRichEditView::QueryAcceptData](#queryacceptdata)|에 데이터에 대 한 참조에 대 한 쿼리는 `IDataObject`합니다.|  
|[CRichEditView::WrapChanged](#wrapchanged)|이 서식 있는 편집의 값에 따라 보기에 대 한 대상 출력 장치 조정 `m_nWordWrap`합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CRichEditView::m_nBulletIndent](#m_nbulletindent)|글머리 기호 목록에 대 한 들여쓰기의 크기를 나타냅니다.|  
|[CRichEditView::m_nWordWrap](#m_nwordwrap)|단어 줄 바꿈 제약 조건을 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 "Rich edit 컨트롤"는 사용자 입력 수 있으며 텍스트를 편집 하는 창입니다. 텍스트 문자 및 단락 서식을 할당할 수 있으며 포함 된 OLE 개체를 포함할 수 있습니다. Rich edit 컨트롤 텍스트의 서식을 지정 하기 위한 프로그래밍 인터페이스를 제공 합니다. 그러나 응용 프로그램 사용자에 게 형식 지정 작업을 제공 하는 데 필요한 사용자 인터페이스 구성 요소를 구현 해야 합니다.  
  
 `CRichEditView`텍스트 및 텍스트의 서식 특성을 유지 관리합니다. `CRichEditDoc`보기에 있는 OLE 클라이언트 항목의 목록을 유지 관리 합니다. `CRichEditCntrItem`컨테이너 쪽 OLE 클라이언트 항목에 대 한 액세스를 제공합니다.  
  
 이 Windows 공용 컨트롤 (및 따라서는 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) 및 관련 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 되는 프로그램에만 사용할 수는 있습니다.  
  
 Rich edit 뷰를 사용 하 여 MFC 응용 프로그램의 예제를 참조 하십시오.는 [워드 패드](../../visual-cpp-samples.md) 샘플 응용 프로그램입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CRichEditView`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrich.h  
  
##  <a name="adjustdialogposition"></a>CRichEditView::AdjustDialogPosition  
 지정된 된 대화 상자를 이동 하 여 현재 선택 영역을 가리지 않습니다 되도록 하려면이 함수를 호출 합니다.  
  
```  
void AdjustDialogPosition(CDialog* pDlg);
```  
  
### <a name="parameters"></a>매개 변수  
 *pDlg*  
 `CDialog` 개체에 대한 포인터입니다.  
  
##  <a name="canpaste"></a>CRichEditView::CanPaste  
 클립보드 rich edit 뷰의에 붙여 넣을 수 있는 정보가 있는지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL CanPaste() const;  
```  
  
### <a name="return-value"></a>반환 값  
 Rich edit 뷰의 수락할 수 있는; 되는 형식에서 데이터 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="cricheditview"></a>CRichEditView::CRichEditView  
 이 함수를 만드는 호출는 `CRichEditView` 개체입니다.  
  
```  
CRichEditView();
```  
  
##  <a name="dopaste"></a>CRichEditView::DoPaste  
 이 함수에서 OLE 항목을 붙여 넣을를 호출 `dataobj` 풍부한을이 문서/뷰를 편집 합니다.  
  
```  
void DoPaste(
    COleDataObject& dataobj,  
    CLIPFORMAT cf,  
    HMETAFILEPICT hMetaPict);
```  
  
### <a name="parameters"></a>매개 변수  
 `dataobj`  
 [COleDataObject](../../mfc/reference/coledataobject-class.md) 붙여 데이터가 들어 있는입니다.  
  
 `cf`  
 원하는 클립보드 형식입니다.  
  
 `hMetaPict`  
 메타 파일을 붙여 넣을 항목을 나타냅니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크의 기본 구현은의 일부분으로이 함수를 호출 [QueryAcceptData](#queryacceptdata)합니다.  
  
 이 함수에는 붙여넣기에 대 한 처리기의 결과에 따라 붙여넣기의 유형을 결정 합니다. 경우 `cf` 가 0 이므로 새 항목에는 현재 아이콘 표현을 사용 합니다. 경우 `cf` 0이 아닌 및 `hMetaPict` 않습니다 **NULL**를 사용 하 여 새 항목 `hMetaPict` 표현에 대 한 합니다.  
  
##  <a name="findtext"></a>CRichEditView::FindText  
 지정된 된 텍스트 찾기 및 현재 선택 되도록 설정 하려면이 함수를 호출 합니다.  
  
```  
BOOL FindText(
    LPCTSTR lpszFind,  
    BOOL bCase = TRUE,  
    BOOL bWord = TRUE,  
    BOOL bNext = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFind`  
 검색할 문자열을 포함 합니다.  
  
 `bCase`  
 검색은 대/소문자 구분 하는 경우를 나타냅니다.  
  
 `bWord`  
 검색 단어 단위로 단어의 일부가 아니라 일치 해야 하는 경우를 나타냅니다.  
  
 `bNext`  
 검색 방향을 나타냅니다. 경우 **TRUE**, 검색 방향이 버퍼의 끝이 있습니다. 경우 **FALSE**, 버퍼의 시작 부분을 향해 검색 방향이 됩니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우에는 `lpszFind` 텍스트를 찾을 수 있습니다; 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 찾기 작업 하는 동안 대기 커서를 표시합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#151](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]  
  
##  <a name="findtextsimple"></a>CRichEditView::FindTextSimple  
 지정된 된 텍스트 찾기 및 현재 선택 되도록 설정 하려면이 함수를 호출 합니다.  
  
```  
BOOL FindTextSimple(
    LPCTSTR lpszFind,  
    BOOL bCase = TRUE,  
    BOOL bWord = TRUE,  
    BOOL bNext = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFind`  
 검색할 문자열을 포함 합니다.  
  
 `bCase`  
 검색은 대/소문자 구분 하는 경우를 나타냅니다.  
  
 `bWord`  
 검색 단어 단위로 단어의 일부가 아니라 일치 해야 하는 경우를 나타냅니다.  
  
 `bNext`  
 검색 방향을 나타냅니다. 경우 **TRUE**, 검색 방향이 버퍼의 끝이 있습니다. 경우 **FALSE**, 버퍼의 시작 부분을 향해 검색 방향이 됩니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우에는 `lpszFind` 텍스트를 찾을 수 있습니다; 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CRichEditView::FindText](#findtext)합니다.  
  
##  <a name="getcharformatselection"></a>CRichEditView::GetCharFormatSelection  
 현재 선택 된 특성을 형식 지정 문자를 가져오려면이 함수를 호출 합니다.  
  
```  
CHARFORMAT2& GetCharFormatSelection();
```  
  
### <a name="return-value"></a>반환 값  
 A [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) 서식 현재 선택 된 특성 문자를 포함 하는 구조입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조는 [EM_GETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb788026) 메시지 및 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) Windows SDK에는 구조입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="getclipboarddata"></a>CRichEditView::GetClipboardData  
 처리의 일부로이 함수를 호출 하는 프레임 워크 [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315)합니다.  
  
```  
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,  
    DWORD dwReco,  
    LPDATAOBJECT lpRichDataObj,  
    LPDATAOBJECT* lplpdataobj);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpchrg`  
 에 대 한 포인터는 [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) 문자 (및 OLE 항목)가 지정한 데이터 개체를 복사할 대상 범위를 지정 하는 구조 `lplpdataobj`합니다.  
  
 `dwReco`  
 클립보드 작업 플래그입니다. 다음이 값 중 하나일 수 있습니다.  
  
- **RECO_COPY** 클립보드에 복사 합니다.  
  
- **RECO_CUT** 를 잘라내어 클립보드에 있습니다.  
  
- **RECO_DRAG** 끌기 작업 (끌어서 놓기)입니다.  
  
- **RECO_DROP** 놓기 작업 (끌어서 놓기)입니다.  
  
- **RECO_PASTE** 클립보드에서 붙여넣기 합니다.  
  
 `lpRichDataObj`  
 에 대 한 포인터는 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) 컨트롤을 편집 하는 풍부한에서 클립보드 데이터를 포함 하는 개체 ( [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341)).  
  
 `lplpdataobj`  
 포인터의 주소를 받는 포인터 변수에 `IDataObject` 에 지정 된 범위를 나타내는 개체는 `lpchrg` 매개 변수입니다. 값 `lplpdataobj` 오류가 반환 되는 경우 무시 됩니다.  
  
### <a name="return-value"></a>반환 값  
 `HRESULT` 작업의 성공 여부를 보고 하는 값입니다. 대 한 자세한 내용은 `HRESULT`, 참조 [COM 오류 코드 구조](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows sdk에서입니다.  
  
### <a name="remarks"></a>설명  
 반환 값은 성공을 나타내는 경우 **IRichEditOleCallback::GetClipboardData** 반환는 `IDataObject` 액세스 하 여 `lplpdataobj`, 그렇지 않으면 액세스 하 여 하나 반환 `lpRichDataObj`합니다. 사용자 고유의 클립보드 데이터를 제공 하려면이 함수를 재정의 합니다. 이 함수의 기본 구현은 반환 **E_NOTIMPL**합니다.  
  
 고급 재정의할 수 있습니다.  
  
 자세한 내용은 참조 [IRichEditOle::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774341), [IRichEditOleCallback::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/bb774315), 및 [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) 는 Windows SDK에서 참조 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) in the Windows SDK입니다.  
  
##  <a name="getcontextmenu"></a>CRichEditView::GetContextMenu  
 처리의 일부로이 함수를 호출 하는 프레임 워크 [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317)합니다.  
  
```  
virtual HMENU GetContextMenu(
    WORD seltyp,  
    LPOLEOBJECT lpoleobj,  
    CHARRANGE* lpchrg);
```  
  
### <a name="parameters"></a>매개 변수  
 *seltyp*  
 선택 영역 형식입니다. 선택 영역 유형 값은 주의 섹션에 설명 되어 있습니다.  
  
 `lpoleobj`  
 에 대 한 포인터는 **OLEOBJECT** 선택 영역에는 OLE 항목을 하나 이상 포함 하는 경우 첫 번째 선택 된 OLE 개체를 지정 하는 구조입니다. 선택 영역에 항목이 없는 경우 `lpoleobj` 은 **NULL**합니다. **OLEOBJECT** 구조는 OLE 개체 v-테이블에 대 한 포인터를 보유 합니다.  
  
 `lpchrg`  
 에 대 한 포인터는 [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) 현재 선택 영역을 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 상황에 맞는 메뉴에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 처리를 오른쪽 마우스 단추의 중요 한 부분입니다.  
  
 선택 유형을 다음 플래그의 조합이 포함 될 수 있습니다.  
  
- `SEL_EMPTY`현재 선택 영역이 없는 것을 나타냅니다.  
  
- `SEL_TEXT`텍스트가 현재 선택 영역에 포함 되어 있음을 나타냅니다.  
  
- `SEL_OBJECT`현재 선택 영역 OLE 항목을 하나 이상 포함 되어 있음을 나타냅니다.  
  
- `SEL_MULTICHAR`현재 선택한 항목 텍스트의 문자를 여러 개 포함 되어 있음을 나타냅니다.  
  
- `SEL_MULTIOBJECT`현재 선택 영역에 둘 이상의 OLE 개체가 포함 되어 있음을 나타냅니다.  
  
 기본 구현은 반환 **NULL**합니다. 고급 재정의할 수 있습니다.  
  
 자세한 내용은 참조 [IRichEditOleCallback::GetContextMenu](http://msdn.microsoft.com/library/windows/desktop/bb774317) 및 [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) Windows sdk에서입니다.  
  
 대 한 자세한 내용은 **OLEOBJECT** 입력의 OLE 데이터 구조 및 구조 할당 문서를 참조는 *OLE 기술 자료*합니다.  
  
##  <a name="getdocument"></a>CRichEditView::GetDocument  
 에 대 한 포인터를 가져오려면이 함수를 호출 하 여 `CRichEditDoc` 이 보기에 연결 된 합니다.  
  
```  
CRichEditDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) 개체와 연결 된 프로그램 `CRichEditView` 개체입니다.  
  
##  <a name="getinplaceactiveitem"></a>CRichEditView::GetInPlaceActiveItem  
 호출 OLE를 가져오려면이 함수를 항목을이 위치에서 현재 활성화 된 `CRichEditView` 개체입니다.  
  
```  
CRichEditCntrItem* GetInPlaceActiveItem() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터를 현재 위치를 단일 활성 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) 이 서식 있는 편집 뷰에서 개체 **NULL** 에 없을 경우 OLE 항목이 현재 내부 활성 상태입니다.  
  
##  <a name="getmargins"></a>CRichEditView::GetMargins  
 인쇄에서 사용 되는 현재 여백을 검색 하려면이 함수를 호출 합니다.  
  
```  
CRect GetMargins() const;  
```  
  
### <a name="return-value"></a>반환 값  
 인쇄에 사용 된 여백에서 측정 `MM_TWIPS`합니다.  
  
##  <a name="getpagerect"></a>CRichEditView::GetPageRect  
 인쇄에서 사용 되는 페이지의 크기를 가져오려면이 함수를 호출 합니다.  
  
```  
CRect GetPageRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 인쇄에 사용 되는 페이지의 경계에서 측정 `MM_TWIPS`합니다.  
  
### <a name="remarks"></a>설명  
 이 값은 용지 크기에 따라 결정 됩니다.  
  
##  <a name="getpapersize"></a>CRichEditView::GetPaperSize  
 현재 용지 크기를 검색 하려면이 함수를 호출 합니다.  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 인쇄에 사용 되는 용지 크기 단위로 `MM_TWIPS`합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#153](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]  
  
##  <a name="getparaformatselection"></a>CRichEditView::GetParaFormatSelection  
 단락 서식 현재 선택 된 특성을 가져오려면이 함수를 호출 합니다.  
  
```  
PARAFORMAT2& GetParaFormatSelection();
```  
  
### <a name="return-value"></a>반환 값  
 A [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) 단락 서식 현재 선택 된 특성을 포함 하는 구조입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [EM_GETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774182) 메시지 및 [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) Windows SDK에는 구조입니다.  
  
##  <a name="getprintrect"></a>CRichEditView::GetPrintRect  
 페이지 사각형 내에서 인쇄 영역 경계를 검색 하려면이 함수를 호출 합니다.  
  
```  
CRect GetPrintRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 인쇄에 사용 되는 이미지 영역 경계 단위로 `MM_TWIPS`합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#154](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]  
  
##  <a name="getprintwidth"></a>CRichEditView::GetPrintWidth  
 인쇄 영역 너비를 결정 하려면이 함수를 호출 합니다.  
  
```  
int GetPrintWidth() const;  
```  
  
### <a name="return-value"></a>반환 값  
 인쇄 영역 너비 단위로 `MM_TWIPS`합니다.  
  
##  <a name="getricheditctrl"></a>CRichEditView::GetRichEditCtrl  
 검색 하려면이 함수 호출의 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) 연관 된 개체는 `CRichEditView` 개체입니다.  
  
```  
CRichEditCtrl& GetRichEditCtrl() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `CRichEditCtrl` 이 보기에 대 한 개체입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CRichEditView::FindText](#findtext)합니다.  
  
##  <a name="getselecteditem"></a>CRichEditView::GetSelectedItem  
 OLE 항목을 검색 하려면이 함수 호출 (한 `CRichEditCntrItem` 개체)이에서 현재 선택 된 `CRichEditView` 개체입니다.  
  
```  
CRichEditCntrItem* GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) 에서 선택한 개체는 `CRichEditView` 개체 **NULL** 경우이 보기에서 선택 된 항목이 있습니다.  
  
##  <a name="gettextlength"></a>CRichEditView::GetTextLength  
 이 텍스트의 길이 검색 하려면이 함수 호출 `CRichEditView` 개체입니다.  
  
```  
long GetTextLength() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 텍스트의 길이 `CRichEditView` 개체입니다.  
  
##  <a name="gettextlengthex"></a>CRichEditView::GetTextLengthEx  
 이 텍스트의 길이 계산 하려면이 함수를 호출 `CRichEditView` 개체입니다.  
  
```  
long GetTextLengthEx(
    DWORD dwFlags,  
    UINT uCodePage = -1) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `dwFlags`  
 텍스트 길이 결정 하는 데 사용할 방법을 지정 하는 값입니다. 이 구성원 하나일 수 있습니다 또는 플래그 소속에 나열 된 값 [GETTEXTLENGTHEX](http://msdn.microsoft.com/library/windows/desktop/bb787915) Windows SDK에 설명 합니다.  
  
 `uCodePage`  
 번역 (1200 유니코드에 대 한 ANSI 코드 페이지에 대 한 CP_ACP)에 대 한 코드 페이지입니다.  
  
### <a name="return-value"></a>반환 값  
 문자 또는 편집 컨트롤의 바이트 수입니다. 호환 되지 않는 플래그 설정 된 경우 `dwFlags`를이 멤버 함수는 반환 `E_INVALIDARG`합니다.  
  
### <a name="remarks"></a>설명  
 `GetTextLengthEx`텍스트의 길이 결정 하는 추가 방법을 제공 합니다. Rich Edit 2.0 기능을 지원합니다. 자세한 내용은 참조 [Rich Edit 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb787873) Windows sdk에서입니다.  
  
##  <a name="insertfileasobject"></a>CRichEditView::InsertFileAsObject  
 지정된 된 파일을 삽입 하려면이 함수 호출 (으로 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) 개체)를 서식 보기를 편집 합니다.  
  
```  
void InsertFileAsObject(LPCTSTR lpszFileName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFileName`  
 삽입 될 파일의 이름을 포함 하는 문자열입니다.  
  
##  <a name="insertitem"></a>CRichEditView::InsertItem  
 삽입 하려면이 함수를 호출 하는 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) 서식 있는 편집 보기에는 개체입니다.  
  
```  
HRESULT InsertItem(CRichEditCntrItem* pItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 삽입할 항목에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `HRESULT` 삽입의 성공 여부를 나타내는 값입니다.  
  
### <a name="remarks"></a>설명  
 대 한 자세한 내용은 `HRESULT`, 참조 [COM 오류 코드 구조](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows sdk에서입니다.  
  
##  <a name="isricheditformat"></a>CRichEditView::IsRichEditFormat  
 이 함수를 호출 `cf` 은 클립보드 형식 텍스트, 서식 있는 텍스트 또는 OLE 항목과 서식 있는 텍스트입니다.  
  
```  
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```  
  
### <a name="parameters"></a>매개 변수  
 `cf`  
 관심 있는 클립보드 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우 `cf` 은 서식 있는 편집 또는 텍스트 클립보드 형식입니다.  
  
##  <a name="isselected"></a>CRichEditView::IsSelected  
 지정된 된 OLE 항목이이 보기에서 현재 선택 되어 있는지 확인 하려면이 함수를 호출 합니다.  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDocItem`  
 보기에 있는 개체에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 개체 선택 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 파생 된 뷰 클래스에 OLE 항목의 선택 집합을 처리 하기 위한 다른 방법을 경우이 함수를 재정의 합니다.  
  
##  <a name="m_nbulletindent"></a>CRichEditView::m_nBulletIndent  
 글머리 기호 목록의; 항목에 대 한 들여쓰기 기본적으로 720 단위는 1/2 인치입니다.  
  
```  
int m_nBulletIndent;  
```  
  
##  <a name="m_nwordwrap"></a>CRichEditView::m_nWordWrap  
 Rich edit 뷰의 대 한 자동 줄 바꿈의 유형을 나타냅니다.  
  
```  
int m_nWordWrap;  
```  
  
### <a name="remarks"></a>설명  
 다음 값 중 하나입니다.  
  
- `WrapNone`단어 단위로 겹쳐지지 않도록을 나타냅니다.  
  
- `WrapToWindow`창의 너비에 따라 자동 줄 바꿈을 나타냅니다.  
  
- `WrapToTargetDevice`대상 장치의 특징을 기반으로 자동 줄 바꿈을 나타냅니다.  
  
### <a name="example"></a>예  
  예를 참조 [CRichEditView::WrapChanged](#wrapchanged)합니다.  
  
##  <a name="onchareffect"></a>CRichEditView::OnCharEffect  
 현재 선택 영역에 대 한 효과 서식 문자를 전환 하려면이 함수를 호출 합니다.  
  
```  
void OnCharEffect(
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwMask`  
 현재 선택한 항목의 수정 하는 효과 서식 지정 문자입니다.  
  
 `dwEffect`  
 원하는 목록 효과 설정/해제를 서식 지정 문자입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 호출할 때마다 현재 선택 영역에 대 한 지정 된 서식 지정 효과 전환합니다.  
  
 대 한 자세한 내용은 `dwMask` 및 `dwEffect` 매개 변수와 해당 잠재적인 값의 해당 데이터 멤버를 참조 [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Windows sdk에서입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#155](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]  
  
##  <a name="onfindnext"></a>CRichEditView::OnFindNext  
 찾기/바꾸기 대화 상자에서 명령을 처리할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnFindNext(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    BOOL bWord);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFind`  
 찾을 문자열입니다.  
  
 `bNext`  
 검색 방향을: **TRUE** 나타냅니다. **FALSE**, 최대 합니다.  
  
 `bCase`  
 검색 대/소문자 구분 여부를 나타냅니다.  
  
 `bWord`  
 검색 단어 단위로 전용인 지 여부를 나타냅니다.  
  
### <a name="remarks"></a>설명  
 내에서 텍스트를 찾으려면이 함수 호출에서 `CRichEditView`합니다. 파생 된 뷰 클래스에 대 한 검색 특성을 변경 하려면이 함수를 재정의 합니다.  
  
##  <a name="oninitialupdate"></a>CRichEditView::OnInitialUpdate  
 보기에는 문서에 처음 연결 되었으나 처음 표시 되는 보기 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현에서는 호출 하 여 [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) 힌트 정보 없이 멤버 함수 (즉, 0에 대 한 기본값을 사용 하는 `lHint` 매개 변수 및 **NULL** 에 대 한 `pHint` 매개 변수). 문서에 대 한 정보를 필요로 하는 한 번만 초기화를 수행 하려면이 함수를 재정의 합니다. 예를 들어 응용 프로그램에 문서 고정 크기의 경우 보기의 스크롤 제한 되는 문서 크기에 따라 초기화를이 함수를 사용할 수 있습니다. 사용 하 여 응용 프로그램의 가변 크기 문서를 지 원하는 경우 `OnUpdate` 하기 위해 스크롤 업데이트 제한 될 때마다 변경 내용을 문서화 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CRichEditView::m_nWordWrap](#m_nwordwrap)합니다.  
  
##  <a name="onpastenativeobject"></a>CRichEditView::OnPasteNativeObject  
 이 함수를 사용 하 여 포함된 된 항목에서 원시 데이터를 로드 합니다.  
  
```  
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpStg*  
 에 대 한 포인터는 [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아닌 그렇지 않은 경우, 0;  
  
### <a name="remarks"></a>설명  
 일반적으로 설정 하려는 만들어는 [COleStreamFile](../../mfc/reference/colestreamfile-class.md) 주위에서 `IStorage`합니다. `COleStreamFile` 보관 파일에 첨부할 수 및 [cobject:: Serialize](../../mfc/reference/cobject-class.md#serialize) 데이터를 로드 하기 위해 호출 합니다.  
  
 고급 재정의할 수 있습니다.  
  
 자세한 내용은 참조 [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) Windows sdk에서입니다.  
  
##  <a name="onparaalign"></a>CRichEditView::OnParaAlign  
 선택한 단락에서 단락 맞춤을 변경 하려면이 함수를 호출 합니다.  
  
```  
void OnParaAlign(WORD wAlign);
```  
  
### <a name="parameters"></a>매개 변수  
 `wAlign`  
 단락 맞춤을 권장합니다. 다음 값 중 하나입니다.  
  
- `PFA_LEFT`왼쪽 여백 단락을 정렬 합니다.  
  
- `PFA_RIGHT`오른쪽 여백 단락을 정렬 합니다.  
  
- `PFA_CENTER`단락 맞춥니다. 가운데 맞춤 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#156](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]  
  
##  <a name="onprinterchanged"></a>CRichEditView::OnPrinterChanged  
 프린터 변경 될 때이 서식 있는 편집 보기에 대 한 특성을 변경 하려면이 함수를 재정의 합니다.  
  
```  
virtual void OnPrinterChanged(const CDC& dcPrinter);
```  
  
### <a name="parameters"></a>매개 변수  
 `dcPrinter`  
 A [CDC](../../mfc/reference/cdc-class.md) 새 프린터에 대 한 개체입니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 물리적 높이와 너비를 출력 장치 (프린터)의 용지 크기를 설정 합니다. 장치 컨텍스트가 없는 연결 된 없을 경우 `dcPrinter`, 기본 구현에서는 11 8.5 인치 용지 크기를 설정 합니다.  
  
##  <a name="onreplaceall"></a>CRichEditView::OnReplaceAll  
 바꾸기 대화 상자에서 모두 바꾸기 명령을 처리할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnReplaceAll(
    LPCTSTR lpszFind,  
    LPCTSTR lpszReplace,  
    BOOL bCase,  
    BOOL bWord);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFind`  
 바꿀 텍스트입니다.  
  
 `lpszReplace`  
 바꿀 텍스트입니다.  
  
 `bCase`  
 검색은 대/소문자 구분 하는 경우를 나타냅니다.  
  
 `bWord`  
 아닌지 검색 단어 단위로 선택 해야 하는 경우를 나타냅니다.  
  
### <a name="remarks"></a>설명  
 지정 된 일부 텍스트 항목을 모두를 다른 문자열로 바꾸려면이 함수를 호출 합니다. 이 보기에 대 한 검색 특성을 변경 하려면이 함수를 재정의 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CRichEditView::FindText](#findtext)합니다.  
  
##  <a name="onreplacesel"></a>CRichEditView::OnReplaceSel  
 바꾸기 대화 상자에서 Replace 명령을 처리할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnReplaceSel(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    BOOL bWord,  
    LPCTSTR lpszReplace);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFind`  
 바꿀 텍스트입니다.  
  
 `bNext`  
 검색의 방향을 나타냅니다: **TRUE** ; 다운 **FALSE**, 최대 합니다.  
  
 `bCase`  
 검색은 대/소문자 구분 하는 경우를 나타냅니다.  
  
 `bWord`  
 아닌지 검색 단어 단위로 선택 해야 하는 경우를 나타냅니다.  
  
 `lpszReplace`  
 바꿀 텍스트입니다.  
  
### <a name="remarks"></a>설명  
 일부 지정 된 텍스트의 한 위치를 다른 문자열로 바꾸려면이 함수를 호출 합니다. 이 보기에 대 한 검색 특성을 변경 하려면이 함수를 재정의 합니다.  
  
##  <a name="ontextnotfound"></a>CRichEditView::OnTextNotFound  
 검색에 실패 될 때마다 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFind`  
 이 텍스트에 찾을 수 없습니다.  
  
### <a name="remarks"></a>설명  
 이 함수에서 출력 알림을 변경 하려면 재정의 [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356)합니다.  
  
 자세한 내용은 참조 [MessageBeep](http://msdn.microsoft.com/library/windows/desktop/ms680356) Windows sdk에서입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#157](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]  
  
##  <a name="onupdatechareffect"></a>CRichEditView::OnUpdateCharEffect  
 프레임 워크에는 문자 효과 명령에 대 한 명령 UI를 업데이트 하려면이 함수를 호출 합니다.  
  
```  
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,  
    DWORD dwMask,  
    DWORD dwEffect);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCmdUI`  
 에 대 한 포인터는 [CCmdUI](../../mfc/reference/ccmdui-class.md) 개체입니다.  
  
 `dwMask`  
 마스크 서식 문자를 나타냅니다.  
  
 `dwEffect`  
 효과 서식 문자를 나타냅니다.  
  
### <a name="remarks"></a>설명  
 / / 마스크 `dwMask` 서식 특성을 확인 하는 문자를 지정 합니다. 플래그는 `dwEffect` 서식 특성을 설정/해제 하는 문자를 나열 합니다.  
  
 대 한 자세한 내용은 `dwMask` 및 `dwEffect` 매개 변수와 해당 잠재적인 값의 해당 데이터 멤버를 참조 [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Windows sdk에서입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#158](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]  
  
##  <a name="onupdateparaalign"></a>CRichEditView::OnUpdateParaAlign  
 프레임 워크 단락 효과 명령에 대 한 명령 UI를 업데이트 하려면이 함수를 호출 합니다.  
  
```  
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,  
    WORD wAlign);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCmdUI`  
 에 대 한 포인터는 [CCmdUI](../../mfc/reference/ccmdui-class.md) 개체입니다.  
  
 `wAlign`  
 확인할 단락 맞춤입니다. 다음 값 중 하나입니다.  
  
- `PFA_LEFT`왼쪽 여백 단락을 정렬 합니다.  
  
- `PFA_RIGHT`오른쪽 여백 단락을 정렬 합니다.  
  
- `PFA_CENTER`단락 맞춥니다. 가운데 맞춤 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#159](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]  
  
##  <a name="printinsiderect"></a>CRichEditView::PrintInsideRect  
 범위 내에 맞게 rich edit 컨트롤의 텍스트에 서식을 지정 하려면이 함수를 호출 *rectLayout* 로 지정 된 장치에 대 한 `pDC`합니다.  
  
```  
long PrintInsideRect(
    CDC* pDC,  
    RECT& rectLayout,  
    long nIndexStart,  
    long nIndexStop,  
    BOOL bOutput);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 출력 영역에 대 한 장치 컨텍스트에 대 한 포인터입니다.  
  
 *rectLayout*  
 [RECT](../../mfc/reference/rect-structure1.md) 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 출력 영역을 정의 하는 합니다.  
  
 `nIndexStart`  
 서식을 지정할 첫 번째 문자의 0부터 시작 인덱스입니다.  
  
 `nIndexStop`  
 서식을 지정할 마지막 문자의 0부터 시작 인덱스입니다.  
  
 *bOutput*  
 텍스트를 렌더링할지 여부를 나타냅니다. 경우 **FALSE**, 텍스트 방금 측정 됩니다.  
  
### <a name="return-value"></a>반환 값  
 1을 더한 출력 영역 내에 포함 된 마지막 문자의 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 일반적으로이 호출에 대 한 호출 뒤 [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) 출력을 생성 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CRichEditView::GetPaperSize](#getpapersize)합니다.  
  
##  <a name="printpage"></a>CRichEditView::PrintPage  
 로 지정 된 출력 장치에 대 한 서식 있는 편집 컨트롤에서 텍스트의 범위 서식을 지정 하려면이 함수를 호출 `pDC`합니다.  
  
```  
long PrintPage(
    CDC* pDC,  
    long nIndexStart,  
    long nIndexStop);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 페이지 출력에 대 한 장치 컨텍스트에 대 한 포인터입니다.  
  
 `nIndexStart`  
 서식을 지정할 첫 번째 문자의 0부터 시작 인덱스입니다.  
  
 `nIndexStop`  
 서식을 지정할 마지막 문자의 0부터 시작 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 페이지 + 1 개에 꼭 맞는 마지막 문자의 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 각 페이지의 레이아웃을 제어는 [GetPageRect](#getpagerect) 및 [GetPrintRect](#getprintrect)합니다. 일반적으로이 호출에 대 한 호출 뒤 [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) 출력을 생성 합니다.  
  
 여백은 물리적 페이지의 논리 페이지가 아닌를 기준으로 하는 참고 합니다. 따라서 여백을 0 많은 프린터 페이지에서 인쇄할 수 없는 영역에는 이후 텍스트를 클립 종종 됩니다. 호출 해야 텍스트 캡처를 방지 하려면 [SetMargins](#setmargins) 인쇄 하기 전에 적절 한 여백을 설정 합니다.  
  
##  <a name="queryacceptdata"></a>CRichEditView::QueryAcceptData  
 서식 있는 편집에 있는 개체를 붙여 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual HRESULT QueryAcceptData(
    LPDATAOBJECT lpdataobj,  
    CLIPFORMAT* lpcfFormat,  
    DWORD dwReco,  
    BOOL bReally,  
    HGLOBAL hMetaFile);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpdataobj*  
 에 대 한 포인터는 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) 쿼리입니다.  
  
 *lpcfFormat*  
 사용할 수 있는 데이터 형식에 대 한 포인터입니다.  
  
 `dwReco`  
 사용되지 않습니다.  
  
 *bReally*  
 붙여넣기 작업을 계속할지 여부를 나타냅니다.  
  
 `hMetaFile`  
 항목의 아이콘을 그리기에 사용 되는 메타 파일에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 `HRESULT` 작업의 성공 여부를 보고 하는 값입니다.  
  
### <a name="remarks"></a>설명  
 다른 조직 파생된 문서 클래스의 COM 항목을 처리 하려면이 함수를 재정의 합니다. 고급 재정의할 수 있습니다.  
  
 대 한 자세한 내용은 `HRESULT` 및 `IDataObject`, 참조 [COM 오류 코드 구조](http://msdn.microsoft.com/library/windows/desktop/ms690088) 및 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)각각 Windows sdk에서입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#160](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]  
  
##  <a name="setcharformat"></a>CRichEditView::SetCharFormat  
 이 새 텍스트 특성을 형식 지정 문자를 설정 하려면이 함수를 호출 `CRichEditView` 개체입니다.  
  
```  
void SetCharFormat(CHARFORMAT2 cf);
```  
  
### <a name="parameters"></a>매개 변수  
 `cf`  
 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) 서식 특성 새 기본 문자를 포함 하는 구조입니다.  
  
### <a name="remarks"></a>설명  
 로 지정 된 특성에만 **dwMask** 소속 `cf` 이 기능으로 변경 합니다.  
  
 자세한 내용은 참조 [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) 메시지 및 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) Windows SDK에는 구조입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]  
  
##  <a name="setmargins"></a>CRichEditView::SetMargins  
 Rich edit 뷰의 대 한 인쇄 여백을 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetMargins(const CRect& rectMargin);
```  
  
### <a name="parameters"></a>매개 변수  
 *rectMargin*  
 인쇄를 위한 새 여백 값은 측정 `MM_TWIPS`합니다.  
  
### <a name="remarks"></a>설명  
 경우 [m_nWordWrap](#m_nwordwrap) 은 `WrapToTargetDevice`를 호출 해야 [WrapChanged](#wrapchanged) 이 함수를 사용 하 여 인쇄 특성을 조정 합니다.  
  
 사용 하는 여백은 [PrintPage](#printpage) 물리적 페이지의 논리 페이지가 아닌 기준으로 합니다. 따라서 여백을 0 많은 프린터 페이지에서 인쇄할 수 없는 영역에는 이후 텍스트를 클립 종종 됩니다. 텍스트 캡처를 방지 하려면 사용 하 여 호출 해야 `SetMargins` 인쇄 하기 전에 적절 한 프린터 여백을 설정 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CRichEditView::GetPaperSize](#getpapersize)합니다.  
  
##  <a name="setpapersize"></a>CRichEditView::SetPaperSize  
 Rich edit 뷰의 인쇄를 위한 용지 크기를 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetPaperSize(CSize sizePaper);
```  
  
### <a name="parameters"></a>매개 변수  
 *sizePaper*  
 인쇄를 위한 새 용지 크기 값은 측정 `MM_TWIPS`합니다.  
  
### <a name="remarks"></a>설명  
 경우 [m_nWordWrap](#m_nwordwrap) 은 `WrapToTargetDevice`를 호출 해야 [WrapChanged](#wrapchanged) 이 함수를 사용 하 여 인쇄 특성을 조정 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#161](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]  
  
##  <a name="setparaformat"></a>CRichEditView::SetParaFormat  
 단락 서식이 현재 선택 영역에 대 한 특성을 설정 하려면이 함수 호출 `CRichEditView` 개체입니다.  
  
```  
BOOL SetParaFormat(PARAFORMAT2& pf);
```  
  
### <a name="parameters"></a>매개 변수  
 `pf`  
 [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) 새 기본값을 포함 하는 구조 단락 서식 특성입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 로 지정 된 특성에만 **dwMask** 소속 `pf` 이 기능으로 변경 합니다.  
  
 자세한 내용은 참조 [EM_SETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774276) 메시지 및 [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) Windows SDK에는 구조입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#162](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]  
  
##  <a name="textnotfound"></a>CRichEditView::TextNotFound  
 내부 검색 상태를 다시 설정 하려면이 함수를 호출 하는 [CRichEditView](../../mfc/reference/cricheditview-class.md) 에 대 한 실패 한 호출 후 컨트롤 [FindText](#findtext)합니다.  
  
```  
void TextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFind`  
 찾을 수 없는 텍스트 문자열이 포함 됩니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 실패 한 호출 직후이 메서드를 호출 하는 것이 좋습니다. [FindText](#findtext) 제대로 컨트롤의 내부 검색 상태를 다시 설정 되도록 합니다.  
  
 `lpszFind` 매개 변수를 제공 하는 문자열을 동일한 콘텐츠를 포함 해야 [FindText](#findtext)합니다. 내부 검색 상태를 재설정 한 후이 메서드를 호출 합니다는 [OnTextNotFound](#ontextnotfound) 메서드에 제공 된 검색 문자열입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CRichEditView::FindText](#findtext)합니다.  
  
##  <a name="wrapchanged"></a>CRichEditView::WrapChanged  
 인쇄 특성 변경 된 경우이 함수 호출 ( [SetMargins](#setmargins) 또는 [SetPaperSize](#setpapersize)).  
  
```  
virtual void WrapChanged();
```  
  
### <a name="remarks"></a>설명  
 변경 내용에 응답 하는 다양 한 보기를 편집 하는 방식을 수정 하려면이 함수를 재정의 [m_nWordWrap](#m_nwordwrap) 또는 인쇄 특성 ( [OnPrinterChanged](#onprinterchanged)).  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#163](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [워드 패드 MFC 샘플](../../visual-cpp-samples.md)   
 [CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc 클래스](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditCntrItem 클래스](../../mfc/reference/cricheditcntritem-class.md)
