---
title: "COleDocument 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDocument
- AFXOLE/COleDocument
- AFXOLE/COleDocument::COleDocument
- AFXOLE/COleDocument::AddItem
- AFXOLE/COleDocument::ApplyPrintDevice
- AFXOLE/COleDocument::EnableCompoundFile
- AFXOLE/COleDocument::GetInPlaceActiveItem
- AFXOLE/COleDocument::GetNextClientItem
- AFXOLE/COleDocument::GetNextItem
- AFXOLE/COleDocument::GetNextServerItem
- AFXOLE/COleDocument::GetPrimarySelectedItem
- AFXOLE/COleDocument::GetStartPosition
- AFXOLE/COleDocument::HasBlankItems
- AFXOLE/COleDocument::OnShowViews
- AFXOLE/COleDocument::RemoveItem
- AFXOLE/COleDocument::UpdateModifiedFlag
- AFXOLE/COleDocument::OnEditChangeIcon
- AFXOLE/COleDocument::OnEditConvert
- AFXOLE/COleDocument::OnEditLinks
- AFXOLE/COleDocument::OnFileSendMail
- AFXOLE/COleDocument::OnUpdateEditChangeIcon
- AFXOLE/COleDocument::OnUpdateEditLinksMenu
- AFXOLE/COleDocument::OnUpdateObjectVerbMenu
- AFXOLE/COleDocument::OnUpdatePasteLinkMenu
- AFXOLE/COleDocument::OnUpdatePasteMenu
dev_langs:
- C++
helpviewer_keywords:
- COleDocument class
- OLE documents, base class
- OLE containers, client items
- visual editing, OLE document base class
- OLE documents
- documents, OLE
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
caps.latest.revision: 23
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
ms.openlocfilehash: 73bd1bc5c2c93e180b42a79cf23ab98360887c31
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="coledocument-class"></a>COleDocument 클래스
비주얼 편집을 지원하는 OLE 문서에 대한 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleDocument : public CDocument  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleDocument::COleDocument](#coledocument)|`COleDocument` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleDocument::AddItem](#additem)|문서에서 유지 관리 하는 항목의 목록에 항목을 추가 합니다.|  
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|문서에서 모든 클라이언트 항목에 대 한 대상 인쇄 장치를 설정합니다.|  
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|OLE 구조적 저장소 파일 형식을 사용 하 여 저장할 문서를 하면 됩니다.|  
|[COleDocument::GetInPlaceActiveItem](#getinplaceactiveitem)|현재 위치에서 활성화 된 OLE 항목을 반환 합니다.|  
|[COleDocument::GetNextClientItem](#getnextclientitem)|반복 하는 데는 다음 클라이언트 항목을 가져옵니다.|  
|[COleDocument::GetNextItem](#getnextitem)|반복 하는 데는 다음 문서 항목을 가져옵니다.|  
|[COleDocument::GetNextServerItem](#getnextserveritem)|반복에 대 한 다음 서버 항목을 가져옵니다.|  
|[COleDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|문서에서 기본 선택 된 OLE 항목을 반환합니다.|  
|[COleDocument::GetStartPosition](#getstartposition)|반복을 시작 하는 초기 위치를 가져옵니다.|  
|[COleDocument::HasBlankItems](#hasblankitems)|문서에 빈 항목을 확인 합니다.|  
|[COleDocument::OnShowViews](#onshowviews)|표시 되거나 숨겨지도록 문서 상태가 될 때 호출 됩니다.|  
|[COleDocument::RemoveItem](#removeitem)|문서에서 유지 관리 하는 항목의 목록에서 항목을 제거 합니다.|  
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|포함 된 OLE 항목을 수정한 경우 수정 된 문서를 표시 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleDocument::OnEditChangeIcon](#oneditchangeicon)|아이콘 변경 메뉴 명령에 이벤트를 처리합니다.|  
|[COleDocument::OnEditConvert](#oneditconvert)|다른 한 형식에서 포함 또는 연결 된 개체의 변환을 처리 합니다.|  
|[COleDocument::OnEditLinks](#oneditlinks)|편집 메뉴에서 링크 명령에 이벤트를 처리합니다.|  
|[COleDocument::OnFileSendMail](#onfilesendmail)|연결 된 문서와 메일 메시지를 보냅니다.|  
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|편집/변경 아이콘 메뉴 옵션에 대 한 명령 UI 업데이트 하기 위한 프레임 워크에 의해 호출 됩니다.|  
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|편집/링크 메뉴 옵션에 대 한 명령 UI 업데이트 하기 위한 프레임 워크에 의해 호출 됩니다.|  
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|편집에 대 한 명령 UI를 업데이트 하기 위한 프레임 워크에서 호출 / *ObjectName* 메뉴 옵션 및 편집에서 액세스 하는 동사 하위 메뉴 / *ObjectName*합니다.|  
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|붙여넣기 메뉴 옵션에 대 한 명령 UI 업데이트 하기 위한 프레임 워크에 의해 호출 됩니다.|  
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|붙여넣기 메뉴 옵션에 대 한 명령 UI 업데이트 하기 위한 프레임 워크에 의해 호출 됩니다.|  
  
## <a name="remarks"></a>주의  
 `COleDocument`파생 된 **CDocument**, Microsoft Foundation 클래스 라이브러리에서 제공 하는 문서/뷰 아키텍처를 사용 하 여 OLE 응용 프로그램 수 있습니다.  
  
 `COleDocument`컬렉션으로 문서를 처리 [CDocItem](../../mfc/reference/cdocitem-class.md) OLE 항목을 처리 하는 개체입니다. 컨테이너와 서버 응용 프로그램 문서 OLE 항목을 포함 하는 일을 할 수 있어야 하기 때문에 플러그형 아키텍처에 필요 합니다. [COleServerItem](../../mfc/reference/coleserveritem-class.md) 및 [활성화](../../mfc/reference/coleclientitem-class.md) 클래스에서 파생 된 모두 `CDocItem`, 응용 프로그램 및 OLE 항목 간의 상호 작용을 관리 합니다.  
  
 간단한 컨테이너 응용 프로그램을 작성 하는 경우 문서에서 파생 `COleDocument`합니다. 지 원하는 해당 문서에 포함 된 포함된 된 항목에 연결 하는 컨테이너 응용 프로그램을 작성 하는 경우 문서에서 파생 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)합니다. 를 작성 하는 서버 응용 프로그램 또는 조합 컨테이너/서버에서 문서 클래스 파생 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)합니다. `COleLinkingDoc`및 `COleServerDoc` 에서 파생 된 `COleDocument`이러한 클래스에서 사용할 수 있는 모든 서비스를 상속 하므로 `COleDocument` 및 **CDocument**합니다.  
  
 사용 하 여 `COleDocument`에서 클래스를 파생 하 고 응용 프로그램의 비 OLE 데이터 뿐만 아니라 포함 또는 연결 된 항목을 관리 하는 기능을 추가 합니다. 정의 하는 경우 `CDocItem`-응용 프로그램의 네이티브 데이터를 저장 하기 위해 파생 클래스에 정의 된 기본 구현을 사용할 수 있습니다 `COleDocument` OLE 및 비 OLE 데이터 모두 저장할 수 있습니다. OLE 항목에서 별도로 비 OLE 데이터를 저장 하기 위한 고유한 데이터 구조를 디자인할 수 있습니다. 자세한 내용은 문서를 참조 하십시오. [컨테이너: 복합 파일](../../mfc/containers-compound-files.md)...  
  
 **CDocument** (MAPI) 전자 메일 서비스를 사용할 수 있으면 메일을 통해 문서를 보내는 기능을 지원 합니다. `COleDocument`이 업데이트 [OnFileSendMail](#onfilesendmail) 복합 문서를 올바르게 처리 하도록 합니다. 자세한 내용은 문서를 참조 [MAPI](../../mfc/mapi.md) 및 [MFC의 MAPI 지원](../../mfc/mapi-support-in-mfc.md)...  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `COleDocument`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="additem"></a>COleDocument::AddItem  
 문서에 항목을 추가 하려면이 함수를 호출 합니다.  
  
```  
virtual void AddItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 추가 되는 문서 항목에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 에 의해 호출 되는 경우이 함수를 명시적으로 호출할 필요가 없습니다는 `COleClientItem` 또는 `COleServerItem` 문서에 대 한 포인터를 받는 생성자입니다.  
  
##  <a name="applyprintdevice"></a>COleDocument::ApplyPrintDevice  
 포함 된 모든 인쇄 대상 장치를 변경 하려면이 함수를 호출 [활성화](../../mfc/reference/coleclientitem-class.md) 응용 프로그램의 컨테이너 문서에 있는 항목입니다.  
  
```  
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>매개 변수  
 `ptd`  
 에 대 한 포인터는 **DVTARGETDEVICE** 데이터 구조를 새 대상 인쇄 장치에 대 한 정보를 포함 합니다. 수 **NULL**합니다.  
  
 `ppd`  
 에 대 한 포인터는 **PRINTDLG** 데이터 구조를 새 대상 인쇄 장치에 대 한 정보를 포함 합니다. 수 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 모든 항목에 대 한 대상 인쇄 장치를 업데이트 하지만 이러한 항목에 대 한 프레젠테이션 캐시를 새로 고치지 않습니다. 항목에 대 한 프레젠테이션 캐시를 업데이트 하려면 호출 [COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink)합니다.  
  
 이 함수에 대 한 인수 OLE 사용 하 여 대상 장치를 식별 하는 정보를 포함 합니다. [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) 구조 Windows에서 공통 인쇄 대화 상자를 초기화 하는 정보를 포함 합니다. 사용자는 대화 상자를 닫은 후 Windows는이 구조에서 사용자의 선택에 대 한 정보를 반환 합니다. `m_pd` 의 멤버는 [CPrintDialog](../../mfc/reference/cprintdialog-class.md) 개체는 **PRINTDLG** 구조입니다.  
  
 자세한 내용은 참조는 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 자세한 내용은 참조는 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="coledocument"></a>COleDocument::COleDocument  
 `COleDocument` 개체를 생성합니다.  
  
```  
COleDocument();
```  
  
##  <a name="enablecompoundfile"></a>COleDocument::EnableCompoundFile  
 복합 파일 형식을 사용 하 여 문서를 저장 하려는 경우이 함수를 호출 합니다.  
  
```  
void EnableCompoundFile(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bEnable`  
 복합 파일 지원을 사용 되는지 여부를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 구조적된 저장소를 라고도 합니다. 일반적으로의 생성자에서이 함수를 호출 하면 `COleDocument`-클래스를 파생 합니다. 복합 문서에 대 한 자세한 내용은 문서를 참조 하십시오. [컨테이너: 복합 파일](../../mfc/containers-compound-files.md)...  
  
 이 멤버 함수를 호출 하지 않으면 문서 비구조적된 ("평면") 파일 형식으로 저장 됩니다.  
  
 복합 파일 지원을 사용 가능 여부가 문서를 한 후 설정은 문서의 수명 동안 변경할 수 없습니다.  
  
##  <a name="getinplaceactiveitem"></a>COleDocument::GetInPlaceActiveItem  
 항목과 OLE를 가져오려면이 함수를 호출 하 여 식별 된 뷰를 포함 하는 프레임 창에서 위치에 현재 활성화 된 `pWnd`합니다.  
  
```  
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 컨테이너 문서를 표시 하는 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 단일, 내부 활성 OLE 항목;에 대 한 포인터 **NULL** 경우 OLE 항목이 없는 현재 "위치에서 활성" 상태에 있습니다.  
  
##  <a name="getnextclientitem"></a>COleDocument::GetNextClientItem  
 반복 해 서 각 문서에서 클라이언트 항목에 액세스 하려면이 함수를 호출 합니다.  
  
```  
COleClientItem* GetNextClientItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 에 대 한 참조는 **위치** 값이 설정에 대 한 이전 호출에서 `GetNextClientItem`; 반환한 초기 값은 `GetStartPosition` 멤버 함수입니다.  
  
### <a name="return-value"></a>반환 값  
 문서에서 다음 클라이언트 항목에 대 한 포인터 또는 **NULL** 더 많은 클라이언트 항목이 없는 경우.  
  
### <a name="remarks"></a>주의  
 값을 각 호출 후 `pos` 또는 클라이언트 항목이 아닐 수 있습니다 문서에서 다음 항목에 대해 설정 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&1;](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]  
  
##  <a name="getnextitem"></a>COleDocument::GetNextItem  
 반복 해 서 각 문서에 항목에 액세스 하려면이 함수를 호출 합니다.  
  
```  
virtual CDocItem* GetNextItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 에 대 한 참조는 **위치** 값이 설정에 대 한 이전 호출에서 `GetNextItem`; 반환한 초기 값은 `GetStartPosition` 멤버 함수입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 위치에 문서 항목에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 값을 각 호출 후 `pos` 로 설정 되어는 **위치** 문서에 다음 항목의 값입니다. 검색된 된 요소는 문서를 새 값의 마지막 요소 이면 `pos` 는 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&2;](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]  
  
##  <a name="getnextserveritem"></a>COleDocument::GetNextServerItem  
 반복 해 서 각 문서에 서버 항목에 액세스 하려면이 함수를 호출 합니다.  
  
```  
COleServerItem* GetNextServerItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 에 대 한 참조는 **위치** 값이 설정에 대 한 이전 호출에서 `GetNextServerItem`; 반환한 초기 값은 `GetStartPosition` 멤버 함수입니다.  
  
### <a name="return-value"></a>반환 값  
 문서에서 다음 서버 항목에 대 한 포인터 또는 **NULL** 더 많은 서버 항목이 없는 경우.  
  
### <a name="remarks"></a>주의  
 값을 각 호출 후 `pos` 수 있거나 서버 항목을 사용할 수 없는 하는 문서에서 다음 항목에 대해 설정 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleServer #&2;](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]  
  
##  <a name="getprimaryselecteditem"></a>COleDocument::GetPrimarySelectedItem  
 지정된 된 보기에서 현재 선택 된 OLE 항목을 검색 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```  
  
### <a name="parameters"></a>매개 변수  
 `pView`  
 문서를 표시 하는 활성 뷰 개체에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 단일, 선택 된 OLE 항목;에 대 한 포인터 **NULL** 없는 OLE 항목을 선택 하거나 둘 이상의 하나를 선택 합니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 목록 검색 포함 된 OLE 된 단일 항목에 대 한 항목 하 고에 대 한 포인터를 반환 합니다. 옵션을 선택 하는 항목이 없으면 또는 여러 항목 선택, 함수 반환 하는 경우 **NULL**합니다. 재정의 해야는 `CView::IsSelected` 작동 하려면이 함수에 대 한 뷰 클래스에 멤버 함수입니다. 사용자 고유의 방법이 포함 된 OLE 항목을 저장 하는 경우이 함수를 재정의 합니다.  
  
##  <a name="getstartposition"></a>COleDocument::GetStartPosition  
 문서에서 첫 번째 항목의 위치를 가져오려면이 함수를 호출 합니다.  
  
```  
virtual POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **위치** 문서의 항목을 반복 하려면 사용할 수 있는 값 **NULL** 문서에 항목이 없습니다.  
  
### <a name="remarks"></a>주의  
 반환 된 값을 전달 `GetNextItem`, `GetNextClientItem`, 또는 `GetNextServerItem`합니다.  
  
##  <a name="hasblankitems"></a>COleDocument::HasBlankItems  
 문서에 빈 항목이 포함 되어 있는지 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL HasBlankItems() const;  
```  
  
### <a name="return-value"></a>반환 값  
 문서에는 빈 항목이; 포함 되어 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 빈 항목은 비어 있는 사각형은 하나입니다.  
  
##  <a name="oneditchangeicon"></a>COleDocument::OnEditChangeIcon  
 OLE 아이콘 변경 대화 상자를 표시 하 고 사용자가 대화 상자에서 선택 아이콘은 현재 선택 된 OLE 항목을 나타내는 아이콘을 변경 합니다.  
  
```  
afx_msg void OnEditChangeIcon();
```  
  
### <a name="remarks"></a>주의  
 `OnEditChangeIcon`만들고 시작는 `COleChangeIconDialog` 아이콘 변경 대화 상자입니다.  
  
##  <a name="oneditconvert"></a>COleDocument::OnEditConvert  
 OLE 변환 대화 상자를 표시 하 고 변환 하거나 대화 상자에서 사용자 선택에 따라 현재 선택 된 OLE 항목을 활성화 합니다.  
  
```  
afx_msg void OnEditConvert();
```  
  
### <a name="remarks"></a>주의  
 `OnEditConvert`만들고 시작는 `COleConvertDialog` 변환 대화 상자입니다.  
  
 변환의 예로 워드 패드 문서에 Microsoft Word 문서를 변환 합니다.  
  
##  <a name="oneditlinks"></a>COleDocument::OnEditLinks  
 OLE 편집/연결 대화 상자를 표시합니다.  
  
```  
afx_msg void OnEditLinks();
```  
  
### <a name="remarks"></a>주의  
 `OnEditLinks`만들고 시작는 `COleLinksDialog` 연결 대화 상자 사용자가 연결 된 개체를 변경할 수 있도록 합니다.  
  
##  <a name="onfilesendmail"></a>COleDocument::OnFileSendMail  
 상주 메일 호스트를 통해 메시지 (있는 경우) 문서와 첨부 보냅니다.  
  
```  
afx_msg void OnFileSendMail();
```  
  
### <a name="remarks"></a>주의  
 `OnFileSendMail`호출 `OnSaveDocument` (저장) 전자 메일을 통해 전송 되는 임시 파일에 제목 및 수정 된 문서를 serialize 하는 데 있습니다. 문서가 수정 되지 않은 경우 임시 파일 필요 하지 않습니다. 원래 전송 됩니다. `OnFileSendMail`MAPI32를 로드합니다. 아직 로드 되지 않은 경우 DLL입니다.  
  
 구현과 달리 `OnFileSendMail` 에 대 한 **CDocument**,이 함수에서 복합 파일을 올바르게 처리 합니다.  
  
 자세한 내용은 참조는 [MAPI 항목](../../mfc/mapi.md) 및 [MFC의 MAPI 지원](../../mfc/mapi-support-in-mfc.md) 문서...  
  
##  <a name="onshowviews"></a>COleDocument::OnShowViews  
 프레임 워크가이 함수를 호출 후 문서의 표시 여부 상태 변경 합니다.  
  
```  
virtual void OnShowViews(BOOL bVisible);
```  
  
### <a name="parameters"></a>매개 변수  
 `bVisible`  
 문서 표시 되거나 숨겨지도록 있게 되었는지 여부를 나타냅니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 버전은 일어나지 않습니다. 응용 프로그램은 특수 한 처리는 문서 표시 유형을 변경 될 때 수행 해야 하는 경우 재정의 합니다.  
  
##  <a name="onupdateeditchangeicon"></a>COleDocument::OnUpdateEditChangeIcon  
 편집 메뉴에서 변경 아이콘 명령 업데이트 하기 위한 프레임 워크에 의해 호출 됩니다.  
  
```  
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCmdUI`  
 에 대 한 포인터는 `CCmdUI` update 명령을 생성 되는 메뉴를 나타내는 구조입니다. 업데이트 처리기 호출의 **사용** 의 멤버 함수는 `CCmdUI` 통해 구조 `pCmdUI` 사용자 인터페이스를 업데이트 하 합니다.  
  
### <a name="remarks"></a>주의  
 `OnUpdateEditChangeIcon`문서에 올바른 아이콘이 있는지 여부에 따라 명령의 사용자 인터페이스를 업데이트 합니다. 동작을 변경 하려면이 함수를 재정의 합니다.  
  
##  <a name="onupdateeditlinksmenu"></a>COleDocument::OnUpdateEditLinksMenu  
 편집 메뉴에서 링크 명령 업데이트 하기 위한 프레임 워크에 의해 호출 됩니다.  
  
```  
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCmdUI`  
 에 대 한 포인터는 `CCmdUI` update 명령을 생성 되는 메뉴를 나타내는 구조입니다. 업데이트 처리기 호출의 **사용** 의 멤버 함수는 `CCmdUI` 통해 구조 `pCmdUI` 사용자 인터페이스를 업데이트 하 합니다.  
  
### <a name="remarks"></a>주의  
 문서에서 첫 번째 OLE 항목부터 `OnUpdateEditLinksMenu` 항목이 링크 이며, 링크가 있으면 링크 명령을 활성화 여부를 테스트 하 여 각 항목에 액세스 합니다. 동작을 변경 하려면이 함수를 재정의 합니다.  
  
##  <a name="onupdateobjectverbmenu"></a>COleDocument::OnUpdateObjectVerbMenu  
 업데이트 하는 프레임 워크에서 호출는 *ObjectName* 편집 메뉴와에서 액세스 동사 하위 메뉴에서 명령을 *ObjectName* 명령, 여기서 *ObjectName* 문서에는 OLE 개체의 이름을 포함 합니다.  
  
```  
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCmdUI`  
 에 대 한 포인터는 `CCmdUI` update 명령을 생성 되는 메뉴를 나타내는 구조입니다. 업데이트 처리기 호출의 **사용** 의 멤버 함수는 `CCmdUI` 통해 구조 `pCmdUI` 사용자 인터페이스를 업데이트 하 합니다.  
  
### <a name="remarks"></a>주의  
 `OnUpdateObjectVerbMenu`업데이트는 *ObjectName* 문서에 적합 한 개체가 있는지 여부에 따라 명령의 사용자 인터페이스입니다. 개체가 있으면는 *ObjectName* 편집 메뉴에서 명령을 사용할 수 있습니다. 이 메뉴 명령을 선택 하면 동사 하위 메뉴가 표시 됩니다. 동사 하위 메뉴에는 편집, 속성 및 등과 같은 개체에 사용할 수 있는 모든 동사 명령이 포함 되어 있습니다. 동작을 변경 하려면이 함수를 재정의 합니다.  
  
##  <a name="onupdatepastelinkmenu"></a>COleDocument::OnUpdatePasteLinkMenu  
 연결 된 OLE 항목을 클립보드에서 붙여 넣을 수 있는지 여부를 결정 하는 프레임 워크에서 호출 됩니다.  
  
```  
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCmdUI`  
 에 대 한 포인터는 `CCmdUI` update 명령을 생성 되는 메뉴를 나타내는 구조입니다. 업데이트 처리기 호출의 **사용** 의 멤버 함수는 `CCmdUI` 통해 구조 `pCmdUI` 사용자 인터페이스를 업데이트 하 합니다.  
  
### <a name="remarks"></a>주의  
 붙여넣기 메뉴 명령은 사용할지 여부는 항목에 붙여 넣을 수 문서 여부에 따라 합니다.  
  
##  <a name="onupdatepastemenu"></a>COleDocument::OnUpdatePasteMenu  
 포함된 된 OLE 항목 클립보드에서 붙여 넣을 수 있는지 여부를 결정 하는 프레임 워크에서 호출 됩니다.  
  
```  
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCmdUI`  
 에 대 한 포인터는 `CCmdUI` update 명령을 생성 되는 메뉴를 나타내는 구조입니다. 업데이트 처리기 호출의 **사용** 의 멤버 함수는 `CCmdUI` 통해 구조 `pCmdUI` 사용자 인터페이스를 업데이트 하 합니다.  
  
### <a name="remarks"></a>주의  
 붙여넣기 메뉴 명령 및 단추를 사용 하는지 여부는 항목에 붙여 넣을 수 문서 여부에 따라 합니다.  
  
##  <a name="removeitem"></a>COleDocument::RemoveItem  
 문서에서 항목을 제거 하려면이 함수를 호출 합니다.  
  
```  
virtual void RemoveItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 문서 항목을 제거할 수에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 일반적으로 필요가 없습니다; 명시적으로이 함수를 호출 하려면 에 대 한 소멸자에 의해 호출 됩니다 `COleClientItem` 및 `COleServerItem`합니다.  
  
##  <a name="updatemodifiedflag"></a>COleDocument::UpdateModifiedFlag  
 포함 된 OLE 항목을 수정한 경우 수정 된 문서를 표시 하려면이 함수를 호출 합니다.  
  
```  
virtual void UpdateModifiedFlag();
```  
  
### <a name="remarks"></a>주의  
 따라서 프레임 워크에 문서에 네이티브 데이터 수정 되지 않았습니다 하는 경우에 문서를 닫기 전에 저장 하 라는 메시지가 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 컨테이너](../../visual-cpp-samples.md)   
 [MFC 샘플 MFCBIND](../../visual-cpp-samples.md)   
 [CDocument 클래스](../../mfc/reference/cdocument-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




