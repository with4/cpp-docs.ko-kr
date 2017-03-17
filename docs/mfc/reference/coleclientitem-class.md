---
title: "활성화 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleClientItem
- AFXOLE/COleClientItem
- AFXOLE/COleClientItem::COleClientItem
- AFXOLE/COleClientItem::Activate
- AFXOLE/COleClientItem::ActivateAs
- AFXOLE/COleClientItem::AttachDataObject
- AFXOLE/COleClientItem::CanCreateFromData
- AFXOLE/COleClientItem::CanCreateLinkFromData
- AFXOLE/COleClientItem::CanPaste
- AFXOLE/COleClientItem::CanPasteLink
- AFXOLE/COleClientItem::Close
- AFXOLE/COleClientItem::ConvertTo
- AFXOLE/COleClientItem::CopyToClipboard
- AFXOLE/COleClientItem::CreateCloneFrom
- AFXOLE/COleClientItem::CreateFromClipboard
- AFXOLE/COleClientItem::CreateFromData
- AFXOLE/COleClientItem::CreateFromFile
- AFXOLE/COleClientItem::CreateLinkFromClipboard
- AFXOLE/COleClientItem::CreateLinkFromData
- AFXOLE/COleClientItem::CreateLinkFromFile
- AFXOLE/COleClientItem::CreateNewItem
- AFXOLE/COleClientItem::CreateStaticFromClipboard
- AFXOLE/COleClientItem::CreateStaticFromData
- AFXOLE/COleClientItem::Deactivate
- AFXOLE/COleClientItem::DeactivateUI
- AFXOLE/COleClientItem::Delete
- AFXOLE/COleClientItem::DoDragDrop
- AFXOLE/COleClientItem::DoVerb
- AFXOLE/COleClientItem::Draw
- AFXOLE/COleClientItem::GetActiveView
- AFXOLE/COleClientItem::GetCachedExtent
- AFXOLE/COleClientItem::GetClassID
- AFXOLE/COleClientItem::GetClipboardData
- AFXOLE/COleClientItem::GetDocument
- AFXOLE/COleClientItem::GetDrawAspect
- AFXOLE/COleClientItem::GetExtent
- AFXOLE/COleClientItem::GetIconFromRegistry
- AFXOLE/COleClientItem::GetIconicMetafile
- AFXOLE/COleClientItem::GetInPlaceWindow
- AFXOLE/COleClientItem::GetItemState
- AFXOLE/COleClientItem::GetLastStatus
- AFXOLE/COleClientItem::GetLinkUpdateOptions
- AFXOLE/COleClientItem::GetType
- AFXOLE/COleClientItem::GetUserType
- AFXOLE/COleClientItem::IsInPlaceActive
- AFXOLE/COleClientItem::IsLinkUpToDate
- AFXOLE/COleClientItem::IsModified
- AFXOLE/COleClientItem::IsOpen
- AFXOLE/COleClientItem::IsRunning
- AFXOLE/COleClientItem::OnActivate
- AFXOLE/COleClientItem::OnActivateUI
- AFXOLE/COleClientItem::OnChange
- AFXOLE/COleClientItem::OnDeactivate
- AFXOLE/COleClientItem::OnDeactivateUI
- AFXOLE/COleClientItem::OnGetClipboardData
- AFXOLE/COleClientItem::OnInsertMenus
- AFXOLE/COleClientItem::OnRemoveMenus
- AFXOLE/COleClientItem::OnSetMenu
- AFXOLE/COleClientItem::OnShowControlBars
- AFXOLE/COleClientItem::OnUpdateFrameTitle
- AFXOLE/COleClientItem::ReactivateAndUndo
- AFXOLE/COleClientItem::Release
- AFXOLE/COleClientItem::Reload
- AFXOLE/COleClientItem::Run
- AFXOLE/COleClientItem::SetDrawAspect
- AFXOLE/COleClientItem::SetExtent
- AFXOLE/COleClientItem::SetHostNames
- AFXOLE/COleClientItem::SetIconicMetafile
- AFXOLE/COleClientItem::SetItemRects
- AFXOLE/COleClientItem::SetLinkUpdateOptions
- AFXOLE/COleClientItem::SetPrintDevice
- AFXOLE/COleClientItem::UpdateLink
- AFXOLE/COleClientItem::CanActivate
- AFXOLE/COleClientItem::OnChangeItemPosition
- AFXOLE/COleClientItem::OnDeactivateAndUndo
- AFXOLE/COleClientItem::OnDiscardUndoState
- AFXOLE/COleClientItem::OnGetClipRect
- AFXOLE/COleClientItem::OnGetItemPosition
- AFXOLE/COleClientItem::OnGetWindowContext
- AFXOLE/COleClientItem::OnScrollBy
- AFXOLE/COleClientItem::OnShowItem
dev_langs:
- C++
helpviewer_keywords:
- OLE containers, client items
- COleClientItem class
- OLE client item class
- container interface class
- OLE containers, interface class
- client items and OLE containers
ms.assetid: 7f571b7c-2758-4839-847a-0cf1ef643128
caps.latest.revision: 24
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
ms.openlocfilehash: a200da03305c20eaf2d9c1de1ea585c82410c570
ms.lasthandoff: 02/24/2017

