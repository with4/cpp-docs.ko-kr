---
title: "CDocument Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDocument"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDocument class"
  - "명령 처리, documents and"
  - "명령 라우팅, documents and"
  - "문서[C++], 명령 라우팅"
  - "문서[C++], document classes"
  - "문서[C++], 다중 뷰"
  - "문서[C++], serialization"
  - "파일[C++], 문서"
  - "serialization[C++], documents and"
  - "뷰[C++], 문서"
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CDocument Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자 정의 문서 클래스에 대 한 기본 기능을 제공합니다.  
  
## 구문  
  
```  
class CDocument : public CCmdTarget  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDocument::CDocument](../Topic/CDocument::CDocument.md)|`CDocument` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDocument::AddView](../Topic/CDocument::AddView.md)|뷰는 문서에 첨부합니다.|  
|[CDocument::BeginReadChunks](../Topic/CDocument::BeginReadChunks.md)|읽기 초기화 데이터를 청크로 분할 합니다.|  
|[CDocument::CanCloseFrame](../Topic/CDocument::CanCloseFrame.md)|재정의할 수 있는 고급. 이 문서는 프레임 창을 닫기 전에 호출 됩니다.|  
|[CDocument::ClearChunkList](../Topic/CDocument::ClearChunkList.md)|청크 목록을 지웁니다.|  
|[CDocument::ClearPathName](../Topic/CDocument::ClearPathName.md)|문서 개체의 경로 지웁니다.|  
|[CDocument::DeleteContents](../Topic/CDocument::DeleteContents.md)|호출 문서 정리를 수행 합니다.|  
|[CDocument::FindChunk](../Topic/CDocument::FindChunk.md)|청크를 지정 된 GUID 찾습니다.|  
|[CDocument::GetAdapter](../Topic/CDocument::GetAdapter.md)|개체 구현에 대 한 포인터를 반환 `IDocument` 인터페이스.|  
|[CDocument::GetDocTemplate](../Topic/CDocument::GetDocTemplate.md)|문서 형식을 설명 하는 문서 서식 파일에 대 한 포인터를 반환 합니다.|  
|[CDocument::GetFile](../Topic/CDocument::GetFile.md)|포인터를 원하는 반환 `CFile` 개체입니다.|  
|[CDocument::GetFirstViewPosition](../Topic/CDocument::GetFirstViewPosition.md)|첫 번째 반환 목록 보기. 반복을 시작 하는 데 사용 합니다.|  
|[CDocument::GetNextView](../Topic/CDocument::GetNextView.md)|뷰는 문서와 연결 된 목록을 반복 합니다.|  
|[CDocument::GetPathName](../Topic/CDocument::GetPathName.md)|문서의 데이터 파일의 경로 반환합니다.|  
|[CDocument::GetThumbnail](../Topic/CDocument::GetThumbnail.md)|축소판 그림을 표시 하려면 축소판 그림 공급자가 사용 하는 비트맵을 만들려면 호출 됩니다.|  
|[CDocument::GetTitle](../Topic/CDocument::GetTitle.md)|문서의 제목을 반환합니다.|  
|[CDocument::InitializeSearchContent](../Topic/CDocument::InitializeSearchContent.md)|호출에 대 한 처리기를 검색 검색 내용을 초기화 합니다.|  
|[CDocument::IsModified](../Topic/CDocument::IsModified.md)|문서를 마지막으로 저장 된 이후 수정 되었는지 여부를 나타냅니다.|  
|[CDocument::IsSearchAndOrganizeHandler](../Topic/CDocument::IsSearchAndOrganizeHandler.md)|지시 여부이 인스턴스의 `CDocument` 작성에 대 한 검색 및 처리기를 구성 합니다.|  
|[CDocument::LoadDocumentFromStream](../Topic/CDocument::LoadDocumentFromStream.md)|문서 데이터 스트림에서 로드 하기 위해 호출 됩니다.|  
|[CDocument::OnBeforeRichPreviewFontChanged](../Topic/CDocument::OnBeforeRichPreviewFontChanged.md)|고급 미리 보기 글꼴을 변경 하기 전에 호출 됩니다.|  
|[CDocument::OnChangedViewList](../Topic/CDocument::OnChangedViewList.md)|보기를 추가 하거나 문서에서 제거 된 후에 호출 됩니다.|  
|[CDocument::OnCloseDocument](../Topic/CDocument::OnCloseDocument.md)|문서를 닫기 위해 호출 됩니다.|  
|[CDocument::OnCreatePreviewFrame](../Topic/CDocument::OnCreatePreviewFrame.md)|미리 보기 프레임 고급 미리 보기를 만들 필요가 있을 때 프레임 워크에 의해 호출 됩니다.|  
|[CDocument::OnDocumentEvent](../Topic/CDocument::OnDocumentEvent.md)|문서의 이벤트에 응답 하는 프레임 워크에서 호출합니다.|  
|[CDocument::OnDrawThumbnail](../Topic/CDocument::OnDrawThumbnail.md)|축소판 그림의 내용을 그리는 데 파생된 클래스에서이 메서드를 재정의 합니다.|  
|[CDocument::OnLoadDocumentFromStream](../Topic/CDocument::OnLoadDocumentFromStream.md)|문서 데이터 스트림에서 로드 할 때 프레임 워크에 의해 호출 됩니다.|  
|[CDocument::OnNewDocument](../Topic/CDocument::OnNewDocument.md)|새 문서를 만들려면 다음과 같이 호출 됩니다.|  
|[CDocument::OnOpenDocument](../Topic/CDocument::OnOpenDocument.md)|기존 문서를 열기 위해 호출 됩니다.|  
|[CDocument::OnPreviewHandlerQueryFocus](../Topic/CDocument::OnPreviewHandlerQueryFocus.md)|HWND GetFocus 함수 호출에서 반환 하는 미리 보기 처리기에 게 지시 합니다.|  
|[CDocument::OnPreviewHandlerTranslateAccelerator](../Topic/CDocument::OnPreviewHandlerTranslateAccelerator.md)|미리 보기 처리기는 미리 보기 처리기를 실행 하는 프로세스의 메시지 펌프에서 전달는 키 입력을 처리 하도록 합니다.|  
|[CDocument::OnRichPreviewBackColorChanged](../Topic/CDocument::OnRichPreviewBackColorChanged.md)|고급 미리 보기 배경 색상 변경 될 때 호출 됩니다.|  
|[CDocument::OnRichPreviewFontChanged](../Topic/CDocument::OnRichPreviewFontChanged.md)|고급 미리 보기 글꼴 변경 될 때 호출 됩니다.|  
|[CDocument::OnRichPreviewSiteChanged](../Topic/CDocument::OnRichPreviewSiteChanged.md)|고급 미리 보기 사이트에서 변경 될 때 호출 됩니다.|  
|[CDocument::OnRichPreviewTextColorChanged](../Topic/CDocument::OnRichPreviewTextColorChanged.md)|고급 미리 보기 텍스트 색이 변경 될 때 호출 됩니다.|  
|[CDocument::OnSaveDocument](../Topic/CDocument::OnSaveDocument.md)|디스크에 문서를 저장 하기 위해 호출 됩니다.|  
|[CDocument::OnUnloadHandler](../Topic/CDocument::OnUnloadHandler.md)|미리 보기 처리기 언로드될 때 프레임 워크에 의해 호출 됩니다.|  
|[CDocument::PreCloseFrame](../Topic/CDocument::PreCloseFrame.md)|프레임 창이 닫히기 전에 호출 됩니다.|  
|[CDocument::ReadNextChunkValue](../Topic/CDocument::ReadNextChunkValue.md)|다음 청크 값을 읽습니다.|  
|[CDocument::ReleaseFile](../Topic/CDocument::ReleaseFile.md)|파일을 다른 응용 프로그램에서 사용 하기 위해 사용할 수 있도록 해제 합니다.|  
|[CDocument::RemoveChunk](../Topic/CDocument::RemoveChunk.md)|지정한 GUID 가진 청크를 제거합니다.|  
|[CDocument::RemoveView](../Topic/CDocument::RemoveView.md)|보기에서 문서를 분리합니다.|  
|[CDocument::ReportSaveLoadException](../Topic/CDocument::ReportSaveLoadException.md)|재정의할 수 있는 고급. 열기 때 호출 또는 예외 때문에 저장 작업을 완료할 수 없습니다.|  
|[CDocument::SaveModified](../Topic/CDocument::SaveModified.md)|재정의할 수 있는 고급. 문서를 저장 해야 하는지 여부를 사용자에 게 호출 합니다.|  
|[CDocument::SetChunkValue](../Topic/CDocument::SetChunkValue.md)|부분 값을 설정합니다.|  
|[CDocument::SetModifiedFlag](../Topic/CDocument::SetModifiedFlag.md)|마지막으로 저장 된 문서를 수정한 나타내는 플래그를 설정 합니다.|  
|[CDocument::SetPathName](../Topic/CDocument::SetPathName.md)|문서에서 사용 하는 데이터 파일의 경로 설정 합니다.|  
|[CDocument::SetTitle](../Topic/CDocument::SetTitle.md)|문서의 제목을 설정합니다.|  
|[CDocument::UpdateAllViews](../Topic/CDocument::UpdateAllViews.md)|문서 보기를 모두 수정 되었습니다 알립니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDocument::OnFileSendMail](../Topic/CDocument::OnFileSendMail.md)|첨부 된 문서를 메일 메시지를 보냅니다.|  
|[CDocument::OnUpdateFileSendMail](../Topic/CDocument::OnUpdateFileSendMail.md)|전자 메일 서비스를 사용할 수 없는 경우 메일 보내기 명령을 수 있습니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDocument::m\_bGetThumbnailMode](../Topic/CDocument::m_bGetThumbnailMode.md)|지정 하는 `CDocument` 개체 dllhost 축소판 그림으로 만들어진.  체크인 해야 `CView::OnDraw`.|  
|[CDocument::m\_bPreviewHandlerMode](../Topic/CDocument::m_bPreviewHandlerMode.md)|지정 하는 `CDocument` 개체의 prevhost에서 만든 `Rich Preview`.  체크인 해야 `CView::OnDraw`.|  
|[CDocument::m\_bSearchMode](../Topic/CDocument::m_bSearchMode.md)|지정 하는 `CDocument` 개체 인덱서 또는 기타 검색 응용 프로그램으로 만들어졌습니다.|  
|[CDocument::m\_clrRichPreviewBackColor](../Topic/CDocument::m_clrRichPreviewBackColor.md)|고급 미리 보기 창의 배경색을 지정합니다.  이 색은 호스트에 의해 설정 됩니다.|  
|[CDocument::m\_clrRichPreviewTextColor](../Topic/CDocument::m_clrRichPreviewTextColor.md)|고급 미리 보기 창의 전경색을 지정합니다.  이 색은 호스트에 의해 설정 됩니다.|  
|[CDocument::m\_lfRichPreviewFont](../Topic/CDocument::m_lfRichPreviewFont.md)|고급 미리 보기 창의 텍스트 글꼴을 지정합니다.  이 글꼴 정보는 호스트에 의해 설정 됩니다.|  
  
## 설명  
 문서 사용자가 일반적으로 파일 열기 명령을 사용 하 여 열고 파일 저장 명령을 사용 하 여 저장 하는 데이터의 단위를 나타냅니다.  
  
 **CDocument** 문서 만들기, 로드 및 저장과 같은 표준 작업을 지원 합니다.  프레임 워크에서 정의 된 인터페이스를 사용 하 여 문서를 조작  **CDocument**.  
  
 응용 프로그램 두 개 이상의 문서 형식을 지원할 수 있습니다. 예를 들어, 응용 프로그램이 텍스트 문서와 스프레드시트를 지원할 수 있습니다.  각 문서 형식에는 연결 된 문서 서식 파일이 없습니다. 리소스 \(예: 메뉴, 아이콘, 액셀러레이터 테이블\) 해당 문서 종류에 사용할 문서 서식 파일을 지정 합니다.  각 문서는 연결에 대 한 포인터 포함 `CDocTemplate` 개체입니다.  
  
 사용자 상호 작용을 통해 문서를  [CView](../../mfc/reference/cview-class.md) 개체에 연결 된.  이미지 문서 프레임 창에서의 렌더링 뷰와 사용자 입력 작업에는 문서를 해석 합니다.  문서에 연결 된 여러 뷰를 가질 수 있습니다.  창에 문서를 열면 프레임 워크 보기를 만들고이 문서에 연결 합니다.  어떤 유형의 뷰와 프레임 창 각 문서를 표시 하는 데 사용 문서 서식 파일을 지정 합니다.  
  
 문서는 표준 프레임 워크의 명령 라우팅 받고 결과적으로 명령에서 표준 사용자 인터페이스 구성 요소 \(예: 파일 저장 메뉴 항목\).  문서 전달 활성 뷰에서 명령을 받습니다.  문서에 지정 된 명령을 처리 하지 않으면 관리 문서 템플릿에 명령을 전달 합니다.  
  
 문서의 데이터를 수정 하면 뷰 각 해당 수정 사항을 반영 해야 합니다.  **CDocument** 제공 된  [UpdateAllViews](../Topic/CDocument::UpdateAllViews.md) 멤버 함수 뷰 자체 필요에 따라 다시 그릴 수 있도록 보기의 이러한 변경 사항 알릴 수.  프레임 워크 또한 사용자는 수정 된 파일을 닫기 전에 저장 하 라는 메시지가 나타납니다.  
  
 일반적인 응용 프로그램에서 문서를 구현 하려면 다음을 수행 해야 합니다.  
  
-   파생 클래스에서  **CDocument** 각 문서 형식에 대 한.  
  
-   각 문서 데이터를 저장 하려면 멤버 변수를 추가 합니다.  
  
-   읽고 문서의 데이터를 수정 하는 방법에 대 한 멤버 함수를 구현 합니다.  문서의 뷰 멤버 함수는 가장 중요 한 사용자입니다.  
  
-   재정의  [CObject::Serialize](../Topic/CObject::Serialize.md) 문서의 데이터를 디스크에서 읽고 쓰기가 문서 클래스의 멤버 함수입니다.  
  
 **CDocument** \(MAPI\) 전자 메일 서비스를 사용할 수 없는 경우 메일을 통해 문서를 보내기를 지원 합니다.  문서를 참조 하십시오.  [MAPI](../../mfc/mapi.md) 및  [MFC의 MAPI 지원](../../mfc/mapi-support-in-mfc.md).  
  
 에 대 한 자세한 내용은  **CDocument**를 참조 하십시오  [직렬화](../../mfc/serialization-in-mfc.md),  [문서\/뷰 아키텍처 항목](../../mfc/document-view-architecture.md), 및  [문서\/뷰 만들기](../../mfc/document-view-creation.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocument`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [MFC 샘플 MDIDOCVW](../../top/visual-cpp-samples.md)   
 [MFC SNAPVW 샘플](../../top/visual-cpp-samples.md)   
 [NPP MFC 샘플](../../top/visual-cpp-samples.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)