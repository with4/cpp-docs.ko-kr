---
title: "COleServerDoc 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleServerDoc
- AFXOLE/COleServerDoc
- AFXOLE/COleServerDoc::COleServerDoc
- AFXOLE/COleServerDoc::ActivateDocObject
- AFXOLE/COleServerDoc::ActivateInPlace
- AFXOLE/COleServerDoc::DeactivateAndUndo
- AFXOLE/COleServerDoc::DiscardUndoState
- AFXOLE/COleServerDoc::GetClientSite
- AFXOLE/COleServerDoc::GetEmbeddedItem
- AFXOLE/COleServerDoc::GetItemClipRect
- AFXOLE/COleServerDoc::GetItemPosition
- AFXOLE/COleServerDoc::GetZoomFactor
- AFXOLE/COleServerDoc::IsDocObject
- AFXOLE/COleServerDoc::IsEmbedded
- AFXOLE/COleServerDoc::IsInPlaceActive
- AFXOLE/COleServerDoc::NotifyChanged
- AFXOLE/COleServerDoc::NotifyClosed
- AFXOLE/COleServerDoc::NotifyRename
- AFXOLE/COleServerDoc::NotifySaved
- AFXOLE/COleServerDoc::OnDeactivate
- AFXOLE/COleServerDoc::OnDeactivateUI
- AFXOLE/COleServerDoc::OnDocWindowActivate
- AFXOLE/COleServerDoc::OnResizeBorder
- AFXOLE/COleServerDoc::OnShowControlBars
- AFXOLE/COleServerDoc::OnUpdateDocument
- AFXOLE/COleServerDoc::RequestPositionChange
- AFXOLE/COleServerDoc::SaveEmbedding
- AFXOLE/COleServerDoc::ScrollContainerBy
- AFXOLE/COleServerDoc::UpdateAllItems
- AFXOLE/COleServerDoc::CreateInPlaceFrame
- AFXOLE/COleServerDoc::DestroyInPlaceFrame
- AFXOLE/COleServerDoc::GetDocObjectServer
- AFXOLE/COleServerDoc::OnClose
- AFXOLE/COleServerDoc::OnExecOleCmd
- AFXOLE/COleServerDoc::OnFrameWindowActivate
- AFXOLE/COleServerDoc::OnGetEmbeddedItem
- AFXOLE/COleServerDoc::OnReactivateAndUndo
- AFXOLE/COleServerDoc::OnSetHostNames
- AFXOLE/COleServerDoc::OnSetItemRects
- AFXOLE/COleServerDoc::OnShowDocument
dev_langs:
- C++
helpviewer_keywords:
- COleServerDoc [MFC], COleServerDoc
- COleServerDoc [MFC], ActivateDocObject
- COleServerDoc [MFC], ActivateInPlace
- COleServerDoc [MFC], DeactivateAndUndo
- COleServerDoc [MFC], DiscardUndoState
- COleServerDoc [MFC], GetClientSite
- COleServerDoc [MFC], GetEmbeddedItem
- COleServerDoc [MFC], GetItemClipRect
- COleServerDoc [MFC], GetItemPosition
- COleServerDoc [MFC], GetZoomFactor
- COleServerDoc [MFC], IsDocObject
- COleServerDoc [MFC], IsEmbedded
- COleServerDoc [MFC], IsInPlaceActive
- COleServerDoc [MFC], NotifyChanged
- COleServerDoc [MFC], NotifyClosed
- COleServerDoc [MFC], NotifyRename
- COleServerDoc [MFC], NotifySaved
- COleServerDoc [MFC], OnDeactivate
- COleServerDoc [MFC], OnDeactivateUI
- COleServerDoc [MFC], OnDocWindowActivate
- COleServerDoc [MFC], OnResizeBorder
- COleServerDoc [MFC], OnShowControlBars
- COleServerDoc [MFC], OnUpdateDocument
- COleServerDoc [MFC], RequestPositionChange
- COleServerDoc [MFC], SaveEmbedding
- COleServerDoc [MFC], ScrollContainerBy
- COleServerDoc [MFC], UpdateAllItems
- COleServerDoc [MFC], CreateInPlaceFrame
- COleServerDoc [MFC], DestroyInPlaceFrame
- COleServerDoc [MFC], GetDocObjectServer
- COleServerDoc [MFC], OnClose
- COleServerDoc [MFC], OnExecOleCmd
- COleServerDoc [MFC], OnFrameWindowActivate
- COleServerDoc [MFC], OnGetEmbeddedItem
- COleServerDoc [MFC], OnReactivateAndUndo
- COleServerDoc [MFC], OnSetHostNames
- COleServerDoc [MFC], OnSetItemRects
- COleServerDoc [MFC], OnShowDocument
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 81b3b8d4c3f25e1c443d5fbcaeddb7b587216d69
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="coleserverdoc-class"></a>COleServerDoc 클래스
OLE 서버 문서의 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleServerDoc::COleServerDoc](#coleserverdoc)|`COleServerDoc` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleServerDoc::ActivateDocObject](#activatedocobject)|연결된 된 DocObject 문서를 활성화합니다.|  
|[COleServerDoc::ActivateInPlace](#activateinplace)|내부 편집에 대 한 문서를 활성화합니다.|  
|[COleServerDoc::DeactivateAndUndo](#deactivateandundo)|서버의 사용자 인터페이스를 비활성화합니다.|  
|[COleServerDoc::DiscardUndoState](#discardundostate)|실행 취소 상태 정보를 삭제합니다.|  
|[COleServerDoc::GetClientSite](#getclientsite)|원본에 대 한 포인터를 검색 `IOleClientSite` 인터페이스입니다.|  
|[COleServerDoc::GetEmbeddedItem](#getembeddeditem)|전체 문서를 나타내는 항목에 대 한 포인터를 반환 합니다.|  
|[COleServerDoc::GetItemClipRect](#getitemcliprect)|내부 편집에 대 한 현재 클리핑 사각형을 반환합니다.|  
|[COleServerDoc::GetItemPosition](#getitemposition)|내부 편집에 대 한 컨테이너 응용 프로그램의 클라이언트 영역을 기준으로 현재 위치 사각형을 반환합니다.|  
|[COleServerDoc::GetZoomFactor](#getzoomfactor)|확대/축소 비율을 픽셀 단위로 반환 합니다.|  
|[COleServerDoc::IsDocObject](#isdocobject)|문서는 DocObject 인지 여부를 확인 합니다.|  
|[COleServerDoc::IsEmbedded](#isembedded)|컨테이너 문서의 포함 된 또는 실행 중인 독립 실행형 문서 인지를 나타냅니다.|  
|[COleServerDoc::IsInPlaceActive](#isinplaceactive)|반환 `TRUE` 항목 위치에서 현재 활성화 된 경우.|  
|[COleServerDoc::NotifyChanged](#notifychanged)|사용자가 문서를 변경 하는 컨테이너 알립니다.|  
|[COleServerDoc::NotifyClosed](#notifyclosed)|사용자가 문서를 닫은 컨테이너에 알립니다.|  
|[COleServerDoc::NotifyRename](#notifyrename)|사용자의 문서를 이름이 컨테이너에 알립니다.|  
|[COleServerDoc::NotifySaved](#notifysaved)|사용자가 문서를 저장 했습니다 컨테이너에 알립니다.|  
|[COleServerDoc::OnDeactivate](#ondeactivate)|사용자 위치에 활성화 된 항목을 비활성화 하는 경우 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::OnDeactivateUI](#ondeactivateui)|컨트롤 및 기타 사용자 인터페이스 요소에는 내부 활성화에 대해 생성을 삭제 하기 위해 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::OnDocWindowActivate](#ondocwindowactivate)|컨테이너의 문서 프레임 창이 활성화 또는 비활성화 될 때 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::OnResizeBorder](#onresizeborder)|컨테이너 응용 프로그램의 프레임 창이 나 문서 창의 크기를 조정할 때 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::OnShowControlBars](#onshowcontrolbars)|내부 편집에 대 한 컨트롤 막대 표시 또는 숨기기 위해 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::OnUpdateDocument](#onupdatedocument)|서버 문서를 포함된 된 항목은 업데이트 된 항목의 컨테이너의 복사본 저장 될 때 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::RequestPositionChange](#requestpositionchange)|내부 편집 프레임의 위치를 변경 합니다.|  
|[COleServerDoc::SaveEmbedding](#saveembedding)|문서를 저장할 컨테이너 응용 프로그램에 알려 줍니다.|  
|[COleServerDoc::ScrollContainerBy](#scrollcontainerby)|컨테이너 문서를 스크롤합니다.|  
|[COleServerDoc::UpdateAllItems](#updateallitems)|사용자가 문서를 변경 하는 컨테이너 알립니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleServerDoc::CreateInPlaceFrame](#createinplaceframe)|내부 편집을 위해 프레임 창을 만들기 위해 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::DestroyInPlaceFrame](#destroyinplaceframe)|내부 편집에 대 한 프레임 창을 삭제 하기 위해 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::GetDocObjectServer](#getdocobjectserver)|이 함수를 만드는 새 재정의 `CDocObjectServer` 개체와이 문서 DocObject 컨테이너 임을 나타냅니다.|  
|[COleServerDoc::OnClose](#onclose)|컨테이너 문서를 닫으려면 요청할 때 프레임 워크에서 호출 합니다.|  
|[COleServerDoc::OnExecOleCmd](#onexecolecmd)|지정 된 명령을 실행 하거나 명령에 대 한 도움말을 표시 합니다.|  
|[COleServerDoc::OnFrameWindowActivate](#onframewindowactivate)|컨테이너의 프레임 창이 활성화 또는 비활성화 될 때 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|가져오기 위해 호출 됩니다는 `COleServerItem` 하는 전체 문서 나타내고 값이 포함된 된 항목을 가져오는 데 사용 합니다. 필요한 구현입니다.|  
|[COleServerDoc::OnReactivateAndUndo](#onreactivateandundo)|내부 편집 하는 동안 변경 내용을 실행 취소 하기 위해 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::OnSetHostNames](#onsethostnames)|컨테이너에 포함된 된 개체에 대 한 창 제목을 설정 하는 경우 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::OnSetItemRects](#onsetitemrects)|컨테이너 응용 프로그램의 창 내에서 내부 편집 프레임 창의 위치를 지정 하기 위해 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::OnShowDocument](#onshowdocument)|표시 하거나 숨기려면 문서 프레임 워크에서 호출 됩니다.|  
  
## <a name="remarks"></a>설명  
 서버 문서에 포함 될 수 있습니다 [COleServerItem](../../mfc/reference/coleserveritem-class.md) 개체를 포함 또는 연결 된 항목에는 서버 인터페이스를 나타냅니다. 항목이 자체 서버 문서로 로드 되는 서버 응용 프로그램이 포함된 된 항목을 편집 하려면 컨테이너에 의해 시작 되 면 `COleServerDoc` 개체에 포함 되어 하나만 `COleServerItem` 전체 문서의 구성 된 개체를 합니다. 기존 문서; 디스크에서 로드 되는 서버 응용 프로그램 연결 된 항목을 편집 하려면 컨테이너에 의해 시작 되 면 링크 된 항목을 나타내기 위해 문서 내용의 일부를 강조 표시 됩니다.  
  
 `COleServerDoc`개체의 항목을 포함할 수도 있습니다는 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 클래스입니다. 이 옵션을 사용 하면 컨테이너 서버 응용 프로그램을 만들 수 있습니다. 제대로 저장할 함수를 제공 하는 프레임 워크는 `COleClientItem` 서비스를 제공 하는 동안 항목의 `COleServerItem` 개체입니다.  
  
 서버 응용 프로그램이 링크를 지원 하지 않는 경우 서버 문서는 문서와 포함된 된 전체 개체를 나타내는 하나의 서버 항목을 항상 포함 됩니다. 서버 응용 프로그램에서 링크를 지원 하는 경우 만들어야 서버 항목 될 때마다 선택 클립보드에 복사 됩니다.  
  
 사용 하도록 `COleServerDoc`를 여기에서 클래스를 파생 하 고 구현는 [문서](#ongetembeddeditem) 포함 된 항목을 지원 하도록 서버 수 있는 멤버 함수입니다. 클래스를 파생 `COleServerItem` 문서에서 항목을 구현 하 고 해당 클래스에서의 개체를 반환 하려면 `OnGetEmbeddedItem`합니다.  
  
 연결 된 항목을 지원 하도록 `COleServerDoc` 제공는 [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem) 멤버 함수입니다. 기본 구현을 사용 하거나 자신만의 문서 항목 관리 방법으로 설정한 경우 재정의할 수 있습니다.  
  
 필요 하면 `COleServerDoc`-응용 프로그램에서 지원할을 문서화 하는 각 서버 유형에 대 한 클래스를 파생 합니다. 예를 들어 서버 응용 프로그램이 워크시트 및 차트를 지 원하는 경우 필요한 두 개의 `COleServerDoc`-파생 된 클래스입니다.  
  
 서버에 대 한 자세한 내용은 문서 참조 [서버: 서버 구현](../../mfc/servers-implementing-a-server.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 `COleServerDoc`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="activatedocobject"></a>COleServerDoc::ActivateDocObject  
 연결된 된 DocObject 문서를 활성화합니다.  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>설명  
 기본적으로 `COleServerDoc` 액티브 문서 (DocObjects 라고도 함)를 지원 하지 않습니다. 이 지원을 사용 하려면 참조 [GetDocObjectServer](#getdocobjectserver) 및 클래스 [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)합니다.  
  
##  <a name="activateinplace"></a>COleServerDoc::ActivateInPlace  
 내부 편집에 대 한 항목을 활성화합니다.  
  
```  
BOOL ActivateInPlace();
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아닌 그렇지 않으면 0, 항목 임을 나타냅니다 완전 개방 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 내부 활성화에 필요한 모든 작업을 수행합니다. 내부 프레임 창, 활성화 및 항목 크기를 조정, 공유 메뉴 및 기타 컨트롤을 설정, 스크롤되어 항목 만들고 내부 프레임 창으로 포커스를 설정 합니다.  
  
 기본 구현에서이 함수가 호출 될 [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow)합니다. 응용 프로그램 (예: 재생)에 내부 활성화에 대 한 또 다른 동사를 지 원하는 경우이 함수를 호출 합니다.  
  
##  <a name="coleserverdoc"></a>COleServerDoc::COleServerDoc  
 생성 된 `COleServerDoc` OLE 시스템 Dll 사용 하 여 연결 하지 않고 개체입니다.  
  
```  
COleServerDoc();
```  
  
### <a name="remarks"></a>설명  
 호출 해야 [COleLinkingDoc::Register](../../mfc/reference/colelinkingdoc-class.md#register) 통신 OLE를 열려고 합니다. 사용 중인 경우 [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) 응용 프로그램에서 `COleLinkingDoc::Register` 의해 라고 `COleLinkingDoc`의의 구현 `OnNewDocument`, `OnOpenDocument`, 및 `OnSaveDocument`합니다.  
  
##  <a name="createinplaceframe"></a>COleServerDoc::CreateInPlaceFrame  
 프레임 워크 내부 편집을 위해 프레임 창을 만들려면이 함수를 호출 합니다.  
  
```  
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pParentWnd`  
 컨테이너 응용 프로그램의 부모 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 내부 프레임 창에 대 한 포인터 또는 **NULL** 실패 합니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 문서 서식 파일에 지정 된 정보를 사용 하 여 프레임을 만듭니다. 사용 되는 보기는 문서에 대해 만든 첫 번째 뷰입니다. 이 보기를 임시로 원래 프레임에서 분리 및 새로 만든된 프레임에 연결 합니다.  
  
 고급 재정의할 수 있습니다.  
  
##  <a name="deactivateandundo"></a>COleServerDoc::DeactivateAndUndo  
 응용 프로그램에서 지원할 실행 취소 하 고 사용자가 항목을 활성화 한 후 있지만 편집 하기 전에 실행 취소를 선택 하는 경우이 함수를 호출 합니다.  
  
```  
BOOL DeactivateAndUndo();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아닌 값이고, 실패하면 0입니다.  
  
### <a name="remarks"></a>설명  
 컨테이너 응용 프로그램은 Microsoft Foundation Class 라이브러리를 사용 하 여를 작성 한 경우이 함수를 호출 하면 [COleClientItem::OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo) 서버의 사용자 인터페이스를 비활성화를 호출할 수 있습니다.  
  
##  <a name="destroyinplaceframe"></a>COleServerDoc::DestroyInPlaceFrame  
 프레임 워크 내부 프레임 창을 삭제 하 고 서버 응용 프로그램의 문서 창에는 내부 활성화 상태로 반환 하려면이 함수를 호출 합니다.  
  
```  
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFrameWnd`  
 내부 프레임 창 소멸 될 예정에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 고급 재정의할 수 있습니다.  
  
##  <a name="discardundostate"></a>COleServerDoc::DiscardUndoState  
 사용자는 실행 취소할 수 없는 편집 작업을 수행 하는 경우 해당 실행 취소 상태 정보를 삭제 하려는 컨테이너 응용 프로그램에서이 함수를 호출 합니다.  
  
```  
BOOL DiscardUndoState();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아닌 값이고, 실패하면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 실행 취소를 지 원하는 서버에 사용할 수 없는 실행 취소 상태 정보로 사용 그렇지 않은 경우는 리소스를 확보할 수 있도록 제공 됩니다.  
  
##  <a name="getclientsite"></a>COleServerDoc::GetClientSite  
 원본에 대 한 포인터를 검색 `IOleClientSite` 인터페이스입니다.  
  
```  
LPOLECLIENTSITE GetClientSite() const;  
```  
  
### <a name="return-value"></a>반환 값  
 원본에 대 한 포인터를 검색 [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706) 인터페이스입니다.  
  
##  <a name="getdocobjectserver"></a>COleServerDoc::GetDocObjectServer  
 이 함수를 만드는 새 재정의 `CDocObjectServer` 항목 및에 대 한 포인터를 반환 합니다.  
  
```  
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDocSite`  
 에 대 한 포인터는 `IOleDocumentSite` 이 문서는 서버에 연결 하는 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CDocObjectServer`; **NULL** 작업이 실패 합니다.  
  
### <a name="remarks"></a>설명  
 DocObject 서버 활성화 될 때, 반환 되는 비- **NULL** 포인터 클라이언트 DocObjects를 지원할 수 있는지를 보여 줍니다. 기본 구현은 반환 **NULL**합니다.  
  
 지 원하는 DocObjects 문서에 대 한 일반적인 구현은 단순히 새 할당 `CDocObjectServer` 개체와 호출자에 게 반환 합니다. 예:  
  
 [!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]  
  
##  <a name="getembeddeditem"></a>COleServerDoc::GetEmbeddedItem  
 전체 문서를 나타내는 항목에 대 한 포인터를 가져오려면이 함수를 호출 합니다.  
  
```  
COleServerItem* GetEmbeddedItem();
```  
  
### <a name="return-value"></a>반환 값  
 전체 문서를 나타내는 항목에 대 한 포인터 **NULL** 작업이 실패 합니다.  
  
### <a name="remarks"></a>설명  
 호출 [COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem), 기본 구현 된 가상 함수입니다.  
  
##  <a name="getitemcliprect"></a>COleServerDoc::GetItemClipRect  
 호출 된 `GetItemClipRect` 위치에서 편집 중인 항목의 사각형 오려낸 좌표를 가져오려면 멤버 함수입니다.  
  
```  
void GetItemClipRect(LPRECT lpClipRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpClipRect`  
 에 대 한 포인터는 `RECT` 구조 또는 `CRect` 항목의 클리핑 사각형 좌표로 받을 개체입니다.  
  
### <a name="remarks"></a>설명  
 좌표는 컨테이너 응용 프로그램 창의 클라이언트 영역을 기준으로 합니다.  
  
 외부 클리핑 사각형 그리기 발생 하지 않습니다. 일반적으로 드로잉은 자동으로 제한 합니다. 이 함수를 사용 하 여 문서에 보이는 부분 외부 사용자가 스크롤 여부를 확인 하려면 이 경우 호출 하 여 필요에 따라 컨테이너 문서 스크롤합니다 [ScrollContainerBy](#scrollcontainerby)합니다.  
  
##  <a name="getitemposition"></a>COleServerDoc::GetItemPosition  
 호출 된 `GetItemPosition` 멤버 함수를 현재 위치에서 편집 중인 항목의 좌표를 가져옵니다.  
  
```  
void GetItemPosition(LPRECT lpPosRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpPosRect`  
 에 대 한 포인터는 `RECT` 구조 또는 `CRect` 있는 항목의 좌표를 받을 개체입니다.  
  
### <a name="remarks"></a>설명  
 좌표는 컨테이너 응용 프로그램 창의 클라이언트 영역을 기준으로 합니다.  
  
 항목을 표시 (또는 표시 되지 않는) 범위를 확인 클리핑 사각형을 현재 항목의 위치를 비교할 수 화면에 있습니다.  
  
##  <a name="getzoomfactor"></a>COleServerDoc::GetZoomFactor  
 `GetZoomFactor` 멤버 함수는 내부 편집을 위해 활성화 된 항목의 "확대/축소 비율"를 결정 합니다.  
  
```  
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,  
    LPSIZE lpSizeDenom = NULL,  
    LPCRECT lpPosRect = NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *lpSizeNum*  
 클래스의 개체에 대 한 포인터 `CSize` 확대/축소 비율의 분자를 보유 합니다. 수 **NULL**합니다.  
  
 *lpSizeDenom*  
 클래스의 개체에 대 한 포인터 `CSize` 확대/축소 비율의 분모를 보유 합니다. 수 **NULL**합니다.  
  
 `lpPosRect`  
 클래스의 개체에 대 한 포인터 `CRect` 항목의 새 위치를 설명 하는 합니다. 이 인수가 **NULL**, 함수에서 해당 항목의 현재 위치를 사용 합니다.  
  
### <a name="return-value"></a>반환 값  
 항목이 내부 활성화 된 경우 0이 아닌 편집 하 고 해당 확대/축소 비율은 100% (1:1); 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 확대/축소 비율 (픽셀)를 현재 범위에 해당 하는 항목의 크기의 비율입니다. 컨테이너 응용 프로그램 항목의 범위 내에서 자연의 범위가 설정 하지 않은 경우 (에 따른 [COleServerItem::OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)) 사용 됩니다.  
  
 분자와 분모 항목의 "확대/축소 비율입니다."를 처음 두 개의 인수를 설정 하는 함수 항목 위치에서 편집 중인 되지 함수는이 기본값은 100% (또는 1:1)에 이러한 인수를 설정 하 고 0을 반환 합니다. 자세한 내용은 기술 참고 40을 참조 하십시오. [MFC/OLE 내부 크기 조정 및 확대/축소](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)합니다.  
  
##  <a name="isdocobject"></a>COleServerDoc::IsDocObject  
 문서는 DocObject 인지 여부를 확인 합니다.  
  
```  
BOOL IsDocObject() const;  
```  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 문서가 DocObject; 그렇지 않으면 **FALSE**합니다.  
  
##  <a name="isembedded"></a>COleServerDoc::IsEmbedded  
 호출 된 `IsEmbedded` 멤버 함수를 문서 컨테이너에 포함 된 개체를 나타내는지 여부를 확인 합니다.  
  
```  
BOOL IsEmbedded() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우에는 `COleServerDoc` 개체는 개체를 나타내는 문서 컨테이너에 포함 된 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 문서 파일에서 로드 한 링크로 컨테이너 응용 프로그램에 의해 조작 될 수 있지만 포함 되지 않습니다. 컨테이너 문서에 포함 된 문서를 포함할 수로 간주 됩니다.  
  
##  <a name="isinplaceactive"></a>COleServerDoc::IsInPlaceActive  
 호출 된 `IsInPlaceActive` 멤버 함수를 현재 항목 내부 활성 상태에 적용 되는지 확인 합니다.  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우에는 `COleServerDoc` 개체 위치에 활성 상태가 그렇지 않으면 0입니다.  
  
##  <a name="notifychanged"></a>COleServerDoc::NotifyChanged  
 문서가 변경 되는 문서에 연결 된 모든 연결 된 항목을 알리지이 함수를 호출 합니다.  
  
```  
void NotifyChanged();
```  
  
### <a name="remarks"></a>설명  
 일반적으로 사용자가 서버 문서의 크기와 같은 일부 전역 특성을 변경한 후이 함수를 호출 합니다. OLE 항목 들어 자동 링크가 포함 된 문서에 연결 된 경우 해당 항목 변경 내용을 반영 하도록 업데이트 됩니다. Microsoft Foundation Class 라이브러리로 작성 된 컨테이너 응용 프로그램에는 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 의 멤버 함수 `COleClientItem` 호출 됩니다.  
  
> [!NOTE]
>  이 기능은 OLE 1 호환을 위해 제공 됩니다. 새 응용 프로그램 사용 해야 [UpdateAllItems](#updateallitems)합니다.  
  
##  <a name="notifyclosed"></a>COleServerDoc::NotifyClosed  
 문서에 닫 혔 음을 컨테이너에 알리기 위해이 함수를 호출 합니다.  
  
```  
void NotifyClosed();
```  
  
### <a name="remarks"></a>설명  
 파일 메뉴에서 [닫기] 명령을 선택 하면 `NotifyClosed` 호출한 `COleServerDoc`의의 구현은 [OnCloseDocument](../../mfc/reference/cdocument-class.md#onclosedocument) 멤버 함수입니다. Microsoft Foundation Class 라이브러리로 작성 된 컨테이너 응용 프로그램에는 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 의 멤버 함수 `COleClientItem` 호출 됩니다.  
  
##  <a name="notifyrename"></a>COleServerDoc::NotifyRename  
 사용자의 서버 문서의 이름을 후이 함수를 호출 합니다.  
  
```  
void NotifyRename(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszNewName`  
 서버 문서;의 새 이름을 지정 하는 문자열에 대 한 포인터 이것이 일반적으로 정규화 된 경로입니다.  
  
### <a name="remarks"></a>설명  
 파일 메뉴에서 다른 이름으로 저장 명령을 선택 하면 `NotifyRename` 호출한 `COleServerDoc`의의 구현은 [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument) 멤버 함수입니다. 이 함수는 OLE 시스템을 컨테이너에 알리는 하는 Dll에 알립니다. Microsoft Foundation Class 라이브러리로 작성 된 컨테이너 응용 프로그램에는 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 의 멤버 함수 `COleClientItem` 호출 됩니다.  
  
##  <a name="notifysaved"></a>COleServerDoc::NotifySaved  
 서버 문서를 저장 한 후이 함수를 호출 합니다.  
  
```  
void NotifySaved();
```  
  
### <a name="remarks"></a>설명  
 저장 명령을 파일 메뉴에서 선택 하면 `NotifySaved` 의해 라고 `COleServerDoc`의 구현의 [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument)합니다. 이 함수는 OLE 시스템을 컨테이너에 알리는 하는 Dll에 알립니다. Microsoft Foundation Class 라이브러리로 작성 된 컨테이너 응용 프로그램에는 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 의 멤버 함수 `COleClientItem` 호출 됩니다.  
  
##  <a name="onclose"></a>COleServerDoc::OnClose  
 컨테이너에서 요청 하는 서버 문서 닫을 수 있음을 경우 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnClose(OLECLOSE dwCloseOption);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwCloseOption`  
 열거형의 값 `OLECLOSE`합니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.  
  
- `OLECLOSE_SAVEIFDIRTY`수정 된 경우에 파일이 저장 됩니다.  
  
- `OLECLOSE_NOSAVE`파일은 내용이 저장 되지 않고 닫혀 있습니다.  
  
- `OLECLOSE_PROMPTSAVE`파일을 수정 하는 경우 사용자는 저장 하는 방법에 대 한 표시 됩니다.  
  
### <a name="remarks"></a>설명  
 기본 구현 호출 `CDocument::OnCloseDocument`합니다.  
  
 자세한 내용 및 추가 값에 대 한 참조 [OLECLOSE](http://msdn.microsoft.com/library/windows/desktop/ms680623) Windows sdk에서입니다.  
  
##  <a name="ondeactivate"></a>COleServerDoc::OnDeactivate  
 포함 또는 연결 된 항목을 현재 내부 활성화를 비활성화 하는 사용자는 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>설명  
 이 함수는 컨테이너 응용 프로그램의 사용자 인터페이스를 원래 상태로 복원 하 고 모든 메뉴 및 내부 활성화에 대해 생성 된 다른 컨트롤을 제거 합니다.  
  
 실행 취소 상태 정보를 무조건 해제이 시점에서.  
  
 자세한 내용은 문서 참조 [활성화](../../mfc/activation-cpp.md)...  
  
##  <a name="ondeactivateui"></a>COleServerDoc::OnDeactivateUI  
 사용자 위치에 활성화 된 항목을 비활성화 하면 호출 됩니다.  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>매개 변수  
 `bUndoable`  
 변경 내용 편집을 취소할 수 있는지 여부를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 모든 메뉴 및 내부 활성화에 대해 생성 된 다른 컨트롤 숨기기, 원래 상태로 컨테이너 응용 프로그램의 사용자 인터페이스를 복원 합니다.  
  
 프레임 워크는 항상 설정 `bUndoable` 를 **FALSE**합니다. 서버 지원 실행 취소 하는 경우 실행 취소할 수 있는 작업이입니다와 기본 클래스 구현을 호출 `bUndoable` 로 설정 **TRUE**합니다.  
  
##  <a name="ondocwindowactivate"></a>COleServerDoc::OnDocWindowActivate  
 프레임 워크를 활성화 하거나 비활성화 내부 편집에 대 한 문서 창을이 함수를 호출 합니다.  
  
```  
virtual void OnDocWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>매개 변수  
 `bActivate`  
 문서 창이 활성화 되거나 비활성화 되려고를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 제거 하거나 적절 하 게 프레임 수준의 사용자 인터페이스 요소를 추가 합니다. 항목을 포함 하는 문서 활성화 또는 비활성화 하는 경우 추가 작업을 수행 하려는 경우이 함수를 재정의 합니다.  
  
 자세한 내용은 문서 참조 [활성화](../../mfc/activation-cpp.md)...  
  
##  <a name="onexecolecmd"></a>COleServerDoc::OnExecOleCmd  
 프레임 워크에는 지정 된 명령을 실행 하거나 명령에 대 한 도움말을 표시 하려면이 함수를 호출 합니다.  
  
```  
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,  
    DWORD nCmdID,  
    DWORD nCmdExecOpt,  
    VARIANTARG* pvarargIn,  
    VARIANTARG* pvarargOut);
```  
  
### <a name="parameters"></a>매개 변수  
 `pguidCmdGroup`  
 명령 집합을 식별 하는 GUID에 대 한 포인터입니다. 수 **NULL** 기본 명령 그룹을 나타냅니다.  
  
 `nCmdID`  
 실행할 명령입니다. 로 식별 되는 그룹에 있어야 `pguidCmdGroup`합니다.  
  
 *nCmdExecOut*  
 방법은 명령, 하나 이상에서 다음 값 중 개체가 실행 해야는 **OLECMDEXECOPT** 열거:  
  
 **OLECMDEXECOPT_DODEFAULT**  
  
 **OLECMDEXECOPT_PROMPTUSER**  
  
 **OLECMDEXECOPT_DONTPROMPTUSER**  
  
 **OLECMDEXECOPT_SHOWHELP**  
  
 `pvarargIn`  
 에 대 한 포인터는 **VARIANTARG** 명령에 대 한 입력된 인수를 포함 합니다. 수 **NULL**합니다.  
  
 `pvarargOut`  
 에 대 한 포인터는 **VARIANTARG** 명령에서 출력이 반환 값을 받을 수 있습니다. 수 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 고, 그렇지 않으면 다음 오류 코드 중 하나:  
  
|값|설명|  
|-----------|-----------------|  
|**E_UNEXPECTED**|예기치 않은 오류가 발생 했습니다.|  
|**E_FAIL**|오류가 발생 했습니다.|  
|**E_NOTIMPL**|MFC 나타냅니다을 변환 하 고 명령 디스패치 하려고 해야 자체|  
|**OLECMDERR_E_UNKNOWNGROUP**|`pguidCmdGroup`이 아닌 **NULL** 하지만 인식 된 명령 그룹을 지정 하지 않습니다|  
|**OLECMDERR_E_NOTSUPPORTED**|`nCmdID`그룹에 올바른 명령으로 인식 되지 않습니다.`pguidCmdGroup`|  
|**OLECMDERR_DISABLED**|로 식별 되는 명령을 `nCmdID` 비활성화 되 고 실행할 수 없습니다|  
|**OLECMDERR_NOHELP**|호출자로 식별 되는 명령에 도움을 요청 `nCmdID` 도움말을 사용할 수 있지만|  
|**OLECMDERR_CANCELED**|사용자는 실행을 취소 했습니다.|  
  
### <a name="remarks"></a>설명  
 `COleCmdUI`사용 하도록 설정, 업데이트 및 사용자 인터페이스 명령 DocObject의 다른 속성을 설정할 데 사용할 수 있습니다. 사용 하 여 실행할 수 있습니다 명령을 초기화 된 후 `OnExecOleCmd`합니다.  
  
 프레임 워크를 변환 및 OLE 문서 명령을 발송 하기 전에 함수를 호출 합니다. 표준 OLE 문서 명령을 처리 하려면이 함수를 재정의 하지 않아도 됩니다. 하지만 사용자 지정 명령을 처리 하거나 매개 변수를 허용 또는 결과 반환 하는 명령을 처리 하려는 경우이 함수에 대 한 재정의 제공 해야 합니다.  
  
 대부분의 명령 인수를 사용 하지 않거나 값을 반환 합니다. 대부분의 명령에 대 한 호출자에 게 전달할 수 **NULL**에 대 한 s `pvarargIn` 및 `pvarargOut`합니다. 입력된 값을 예상 하는 명령에 대 한 호출자가 선언 하 고 초기화할 수는 **VARIANTARG** 변수에서 변수에 대 한 포인터를 전달 하 고 `pvarargIn`합니다. 단일 값을 필요로 하는 명령에 대 한 인수 수에 저장 될 직접는 **VARIANTARG** 함수에 전달 합니다. 내에 여러 인수를 패키지 해야 합니다는 **VARIANTARG** 지원 되는 유형 중 하나를 사용 하 여 (예: `IDispatch` 및 **SAFEARRAY** ).  
  
 마찬가지로, 명령 인수를 호출자에 게 반환 하는 경우 사용할 수를 선언 하는 **VARIANTARG**, 되도록 초기화 `VT_EMPTY`, 주소를 전달 하 고 `pvarargOut`합니다. 개체에서 직접 해당 값을 저장할 수 명령에서 단일 값을 반환 하는 경우 `pvarargOut`합니다. 여러 출력 값에 대 한 적절 한 어떤 방식으로든 패키지 해야는 **VARIANTARG**합니다.  
  
 이 함수의 기본 클래스 구현을 안내는 **OLE_COMMAND_MAP** 명령 대상 및 적절 한 처리기를 명령 디스패치 시도와 관련 된 구조입니다. 기본 클래스 구현을 반환 값 또는 인수를 허용 하지 않는 명령 에서만 작동 합니다. 이 함수를 재정의 하 고 작업을 해야 않는 인수를 허용 하거나 값을 반환 하는 명령을 처리 해야 할 경우는 `pvarargIn` 및 `pvarargOut` 매개 변수 직접 합니다.  
  
##  <a name="onframewindowactivate"></a>COleServerDoc::OnFrameWindowActivate  
 컨테이너 응용 프로그램의 프레임 창이 활성화 또는 비활성화 하는 경우 프레임 워크에서이 함수를 호출 합니다.  
  
```  
virtual void OnFrameWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>매개 변수  
 `bActivate`  
 프레임 창이 활성화 되거나 비활성화 되려고를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 프레임 창에 수도 있습니다. 모든 도움말 모드를 취소 합니다. 프레임 창이 활성화 또는 비활성화 될 때 특수 한 처리를 수행 하려는 경우이 함수를 재정의 합니다.  
  
 자세한 내용은 문서 참조 [활성화](../../mfc/activation-cpp.md)...  
  
##  <a name="ongetembeddeditem"></a>COleServerDoc::OnGetEmbeddedItem  
 컨테이너 응용 프로그램을 만들거나 포함된 된 항목을 편집할 서버 응용 프로그램을 호출할 때 프레임 워크에서 호출 합니다.  
  
```  
virtual COleServerItem* OnGetEmbeddedItem() = 0;  
```  
  
### <a name="return-value"></a>반환 값  
 전체 문서를 나타내는 항목에 대 한 포인터 **NULL** 작업이 실패 합니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 없습니다. 전체 문서를 나타내는 항목을 반환 하려면이 함수를 재정의 해야 합니다. 이 반환 값의 개체 여야 합니다.는 `COleServerItem`-클래스를 파생 합니다.  
  
##  <a name="onreactivateandundo"></a>COleServerDoc::OnReactivateAndUndo  
 프레임 워크는 사용자가 내부에서 활성화, 변경 및 이후에 비활성화 된 항목에 대 한 변경 내용을 실행 취소 하도록 선택 하는 경우이 함수를 호출 합니다.  
  
```  
virtual BOOL OnReactivateAndUndo();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 그렇지 반환 작업만 **FALSE** 실패를 나타내려면 합니다.  
  
 응용 프로그램 실행 취소를 지 원하는 경우이 함수를 재정의 합니다. 실행 취소 작업을 수행한 다음 호출 하 여 항목을 활성화 합니다는 일반적으로 `ActivateInPlace`합니다. 컨테이너 응용 프로그램 Microsoft Foundation Class 라이브러리를 작성 하는 경우 호출 `COleClientItem::ReactivateAndUndo` 하면이 함수를 호출할 수 있습니다.  
  
##  <a name="onresizeborder"></a>COleServerDoc::OnResizeBorder  
 컨테이너 응용 프로그램의 프레임 창 크기가 변경 될 때 프레임 워크에서이 함수를 호출 합니다.  
  
```  
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,  
    LPOLEINPLACEUIWINDOW lpUIWindow,  
    BOOL bFrame);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRectBorder`  
 에 대 한 포인터는 `RECT` 구조 또는 `CRect` 테두리의 좌표를 지정 하는 개체입니다.  
  
 `lpUIWindow`  
 클래스의 개체에 대 한 포인터 **IOleInPlaceUIWindow** 현재 내부 편집 세션을 소유 하는입니다.  
  
 *bFrame*  
 **TRUE** 경우 `lpUIWindow` 컨테이너 응용 프로그램의 최상위 프레임 창이 가리키는 또는 **FALSE** 경우 `lpUIWindow` 컨테이너 응용 프로그램의 문서 수준 프레임 창을 가리킵니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 크기를 조정 하 고 도구 모음과 기타 사용자 인터페이스 요소를 새 창 크기에 맞게 조정 합니다.  
  
 자세한 내용은 참조 [IOleInPlaceUIWindow](http://msdn.microsoft.com/library/windows/desktop/ms680716) Windows sdk에서입니다.  
  
 고급 재정의할 수 있습니다.  
  
##  <a name="onsethostnames"></a>COleServerDoc::OnSetHostNames  
 컨테이너를 설정 하거나이 문서에 대 한 호스트 이름을 변경 하는 경우 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnSetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszHost`  
 컨테이너 응용 프로그램의 이름을 지정 하는 문자열에 대 한 포인터입니다.  
  
 `lpszHostObj`  
 문서에 대 한 컨테이너의 이름을 지정 하는 문자열에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은이 문서를 참조 하는 모든 보기에 대 한 문서 제목을 변경 합니다.  
  
 응용 프로그램이 다른 메커니즘을 통해 제목을 설정 하는 경우이 함수를 재정의 합니다.  
  
##  <a name="onsetitemrects"></a>COleServerDoc::OnSetItemRects  
 프레임 워크의 내부 편집 프레임 창을 컨테이너 응용 프로그램의 프레임 창 내에서 위치를 지정 하려면이 함수를 호출 합니다.  
  
```  
virtual void OnSetItemRects(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpPosRect`  
 에 대 한 포인터는 `RECT` 구조 또는 `CRect` 컨테이너 응용 프로그램의 클라이언트 영역을 기준으로 내부 프레임 창 위치를 지정 하는 개체입니다.  
  
 `lpClipRect`  
 에 대 한 포인터는 `RECT` 구조 또는 `CRect` 내부 프레임 창을 클리핑 사각형 컨테이너 응용 프로그램의 클라이언트 영역을 기준으로 지정 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 필요한 경우 보기의 확대/축소 비율을 업데이트 하려면이 함수를 재정의 합니다.  
  
 이 함수는 일반적으로 대 한 응답으로 호출 됩니다는 `RequestPositionChange` 컨테이너 내부 항목에 대 한 위치 변경 요청에 의해 언제 든 지 호출할 수 있지만 호출 합니다.  
  
##  <a name="onshowcontrolbars"></a>COleServerDoc::OnShowControlBars  
 이 함수를 식별 하 여 프레임 창과 연결 된 서버 응용 프로그램의 컨트롤 막대를 표시할지를 호출 하는 프레임 워크 `pFrameWnd`합니다.  
  
```  
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFrameWnd`  
 컨트롤 막대를 숨기 거 나 표시 해야 하는 프레임 창에 대 한 포인터입니다.  
  
 `bShow`  
 컨트롤 막대는 표시 하거나 숨길 있는지 여부를 결정 합니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 프레임 창을 소유 하는 모든 컨트롤 막대를 열거 및 숨기 거 나 표시 합니다.  
  
##  <a name="onshowdocument"></a>COleServerDoc::OnShowDocument  
 호출 하 여 프레임 워크는 `OnShowDocument` 서버 문서를 숨기 거 나 표시 해야 하는 경우에 작동 합니다.  
  
```  
virtual void OnShowDocument(BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 `bShow`  
 문서에 사용자 인터페이스를 표시 하거나 숨길 수 있는지 여부를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 경우 `bShow` 은 **TRUE**, 기본 구현에서는 필요한 경우 서버 응용 프로그램을 활성화 하 고 컨테이너 응용 프로그램 항목을 볼 수 있도록 해당 창을 스크롤하여 하 합니다. 경우 `bShow` 은 **FALSE**, 호출을 통해 항목을 비활성화 하는 기본 구현은 `OnDeactivate`, 다음를 제거 하거나 첫 번째 문서에 대해 생성 된 모든 프레임 창을 숨깁니다. 문서가 없으면 표시 유지 하는 경우 기본 구현에서는 서버 응용 프로그램을 숨깁니다.  
  
##  <a name="onupdatedocument"></a>COleServerDoc::OnUpdateDocument  
 복합 문서에 포함된 된 항목은 문서를 저장 하는 경우 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnUpdateDocument();
```  
  
### <a name="return-value"></a>반환 값  
 문서가 업데이트 되었습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 기본 구현 호출은 [COleServerDoc::NotifySaved](#notifysaved) 및 [COleServerDoc::SaveEmbedding](#saveembedding) 멤버 함수 이며 다음 깨끗 문서를 표시 합니다. 특수 처리 포함된 된 항목을 업데이트할 때 수행 해야 할 경우이 함수를 재정의 합니다.  
  
##  <a name="requestpositionchange"></a>COleServerDoc::RequestPositionChange  
 이 항목의 위치를 변경 하 고 컨테이너 응용 프로그램에 함수를 호출 합니다.  
  
```  
void RequestPositionChange(LPCRECT lpPosRect);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpPosRect`  
 에 대 한 포인터는 `RECT` 구조 또는 `CRect` 항목의 새 위치를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 일반적으로 호출 (함께에서 `UpdateAllItems`) 내부 활성 항목의 데이터가 변경 되었을 때. 이 호출은 다음 컨테이너 수 또는 호출 하 여 변경 내용을 성능이 떨어질 수 있습니다 `OnSetItemRects`합니다. 결과 위치는 요청 된 것과에서 다를 수 있습니다.  
  
##  <a name="saveembedding"></a>COleServerDoc::SaveEmbedding  
 컨테이너 응용 프로그램에서 포함된 된 개체를 저장 하도록 하려면이 함수를 호출 합니다.  
  
```  
void SaveEmbedding();
```  
  
### <a name="remarks"></a>설명  
 이 함수를 자동으로 호출 `OnUpdateDocument`합니다. 이 함수는 일반적으로 특정 사용자 동작의 결과로 호출 되므로, 디스크에 업데이트할 항목을 발생 시키는 참고 합니다.  
  
##  <a name="scrollcontainerby"></a>COleServerDoc::ScrollContainerBy  
 호출 된 `ScrollContainerBy` 멤버 함수를 컨테이너 문서의 스크롤 막대 크기를 픽셀 단위로 나타낸 `sizeScroll`합니다.  
  
```  
BOOL ScrollContainerBy(CSize sizeScroll);
```  
  
### <a name="parameters"></a>매개 변수  
 `sizeScroll`  
 컨테이너 문서 스크롤해야 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 양수 값과 오른쪽 아래로 스크롤 나타냅니다. 음수 값을 왼쪽 위로 스크롤 나타냅니다.  
  
##  <a name="updateallitems"></a>COleServerDoc::UpdateAllItems  
 문서가 변경 되는 문서에 연결 된 모든 연결 된 항목을 알리지이 함수를 호출 합니다.  
  
```  
void UpdateAllItems(
    COleServerItem* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSender`  
 문서를 수정 하는 항목에 대 한 포인터 또는 **NULL** 모든 항목은 업데이트 해야 하는 경우.  
  
 `lHint`  
 수정에 대 한 정보를 포함합니다.  
  
 `pHint`  
 수정에 대 한 정보를 저장 하는 개체에 대 한 포인터입니다.  
  
 `nDrawAspect`  
 항목을 그릴 수 있도록 방법을 결정 합니다. 이 값은에서 값의 `DVASPECT` 열거형입니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.  
  
- `DVASPECT_CONTENT`항목은 해당 컨테이너 내에 포함 된 개체로 표시 될 수 하는 방식으로 표시 됩니다.  
  
- `DVASPECT_THUMBNAIL`검색 도구에 표시 될 수 있도록 "미리" 표현에서 항목이 렌더링 됩니다.  
  
- `DVASPECT_ICON`항목은 아이콘으로 표시 됩니다.  
  
- `DVASPECT_DOCPRINT`항목 파일 메뉴에서 인쇄 명령을 사용 하 여 인쇄할 때 처럼 표시 됩니다.  
  
### <a name="remarks"></a>설명  
 일반적으로 사용자는 서버 문서를 변경한 후이 함수를 호출 합니다. OLE 항목 들어 자동 링크가 포함 된 문서에 연결 된 경우 해당 항목 변경 내용을 반영 하도록 업데이트 됩니다. Microsoft Foundation Class 라이브러리로 작성 된 컨테이너 응용 프로그램에는 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 의 멤버 함수 `COleClientItem` 호출 됩니다.  
  
 이 함수 호출의 `OnUpdate` 각 보내는 항목을 전달 하는 제외 하 고 문서 항목에 대 한 멤버 함수 `pHint`, `lHint`, 및 `nDrawAspect`합니다. 이러한 매개 변수를 사용 하 여 수정 내용에 문서에 대 한 항목에 정보를 전달 합니다. 사용 하 여 정보를 인코딩할 수 `lHint` 하거나 정의할 수 있습니다는 `CObject`-수정 작업에 대 한 정보를 저장 하 고 사용 하 여 해당 클래스의 개체를 전달 하는 클래스를 파생 `pHint`합니다. 재정의 `OnUpdate` 멤버 함수에서 프로그램 `COleServerItem`-표시 변경 되었는지 여부에 따라 각 항목의 업데이트를 최적화 하는 클래스를 파생 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 HIERSVR](../../visual-cpp-samples.md)   
 [COleLinkingDoc 클래스](../../mfc/reference/colelinkingdoc-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDocument 클래스](../../mfc/reference/coledocument-class.md)   
 [COleLinkingDoc 클래스](../../mfc/reference/colelinkingdoc-class.md)   
 [COleTemplateServer 클래스](../../mfc/reference/coletemplateserver-class.md)