---
# <a name="coleclientitem-class"></a>활성화 클래스
OLE 항목에 대한 컨테이너 인터페이스를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleClientItem : public CDocItem  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleClientItem::COleClientItem](#coleclientitem)|`COleClientItem` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleClientItem::Activate](#activate)|작업에 대 한 OLE 항목 열리고 지정된 된 동사를 실행 합니다.|  
|[COleClientItem::ActivateAs](#activateas)|다른 형식으로 항목을 활성화합니다.|  
|[COleClientItem::AttachDataObject](#attachdataobject)|OLE 개체의에서 데이터에 액세스합니다.|  
|[COleClientItem::CanCreateFromData](#cancreatefromdata)|컨테이너 응용 프로그램 포함된 된 개체를 만들 수 있는지 여부를 나타냅니다.|  
|[COleClientItem::CanCreateLinkFromData](#cancreatelinkfromdata)|컨테이너 응용 프로그램의 연결된 된 개체를 만들 수 있는지 여부를 나타냅니다.|  
|[COleClientItem::CanPaste](#canpaste)|클립보드 돌출형 또는 정적 OLE 항목에 포함 되어 있는지 여부를 나타냅니다.|  
|[COleClientItem::CanPasteLink](#canpastelink)|연결 가능한 OLE 항목을 클립보드에 포함 되어 있는지 여부를 나타냅니다.|  
|[COleClientItem::Close](#close)|서버에 대 한 링크를 닫지만에서는 OLE 항목을 제거 하지 않습니다.|  
|[COleClientItem::ConvertTo](#convertto)|항목을 다른 형식으로 변환합니다.|  
|[COleClientItem::CopyToClipboard](#copytoclipboard)|OLE 항목을 클립보드에 복사합니다.|  
|[COleClientItem::CreateCloneFrom](#createclonefrom)|기존 항목의 복제본을 만듭니다.|  
|[COleClientItem::CreateFromClipboard](#createfromclipboard)|클립보드의 포함된 된 항목을 만듭니다.|  
|[COleClientItem::CreateFromData](#createfromdata)|데이터 개체에서 포함된 된 항목을 만듭니다.|  
|[COleClientItem::CreateFromFile](#createfromfile)|파일에서 포함된 된 항목을 만듭니다.|  
|[COleClientItem::CreateLinkFromClipboard](#createlinkfromclipboard)|클립보드의 연결된 된 항목을 만듭니다.|  
|[COleClientItem::CreateLinkFromData](#createlinkfromdata)|데이터 개체에서 연결된 된 항목을 만듭니다.|  
|[COleClientItem::CreateLinkFromFile](#createlinkfromfile)|파일에서 연결된 된 항목을 만듭니다.|  
|[COleClientItem::CreateNewItem](#createnewitem)|서버 응용 프로그램을 시작 하 여 새 포함 된 항목을 만듭니다.|  
|[COleClientItem::CreateStaticFromClipboard](#createstaticfromclipboard)|클립보드의 정적 항목을 만듭니다.|  
|[COleClientItem::CreateStaticFromData](#createstaticfromdata)|데이터 개체에서 정적 항목을 만듭니다.|  
|[COleClientItem::Deactivate](#deactivate)|항목을 비활성화합니다.|  
|[COleClientItem::DeactivateUI](#deactivateui)|컨테이너 응용 프로그램의 사용자 인터페이스를 원래 상태로 복원합니다.|  
|[COleClientItem::Delete](#delete)|삭제 하거나 연결된 된 항목 되었으면 OLE 항목을 닫습니다.|  
|[COleClientItem::DoDragDrop](#dodragdrop)|끌어서 놓기 작업을 수행합니다.|  
|[COleClientItem::DoVerb](#doverb)|지정된 된 동사를 실행합니다.|  
|[COleClientItem::Draw](#draw)|OLE 항목을 그립니다.|  
|[COleClientItem::GetActiveView](#getactiveview)|내부에서 활성화 될 항목이 있는 뷰를 가져옵니다.|  
|[COleClientItem::GetCachedExtent](#getcachedextent)|OLE 항목의 사각형의 경계를 반환합니다.|  
|[COleClientItem::GetClassID](#getclassid)|현재 항목의 클래스 ID를 가져옵니다.|  
|[COleClientItem::GetClipboardData](#getclipboarddata)|호출 하 여 클립보드에 배치 하는 데이터를 가져옵니다는 `CopyToClipboard` 멤버 함수입니다.|  
|[COleClientItem::GetDocument](#getdocument)|반환 된 `COleDocument` 있는 항목을 포함 하는 개체입니다.|  
|[COleClientItem::GetDrawAspect](#getdrawaspect)|렌더링에 대 한 항목의 현재 뷰를 가져옵니다.|  
|[COleClientItem::GetExtent](#getextent)|OLE 항목의 사각형의 경계를 반환합니다.|  
|[COleClientItem::GetIconFromRegistry](#geticonfromregistry)|CLSID에 특정 서버에 연결 된 아이콘에 대 한 핸들을 검색 합니다.|  
|[COleClientItem::GetIconicMetafile](#geticonicmetafile)|항목의 아이콘을 그리는 데 사용 하 여 메타 파일을 가져옵니다.|  
|[COleClientItem::GetInPlaceWindow](#getinplacewindow)|항목의 전체 편집 창에 대 한 포인터를 반환합니다.|  
|[COleClientItem::GetItemState](#getitemstate)|항목의 현재 상태를 가져옵니다.|  
|[COleClientItem::GetLastStatus](#getlaststatus)|마지막 OLE 작업의 상태를 반환합니다.|  
|[COleClientItem::GetLinkUpdateOptions](#getlinkupdateoptions)|연결된 된 항목 (고급 기능)에 대 한 업데이트 모드를 반환합니다.|  
|[COleClientItem::GetType](#gettype)|OLE 항목의 유형 (포함 된, 연결, 또는 정적)를 반환합니다.|  
|[COleClientItem::GetUserType](#getusertype)|항목의 형식을 설명 하는 문자열을 가져옵니다.|  
|[COleClientItem::IsInPlaceActive](#isinplaceactive)|반환 `TRUE` 항목이에 내부 활성화 해야 하는 경우.|  
|[COleClientItem::IsLinkUpToDate](#islinkuptodate)|반환 **TRUE** 항목이 있는 경우 연결 된 원본 문서와 최신 상태입니다.|  
|[COleClientItem::IsModified](#ismodified)|반환 `TRUE` 항목이 마지막으로 저장 된 이후 수정 된 경우.|  
|[COleClientItem::IsOpen](#isopen)|반환 `TRUE` 항목이 서버 응용 프로그램에서 현재 열려 있는 경우.|  
|[COleClientItem::IsRunning](#isrunning)|반환 `TRUE` 항목의 서버 응용 프로그램을 실행 하는 경우.|  
|[COleClientItem::OnActivate](#onactivate)|활성화 되는 항목에 알리기 위해 프레임 워크에 의해 호출 됩니다.|  
|[COleClientItem::OnActivateUI](#onactivateui)|활성화 된 해당 사용자 인터페이스를 표시 해야 하는 항목에 알리기 위해 프레임 워크에 의해 호출 됩니다.|  
|[COleClientItem::OnChange](#onchange)|OLE 항목을 변경 하는 서버 때 호출 됩니다. 필요한 구현입니다.|  
|[COleClientItem::OnDeactivate](#ondeactivate)|항목 비활성화 된 경우에 프레임 워크에서 호출 합니다.|  
|[COleClientItem::OnDeactivateUI](#ondeactivateui)|서버는 해당 위치에서 사용자 인터페이스를 제거 하는 경우에 프레임 워크에서 호출 합니다.|  
|[COleClientItem::OnGetClipboardData](#ongetclipboarddata)|클립보드에 복사할 데이터를 가져오기 위해 프레임 워크에 의해 호출 됩니다.|  
|[COleClientItem::OnInsertMenus](#oninsertmenus)|복합 메뉴를 만드는 프레임 워크에 의해 호출 됩니다.|  
|[COleClientItem::OnRemoveMenus](#onremovemenus)|복합 메뉴에서 컨테이너의 메뉴를 제거 하려면 프레임 워크에 의해 호출 됩니다.|  
|[COleClientItem::OnSetMenu](#onsetmenu)|설치 하 고 제거 하 여 복합 프레임 워크에 의해 호출 됩니다.|  
|[COleClientItem::OnShowControlBars](#onshowcontrolbars)|표시 하 고 컨트롤 막대를 숨기는 프레임 워크에서 호출 됩니다.|  
|[COleClientItem::OnUpdateFrameTitle](#onupdateframetitle)|프레임 창의 제목 표시줄을 업데이트 하는 프레임 워크에서 호출 됩니다.|  
|[COleClientItem::ReactivateAndUndo](#reactivateandundo)|항목을 다시 활성화 하 고 마지막 위치에서 편집 작업을 취소 합니다.|  
|[COleClientItem::Release](#release)|OLE 링크 된 항목에 대 한 연결을 해제 하 고 열려 있으면 닫습니다. 클라이언트 항목을 제거 하지 않습니다.|  
|[COleClientItem::Reload](#reload)|함수 호출 후에 다시 로드 하는 항목 `ActivateAs`합니다.|  
|[COleClientItem::Run](#run)|항목에 연결 된 응용 프로그램을 실행 합니다.|  
|[COleClientItem::SetDrawAspect](#setdrawaspect)|렌더링에 대 한 항목의 현재 보기를 설정합니다.|  
|[COleClientItem::SetExtent](#setextent)|OLE 항목의 경계 사각형을 설정합니다.|  
|[COleClientItem::SetHostNames](#sethostnames)|OLE 항목을 편집할 때 서버 표시 이름을 설정 합니다.|  
|[COleClientItem::SetIconicMetafile](#seticonicmetafile)|항목의 아이콘을 그리는 데 사용 하 여 메타 파일을 캐시 합니다.|  
|[COleClientItem::SetItemRects](#setitemrects)|항목의 경계 사각형을 설정합니다.|  
|[COleClientItem::SetLinkUpdateOptions](#setlinkupdateoptions)|연결된 된 항목 (고급 기능)에 대 한 업데이트 모드를 설정합니다.|  
|[COleClientItem::SetPrintDevice](#setprintdevice)|이 클라이언트 항목에 대 한 대상 인쇄 장치를 설정합니다.|  
|[COleClientItem::UpdateLink](#updatelink)|항목의 프레젠테이션 캐시를 업데이트 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleClientItem::CanActivate](#canactivate)|내부 활성화 허용 되는지 여부를 결정 하는 프레임 워크에서 호출 됩니다.|  
|[COleClientItem::OnChangeItemPosition](#onchangeitemposition)|항목의 위치 변경 될 때 프레임 워크에 의해 호출 됩니다.|  
|[COleClientItem::OnDeactivateAndUndo](#ondeactivateandundo)|활성화 된 후 실행 취소 하는 프레임 워크에서 호출 됩니다.|  
|[COleClientItem::OnDiscardUndoState](#ondiscardundostate)|항목의 실행 취소 상태 정보를 삭제 하는 프레임 워크에서 호출 됩니다.|  
|[COleClientItem::OnGetClipRect](#ongetcliprect)|항목의 클리핑 사각형의 좌표를 가져오기 위해 프레임 워크에서 호출 됩니다.|  
|[COleClientItem::OnGetItemPosition](#ongetitemposition)|보기를 기준으로 항목의 위치를 가져오기 위해 프레임 워크에 의해 호출 됩니다.|  
|[COleClientItem::OnGetWindowContext](#ongetwindowcontext)|항목 위치에서 활성화 될 때 프레임 워크에서 호출 합니다.|  
|[COleClientItem::OnScrollBy](#onscrollby)|항목 보기로 스크롤할 프레임 워크에 의해 호출 됩니다.|  
|[COleClientItem::OnShowItem](#onshowitem)|OLE 항목을 표시 하는 프레임 워크에서 호출 됩니다.|  
  
## <a name="remarks"></a>주의  
 OLE 항목 데이터를 통합할 수 있습니다 "원활 하 게" 문서를 단일 문서 사용자에 게 표시 되도록 하는 서버 응용 프로그램에서 만들고 유지 관리를 나타냅니다. 결과 "복합 문서"를 포함 하는 문서와 OLE 항목으로 이루어져 있습니다.  
  
 OLE 항목 포함 되거나 연결 될 수 있습니다. 포함 된 경우 해당 데이터는 복합 문서의 일부로 저장 됩니다. 이 연결 된 경우 해당 데이터는 별도 서버 응용 프로그램에서 만든 파일의 일부로 저장 됩니다 하 고 해당 파일에 대 한 링크만 복합 문서에 저장 됩니다. 모든 OLE 항목 편집을 호출 해야 하는 서버 응용 프로그램을 지정 하는 정보를 포함 합니다.  
  
 `COleClientItem`서버 응용 프로그램에서 요청에 대 한 응답으로 호출 하는 여러 재정의 가능한 함수 정의 이러한 함수는 일반적으로 알림으로 작동합니다. 이렇게 하면 서버 응용 프로그램의 컨테이너에 OLE 항목을 편집할 때 사용자가 변경 내용 알리기 위해 또는 편집 중에 필요한 정보를 검색할 수 있습니다.  
  
 `COleClientItem`함께 사용할 수는 [COleDocument](../../mfc/reference/coledocument-class.md), [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), 또는 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) 클래스입니다. 사용 하 여 `COleClientItem`에서 클래스를 파생 하 고 구현에서 [OnChange](#onchange) 컨테이너 항목에 대 한 변경 내용에 응답 하는 방법을 정의 하는 멤버 함수입니다. 내부 활성화를 지원 하기 위해 재정의 [OnGetItemPosition](#ongetitemposition) 멤버 함수입니다. 이 함수는 OLE 항목의 표시 된 위치에 대 한 정보를 제공합니다.  
  
 컨테이너 인터페이스를 사용 하는 방법에 대 한 자세한 내용은 문서를 참조 [컨테이너: 컨테이너 구현](../../mfc/containers-implementing-a-container.md) 및 [활성화](../../mfc/activation-cpp.md)합니다.  
  
> [!NOTE]
>  [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 포함 및 연결 된 항목으로 "개체"를 참조 하 고 종류의 항목으로 "classes"를 선택 합니다. 이 참조는 해당 하는 c + + 개체 및 c + + 클래스에서 OLE 범주를 구분 하기 위해 "type" 라는 용어는 OLE 엔터티 구분 하기 위해 "item" 이라는 용어를 사용 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleClientItem`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="activate"></a>COleClientItem::Activate  
 대신 지정된 된 동사를 실행 하려면이 함수를 호출 [DoVerb](#doverb) 예외가 throw 되 면 직접 처리 하는 작업을 수행할 수 있도록 합니다.  
  
```  
void Activate(
    LONG nVerb,  
    CView* pView,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `nVerb`  
 실행 하는 동사를 지정 합니다. 다음 중 하나일 수 있습니다.  
  
|값|의미|기호|  
|-----------|-------------|------------|  
|– 0|기본 동사|`OLEIVERB_PRIMARY`|  
|– 1|보조 동사|(None)|  
|– 1|편집을 위해 표시 항목|`OLEIVERB_SHOW`|  
|– 2|별도 창에서 항목 편집|`OLEIVERB_OPEN`|  
|– 3|항목 숨기기|`OLEIVERB_HIDE`|  
  
 일반적으로-1 값은 다른 동사에 대 한 별칭입니다. 열기 편집 지원 되지 않는 경우-2는 것과 동일한 효과가-1입니다. 추가 값에 대 한 참조 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `pView`  
 OLE 항목;를 포함 하는 컨테이너 보기 창에 대 한 포인터 이 위치에서 활성화에 대 한 서버 응용 프로그램에서 사용 됩니다. 이 매개 변수 여야 **NULL** 컨테이너 내부 활성화를 지원 하지 않는 경우.  
  
 `lpMsg`  
 항목을 활성화할 수를 발생 시킨 메시지에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 Microsoft Foundation Class 라이브러리를 사용 하 여 서버 응용 프로그램이 작성 하는 경우에이 함수로는 [OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb) 멤버 함수는 해당 `COleServerItem` 실행할 개체입니다.  
  
 기본 동사는 편집 및&0;에 지정 된 경우는 `nVerb` OLE 항목을 편집할 수 있도록 매개 변수를 서버 응용 프로그램이 시작 됩니다. 컨테이너 응용 프로그램에서 내부 활성화를 지 원하는 경우 편집 가능 위치에 있습니다. 컨테이너 내부 활성화 (또는 Open 동사를 지정 하는 경우)을 지원 하지 않으면 서버가 별도 창에서 시작 되 고 편집 할 수 있습니다. 일반적으로 컨테이너 응용 프로그램의 사용자 두 번 클릭 하면 OLE 항목을 기본 동사에 대 한 값은 `nVerb` 매개 변수는 사용자가 수행할 수 있는 작업을 결정 합니다. 그러나 서버에서 하나의 작업을 지 원하는 경우 시간이에 지정 된 값에 관계 없이 해당 동작을는 `nVerb` 매개 변수입니다.  
  
 자세한 내용은 참조 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="activateas"></a>COleClientItem::ActivateAs  
 OLE의 개체 변환 기능을 사용 하 여 지정 된 형식의 항목 것 처럼 항목을 활성화 하 `clsidNew`합니다.  
  
```  
virtual BOOL ActivateAs(
    LPCTSTR lpszUserType,  
    REFCLSID clsidOld,  
    REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszUserType*  
 "Word 문서입니다."와 같은 대상 사용자 유형을 나타내는 문자열에 대 한 포인터  
  
 *clsidOld*  
 항목의 현재 클래스에 대 한 참조 id입니다. 클래스 ID를 나타내야 실제 개체의 유형을 저장 시, 하지 않은 경우 링크 합니다. 이 경우 링크를 참조 하는 항목의 CLSID 해야 합니다. [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md) 자동으로 해당 항목에 대 한 올바른 클래스 ID를 제공 합니다.  
  
 `clsidNew`  
 대상 클래스 ID에 대 한 참조  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 자동으로 호출 됩니다 [COleConvertDialog::DoConvert](../../mfc/reference/coleconvertdialog-class.md#doconvert)합니다. 이 일반적으로 직접 호출 되지 합니다.  
  
##  <a name="attachdataobject"></a>COleClientItem::AttachDataObject  
 초기화 하려면이 함수를 호출 하는 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE 항목의 데이터에 액세스 합니다.  
  
```  
void AttachDataObject(COleDataObject& rDataObject) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *rDataObject*  
 에 대 한 참조는 `COleDataObject` OLE 항목에서 데이터에 대 한 액세스를 허용 하도록 초기화 될 개체입니다.  
  
##  <a name="canactivate"></a>COleClientItem::CanActivate  
 사용자가 OLE 항목;의 내부 활성화를 요청할 때 프레임 워크에서 호출 이 함수의 반환 값은 현재 위치 활성화 허용 되는지 여부를 결정 합니다.  
  
```  
virtual BOOL CanActivate();
```  
  
### <a name="return-value"></a>반환 값  
 내부 활성화 허용 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현에서는 컨테이너에 유효한 창 하는 경우 내부 활성화를 허용 합니다. 수락 또는 거절 정품 인증 요청에 대 한 특별 한 논리를 구현 하려면이 함수를 재정의 합니다. 예를 들어 OLE 항목이 너무 작거나 현재 표시 되지 않는 경우 정품 인증 요청을 거부할 수 있습니다.  
  
 자세한 내용은 참조 [IOleInPlaceSite::CanInPlaceActivate](http://msdn.microsoft.com/library/windows/desktop/ms691236) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="cancreatefromdata"></a>COleClientItem::CanCreateFromData  
 컨테이너 응용 프로그램에서 포함된 된 개체를 만들 수 있는지 검사는 주어진 `COleDataObject` 개체입니다.  
  
```  
static BOOL PASCAL CanCreateFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDataObject`  
 에 대 한 포인터는 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE 항목 만들 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 컨테이너에서 포함된 된 개체를 만들 수 있으면 0이 아닌는 `COleDataObject` 개체 하 고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 `COleDataObject` 클래스 끌어서 놓기를 통해 클립보드에서 또는 포함된 된 OLE 항목에서 다양 한 형식의 데이터를에서 검색 하는 것에 대 한 데이터 전송에 사용 됩니다.  
  
 컨테이너를 자신의 붙여넣기 편집 하 고 편집 하 여 붙여넣기 명령을 사용할지 여부를 결정이 함수를 사용할 수 있습니다.  
  
 자세한 내용은 문서를 참조 하십시오. [데이터 개체 및 데이터 소스 (OLE)](../../mfc/data-objects-and-data-sources-ole.md)합니다.  
  
##  <a name="cancreatelinkfromdata"></a>COleClientItem::CanCreateLinkFromData  
 컨테이너 응용 프로그램에서 연결된 된 개체를 만들 수 있는지 검사는 주어진 `COleDataObject` 개체입니다.  
  
```  
static BOOL PASCAL CanCreateLinkFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDataObject`  
 에 대 한 포인터는 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE 항목 만들 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 컨테이너에서 연결된 된 개체를 만들 수 있으면&0;이 아닌는 `COleDataObject` 개체입니다.  
  
### <a name="remarks"></a>주의  
 `COleDataObject` 클래스 끌어서 놓기를 통해 클립보드에서 또는 포함된 된 OLE 항목에서 다양 한 형식의 데이터를에서 검색 하는 것에 대 한 데이터 전송에 사용 됩니다.  
  
 컨테이너를 자신의 편집 하 여 붙여넣기 및 편집 링크 붙여넣기 명령을 사용할지 여부를 결정이 함수를 사용할 수 있습니다.  
  
 자세한 내용은 문서를 참조 하십시오. [데이터 개체 및 데이터 소스 (OLE)](../../mfc/data-objects-and-data-sources-ole.md)합니다.  
  
##  <a name="canpaste"></a>COleClientItem::CanPaste  
 포함된 된 OLE 항목 클립보드에서 붙여 넣을 수 있는지 여부를 표시 하려면이 함수를 호출 합니다.  
  
```  
static BOOL PASCAL CanPaste();
```  
  
### <a name="return-value"></a>반환 값  
 포함된 된 OLE 항목; 클립보드에서 붙여 넣을 수 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778) 및 [OleQueryCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms683739) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="canpastelink"></a>COleClientItem::CanPasteLink  
 연결 된 OLE 항목을 클립보드에서 붙여 넣을 수 있는지 여부를 표시 하려면이 함수를 호출 합니다.  
  
```  
static BOOL PASCAL CanPasteLink();
```  
  
### <a name="return-value"></a>반환 값  
 연결된 된 OLE 항목; 클립보드에서 붙여 넣을 수 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778) 및 [OleQueryLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms690244) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="close"></a>COleClientItem::Close  
 메모리에 해당 처리기 하지만 실행 하지 않는 서버를 로드 합니다. 즉, 로드 된 상태로 실행 상태에서 OLE 항목의 상태를 변경 하려면이 함수를 호출 합니다.  
  
```  
void Close(OLECLOSE dwCloseOption = OLECLOSE_SAVEIFDIRTY);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwCloseOption`  
 OLE 항목을 어떤 상황에서 플래그를 지정 하는 로드 된 상태로 반환 될 때 저장 됩니다. 다음 값 중 하나일 수 있습니다.  
  
- `OLECLOSE_SAVEIFDIRTY`OLE 항목을 저장 합니다.  
  
- `OLECLOSE_NOSAVE`OLE 항목을 저장 하지 마십시오.  
  
- `OLECLOSE_PROMPTSAVE`OLE 항목을 저장할 것인지 여부에 사용자 메시지를 표시 합니다.  
  
### <a name="remarks"></a>주의  
 OLE 항목이 실행 되지 않는 경우에이 함수를 사용 해도 아무 효과가 없습니다.  
  
 자세한 내용은 참조 [IOleObject::Close](http://msdn.microsoft.com/library/windows/desktop/ms683922) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="coleclientitem"></a>COleClientItem::COleClientItem  
 생성 된 `COleClientItem` 개체는 c + + 개체를 생성 하 고 모든 OLE 초기화를 수행 하지 않습니다, 문서 항목의 컨테이너 문서의 컬렉션에 추가 합니다.  
  
```  
COleClientItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pContainerDoc`  
 이 항목에 포함 될 컨테이너 문서에 대 한 포인터입니다. 될 수 있습니다 [COleDocument](../../mfc/reference/coledocument-class.md) 파생 항목입니다.  
  
### <a name="remarks"></a>주의  
 전달 하는 경우는 **NULL** 포인터 추가 없음 컨테이너 문서에 이루어집니다. 명시적으로 호출 해야 [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem)합니다.  
  
 OLE 항목을 사용 하기 전에 생성 멤버 함수는 다음 중 하나를 호출 해야 합니다.  
  
- [CreateFromClipboard](#createfromclipboard)  
  
- [CreateFromData](#createfromdata)  
  
- [CreateFromFile](#createfromfile)  
  
- [CreateStaticFromClipboard](#createstaticfromclipboard)  
  
- [CreateStaticFromData](#createstaticfromdata)  
  
- [CreateLinkFromClipboard](#createlinkfromclipboard)  
  
- [CreateLinkFromData](#createlinkfromdata)  
  
- [CreateLinkFromFile](#createlinkfromfile)  
  
- [CreateNewItem](#createnewitem)  
  
- [CreateCloneFrom](#createclonefrom)  
  
##  <a name="convertto"></a>COleClientItem::ConvertTo  
 이 멤버 함수를 호출 하 여 지정 된 형식과 항목 변환 `clsidNew`합니다.  
  
```  
virtual BOOL ConvertTo(REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>매개 변수  
 `clsidNew`  
 클래스 ID는 대상 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 자동으로 호출 됩니다 [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)합니다. 직접 호출할 필요는 없습니다.  
  
##  <a name="copytoclipboard"></a>COleClientItem::CopyToClipboard  
 OLE 항목을 클립보드로 복사 하려면이 함수를 호출 합니다.  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bIncludeLink`  
 **True 이면** 연결 정보를 클립보드로 복사할지, 붙여 넣은 하 고 그렇지 않으면 연결된 된 항목 허용 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 일반적으로 편집 메뉴에서 복사 또는 잘라내기 명령에 대 한 메시지 처리기를 작성 하는 경우이 함수를 호출 합니다. 복사 또는 잘라내기 명령 구현 하려는 경우 컨테이너 응용 프로그램에서 선택 항목을 구현 해야 합니다.  
  
 자세한 내용은 참조 [OleSetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms686623) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="createclonefrom"></a>COleClientItem::CreateCloneFrom  
 지정된 된 OLE 항목의 복사본을 만들고이 함수를 호출 합니다.  
  
```  
BOOL CreateCloneFrom(const COleClientItem* pSrcItem);
```  
  
### <a name="parameters"></a>매개 변수  
 *pSrcItem*  
 복제 하려면 OLE 항목에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 복사는 소스 항목에 동일 합니다. 실행 취소 작업을 지원 하기 위해이 함수를 사용할 수 있습니다.  
  
##  <a name="createfromclipboard"></a>COleClientItem::CreateFromClipboard  
 클립보드의 내용에서 포함된 된 항목을 만들려면이 함수를 호출 합니다.  
  
```  
BOOL CreateFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *렌더링*  
 서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값에 대 한 참조 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `cfFormat`  
 OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.  
  
 `lpFormatEtc`  
 에 대 한 포인터는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조를 사용 하는 경우 *렌더링* 는 **OLERENDER_FORMAT** 또는 **OLERENDER_DRAW**합니다. 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에이 매개 변수 값을 제공 `cfFormat`합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 일반적으로 편집 메뉴에서 붙여넣기 명령에 대 한 메시지 처리기에서이 함수를 호출 합니다. (경우에 붙여넣기 명령 프레임 워크에서 사용할 수는 [CanPaste](#canpaste)&0;이 아닌 멤버 함수를 반환 합니다.)  
  
 자세한 내용은 참조 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="createfromdata"></a>COleClientItem::CreateFromData  
 포함된 된 항목을 만들려면이 함수를 호출 하는 `COleDataObject` 개체입니다.  
  
```  
BOOL CreateFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDataObject`  
 에 대 한 포인터는 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE 항목 만들 개체입니다.  
  
 *렌더링*  
 서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값에 대 한 참조 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `cfFormat`  
 OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.  
  
 `lpFormatEtc`  
 에 대 한 포인터는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조를 사용 하는 경우 *렌더링* 는 **OLERENDER_FORMAT** 또는 **OLERENDER_DRAW**합니다. 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에이 매개 변수 값을 제공 `cfFormat`합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 클립보드 또는 끌어 놓기 작업의 붙여넣기 등의 데이터 전송 작업을 제공 `COleDataObject` 정보를 포함 하는 서버 응용 프로그램에서 제공 되는 개체입니다. 재정의에 사용 되는 일반적으로 [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop)합니다.  
  
 자세한 내용은 참조 [OleCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms691211), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="createfromfile"></a>COleClientItem::CreateFromFile  
 파일에서 포함된 된 OLE 항목을 만들려면이 함수를 호출 합니다.  
  
```  
BOOL CreateFromFile(
    LPCTSTR lpszFileName,  
    REFCLSID clsid = CLSID_NULL,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFileName`  
 OLE 항목을 만들 수 있는 파일의 이름에 대 한 포인터입니다.  
  
 `clsid`  
 나중에 사용하기 위해 예약되어 있습니다.  
  
 *렌더링*  
 서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값에 대 한 참조 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `cfFormat`  
 OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.  
  
 `lpFormatEtc`  
 에 대 한 포인터는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조를 사용 하는 경우 *렌더링* 는 **OLERENDER_FORMAT** 또는 **OLERENDER_DRAW**합니다. 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에이 매개 변수 값을 제공 `cfFormat`합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 호출 하는 프레임 워크 [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem) 파일에서 만들기를 선택한 경우 사용자 개체 삽입 대화 상자에서 확인을 선택 하는 경우.  
  
 자세한 내용은 참조 [OleCreateFromFile](http://msdn.microsoft.com/library/windows/desktop/ms690116), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="createlinkfromclipboard"></a>COleClientItem::CreateLinkFromClipboard  
 클립보드의 내용에서 연결된 된 항목을 만들려면이 함수를 호출 합니다.  
  
```  
BOOL CreateLinkFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *렌더링*  
 서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값에 대 한 참조 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `cfFormat`  
 OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.  
  
 `lpFormatEtc`  
 에 대 한 포인터는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조를 사용 하는 경우 *렌더링* 는 **OLERENDER_FORMAT** 또는 **OLERENDER_DRAW**합니다. 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에이 매개 변수 값을 제공 `cfFormat`합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 일반적으로 편집 메뉴에서 연결 하 여 붙여넣기 명령에 대 한 메시지 처리기에서이 함수를 호출 합니다. (연결 하 여 붙여넣기 명령이의 기본 구현에서 사용 되는지 [COleDocument](../../mfc/reference/coledocument-class.md) 클립보드에 연결 될 수 있는 OLE 항목을 포함 하는 경우.)  
  
 자세한 내용은 참조 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="createlinkfromdata"></a>COleClientItem::CreateLinkFromData  
 연결된 된 항목을 만들려면이 함수를 호출 하는 `COleDataObject` 개체입니다.  
  
```  
BOOL CreateLinkFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDataObject`  
 에 대 한 포인터는 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE 항목 만들 개체입니다.  
  
 *렌더링*  
 서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값에 대 한 참조 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `cfFormat`  
 OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.  
  
 `lpFormatEtc`  
 에 대 한 포인터는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조를 사용 하는 경우 *렌더링* 는 **OLERENDER_FORMAT** 또는 **OLERENDER_DRAW**합니다. 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에이 매개 변수 값을 제공 `cfFormat`합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 사용자 링크를 만들 수 있음을 나타낼 때이 놓기 작업 중 호출 합니다. 편집 붙여넣기 명령을 처리 하도록 데도 수 있습니다. 프레임 워크에 의해 호출 될 `COleClientItem::CreateLinkFromClipboard` 및 [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) 링크 옵션을 선택한 경우.  
  
 자세한 내용은 참조 [OleCreateLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms680731), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="createlinkfromfile"></a>COleClientItem::CreateLinkFromFile  
 파일에서 연결된 된 OLE 항목을 만들려면이 함수를 호출 합니다.  
  
```  
BOOL CreateLinkFromFile(
    LPCTSTR lpszFileName,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFileName`  
 OLE 항목을 만들 수 있는 파일의 이름에 대 한 포인터입니다.  
  
 *렌더링*  
 서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값에 대 한 참조 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `cfFormat`  
 OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.  
  
 `lpFormatEtc`  
 에 대 한 포인터는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조를 사용 하는 경우 *렌더링* 는 **OLERENDER_FORMAT** 또는 **OLERENDER_DRAW**합니다. 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에이 매개 변수 값을 제공 `cfFormat`합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 사용자 파일에서 만들기를 선택 하 고 링크 확인란이 선택 되어 개체 삽입 대화 상자에서 확인을 선택 하는 경우이 함수를 호출 합니다. 호출 되어 [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem)합니다.  
  
 자세한 내용은 참조 [OleCreateLinkToFile](http://msdn.microsoft.com/library/windows/desktop/ms678434), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="createnewitem"></a>COleClientItem::CreateNewItem  
 포함된 된 항목을 만들려면이 함수를 호출 합니다. 이 함수는 OLE 항목을 만들 수 있도록 하는 서버 응용 프로그램을 시작 합니다.  
  
```  
BOOL CreateNewItem(
    REFCLSID clsid,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `clsid`  
 고유 하 게 만들 OLE 항목의 형식을 식별 하는 ID입니다.  
  
 *렌더링*  
 서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값에 대 한 참조 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `cfFormat`  
 OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.  
  
 `lpFormatEtc`  
 에 대 한 포인터는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조를 사용 하는 경우 *렌더링* 는 **OLERENDER_FORMAT** 또는 **OLERENDER_DRAW**합니다. 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에이 매개 변수 값을 제공 `cfFormat`합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 새로 만들기 단추를 선택 하는 경우 사용자 개체 삽입 대화 상자에서 확인을 선택 하는 경우이 함수를 호출 하는 프레임 워크입니다.  
  
 자세한 내용은 참조 [OleCreate](http://msdn.microsoft.com/library/windows/desktop/ms678409), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="createstaticfromclipboard"></a>COleClientItem::CreateStaticFromClipboard  
 항목을 만드는 정적 클립보드의 내용에서이 함수를 호출 합니다.  
  
```  
BOOL CreateStaticFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *렌더링*  
 서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값에 대 한 참조 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `cfFormat`  
 OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.  
  
 `lpFormatEtc`  
 에 대 한 포인터는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조를 사용 하는 경우 *렌더링* 는 **OLERENDER_FORMAT** 또는 **OLERENDER_DRAW**합니다. 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에이 매개 변수 값을 제공 `cfFormat`합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 정적 항목을 포함 하지 네이티브 데이터; 프레젠테이션 데이터 결과적으로 편집할 수 없습니다. 하면 일반적으로이 함수를 호출 하는 경우는 [CreateFromClipboard](#createfromclipboard) 멤버 함수가 실패 합니다.  
  
 자세한 내용은 참조 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="createstaticfromdata"></a>COleClientItem::CreateStaticFromData  
 정적 항목을 만들려면이 함수를 호출 하는 `COleDataObject` 개체입니다.  
  
```  
BOOL CreateStaticFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDataObject`  
 에 대 한 포인터는 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE 항목 만들 개체입니다.  
  
 *렌더링*  
 서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값에 대 한 참조 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `cfFormat`  
 OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.  
  
 `lpFormatEtc`  
 에 대 한 포인터는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조를 사용 하는 경우 *렌더링* 는 **OLERENDER_FORMAT** 또는 **OLERENDER_DRAW**합니다. 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에이 매개 변수 값을 제공 `cfFormat`합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 **FORMATETC** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 정적 항목을 포함 하지 네이티브 데이터; 프레젠테이션 데이터 따라서 편집할 수 있습니다. 이것은 기본적으로 동일 [CreateStaticFromClipboard](#createstaticfromclipboard) 는 임의의에서 정적 항목을 만들 수 있습니다 한다는 점을 제외 하면 `COleDataObject`클립보드에서 뿐만 아니라, 합니다.  
  
 에 사용 된 [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) 정적을 선택 하면 됩니다.  
  
 자세한 내용은 참조 [OleCreateStaticFromData](http://msdn.microsoft.com/library/windows/desktop/ms687290), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="deactivate"></a>COleClientItem::Deactivate  
 OLE 항목을 비활성화 하 고 모든 관련된 리소스를 해제 하려면이 함수를 호출 합니다.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>주의  
 일반적으로 항목의 범위 외부의 클라이언트 영역에서 마우스를 클릭할 때 내부 활성 OLE 항목을 비활성화 합니다. OLE 항목을 비활성화 하면를 호출 하지 못하도록 하는 실행 취소 상태에 삭제 됩니다 참고는 [ReactivateAndUndo](#reactivateandundo) 멤버 함수입니다.  
  
 응용 프로그램 실행 취소를 지 원하는 경우 호출 하지 않으면 `Deactivate`; 대신, 호출 [DeactivateUI](#deactivateui)합니다.  
  
 자세한 내용은 참조 [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="deactivateui"></a>COleClientItem::DeactivateUI  
 사용자 위치에 활성화 된 항목을 비활성화 하는 경우이 함수를 호출 합니다.  
  
```  
void DeactivateUI();
```  
  
### <a name="remarks"></a>주의  
 이 함수는 컨테이너 응용 프로그램의 사용자 인터페이스를 모든 메뉴 및 내부 활성화에 대해 생성 된 다른 컨트롤 숨기기, 원래 상태로 복원 합니다.  
  
 이 함수는 항목에 대 한 실행 취소 상태 정보를 플러시하지 않습니다. 정보를 보관 되도록 [ReactivateAndUndo](#reactivateandundo) 수 나중에 사용할 서버 응용 프로그램의 실행 취소 명령을 실행 하려면 경우 컨테이너의 실행 취소 명령을 항목을 비활성화 한 후에 즉시 선택 됩니다.  
  
 자세한 내용은 참조 [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="delete"></a>COleClientItem::Delete  
 OLE 항목이 컨테이너 문서에서 삭제 하려면이 함수를 호출 합니다.  
  
```  
void Delete(BOOL bAutoDelete = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bAutoDelete`  
 문서에서 제거할 항목을 지정 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수 호출의 [릴리스](#release) 차례로 항목을 영구적으로 제거 하는 OLE 항목에서 문서에 대 한 c + + 개체를 삭제 하는 멤버 함수입니다. OLE 항목이 포함 되어 있으면 해당 항목에 대 한 네이티브 데이터 삭제 됩니다. 가 실행 중인 서버를 항상 닫습니다. 따라서 항목 열기 링크 이면이 함수를 닫습니다.  
  
##  <a name="dodragdrop"></a>COleClientItem::DoDragDrop  
 호출 된 `DoDragDrop` 끌어서 놓기 작업을 수행 하는 멤버 함수입니다.  
  
```  
DROPEFFECT DoDragDrop(
    LPCRECT lpItemRect,  
    CPoint ptOffset,  
    BOOL bIncludeLink = FALSE,  
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,  
    LPCRECT lpRectStartDrag = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpItemRect`  
 클라이언트 좌표 (픽셀)의 화면에서 항목의 사각형입니다.  
  
 `ptOffset`  
 오프셋 `lpItemRect` 여기서 마우스 위치 당시 끕니다.  
  
 `bIncludeLink`  
 으로 설정 합니다. **TRUE** 링크 데이터를 클립보드에 복사 하는 경우. 로 설정 **FALSE** 서버 응용 프로그램 링크를 지원 하지 않는 경우.  
  
 `dwEffects`  
 끌기 소스는 끌기 작업의 허용 되는 효과 결정 합니다.  
  
 `lpRectStartDrag`  
 끌기 실제로 시작 위치를 정의 하는 사각형에 대 한 포인터입니다. 자세한 내용은 아래 설명 부분을 참조하십시오.  
  
### <a name="return-value"></a>반환 값  
 `DROPEFFECT` 값입니다. 있으면 `DROPEFFECT_MOVE`, 원래 데이터를 제거 해야 합니다.  
  
### <a name="remarks"></a>주의  
 끌어서 놓기 작업이 즉시 시작 되지 않습니다. 마우스 커서에 지정 된 사각형에서 벗어날 때까지 기다렸다가 `lpRectStartDrag` 또는 지정 된 기간 (밀리초) 지나야 합니다. 경우 `lpRectStartDrag` 는 **NULL**은&1; 픽셀의 사각형의 크기입니다.  
  
 지연 시간 레지스트리 키 설정으로 지정 됩니다. 호출 하 여 지연 시간을 변경할 수 있습니다 [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) 또는 [cwinapp:: Writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint)합니다. 지연 시간을 지정 하지 않으면 기본값은 200 밀리초 사용 됩니다. 끌기 지연 시간은 다음과 같이 저장 됩니다.  
  
-   Windows NT 끌어서 지연 시간 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay에 저장 됩니다.  
  
-   Windows 3.x 끌어서 지연 시간 WIN에 저장 됩니다. INI 파일 [Windows} 섹션.  
  
-   Windows 95/98 끌어서 지연 시간은 성공의 캐시 된 버전에 저장 됩니다. INI 합니다.  
  
 지연 정보 레지스트리에 저장 됩니다 드래그 하는 방법에 대 한 자세한 정보에 대 한 또는 합니다. INI 파일 참조 [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="doverb"></a>COleClientItem::DoVerb  
 호출 `DoVerb` 지정된 된 동사를 실행 합니다.  
  
```  
virtual BOOL DoVerb(
    LONG nVerb,  
    CView* pView,
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `nVerb`  
 실행 하는 동사를 지정 합니다. 다음 중 하나를 포함할 수 있습니다.  
  
|값|의미|기호|  
|-----------|-------------|------------|  
|– 0|기본 동사|`OLEIVERB_PRIMARY`|  
|– 1|보조 동사|(None)|  
|– 1|편집을 위해 표시 항목|`OLEIVERB_SHOW`|  
|– 2|별도 창에서 항목 편집|`OLEIVERB_OPEN`|  
|– 3|항목 숨기기|`OLEIVERB_HIDE`|  
  
 일반적으로-1 값은 다른 동사에 대 한 별칭입니다. 열기 편집 지원 되지 않는 경우-2는 것과 동일한 효과가-1입니다. 추가 값에 대 한 참조 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `pView`  
 보기 창;에 대 한 포인터 이 위치에서 활성화에 대 한 서버에서 사용 됩니다. 이 매개 변수 여야 **NULL** 컨테이너 응용 프로그램에서 내부 활성화를 허용 하지 않으면.  
  
 `lpMsg`  
 항목을 활성화할 수를 발생 시킨 메시지에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 동사; 성공적으로 실행 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수 호출의 [활성화](#activate) 동사를 실행 하는 멤버 함수입니다. 또한 예외를 포착 하 고 throw 되는 경우 사용자에 게 메시지 상자를 표시 합니다.  
  
 기본 동사는 편집 및&0;에 지정 된 경우는 `nVerb` OLE 항목을 편집할 수 있도록 매개 변수를 서버 응용 프로그램이 시작 됩니다. 컨테이너 응용 프로그램에서 내부 활성화를 지 원하는 경우 편집 가능 위치에 있습니다. 컨테이너 내부 활성화 (또는 Open 동사를 지정 하는 경우)을 지원 하지 않으면 서버가 별도 창에서 시작 되 고 편집 할 수 있습니다. 일반적으로 컨테이너 응용 프로그램의 사용자 두 번 클릭 하면 OLE 항목을 기본 동사에 대 한 값은 `nVerb` 매개 변수는 사용자가 수행할 수 있는 작업을 결정 합니다. 그러나 서버에서 하나의 작업을 지 원하는 경우 시간이에 지정 된 값에 관계 없이 해당 동작을는 `nVerb` 매개 변수입니다.  
  
##  <a name="draw"></a>COleClientItem::Draw  
 지정 된 장치 컨텍스트를 사용 하 여 지정된 된 경계 사각형에 OLE 항목을 그리는 데이 함수를 호출 합니다.  
  
```  
BOOL Draw(
    CDC* pDC,  
    LPCRECT lpBounds,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 에 대 한 포인터는 [CDC](../../mfc/reference/cdc-class.md) OLE 항목을 그리는 데 사용 되는 개체입니다.  
  
 `lpBounds`  
 에 대 한 포인터는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 `RECT` 를 (논리 단위를 장치 컨텍스트에 따라 결정)에 OLE 항목을 그릴 경계 사각형을 정의 하는 구조입니다.  
  
 `nDrawAspect`  
 OLE의 모양을 항목, 즉, 표시 방법을 지정 합니다. 경우 `nDrawAspect` -1을 사용 하 여 설정 마지막 측면은 [SetDrawAspect](#setdrawaspect) 사용 됩니다. 이 플래그에 대 한 가능한 값에 대 한 자세한 내용은 참조 [SetDrawAspect](#setdrawaspect)합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 함수에 의해 만들어진 OLE 항목의 메타 파일 표시를 사용할 수는 [OnDraw](../../mfc/reference/coleserveritem-class.md#ondraw) 의 멤버 함수 `COleServerItem`합니다.  
  
 일반적으로 사용 **그리기** 화면 표시로 화면 장치 컨텍스트를 전달 `pDC`합니다. 이 경우 처음 두 매개 변수를 지정 해야 합니다.  
  
 `lpBounds` 매개 변수는 대상 장치 컨텍스트 (기준으로 현재 매핑 모드)에서 사각형을 식별 합니다. 렌더링 그림 확장 될 수 및 표시 된 보기와 최종 인쇄 이미지 크기를 조정 하는 보기를 적용 하려면 컨테이너 응용 프로그램에서 사용할 수 있습니다.  
  
 자세한 내용은 참조 [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getactiveview"></a>COleClientItem::GetActiveView  
 항목은 활성화 될 보기를 반환 합니다.  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>반환 값  
 보기;에 대 한 포인터 그렇지 않으면 **NULL** 항목이 활성화 될 경우.  
  
##  <a name="getcachedextent"></a>COleClientItem::GetCachedExtent  
 OLE 항목의 크기를 검색 하려면이 함수를 호출 합니다.  
  
```  
BOOL GetCachedExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpSize`  
 에 대 한 포인터는 **크기** 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 크기 정보를 받게 될 개체입니다.  
  
 `nDrawAspect`  
 검색할 경계가 OLE 항목의 모양을 지정 합니다. 가능한 값에 대 한 참조 [SetDrawAspect](#setdrawaspect)합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 OLE 항목은 비어 있는 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 동일한 정보를 제공 [GetExtent](#getextent)합니다. 호출할 수 있습니다 `GetCachedExtent` 범위에 정보를 가져올 처리 하는 동안 다른 OLE 처리기와 같은 [OnChange](#onchange)합니다. 차원은 `MM_HIMETRIC` 단위입니다.  
  
 이것이 가능 하기 때문에 `GetCachedExtent` 사용 하 여는 [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318) 인터페이스를 사용 하지 않고는 [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709) 인터페이스를이 항목의 범위를 가져옵니다. **IViewObject2** COM 개체에 대 한 이전 호출에 사용 되는 범위 정보를 캐시 [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)합니다.  
  
 자세한 내용은 참조 [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getclassid"></a>COleClientItem::GetClassID  
 가 가리키는 메모리에 있는 항목의 클래스 ID를 반환 합니다. `pClassID`합니다.  
  
```  
void GetClassID(CLSID* pClassID) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pClassID`  
 형식의 식별자에 대 한 포인터 [CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) 클래스 ID를 검색 에 대 한 내용은 **CLSID**, 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 클래스 ID는은 항목을 편집 하는 응용 프로그램을 고유 하 게 식별 하는 128 비트 숫자입니다.  
  
 자세한 내용은 참조 [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getclipboarddata"></a>COleClientItem::GetClipboardData  
 가져오려면이 함수를 호출 하는 `COleDataSource` 개체를 호출 하 여 클립보드에 배치 하는 모든 데이터를 포함 하는 [CopyToClipboard](#copytoclipboard) 멤버 함수입니다.  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDataSource`  
 에 대 한 포인터는 [COleDataSource](../../mfc/reference/coledatasource-class.md) OLE 항목에 포함 된 데이터를 받게 될 개체입니다.  
  
 `bIncludeLink`  
 **True 이면** 포함 하 고, 그렇지 않으면 데이터 연결 해야 하면 **FALSE**합니다.  
  
 `lpOffset`  
 마우스 커서를 픽셀 단위로 개체의 원점부터의 오프셋입니다.  
  
 `lpSize`  
 크기 (픽셀)에서 개체입니다.  
  
### <a name="remarks"></a>주의  
 `GetClipboardData`기본 구현은 라고 [OnGetClipboardData](#ongetclipboarddata)합니다. 재정의 `OnGetClipboardData` 에서 제공 하는 것 외에도 데이터 형식을 제공 하려는 경우에 `CopyToClipboard`합니다. 배치에서 이러한 형식이 `COleDataSource` 하기 전이나 호출한 후 개체 `CopyToClipboard`, 다음 전달 하는 `COleDataSource` 개체를 [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard) 함수입니다. 예를 들어 클립보드에 함께 해당 컨테이너 문서의 OLE 항목의 위치를 하려는 경우 해당 정보를 전달 하기 위한 고유한 형식을 정의 하는에 저장 된 `COleDataSource` 호출 하기 전에 `CopyToClipboard`합니다.  
  
##  <a name="getdocument"></a>COleClientItem::GetDocument  
 OLE 항목을 포함 하는 문서에 대 한 포인터를 가져오려면이 함수를 호출 합니다.  
  
```  
COleDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>반환 값  
 OLE 항목을 포함 하는 문서에 대 한 포인터입니다. **NULL** 항목 문서의 일부가 아닌 경우.  
  
### <a name="remarks"></a>주의  
 이 포인터에 액세스할 수 있습니다.는 `COleDocument` 에 인수로 전달 되는 개체는 `COleClientItem` 생성자입니다.  
  
##  <a name="getdrawaspect"></a>COleClientItem::GetDrawAspect  
 호출의 `GetDrawAspect` 멤버 함수를 현재 "모양" 또는 항목의 보기를 확인 합니다.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 값은 `DVASPECT` 열거형과 해당 값에 대 한 참조에 나열 된 [SetDrawAspect](#setdrawaspect)합니다.  
  
### <a name="remarks"></a>주의  
 모양 항목 렌더링 하는 하는 방법을 지정 합니다.  
  
##  <a name="getextent"></a>COleClientItem::GetExtent  
 OLE 항목의 크기를 검색 하려면이 함수를 호출 합니다.  
  
```  
BOOL GetExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)- 1);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpSize`  
 에 대 한 포인터는 **크기** 구조 또는 `CSize` 크기 정보를 받게 될 개체입니다.  
  
 `nDrawAspect`  
 검색할 경계가 OLE 항목의 모양을 지정 합니다. 가능한 값에 대 한 참조 [SetDrawAspect](#setdrawaspect)합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 OLE 항목은 비어 있는 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 Microsoft Foundation Class 라이브러리를 사용 하 여 서버 응용 프로그램이 작성 하는 경우에이 함수로는 [합니다](../../mfc/reference/coleserveritem-class.md#ongetextent) 멤버 함수는 해당 `COleServerItem` 개체를 호출할 수 있습니다. 마지막으로 설정 하는 크기에서 검색 된 크기가 다를 수 있습니다는 [SetExtent](#setextent) 멤버 함수,으로 지정 된 크기 `SetExtent` 한 제안으로 처리 됩니다. 차원은 `MM_HIMETRIC` 단위입니다.  
  
> [!NOTE]
>  호출 하지 마십시오 `GetExtent` OLE 핸들러의 처리 하는 동안 같은 [OnChange](#onchange)합니다. 호출 [GetCachedExtent](#getcachedextent) 대신 합니다.  
  
 자세한 내용은 참조 [IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="geticonfromregistry"></a>COleClientItem::GetIconFromRegistry  
 CLSID에 특정 서버에 연결 된 아이콘 리소스에 대 한 핸들을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
HICON GetIconFromRegistry() const;  
  
static HICON GetIconFromRegistry(CLSID& clsid);
```  
  
### <a name="parameters"></a>매개 변수  
 `clsid`  
 아이콘와 연결 된 서버에 대 한 CLSID에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 아이콘 리소스에 대 한 유효한 핸들 또는 **NULL** 서버의 아이콘 또는 기본 아이콘을 찾을 수 없는 경우.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 서버를 시작 되거나 서버에서 이미 실행 중인 경우에 아이콘을 동적으로 가져올 되지 않습니다. 대신이 멤버 함수 서버의 실행 가능 이미지 열고으로 등록 된 서버와 관련 된 정적 아이콘을 검색 합니다.  
  
##  <a name="geticonicmetafile"></a>COleClientItem::GetIconicMetafile  
 항목의 아이콘을 그리는 데 사용 하 여 메타 파일을 검색 합니다.  
  
```  
HGLOBAL GetIconicMetafile();
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 메타 파일에 대 한 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 현재 아이콘이 없는 경우에 기본 아이콘이 반환 됩니다. 이 MFC/OLE 대화 상자에서 자동으로 호출 되 고는 직접 호출 하지 않습니다.  
  
 이 함수 호출 [SetIconicMetafile](#seticonicmetafile) 나중에 사용할 메타 파일을 캐시 하도록 합니다.  
  
##  <a name="getinplacewindow"></a>COleClientItem::GetInPlaceWindow  
 호출 된 `GetInPlaceWindow` 포인터를 얻으려면 항목 연결이 열린 창에 내부 편집에 대 한 멤버 함수입니다.  
  
```  
CWnd* GetInPlaceWindow();
```  
  
### <a name="return-value"></a>반환 값  
 항목의 내부 편집 창의;에 대 한 포인터 **NULL** 항목 아니기 때문에 또는 해당 서버를 사용할 수 없는 경우.  
  
### <a name="remarks"></a>주의  
 이 함수에 내부 활성화 되는 항목에 대해서만 호출 되어야 합니다.  
  
##  <a name="getitemstate"></a>COleClientItem::GetItemState  
 OLE 항목의 현재 상태를 가져오려면이 함수를 호출 합니다.  
  
```  
UINT GetItemState() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **COleClientItem::ItemState** 열거형 값 중 하나일 수 있습니다: `emptyState`, **loadedState**, `openState`, `activeState`, `activeUIState`합니다. 이러한 상태에 대 한 내용은 문서를 참조 하십시오. [컨테이너: 클라이언트 항목 상태](../../mfc/containers-client-item-states.md)합니다.  
  
### <a name="remarks"></a>주의  
 OLE 항목의 상태가 변경 될 때 알림을 받으려면를 사용 하 여는 [OnChange](#onchange) 멤버 함수입니다.  
  
 자세한 내용은 문서를 참조 하십시오. [컨테이너: 클라이언트 항목 상태](../../mfc/containers-client-item-states.md)합니다.  
  
##  <a name="getlaststatus"></a>COleClientItem::GetLastStatus  
 마지막 OLE 작업의 상태 코드를 반환합니다.  
  
```  
SCODE GetLastStatus() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `SCODE` 값입니다.  
  
### <a name="remarks"></a>주의  
 멤버에 대 한 반환 하는 함수는 **BOOL** 값 **FALSE**, 다른 멤버 반환 하는 함수 또는 **NULL**, `GetLastStatus` 보다 자세한 오류 정보를 반환 합니다. 대부분의 OLE 멤버 함수 보다 심각한 오류에 대 한 예외를 throw 하 유의 합니다. 해석에 특정 정보는 `SCODE` 마지막으로 반환 되는 기본 OLE 호출에 따라 달라 집니다는 `SCODE` 값입니다.  
  
 대 한 자세한 내용은 `SCODE`, 참조 [COM 오류 코드 구조](http://msdn.microsoft.com/library/windows/desktop/ms690088) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 설명서입니다.  
  
##  <a name="getlinkupdateoptions"></a>COleClientItem::GetLinkUpdateOptions  
 OLE 항목에 대 한 연결 업데이트 옵션의 현재 값을 가져오려면이 함수를 호출 합니다.  
  
```  
OLEUPDATE GetLinkUpdateOptions();
```  
  
### <a name="return-value"></a>반환 값  
 다음 값 중 하나입니다.  
  
- `OLEUPDATE_ALWAYS`가능 하면 연결된 된 항목을 업데이트 합니다. 이 옵션은 연결 대화 상자에서 자동 연결 업데이트 라디오 단추를 지원 합니다.  
  
- `OLEUPDATE_ONCALL`컨테이너 응용 프로그램의 요청에만 연결 된 항목을 업데이트 (때는 [UpdateLink](#updatelink) 멤버 함수를 호출). 이 옵션은 연결 대화 상자에서 수동 연결 업데이트 라디오 단추를 지원 합니다.  
  
### <a name="remarks"></a>주의  
 이 작업은 고급 작업입니다.  
  
 이 함수에서 자동으로 호출 되는 [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) 클래스입니다.  
  
 자세한 내용은 참조 [IOleLink::GetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680100) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="gettype"></a>COleClientItem::GetType  
 OLE 항목을 포함 또는 연결 하는 여부 또는 정적 확인 하려면이 함수를 호출 합니다.  
  
```  
OLE_OBJTYPE GetType() const;  
```  
  
### <a name="return-value"></a>반환 값  
 다음 값 중 하나를 사용 하는 부호 없는 정수:  
  
- `OT_LINK`OLE 항목에는 링크입니다.  
  
- `OT_EMBEDDED`OLE 항목이 포함 되어 있습니다.  
  
- `OT_STATIC`OLE 항목은 정적, 즉, 네이티브가 아닌 데이터 프레젠테이션 데이터만 포함 하 고 편집할 수 없습니다.  
  
##  <a name="getusertype"></a>COleClientItem::GetUserType  
 "Word 문서입니다."와 같은 OLE 항목의 형식을 설명 하는 사용자가 볼 수 문자열을 가져오려면이 함수를 호출 합니다.  
  
```  
void GetUserType(
    USERCLASSTYPE nUserClassType,  
    CString& rString);
```  
  
### <a name="parameters"></a>매개 변수  
 *nUserClassType*  
 OLE 항목의 형식을 설명 하는 문자열의 원하는 값을 나타내는 값입니다. 이 경우 다음 값 중 하나가 있을 수 있습니다.  
  
- `USERCLASSTYPE_FULL`사용자에 게 표시 되는 전체 형식 이름입니다.  
  
- `USERCLASSTYPE_SHORT`팝업 메뉴 및 연결 편집 대화 상자에서 사용 하기 위해 짧은 이름 (최대&15; 자).  
  
- `USERCLASSTYPE_APPNAME`서비스 클래스를 제공 하는 응용 프로그램의 이름입니다.  
  
 `rString`  
 에 대 한 참조는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) OLE 항목의 형식을 설명 하는 문자열 반환 되는 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 방식은 시스템 등록 데이터베이스에 있는 항목입니다.  
  
 전체 형식 이름이 요청 하지만 사용할 수 없는 경우 짧은 이름은 대신 사용 됩니다. OLE 항목의 형식에 대 한 항목이 등록 데이터베이스에서 찾을 수 없거나 OLE 항목의 형식에 등록 된 사용자 형식이 없습니다가 없을 경우 다음 사용자 유형을 현재에 저장 하는 경우 OLE 항목이 사용 됩니다. 해당 사용자 형식 이름의 빈 문자열인 경우 "알 수 없는 개체를" 사용 됩니다.  
  
 자세한 내용은 참조 [IOleObject::GetUserType](http://msdn.microsoft.com/library/windows/desktop/ms688643) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="isinplaceactive"></a>COleClientItem::IsInPlaceActive  
 OLE 항목에 내부 활성화 되었는지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>반환 값  
 OLE 항목에 내부 활성화; 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 항목 위치에서 편집 되는 여부에 따라 다른 논리를 실행 하려면 일반적 됩니다. 함수는 현재 항목 상태가 같을 인지 확인은 `activeState` 또는 `activeUIState`합니다.  
  
##  <a name="islinkuptodate"></a>COleClientItem::IsLinkUpToDate  
 OLE 항목은 최신이 함수를 호출 합니다.  
  
```  
BOOL IsLinkUpToDate() const;  
```  
  
### <a name="return-value"></a>반환 값  
 OLE 항목이 최신; 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 링크 된 항목을 원본 문서를 업데이트 한 경우 오래 유지 될 수 있습니다. 마찬가지로 내 링크를 포함 하는 포함 된 항목 만료 될 수 있습니다. 함수에는 OLE 항목에 대 한 재귀적 검사를 수행합니다. OLE 항목이 최신 인지 확인 하는 업데이트를 실제로 수행 보다 비용이 수 note 합니다.  
  
 이 의해 자동으로 호출 되는 [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) 구현 합니다.  
  
 자세한 내용은 참조 [IOleObject::IsUpToDate](http://msdn.microsoft.com/library/windows/desktop/ms686624) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="ismodified"></a>COleClientItem::IsModified  
 OLE 항목은 커밋되지 않은 데이터 (마지막으로 저장 된 이후 수정)이이 함수를 호출 합니다.  
  
```  
BOOL IsModified() const;  
```  
  
### <a name="return-value"></a>반환 값  
 OLE 항목이 더티; 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [IPersistStorage::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="isopen"></a>COleClientItem::IsOpen  
 OLE 항목이 열려 있는지 확인 하려면이 함수를 호출 합니다. 즉, 별도 창에서 실행 중인 서버 응용 프로그램의 인스턴스로 열립니다.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>반환 값  
 OLE 항목이 열려 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 해칭 패턴을 사용 하 여 개체를 그릴 시점을 결정 하는 데 사용 됩니다. 열려 있는 개체를 개체 위에 그려야 빗살 무늬가 있어야 합니다. 사용할 수는 [CRectTracker](../../mfc/reference/crecttracker-class.md) 이 작업을 수행 하는 개체입니다.  
  
##  <a name="isrunning"></a>COleClientItem::IsRunning  
 OLE 항목; 실행 여부를이 함수를 호출 합니다. 즉, 항목 인지 서버 응용 프로그램에서 실행 되 고 로드 합니다.  
  
```  
BOOL IsRunning() const;  
```  
  
### <a name="return-value"></a>반환 값  
 OLE 항목; 실행 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [OleIsRunning](http://msdn.microsoft.com/library/windows/desktop/ms688705) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="onactivate"></a>COleClientItem::OnActivate  
 항목을 방금 계신다면 제자리에서에 알리기 위해 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnActivate();
```  
  
### <a name="remarks"></a>주의  
 참고가이 함수를 해당 사용자 인터페이스 컨테이너 응용 프로그램에 설치 되어 있는지를 나타내는 것이 아니라 서버 실행을 나타내기 위해 호출 됩니다. 이때 개체는 활성 사용자 인터페이스가 없는 (않습니다 `activeUIState`). 해당 메뉴 또는 도구 모음에는 설치 되지 않았습니다. [OnActivateUI](#onactivateui) 이 경우 멤버 함수를 호출 합니다.  
  
 기본 구현 호출 하 여는 [OnChange](#onchange) 멤버 함수를 **OLE_CHANGEDSTATE** 매개 변수로 합니다. 항목에 내부 활성화 되 면 사용자 지정 처리를 수행 하려면이 함수를 재정의 합니다.  
  
##  <a name="onactivateui"></a>COleClientItem::OnActivateUI  
 프레임 워크 호출 `OnActivateUI` 개체가 활성 UI 상태에 입력 하는 경우.  
  
```  
virtual void OnActivateUI();
```  
  
### <a name="remarks"></a>주의  
 개체는 이제 해당 도구 모음 및 메뉴에 설치 됩니다.  
  
 기본 구현은 기억 서버의 `HWND` 나중을 위해 **GetServerWindow** 호출 합니다.  
  
##  <a name="onchange"></a>COleClientItem::OnChange  
 사용자 수정, 저장, 또는 OLE 항목을 닫습니다 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnChange(
    OLE_NOTIFICATION nCode,  
    DWORD dwParam);
```  
  
### <a name="parameters"></a>매개 변수  
 `nCode`  
 이 항목 변경 하는 이유는 서버. 다음 값 중 하나일 수 있습니다.  
  
- `OLE_CHANGED`OLE 항목의 모양 변경 되었습니다.  
  
- `OLE_SAVED`OLE 항목 저장 되었습니다.  
  
- `OLE_CLOSED`OLE 항목 사용 중지 되었습니다.  
  
- `OLE_CHANGED_STATE`OLE 항목은 다른 한 상태에서 변경 되었습니다.  
  
 `dwParam`  
 경우 `nCode` 는 `OLE_SAVED` 또는 `OLE_CLOSED`,이 매개 변수는 사용 되지 않습니다. 경우 `nCode` 는 `OLE_CHANGED`,이 매개 변수 변경 된 OLE 항목의 모양을 지정 합니다. 가능한 값에 대 한 참조는 `dwParam` 의 매개 변수 [COleClientItem::Draw](#draw)합니다. 경우 `nCode` 는 `OLE_CHANGED_STATE`,이 매개 변수는 한 **COleClientItem::ItemState** 값을 열거 하 고 입력 되는 상태를 설명 합니다. 다음 값 중 하나일 수 있습니다: `emptyState`, **loadedState**, `openState`, `activeState`, 또는 `activeUIState`합니다.  
  
### <a name="remarks"></a>주의  
 (에 대 한 응답에서이 함수가 호출 되어 서버 응용 프로그램은 Microsoft Foundation Class 라이브러리를 사용 하 여를 작성 한 경우는 `Notify` 의 멤버 함수 `COleServerDoc` 또는 `COleServerItem`.) 기본 구현 컨테이너 문서 표시 하는 경우 수정 된 것으로 `nCode` 는 `OLE_CHANGED` 또는 `OLE_SAVED`합니다.  
  
 에 대 한 `OLE_CHANGED_STATE`, 현재 상태에서 반환 된 [GetItemState](#getitemstate) 이 상태 변경 하기 전에 현재 상태를 의미 하는 이전 상태를 계속 됩니다.  
  
 OLE 항목의 상태 변화에 대응 하려면이 함수를 재정의 합니다. 일반적으로 항목이 표시 되는 영역을 무효화 하 여 항목의 모양을 업데이트 합니다. 재정의 시 맨 앞에 기본 클래스 구현을 호출 합니다.  
  
##  <a name="onchangeitemposition"></a>COleClientItem::OnChangeItemPosition  
 OLE 항목의 범위는 현재 위치에서 활성화 하는 동안 변경 된 컨테이너에 알리는 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnChangeItemPosition(const CRect& rectPos);
```  
  
### <a name="parameters"></a>매개 변수  
 *rectPos*  
 컨테이너 응용 프로그램의 클라이언트 영역을 기준으로 항목의 위치를 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 항목의 위치가 성공적으로 변경 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 OLE 항목 및 호출 표시 되는 새 사각형을 결정 하는 기본 구현은 [SetItemRects](#setitemrects) 새 값으로. 기본 구현 항목에 대해 표시 되는 사각형을 계산 하 고 서버에 해당 정보를 전달 합니다.  
  
 크기 조정/이동 작업에 특별 한 규칙을 적용 하려면이 함수를 재정의 합니다. 서버에서 호출 되기 때문에이 호출 결과 응용 프로그램은 MFC를 작성 하는 경우 [COleServerDoc::RequestPositionChange](../../mfc/reference/coleserverdoc-class.md#requestpositionchange)합니다.  
  
##  <a name="ondeactivate"></a>COleClientItem::OnDeactivate  
 OLE 항목은 내부 활성 상태에서 전환 될 때 프레임 워크에서 호출 ( `activeState`) 로드 된 상태로, 내부 활성화 된 후에 비활성화 된 것을 의미 합니다.  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>주의  
 Note이 함수가 호출 되어 있음을 나타냅니다 OLE 항목은, 하지 컨테이너 응용 프로그램에서 제거 된 사용자 인터페이스 합니다. 이 경우는 [OnDeactivateUI](#ondeactivateui) 멤버 함수를 호출 합니다.  
  
 기본 구현 호출 하 여는 [OnChange](#onchange) 멤버 함수를 **OLE_CHANGEDSTATE** 매개 변수로 합니다. 내부 활성 항목 비활성화 되 면 사용자 지정 처리를 수행 하려면이 함수를 재정의 합니다. 예를 들어 컨테이너 응용 프로그램의 실행 취소 명령을 지 원하는 경우 재정의할 수 있습니다 실행 취소 상태를 삭제 하려면이 함수를 나타내는 항목이 비활성화 되 면 OLE 항목에 수행 된 마지막 작업 수 없는 실행 취소할 수 있습니다.  
  
##  <a name="ondeactivateandundo"></a>COleClientItem::OnDeactivateAndUndo  
 사용자 위치에 OLE 항목을 활성화 한 후 실행 취소 명령을 호출 하는 경우 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnDeactivateAndUndo();
```  
  
### <a name="remarks"></a>주의  
 기본 구현 호출 하 여 [DeactivateUI](#deactivateui) 서버의 사용자 인터페이스를 비활성화 합니다. 컨테이너 응용 프로그램의 실행 취소 명령을 구현 하는 경우이 함수를 재정의 합니다. 재정의 시, 기본 클래스 버전의 함수를 호출 하 고 응용 프로그램에서 실행 되는 마지막 명령 실행 취소 합니다.  
  
 자세한 내용은 참조 [IOleInPlaceSite::DeactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms683743) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="ondeactivateui"></a>COleClientItem::OnDeactivateUI  
 사용자 위치에 활성화 된 항목을 비활성화 하면 호출 됩니다.  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>매개 변수  
 `bUndoable`  
 편집 변경 되는지 실행 취소가 가능 여부를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 컨테이너 응용 프로그램의 사용자 인터페이스를 모든 메뉴 및 내부 활성화에 대해 생성 된 다른 컨트롤 숨기기, 원래 상태로 복원 합니다.  
  
 경우 `bUndoable` 는 **FALSE**, 컨테이너는 실행 취소 명령을 사용 하지 않도록, 서버에서 수행 된 마지막 작업을 나타내기 때문에 컨테이너의 실행 취소 상태를 실제로 삭제은 취소할 수 없습니다.  
  
##  <a name="ondiscardundostate"></a>COleClientItem::OnDiscardUndoState  
 OLE 항목을 편집 하는 동안 실행 취소 상태를 삭제 하는 동작을 수행 하는 경우에 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnDiscardUndoState();
```  
  
### <a name="remarks"></a>주의  
 기본 구현은 아무 작업도 수행하지 않습니다. 컨테이너 응용 프로그램의 실행 취소 명령을 구현 하는 경우이 함수를 재정의 합니다. 재정의 시, 컨테이너 응용 프로그램의 실행 취소 상태를 삭제 합니다.  
  
 서버는 Microsoft Foundation 클래스 라이브러리 사용 하는 서버를 작성 하는 경우이 호출 될이 함수를 호출 하 여 발생할 수 있습니다 [COleServerDoc::DiscardUndoState](../../mfc/reference/coleserverdoc-class.md#discardundostate)합니다.  
  
 자세한 내용은 참조 [IOleInPlaceSite::DiscardUndoState](http://msdn.microsoft.com/library/windows/desktop/ms688642) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="ongetclipboarddata"></a>COleClientItem::OnGetClipboardData  
 가져오려는 프레임 워크에서 호출을 `COleDataSource` 개체 중 하나를 호출 하 여 클립보드에 배치 하는 모든 데이터를 포함 하는 [CopyToClipboard](#copytoclipboard) 또는 [DoDragDrop](#dodragdrop) 멤버 함수입니다.  
  
```  
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,  
    LPPOINT lpOffset,  
    LPSIZE lpSize);
```  
  
### <a name="parameters"></a>매개 변수  
 `bIncludeLink`  
 으로 설정 합니다. **TRUE** 링크 데이터를 클립보드에 복사 하는 경우. 으로 설정 합니다. **FALSE** 서버 응용 프로그램 링크를 지원 하지 않는 경우.  
  
 `lpOffset`  
 마우스 커서의 오프셋 (픽셀)에서 개체의 원점부터 포인터입니다.  
  
 `lpSize`  
 픽셀 단위로 개체의 크기에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [COleDataSource](../../mfc/reference/coledatasource-class.md) 클립보드 데이터를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현에서는 호출 [GetClipboardData](#getclipboarddata)합니다.  
  
##  <a name="ongetcliprect"></a>COleClientItem::OnGetClipRect  
 프레임 워크 호출의 `OnGetClipRect` 위치에서 편집 중인 항목의 클리핑 사각형 좌표를 가져오려면 멤버 함수입니다.  
  
```  
virtual void OnGetClipRect(CRect& rClipRect);
```  
  
### <a name="parameters"></a>매개 변수  
 *rClipRect*  
 클래스의 개체에 대 한 포인터 [CRect](../../atl-mfc-shared/reference/crect-class.md) 하는 항목의 클리핑 사각형 좌표를 저장 합니다.  
  
### <a name="remarks"></a>주의  
 좌표는 컨테이너 응용 프로그램 창의 클라이언트 영역을 기준으로 합니다.  
  
 기본 구현은 단순히 있는 항목을 내부에서 활성 상태 보기의 클라이언트 사각형을 반환 합니다.  
  
##  <a name="ongetitemposition"></a>COleClientItem::OnGetItemPosition  
 프레임 워크 호출의 `OnGetItemPosition` 위치에서 편집 중인 항목의 좌표를 가져오려면 멤버 함수입니다.  
  
```  
virtual void OnGetItemPosition(CRect& rPosition);
```  
  
### <a name="parameters"></a>매개 변수  
 `rPosition`  
 에 대 한 참조는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 항목의 위치 좌표를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 좌표는 컨테이너 응용 프로그램 창의 클라이언트 영역을 기준으로 합니다.  
  
 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 위치에서 편집을 지 원하는 응용 프로그램에는 구현이 필요 합니다.  
  
##  <a name="ongetwindowcontext"></a>COleClientItem::OnGetWindowContext  
 항목 위치에서 활성화 될 때 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnGetWindowContext(
    CFrameWnd** ppMainFrame,  
    CFrameWnd** ppDocFrame,  
    LPOLEINPLACEFRAMEINFO lpFrameInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppMainFrame`  
 주 프레임 창에 대 한 포인터에 대 한 포인터입니다.  
  
 `ppDocFrame`  
 문서 프레임 창에 대 한 포인터에 대 한 포인터입니다.  
  
 `lpFrameInfo`  
 에 대 한 포인터는 [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) 구조를 프레임 창 정보를 받게 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 OLE 항목의 부모 창에 대 한 정보를 검색에 사용 됩니다.  
  
 컨테이너 MDI 응용 프로그램의 경우 기본 구현에 대 한 포인터를 반환 하는 [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md) 개체 `ppMainFrame` 활성에 대 한 포인터 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) 개체 `ppDocFrame`합니다. 컨테이너 SDI 응용 프로그램의 경우 기본 구현에 대 한 포인터를 반환 하는 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 개체 `ppMainFrame` 반환 **NULL** 에서 `ppDocFrame`합니다. 기본 구현에서는 또한 멤버에서 채웁니다 `lpFrameInfo`합니다.  
  
 기본 구현에서는 응용 프로그램에 적합 하지 않는 경우에이 함수를 재정의 합니다. 예를 들어, 응용 프로그램에 다른 SDI 또는 MDI 사용자 인터페이스 패러다임입니다. 고급 재정의할 수 있습니다.  
  
 자세한 내용은 참조 [IOleInPlaceSite::GetWindowContext](http://msdn.microsoft.com/library/windows/desktop/ms694366) 및 [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="oninsertmenus"></a>COleClientItem::OnInsertMenus  
 컨테이너 응용 프로그램의 메뉴를 빈 메뉴에 삽입 하는 내부 활성화 동안 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnInsertMenus(
    CMenu* pMenuShared,  
    LPOLEMENUGROUPWIDTHS lpMenuWidths);
```  
  
### <a name="parameters"></a>매개 변수  
 `pMenuShared`  
 빈 메뉴를 가리킵니다.  
  
 `lpMenuWidths`  
 6의 배열을 가리킵니다 **긴** 메뉴 그룹의 각 메뉴의 수를 나타내는 값: 파일, 편집, 컨테이너, 개체, 창 도움말입니다. 파일, 컨테이너 및 창 메뉴 그룹의 경우 0, 2 및 4이 배열의 요소에 해당 하는 컨테이너 응용 프로그램.  
  
### <a name="remarks"></a>주의  
 그런 다음이 메뉴는 자체 메뉴, 복합 메뉴 만들기를 삽입 하는 서버에 전달 됩니다. 이 함수는 여러 복합 메뉴를 만들려는 반복적으로 호출할 수 있습니다.  
  
 기본 구현은 삽입 `pMenuShared` 전체 컨테이너 메뉴; 즉, 파일, 컨테이너 및 창 메뉴 그룹입니다. [CDocTemplate::SetContainerInfo](../../mfc/reference/cdoctemplate-class.md#setcontainerinfo) 이 메뉴 리소스를 설정 하는 데 사용 됩니다. 또한 기본 구현에서는 0, 2 및 4에서 요소에 적절 한 값을 지정 `lpMenuWidths`메뉴 리소스에 따라 합니다. 기본 구현에서는 응용 프로그램에 적합 하지 않은 경우이 함수를 재정의 합니다. 예를 들어, 응용 프로그램 문서 형식을 사용 리소스를 연결 하기 위한 문서 서식 파일을 사용 하지 않는 경우. 또한 재정의 해야이 함수를 재정의 하는 경우 [OnSetMenu](#onsetmenu) 및 [OnRemoveMenus](#onremovemenus)합니다. 고급 재정의할 수 있습니다.  
  
 자세한 내용은 참조 [IOleInPlaceFrame::InsertMenus](http://msdn.microsoft.com/library/windows/desktop/ms683987) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="onremovemenus"></a>COleClientItem::OnRemoveMenus  
 내부 활성화 종료 될 때 지정 된 복합 메뉴에서 컨테이너의 메뉴를 제거 하려면 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnRemoveMenus(CMenu* pMenuShared);
```  
  
### <a name="parameters"></a>매개 변수  
 `pMenuShared`  
 호출 하 여 생성 된 복합 메뉴 가리키는 [OnInsertMenus](#oninsertmenus) 멤버 함수입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현에서 제거 `pMenuShared` 있는 전체 컨테이너 메뉴, 파일, 컨테이너 및 창 메뉴 그룹입니다. 기본 구현에서는 응용 프로그램에 적합 하지 않은 경우이 함수를 재정의 합니다. 예를 들어, 응용 프로그램 문서 형식을 사용 리소스를 연결 하기 위한 문서 서식 파일을 사용 하지 않는 경우. 이 함수를 재정의 하는 경우 아마도 재정의 해야 [OnInsertMenus](#oninsertmenus) 및 [OnSetMenu](#onsetmenu) 도 합니다. 고급 재정의할 수 있습니다.  
  
 에 하위 메뉴가 `pMenuShared` 서버가 반복적으로 호출 하는 경우 둘 이상의 복합 메뉴에서 공유할 수 있습니다 `OnInsertMenus`합니다. 재정의에서는 모든 하위 메뉴를 삭제 하면 안 되는 따라서 `OnRemoveMenus`;만 분리 해야 합니다.  
  
 자세한 내용은 참조 [IOleInPlaceFrame::RemoveMenus](http://msdn.microsoft.com/library/windows/desktop/ms688685) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="onscrollby"></a>COleClientItem::OnScrollBy  
 서버에서 요청에 따라에서 OLE 항목 스크롤해야 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual BOOL OnScrollBy(CSize sizeExtent);
```  
  
### <a name="parameters"></a>매개 변수  
 *sizeExtent*  
 X와 y 방향 스크롤할 픽셀 거리를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 항목을 스크롤한; 0이 아닌 항목을 스크롤할 수 있는 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 예를 들어 부분적으로 표시 된 OLE 항목 바로 편집 기능을 수행 하는 동안 표시 되는 영역 외부 사용자가 이동 하는 경우이 함수는 커서를 계속 표시 되도록 호출 됩니다. 기본 구현은 아무 작업도 수행하지 않습니다. 지정된 된 크기 만큼 항목을 스크롤할이 함수를 재정의 합니다. Note 스크롤, 결과로 OLE 항목의 보이는 부분을 변경할 수 있도록 합니다. 호출 [SetItemRects](#setitemrects) 항목의 표시 사각형을 업데이트 합니다.  
  
 자세한 내용은 참조 [IOleInPlaceSite::Scroll](http://msdn.microsoft.com/library/windows/desktop/ms690291) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="onsetmenu"></a>COleClientItem::OnSetMenu  
 프레임 워크에 의해 두 번 호출 된 위치에서 활성화가 시작 되 고 종료 합니다. 복합 메뉴와 두 번째 설치를 처음으로 (으로 `holemenu` 같지 **NULL**) 제거 합니다.  
  
```  
virtual void OnSetMenu(
    CMenu* pMenuShared,  
    HOLEMENU holemenu,  
    HWND hwndActiveObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `pMenuShared`  
 호출 하 여 생성 된 복합 메뉴에 대 한 포인터는 [OnInsertMenus](#oninsertmenus) 멤버 함수 및 `InsertMenu` 함수입니다.  
  
 `holemenu`  
 반환 되는 메뉴 설명자에 대 한 핸들의 **OleCreateMenuDescriptor** 함수 또는 **NULL** 디스패치 코드가 제거 될 경우.  
  
 *hwndActiveObject*  
 OLE 항목에 대 한 편집 창에 대 한 핸들입니다. 이 OLE에서 편집 명령을 수신할 창입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현에서는 설치 또는 복합 메뉴를 제거 하 고 다음 호출에서 [OleSetMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms692831) 함수를 설치 하거나 디스패치 코드를 제거 합니다. 기본 구현에서는 응용 프로그램에 적합 하지 않은 경우이 함수를 재정의 합니다. 이 함수를 재정의 하는 경우 아마도 재정의 해야 [OnInsertMenus](#oninsertmenus) 및 [OnRemoveMenus](#onremovemenus) 도 합니다. 고급 재정의할 수 있습니다.  
  
 자세한 내용은 참조 [OleCreateMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms691415), [OleSetMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms692831), 및 [IOleInPlaceFrame::SetMenu](http://msdn.microsoft.com/library/windows/desktop/ms693713) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="onshowcontrolbars"></a>COleClientItem::OnShowControlBars  
 표시 하 고 컨테이너 응용 프로그램의 컨트롤 막대를 숨기는 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFrameWnd`  
 컨테이너 응용 프로그램의 프레임 창에 대 한 포인터입니다. 이 주 프레임 창 또는 MDI 자식 창을 수 있습니다.  
  
 `bShow`  
 컨트롤 막대를 표시 하거나 숨길 수 있는지 여부를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 컨트롤 막대 상태 이면 함수를 호출 하면 변경 하면 0이 아니고 0 호출은 변경 없음, 아니면 `pFrameWnd` 컨테이너의 프레임 창을를 가리키지 않습니다.  
  
### <a name="remarks"></a>주의  
 컨트롤 막대에 지정 된 상태에 이미 있는 경우이 함수는 0을 반환 *bShow 합니다.* 이 발생 하는 예를 들어, 컨트롤 막대 숨겨져 있는 경우 및 `bShow` 는 **FALSE**합니다.  
  
 기본 구현에서는 최상위 프레임 창에서 도구 모음을 제거합니다.  
  
##  <a name="onshowitem"></a>COleClientItem::OnShowItem  
 편집 하는 동안 완전히 표시 하 여 OLE 항목을 표시 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnShowItem();
```  
  
### <a name="remarks"></a>주의  
 컨테이너 응용 프로그램 포함 된 항목에 대 한 링크를 지 원하는 경우에 사용 됩니다 (즉, 문서 클래스에서 파생 하는 경우 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)). 이 함수는 내부 활성화 또는 OLE 항목 링크 소스가 고 때 사용자가 편집 하는 동안 호출 됩니다. 기본 구현은 컨테이너 문서에서 첫 번째 보기를 활성화합니다. OLE 항목을 볼 수 있도록 문서를 스크롤합니다 하려면이 함수를 재정의 합니다.  
  
##  <a name="onupdateframetitle"></a>COleClientItem::OnUpdateFrameTitle  
 프레임 창의 제목 표시줄을 업데이트 하는 내부 활성화 하는 동안 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnUpdateFrameTitle();
```  
  
### <a name="return-value"></a>반환 값  
 이 경우&0;이 아닌 함수를 업데이트 했습니다. 프레임 제목, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 프레임 창 제목을 변경 되지 않습니다. 예를 들어 응용 프로그램을 다른 프레임 제목을 사용 하려면이 함수를 재정의 " *서버 응용 프로그램* - *항목* 에서 *docname*" (예: "Microsoft Excel-보고서에는 스프레드시트입니다. 문서 ")입니다. 고급 재정의할 수 있습니다.  
  
##  <a name="reactivateandundo"></a>COleClientItem::ReactivateAndUndo  
 OLE 항목을 다시 활성화 하 고 내부 편집 하는 동안 사용자가 수행한 마지막 작업을 취소 하려면이 함수를 호출 합니다.  
  
```  
BOOL ReactivateAndUndo();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 컨테이너 응용 프로그램을 실행 취소 명령의 지 원하는 경우 OLE 항목을 비활성화 한 후 즉시 실행 취소 명령을 선택 하는 경우이 함수를 호출 합니다.  
  
 이 함수를 호출 하는 서버 사용 하면 서버 응용 프로그램이 Microsoft Foundation 클래스 라이브러리를 작성 한 경우 [COleServerDoc::OnReactivateAndUndo](../../mfc/reference/coleserverdoc-class.md#onreactivateandundo)합니다.  
  
 자세한 내용은 참조 [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="release"></a>COleClientItem::Release  
 OLE 항목에서 사용 하는 리소스를 정리 하려면이 함수를 호출 합니다.  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwCloseOption`  
 OLE 항목을 어떤 상황에서 플래그를 지정 하는 로드 된 상태로 반환 될 때 저장 됩니다. 가능한 값 목록은 참조 하십시오. [COleClientItem::Close](#close)합니다.  
  
### <a name="remarks"></a>주의  
 **릴리스** 호출한는 `COleClientItem` 소멸자입니다.  
  
 자세한 내용은 참조 [iunknown:: Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="reload"></a>COleClientItem::Reload  
 닫고 다시 로드 하는 항목입니다.  
  
```  
BOOL Reload();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 호출 된 `Reload` 함수를 호출 하 여 다른 종류의 항목으로 항목을 활성화 한 후 [ActivateAs](#activateas)합니다.  
  
##  <a name="run"></a>COleClientItem::Run  
 이 항목에 연결 된 응용 프로그램을 실행 합니다.  
  
```  
void Run();
```  
  
### <a name="remarks"></a>주의  
 호출 된 **실행** 멤버 함수는 항목을 활성화 하기 전에 서버 응용 프로그램을 시작 합니다. 자동으로 이렇게 [활성화](#activate) 및 [DoVerb](#doverb)이므로 일반적으로 필요 없는이 함수를 호출 합니다. 와 같은 항목 특성을 설정 하기 위해 서버를 실행 해야 하는 경우이 함수를 호출할 [SetExtent](#setextent)를 실행 하기 전에 [DoVerb](#doverb)합니다.  
  
##  <a name="setdrawaspect"></a>COleClientItem::SetDrawAspect  
 호출 된 `SetDrawAspect` 멤버 함수를 "모양" 또는 항목의 보기를 설정 합니다.  
  
```  
virtual void SetDrawAspect(DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>매개 변수  
 `nDrawAspect`  
 `DVASPECT` 열거형의 값입니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.  
  
- `DVASPECT_CONTENT`항목은 해당 컨테이너 내에 포함 된 개체로 표시 될 수는 방식으로 표시 됩니다.  
  
- `DVASPECT_THUMBNAIL`항목이 검색 도구에 표시 될 수 있도록 "미리 보기" 표현에 렌더링 됩니다.  
  
- `DVASPECT_ICON`항목이는 아이콘으로 표시 됩니다.  
  
- `DVASPECT_DOCPRINT`항목 파일 메뉴에서 인쇄 명령을 사용 하 여 인쇄할 때 처럼 표시 됩니다.  
  
### <a name="remarks"></a>주의  
 모양을 방법을 지정 항목을 통해 렌더링할 [그리기](#draw) 의 기본값 해당 함수에 대해 `nDrawAspect` 인수를 사용 합니다.  
  
 아이콘 변경 (및 아이콘 변경 대화 상자를 직접 호출 하는 다른 대화 상자)에서이 함수를 자동으로 호출 아이콘 표시 측면은 사용자가 요청할 때 사용할 수 있도록 합니다.  
  
##  <a name="setextent"></a>COleClientItem::SetExtent  
 OLE 항목에 사용할 수 있는 공간을 지정 하려면이 함수를 호출 합니다.  
  
```  
void SetExtent(
    const CSize& size,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>매개 변수  
 `size`  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) 크기 정보를 포함 하는 개체입니다.  
  
 `nDrawAspect`  
 설정할 경계가 OLE 항목의 모양을 지정 합니다. 가능한 값에 대 한 참조 [SetDrawAspect](#setdrawaspect)합니다.  
  
### <a name="remarks"></a>주의  
 이 인해 서버 응용 프로그램이 Microsoft Foundation Class 라이브러리를 사용 하 여 작성는 [OnSetExtent](../../mfc/reference/coleserveritem-class.md#onsetextent) 멤버 함수는 해당 `COleServerItem` 개체를 호출할 수 있습니다. 그런 다음 OLE 항목의 표시를 적절 하 게 조정할 수 있습니다. 차원에 있어야 합니다. `MM_HIMETRIC` 단위입니다. 사용자가 OLE 항목 크기 조정 또는 레이아웃 협상 형태의 지 원하는 경우이 함수를 호출 합니다.  
  
 자세한 내용은 참조 [IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="sethostnames"></a>COleClientItem::SetHostNames  
 컨테이너 응용 프로그램의 이름 및 포함된 된 OLE 항목에 대 한 컨테이너의 이름을 지정 하려면이 함수를 호출 합니다.  
  
```  
void SetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszHost`  
 컨테이너 응용 프로그램의 사용자 표시 이름에 대 한 포인터입니다.  
  
 `lpszHostObj`  
 OLE 항목을 포함 하는 컨테이너의 식별 문자열에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 호출 하는 서버 응용 프로그램이 Microsoft Foundation Class 라이브러리를 사용 하 여 작성는 [OnSetHostNames](../../mfc/reference/coleserverdoc-class.md#onsethostnames) 의 멤버 함수는 `COleServerDoc` OLE 항목을 포함 하는 문서입니다. OLE 항목을 편집할 때이 정보는 창 제목에 사용 됩니다. 컨테이너 문서를 로드할 때마다 프레임 워크는 문서에 있는 모든 OLE 항목에 대 한이 함수를 호출 합니다. `SetHostNames`포함 된 항목에만 적용 됩니다. 편집을 위해 포함된 된 OLE 항목 활성화 될 때마다가이 함수를 호출 하려면 필요는 없습니다.  
  
 이 자동으로 응용 프로그램 이름 및 문서 이름을 사용 하 여 개체를 로드할 때 또는 라고도 다른 이름으로 파일을 저장 하는 경우 합니다. 일반적으로이 함수를 직접 호출할 필요가 없다는 적절 하 게 합니다.  
  
 자세한 내용은 참조 [IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="seticonicmetafile"></a>COleClientItem::SetIconicMetafile  
 항목의 아이콘을 그리는 데 사용 하 여 메타 파일을 캐시 합니다.  
  
```  
BOOL SetIconicMetafile(HGLOBAL hMetaPict);
```  
  
### <a name="parameters"></a>매개 변수  
 `hMetaPict`  
 항목의 아이콘을 그리는 데 사용 하 여 메타 파일에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 [GetIconicMetafile](#geticonicmetafile) 메타 파일을 검색할 수 있습니다.  
  
 `hMetaPict` 매개 변수 항목;에 복사 되며 따라서 `hMetaPict` 호출자가 해제 해야 합니다.  
  
##  <a name="setitemrects"></a>COleClientItem::SetItemRects  
 경계 사각형 또는 OLE 항목의 표시 사각형을 설정 하려면이 함수를 호출 합니다.  
  
```  
BOOL SetItemRects(
    LPCRECT lpPosRect = NULL,  
    LPCRECT lpClipRect = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *lprcPosRect*  
 부모 창의 클라이언트 좌표에서 상대적인 OLE 항목의 경계를 포함 하는 사각형에 대 한 포인터입니다.  
  
 *lprcClipRect*  
 부모 창의 클라이언트 좌표에서 상대적인 OLE 항목의 표시 되는 부분의 범위가 포함 된 사각형에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현에서이 함수는 호출 된 [OnChangeItemPosition](#onchangeitemposition) 멤버 함수입니다. 위치 또는 표시 되는 부분 OLE 항목 변경 될 때마다이 함수를 호출 해야 합니다. 일반적으로이 값에서 보기의 호출 [OnSize](../../mfc/reference/cwnd-class.md#onsize) 및 [OnScrollBy](../../mfc/reference/cview-class.md#onscrollby) 멤버 함수입니다.  
  
 자세한 내용은 참조 [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="setlinkupdateoptions"></a>COleClientItem::SetLinkUpdateOptions  
 지정된 된 연결 된 항목의 표시에 대 한 연결 업데이트 옵션을 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetLinkUpdateOptions(OLEUPDATE dwUpdateOpt);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwUpdateOpt*  
 이 항목에 대 한 연결 업데이트 옵션의 값입니다. 이 값에는 다음 중 하나 여야 합니다.  
  
- `OLEUPDATE_ALWAYS`가능 하면 연결된 된 항목을 업데이트 합니다. 이 옵션은 연결 대화 상자에서 자동 연결 업데이트 라디오 단추를 지원 합니다.  
  
- `OLEUPDATE_ONCALL`컨테이너 응용 프로그램의 요청에만 연결 된 항목을 업데이트 (때는 [UpdateLink](#updatelink) 멤버 함수를 호출). 이 옵션은 연결 대화 상자에서 수동 연결 업데이트 라디오 단추를 지원 합니다.  
  
### <a name="remarks"></a>주의  
 일반적으로 연결 대화 상자에서 사용자가 선택한 업데이트 옵션 변경 하면 안 됩니다.  
  
 자세한 내용은 참조 [IOleLink::SetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680120) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="setprintdevice"></a>COleClientItem::SetPrintDevice  
 이 항목에 대 한 인쇄 대상 장치를 변경 하려면이 함수를 호출 합니다.  
  
```  
BOOL SetPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL SetPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>매개 변수  
 `ptd`  
 에 대 한 포인터는 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) 데이터 구조를 새 대상 인쇄 장치에 대 한 정보를 포함 합니다. 수 **NULL**합니다.  
  
 `ppd`  
 에 대 한 포인터는 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646940) 데이터 구조를 새 대상 인쇄 장치에 대 한 정보를 포함 합니다. 수 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 항목에 대 한 대상 인쇄 장치를 업데이트 하지만 프레젠테이션 캐시를 새로 고치지 않습니다. 항목에 대 한 프레젠테이션 캐시를 업데이트 하려면 호출 [UpdateLink](#updatelink)합니다.  
  
 이 함수에 대 한 인수는 대상 장치를 식별 하는 OLE 시스템이 사용 하는 정보를 포함 합니다. **PRINTDLG** 구조 Windows에서 공통 인쇄 대화 상자를 초기화 하는 정보를 포함 합니다. 사용자는 대화 상자를 닫은 후 Windows는이 구조에서 사용자의 선택에 대 한 정보를 반환 합니다. `m_pd` 의 멤버는 [CPrintDialog](../../mfc/reference/cprintdialog-class.md) 개체는 **PRINTDLG** 구조입니다.  
  
 이 구조에 대 한 자세한 내용은 참조 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 자세한 내용은 참조 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="updatelink"></a>COleClientItem::UpdateLink  
 OLE 항목의 프레젠테이션 데이터를 즉시 업데이트 하려면이 함수를 호출 합니다.  
  
```  
BOOL UpdateLink();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아닌 값이고, 실패하면 0입니다.  
  
### <a name="remarks"></a>주의  
 연결 된 항목에 대 한 함수를 OLE 항목에 대 한 새 프레젠테이션을 가져올 소스를 링크를 찾습니다. 이 프로세스는 하나 이상의 서버, 응용 프로그램 실행 시간이 오래 걸릴 수 있는 포함 될 수 있습니다. 포함 된 항목에 대 한 함수를 재귀적으로 만료 될 수 있는 링크가 포함 된 항목에 포함 되는지 여부를 확인 하 고 해당 업데이트를 작동 합니다. 사용자 연결 대화 상자를 사용 하 여 개별 링크를 수동으로 업데이트 수입니다.  
  
 자세한 내용은 참조 [IOleLink::Update](http://msdn.microsoft.com/library/windows/desktop/ms692660) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 MFCBIND](../../visual-cpp-samples.md)   
 [MFC 샘플 OCLIENT](../../visual-cpp-samples.md)   
 [CDocItem 클래스](../../mfc/reference/cdocitem-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleServerItem 클래스](../../mfc/reference/coleserveritem-class.md)

