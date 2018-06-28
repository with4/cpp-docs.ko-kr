---
title: CMFCToolBarEditBoxButton 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CanBeStretched
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CopyFrom
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetByCmd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContentsAll
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetEditBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetHwnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetInvalidateRect
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::HaveHotBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::IsFlatMode
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::NotifyCommand
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnAddToCustomizePage
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnChangeParentWnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnClick
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnCtlColor
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnGlobalFontsChanged
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnMove
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnShow
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnSize
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnUpdateToolTip
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetFlatMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarEditBoxButton [MFC], CMFCToolBarEditBoxButton
- CMFCToolBarEditBoxButton [MFC], CanBeStretched
- CMFCToolBarEditBoxButton [MFC], CopyFrom
- CMFCToolBarEditBoxButton [MFC], GetByCmd
- CMFCToolBarEditBoxButton [MFC], GetContentsAll
- CMFCToolBarEditBoxButton [MFC], GetContextMenuID
- CMFCToolBarEditBoxButton [MFC], GetEditBorder
- CMFCToolBarEditBoxButton [MFC], GetHwnd
- CMFCToolBarEditBoxButton [MFC], GetInvalidateRect
- CMFCToolBarEditBoxButton [MFC], HaveHotBorder
- CMFCToolBarEditBoxButton [MFC], IsFlatMode
- CMFCToolBarEditBoxButton [MFC], NotifyCommand
- CMFCToolBarEditBoxButton [MFC], OnAddToCustomizePage
- CMFCToolBarEditBoxButton [MFC], OnChangeParentWnd
- CMFCToolBarEditBoxButton [MFC], OnClick
- CMFCToolBarEditBoxButton [MFC], OnCtlColor
- CMFCToolBarEditBoxButton [MFC], OnGlobalFontsChanged
- CMFCToolBarEditBoxButton [MFC], OnMove
- CMFCToolBarEditBoxButton [MFC], OnShow
- CMFCToolBarEditBoxButton [MFC], OnSize
- CMFCToolBarEditBoxButton [MFC], OnUpdateToolTip
- CMFCToolBarEditBoxButton [MFC], SetContextMenuID
- CMFCToolBarEditBoxButton [MFC], SetFlatMode
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0e6c4493239030380ab935d473af48d4107556d4
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041424"
---
# <a name="cmfctoolbareditboxbutton-class"></a>CMFCToolBarEditBoxButton 클래스
편집 컨트롤을 포함 하는 도구 모음 단추 ( [CEdit 클래스](../../mfc/reference/cedit-class.md)).  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCToolBarEditBoxButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton](#cmfctoolbareditboxbutton)|`CMFCToolBarEditBoxButton` 개체를 생성합니다.|  
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CanBeStretched](#canbestretched)|사용자 지정 하는 동안 사용자의 단추를 늘릴 수 있는지 여부를 지정 합니다. (재정의 [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|  
|[CMFCToolBarEditBoxButton::CopyFrom](#copyfrom)|도구 모음 단추 속성은 현재 단추에 복사합니다. (재정의 [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::CreateEdit](#createedit)|단추에 새 편집 컨트롤을 만듭니다.|  
|`CMFCToolBarEditBoxButton::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|[CMFCToolBarEditBoxButton::GetByCmd](#getbycmd)|첫 번째 검색 `CMFCToolBarEditBoxButton` 지정한 명령 id입니다. 응용 프로그램의 개체|  
|[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)|지정 된 명령 id입니다. 있는 첫 번째 편집 상자 도구 모음 컨트롤의 텍스트를 검색 합니다.|  
|[CMFCToolBarEditBoxButton::GetContextMenuID](#getcontextmenuid)|단추와 연결 된 바로 가기 메뉴의 리소스 ID를 검색 합니다.|  
|[CMFCToolBarEditBoxButton::GetEditBorder](#geteditborder)|편집 상자 단추의 편집 부분 경계 사각형을 검색 합니다.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::GetEditBox](#geteditbox)|단추에 포함 된 편집 컨트롤에 대 한 포인터를 반환 합니다.|  
|[CMFCToolBarEditBoxButton::GetHwnd](#gethwnd)|도구 모음 단추와 연결 된 창 핸들을 검색 합니다. (재정의 [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|  
|[CMFCToolBarEditBoxButton::GetInvalidateRect](#getinvalidaterect)|영역 다시 그려야 하는 단추의 클라이언트 영역을 검색 합니다. (재정의 [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect).)|  
|`CMFCToolBarEditBoxButton::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에서는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|  
|[CMFCToolBarEditBoxButton::HaveHotBorder](#havehotborder)|사용자가 단추를 클릭 하는 경우 단추의 테두리 표시 되는지 여부를 결정 합니다. (재정의 [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)|편집 상자 단추 평면 스타일 있는지 확인 합니다.|  
|[CMFCToolBarEditBoxButton::NotifyCommand](#notifycommand)|단추를 처리 하는 지 여부를 지정 된 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 메시지입니다. (재정의 [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|  
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](#onaddtocustomizepage)|단추에 추가 되는 프레임 워크에서 호출 된 **사용자 지정** 대화 상자. (재정의 [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|  
|`CMFCToolBarEditBoxButton::OnCalculateSize`|지정 된 장치 컨텍스트와 도킹 상태에 대 한 단추 크기를 계산 하기 위해 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](#onchangeparentwnd)|새 도구 모음에 단추를 삽입할 때 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarEditBoxButton::OnClick](#onclick)|사용자가 마우스 단추를 클릭할 때 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarEditBoxButton::OnCtlColor](#onctlcolor)|부모 도구 모음에서 WM_CTLCOLOR 메시지를 처리 하는 경우 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|  
|`CMFCToolBarEditBoxButton::OnDraw`|지정 된 스타일 및 옵션을 사용 하 여 단추를 그리기 위해 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|단추를 그리기 위해 프레임 워크에서 호출 된 **명령을** 의 창은 **사용자 지정** 대화 상자. (재정의 [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](#onglobalfontschanged)|전역 글꼴 변경 될 때 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|  
|[CMFCToolBarEditBoxButton::OnMove](#onmove)|부모 도구 모음에서 이동 하면 프레임 워크에서 호출 합니다. (재정의 [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|  
|[CMFCToolBarEditBoxButton::OnShow](#onshow)|프레임 워크에서 때 호출 단추 수 표시 하거나 숨깁니다. (재정의 [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|  
|[CMFCToolBarEditBoxButton::OnSize](#onsize)|부모 도구 모음에서 해당 크기를 변경 합니다. 또는 위치 및 이러한 변경 하면 크기를 변경 하려면 단추가 때 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|  
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](#onupdatetooltip)|부모 도구 모음에서 도구 설명 텍스트를 업데이트 하는 경우 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|  
|`CMFCToolBarEditBoxButton::Serialize`|보관 파일에서이 개체를 읽거나 보관 파일에 씁니다. (재정의 [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|`CMFCToolBarEditBoxButton::SetACCData`|제공 된 정보를 표시 `CAccessibilityData` 도구 모음 단추에서 내게 필요한 옵션 데이터와 개체입니다. (재정의 [CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContents](#setcontents)|단추의 edit 컨트롤의 텍스트를 설정합니다.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)|지정한 명령 ID가 되 고 해당 단추의 편집 컨트롤의 텍스트는 편집 컨트롤 단추를 찾습니다.|  
|[CMFCToolBarEditBoxButton::SetContextMenuID](#setcontextmenuid)|단추와 연결 된 바로 가기 메뉴의 리소스 ID를 지정 합니다.|  
|[CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)|응용 프로그램의 편집 상자 단추의 평면 스타일 모양을 지정합니다.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetStyle](#setstyle)|단추 스타일을 지정합니다. (재정의 [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|  
  
## <a name="remarks"></a>설명  
 편집 상자 단추를 도구 모음을 추가 하려면 다음이 단계를 수행 합니다.  
  
 1. 부모 도구 모음 리소스의 단추에 대한 더미 리소스 ID를 예약합니다.  
  
 2. 생성 된 `CMFCToolBarEditBoxButton` 개체입니다.  
  
 3. AFX_WM_RESETTOOLBAR 메시지를 처리 하는 메시지 처리기에서 더미 단추 새 콤보 상자 단추를 사용 하 여 대체 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)합니다.  
  
 자세한 내용은 참조 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 `CMFCToolBarEditBoxButton` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 예제에서는 지정 하는 사용자 수 단추 사용자 지정 하는 동안 스트레치, 단추를 누를 때 단추의 테두리 표시 되도록 지정, 텍스트 상자 컨트롤의 텍스트를 설정는 응용 프로그램에서 편집 상자 단추의 평면 스타일 모양을 지정 하는 방법을 보여 줍니다. cation, 도구 모음 스타일 편집 상자 컨트롤을 지정 합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 `CMFCToolBarEditBoxButton` 
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtoolbareditboxbutton.h  
  
##  <a name="canbestretched"></a>  CMFCToolBarEditBoxButton::CanBeStretched  
 사용자 지정 하는 동안 사용자의 단추를 늘릴 수 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `TRUE`을 반환합니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 프레임 워크에는 사용자를 사용자 지정 하는 동안 도구 모음 단추를 늘이는 허용 되지 않습니다. 이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) 하 여 사용자가 사용자 지정 하는 동안 편집 상자 도구 모음 단추를 늘릴 수 있도록 합니다.  
  
##  <a name="cmfctoolbareditboxbutton"></a>  CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton  
 생성 된 [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) 개체입니다.  
  
```  
CMFCToolBarEditBoxButton(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=ES_AUTOHSCROLL,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *uiID*  
 컨트롤 ID를 지정 합니다.  
  
 [in] *iImage*  
 도구 모음 이미지의 0부터 시작 인덱스를 지정합니다. 이미지에는 [CMFCToolBarImages 클래스](../../mfc/reference/cmfctoolbarimages-class.md) 개체를 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md) 클래스를 유지 관리 합니다.  
  
 [in] *dwStyle*  
 편집 컨트롤의 스타일을 지정합니다.  
  
 [in] *iWidth*  
 편집 컨트롤의 픽셀에서 너비를 지정합니다.  
  
### <a name="remarks"></a>설명  
 기본 생성자는 다음과 같은 상황에 편집 컨트롤의 스타일을 설정합니다.  
  
 `WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL`  
  
 컨트롤의 기본 너비는 150 픽셀입니다.  
  
##  <a name="copyfrom"></a>  CMFCToolBarEditBoxButton::CopyFrom  
 도구 모음 단추 속성은 현재 단추에 복사합니다.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *src*  
 복사할 소스 단추에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 이 도구 모음 단추를 도구 모음 단추 복사 하려면이 메서드를 호출 합니다. *src* 형식 이어야 합니다 `CMFCToolBarEditBoxButton`합니다.  
  
##  <a name="createedit"></a>  CMFCToolBarEditBoxButton::CreateEdit  
 단추에 새 편집 컨트롤을 만듭니다.  
  
```  
virtual CEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pWndParent*  
 편집 컨트롤의 부모 창을 지정합니다. NULL이 아니어야 합니다.  
  
 [in] *rect*  
 편집 컨트롤의 크기와 위치를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 편집 컨트롤에 대 한 포인터 `NULL` 컨트롤의 생성 및 첨부 파일 실패 합니다.  
  
### <a name="remarks"></a>설명  
 생성할는 `CMFCToolBarEditBoxButton` 두 단계를 수행에서 하는 개체입니다. 먼저 생성자를 호출 하 고 다음 `CreateEdit`, Windows 편집 컨트롤을 만들고에 연결 하는 `CMFCToolBarEditBoxButton` 개체입니다.  
  
##  <a name="getbycmd"></a>  CMFCToolBarEditBoxButton::GetByCmd  
 첫 번째 검색 `CMFCToolBarEditBoxButton` 지정한 명령 id입니다. 응용 프로그램의 개체  
  
```  
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *uiCmd*  
 검색할 단추의 명령 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 `CMFCToolBarEditBoxButton` 지정한 명령 ID가 있는 응용 프로그램의 개체 또는 `NULL` 이러한 개체가 없는 경우.  
  
### <a name="remarks"></a>설명  
 이 공유 유틸리티 메서드는 메서드에서 같은 [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall) 및 [CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall) 첫 번째 편집 상자 도구 모음 텍스트를 가져오거나 설정 하려면 컨트롤을 지정 된 명령 id입니다.  
  
##  <a name="getcontentsall"></a>  CMFCToolBarEditBoxButton::GetContentsAll  
 지정 된 명령 id입니다. 있는 첫 번째 편집 상자 도구 모음 컨트롤의 텍스트를 검색 합니다.  
  
```  
static CString __stdcall GetContentsAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *uiCmd*  
 내용을 검색할 단추의 명령 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 A `CString` 있는 지정 된 명령 id입니다. 첫 번째 편집 상자 도구 모음 컨트롤의 텍스트가 포함 된 개체  
  
### <a name="remarks"></a>설명  
 이 이렇게 하지 않으면 빈 문자열을 반환 `CMFCToolBarEditBoxButton` 개체는 지정한 명령 id입니다.  
  
##  <a name="getcontextmenuid"></a>  CMFCToolBarEditBoxButton::GetContextMenuID  
 단추와 연결 된 바로 가기 메뉴의 리소스 ID를 검색 합니다.  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>반환 값  
 단추에 연결 된 바로 가기 메뉴가 경우 0 또는 단추와 연결 된 바로 가기 메뉴의 리소스 ID입니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크 리소스 ID를 사용 하 여 단추 마우스 바로 가기 메뉴를 만듭니다.  
  
##  <a name="geteditborder"></a>  CMFCToolBarEditBoxButton::GetEditBorder  
 편집 상자 단추의 편집 부분 경계 사각형을 검색 합니다.  
  
```  
virtual void GetEditBorder(CRect& rectBorder);
```  
  
### <a name="parameters"></a>매개 변수  
 [out] *rectBorder*  
 에 대 한 참조는 `CRect` 경계 사각형을 받는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 클라이언트 좌표로 편집 컨트롤의 경계 사각형을 검색합니다. 1 픽셀씩 각 방향에는 사각형의 크기를 확장합니다.  
  
 [CMFCVisualManager::OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) 주위에 테두리를 그릴 때이 메서드를 호출 메서드는 `CMFCToolBarEditBoxButton` 개체입니다.  
  
##  <a name="geteditbox"></a>  CMFCToolBarEditBoxButton::GetEditBox  
 에 대 한 포인터를 반환 합니다.는 [CEdit 클래스](../../mfc/reference/cedit-class.md) 단추에 포함 된 컨트롤입니다.  
  
```  
CEdit* GetEditBox() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CEdit 클래스](../../mfc/reference/cedit-class.md) 단추가 포함 된 컨트롤입니다. `NULL` 경우는 `CEdit` 컨트롤 아직 생성 되지 않은 합니다.  
  
### <a name="remarks"></a>설명  
 만들는 `CEdit` 호출 하 여 컨트롤 [CMFCToolBarEditBoxButton::CreateEdit](#createedit)합니다.  
  
##  <a name="gethwnd"></a>  CMFCToolBarEditBoxButton::GetHwnd  
 도구 모음 단추와 연결 된 창 핸들을 검색 합니다.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>반환 값  
 단추와 연결 된 창 핸들입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 재정의 [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) 편집 상자 단추 편집 컨트롤 파트의 창 핸들을 반환 하 여 메서드.  
  
##  <a name="getinvalidaterect"></a>  CMFCToolBarEditBoxButton::GetInvalidateRect  
 영역 다시 그려야 하는 단추의 클라이언트 영역을 검색 합니다.  
  
```  
virtual const CRect GetInvalidateRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `CRect` 다시 그려야 하는 지역을 지정 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드가 기본 클래스 구현을 확장 [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect), 텍스트 레이블 영역 지역에 포함 하 여 합니다.  
  
##  <a name="havehotborder"></a>  CMFCToolBarEditBoxButton::HaveHotBorder  
 사용자가 단추를 클릭 하는 경우 단추의 테두리 표시 되는지 여부를 결정 합니다.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>반환 값  
 단추를 선택 하는 경우의 테두리를 표시 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드가 기본 클래스 구현을 확장 [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder), 컨트롤이 표시 되는 경우 0이 아닌 값을 반환 합니다.  
  
##  <a name="isflatmode"></a>  CMFCToolBarEditBoxButton::IsFlatMode  
 편집 상자 단추 평면 스타일 있는지 확인 합니다.  
  
```  
static BOOL __stdcall IsFlatMode();
```  
  
### <a name="return-value"></a>반환 값  
 단추 평면 스타일; 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 편집 상자 단추 평면 스타일을 적용 합니다. 사용 하 여는 [CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode) 응용 프로그램에 대 한 평면 스타일 모양을 변경 하는 메서드.  
  
##  <a name="notifycommand"></a>  CMFCToolBarEditBoxButton::NotifyCommand  
 단추를 처리 하는 지 여부를 지정 된 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 메시지입니다.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *iNotifyCode*  
 명령과 사용 하 여 연결 된 알림 메시지입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 단추 WM_COMMAND 메시지를 처리 하는 경우 또는 `FALSE` 를 나타내는 부모 도구 모음에서 메시지를 처리할 수 있어야 합니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크를 보낼 때이 메서드를 호출는 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 메시지를 부모 창입니다.  
  
 이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) 처리 하 여는 [EN_UPDATE](http://msdn.microsoft.com/library/windows/desktop/bb761687) 알림입니다. 이 개체와 동일한 명령 ID 가진 각 편집 상자에 대 한이 개체의 텍스트 레이블을에 텍스트 레이블을 설정합니다.  
  
##  <a name="onaddtocustomizepage"></a>  CMFCToolBarEditBoxButton::OnAddToCustomizePage  
 단추에 추가 되는 프레임 워크에서 호출 된 **사용자 지정** 대화 상자.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage))이이 개체와 같은 명령 ID가 있는 모든 도구 모음에서 편집 상자 컨트롤에서 속성을 복사 하 여 합니다. 없는 도구 모음에 있는이 개체와 같은 명령 ID는 편집 상자 컨트롤 하는 경우이 메서드는 아무 작업도 수행 합니다.  
  
 에 대 한 자세한 내용은 **사용자 지정** 대화 상자, 참조 [CMFCToolBarsCustomizeDialog 클래스](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)합니다.  
  
##  <a name="onchangeparentwnd"></a>  CMFCToolBarEditBoxButton::OnChangeParentWnd  
 새 도구 모음에 단추를 삽입할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pWndParent*  
 새 부모 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 재정의 ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) 내부 다시 만들어 `CEdit` 개체입니다.  
  
##  <a name="onclick"></a>  CMFCToolBarEditBoxButton::OnClick  
 사용자가 마우스 단추를 클릭할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pWnd*  
 사용되지 않습니다.  
  
 [in] *bDelay*  
 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 단추 클릭 하 여 메시지를 처리 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 재정의 ( [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)) 하는 경우 0이 아닌 값을 반환 하 여 내부 `CEdit` 개체가 표시 됩니다.  
  
##  <a name="onctlcolor"></a>  CMFCToolBarEditBoxButton::OnCtlColor  
 부모 도구 모음에서 WM_CTLCOLOR 메시지를 처리 하는 경우 프레임 워크에서 호출 됩니다.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pDC*  
 단추를 표시 하는 장치 컨텍스트.  
  
 [in] *nCtlColor*  
 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 전역 창 브러시에 사용 되는 핸들입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 재정의 ( [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)) 전체 텍스트 및 배경색을 하는 텍스트 색과 배경색의 제공 된 장치 컨텍스트를 각각 설정 하 여 합니다.  
  
 응용 프로그램에 사용할 수 있는 전역 옵션에 대 한 자세한 내용은 참조 [AFX_GLOBAL_DATA 구조체](../../mfc/reference/afx-global-data-structure.md)합니다.  
  
##  <a name="onglobalfontschanged"></a>  CMFCToolBarEditBoxButton::OnGlobalFontsChanged  
 전역 글꼴 변경 될 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) 글로벌 글꼴의 컨트롤의 글꼴을 변경 하 여 합니다.  
  
 응용 프로그램에 사용할 수 있는 전역 옵션에 대 한 자세한 내용은 참조 [AFX_GLOBAL_DATA 구조체](../../mfc/reference/afx-global-data-structure.md)합니다.  
  
##  <a name="onmove"></a>  CMFCToolBarEditBoxButton::OnMove  
 부모 도구 모음에서 이동 하면 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 재정의 ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove))의 내부 위치를 업데이트 하 여 `CEdit` 개체  
  
##  <a name="onshow"></a>  CMFCToolBarEditBoxButton::OnShow  
 프레임 워크에서 때 호출 단추 수 표시 하거나 숨깁니다.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *bShow*  
 단추가 표시 되는지 여부를 지정 합니다. 이 매개 변수가 `TRUE`, 단추가 표시 됩니다. 그렇지 않으면 단추가 표시 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) 하는 경우에 단추를 표시 하 여 *bShow* 은 `TRUE`합니다. 그렇지 않으면이 메서드는 단추를 숨깁니다.  
  
##  <a name="onsize"></a>  CMFCToolBarEditBoxButton::OnSize  
 부모 도구 모음에서 해당 크기를 변경 합니다. 또는 위치 및 이러한 변경 하면 크기를 변경 하려면 단추가 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *iSize*  
 새 너비 (픽셀)에서 단추입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 재정의 [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize), 크기 및 위치는 내부 업데이트 하 여 `CEdit` 개체입니다.  
  
##  <a name="onupdatetooltip"></a>  CMFCToolBarEditBoxButton::OnUpdateToolTip  
 부모 도구 모음에서 도구 설명 텍스트를 업데이트 하는 경우 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pWndParent*  
 사용되지 않습니다.  
  
 [in] *iButtonIndex*  
 사용되지 않습니다.  
  
 [in] *wndToolTip*  
 도구 설명 텍스트를 표시 하는 컨트롤입니다.  
  
 [out] *str*  
 A `CString` 업데이트 된 도구 설명 텍스트를 받는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 도구 설명 텍스트; 업데이트 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) 단추의 편집 부분에 연관 된 도구 설명 텍스트를 표시 하 여 합니다. 경우 내부 `CEdit` 개체가 `NULL` 또는의 창 핸들은 `CEdit` 개체가 기존 창 식별 하지 않습니다,이 메서드는 아무 작업도 수행 하 고 반환 `FALSE`합니다.  
  
##  <a name="setcontents"></a>  CMFCToolBarEditBoxButton::SetContents  
 텍스트 상자 컨트롤에서 텍스트를 설정 합니다.  
  
```  
virtual void SetContents(const CString& sContents);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *sContents*  
 설정할 새 텍스트를 지정 합니다.  
  
##  <a name="setcontentsall"></a>  CMFCToolBarEditBoxButton::SetContentsAll  
 발견 한 [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) 가지고 있는 개체 ID를 지정 된 명령을 해당 텍스트 상자에 지정된 된 텍스트를 설정 합니다.  
  
```  
static BOOL SetContentsAll(
    UINT uiCmd,  
    const CString& strContents);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *uiCmd*  
 텍스트를 변경할 수는 컨트롤의 명령 ID를 지정 합니다.  
  
 [in] *strContents*  
 설정할 새 텍스트를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 텍스트 설정 되었으면 0이 아닌 인 경우 0은 `CMFCToolBarEditBoxButton` 지정한 명령 ID 가진 컨트롤 존재 하지 않습니다.  
  
##  <a name="setcontextmenuid"></a>  CMFCToolBarEditBoxButton::SetContextMenuID  
 단추와 연결 된 바로 가기 메뉴의 리소스 ID를 지정 합니다.  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *uiCmd*  
 바로 가기 메뉴의 리소스 ID입니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크 리소스 ID를 사용 하 여 도구 모음 단추를 클릭할 때 바로 가기 메뉴를 만듭니다.  
  
##  <a name="setflatmode"></a>  CMFCToolBarEditBoxButton::SetFlatMode  
 응용 프로그램의 편집 상자 단추의 평면 스타일 모양을 지정합니다.  
  
```  
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *bFlat*  
 편집 상자 단추에 대 한 기본 스타일입니다. 이 매개 변수가 `TRUE`, 평면 스타일 모양을 사용할 수 있습니다; 그렇지 않으면 평면 스타일 모양을 사용 불가능 합니다.  
  
### <a name="remarks"></a>설명  
 편집 상자 단추에 대 한 기본 플랫 스타일은 `TRUE`합니다. 사용 하 여는 [CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode) 평면 스타일 모양을 응용 프로그램에 대 한를 검색 하는 메서드입니다.  
  
##  <a name="setstyle"></a>  CMFCToolBarEditBoxButton::SetStyle  
 도구 모음 스타일 편집 상자 컨트롤을 지정 합니다.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *nStyle*  
 설정할 새 스타일입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 설정 [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) 를 *nStyle* 응용 프로그램 사용자 지정 모드에는 응용 프로그램에 사용자 지정 모드 (참조 없을때사용하도록설정하는경우텍스트상자비활성화[ CMFCToolBar::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) 및 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)). 참조 [ToolBar 컨트롤 스타일](../../mfc/reference/toolbar-control-styles.md) 유효한 스타일 플래그 목록은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CEdit 클래스](../../mfc/reference/cedit-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)



