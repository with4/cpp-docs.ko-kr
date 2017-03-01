---
title: "CDocument 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocument
dev_langs:
- C++
helpviewer_keywords:
- documents [C++], serialization
- files [C++], documents
- command handling, documents and
- documents [C++], document classes
- documents [C++], multiple views
- serialization [C++], documents and
- CDocument class
- command routing, documents and
- views [C++], document
- documents [C++], command routing
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
caps.latest.revision: 21
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4d64b95f77139d984b855e710f3951434e489dd5
ms.lasthandoff: 02/24/2017

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
|[CDocument::BeginReadChunks](#beginreadchunks)|초기화 하는 읽기를 청크 합니다.|  
|[CDocument::CanCloseFrame](#cancloseframe)|고급 재정의할 수 있습니다. 이 문서를 보고 하는 프레임 창을 닫기 전에 호출 됩니다.|  
|[CDocument::ClearChunkList](#clearchunklist)|청크 목록을 지웁니다.|  
|[CDocument::ClearPathName](#clearpathname)|문서 개체의 경로 지웁니다.|  
|[CDocument::DeleteContents](#deletecontents)|문서의 정리를 수행 하기 위해 호출 합니다.|  
|[CDocument::FindChunk](#findchunk)|지정 된 GUID 가진 청크를 찾습니다.|  
|[CDocument::GetAdapter](#getadapter)|개체를 구현 하는 데 대 한 포인터를 반환 `IDocument` 인터페이스입니다.|  
|[CDocument::GetDocTemplate](#getdoctemplate)|문서 형식을 설명 하는 서식 파일에 대 한 포인터를 반환 합니다.|  
|[CDocument::GetFile](#getfile)|원하는에 대 한 포인터를 반환 `CFile` 개체입니다.|  
|[CDocument::GetFirstViewPosition](#getfirstviewposition)|첫 번째 위치를 반환; 뷰 목록에서 반복을 시작 하는 데 사용 합니다.|  
|[CDocument::GetNextView](#getnextview)|뷰는 문서와 연결 된 목록을 반복 합니다.|  
|[CDocument::GetPathName](#getpathname)|문서 데이터 파일의 경로 반환합니다.|  
|[CDocument::GetThumbnail](#getthumbnail)|미리 보기를 표시할 축소판 공급자에서 사용할 비트맵을 만들려면 호출 됩니다.|  
|[CDocument::GetTitle](#gettitle)|문서의 제목을 반환합니다.|  
|[CDocument::InitializeSearchContent](#initializesearchcontent)|검색 처리기에 대 한 콘텐츠 검색을 초기화 하기 위해 호출 합니다.|  
|[CDocument::IsModified](#ismodified)|문서 마지막으로 저장 된 이후 수정 되었는지 여부를 나타냅니다.|  
|[CDocument::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|지시 있는지 여부를이 인스턴스의 `CDocument` 검색 / / 구성 처리기에 대 한 개체를 만든 합니다.|  
|[CDocument::LoadDocumentFromStream](#loaddocumentfromstream)|스트림에서 문서 데이터를 로드 하기 위해 호출 합니다.|  
|[CDocument::OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|고급 미리 보기 글꼴을 변경 하기 전에 호출 합니다.|  
|[CDocument::OnChangedViewList](#onchangedviewlist)|보기에 추가 하거나 문서에서 제거 된 후 호출 됩니다.|  
|[CDocument::OnCloseDocument](#onclosedocument)|호출 하 여 문서를 닫습니다.|  
|[CDocument::OnCreatePreviewFrame](#oncreatepreviewframe)|고급 미리 보기에 대 한 미리 보기 프레임을 만드는 데 필요한 때에 프레임 워크에서 호출 합니다.|  
|[CDocument::OnDocumentEvent](#ondocumentevent)|문서 이벤트에 대 한 응답으로 프레임 워크에 의해 호출 됩니다.|  
|[CDocument::OnDrawThumbnail](#ondrawthumbnail)|미리 보기의 내용을 가져오고 하려면 파생된 클래스에서이 메서드를 재정의 합니다.|  
|[CDocument::OnLoadDocumentFromStream](#onloaddocumentfromstream)|스트림에서 문서 데이터를 로드 하는 경우에 프레임 워크에서 호출 합니다.|  
|[CDocument::OnNewDocument](#onnewdocument)|새 문서를 만들기 위해 호출 합니다.|  
|[CDocument::OnOpenDocument](#onopendocument)|기존 문서를 열기 위해 호출 합니다.|  
|[CDocument::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|HWND GetFocus 함수 호출에서 반환 하는 미리 보기 처리기를 전달 합니다.|  
|[CDocument::OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|미리 보기 처리기 실행 중인 프로세스의 메시지 펌프에서 쌓입니다 키 입력을 처리 하는 미리 보기 처리기를 전달 합니다.|  
|[CDocument::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|고급 미리 보기 배경 색이 변경 되 면 호출 됩니다.|  
|[CDocument::OnRichPreviewFontChanged](#onrichpreviewfontchanged)|고급 미리 보기 글꼴 변경 될 때 호출 됩니다.|  
|[CDocument::OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|고급 미리 보기 사이트 변경 될 때 호출 됩니다.|  
|[CDocument::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|고급 미리 보기 텍스트 색이 변경 되 면 호출 됩니다.|  
|[CDocument::OnSaveDocument](#onsavedocument)|문서를 저장할 디스크를 호출 합니다.|  
|[CDocument::OnUnloadHandler](#onunloadhandler)|미리 보기 처리기 언로드될 때 프레임 워크에 의해 호출 합니다.|  
|[CDocument::PreCloseFrame](#precloseframe)|프레임 창을 닫기 전에 호출 됩니다.|  
|[CDocument::ReadNextChunkValue](#readnextchunkvalue)|다음 청크 값을 읽습니다.|  
|[CDocument::ReleaseFile](#releasefile)|다른 응용 프로그램에서 사용 하기 위해 사용할 수 있도록 파일을 해제 합니다.|  
|[CDocument::RemoveChunk](#removechunk)|지정 된 GUID 가진 청크를 제거합니다.|  
|[CDocument::RemoveView](#removeview)|문서에서 보기를 분리합니다.|  
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|고급 재정의할 수 있습니다. 열린 때 호출 또는 저장 작업 예외 때문에 완료할 수 없습니다.|  
|[CDocument::SaveModified](#savemodified)|고급 재정의할 수 있습니다. 문서를 저장할지 여부를 사용자에 게 요청을 호출 합니다.|  
|[CDocument::SetChunkValue](#setchunkvalue)|청크 값을 설정합니다.|  
|[CDocument::SetModifiedFlag](#setmodifiedflag)|마지막으로 저장 되므로 문서 수정한를 나타내는 플래그를 설정 합니다.|  
|[CDocument::SetPathName](#setpathname)|문서에서 사용 하는 데이터 파일의 경로 설정 합니다.|  
|[CDocument::SetTitle](#settitle)|문서의 제목을 설정합니다.|  
|[CDocument::UpdateAllViews](#updateallviews)|수정 된 문서는 모든 보기에 알립니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDocument::OnFileSendMail](#onfilesendmail)|연결 된 문서와 메일 메시지를 보냅니다.|  
|[CDocument::OnUpdateFileSendMail](#onupdatefilesendmail)|전자 메일 서비스를 사용할 수 있으면 메일 보내기 명령을 활성화 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDocument::m_bGetThumbnailMode](#m_bgetthumbnailmode)|지정 하는 `CDocument` dllhost 축소판 그림으로 개체가 생성 되었습니다. 체크 인 않아야 `CView::OnDraw`합니다.|  
|[CDocument::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|지정 하는 `CDocument` 에 대 한 prevhost 개체가 `Rich Preview`합니다. 체크 인 않아야 `CView::OnDraw`합니다.|  
|[CDocument::m_bSearchMode](#m_bsearchmode)|지정 하는 `CDocument` 인덱서 또는 다른 검색 응용 프로그램에서 개체가 생성 되었습니다.|  
|[CDocument::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|고급 미리 보기 창의 배경색을 지정합니다. 이 색은 호스트에 의해 설정 됩니다.|  
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|고급 미리 보기 창의 전경색을 지정합니다. 이 색은 호스트에 의해 설정 됩니다.|  
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|고급 미리 보기 창에 대 한 텍스트 글꼴을 지정합니다. 이 글꼴 정보는 호스트에 의해 설정 됩니다.|  
  
## <a name="remarks"></a>주의  
 문서는 사용자에서 일반적으로 파일 열기 명령을 사용 하 여 열고 하 고 파일 저장 명령을 사용 하 여 저장 하는 데이터의 단위를 나타냅니다.  
  
 **CDocument** 문서 만들기, 로드, 저장 등의 표준 작업을 지원 합니다. 프레임 워크에서 정의 된 인터페이스를 사용 하 여 문서를 조작 **CDocument**합니다.  
  
 응용 프로그램에 개 이상의 문서 유형을 지원할 수 있습니다. 예를 들어, 응용 프로그램에 스프레드시트 및 텍스트 문서를 모두 지원 될 수 있습니다. 각 형식의 문서에 연결 된 문서 템플릿. 문서 서식 파일은 해당 문서 유형에 대 한 어떤 리소스 (예: 메뉴, 아이콘 또는 액셀러레이터 키 테이블) 사용을 지정 합니다. 해당 연결에 대 한 포인터를 포함 하는 각 문서 `CDocTemplate` 개체입니다.  
  
 사용자가 문서를 통해 상호 작용은 [CView](../../mfc/reference/cview-class.md) 연결 된 개체입니다. 보기의 문서 프레임 창에 이미지를 렌더링 하 고 문서에 대 한 작업으로 사용자 입력 해석 합니다. 문서에 연결 된 여러 뷰가 있을 수 있습니다. 사용자는 문서 창을 열면 프레임 워크는 뷰를 만들고 문서에 연결 합니다. 문서 서식 파일은 어떤 유형의 뷰 및 프레임 창은 각 형식의 문서를 표시 하는 데 지정 합니다.  
  
 프레임 워크의 표준의 일부인 문서 라우팅 명령 및 결과적으로 표준 사용자 인터페이스 구성 요소 (예: 파일 저장 메뉴 항목)에서 명령을 수신 합니다. 문서에는 현재 보기에 의해 전달 되는 명령을 받습니다. 문서에서 지정된 된 명령을 처리 하지 않는 경우를 통해 관리 하는 서식 파일에 명령을 전달 합니다.  
  
 문서 데이터를 수정한 경우 이러한 수정 사항을 반영 해야 각 뷰에 해당 합니다. **CDocument** 제공는 [UpdateAllViews](#updateallviews) 멤버 함수 뷰 자체 필요에 따라 repaint 수 있으므로 이러한 변경 사항을 보기를 알릴 수 있습니다. 프레임 워크에는 수정 된 파일을 닫기 전에 저장 하 라는 메시지 표시 합니다.  
  
 일반 응용 프로그램에서 문서를 구현 하려면 다음을 수행 해야 합니다.  
  
-   클래스를 파생 **CDocument** 각 문서 유형에 대 한 합니다.  
  
-   각 문서의 데이터를 저장할 멤버 변수를 추가 합니다.  
  
-   읽기 및 문서의 데이터를 수정 하기 위한 멤버 함수를 구현 합니다. 문서 보기는 이러한 멤버 함수 중 가장 중요 한 사용자입니다.  
  
-   재정의 [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) 문서와 데이터를 디스크에서 읽고 쓰기 위해 문서 클래스에서 멤버 함수입니다.  
  
 **CDocument** (MAPI) 전자 메일 서비스를 사용할 수 있으면 메일을 통해 문서를 보내는 기능을 지원 합니다. 문서를 참조 [MAPI](../../mfc/mapi.md) 및 [MFC의 MAPI 지원](../../mfc/mapi-support-in-mfc.md)합니다.  
  
 대 한 자세한 내용은 **CDocument**, 참조 [Serialization](../../mfc/serialization-in-mfc.md), [문서/뷰 아키텍처 항목](../../mfc/document-view-architecture.md), 및 [문서/뷰 만들기](../../mfc/document-view-creation.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocument`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="a-nameaddviewa--cdocumentaddview"></a><a name="addview"></a>CDocument::AddView  
 문서에 뷰를 연결 하려면이 함수를 호출 합니다.  
  
```  
void AddView(CView* pView);
```  
  
### <a name="parameters"></a>매개 변수  
 `pView`  
 추가 하려는 보기를 가리킵니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 문서와 관련 된 보기 목록에 지정된 된 뷰 추가 또한 함수는이 문서에 보기의 문서 포인터를 설정합니다. 프레임 워크 문서;에 새로 만든된 뷰 개체를 연결 하는 경우이 함수 호출 이 분할자 창을 분할 하는 경우 또는 새 파일, 파일 열기 또는 새 창 명령에 대 한 응답으로 발생 합니다.  
  
 수동으로 만들고 뷰를 연결 하는 경우에이 함수를 호출 합니다. 일반적으로 프레임 워크를 정의 하 여 문서 및 뷰를 연결할 수는 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 문서 클래스, 클래스 뷰 및 프레임 창 클래스를 연결 하는 개체입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocViewSDI #&12;](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]  
  
##  <a name="a-namebeginreadchunksa--cdocumentbeginreadchunks"></a><a name="beginreadchunks"></a>CDocument::BeginReadChunks  
 초기화 하는 읽기를 청크 합니다.  
  
```  
virtual void BeginReadChunks ();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namecancloseframea--cdocumentcancloseframe"></a><a name="cancloseframe"></a>CDocument::CanCloseFrame  
 문서를 표시 하는 프레임 창을 닫기 전에 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFrame`  
 프레임 창에는 문서에 연결 하는 뷰의 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 프레임 창을; 안전 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현에서는 다른 문서를 표시 하는 프레임 창 되어 있는지 확인 합니다. 지정 된 프레임 창은 문서를 표시 하는 마지막 것 이면 함수 하 라는 메시지가 수정 된 경우 문서를 저장 합니다. 프레임 창의 닫을 때 특수 한 처리를 수행 하려는 경우이 함수를 재정의 합니다. 고급 재정의할 수 있습니다.  
  
##  <a name="a-namecdocumenta--cdocumentcdocument"></a><a name="cdocument"></a>CDocument::CDocument  
 생성 된 **CDocument** 개체입니다.  
  
```  
CDocument();
```  
  
### <a name="remarks"></a>주의  
 프레임 워크를 문서 생성을 처리 합니다. 재정의 [OnNewDocument](#onnewdocument) 문서별 별로 초기화를 수행 하는 멤버 함수 단일 문서 인터페이스 (SDI) 응용 프로그램에서 특히 중요 합니다.  
  
##  <a name="a-nameclearchunklista--cdocumentclearchunklist"></a><a name="clearchunklist"></a>CDocument::ClearChunkList  
 청크 목록을 지웁니다.  
  
```  
virtual void ClearChunkList ();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameclearpathnamea--cdocumentclearpathname"></a><a name="clearpathname"></a>CDocument::ClearPathName  
 문서 개체의 경로 지웁니다.  
  
```  
virtual void ClearPathName();
```  
  
### <a name="remarks"></a>주의  
 경로 지우면는 `CDocument` 개체는 응용 프로그램이 하도록 문서가 저장 된 다음 사용자를 표시 합니다. 이렇게 하면 한 **저장** 명령 처럼 작동 합니다.는 **이름으로 저장** 명령입니다.  
  
##  <a name="a-namedeletecontentsa--cdocumentdeletecontents"></a><a name="deletecontents"></a>CDocument::DeleteContents  
 데이터를 삭제 하는 문서를 삭제 하지 않고 프레임 워크에서 호출 된 **CDocument** 개체 자체입니다.  
  
```  
virtual void DeleteContents();
```  
  
### <a name="remarks"></a>주의  
 문서가 소멸 되도록 하기 바로 전에 호출 됩니다. 이 재사용 되기 전에 문서 비어 있는지 확인 하는 것이 라고도 합니다. 이 특히 중요 한 개의 문서만;를 사용 하 여 SDI 응용 프로그램 문서에는 사용자가 만들거나 다른 문서를 열 때마다 다시 사용 됩니다. "편집 모두 지우기" 또는 모든 문서의 데이터를 삭제 하는 비슷한 명령을 구현 하려면이 함수를 호출 합니다. 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 문서에서 데이터를 삭제 하려면이 함수를 재정의 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&57;](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]  
  
##  <a name="a-namefindchunka--cdocumentfindchunk"></a><a name="findchunk"></a>CDocument::FindChunk  
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
 청크의 PID를 찾을 수를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우 내부 청크 목록에서 위치를 제공 합니다. 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetadaptera--cdocumentgetadapter"></a><a name="getadapter"></a>CDocument::GetAdapter  
 구현 하는 개체에 대 한 포인터를 반환 된 `IDocument` 인터페이스입니다.  
  
```  
virtual ATL::IDocument* GetAdapter();
```  
  
### <a name="return-value"></a>반환 값  
 구현 하는 개체에 대 한 포인터는 `IDocument` 인터페이스입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetdoctemplatea--cdocumentgetdoctemplate"></a><a name="getdoctemplate"></a>CDocument::GetDocTemplate  
 이 문서 유형에 대 한 서식 파일에 대 한 포인터를 가져오려면이 함수를 호출 합니다.  
  
```  
CDocTemplate* GetDocTemplate() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 문서 유형에 대 한 문서 서식 파일에 대 한 포인터 또는 **NULL** 문서 문서 서식 파일에서 관리 되지 않는 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&58;](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]  
  
##  <a name="a-namegetfilea--cdocumentgetfile"></a><a name="getfile"></a>CDocument::GetFile  
 이 멤버 함수에 대 한 단서를 호출 하는 `CFile` 개체입니다.  
  
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
 공유 및 액세스 모드입니다. 파일을 열 때 수행할 동작을 지정 합니다. CFile 생성자에 나열 된 옵션을 조합할 수 [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) 비트 OR를 사용 하 여 (|) 연산자. 에 대 한 액세스 권한 및 공유 하나 옵션은 필요 합니다. **modeCreate** 및 **modeNoInherit** 모드는 선택 사항입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CFile` 개체입니다.  
  
##  <a name="a-namegetfirstviewpositiona--cdocumentgetfirstviewposition"></a><a name="getfirstviewposition"></a>CDocument::GetFirstViewPosition  
 뷰는 문서와 연결 된 목록에서 첫 번째 보기의 위치를 가져오려면이 함수를 호출 합니다.  
  
```  
virtual POSITION GetFirstViewPosition() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **위치** 와 반복에 대해 사용할 수 있는 값은 [GetNextView](#getnextview) 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&59;](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="a-namegetnextviewa--cdocumentgetnextview"></a><a name="getnextview"></a>CDocument::GetNextView  
 문서 보기의 모든 반복 하려면이 함수를 호출 합니다.  
  
```  
virtual CView* GetNextView(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `rPosition`  
 에 대 한 참조는 **위치** 에 대 한 이전 호출에서 반환 된 값은 `GetNextView` 또는 [GetFirstViewPosition](#getfirstviewposition) 멤버 함수입니다. 이 값이 아니어야 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 로 식별 되는 보기에 대 한 포인터 `rPosition`합니다.  
  
### <a name="remarks"></a>주의  
 로 식별 되는 뷰를 반환 하는 함수 `rPosition` 다음 설정 `rPosition` 에 **위치** 목록에 다음 보기가의 값입니다. 검색 된 뷰는 목록에서 마지막 `rPosition` 로 설정 된 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&59;](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="a-namegetpathnamea--cdocumentgetpathname"></a><a name="getpathname"></a>CDocument::GetPathName  
 문서의 디스크 파일의 정규화 된 경로 가져오려면이 함수를 호출 합니다.  
  
```  
const CString& GetPathName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 문서의 정규화 된 경로입니다. 이 문자열은 저장 되지 않은 문서나 연결 된 디스크 파일이 없는 경우 비어 있습니다.  
  
##  <a name="a-namegetthumbnaila--cdocumentgetthumbnail"></a><a name="getthumbnail"></a>CDocument::GetThumbnail  
 미리 보기를 표시 하는 축소판 그림 공급자에서 사용할 비트맵을 만듭니다.  
  
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
 함수가 성공적으로 반환 될 때를 비트맵에 대 한 핸들을 포함 합니다.  
  
 `pdwAlpha`  
 함수에서 성공적으로 반환 되는 알파 채널 값을 지정 하는 DWORD를 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 성공적으로 고, 그렇지 않으면 미리 보기에 대 한 비트맵을 만든 경우 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegettitlea--cdocumentgettitle"></a><a name="gettitle"></a>CDocument::GetTitle  
 일반적으로 문서의 파일 이름에서 파생 된 문서의 제목을 가져오려면이 함수를 호출 합니다.  
  
```  
const CString& GetTitle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 문서의 제목입니다.  
  
##  <a name="a-nameinitializesearchcontenta--cdocumentinitializesearchcontent"></a><a name="initializesearchcontent"></a>CDocument::InitializeSearchContent  
 검색 처리기에 대 한 콘텐츠 검색을 초기화 하기 위해 호출 합니다.  
  
```  
virtual void InitializeSearchContent ();
```  
  
### <a name="remarks"></a>주의  
 콘텐츠 검색을 초기화 하려면 파생된 클래스에서이 메서드를 재정의 합니다. 콘텐츠 부분으로 구분 된 문자열 이어야 합니다 ";"입니다. 예를 들어 "지점을; 사각형입니다. ole 항목 "입니다.  
  
##  <a name="a-nameismodifieda--cdocumentismodified"></a><a name="ismodified"></a>CDocument::IsModified  
 문서 마지막으로 저장 된 이후 수정 되었는지 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
virtual BOOL IsModified();
```  
  
### <a name="return-value"></a>반환 값  
 마지막으로 저장 된; 이후 수정 되었는지 문서 하면 0이 아니고 그렇지 않으면 0입니다.  
  
##  <a name="a-nameissearchandorganizehandlera--cdocumentissearchandorganizehandler"></a><a name="issearchandorganizehandler"></a>CDocument::IsSearchAndOrganizeHandler  
 지시 있는지 여부를이 인스턴스의 `CDocument` 검색 / / 구성 처리기에 대해 만들어진.  
  
```  
BOOL IsSearchAndOrganizeHandler() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 경우의이 인스턴스에 `CDocument` 검색 / / 구성 처리기에 대 한 생성 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수가 반환 하는 현재 `TRUE` 의 프로세스 서버에 구현 된 풍부한 미리 보기 처리기에 대해서만 합니다. 이 함수를 반환 하 여 응용 프로그램 수준 (m_bPreviewHandlerMode, m_bSearchMode, m_bGetThumbnailMode) 적절 한 플래그를 설정할 수 있습니다 `TRUE`합니다.  
  
##  <a name="a-nameloaddocumentfromstreama--cdocumentloaddocumentfromstream"></a><a name="loaddocumentfromstream"></a>CDocument::LoadDocumentFromStream  
 스트림에서 문서 데이터를 로드 하기 위해 호출 합니다.  
  
```  
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,  
    DWORD dwGrfMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStream`  
 스트림에 대 한 포인터입니다. 이 스트림은 셸에서 제공 됩니다.  
  
 `dwGrfMode`  
 스트림에 액세스 모드입니다.  
  
### <a name="return-value"></a>반환 값  
 로드 작업이 성공 하면, 그렇지 않으면 HRESULT 오류 코드와 함께 S_OK입니다.  
  
### <a name="remarks"></a>주의  
 스트림에서 데이터를 로드 하는 방법을 사용자 지정 하는 파생된 클래스에서이 메서드를 재정의할 수 있습니다.  
  
##  <a name="a-namembgetthumbnailmodea--cdocumentmbgetthumbnailmode"></a><a name="m_bgetthumbnailmode"></a>CDocument::m_bGetThumbnailMode  
 지정 하는 `CDocument` dllhost 축소판 그림으로 개체가 생성 되었습니다. 체크 인 않아야 `CView::OnDraw`합니다.  
  
```  
BOOL m_bGetThumbnailMode;  
```  
  
### <a name="remarks"></a>주의  
 `TRUE`문서 dllhost 미리 보기에 대 한 하 여 작성 된 파일 인지를 나타냅니다.  
  
##  <a name="a-namembpreviewhandlermodea--cdocumentmbpreviewhandlermode"></a><a name="m_bpreviewhandlermode"></a>CDocument::m_bPreviewHandlerMode  
 지정 하는 `CDocument` 개체가 prevhost 풍부한 미리 보기. 체크 인 않아야 `CView::OnDraw`합니다.  
  
```  
BOOL m_bPreviewHandlerMode;  
```  
  
### <a name="remarks"></a>주의  
 `TRUE`고급 미리 보기에 대 한 prevhost 하 여 문서를 만든 것을 나타냅니다.  
  
##  <a name="a-namembsearchmodea--cdocumentmbsearchmode"></a><a name="m_bsearchmode"></a>CDocument::m_bSearchMode  
 지정 하는 `CDocument` 인덱서 또는 다른 검색 응용 프로그램에서 개체가 생성 되었습니다.  
  
```  
BOOL m_bSearchMode;  
```  
  
### <a name="remarks"></a>주의  
 `TRUE`인덱서 또는 다른 검색 응용 프로그램에서 문서를 만든 것을 나타냅니다.  
  
##  <a name="a-namemclrrichpreviewbackcolora--cdocumentmclrrichpreviewbackcolor"></a><a name="m_clrrichpreviewbackcolor"></a>CDocument::m_clrRichPreviewBackColor  
 고급 미리 보기 창의 배경색을 지정합니다. 이 색은 호스트에 의해 설정 됩니다.  
  
```  
COLORREF m_clrRichPreviewBackColor;  
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namemclrrichpreviewtextcolora--cdocumentmclrrichpreviewtextcolor"></a><a name="m_clrrichpreviewtextcolor"></a>CDocument::m_clrRichPreviewTextColor  
 풍부한 미리 보기 창의 전경색을 지정합니다. 이 색은 호스트에 의해 설정 됩니다.  
  
```  
COLORREF m_clrRichPreviewTextColor;  
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namemlfrichpreviewfonta--cdocumentmlfrichpreviewfont"></a><a name="m_lfrichpreviewfont"></a>CDocument::m_lfRichPreviewFont  
 고급 미리 보기 창에 대 한 텍스트 글꼴을 지정합니다. 이 글꼴 정보는 호스트에 의해 설정 됩니다.  
  
```  
CFont m_lfRichPreviewFont;  
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonbeforerichpreviewfontchangeda--cdocumentonbeforerichpreviewfontchanged"></a><a name="onbeforerichpreviewfontchanged"></a>CDocument::OnBeforeRichPreviewFontChanged  
 고급 미리 보기 글꼴을 변경 하기 전에 호출 합니다.  
  
```  
virtual void OnBeforeRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonchangedviewlista--cdocumentonchangedviewlist"></a><a name="onchangedviewlist"></a>CDocument::OnChangedViewList  
 보기에 추가 하거나 문서에서 제거 된 후에 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnChangedViewList();
```  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현은 인지 확인 마지막 보기 제거 되 고, 그럴 경우 문서를 삭제 합니다. 프레임 워크를 추가 하거나 뷰를 제거 하는 경우에 특수 한 처리를 수행 하려는 경우이 함수를 재정의 합니다. 예를 들어 문서에 연결 된 뷰가 없는 경우에 계속 열려를 원한다 면이 함수를 재정의 합니다.  
  
##  <a name="a-nameonclosedocumenta--cdocumentonclosedocument"></a><a name="onclosedocument"></a>CDocument::OnCloseDocument  
 문서를 닫을 때, 일반적으로 파일 닫기 명령의 일부로 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnCloseDocument();
```  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현은 제거의 모든 문서 보기에 사용 되는 프레임, 있는 뷰를 닫습니다, 문서의 내용을 정리 하 고 다음 호출에서 [DeleteContents](#deletecontents) 멤버 함수는 문서 데이터를 삭제 합니다.  
  
 특별 한 정리 작업 프레임 워크는 문서를 닫을 때 처리를 수행 하려는 경우이 함수를 재정의 합니다. 예를 들어, 문서 데이터베이스의 레코드를 나타내는 경우이 함수는 데이터베이스를 재정의 하는 것이 좋습니다. 재정의에서이 함수의 기본 클래스 버전을 호출 해야 합니다.  
  
##  <a name="a-nameoncreatepreviewframea--cdocumentoncreatepreviewframe"></a><a name="oncreatepreviewframe"></a>CDocument::OnCreatePreviewFrame  
 고급 미리 보기에 대 한 미리 보기 프레임을 만드는 데 필요한 때에 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnCreatePreviewFrame();
```  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 성공적으로 고, 그렇지 않으면 프레임을 만든 경우 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondocumenteventa--cdocumentondocumentevent"></a><a name="ondocumentevent"></a>CDocument::OnDocumentEvent  
 문서 이벤트에 대 한 응답으로 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnDocumentEvent(DocumentEvent deEvent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `deEvent`  
 이벤트의 형식을 설명 하는 열거형된 데이터 형식입니다.  
  
### <a name="remarks"></a>주의  
 문서 이벤트 여러 클래스에 영향을 줄 수 있습니다. 이 메서드는 이외의 다른 클래스에 영향을 주는 문서 이벤트를 처리 하는 일을 담당는 [CDocument 클래스](../../mfc/reference/cdocument-class.md)합니다. 현재는 문서 이벤트에 응답 해야 하는 유일한 클래스는 [CDataRecoveryHandler 클래스](../../mfc/reference/cdatarecoveryhandler-class.md)합니다. `CDocument` 클래스 메서드가 다른 재정의할 수에 영향을 처리는 `CDocument`합니다.  
  
 다음 표에서 가능한 값에 대 한 `deEvent` 와 해당 하는 이벤트입니다.  
  
|값|해당 하는 이벤트|  
|-----------|-------------------------|  
|`onAfterNewDocument`|새 문서를 만들었습니다.|  
|`onAfterOpenDocument`|새 문서를 열었습니다.|  
|`onAfterSaveDocument`|문서를 저장 합니다.|  
|`onAfterCloseDocument`|문서가 닫혔습니다.|  
  
##  <a name="a-nameondrawthumbnaila--cdocumentondrawthumbnail"></a><a name="ondrawthumbnail"></a>CDocument::OnDrawThumbnail  
 축소판 그림을 그릴 파생된 클래스에서이 메서드를 재정의 합니다.  
  
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
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonfilesendmaila--cdocumentonfilesendmail"></a><a name="onfilesendmail"></a>CDocument::OnFileSendMail  
 상주 메일 호스트를 통해 메시지 (있는 경우) 문서와 첨부 보냅니다.  
  
```  
void OnFileSendMail();
```  
  
### <a name="remarks"></a>주의  
 `OnFileSendMail`호출 [OnSaveDocument](#onsavedocument) (저장) 전자 메일을 통해 전송 되는 임시 파일에 제목 및 수정 된 문서를 serialize 하는 데 있습니다. 문서가 수정 되지 않은 경우 임시 파일 필요 하지 않습니다. 원래 전송 됩니다. `OnFileSendMail`MAPI32를 로드합니다. 아직 로드 되지 않은 경우 DLL입니다.  
  
 구현 하는 특별 한 `OnFileSendMail` 에 대 한 [COleDocument](../../mfc/reference/coledocument-class.md) 올바르게 복합 파일 핸들입니다.  
  
 **CDocument** (MAPI) 전자 메일 서비스를 사용할 수 있으면 메일을 통해 문서를 보내는 기능을 지원 합니다. 문서를 참조 [MAPI 항목](../../mfc/mapi.md) 및 [MFC의 MAPI 지원](../../mfc/mapi-support-in-mfc.md)합니다.  
  
##  <a name="a-nameonloaddocumentfromstreama--cdocumentonloaddocumentfromstream"></a><a name="onloaddocumentfromstream"></a>CDocument::OnLoadDocumentFromStream  
 스트림에서 문서 데이터를 로드 하는 경우에 프레임 워크에서 호출 합니다.  
  
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
 로드에 성공 하면 s_ok이 고 그렇지 않으면 오류 코드가 있습니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonnewdocumenta--cdocumentonnewdocument"></a><a name="onnewdocument"></a>CDocument::OnNewDocument  
 새 파일 명령 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual BOOL OnNewDocument();
```  
  
### <a name="return-value"></a>반환 값  
 문서가 성공적으로 초기화 됩니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현에서는 호출 하는 [DeleteContents](#deletecontents) 멤버 함수는 문서 비어 있고 그런 다음 새 문서를 새로으로 표시 되도록 합니다. 새 문서에 대 한 데이터 구조를 초기화 하려면이 함수를 재정의 합니다. 재정의에서이 함수의 기본 클래스 버전을 호출 해야 합니다.  
  
 SDI 응용 프로그램에서 새 파일 명령을 선택한 경우에 프레임 워크를 새로 만드는 대신 기존 문서를 다시 초기화 하려면이 함수를 사용 합니다. 사용자가 여러 문서 MDI (인터페이스) 응용 프로그램에서 새 파일을 한 경우 프레임 워크 때마다 새 문서를 만들고 및 초기화 하는 데이 함수를 호출 합니다. SDI 응용 프로그램에 적용 하려면 새 파일 명령에 대 한 생성자에서이 함수 대신에 초기화 코드를 배치 해야 합니다.  
  
 에서는 인 사례 `OnNewDocument` 두 번 호출 됩니다. 이 문서를 ActiveX 문서도 포함 되 면 발생 합니다. 함수를 처음 호출할는 `CreateInstance` 메서드 (에 의해 노출 되는 `COleObjectFactory`-파생 클래스)에서 두 번째 시간는 `InitNew` 메서드 (에 의해 노출 되는 `COleServerDoc`-파생 클래스).  
  
### <a name="example"></a>예제  
 다음 예제에는 문서 개체를 초기화 하는 여러 방법 설명 합니다.  
  
 [!code-cpp[NVC_MFCDocView #&60;](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&61;](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&62;](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
##  <a name="a-nameonopendocumenta--cdocumentonopendocument"></a><a name="onopendocument"></a>CDocument::OnOpenDocument  
 파일 열기 명령의 일부로 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszPathName`  
 문서를 열 수의 경로를 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 문서를 로드 했습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현은 호출 지정된 된 파일을 엽니다는 [DeleteContents](#deletecontents) 문서 비어 있는지 확인 하려면 함수 호출 [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) 파일을 읽을 수의 콘텐츠를 다음 정리로 문서를 표시 합니다. 보관 메커니즘 또는 파일 메커니즘 이외의 것을 사용 하려는 경우이 함수를 재정의 합니다. 예를 들어 위치 문서 별도 파일 보다는 데이터베이스의 레코드를 나타내며 응용 프로그램을 작성할 수 있습니다.  
  
 이 함수를 사용 하 여 기존 다시 초기화 하는 프레임 워크 SDI 응용 프로그램에서 파일 열기 명령을 선택한 경우에 **CDocument** 새로 만들지 보다 개체입니다. 프레임 워크가 생성 하는 새 사용자가 MDI 응용 프로그램에서 파일 열기 선택, **CDocument** 때마다 개체를 초기화 하는 데이 함수를 호출 하는 다음. SDI 응용 프로그램에 적용 되기 위해서는 파일 열기 명령에 대 한 생성자에서이 함수 대신에 초기화 코드를 배치 해야 합니다.  
  
### <a name="example"></a>예제  
 다음 예제에는 문서 개체를 초기화 하는 여러 방법 설명 합니다.  
  
 [!code-cpp[NVC_MFCDocView #&60;](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&61;](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&62;](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&63;](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]  
  
##  <a name="a-nameonpreviewhandlerqueryfocusa--cdocumentonpreviewhandlerqueryfocus"></a><a name="onpreviewhandlerqueryfocus"></a>CDocument::OnPreviewHandlerQueryFocus  
 호출에서 검색 된 HWND를 반환 하는 미리 보기 처리기에 전달 된 `GetFocus` 함수입니다.  
  
```  
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `phwnd`  
 [out] 이 메서드가 반환 될 때 호출에서 반환 된 HWND에 대 한 포인터를 포함 된 `GetFocus` 는 미리 보기 처리기의 전경 스레드에서 함수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 반환 또는 그렇지 않으면 오류 값을 지정 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonpreviewhandlertranslateacceleratora--cdocumentonpreviewhandlertranslateaccelerator"></a><a name="onpreviewhandlertranslateaccelerator"></a>CDocument::OnPreviewHandlerTranslateAccelerator  
 미리 보기 처리기 실행 중인 프로세스의 메시지 펌프에서 쌓입니다 키 입력을 처리 하는 미리 보기 처리기를 전달 합니다.  
  
```  
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```  
  
### <a name="parameters"></a>매개 변수  
 `pmsg`  
 [in] 창 메시지에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 미리 보기 처리기에서 키 입력 메시지를 처리할 수 있습니다, 처리기 처리 하 고 S_OK를 반환 합니다. 미리 보기 처리기 키 입력 메시지를 처리할 수 없는 경우 그에 제공을 통해 호스트 `IPreviewHandlerFrame::TranslateAccelerator`합니다. 호스트에서 메시지를 처리 하는 경우이 메서드는 S_OK를 반환 합니다. 호스트에서 메시지를 처리 하지 않습니다,이 메서드는 S_FALSE를 반환 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonrichpreviewbackcolorchangeda--cdocumentonrichpreviewbackcolorchanged"></a><a name="onrichpreviewbackcolorchanged"></a>CDocument::OnRichPreviewBackColorChanged  
 고급 미리 보기 배경 색이 변경 되 면 호출 됩니다.  
  
```  
virtual void OnRichPreviewBackColorChanged();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonrichpreviewfontchangeda--cdocumentonrichpreviewfontchanged"></a><a name="onrichpreviewfontchanged"></a>CDocument::OnRichPreviewFontChanged  
 고급 미리 보기 글꼴 변경 될 때 호출 됩니다.  
  
```  
virtual void OnRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonrichpreviewsitechangeda--cdocumentonrichpreviewsitechanged"></a><a name="onrichpreviewsitechanged"></a>CDocument::OnRichPreviewSiteChanged  
 고급 미리 보기 사이트 변경 될 때 호출 됩니다.  
  
```  
virtual void OnRichPreviewSiteChanged();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonrichpreviewtextcolorchangeda--cdocumentonrichpreviewtextcolorchanged"></a><a name="onrichpreviewtextcolorchanged"></a>CDocument::OnRichPreviewTextColorChanged  
 고급 미리 보기 텍스트 색이 변경 되 면 호출 됩니다.  
  
```  
virtual void OnRichPreviewTextColorChanged();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonsavedocumenta--cdocumentonsavedocument"></a><a name="onsavedocument"></a>CDocument::OnSaveDocument  
 파일 저장 또는 다른 이름으로 저장 명령의 일환으로 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszPathName`  
 하 고 파일을 저장 해야 하는 정규화 된 경로를 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 문서 저장 되었습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현은 호출은 지정된 된 파일을 엽니다 [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) 문서의 데이터를 쓸 파일을을 선택한 다음 표시 문서도 정리 합니다. 프레임 워크는 문서를 저장할 때 특수 한 처리를 수행 하려는 경우이 함수를 재정의 합니다. 예를 들어 위치 문서 별도 파일 보다는 데이터베이스의 레코드를 나타내며 응용 프로그램을 작성할 수 있습니다.  
  
##  <a name="a-nameonunloadhandlera--cdocumentonunloadhandler"></a><a name="onunloadhandler"></a>CDocument::OnUnloadHandler  
 미리 보기 처리기 언로드될 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnUnloadHandler();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonupdatefilesendmaila--cdocumentonupdatefilesendmail"></a><a name="onupdatefilesendmail"></a>CDocument::OnUpdateFileSendMail  
 수 있도록는 **ID_FILE_SEND_MAIL** 메일 지원 (MAPI) 되 면 명령입니다.  
  
```  
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCmdUI`  
 에 대 한 포인터는 [CCmdUI](../../mfc/reference/ccmdui-class.md) 연관 된 개체는 **ID_FILE_SEND_MAIL** 명령입니다.  
  
### <a name="remarks"></a>주의  
 그렇지 않은 경우 제거 함수는 **ID_FILE_SEND_MAIL** 위의 구분 기호를 포함 하 여 메뉴에서 또는 필요에 따라 항목 메뉴 명령입니다. MAPI는 경우 사용할 수 MAPI32 합니다. DLL은 경로 win [Mail] 섹션에 표시 됩니다. INI 파일, MAPI =&1;입니다. 파일 메뉴에서이 명령을 준비 하는 대부분의 응용 프로그램.  
  
 **CDocument** (MAPI) 전자 메일 서비스를 사용할 수 있으면 메일을 통해 문서를 보내는 기능을 지원 합니다. 문서를 참조 [MAPI 항목](../../mfc/mapi.md) 및 [MFC의 MAPI 지원](../../mfc/mapi-support-in-mfc.md)합니다.  
  
##  <a name="a-nameprecloseframea--cdocumentprecloseframe"></a><a name="precloseframe"></a>CDocument::PreCloseFrame  
 이 멤버 함수는 프레임 창 소멸 되기 전에 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void PreCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFrame`  
 에 대 한 포인터는 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 보유 하는 연결 된 **CDocument** 개체입니다.  
  
### <a name="remarks"></a>주의  
 사용자 지정 정리를 제공 하 고는 기본 클래스를 호출 해야 재정의할 수 있습니다.  
  
 기본값은 `PreCloseFrame` 는 아무 작업도 수행 **CDocument**합니다. **CDocument**-파생 된 클래스 [COleDocument](../../mfc/reference/coledocument-class.md) 및 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) 이 멤버 함수를 사용 합니다.  
  
##  <a name="a-namereadnextchunkvaluea--cdocumentreadnextchunkvalue"></a><a name="readnextchunkvalue"></a>CDocument::ReadNextChunkValue  
 다음 청크 값을 읽습니다.  
  
```  
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppValue`  
 [out] 함수가 반환 될 때 `ppValue` 읽은 값을 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namereleasefilea--cdocumentreleasefile"></a><a name="releasefile"></a>CDocument::ReleaseFile  
 이 멤버 함수는 다른 응용 프로그램에서 사용 하기 위해 사용할 수 있도록 파일을 해제 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual void ReleaseFile(
    CFile* pFile,  
    BOOL bAbort);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFile`  
 출시 될 CFile 개체에 대 한 포인터입니다.  
  
 `bAbort`  
 파일 중 하나를 사용 하 여 해제 되는지를 지정 `CFile::Close` 또는 `CFile::Abort`합니다. **FALSE** 파일이 사용 하 여 출시 될 경우 [CFile::Close](../../mfc/reference/cfile-class.md#close); **TRUE** 파일이 사용 하 여 출시 될 경우 [cfile:: Abort](../../mfc/reference/cfile-class.md#abort)합니다.  
  
### <a name="remarks"></a>주의  
 경우 `bAbort` 는 **TRUE**, `ReleaseFile` 호출 `CFile::Abort`, 파일 해제 됩니다. `CFile::Abort`예외를 throw 하지 않습니다.  
  
 경우 `bAbort` 는 **FALSE**, `ReleaseFile` 호출 `CFile::Close` 파일 해제 됩니다.  
  
 이 멤버 함수는 파일을 배포 하기 전에 사용자가 작업을 요구 하도록 재정의 합니다.  
  
##  <a name="a-nameremovechunka--cdocumentremovechunk"></a><a name="removechunk"></a>CDocument::RemoveChunk  
 지정된 된 GUID와 청크를 제거합니다.  
  
```  
virtual void RemoveChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>매개 변수  
 `Guid`  
 제거할 일정의 GUID를 지정 합니다.  
  
 `Pid`  
 제거할 일정의 PID를 지정 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameremoveviewa--cdocumentremoveview"></a><a name="removeview"></a>CDocument::RemoveView  
 문서에서 보기를 분리 하려면이 함수를 호출 합니다.  
  
```  
void RemoveView(CView* pView);
```  
  
### <a name="parameters"></a>매개 변수  
 `pView`  
 제거 하 고 보기를 가리킵니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 지정된 된 보기 문서와 관련 된 보기 목록에서 제거 또한 보기의 문서 포인터를 설정 **NULL**합니다. 이 함수는 프레임 창의 닫을 또는 분할자 창의 창이 닫힐 때 프레임 워크에 의해 호출 됩니다.  
  
 보기를 수동으로 분리 하는 경우에이 함수를 호출 합니다. 일반적으로 프레임 워크를 정의 하 여 문서 및 뷰를 분리할 수는 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 문서 클래스, 클래스 뷰 및 프레임 창 클래스를 연결 하는 개체입니다.  
  
 예 [AddView](#addview) 샘플 구현에 대 한 합니다.  
  
##  <a name="a-namereportsaveloadexceptiona--cdocumentreportsaveloadexception"></a><a name="reportsaveloadexception"></a>CDocument::ReportSaveLoadException  
 예외가 발생 하는 경우 호출 (일반적으로 [CFileException](../../mfc/reference/cfileexception-class.md) 또는 [CArchiveException](../../mfc/reference/carchiveexception-class.md))을 저장 하거나 문서를 로드 합니다.  
  
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
 Throw 된 예외를 가리킵니다. 수 **NULL**합니다.  
  
 *bSaving*  
 어떤 작업이 진행 중이면 했는지를 나타내는 플래그입니다. 문서를 저장 0 문서를 로드 하는 경우 0이 아닌 지정 합니다.  
  
 `nIDPDefault`  
 함수는 보다 구체적인 항목을 지정 하지 않은 경우 표시할 오류 메시지의 식별자입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현에서는 예외 개체를 검사 하 고 원인을 구체적으로 설명 하는 오류 메시지를 찾습니다. 특정 메시지 없거나 경우 *e* 는 **NULL**로 지정 된 일반 메시지는 `nIDPDefault` 매개 변수를 사용 합니다. 함수는 다음 오류 메시지가 포함 된 메시지 상자를 표시 합니다. 추가, 사용자 지정 된 오류 메시지를 제공 하려는 경우이 함수를 재정의 합니다. 고급 재정의할 수 있습니다.  
  
##  <a name="a-namesavemodifieda--cdocumentsavemodified"></a><a name="savemodified"></a>CDocument::SaveModified  
 수정 된 문서를 닫을 수 있게 되기 전에 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL SaveModified();
```  
  
### <a name="return-value"></a>반환 값  
 안전 하 게 문서를 닫고 계속 하면 0이 아니고 문서를 닫을 수 해야 하는 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 기본 구현에는 변경 되었으면 하는 경우 사용자는 문서에 변경 내용을 저장할 것인지 묻는 메시지 상자가 표시 됩니다. 프로그램에 필요한 다른 묻는 프로시저를 하는 경우이 함수를 재정의 합니다. 고급 재정의할 수 있습니다.  
  
##  <a name="a-namesetchunkvaluea--cdocumentsetchunkvalue"></a><a name="setchunkvalue"></a>CDocument::SetChunkValue  
 청크 값을 설정합니다.  
  
```  
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `pValue`  
 청크 설정할 값을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namesetmodifiedflaga--cdocumentsetmodifiedflag"></a><a name="setmodifiedflag"></a>CDocument::SetModifiedFlag  
 문서의 모든 수정 사항은 수행한 후이 함수를 호출 합니다.  
  
```  
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bModified`  
 문서 수정 되었는지 여부를 나타내는 플래그입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 일관 되 게 호출 하 여 프레임 워크는 문서를 닫기 전에 변경 내용을 저장 하 라는 있는지 확인 합니다. 기본값을 사용 하면 일반적으로 **TRUE** 에 대 한는 `bModified` 매개 변수입니다. 정리 문서 (수정 되지 않은)를 표시 하려면 값이 함수를 호출 **FALSE**합니다.  
  
##  <a name="a-namesetpathnamea--cdocumentsetpathname"></a><a name="setpathname"></a>CDocument::SetPathName  
 문서의 디스크 파일의 정규화 된 경로 지정 하려면이 함수를 호출 합니다.  
  
```  
virtual void SetPathName(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszPathName`  
 문서에 대 한 경로로 사용할 문자열을 가리킵니다.  
  
 `bAddToMRU`  
 파일 이름에 추가 하는지 여부를 가장 최근에 사용 된 파일 목록 (MRU)를 결정 합니다. 경우 **TRUE 이면** 파일 이름이 추가 됩니다. **FALSE**, 추가 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 값에 따라 `bAddToMRU` 경로 추가 또는 응용 프로그램에서 관리 하는 최근에 사용한 목록에 추가 되지 않습니다. 참고 일부 문서는 디스크 파일에 관련 되지 않습니다. 프레임 워크에서 사용 되는 파일 열기 및 저장에 대 한 기본 구현을 재정의 하는 경우에이 함수를 호출 합니다.  
  
##  <a name="a-namesettitlea--cdocumentsettitle"></a><a name="settitle"></a>CDocument::SetTitle  
 문서의 제목 (프레임 창의 제목 표시줄에 표시 되는 문자열)을 지정 하려면이 함수를 호출 합니다.  
  
```  
virtual void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszTitle`  
 문서의 제목으로 사용할 문자열을 가리킵니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 호출 문서를 표시 하는 모든 프레임 창의 제목을 업데이트 합니다.  
  
##  <a name="a-nameupdateallviewsa--cdocumentupdateallviews"></a><a name="updateallviews"></a>CDocument::UpdateAllViews  
 문서 수정 된 후에이 함수를 호출 합니다.  
  
```  
void UpdateAllViews(
    CView* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSender`  
 문서를 수정 하는 보기를 가리키는 또는 **NULL** 모든 뷰는 업데이트 해야 하는 경우.  
  
 `lHint`  
 수정에 대 한 정보를 포함합니다.  
  
 `pHint`  
 수정 하는 방법에 대 한 정보를 저장 하는 개체를 가리킵니다.  
  
### <a name="remarks"></a>주의  
 호출한 후에이 함수를 호출 해야는 [SetModifiedFlag](#setmodifiedflag) 멤버 함수입니다. 이 함수에 의해 지정 된 보기를 제외 하 고 문서에 연결 하는 각 보기 알립니다 `pSender`, 수정 된 문서입니다. 일반적으로 사용자가 뷰를 통해 문서를 변경한 후 뷰 클래스에서이 함수를 호출 합니다.  
  
 이 함수를 호출의 [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) 전달 전송을 제외 하 고 문서 보기의 각 멤버 함수 볼 `pHint` 및 `lHint`합니다. 이러한 매개 변수를 사용 하 여 변경 문서에 대 한 보기에 정보를 전달 합니다. 사용 하 여 정보를 인코딩할 수 `lHint` 정의할 수 및/또는 [CObject](../../mfc/reference/cobject-class.md)-파생 클래스를 수정 하는 방법에 대 한 정보를 저장 하 고 사용 하 여 해당 클래스의 개체를 전달 `pHint`합니다. 재정의 `CView::OnUpdate` 멤버 함수에서 프로그램 [CView](../../mfc/reference/cview-class.md)-전달 되는 정보에 따라 보기의 표시를 업데이트 하는 최적화 하는 클래스를 파생 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&64;](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 MDIDOCVW](../../visual-cpp-samples.md)   
 [MFC 샘플 SNAPVW](../../visual-cpp-samples.md)   
 [MFC 샘플 NPP](../../visual-cpp-samples.md)   
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)   
 [CView 클래스](../../mfc/reference/cview-class.md)   
 [CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)

