---
title: CDocument 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocument
- AFXWIN/CDocument
- AFXWIN/CDocument::CDocument
- AFXWIN/CDocument::AddView
- AFXWIN/CDocument::BeginReadChunks
- AFXWIN/CDocument::CanCloseFrame
- AFXWIN/CDocument::ClearChunkList
- AFXWIN/CDocument::ClearPathName
- AFXWIN/CDocument::DeleteContents
- AFXWIN/CDocument::FindChunk
- AFXWIN/CDocument::GetAdapter
- AFXWIN/CDocument::GetDocTemplate
- AFXWIN/CDocument::GetFile
- AFXWIN/CDocument::GetFirstViewPosition
- AFXWIN/CDocument::GetNextView
- AFXWIN/CDocument::GetPathName
- AFXWIN/CDocument::GetThumbnail
- AFXWIN/CDocument::GetTitle
- AFXWIN/CDocument::InitializeSearchContent
- AFXWIN/CDocument::IsModified
- AFXWIN/CDocument::IsSearchAndOrganizeHandler
- AFXWIN/CDocument::LoadDocumentFromStream
- AFXWIN/CDocument::OnBeforeRichPreviewFontChanged
- AFXWIN/CDocument::OnChangedViewList
- AFXWIN/CDocument::OnCloseDocument
- AFXWIN/CDocument::OnCreatePreviewFrame
- AFXWIN/CDocument::OnDocumentEvent
- AFXWIN/CDocument::OnDrawThumbnail
- AFXWIN/CDocument::OnLoadDocumentFromStream
- AFXWIN/CDocument::OnNewDocument
- AFXWIN/CDocument::OnOpenDocument
- AFXWIN/CDocument::OnPreviewHandlerQueryFocus
- AFXWIN/CDocument::OnPreviewHandlerTranslateAccelerator
- AFXWIN/CDocument::OnRichPreviewBackColorChanged
- AFXWIN/CDocument::OnRichPreviewFontChanged
- AFXWIN/CDocument::OnRichPreviewSiteChanged
- AFXWIN/CDocument::OnRichPreviewTextColorChanged
- AFXWIN/CDocument::OnSaveDocument
- AFXWIN/CDocument::OnUnloadHandler
- AFXWIN/CDocument::PreCloseFrame
- AFXWIN/CDocument::ReadNextChunkValue
- AFXWIN/CDocument::ReleaseFile
- AFXWIN/CDocument::RemoveChunk
- AFXWIN/CDocument::RemoveView
- AFXWIN/CDocument::ReportSaveLoadException
- AFXWIN/CDocument::SaveModified
- AFXWIN/CDocument::SetChunkValue
- AFXWIN/CDocument::SetModifiedFlag
- AFXWIN/CDocument::SetPathName
- AFXWIN/CDocument::SetTitle
- AFXWIN/CDocument::UpdateAllViews
- AFXWIN/CDocument::OnFileSendMail
- AFXWIN/CDocument::OnUpdateFileSendMail
- AFXWIN/CDocument::m_bGetThumbnailMode
- AFXWIN/CDocument::m_bPreviewHandlerMode
- AFXWIN/CDocument::m_bSearchMode
- AFXWIN/CDocument::m_clrRichPreviewBackColor
- AFXWIN/CDocument::m_clrRichPreviewTextColor
- AFXWIN/CDocument::m_lfRichPreviewFont
dev_langs:
- C++
helpviewer_keywords:
- CDocument [MFC], CDocument
- CDocument [MFC], AddView
- CDocument [MFC], BeginReadChunks
- CDocument [MFC], CanCloseFrame
- CDocument [MFC], ClearChunkList
- CDocument [MFC], ClearPathName
- CDocument [MFC], DeleteContents
- CDocument [MFC], FindChunk
- CDocument [MFC], GetAdapter
- CDocument [MFC], GetDocTemplate
- CDocument [MFC], GetFile
- CDocument [MFC], GetFirstViewPosition
- CDocument [MFC], GetNextView
- CDocument [MFC], GetPathName
- CDocument [MFC], GetThumbnail
- CDocument [MFC], GetTitle
- CDocument [MFC], InitializeSearchContent
- CDocument [MFC], IsModified
- CDocument [MFC], IsSearchAndOrganizeHandler
- CDocument [MFC], LoadDocumentFromStream
- CDocument [MFC], OnBeforeRichPreviewFontChanged
- CDocument [MFC], OnChangedViewList
- CDocument [MFC], OnCloseDocument
- CDocument [MFC], OnCreatePreviewFrame
- CDocument [MFC], OnDocumentEvent
- CDocument [MFC], OnDrawThumbnail
- CDocument [MFC], OnLoadDocumentFromStream
- CDocument [MFC], OnNewDocument
- CDocument [MFC], OnOpenDocument
- CDocument [MFC], OnPreviewHandlerQueryFocus
- CDocument [MFC], OnPreviewHandlerTranslateAccelerator
- CDocument [MFC], OnRichPreviewBackColorChanged
- CDocument [MFC], OnRichPreviewFontChanged
- CDocument [MFC], OnRichPreviewSiteChanged
- CDocument [MFC], OnRichPreviewTextColorChanged
- CDocument [MFC], OnSaveDocument
- CDocument [MFC], OnUnloadHandler
- CDocument [MFC], PreCloseFrame
- CDocument [MFC], ReadNextChunkValue
- CDocument [MFC], ReleaseFile
- CDocument [MFC], RemoveChunk
- CDocument [MFC], RemoveView
- CDocument [MFC], ReportSaveLoadException
- CDocument [MFC], SaveModified
- CDocument [MFC], SetChunkValue
- CDocument [MFC], SetModifiedFlag
- CDocument [MFC], SetPathName
- CDocument [MFC], SetTitle
- CDocument [MFC], UpdateAllViews
- CDocument [MFC], OnFileSendMail
- CDocument [MFC], OnUpdateFileSendMail
- CDocument [MFC], m_bGetThumbnailMode
- CDocument [MFC], m_bPreviewHandlerMode
- CDocument [MFC], m_bSearchMode
- CDocument [MFC], m_clrRichPreviewBackColor
- CDocument [MFC], m_clrRichPreviewTextColor
- CDocument [MFC], m_lfRichPreviewFont
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 696b0d63a7b81b550e99981f199132713fe8a6ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdocument-class"></a>CDocument 클래스
사용자 정의 문서 클래스에 대한 기본 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDocument : public CCmdTarget  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDocument::CDocument](#cdocument)|`CDocument` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDocument::AddView](#addview)|문서에 뷰를 연결 합니다.|  
|[CDocument::BeginReadChunks](#beginreadchunks)|초기화 읽기를 청크 합니다.|  
|[CDocument::CanCloseFrame](#cancloseframe)|고급 재정의할 수 있습니다. 이 문서를 보지 프레임 창을 닫기 전에 호출 됩니다.|  
|[CDocument::ClearChunkList](#clearchunklist)|청크 목록을 지웁니다.|  
|[CDocument::ClearPathName](#clearpathname)|문서 개체의 경로 지웁니다.|  
|[CDocument::DeleteContents](#deletecontents)|문서의 정리를 수행 하도록 호출 됩니다.|  
|[CDocument::FindChunk](#findchunk)|지정 된 GUID 가진 청크를 찾습니다.|  
|[CDocument::GetAdapter](#getadapter)|개체를 구현 하는 데 대 한 포인터를 반환 `IDocument` 인터페이스입니다.|  
|[CDocument::GetDocTemplate](#getdoctemplate)|문서의 유형을 설명 하는 서식 파일에 대 한 포인터를 반환 합니다.|  
|[CDocument::GetFile](#getfile)|포인터를 원하는 반환 `CFile` 개체입니다.|  
|[CDocument::GetFirstViewPosition](#getfirstviewposition)|첫 번째 위치를 반환 뷰만 목록에서 반복 시작 하는 데 사용 합니다.|  
|[CDocument::GetNextView](#getnextview)|문서에 연결 된 뷰 목록을 반복 합니다.|  
|[CDocument::GetPathName](#getpathname)|문서의 데이터 파일의 경로 반환합니다.|  
|[CDocument::GetThumbnail](#getthumbnail)|비트맵의 미리 보기를 표시할 축소판 공급자에서 사용할을 만들기 위해 호출 됩니다.|  
|[CDocument::GetTitle](#gettitle)|문서의 제목을 반환합니다.|  
|[CDocument::InitializeSearchContent](#initializesearchcontent)|검색 처리기에 대 한 콘텐츠 검색을 초기화 하기 위해 호출 합니다.|  
|[CDocument::IsModified](#ismodified)|문서의 마지막으로 저장 된 이후 수정 되었는지 여부를 나타냅니다.|  
|[CDocument::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|지시 있는지 여부를이 인스턴스의 `CDocument` 검색 및 구성 처리기에 대 한 개체를 만든 합니다.|  
|[CDocument::LoadDocumentFromStream](#loaddocumentfromstream)|스트림에서 문서 데이터를 로드 하기 위해 호출 합니다.|  
|[CDocument::OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|서식 있는 미리 보기 글꼴 변경 되기 전에 호출 됩니다.|  
|[CDocument::OnChangedViewList](#onchangedviewlist)|보기에 추가 하거나 문서에서 제거 된 후 호출 됩니다.|  
|[CDocument::OnCloseDocument](#onclosedocument)|호출 하 여 문서를 닫습니다.|  
|[CDocument::OnCreatePreviewFrame](#oncreatepreviewframe)|서식 있는 미리 보기에 대 한 미리 보기 프레임을 만드는 데 필요한 프레임 워크에서 호출 됩니다.|  
|[CDocument::OnDocumentEvent](#ondocumentevent)|문서 이벤트에 대 한 응답으로 프레임 워크에서 호출 됩니다.|  
|[CDocument::OnDrawThumbnail](#ondrawthumbnail)|미리 보기의 콘텐츠를 그리는 데 파생된 클래스에서이 메서드를 재정의 합니다.|  
|[CDocument::OnLoadDocumentFromStream](#onloaddocumentfromstream)|스트림에서 문서 데이터를 로드 하는 데 필요한 프레임 워크에서 호출 됩니다.|  
|[CDocument::OnNewDocument](#onnewdocument)|새 문서를 만들기 위해 호출 합니다.|  
|[CDocument::OnOpenDocument](#onopendocument)|기존 문서 열기 위해 호출 됩니다.|  
|[CDocument::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|미리 보기 처리기 포커스 받기 함수 호출에서 HWND를 반환 하는 전달 합니다.|  
|[CDocument::OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|미리 보기 처리기 미리 보기 처리기 실행 중인 프로세스의 메시지 펌프에서 위로 전달 키 입력을 처리 하도록 지시 합니다.|  
|[CDocument::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|서식 있는 미리 보기 배경색 변경 될 때 호출 됩니다.|  
|[CDocument::OnRichPreviewFontChanged](#onrichpreviewfontchanged)|서식 있는 미리 보기 글꼴 변경 될 때 호출 됩니다.|  
|[CDocument::OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|서식 있는 미리 보기 사이트 변경 될 때 호출 됩니다.|  
|[CDocument::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|서식 있는 미리 보기 텍스트 색이 변경 되 면 호출 됩니다.|  
|[CDocument::OnSaveDocument](#onsavedocument)|디스크에 문서를 저장 하기 위해 호출 합니다.|  
|[CDocument::OnUnloadHandler](#onunloadhandler)|미리 보기 처리기 언로드되는 때 프레임 워크에서 호출 됩니다.|  
|[CDocument::PreCloseFrame](#precloseframe)|프레임 창을 닫기 전에 호출 됩니다.|  
|[CDocument::ReadNextChunkValue](#readnextchunkvalue)|다음 청크 값을 읽습니다.|  
|[CDocument::ReleaseFile](#releasefile)|다른 응용 프로그램에서 사용 하기 위해 사용할 수 있도록 파일을 해제 합니다.|  
|[CDocument::RemoveChunk](#removechunk)|지정 된 GUID 가진 청크를 제거합니다.|  
|[CDocument::RemoveView](#removeview)|문서에서 보기를 분리합니다.|  
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|고급 재정의할 수 있습니다. 열린 때 호출 또는 저장 작업 예외로 인해 완료할 수 없습니다.|  
|[CDocument::SaveModified](#savemodified)|고급 재정의할 수 있습니다. 문서를 저장할지 여부는 사용자에 게 확인 하기 위해 호출 합니다.|  
|[CDocument::SetChunkValue](#setchunkvalue)|청크 값을 설정합니다.|  
|[CDocument::SetModifiedFlag](#setmodifiedflag)|마지막으로 저장 한 후 문서 수정한 나타내는 플래그를 설정 합니다.|  
|[CDocument::SetPathName](#setpathname)|문서에서 사용 하는 데이터 파일의 경로 설정 합니다.|  
|[CDocument::SetTitle](#settitle)|문서의 제목을 설정합니다.|  
|[CDocument::UpdateAllViews](#updateallviews)|수정 된 문서는 모든 보기에 알립니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDocument::OnFileSendMail](#onfilesendmail)|연결 된 문서와 메일 메시지를 보냅니다.|  
|[CDocument::OnUpdateFileSendMail](#onupdatefilesendmail)|전자 메일 서비스를 사용할 수 있는 경우 메일 보내기 명령을 활성화 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDocument::m_bGetThumbnailMode](#m_bgetthumbnailmode)|지정 하는 `CDocument` 미리 보기에 대 한 dllhost 개체가 있습니다. 체크 인할 수 `CView::OnDraw`합니다.|  
|[CDocument::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|지정 하는 `CDocument` 에 대 한 prevhost 개체가 `Rich Preview`합니다. 체크 인할 수 `CView::OnDraw`합니다.|  
|[CDocument::m_bSearchMode](#m_bsearchmode)|지정 하는 `CDocument` 인덱서 또는 다른 검색 응용 프로그램에서 개체를 만든 합니다.|  
|[CDocument::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|서식 있는 미리 보기 창의 배경색을 지정합니다. 이 색은 호스트에 의해 설정 됩니다.|  
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|서식 있는 미리 보기 창의 전경색을 지정합니다. 이 색은 호스트에 의해 설정 됩니다.|  
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|서식 있는 미리 보기 창에 대 한 텍스트 글꼴을 지정합니다. 이 글꼴 정보 호스트에 의해 설정 됩니다.|  
  
## <a name="remarks"></a>설명  
 문서는 사용자가 일반적으로 파일 열기 명령을 사용 하 여 열립니다을 파일 저장 명령을 사용 하 여 저장 하는 데이터의 단위를 나타냅니다.  
  
 **CDocument** 문서 만들기, 로드 및 저장 같은 표준 작업을 지원 합니다. 프레임 워크에 정의 된 인터페이스를 사용 하 여 문서를 조작 **CDocument**합니다.  
  
 응용 프로그램 문서의; 둘 이상의 유형을 지원할 수 있습니다. 예, 응용 프로그램 스프레드시트 및 텍스트 문서를 모두 지원할 수 있습니다. 각 유형의 문서에 연결 된 문서 템플릿; 문서 서식 파일 해당 형식의 문서에 사용 되는 리소스 (예: 메뉴, 아이콘 또는 액셀러레이터 키 테이블)을 지정 합니다. 각 문서에 연결 된에 대 한 포인터 `CDocTemplate` 개체입니다.  
  
 사용자가 통해 문서 상호 작용은 [CView](../../mfc/reference/cview-class.md) 연결 된 개체입니다. 보기의 문서 프레임 창에 이미지를 렌더링 하 고 문서에 대 한 작업으로 사용자 입력 해석 합니다. 문서에 연결 된 여러 뷰가 있을 수 있습니다. 사용자가 문서에서 창을 열면 프레임 워크는 뷰를 만들고 문서에 연결 합니다. 문서 서식 파일 보기 및 프레임 창의 어떤 유형의 각 문서 유형에 표시할 때 사용을 지정 합니다.  
  
 문서 프레임 워크의 표준의 일부는 라우팅 명령 및 결과적으로 표준 사용자 인터페이스 구성 요소 (예: 파일 저장을 메뉴 항목)에서 명령을 수신 합니다. 문서를 현재 보기에 의해 전달 되는 명령을 받습니다. 문서에서 지정된 된 명령을 처리 하지 않는 경우를 통해 관리 하는 서식 파일에 명령을 전달 합니다.  
  
 문서 데이터가 수정 될 때 이러한 수정 내용을 반영 해야 각 해당 보기. **CDocument** 제공는 [UpdateAllViews](#updateallviews) 멤버 함수가 보기 수 자동으로 그려지도록 필요에 따라 하므로 이러한 변경 사항을 보기를 알릴 수 있습니다. 프레임 워크에는 수정 된 파일을 닫기 전에 저장 하 라는 메시지 표시 합니다.  
  
 일반 응용 프로그램에서 문서를 구현 하려면 다음을 수행 해야 합니다.  
  
-   클래스를 파생 **CDocument** 각 문서 유형에 대 한 합니다.  
  
-   각 문서의 데이터를 저장 하려면 멤버 변수를 추가 합니다.  
  
-   읽기 및 문서의 데이터를 수정 하기 위한 멤버 함수를 구현 합니다. 문서의 뷰는 이러한 멤버 함수 중 가장 중요 한 사용자입니다.  
  
-   재정의 [cobject:: Serialize](../../mfc/reference/cobject-class.md#serialize) 디스크에서 문서의 데이터를 읽고 쓰는 데 문서 클래스에 멤버 함수입니다.  
  
 **CDocument** (MAPI) 전자 메일 서비스를 사용할 수 있는 경우 메일을 통해 문서를 보내는 기능을 지원 합니다. 문서를 참조 [MAPI](../../mfc/mapi.md) 및 [MFC의 MAPI 지원](../../mfc/mapi-support-in-mfc.md)합니다.  
  
 대 한 자세한 내용은 **CDocument**, 참조 [Serialization](../../mfc/serialization-in-mfc.md), [문서/뷰 아키텍처 항목](../../mfc/document-view-architecture.md), 및 [문서/뷰 만들기](../../mfc/document-view-creation.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocument`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="addview"></a>  CDocument::AddView  
 문서에 뷰를 연결 하려면이 함수를 호출 합니다.  
  
```  
void AddView(CView* pView);
```  
  
### <a name="parameters"></a>매개 변수  
 `pView`  
 추가 하려는 보기를 가리킵니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 지정된 된 뷰 문서와 관련 된 보기 목록에 추가 함수는 또한이 문서에 해당 보기의 문서 포인터를 설정합니다. 프레임 워크; 문서를 새로 만든된 뷰 개체를 연결 하는 경우이 함수 호출 이 창에 분할 될 때 또는 새 파일, 파일 열기 또는 새 창 명령에 대 한 응답으로 발생 합니다.  
  
 수동으로 만들고 뷰를 연결 하는 경우에이 함수를 호출 합니다. 일반적으로 문서 및 뷰를 정의 하 여 연결 프레임 워크 수는 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 문서 클래스, 클래스 뷰 및 프레임 창 클래스를 연결 하는 개체입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]  
  
##  <a name="beginreadchunks"></a>  CDocument::BeginReadChunks  
 초기화 읽기를 청크 합니다.  
  
```  
virtual void BeginReadChunks ();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="cancloseframe"></a>  CDocument::CanCloseFrame  
 문서를 표시 하는 프레임 창을 닫기 전에 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFrame`  
 문서에 연결 하는 보기의 프레임 창을 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 프레임 창을; 안전 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 프레임 창과 문서를 표시 되어 있는지 확인 합니다. 지정 된 프레임 창을 마지막 한 문서를 표시 하는 경우 함수 수정 된 경우에 문서를 저장 하 라는 메시지 표시 합니다. 프레임 창의 닫을 때 특별 한 처리를 수행 하려는 경우이 함수를 재정의 합니다. 고급 재정의할 수 있습니다.  
  
##  <a name="cdocument"></a>  CDocument::CDocument  
 생성 된 **CDocument** 개체입니다.  
  
```  
CDocument();
```  
  
### <a name="remarks"></a>설명  
 프레임 워크를 문서 만들기를 처리합니다. 재정의 [OnNewDocument](#onnewdocument) 문서별 기준 초기화를 수행 하는 멤버 함수 단일 문서 SDI (인터페이스) 응용 프로그램에서 특히 중요 합니다.  
  
##  <a name="clearchunklist"></a>  CDocument::ClearChunkList  
 청크 목록을 지웁니다.  
  
```  
virtual void ClearChunkList ();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="clearpathname"></a>  CDocument::ClearPathName  
 문서 개체의 경로 지웁니다.  
  
```  
virtual void ClearPathName();
```  
  
### <a name="remarks"></a>설명  
 경로에서 선택을 취소 한 `CDocument` 개체가 문서가 저장 된 다음 사용자를 표시 하도록 응용 프로그램. 이렇게 하면 한 **저장** 명령 처럼 작동 합니다.는 **다른 이름으로 저장** 명령입니다.  
  
##  <a name="deletecontents"></a>  CDocument::DeleteContents  
 삭제 하지 않고 문서의 데이터를 삭제 하기 위해 프레임 워크에서 호출 된 **CDocument** 개체 자체입니다.  
  
```  
virtual void DeleteContents();
```  
  
### <a name="remarks"></a>설명  
 문서가 소멸 될 예정 바로 전에 호출 됩니다. 이 재사용 되기 전에 문서 비어 있는지 확인 하는 것이 라고도 합니다. 이 특히 중요 한 문서를 사용 하 여 SDI 응용 프로그램에 대 한 문서에는 사용자가 만들거나 다른 문서를 열 때마다 다시 사용 됩니다. "편집 모두 지우기" 또는 문서의 데이터를 모두 삭제 하 여 비슷한 명령을 구현 하려면이 함수를 호출 합니다. 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 문서에서 데이터를 삭제 하려면이 함수를 재정의 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]  
  
##  <a name="findchunk"></a>  CDocument::FindChunk  
 지정 된 GUID 가진 청크를 찾습니다.  
  
```  
virtual POSITION FindChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>매개 변수  
 `guid`  
 찾을 청크의 GUID를 지정 합니다.  
  
 `pid`  
 찾을 청크의 PID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우 내부 청크 목록에서 위치입니다. 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getadapter"></a>  CDocument::GetAdapter  
 구현 하는 개체에 대 한 포인터를 반환 된 `IDocument` 인터페이스입니다.  
  
```  
virtual ATL::IDocument* GetAdapter();
```  
  
### <a name="return-value"></a>반환 값  
 구현 하는 개체에 대 한 포인터는 `IDocument` 인터페이스입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getdoctemplate"></a>  CDocument::GetDocTemplate  
 이 문서 종류에 대 한 서식 파일에 대 한 포인터를 가져오려면이 함수를 호출 합니다.  
  
```  
CDocTemplate* GetDocTemplate() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 문서 유형에 대 한 문서 서식 파일에 대 한 포인터 또는 **NULL** 문서 문서 서식 파일에서 관리 되지 않는 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]  
  
##  <a name="getfile"></a>  CDocument::GetFile  
 이 멤버 함수에 포인터를 얻으려면 호출는 `CFile` 개체입니다.  
  
```  
virtual CFile* GetFile(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFileName`  
 문자열은 원하는 파일을 경로입니다. 상대 또는 절대 경로일 수 있습니다.  
  
 `pError`  
 작업의 완료 상태를 나타내는 기존 파일 예외 개체에 대 한 포인터입니다.  
  
 `nOpenFlags`  
 공유 및 액세스 모드입니다. 파일을 열 때 수행할 동작을 지정 합니다. CFile 생성자에 나열 된 옵션을 결합할 수 [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) 비트 OR를 사용 하 여 (&#124;) 연산자. 에 대 한 액세스 권한 및 하나의 공유 옵션은 필수 사항이 고, **modeCreate** 및 **modeNoInherit** 모드는 선택 사항입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CFile` 개체입니다.  
  
##  <a name="getfirstviewposition"></a>  CDocument::GetFirstViewPosition  
 문서와 관련 된 보기 목록에서 첫 번째 보기의 위치를 가져오려면이 함수를 호출 합니다.  
  
```  
virtual POSITION GetFirstViewPosition() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **위치** 와 반복에 대해 사용할 수 있는 값의 [GetNextView](#getnextview) 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="getnextview"></a>  CDocument::GetNextView  
 문서 보기의 모든 반복 하려면이 함수를 호출 합니다.  
  
```  
virtual CView* GetNextView(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `rPosition`  
 에 대 한 참조는 **위치** 대 한 이전 호출에서 반환 된 값은 `GetNextView` 또는 [GetFirstViewPosition](#getfirstviewposition) 멤버 함수입니다. 이 값이 아니어야 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 로 식별 되는 보기에 대 한 포인터 `rPosition`합니다.  
  
### <a name="remarks"></a>설명  
 로 식별 되는 뷰를 반환 하는 함수 `rPosition` 다음 설정 `rPosition` 에 **위치** 목록에서 다음 보기의 값입니다. 검색된 보기는 목록에서 마지막 `rPosition` 로 설정 된 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="getpathname"></a>  CDocument::GetPathName  
 문서 디스크 파일의 정규화 된 경로 가져오려면이 함수를 호출 합니다.  
  
```  
const CString& GetPathName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 문서의 정규화 된 경로입니다. 문서 저장 되지 않은 있거나 연결 된 디스크 파일이 없는 경우이 문자열이 비어 있습니다.  
  
##  <a name="getthumbnail"></a>  CDocument::GetThumbnail  
 미리 보기를 표시할 축소판 공급자에서 사용할 비트맵을 만듭니다.  
  
```  
virtual BOOL GetThumbnail(
    UINT cx,  
    HBITMAP* phbmp,  
    DWORD* pdwAlpha);
```  
  
### <a name="parameters"></a>매개 변수  
 `cx`  
 비트맵의 높이 너비를 지정합니다.  
  
 `phbmp`  
 함수는 성공적으로 반환 될 때 비트맵에 대 한 핸들을 포함 합니다.  
  
 `pdwAlpha`  
 함수에서 성공적으로 반환 되는 알파 채널 값을 지정 하는 DWORD를 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 미리 보기에 대 한 비트맵을 성공적으로 만들어진 경우 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="gettitle"></a>  CDocument::GetTitle  
 일반적으로 문서의 파일 이름에서 파생 되는 문서의 제목을 가져오려면이 함수를 호출 합니다.  
  
```  
const CString& GetTitle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 문서의 제목입니다.  
  
##  <a name="initializesearchcontent"></a>  CDocument::InitializeSearchContent  
 검색 처리기에 대 한 콘텐츠 검색을 초기화 하기 위해 호출 합니다.  
  
```  
virtual void InitializeSearchContent ();
```  
  
### <a name="remarks"></a>설명  
 콘텐츠 검색을 초기화 하기 위해 파생된 클래스에서이 메서드를 재정의 합니다. 내용은 부분으로 구분 된 문자열 이어야 합니다 ";"입니다. 예를 들어 "point; 사각형입니다. ole 항목 "입니다.  
  
##  <a name="ismodified"></a>  CDocument::IsModified  
 문서의 마지막으로 저장 된 이후 수정 되었는지 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
virtual BOOL IsModified();
```  
  
### <a name="return-value"></a>반환 값  
 마지막으로 저장 된; 이후 수정 되었는지 문서 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="issearchandorganizehandler"></a>  CDocument::IsSearchAndOrganizeHandler  
 지시 있는지 여부를이 인스턴스의 `CDocument` 검색 및 구성 처리기에 대 한 생성 합니다.  
  
```  
BOOL IsSearchAndOrganizeHandler() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 경우의이 인스턴스에 `CDocument` 검색 및 구성 처리기에 대 한 생성 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 반환 현재 `TRUE` 프로세스 서버를 벗어난에 구현 된 풍부한 미리 보기 처리기에 대 한 합니다. 이 함수를 반환 하도록 프로그램 응용 프로그램 수준 (m_bPreviewHandlerMode, m_bSearchMode, m_bGetThumbnailMode) 적절 한 플래그를 설정할 수 있습니다 `TRUE`합니다.  
  
##  <a name="loaddocumentfromstream"></a>  CDocument::LoadDocumentFromStream  
 스트림에서 문서 데이터를 로드 하기 위해 호출 합니다.  
  
```  
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,  
    DWORD dwGrfMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStream`  
 스트림에 대 한 포인터입니다. 이 스트림에 셸에서 제공 됩니다.  
  
 `dwGrfMode`  
 스트림에 액세스 모드입니다.  
  
### <a name="return-value"></a>반환 값  
 로드 작업에 성공 하면 그렇지 않으면 HRESULT 오류 코드와 함께 S_OK입니다.  
  
### <a name="remarks"></a>설명  
 스트림에서 데이터를 로드 하는 방법을 사용자 지정 하는 파생된 클래스에서이 메서드를 재정의할 수 있습니다.  
  
##  <a name="m_bgetthumbnailmode"></a>  CDocument::m_bGetThumbnailMode  
 지정 하는 `CDocument` 미리 보기에 대 한 dllhost 개체가 있습니다. 체크 인할 수 `CView::OnDraw`합니다.  
  
```  
BOOL m_bGetThumbnailMode;  
```  
  
### <a name="remarks"></a>설명  
 `TRUE` 문서 미리 보기에 대 한 dllhost에서 생성 되었는지 나타냅니다.  
  
##  <a name="m_bpreviewhandlermode"></a>  CDocument::m_bPreviewHandlerMode  
 지정 된 `CDocument` 개체가 prevhost 풍부한 미리 보기에 대 한 합니다. 체크 인할 수 `CView::OnDraw`합니다.  
  
```  
BOOL m_bPreviewHandlerMode;  
```  
  
### <a name="remarks"></a>설명  
 `TRUE` 서식 있는 미리 보기에 대 한 문서 prevhost 하 여 생성 되었는지 나타냅니다.  
  
##  <a name="m_bsearchmode"></a>  CDocument::m_bSearchMode  
 지정 하는 `CDocument` 인덱서 또는 다른 검색 응용 프로그램에서 개체가 만들어진 합니다.  
  
```  
BOOL m_bSearchMode;  
```  
  
### <a name="remarks"></a>설명  
 `TRUE` 인덱서 또는 다른 검색 응용 프로그램에서 문서를 만든 나타냅니다.  
  
##  <a name="m_clrrichpreviewbackcolor"></a>  CDocument::m_clrRichPreviewBackColor  
 서식 있는 미리 보기 창의 배경색을 지정 합니다. 이 색은 호스트에 의해 설정 됩니다.  
  
```  
COLORREF m_clrRichPreviewBackColor;  
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="m_clrrichpreviewtextcolor"></a>  CDocument::m_clrRichPreviewTextColor  
 서식 있는 미리 보기 창의 전경색을 지정합니다. 이 색은 호스트에 의해 설정 됩니다.  
  
```  
COLORREF m_clrRichPreviewTextColor;  
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="m_lfrichpreviewfont"></a>  CDocument::m_lfRichPreviewFont  
 서식 있는 미리 보기 창에 대 한 텍스트 글꼴을 지정합니다. 이 글꼴 정보 호스트에 의해 설정 됩니다.  
  
```  
CFont m_lfRichPreviewFont;  
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="onbeforerichpreviewfontchanged"></a>  CDocument::OnBeforeRichPreviewFontChanged  
 서식 있는 미리 보기 글꼴 변경 되기 전에 호출 됩니다.  
  
```  
virtual void OnBeforeRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="onchangedviewlist"></a>  CDocument::OnChangedViewList  
 보기에 추가 하거나 문서에서 제거 된 후 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnChangedViewList();
```  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현은 인지 확인 마지막 보기 제거 되 고,이 경우 문서를 삭제 합니다. 프레임 워크를 추가 하거나 뷰를 제거 하는 경우에 특별 한 처리를 수행 하려는 경우이 함수를 재정의 합니다. 예를 들어 문서에 연결 된 뷰가 없는 경우에 계속 열려를 원하는 경우이 함수를 재정의 합니다.  
  
##  <a name="onclosedocument"></a>  CDocument::OnCloseDocument  
 문서를 닫을 때, 일반적으로 파일 닫기 명령의 일부로 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnCloseDocument();
```  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현은 제거의 모든 문서 보기에 사용 되는 프레임, 있는 뷰를 닫습니다, 문서 내용을를 정리 하 고 다음 호출에서 [DeleteContents](#deletecontents) 멤버 함수는 문서를 삭제 하려면 데이터입니다.  
  
 프레임 워크는 문서를 닫을 때 처리 하는 특별 한 정리를 수행 하려는 경우이 함수를 재정의 합니다. 예를 들어 문서 데이터베이스의 레코드를 나타내는 경우이 함수는 데이터베이스를 재정의 하는 것이 좋습니다. 재정의에서이 함수의 기본 클래스 버전을 호출 해야 합니다.  
  
##  <a name="oncreatepreviewframe"></a>  CDocument::OnCreatePreviewFrame  
 서식 있는 미리 보기에 대 한 미리 보기 프레임을 만드는 데 필요한 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnCreatePreviewFrame();
```  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 프레임 성공적으로 만들어지면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="ondocumentevent"></a>  CDocument::OnDocumentEvent  
 문서 이벤트에 대 한 응답으로 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDocumentEvent(DocumentEvent deEvent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `deEvent`  
 이벤트의 형식을 설명 하는 열거형된 데이터 형식입니다.  
  
### <a name="remarks"></a>설명  
 문서 이벤트 여러 클래스에 영향을 줄 수 있습니다. 이 메서드는 이외의 다른 클래스에 영향을 주는 문서 이벤트를 처리 하는 일을 담당는 [CDocument 클래스](../../mfc/reference/cdocument-class.md)합니다. 현재 문서 이벤트에 응답 해야 하는 유일한 클래스는는 [CDataRecoveryHandler 클래스](../../mfc/reference/cdatarecoveryhandler-class.md)합니다. `CDocument` 클래스에 미치는 영향에 처리를 담당 다른 재정의 가능한 메서드가 `CDocument`합니다.  
  
 다음 표에서 가능한 값에 대 한 `deEvent` 와 해당 하는 이벤트입니다.  
  
|값|해당 하는 이벤트|  
|-----------|-------------------------|  
|`onAfterNewDocument`|새 문서를 만들었습니다.|  
|`onAfterOpenDocument`|새 문서를 열었습니다.|  
|`onAfterSaveDocument`|문서를 저장 합니다.|  
|`onAfterCloseDocument`|문서가 닫혔습니다.|  
  
##  <a name="ondrawthumbnail"></a>  CDocument::OnDrawThumbnail  
 축소판 그림을 그리는 데 파생된 클래스에서이 메서드를 재정의 합니다.  
  
```  
virtual void OnDrawThumbnail(
    CDC& dc,  
    LPRECT lprcBounds);
```  
  
### <a name="parameters"></a>매개 변수  
 `dc`  
 장치 컨텍스트에 대 한 참조입니다.  
  
 `lprcBounds`  
 미리 보기를 그리도록 영역의 경계 사각형을 지정 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="onfilesendmail"></a>  CDocument::OnFileSendMail  
 상주 메일 호스트를 통해 메시지 (있는 경우) 문서와 함께 첨부 보냅니다.  
  
```  
void OnFileSendMail();
```  
  
### <a name="remarks"></a>설명  
 `OnFileSendMail` 호출 [OnSaveDocument](#onsavedocument) (저장) 한 다음 전자 메일을 통해 전송 된 임시 파일에 제목이 없는 및 수정 된 문서를 serialize 하 합니다. 문서 수정 되지 않은 경우 임시 파일은 필요 하지; 원래 전송 됩니다. `OnFileSendMail` MAPI32를 로드합니다. 로드 되지 않았으면 DLL입니다.  
  
 구현 하는 특별 한 `OnFileSendMail` 에 대 한 [COleDocument](../../mfc/reference/coledocument-class.md) 올바르게 복합 파일 핸들입니다.  
  
 **CDocument** (MAPI) 전자 메일 서비스를 사용할 수 있는 경우 메일을 통해 문서를 보내는 기능을 지원 합니다. 문서를 참조 [MAPI 항목](../../mfc/mapi.md) 및 [MFC의 MAPI 지원](../../mfc/mapi-support-in-mfc.md)합니다.  
  
##  <a name="onloaddocumentfromstream"></a>  CDocument::OnLoadDocumentFromStream  
 스트림에서 문서 데이터를 로드 하는 데 필요한 프레임 워크에서 호출 됩니다.  
  
```  
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,  
    DWORD grfMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStream`  
 들어오는 스트림에 대 한 포인터입니다.  
  
 `grfMode`  
 스트림에 액세스 모드입니다.  
  
### <a name="return-value"></a>반환 값  
 로드가 성공 하면 s_ok이 고 그렇지 않으면 오류 코드가 있습니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="onnewdocument"></a>  CDocument::OnNewDocument  
 새 파일 명령 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnNewDocument();
```  
  
### <a name="return-value"></a>반환 값  
 문서를 초기화 했습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현에서는 호출 하는 [DeleteContents](#deletecontents) 멤버 함수를 확인 하는 문서 비어 다음 깨끗 새 문서를 표시 합니다. 새 문서에 대 한 데이터 구조를 초기화 하려면이 함수를 재정의 합니다. 재정의에서이 함수의 기본 클래스 버전을 호출 해야 합니다.  
  
 SDI 응용 프로그램에서 새 파일 명령을 선택한 경우에 프레임 워크를 새로 만드는 대신 기존 문서를 다시 초기화 하려면이 함수를 사용 합니다. 사용자가 다중 문서 MDI (인터페이스) 응용 프로그램에서 새 파일을 한 경우에 프레임 워크 될 때마다 새 문서를 만들고를 초기화 하는 데이 함수를 호출 합니다. SDI 응용 프로그램에 적용 하려면 새 파일 명령에 대 한 생성자에서이 함수 대신에 초기화 코드를 배치 해야 합니다.  
  
 에서는 인 사례 `OnNewDocument` 두 번 호출 됩니다. 이 문서는 ActiveX 문서 서버로 포함 된 경우에 발생 합니다. 함수를 처음 호출 됩니다는 `CreateInstance` 메서드 (에 의해 노출는 `COleObjectFactory`-파생 클래스) 및에서 두 번째 시간은 `InitNew` 메서드 (의해 노출 되는 `COleServerDoc`-파생 클래스).  
  
### <a name="example"></a>예제  
 다음 예제는 문서 개체를 초기화 하는 대체 방법이 설명 합니다.  
  
 [!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
##  <a name="onopendocument"></a>  CDocument::OnOpenDocument  
 파일 열기 명령 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszPathName`  
 문서를 열 수의 경로를 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 문서를 로드 했습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현은 호출 지정된 된 파일을 엽니다는 [DeleteContents](#deletecontents) 문서 비어 있는지 확인 하려면 함수 호출 [cobject:: Serialize](../../mfc/reference/cobject-class.md#serialize) 읽을 파일의 수 내용 하 고 깨끗 문서를 표시 합니다. 보관 메커니즘 또는 파일 메커니즘 이외의 항목을 사용 하려는 경우이 함수를 재정의 합니다. 예를 들어 문서 위치 별도 파일 보다는 데이터베이스의 레코드를 나타내며 응용 프로그램을 작성할 수 있습니다.  
  
 이 함수를 사용 하 여 기존 다시 초기화 하도록 프레임 워크 SDI 응용 프로그램에서 파일 열기 명령을 선택한 경우에 **CDocument** 새로 만드는 것 보다 개체입니다. 프레임 워크가 생성 하는 새 사용자가 MDI 응용 프로그램에서 파일 열기 선택, **CDocument** 개체 때마다 다음 초기화 하는 데이 함수를 호출 합니다. 파일 열기 명령 SDI 응용 프로그램에 적용 하려면에 대 한 생성자에서이 함수 대신에 초기화 코드를 배치 해야 합니다.  
  
### <a name="example"></a>예제  
 다음 예제는 문서 개체를 초기화 하는 대체 방법이 설명 합니다.  
  
 [!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]  
  
##  <a name="onpreviewhandlerqueryfocus"></a>  CDocument::OnPreviewHandlerQueryFocus  
 미리 보기 처리기 HWND 검색 호출에서 반환할 수를 알려는 `GetFocus` 함수입니다.  
  
```  
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `phwnd`  
 [out] 이 메서드가 반환 될 때 호출에서 반환 된 HWND에 대 한 포인터를 포함 된 `GetFocus` 미리 보기 처리기 포그라운드 스레드에서 함수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 반환 또는 그렇지 않으면 오류 값을 추가 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="onpreviewhandlertranslateaccelerator"></a>  CDocument::OnPreviewHandlerTranslateAccelerator  
 미리 보기 처리기 미리 보기 처리기 실행 중인 프로세스의 메시지 펌프에서 위로 전달 키 입력을 처리 하도록 지시 합니다.  
  
```  
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```  
  
### <a name="parameters"></a>매개 변수  
 `pmsg`  
 [in] 창 메시지에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 미리 보기 처리기에서 키 입력 메시지를 처리할 수, 처리기를 처리 하 고 S_OK를 반환 합니다. 통해 호스트에 제공 하는 미리 보기 처리기 키 입력 메시지를 처리할 수 없는 경우 `IPreviewHandlerFrame::TranslateAccelerator`합니다. 호스트에서 메시지를 처리 하는 경우이 메서드는 S_OK를 반환 합니다. 호스트에서 메시지를 처리 하지 않습니다,이 메서드는 S_FALSE를 반환 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="onrichpreviewbackcolorchanged"></a>  CDocument::OnRichPreviewBackColorChanged  
 서식 있는 미리 보기 배경색 변경 될 때 호출 됩니다.  
  
```  
virtual void OnRichPreviewBackColorChanged();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="onrichpreviewfontchanged"></a>  CDocument::OnRichPreviewFontChanged  
 서식 있는 미리 보기 글꼴 변경 될 때 호출 됩니다.  
  
```  
virtual void OnRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="onrichpreviewsitechanged"></a>  CDocument::OnRichPreviewSiteChanged  
 서식 있는 미리 보기 사이트 변경 될 때 호출 됩니다.  
  
```  
virtual void OnRichPreviewSiteChanged();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="onrichpreviewtextcolorchanged"></a>  CDocument::OnRichPreviewTextColorChanged  
 서식 있는 미리 보기 텍스트 색이 변경 되 면 호출 됩니다.  
  
```  
virtual void OnRichPreviewTextColorChanged();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="onsavedocument"></a>  CDocument::OnSaveDocument  
 파일 저장 또는 다른 이름으로 저장 명령의 일환으로 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszPathName`  
 파일 저장 되어야 하는 정규화 된 경로를 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 문서 저장 되었습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현은 호출 지정된 된 파일을 엽니다 [cobject:: Serialize](../../mfc/reference/cobject-class.md#serialize) 문서의 데이터를 쓸 파일을을 선택한 다음 표시 문서도 정리 합니다. 프레임 워크는 문서를 저장할 때 특수 한 처리를 수행 하려는 경우이 함수를 재정의 합니다. 예를 들어 문서 위치 별도 파일 보다는 데이터베이스의 레코드를 나타내며 응용 프로그램을 작성할 수 있습니다.  
  
##  <a name="onunloadhandler"></a>  CDocument::OnUnloadHandler  
 미리 보기 처리기 언로드될 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnUnloadHandler();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="onupdatefilesendmail"></a>  CDocument::OnUpdateFileSendMail  
 사용 하도록 설정 된 **ID_FILE_SEND_MAIL** 메일 지원 (MAPI) 되 면 명령 합니다.  
  
```  
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCmdUI`  
 에 대 한 포인터는 [CCmdUI](../../mfc/reference/ccmdui-class.md) 연관 된 개체는 **ID_FILE_SEND_MAIL** 명령입니다.  
  
### <a name="remarks"></a>설명  
 그렇지 않은 경우 제거 함수는 **ID_FILE_SEND_MAIL** 적절 하 게 항목 메뉴 아래 또는 위의 구분 기호를 포함 하 여 메뉴에서 명령을 합니다. MAPI는 경우 사용할 수 MAPI32 합니다. DLL의 경로 win [Mail] 섹션은 합니다. INI 파일의 MAPI = 1입니다. 대부분의 응용 프로그램 파일 메뉴에서이 명령을 배치 합니다.  
  
 **CDocument** (MAPI) 전자 메일 서비스를 사용할 수 있는 경우 메일을 통해 문서를 보내는 기능을 지원 합니다. 문서를 참조 [MAPI 항목](../../mfc/mapi.md) 및 [MFC의 MAPI 지원](../../mfc/mapi-support-in-mfc.md)합니다.  
  
##  <a name="precloseframe"></a>  CDocument::PreCloseFrame  
 이 멤버 함수는 프레임 창 소멸 되기 전에 프레임 워크에서 호출 됩니다.  
  
```  
virtual void PreCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFrame`  
 에 대 한 포인터는 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 보유 하는 연결 된 **CDocument** 개체입니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 정리를 제공 하 고는 기본 클래스를 호출 해야 재정의할 수 있습니다.  
  
 기본값은 `PreCloseFrame` 는 아무 작업도 수행 **CDocument**합니다. **CDocument**-파생 된 클래스 [COleDocument](../../mfc/reference/coledocument-class.md) 및 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) 이 멤버 함수를 사용 합니다.  
  
##  <a name="readnextchunkvalue"></a>  CDocument::ReadNextChunkValue  
 다음 청크 값을 읽습니다.  
  
```  
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppValue`  
 [out] 함수가 반환할 때 `ppValue` 읽은 값을 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="releasefile"></a>  CDocument::ReleaseFile  
 이 멤버 함수는 다른 응용 프로그램에서 사용 하기 위해 사용할 수 있도록 파일을 해제 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void ReleaseFile(
    CFile* pFile,  
    BOOL bAbort);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFile`  
 릴리스될 CFile 개체에 대 한 포인터입니다.  
  
 `bAbort`  
 파일 중 하나를 사용 하 여 해제 되는지를 지정 `CFile::Close` 또는 `CFile::Abort`합니다. **FALSE** 파일이 사용 하 여 출시 될 경우 [CFile::Close](../../mfc/reference/cfile-class.md#close); **TRUE** 파일이 사용 하 여 출시 될 경우 [cfile:: Abort](../../mfc/reference/cfile-class.md#abort)합니다.  
  
### <a name="remarks"></a>설명  
 경우 `bAbort` 은 **TRUE**, `ReleaseFile` 호출 `CFile::Abort`, 파일 해제 됩니다. `CFile::Abort` 예외를 throw 하지 않습니다.  
  
 경우 `bAbort` 은 **FALSE**, `ReleaseFile` 호출 `CFile::Close` 파일 해제 됩니다.  
  
 이 멤버 함수는 파일을 배포 하기 전에 사용자가 작업을 요구 하도록 재정의 합니다.  
  
##  <a name="removechunk"></a>  CDocument::RemoveChunk  
 지정한 GUID 가진 청크를 제거합니다.  
  
```  
virtual void RemoveChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>매개 변수  
 `Guid`  
 제거할 청크의 GUID를 지정 합니다.  
  
 `Pid`  
 제거할 청크의 PID를 지정 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="removeview"></a>  CDocument::RemoveView  
 문서에서 보기를 분리 하려면이 함수를 호출 합니다.  
  
```  
void RemoveView(CView* pView);
```  
  
### <a name="parameters"></a>매개 변수  
 `pView`  
 제거 하 고 보기를 가리킵니다.  
  
### <a name="remarks"></a>설명  
 이 함수는; 문서와 연결 된 보기 목록에서 지정된 된 뷰를 제거 합니다. 또한 보기의 문서 포인터 설정 **NULL**합니다. 이 함수는 프레임 창이 닫혀 또는 분할자 창의 창이 닫힐 때 프레임 워크에서 호출 됩니다.  
  
 보기를 수동으로 분리 하는 경우에이 함수를 호출 합니다. 일반적으로 프레임 워크를 정의 하 여 문서 및 뷰를 분리할 수는 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 문서 클래스, 클래스 뷰 및 프레임 창 클래스를 연결 하는 개체입니다.  
  
 예제를 참조 [AddView](#addview) 샘플 구현에 대 한 합니다.  
  
##  <a name="reportsaveloadexception"></a>  CDocument::ReportSaveLoadException  
 예외가 발생 하는 경우 호출 됩니다 (일반적으로 [CFileException](../../mfc/reference/cfileexception-class.md) 또는 [CArchiveException](../../mfc/reference/carchiveexception-class.md)) 문서를 로드 하거나 저장 하는 동안 합니다.  
  
```  
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,  
    CException* e,  
    BOOL bSaving,  
    UINT nIDPDefault);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszPathName`  
 중인 문서의 이름을 가리키는 저장 되거나 로드 합니다.  
  
 *e*  
 Throw 된 예외를 가리킵니다. 되었을 **NULL**합니다.  
  
 *bSaving*  
 어떤 작업이; 진행 중 이어서 나타내는 플래그입니다. 문서가 저장 된 경우 되 고, 0 문서를 로드 하는 경우에 0이 아닙니다.  
  
 `nIDPDefault`  
 함수는 보다 구체적인 하나를 지정 하지 않은 경우 표시할 오류 메시지의 식별자입니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 예외 개체를 검사 하 고 원인이 구체적으로 설명 하는 오류 메시지를 찾습니다. 특정 메시지 없거나 경우 *e* 은 **NULL**로 지정 된 일반 메시지는 `nIDPDefault` 매개 변수를 사용 합니다. 함수는 다음 오류 메시지가 포함 된 메시지 상자를 표시 합니다. 추가, 사용자 지정 된 오류 메시지를 제공 하려는 경우이 함수를 재정의 합니다. 고급 재정의할 수 있습니다.  
  
##  <a name="savemodified"></a>  CDocument::SaveModified  
 수정 된 문서를 닫을 수 있게 되기 전에 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL SaveModified();
```  
  
### <a name="return-value"></a>반환 값  
 계속 하 고 종결; 문서를 안전 하 게 하는 경우 0이 아닌 문서를 닫을 수 해야 하는 경우 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현은 모든 적용 된 경우 사용자는 문서에 변경 내용을 저장할 것인지 묻는 메시지 상자가 표시 됩니다. 프로그램에 필요한 다른 묻는 프로시저를이 함수를 재정의 합니다. 고급 재정의할 수 있습니다.  
  
##  <a name="setchunkvalue"></a>  CDocument::SetChunkValue  
 청크 값을 설정합니다.  
  
```  
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `pValue`  
 설정할 청크 값을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setmodifiedflag"></a>  CDocument::SetModifiedFlag  
 문서에 대 한 수정을 수행한 후이 함수를 호출 합니다.  
  
```  
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bModified`  
 문서 수정 되었는지 여부를 나타내는 플래그입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 일관 되 게 호출 하 여 프레임 워크는 문서를 닫기 전에 변경 내용을 저장 하 라는 있는지 확인 합니다. 기본값을 사용 해야 하는 일반적으로 **TRUE** 에 대 한는 `bModified` 매개 변수입니다. 정리 문서 (수정 되지 않은)를 표시 하려면 값이 함수를 호출 **FALSE**합니다.  
  
##  <a name="setpathname"></a>  CDocument::SetPathName  
 문서 디스크 파일의 정규화 된 경로 지정 하려면이 함수를 호출 합니다.  
  
```  
virtual void SetPathName(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszPathName`  
 문서에 대 한 경로로 사용할 문자열을 가리킵니다.  
  
 `bAddToMRU`  
 파일 이름에 추가 하는지 여부를 가장 최근에 사용한 (MRU) 파일 목록 결정 합니다. 경우 **TRUE 이면** 파일 이름이 추가 될 경우 **FALSE**, 추가 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 값에 따라 `bAddToMRU` 경로 추가 또는 응용 프로그램에 의해 관리 되는 MRU 목록에 추가 되지 됩니다. 일부 문서는 디스크 파일에 연결 되지 않은 참고 합니다. 프레임 워크에서 사용 되는 파일 열기 및 저장에 대 한 기본 구현을 재정의 하는 경우에이 함수를 호출 합니다.  
  
##  <a name="settitle"></a>  CDocument::SetTitle  
 문서의 제목 (프레임 창의 제목 표시줄에 표시 되는 문자열)을 지정 하려면이 함수를 호출 합니다.  
  
```  
virtual void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszTitle`  
 문서의 제목으로 사용할 문자열을 가리킵니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 호출 문서를 표시 하는 모든 프레임 창의 제목을 업데이트 합니다.  
  
##  <a name="updateallviews"></a>  CDocument::UpdateAllViews  
 문서 수정 된 후이 함수를 호출 합니다.  
  
```  
void UpdateAllViews(
    CView* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSender`  
 문서를 수정 하는 뷰를 가리키는 또는 **NULL** 모든 뷰는 업데이트 해야 하는 경우.  
  
 `lHint`  
 수정에 대 한 정보를 포함합니다.  
  
 `pHint`  
 수정에 대 한 정보를 저장 하는 개체를 가리킵니다.  
  
### <a name="remarks"></a>설명  
 호출한 후에이 함수를 호출 해야는 [SetModifiedFlag](#setmodifiedflag) 멤버 함수입니다. 이 함수에 의해 지정 된 보기를 제외 하 고는 문서에 연결 된 각 보기에 알립니다 `pSender`, 문서를 수정 합니다. 일반적으로 사용자가 뷰를 통해 문서를 변경한 후 뷰 클래스에서이 함수를 호출 합니다.  
  
 이 함수 호출의 [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) 전달 보내는 제외 하 고 문서 보기의 각 멤버 함수 볼 `pHint` 및 `lHint`합니다. 이러한 매개 변수를 사용 하 여 수정 내용에 문서에 대 한 보기에 정보를 전달 합니다. 사용 하 여 정보를 인코딩할 수 `lHint` 정의할 수 있습니다 및/또는 [CObject](../../mfc/reference/cobject-class.md)-수정 작업에 대 한 정보를 저장 하 고 사용 하 여 해당 클래스의 개체를 전달 하는 클래스를 파생 `pHint`합니다. 재정의 `CView::OnUpdate` 멤버 함수에서 프로그램 [CView](../../mfc/reference/cview-class.md)-업데이트 된 정보에 기반 하는 보기의 표시를 최적화 하는 클래스를 파생 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 MDIDOCVW](../../visual-cpp-samples.md)   
 [MFC 샘플 SNAPVW](../../visual-cpp-samples.md)   
 [MFC 샘플 NPP](../../visual-cpp-samples.md)   
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)   
 [CView 클래스](../../mfc/reference/cview-class.md)   
 [CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)
