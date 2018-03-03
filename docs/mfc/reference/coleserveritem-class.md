---
title: "COleServerItem 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleServerItem
- AFXOLE/COleServerItem
- AFXOLE/COleServerItem::COleServerItem
- AFXOLE/COleServerItem::AddOtherClipboardData
- AFXOLE/COleServerItem::CopyToClipboard
- AFXOLE/COleServerItem::DoDragDrop
- AFXOLE/COleServerItem::GetClipboardData
- AFXOLE/COleServerItem::GetDocument
- AFXOLE/COleServerItem::GetEmbedSourceData
- AFXOLE/COleServerItem::GetItemName
- AFXOLE/COleServerItem::GetLinkSourceData
- AFXOLE/COleServerItem::GetObjectDescriptorData
- AFXOLE/COleServerItem::IsConnected
- AFXOLE/COleServerItem::IsLinkedItem
- AFXOLE/COleServerItem::NotifyChanged
- AFXOLE/COleServerItem::OnDoVerb
- AFXOLE/COleServerItem::OnDraw
- AFXOLE/COleServerItem::OnDrawEx
- AFXOLE/COleServerItem::OnGetClipboardData
- AFXOLE/COleServerItem::OnGetExtent
- AFXOLE/COleServerItem::OnInitFromData
- AFXOLE/COleServerItem::OnQueryUpdateItems
- AFXOLE/COleServerItem::OnRenderData
- AFXOLE/COleServerItem::OnRenderFileData
- AFXOLE/COleServerItem::OnRenderGlobalData
- AFXOLE/COleServerItem::OnSetColorScheme
- AFXOLE/COleServerItem::OnSetData
- AFXOLE/COleServerItem::OnSetExtent
- AFXOLE/COleServerItem::OnUpdate
- AFXOLE/COleServerItem::OnUpdateItems
- AFXOLE/COleServerItem::SetItemName
- AFXOLE/COleServerItem::GetDataSource
- AFXOLE/COleServerItem::OnHide
- AFXOLE/COleServerItem::OnOpen
- AFXOLE/COleServerItem::OnShow
- AFXOLE/COleServerItem::m_sizeExtent
dev_langs:
- C++
helpviewer_keywords:
- COleServerItem [MFC], COleServerItem
- COleServerItem [MFC], AddOtherClipboardData
- COleServerItem [MFC], CopyToClipboard
- COleServerItem [MFC], DoDragDrop
- COleServerItem [MFC], GetClipboardData
- COleServerItem [MFC], GetDocument
- COleServerItem [MFC], GetEmbedSourceData
- COleServerItem [MFC], GetItemName
- COleServerItem [MFC], GetLinkSourceData
- COleServerItem [MFC], GetObjectDescriptorData
- COleServerItem [MFC], IsConnected
- COleServerItem [MFC], IsLinkedItem
- COleServerItem [MFC], NotifyChanged
- COleServerItem [MFC], OnDoVerb
- COleServerItem [MFC], OnDraw
- COleServerItem [MFC], OnDrawEx
- COleServerItem [MFC], OnGetClipboardData
- COleServerItem [MFC], OnGetExtent
- COleServerItem [MFC], OnInitFromData
- COleServerItem [MFC], OnQueryUpdateItems
- COleServerItem [MFC], OnRenderData
- COleServerItem [MFC], OnRenderFileData
- COleServerItem [MFC], OnRenderGlobalData
- COleServerItem [MFC], OnSetColorScheme
- COleServerItem [MFC], OnSetData
- COleServerItem [MFC], OnSetExtent
- COleServerItem [MFC], OnUpdate
- COleServerItem [MFC], OnUpdateItems
- COleServerItem [MFC], SetItemName
- COleServerItem [MFC], GetDataSource
- COleServerItem [MFC], OnHide
- COleServerItem [MFC], OnOpen
- COleServerItem [MFC], OnShow
- COleServerItem [MFC], m_sizeExtent
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd64d6a2cf4fe36e62f5c6599521780c4ee002ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="coleserveritem-class"></a>COleServerItem 클래스
OLE 항목에 대한 서버 인터페이스를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleServerItem : public CDocItem  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleServerItem::COleServerItem](#coleserveritem)|`COleServerItem` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleServerItem::AddOtherClipboardData](#addotherclipboarddata)|프레젠테이션 및 변환 형식에 배치 된 `COleDataSource` 개체입니다.|  
|[COleServerItem::CopyToClipboard](#copytoclipboard)|항목을 클립보드에 복사 합니다.|  
|[COleServerItem::DoDragDrop](#dodragdrop)|끌어서 놓기 작업을 수행합니다.|  
|[COleServerItem::GetClipboardData](#getclipboarddata)|데이터 전송 (끌어서 놓기 또는 클립보드)에서 사용 하기 위해 데이터 소스를 가져옵니다.|  
|[COleServerItem::GetDocument](#getdocument)|항목이 포함 된 서버 문서를 반환 합니다.|  
|[COleServerItem::GetEmbedSourceData](#getembedsourcedata)|가져옵니다는 **CF_EMBEDSOURCE** OLE 항목에 대 한 데이터입니다.|  
|[COleServerItem::GetItemName](#getitemname)|항목의 이름을 반환합니다. 연결 된 항목에 사용 합니다.|  
|[COleServerItem::GetLinkSourceData](#getlinksourcedata)|가져옵니다는 `CF_LINKSOURCE` OLE 항목에 대 한 데이터입니다.|  
|[COleServerItem::GetObjectDescriptorData](#getobjectdescriptordata)|가져옵니다는 **CF_OBJECTDESCRIPTOR** OLE 항목에 대 한 데이터입니다.|  
|[COleServerItem::IsConnected](#isconnected)|항목이 현재 활성 컨테이너에 연결 되어 있는지 여부를 나타냅니다.|  
|[COleServerItem::IsLinkedItem](#islinkeditem)|항목에 연결 된 OLE 항목을 나타내는지 여부를 나타냅니다.|  
|[COleServerItem::NotifyChanged](#notifychanged)|자동 링크 업데이트와 함께 모든 컨테이너를 업데이트합니다.|  
|[COleServerItem::OnDoVerb](#ondoverb)|동사를 실행 하기 위해 호출 합니다.|  
|[Coleserveritem:: Ondraw](#ondraw)|컨테이너; 항목을 그리는 요청할 때 호출 필요한 구현입니다.|  
|[COleServerItem::OnDrawEx](#ondrawex)|특수 항목 그리기에 대 한 호출 됩니다.|  
|[COleServerItem::OnGetClipboardData](#ongetclipboarddata)|데이터를 클립보드에 복사 합니다를 확보 하기 위해 프레임 워크에서 호출 됩니다.|  
|[COleServerItem::OnGetExtent](#ongetextent)|OLE 항목의 크기를 검색 하기 위해 프레임 워크에서 호출 됩니다.|  
|[COleServerItem::OnInitFromData](#oninitfromdata)|지정 된 데이터 전송 개체의 내용을 사용 하 여 OLE 항목을 초기화 하기 위해 프레임 워크에서 호출 됩니다.|  
|[COleServerItem::OnQueryUpdateItems](#onqueryupdateitems)|연결된 된 항목이 업데이트 해야 하는지 여부를 결정 하기 위해 호출 합니다.|  
|[COleServerItem::OnRenderData](#onrenderdata)|지연 된 렌더링의 일환으로 데이터를 검색합니다.|  
|[COleServerItem::OnRenderFileData](#onrenderfiledata)|데이터를 검색 한 `CFile` 지연 된 렌더링의 일부로 개체입니다.|  
|[COleServerItem::OnRenderGlobalData](#onrenderglobaldata)|데이터를 검색 한 `HGLOBAL` 지연 된 렌더링의 일환으로 합니다.|  
|[COleServerItem::OnSetColorScheme](#onsetcolorscheme)|항목의 색 구성표를 설정 하기 위해 호출 합니다.|  
|[COleServerItem::OnSetData](#onsetdata)|항목의 데이터를 설정 하기 위해 호출 합니다.|  
|[COleServerItem::OnSetExtent](#onsetextent)|OLE 항목의 크기를 설정 하기 위해 프레임 워크에서 호출 됩니다.|  
|[COleServerItem::OnUpdate](#onupdate)|호출 문서 항목의 일부분에 속하는 경우 변경 됩니다.|  
|[COleServerItem::OnUpdateItems](#onupdateitems)|서버 문서에서 모든 항목의 프레젠테이션 캐시를 업데이트 하기 위해 호출 합니다.|  
|[COleServerItem::SetItemName](#setitemname)|항목의 이름을 설정합니다. 연결 된 항목에 사용 합니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleServerItem::GetDataSource](#getdatasource)|변환 형식을 저장 하는 데 사용 하는 개체를 가져옵니다.|  
|[COleServerItem::OnHide](#onhide)|OLE 항목을 숨기기 위해 프레임 워크에서 호출 됩니다.|  
|[COleServerItem::OnOpen](#onopen)|OLE 항목을 자체 최상위 창에 표시 하기 위해 프레임 워크에서 호출 됩니다.|  
|[COleServerItem::OnShow](#onshow)|컨테이너 항목을 표시 하기 위해 요청 하면 호출 됩니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COleServerItem::m_sizeExtent](#m_sizeextent)|OLE 항목의 표시 되는 방법에 대 한 서버를 알립니다.|  
  
## <a name="remarks"></a>설명  
 링크 된 항목 일부 또는 전체 서버 문서를 나타낼 수 있습니다. 포함된 된 항목은 항상 전체 서버 문서를 나타냅니다.  
  
 `COleServerItem` 클래스 정의 OLE 시스템 동적 연결 라이브러리 (Dll)에 의해 호출 되는 몇 가지 재정의 가능한 멤버 함수 일반적으로 컨테이너 응용 프로그램의 요청에 대 한 응답에서입니다. 이러한 멤버 함수는 표시, 동사를 실행 하거나 다양 한 형식의 데이터 검색 하는 등 다양 한 방법으로 간접적으로 항목을 조작 하는 컨테이너 응용 프로그램을 허용 합니다.  
  
 사용 하도록 `COleServerItem`를 여기에서 클래스를 파생 하 고 구현는 [OnDraw](#ondraw) 및 [Serialize](../../mfc/reference/cobject-class.md#serialize) 멤버 함수입니다. `OnDraw` 함수 컨테이너 응용 프로그램이 복합 문서를 열 때 표시 될 수 있도록 항목의 메타 파일 표시를 제공 합니다. `Serialize` 의 기능은 `CObject` 포함 된 항목을 서버 및 컨테이너 응용 프로그램 간에 전송 될 수 있도록 항목의 기본 표시를 제공 합니다. [OnGetExtent](#ongetextent) 항목 크기를 조정 하려면 컨테이너를 사용 하면 컨테이너에 대 한 항목의 원래 크기를 제공 합니다.  
  
 서버 및 관련된 항목에 대 한 자세한 내용은 문서 참조 [서버: 서버 구현](../../mfc/servers-implementing-a-server.md) 및 문서에 "컨테이너/서버 응용 만들기" [컨테이너: 고급 기능](../../mfc/containers-advanced-features.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleServerItem`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="addotherclipboarddata"></a>COleServerItem::AddOtherClipboardData  
 지정 된 OLE 항목에 대 한 프레젠테이션 및 변환 형식을 추가 하려면이 함수를 호출 `COleDataSource` 개체입니다.  
  
```  
void AddOtherClipboardData(COleDataSource* pDataSource);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDataSource`  
 에 대 한 포인터는 `COleDataSource` 개체에서 데이터를 배치 합니다.  
  
### <a name="remarks"></a>설명  
 구현 해야 합니다는 [OnDraw](#ondraw) 멤버 함수를 항목에 대 한 표시 형식 (예: 메타 파일 그림)을 제공 합니다. 등록을 지원 하기 위해 다른 변환 형식을 사용 하 여는 [COleDataSource](../../mfc/reference/coledatasource-class.md) 에서 반환 된 개체 [GetDataSource](#getdatasource) 재정의 [OnRenderData](#onrenderdata) 멤버 함수를 지원 하려는 형식의 데이터를에서 제공 합니다.  
  
##  <a name="coleserveritem"></a>COleServerItem::COleServerItem  
 생성 된 `COleServerItem` 문서 항목의 서버 문서 컬렉션에 추가 하는 개체입니다.  
  
```  
COleServerItem(
    COleServerDoc* pServerDoc,  
    BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>매개 변수  
 `pServerDoc`  
 새 항목을 포함 하는 문서에 대 한 포인터입니다.  
  
 `bAutoDelete`  
 에 대 한 링크가 해제 될 때 개체를 삭제할 수 있는지 여부를 나타내는 플래그입니다. 이 속성을 설정 **FALSE** 경우는 `COleServerItem` 개체를 삭제 해야 하는 문서의 데이터의 필수적인 부분입니다. 이 속성을 설정 **TRUE** 개체는 프레임 워크에서 삭제할 수 있는 문서의 데이터에서 특정 범위를 식별 하는 데 사용 되는 보조 구조 하는 경우.  
  
##  <a name="copytoclipboard"></a>COleServerItem::CopyToClipboard  
 OLE 항목을 클립보드로 복사 하려면이 함수를 호출 합니다.  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bIncludeLink`  
 이 속성을 설정 **TRUE** 링크 데이터를 클립보드에 복사할 경우. 이 속성을 설정 **FALSE** 서버 응용 프로그램이 링크를 지원 하지 않는 경우.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용는 [OnGetClipboardData](#ongetclipboarddata) 만들려는 멤버 함수는 [COleDataSource](../../mfc/reference/coledatasource-class.md) 지원 되는 형식에서 OLE 항목의 데이터를 포함 하는 개체입니다. 그런 다음 저장 하는 함수는 `COleDataSource` 개체를 사용 하 여 클립보드에는 [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard) 함수입니다. `COleDataSource` 개체 항목의 네이티브 데이터와 표현 포함 `CF_METAFILEPICT` 으로 형식으로 데이터를 지원 하도록 선택 하면 모든 변환 형식입니다. 구현한 해야 [Serialize](../../mfc/reference/cobject-class.md#serialize) 및 [OnDraw](#ondraw) 작동 하려면이 멤버 함수에 대 한 합니다.  
  
##  <a name="dodragdrop"></a>COleServerItem::DoDragDrop  
 호출 된 `DoDragDrop` 멤버 함수를 끌어서 놓기 작업을 수행 합니다.  
  
```  
DROPEFFECT DoDragDrop(
    LPCRECT lpRectItem,  
    CPoint ptOffset,  
    BOOL bIncludeLink = FALSE,  
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,  
    LPCRECT lpRectStartDrag = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpRectItem*  
 클라이언트 영역 상대적인 화면에서 항목의 사각형입니다.  
  
 `ptOffset`  
 오프셋 `lpItemRect` 끌기 당시에 있던 마우스 위치입니다.  
  
 `bIncludeLink`  
 이 속성을 설정 **TRUE** 링크 데이터를 클립보드에 복사할 경우. 로 설정 **FALSE** 응용 프로그램 링크를 지원 하지 않는 경우.  
  
 `dwEffects`  
 끌기 작업 (복사, 이동 및 링크의 조합)에 끌기 소스를 사용할 수 있는 효과 결정 합니다.  
  
 `lpRectStartDrag`  
 끌기 실제로 시작 위치를 정의 하는 사각형에 대 한 포인터입니다. 자세한 내용은 아래 설명 부분을 참조하십시오.  
  
### <a name="return-value"></a>반환 값  
 `DROPEFFECT` 열거형의 값입니다. 이 경우 `DROPEFFECT_MOVE`, 원래 데이터를 제거 해야 합니다.  
  
### <a name="remarks"></a>설명  
 끌어서 놓기 작업이 즉시 시작 되지 않습니다. 마우스 커서가으로 지정 된 사각형을 벗어날 때까지 기다렸다가 `lpRectStartDrag` 지정 된 기간 (밀리초) 조건이 충족 될 때까지 또는 합니다. 경우 `lpRectStartDrag` 은 **NULL**, 하나의 픽셀 마우스 커서를 이동 하는 경우 끌기 시작 되도록 기본 사각형 사용 됩니다.  
  
 레지스트리 키 설정 지연 시간 지정 됩니다. 호출 하 여 지연 시간을 변경할 수 있습니다 [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) 또는 [cwinapp:: Writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint)합니다. 지연 시간을 지정 하지 않으면 기본값은 200 밀리초 사용 됩니다. 끌어서 지연 시간을 다음과 같이 저장 됩니다.  
  
-   Windows NT 끌어서 지연 시간 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay에 저장 됩니다.  
  
-   Windows 3.x 끌어서 지연 시간 WIN에 저장 됩니다. INI 파일 [Windows} 섹션.  
  
-   Windows 95/98 끌어서 지연 시간 WIN의 캐시 된 버전에 저장 됩니다. INI 합니다.  
  
 연기 된 정보는 레지스트리에 저장 됩니다는 방법에 대 한 자세한 내용은 끌어에 대 한 또는 합니다. INI 파일 참조 [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) Windows sdk에서입니다.  
  
##  <a name="getclipboarddata"></a>COleServerItem::GetClipboardData  
 이 함수를 지정 된 채우기 호출 [COleDataSource](../../mfc/reference/coledatasource-class.md) 개체를 호출한 경우 클립보드에 복사할 수 있는 모든 데이터로 [CopyToClipboard](#copytoclipboard) (경우에 동일한 데이터를 전송 합니다 있습니다 호출 [DoDragDrop](#dodragdrop)).  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDataSource`  
 에 대 한 포인터는 `COleDataSource` 지원 되는 모든 형식에서 OLE 항목의 데이터를 받게 될 개체입니다.  
  
 `bIncludeLink`  
 **True 이면** 링크 데이터를 클립보드에 복사할 경우. **FALSE** 서버 응용 프로그램이 링크를 지원 하지 않는 경우.  
  
 `lpOffset`  
 개체의 원점부터 마우스 커서를 픽셀 단위로 오프셋입니다.  
  
 `lpSize`  
 픽셀 단위로 개체의 크기입니다.  
  
### <a name="remarks"></a>설명  
 이 함수 호출의 [GetEmbedSourceData](#getembedsourcedata) OLE 항목 및 호출에 대 한 원시 데이터를 가져오려는 멤버 함수는 [AddOtherClipboardData](#addotherclipboarddata) 표시 형식 및 모든 멤버 함수 지원 되는 변환 형식입니다. 경우 `bIncludeLink` 은 **TRUE**,이 함수는 호출 또한 [GetLinkSourceData](#getlinksourcedata) 항목에 대 한 연결 데이터를 가져오려는 합니다.  
  
 형식에 배치 하려는 경우이 함수를 재정의 한 `COleDataSource` 앞 이나 뒤에서 제공 하는 해당 형식의 개체 `CopyToClipboard`합니다.  
  
##  <a name="getdatasource"></a>COleServerItem::GetDataSource  
 가져오려면이 함수를 호출 하 여 [COleDataSource](../../mfc/reference/coledatasource-class.md) 서버 응용 프로그램이 지 원하는 변환 형식을 저장 하는 데 사용 되는 개체입니다.  
  
```  
COleDataSource* GetDataSource();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `COleDataSource` 변환 형식을 저장 하는 데 사용 되는 개체입니다.  
  
### <a name="remarks"></a>설명  
 서버 응용 프로그램 작업 데이터를 전송 하는 동안 다양 한 형식에 데이터를 제공 하려는 경우 해당 형식으로 등록 된 `COleDataSource` 이 함수에서 반환 된 개체입니다. 예를 들어, 입력 하려는 경우는 **CF_TEXT** 클립보드 또는 끌어 놓기 작업에 대 한 OLE 항목의 표시를 하는 형식으로 등록 합니다는 `COleDataSource` 이 함수를 반환 하는 개체와 다음 재정의  **OnRenderXxxData** 멤버 함수가 데이터를 제공 합니다.  
  
##  <a name="getdocument"></a>COleServerItem::GetDocument  
 항목을 포함 하는 문서에 대 한 포인터를 가져오려면이 함수를 호출 합니다.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항목이 포함 된 문서에 대 한 포인터 **NULL** 항목이 문서의 일부가 아닌 경우.  
  
### <a name="remarks"></a>설명  
 이렇게 하면에 대 한 인수로 전달 되는 서버 문서에 대 한 액세스는 `COleServerItem` 생성자입니다.  
  
##  <a name="getembedsourcedata"></a>COleServerItem::GetEmbedSourceData  
 가져오려면이 함수를 호출 하 여 **CF_EMBEDSOURCE** OLE 항목에 대 한 데이터입니다.  
  
```  
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpStgMedium`  
 에 대 한 포인터는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 를 받을 구조는 **CF_EMBEDSOURCE** OLE 항목에 대 한 데이터입니다.  
  
### <a name="remarks"></a>설명  
 이 형식 항목의 네이티브 데이터를 포함 합니다. 구현 해야 합니다는 `Serialize` 제대로 작동 하려면이 함수에 대 한 멤버 함수입니다.  
  
 결과 수를 사용 하 여 다음 데이터 원본에 추가 하는 수 [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata)합니다. 이 함수는 자동으로 호출 [COleServerItem::OnGetClipboardData](#ongetclipboarddata)합니다.  
  
 자세한 내용은 참조 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Windows sdk에서입니다.  
  
##  <a name="getitemname"></a>COleServerItem::GetItemName  
 항목의 이름을 가져오려면이 함수를 호출 합니다.  
  
```  
const CString& GetItemName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항목의 이름입니다.  
  
### <a name="remarks"></a>설명  
 일반적으로 연결 된 항목에 대해서만이 함수를 호출 합니다.  
  
##  <a name="getlinksourcedata"></a>COleServerItem::GetLinkSourceData  
 가져오려면이 함수를 호출 하 여 `CF_LINKSOURCE` OLE 항목에 대 한 데이터입니다.  
  
```  
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpStgMedium`  
 에 대 한 포인터는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 를 받을 구조는 `CF_LINKSOURCE` OLE 항목에 대 한 데이터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 형식에는 OLE 항목 유형과 OLE 항목을 포함 하는 문서를 찾는 데 필요한 정보를 설명 하는 CLSID 포함 됩니다.  
  
 결과 데이터 원본에 추가할 수 있습니다 [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata)합니다. 이 함수는 자동으로 호출 [OnGetClipboardData](#ongetclipboarddata)합니다.  
  
 자세한 내용은 참조 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Windows sdk에서입니다.  
  
##  <a name="getobjectdescriptordata"></a>COleServerItem::GetObjectDescriptorData  
 가져오려면이 함수를 호출 하 여 **CF_OBJECTDESCRIPTOR** OLE 항목에 대 한 데이터입니다.  
  
```  
void GetObjectDescriptorData(
    LPPOINT lpOffset,  
    LPSIZE lpSize,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpOffset`  
 OLE 항목의 왼쪽 위 모서리에서 마우스 클릭의 오프셋입니다. 수 **NULL**합니다.  
  
 `lpSize`  
 OLE 항목의 크기입니다. 수 **NULL**합니다.  
  
 `lpStgMedium`  
 에 대 한 포인터는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 를 받을 구조는 **CF_OBJECTDESCRIPTOR** OLE 항목에 대 한 데이터입니다.  
  
### <a name="remarks"></a>설명  
 정보에 복사 되는 **STGMEDIUM** 가리키는 구조 `lpStgMedium`합니다. 이 형식 붙여넣기 대화 상자에 필요한 정보를 포함 합니다.  
  
 자세한 내용은 참조 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Windows sdk에서입니다.  
  
##  <a name="isconnected"></a>COleServerItem::IsConnected  
 OLE 항목이 연결 되어 있는지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsConnected() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항목이 연결 된; 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 OLE 항목에 하나 이상의 컨테이너 항목에 대 한 참조가 있는 경우 연결로 간주 됩니다. 항목 참조 개수가 0 보다 큰 경우 있거나 보고서가 포함된 된 항목에 연결 되어 있습니다.  
  
##  <a name="islinkeditem"></a>COleServerItem::IsLinkedItem  
 OLE 항목이 연결된 된 항목 인지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsLinkedItem() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항목이 연결된 된 항목; 이면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 항목은 항목이 유효 포함 된 항목의 문서 목록에 반환 되지 않습니다 연결 됩니다. 링크 된 항목 수 또는 컨테이너에 연결 하지 않을 수 있습니다.  
  
 연결 및 포함 된 항목에 대 한 동일한 클래스를 사용 하는 경우 `IsLinkedItem`대부분의 경우 코드가 자주 발생 하지만 포함 된 항목을 다르게 동작 하는 연결 된 항목을 만들 수 있습니다.  
  
##  <a name="m_sizeextent"></a>COleServerItem::m_sizeExtent  
 이 멤버는 개체의 표시 되는 컨테이너 문서의 서버에 알려 줍니다.  
  
```  
CSize m_sizeExtent;  
```  
  
### <a name="remarks"></a>설명  
 기본 구현은 [OnSetExtent](#onsetextent) 이 멤버를 설정 합니다.  
  
##  <a name="notifychanged"></a>COleServerItem::NotifyChanged  
 연결된 된 항목이 변경 되 면이 함수를 호출 합니다.  
  
```  
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>매개 변수  
 `nDrawAspect`  
 값은 `DVASPECT` 변경 된 OLE 항목의 어떤 부분을 나타내는 열거형입니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.  
  
- `DVASPECT_CONTENT`항목은 해당 컨테이너 내에 포함 된 개체로 표시 될 수 하는 방식으로 표시 됩니다.  
  
- `DVASPECT_THUMBNAIL`검색 도구에 표시 될 수 있도록 "미리" 표현에서 항목이 렌더링 됩니다.  
  
- `DVASPECT_ICON`항목은 아이콘으로 표시 됩니다.  
  
- `DVASPECT_DOCPRINT`항목 파일 메뉴에서 인쇄 명령을 사용 하 여 인쇄할 때 처럼 표시 됩니다.  
  
### <a name="remarks"></a>설명  
 컨테이너 항목이 들어 자동 링크가 포함 된 문서에 연결 된 경우 해당 항목 변경 내용을 반영 하도록 업데이트 됩니다. Microsoft Foundation Class 라이브러리를 사용 하 여 작성 하는 컨테이너 응용 프로그램에서 [COleClientItem::OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 눌렀을 때 호출 됩니다.  
  
##  <a name="ondoverb"></a>COleServerItem::OnDoVerb  
 지정된 된 동사를 실행 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDoVerb(LONG iVerb);
```  
  
### <a name="parameters"></a>매개 변수  
 `iVerb`  
 실행 하는 동사를 지정 합니다. 다음 중 하나가 수 있습니다.  
  
|값|의미|기호|  
|-----------|-------------|------------|  
|0|기본 동사|`OLEIVERB_PRIMARY`|  
|1|보조 동사|(None)|  
|- 1|편집을 위해 표시 항목|`OLEIVERB_SHOW`|  
|- 2|별도 창에서 항목을 편집|`OLEIVERB_OPEN`|  
|- 3|항목 숨기기|`OLEIVERB_HIDE`|  
  
 일반적으로-1 값은 다른 동사에 대 한 별칭입니다. 편집 열고 지원 되지 않는 경우-2가-1과 같습니다. 추가 값에 대 한 참조 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows sdk에서입니다.  
  
### <a name="remarks"></a>설명  
 Microsoft Foundation Class 라이브러리 사용 하는 컨테이너 응용 프로그램을 작성 하는 경우이 함수는 호출 될 때는 [COleClientItem::Activate](../../mfc/reference/coleclientitem-class.md#activate) 멤버 함수는 해당 `COleClientItem` 개체를 호출 합니다. 기본 구현 호출은 [문서가](#onshow) 경우 멤버 함수에서 기본 동사 또는 `OLEIVERB_SHOW` 지정 된 [OnOpen](#onopen) 경우 보조 동사 또는 `OLEIVERB_OPEN` 지정 된 및 [OnHide](#onhide) 경우 `OLEIVERB_HIDE` 지정 됩니다. 기본 구현 호출 `OnShow` 경우 `iVerb` 위에 나열 된 동사 중 하나가 아닙니다.  
  
 기본 동사 프로그램 항목이 표시 되지 않을 경우이 함수를 재정의 합니다. 예를 들어 항목 사운드 녹음 이며 해당 기본 동사는 재생 하는 경우 항목을 재생할 서버 응용 프로그램을 표시 해야 없습니다.  
  
 자세한 내용은 참조 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows sdk에서입니다.  
  
##  <a name="ondraw"></a>Coleserveritem:: Ondraw  
 OLE 항목을 메타 파일로 렌더링 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnDraw(
    CDC* pDC,  
    CSize& rSize) = 0;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 에 대 한 포인터는 [CDC](../../mfc/reference/cdc-class.md) 개체 항목을 그리는입니다. 디스플레이 컨텍스트는 자동으로 연결 특성 디스플레이 컨텍스트 되므로 특성 함수를 호출할 수 있지만 이렇게 하면 지금 하 게 만드는 메타 파일 장치 전용입니다.  
  
 `rSize`  
 크기에 **HIMETRIC** 를 그릴 메타 파일의 단위입니다.  
  
### <a name="return-value"></a>반환 값  
 항목이 성공적으로 그린; 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 OLE 항목의 메타 파일 표시는 컨테이너 응용 프로그램에서 항목을 표시 하는 데 사용 됩니다. 메타 파일에 사용 되는 Microsoft Foundation 클래스 라이브러리와 컨테이너 응용 프로그램 작성 된 있는지는 [그리기](../../mfc/reference/coleclientitem-class.md#draw) 멤버 함수는 해당 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 개체입니다. 기본 구현은 없습니다. 에 지정 된 장치 컨텍스트의 항목을 그릴이 함수를 재정의 해야 합니다.  
  
##  <a name="ondrawex"></a>COleServerItem::OnDrawEx  
 모든 그리기 위한 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnDrawEx(
    CDC* pDC,  
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 에 대 한 포인터는 [CDC](../../mfc/reference/cdc-class.md) 개체 항목을 그리는입니다. DC는 자동으로 연결 특성 DC에 되므로 특성 함수를 호출할 수 있지만 이렇게 하면 지금 하 게 만드는 메타 파일 장치 전용입니다.  
  
 `nDrawAspect`  
 `DVASPECT` 열거형의 값입니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.  
  
- `DVASPECT_CONTENT`항목은 해당 컨테이너 내에 포함 된 개체로 표시 될 수 하는 방식으로 표시 됩니다.  
  
- `DVASPECT_THUMBNAIL`검색 도구에 표시 될 수 있도록 "미리" 표현에서 항목이 렌더링 됩니다.  
  
- `DVASPECT_ICON`항목은 아이콘으로 표시 됩니다.  
  
- `DVASPECT_DOCPRINT`항목 파일 메뉴에서 인쇄 명령을 사용 하 여 인쇄할 때 처럼 표시 됩니다.  
  
 `rSize`  
 에 있는 항목의 크기 **HIMETRIC** 단위입니다.  
  
### <a name="return-value"></a>반환 값  
 항목이 성공적으로 그린; 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 기본 구현 호출 `OnDraw` 때 `DVASPECT` 같으면 `DVASPECT_CONTENT`; 그렇지 않으면 요청이 실패 합니다.  
  
 이 함수 이외의 다른 측면에 대 한 프레젠테이션 데이터를 제공 하도록 재정의 `DVASPECT_CONTENT`와 같은 `DVASPECT_ICON` 또는 `DVASPECT_THUMBNAIL`합니다.  
  
##  <a name="ongetclipboarddata"></a>COleServerItem::OnGetClipboardData  
 가져오려는 프레임 워크에서 호출을 `COleDataSource` 개체를 호출 하 여 클립보드에 배치 하는 모든 데이터를 포함 하는 [CopyToClipboard](#copytoclipboard) 멤버 함수입니다.  
  
```  
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,  
    LPPOINT lpOffset,  
    LPSIZE lpSize);
```  
  
### <a name="parameters"></a>매개 변수  
 `bIncludeLink`  
 이 속성을 설정 **TRUE** 링크 데이터를 클립보드에 복사할 경우. 이 속성을 설정 **FALSE** 서버 응용 프로그램이 링크를 지원 하지 않는 경우.  
  
 `lpOffset`  
 픽셀 단위로 개체의 원점부터 마우스 커서의 오프셋입니다.  
  
 `lpSize`  
 픽셀 단위로 개체의 크기입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [COleDataSource](../../mfc/reference/coledatasource-class.md) 클립보드 데이터를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현을 호출 [GetClipboardData](#getclipboarddata)합니다.  
  
##  <a name="ongetextent"></a>COleServerItem::OnGetExtent  
 에 크기를 검색 하기 위해 프레임 워크에서 호출 **HIMETRIC** OLE 항목의 단위입니다.  
  
```  
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>매개 변수  
 `nDrawAspect`  
 검색할 수 있는 경계는 해당 OLE 항목의 모양을 지정 합니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.  
  
- `DVASPECT_CONTENT`항목은 해당 컨테이너 내에 포함 된 개체로 표시 될 수 하는 방식으로 표시 됩니다.  
  
- `DVASPECT_THUMBNAIL`검색 도구에 표시 될 수 있도록 "미리" 표현에서 항목이 렌더링 됩니다.  
  
- `DVASPECT_ICON`항목은 아이콘으로 표시 됩니다.  
  
- `DVASPECT_DOCPRINT`항목 파일 메뉴에서 인쇄 명령을 사용 하 여 인쇄할 때 처럼 표시 됩니다.  
  
 `rSize`  
 에 대 한 참조는 `CSize` OLE 항목의 크기를 받게 될 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 Microsoft Foundation Class 라이브러리 사용 하는 컨테이너 응용 프로그램을 작성 하는 경우이 함수는 호출 될 때는 [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent) 멤버 함수는 해당 `COleClientItem` 개체를 호출 합니다. 기본 구현은 아무 작업도 수행하지 않습니다. 사용자가 직접를 그 구현 해야 합니다. OLE 항목의 크기에 대 한 요청을 처리할 때 특수 한 처리를 수행 하려는 경우이 함수를 재정의 합니다.  
  
##  <a name="onhide"></a>COleServerItem::OnHide  
 OLE 항목을 숨기기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>설명  
 기본 호출 **COleServerDoc::OnShowDocument (FALSE)**합니다. 또한 함수 OLE 항목은 숨겨진 컨테이너 알립니다. OLE 항목을 숨길 때 특수 한 처리를 수행 하려는 경우이 함수를 재정의 합니다.  
  
##  <a name="oninitfromdata"></a>COleServerItem::OnInitFromData  
 내용을 사용 하 여 OLE 항목을 초기화 하기 위해 프레임 워크에서 호출 `pDataObject`합니다.  
  
```  
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,  
    BOOL bCreation);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDataObject`  
 OLE 항목을 초기화 하기 위한 다양 한 형식의 데이터를 포함 하는 OLE 데이터 개체에 대 한 포인터입니다.  
  
 `bCreation`  
 **True 이면** 컨테이너 응용 프로그램에서 새롭게 작성 되 고 OLE 항목을 초기화 하는 함수가 호출 됩니다. **FALSE** 이미 기존 OLE 항목의 내용을 대체 하는 함수가 호출 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 경우 `bCreation` 은 **TRUE**, 컨테이너 현재 선택을 기반으로 새 개체 삽입을 구현 하는 경우이 함수를 호출 합니다. 선택한 데이터는 새 OLE 항목을 만들 때 사용 됩니다. 예를 들어 때 스프레드시트 프로그램에서 셀 범위를 선택 하 고 다음 삽입할 새 개체를 사용 하 여 차트를 만드는 값에 따라 선택한 범위에 있습니다. 기본 구현은 아무 작업도 수행하지 않습니다. 제공 하는 것에서 허용 되는 형식이 선택 하려면이 함수를 재정의 `pDataObject` 제공 되는 데이터에 따라 OLE 항목을 초기화 합니다. 고급 재정의할 수 있습니다.  
  
 자세한 내용은 참조 [IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510) Windows sdk에서입니다.  
  
##  <a name="onopen"></a>COleServerItem::OnOpen  
 서버 응용 프로그램의 개별 인스턴스가 아닌 내부 OLE 항목을 표시 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnOpen();
```  
  
### <a name="remarks"></a>설명  
 기본 구현은 활성화; OLE 항목을 포함 하는 문서를 표시 하는 첫 번째 프레임 창 미니 서버 응용 프로그램을 사용 하는 경우 기본 구현에는 주 창을 보여 줍니다. 또한 함수 OLE 항목 열렸음을 컨테이너 알립니다.  
  
 OLE 항목을 열 때 특수 한 처리를 수행 하려는 경우이 함수를 재정의 합니다. 이 특히 자주 열릴 때 링크를 선택 영역을 설정 하려면 연결 된 항목입니다.  
  
 자세한 내용은 참조 [IOleClientSite::OnShowWindow](http://msdn.microsoft.com/library/windows/desktop/ms688658) Windows sdk에서입니다.  
  
##  <a name="onqueryupdateitems"></a>COleServerItem::OnQueryUpdateItems  
 현재 서버 문서에 연결된 된 항목이 만료 되는지 여부를 확인 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnQueryUpdateItems();
```  
  
### <a name="return-value"></a>반환 값  
 문서에 필요한 업데이트; 항목에는 0이 아닌 모든 항목은 최신 경우 0입니다.  
  
### <a name="remarks"></a>설명  
 원본 문서 변경 되었지만 연결된 된 항목은 문서의 변경 내용을 반영 하도록 업데이트 되지 않은 경우 항목이 최신이 아닙니다.  
  
##  <a name="onrenderdata"></a>COleServerItem::OnRenderData  
 지정 된 형식의 데이터를 검색 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 정보가 요청 된 형식을 지정 하는 구조입니다.  
  
 `lpStgMedium`  
 가리키는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 반환 될 데이터는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 지정 된 형식에 이전에 배치 이란는 `COleDataSource` 를 사용 하 여 개체는 [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) 또는 [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) 지연 된 렌더링 하기 위한 멤버 함수입니다. 이 함수의 기본 구현을 호출 [OnRenderFileData](#onrenderfiledata) 또는 [OnRenderGlobalData](#onrenderglobaldata)각각 제공 되는 저장소 미디어로 파일 또는 메모리 경우. 이러한 형식 중 아무것도 지정 하지 기본 구현에서는 0을 반환 하 고 아무 작업도 수행 합니다.  
  
 경우 `lpStgMedium` ->  *tymed* 은 **TYMED_NULL**, **STGMEDIUM** 할당는 및에 지정 된 대로 채워진 *lpFormatEtc-> tymed*합니다. 그렇지 않은 경우 **TYMED_NULL**, **STGMEDIUM** 데이터와 함께에서 채워야 합니다.  
  
 고급 재정의할 수 있습니다. 요청 된 형식 및 중간 규모의 데이터를 제공 하려면이 함수를 재정의 합니다. 데이터에 따라 대신이 함수의 다른 버전 중 하나를 재정의 하는 것이 좋습니다. 데이터가 작고 크기가 고정 되어 있으면 재정의 `OnRenderGlobalData`합니다. 데이터 파일에는 가변 크기의 경우 재정의 `OnRenderFileData`합니다.  
  
 자세한 내용은 참조 [idataobject:: Getdata](http://msdn.microsoft.com/library/windows/desktop/ms678431), [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177), 및 [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) Windows sdk에서입니다.  
  
##  <a name="onrenderfiledata"></a>COleServerItem::OnRenderFileData  
 저장소 미디어로 파일을 때 지정 된 형식의 데이터를 검색 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 정보가 요청 된 형식을 지정 하는 구조입니다.  
  
 `pFile`  
 가리키는 `CFile` 데이터 렌더링 해야 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 지정 된 형식에 이전에 배치 이란는 `COleDataSource` 를 사용 하 여 개체는 [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) 지연 된 렌더링 하기 위한 멤버 함수입니다. 이 함수의 기본 구현은 단순히 반환 **FALSE**합니다.  
  
 고급 재정의할 수 있습니다. 요청 된 형식 및 중간 규모의 데이터를 제공 하려면이 함수를 재정의 합니다. 데이터에 따라 대신이 함수는 다른 버전 중 하나를 재정의 하는 것이 좋습니다. 여러 저장소 미디어를 처리 하려는 경우 재정의 [OnRenderData](#onrenderdata)합니다. 데이터 파일에는 가변 크기의 경우 재정의 [OnRenderFileData](#onrenderfiledata)합니다.  
  
 자세한 내용은 참조 [idataobject:: Getdata](http://msdn.microsoft.com/library/windows/desktop/ms678431) 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows sdk에서입니다.  
  
##  <a name="onrenderglobaldata"></a>COleServerItem::OnRenderGlobalData  
 지정 된 저장소 미디어로 전역 메모리 때 지정 된 형식의 데이터를 검색 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFormatEtc`  
 가리키는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 정보가 요청 된 형식을 지정 하는 구조입니다.  
  
 `phGlobal`  
 반환 될 데이터는 전역 메모리에 대 한 핸들을 가리킵니다. 이 매개 변수 수 없는 메모리를 할당할 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 지정 된 형식에 이전에 배치 이란는 `COleDataSource` 를 사용 하 여 개체는 [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) 지연 된 렌더링 하기 위한 멤버 함수입니다. 이 함수의 기본 구현은 단순히 반환 **FALSE**합니다.  
  
 경우 `phGlobal` 은 **NULL**, 다음 새 `HGLOBAL` 할당 되 고 반환 해야 `phGlobal`합니다. 그렇지 않은 경우는 `HGLOBAL` 에 지정 된 `phGlobal` 데이터로 채워야 합니다. 데이터의 양을에 배치 된 `HGLOBAL` 메모리 블록의 현재 크기를 넘지 않아야 합니다. 또한, 더 큰 크기로 블록 다시 할당할 수 없습니다.  
  
 고급 재정의할 수 있습니다. 요청 된 형식 및 중간 규모의 데이터를 제공 하려면이 함수를 재정의 합니다. 데이터에 따라 대신이 함수의 다른 버전 중 하나를 재정의 하는 것이 좋습니다. 여러 저장소 미디어를 처리 하려는 경우 재정의 [OnRenderData](#onrenderdata)합니다. 데이터 파일에는 가변 크기의 경우 재정의 [OnRenderFileData](#onrenderfiledata)합니다.  
  
 자세한 내용은 참조 [idataobject:: Getdata](http://msdn.microsoft.com/library/windows/desktop/ms678431) 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows sdk에서입니다.  
  
##  <a name="onsetcolorscheme"></a>COleServerItem::OnSetColorScheme  
 OLE 항목을 편집할 때 사용할 색상표를 지정 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpLogPalette`  
 Windows에 대 한 포인터 [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 색상표; 사용 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 컨테이너 응용 프로그램에서 Microsoft Foundation Class 라이브러리를 사용 하 여 작성 된 경우이 함수는 호출 될 때는 [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) 함수는 해당 `COleClientItem` 개체를 호출 합니다. 기본 구현은 반환 **FALSE**합니다. 권장된 팔레트를 사용 하려는 경우이 함수를 재정의 합니다. 제안 된 색상표를 사용 하는 서버 응용 프로그램이 않아도 됩니다.  
  
 자세한 내용은 참조 [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) Windows sdk에서입니다.  
  
##  <a name="onsetdata"></a>COleServerItem::OnSetData  
 지정 된 데이터 OLE 항목의 데이터를 대체 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpFormatEtc`  
 에 대 한 포인터는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조 데이터의 형식을 지정 합니다.  
  
 `lpStgMedium`  
 에 대 한 포인터는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 구조에서 멤버의 데이터입니다.  
  
 `bRelease`  
 함수 호출을 완료 한 후 저장 미디어의 소유권을 가진 사용자를 나타냅니다. 호출자에 게 저장 매체를 대신 하 여 할당 된 리소스를 해제 하는 데 담당자 결정 합니다. 호출자에 게가 작업을 설정 하 여 수행 `bRelease`합니다. 경우 `bRelease` 가 0이 아닌 경우 서버 항목 사용을 마칠 때 미디어 해제 소유권을 갖습니다. 때 `bRelease` 은 0, 호출자에 게 소유권을 보유 하 고 서버 항목은 호출 기간 동안에만 저장 매체를 사용할 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 서버 항목은 변경 내용이 데이터를 소유는 성공적으로 가져온 것입니다. 즉, 소유권을 고려 되지 경우 0을 반환 합니다. 데이터 원본 변수를 사용할 경우 소유권에 저장소 매체를 호출 하 여 해제 된 [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) 함수입니다.  
  
 기본 구현은 아무 작업도 수행하지 않습니다. 지정 된 데이터 OLE 항목의 데이터를 대체 하려면이 함수를 재정의 합니다. 고급 재정의할 수 있습니다.  
  
 자세한 내용은 참조 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177), 및 [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) Windows sdk에서입니다.  
  
##  <a name="onsetextent"></a>COleServerItem::OnSetExtent  
 컨테이너 문서에 사용 가능한 공간을 OLE 항목에 지시 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,  
    const CSize& size);
```  
  
### <a name="parameters"></a>매개 변수  
 `nDrawAspect`  
 해당 범위가 지정 된 OLE 항목의 모양을 지정 합니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.  
  
- `DVASPECT_CONTENT`항목은 해당 컨테이너 내에 포함 된 개체로 표시 될 수 하는 방식으로 표시 됩니다.  
  
- `DVASPECT_THUMBNAIL`검색 도구에 표시 될 수 있도록 "미리" 표현에서 항목이 렌더링 됩니다.  
  
- `DVASPECT_ICON`항목은 아이콘으로 표시 됩니다.  
  
- `DVASPECT_DOCPRINT`항목 파일 메뉴에서 인쇄 명령을 사용 하 여 인쇄할 때 처럼 표시 됩니다.  
  
 `size`  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) OLE 항목의 새 크기를 지정 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 Microsoft Foundation Class 라이브러리 사용 하는 컨테이너 응용 프로그램을 작성 하는 경우이 함수는 호출 될 때는 [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent) 멤버 함수는 해당 `COleClientItem` 개체를 호출 합니다. 기본 구현에서는 설정 된 [m_sizeExtent](#m_sizeextent) 멤버 지정된 된 크기를 경우 `nDrawAspect` 은 `DVASPECT_CONTENT`; 그렇지 않으면 0을 반환 합니다. 항목의 크기를 변경 하면 특수 한 처리를 수행 하려면이 함수를 재정의 합니다.  
  
##  <a name="onshow"></a>COleServerItem::OnShow  
 원위치에서 OLE 항목을 표시 하는 서버 응용 프로그램에 지시 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>설명  
 표시할 항목을 필요로 하는 컨테이너 응용 프로그램의 사용자는 항목을 만들거나 편집 같은 한 동사를 실행 하는 경우이 함수는 일반적으로 호출 합니다. 기본 구현에는 내부 활성화를 시도합니다. 실패 하면, 함수 호출의 `OnOpen` OLE 항목을 별도 창에 표시 하려면 멤버 함수입니다.  
  
 OLE 항목을 표시할 때 특별 한 처리를 수행 하려는 경우이 함수를 재정의 합니다.  
  
##  <a name="onupdate"></a>COleServerItem::OnUpdate  
 항목이 수정 된 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnUpdate(
    COleServerItem* pSender,  
    LPARAM lHint,  
    CObject* pHint,  
    DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSender`  
 문서를 수정 하는 항목에 대 한 포인터입니다. 수 **NULL**합니다.  
  
 `lHint`  
 수정에 대 한 정보를 포함합니다.  
  
 `pHint`  
 수정에 대 한 정보를 저장 하는 개체에 대 한 포인터입니다.  
  
 `nDrawAspect`  
 `DVASPECT` 열거형의 값입니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.  
  
- `DVASPECT_CONTENT`항목은 해당 컨테이너 내에 포함 된 개체로 표시 될 수 하는 방식으로 표시 됩니다.  
  
- `DVASPECT_THUMBNAIL`검색 도구에 표시 될 수 있도록 "미리" 표현에서 항목이 렌더링 됩니다.  
  
- `DVASPECT_ICON`항목은 아이콘으로 표시 됩니다.  
  
- `DVASPECT_DOCPRINT`항목 파일 메뉴에서 인쇄 명령을 사용 하 여 인쇄할 때 처럼 표시 됩니다.  
  
### <a name="remarks"></a>설명  
 기본 구현 호출 [NotifyChanged](#notifychanged)힌트 또는 보낸 사람에 관계 없이, 합니다.  
  
##  <a name="onupdateitems"></a>COleServerItem::OnUpdateItems  
 서버 문서에서 모든 항목을 업데이트 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnUpdateItems();
```  
  
### <a name="remarks"></a>설명  
 기본 구현 호출 [UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink) 모든 `COleClientItem` 문서의 개체입니다.  
  
##  <a name="setitemname"></a>COleServerItem::SetItemName  
 해당 이름을 설정 하는 연결 된 항목을 만들 때이 함수를 호출 합니다.  
  
```  
void SetItemName(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszItemName`  
 항목의 새 이름에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이름은 문서 내에서 고유 해야 합니다. 연결 된 항목을 편집 하는 서버 응용 프로그램 호출 되 면 응용 프로그램에서 항목을 찾습니다.이 이름을 사용 합니다. 포함 된 항목에 대 한이 함수를 호출할 필요가 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 HIERSVR](../../visual-cpp-samples.md)   
 [CDocItem 클래스](../../mfc/reference/cdocitem-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleClientItem 클래스](../../mfc/reference/coleclientitem-class.md)   
 [COleServerDoc 클래스](../../mfc/reference/coleserverdoc-class.md)   
 [COleTemplateServer 클래스](../../mfc/reference/coletemplateserver-class.md)
