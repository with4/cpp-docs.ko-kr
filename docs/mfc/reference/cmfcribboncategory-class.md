---
title: CMFCRibbonCategory 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonCategory
- AFXRIBBONCATEGORY/CMFCRibbonCategory
- AFXRIBBONCATEGORY/CMFCRibbonCategory::CMFCRibbonCategory
- AFXRIBBONCATEGORY/CMFCRibbonCategory::AddHidden
- AFXRIBBONCATEGORY/CMFCRibbonCategory::AddPanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::CopyFrom
- AFXRIBBONCATEGORY/CMFCRibbonCategory::FindByData
- AFXRIBBONCATEGORY/CMFCRibbonCategory::FindByID
- AFXRIBBONCATEGORY/CMFCRibbonCategory::FindPanelWithElem
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetContextID
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetData
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetDroppedDown
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetElements
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetElementsByID
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetFirstVisibleElement
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetFocused
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetHighlighted
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetImageCount
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetImageSize
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetItemIDsList
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetLastVisibleElement
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetLargeImages
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetMaxHeight
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetName
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanelCount
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanelFromPoint
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanelIndex
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetParentButton
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetParentMenuBar
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetParentRibbonBar
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetRect
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetSmallImages
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetTabColor
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetTabRect
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetTextTopLine
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetVisibleElements
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HighlightPanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HitTest
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HitTestEx
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HitTestScrollButtons
- AFXRIBBONCATEGORY/CMFCRibbonCategory::IsActive
- AFXRIBBONCATEGORY/CMFCRibbonCategory::IsVisible
- AFXRIBBONCATEGORY/CMFCRibbonCategory::IsWindows7Look
- AFXRIBBONCATEGORY/CMFCRibbonCategory::NotifyControlCommand
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnCancelMode
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnDraw
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnDrawImage
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnDrawMenuBorder
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnKey
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnLButtonDown
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnLButtonUp
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnMouseMove
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnRTLChanged
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnScrollHorz
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnUpdateCmdUI
- AFXRIBBONCATEGORY/CMFCRibbonCategory::RecalcLayout
- AFXRIBBONCATEGORY/CMFCRibbonCategory::RemovePanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::ReposPanels
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetCollapseOrder
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetData
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetKeys
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetName
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetTabColor
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCategory [MFC], CMFCRibbonCategory
- CMFCRibbonCategory [MFC], AddHidden
- CMFCRibbonCategory [MFC], AddPanel
- CMFCRibbonCategory [MFC], CopyFrom
- CMFCRibbonCategory [MFC], FindByData
- CMFCRibbonCategory [MFC], FindByID
- CMFCRibbonCategory [MFC], FindPanelWithElem
- CMFCRibbonCategory [MFC], GetContextID
- CMFCRibbonCategory [MFC], GetData
- CMFCRibbonCategory [MFC], GetDroppedDown
- CMFCRibbonCategory [MFC], GetElements
- CMFCRibbonCategory [MFC], GetElementsByID
- CMFCRibbonCategory [MFC], GetFirstVisibleElement
- CMFCRibbonCategory [MFC], GetFocused
- CMFCRibbonCategory [MFC], GetHighlighted
- CMFCRibbonCategory [MFC], GetImageCount
- CMFCRibbonCategory [MFC], GetImageSize
- CMFCRibbonCategory [MFC], GetItemIDsList
- CMFCRibbonCategory [MFC], GetLastVisibleElement
- CMFCRibbonCategory [MFC], GetLargeImages
- CMFCRibbonCategory [MFC], GetMaxHeight
- CMFCRibbonCategory [MFC], GetName
- CMFCRibbonCategory [MFC], GetPanel
- CMFCRibbonCategory [MFC], GetPanelCount
- CMFCRibbonCategory [MFC], GetPanelFromPoint
- CMFCRibbonCategory [MFC], GetPanelIndex
- CMFCRibbonCategory [MFC], GetParentButton
- CMFCRibbonCategory [MFC], GetParentMenuBar
- CMFCRibbonCategory [MFC], GetParentRibbonBar
- CMFCRibbonCategory [MFC], GetRect
- CMFCRibbonCategory [MFC], GetSmallImages
- CMFCRibbonCategory [MFC], GetTabColor
- CMFCRibbonCategory [MFC], GetTabRect
- CMFCRibbonCategory [MFC], GetTextTopLine
- CMFCRibbonCategory [MFC], GetVisibleElements
- CMFCRibbonCategory [MFC], HighlightPanel
- CMFCRibbonCategory [MFC], HitTest
- CMFCRibbonCategory [MFC], HitTestEx
- CMFCRibbonCategory [MFC], HitTestScrollButtons
- CMFCRibbonCategory [MFC], IsActive
- CMFCRibbonCategory [MFC], IsVisible
- CMFCRibbonCategory [MFC], IsWindows7Look
- CMFCRibbonCategory [MFC], NotifyControlCommand
- CMFCRibbonCategory [MFC], OnCancelMode
- CMFCRibbonCategory [MFC], OnDraw
- CMFCRibbonCategory [MFC], OnDrawImage
- CMFCRibbonCategory [MFC], OnDrawMenuBorder
- CMFCRibbonCategory [MFC], OnKey
- CMFCRibbonCategory [MFC], OnLButtonDown
- CMFCRibbonCategory [MFC], OnLButtonUp
- CMFCRibbonCategory [MFC], OnMouseMove
- CMFCRibbonCategory [MFC], OnRTLChanged
- CMFCRibbonCategory [MFC], OnScrollHorz
- CMFCRibbonCategory [MFC], OnUpdateCmdUI
- CMFCRibbonCategory [MFC], RecalcLayout
- CMFCRibbonCategory [MFC], RemovePanel
- CMFCRibbonCategory [MFC], ReposPanels
- CMFCRibbonCategory [MFC], SetCollapseOrder
- CMFCRibbonCategory [MFC], SetData
- CMFCRibbonCategory [MFC], SetKeys
- CMFCRibbonCategory [MFC], SetName
- CMFCRibbonCategory [MFC], SetTabColor
ms.assetid: 99ba25b6-d060-4fdd-bfab-3c46c22981bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44caf81fd73567e9c206bdfe62869f5fc145fd33
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039109"
---
# <a name="cmfcribboncategory-class"></a>CMFCRibbonCategory 클래스
`CMFCRibbonCategory` 클래스 구현 그룹을 포함 하는 리본 탭 [리본 패널](../../mfc/reference/cmfcribbonpanel-class.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonCategory : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonCategory::CMFCRibbonCategory](#cmfcribboncategory)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonCategory::AddHidden](#addhidden)|리본 범주에는 숨겨진된 요소를 추가합니다.|  
|[CMFCRibbonCategory::AddPanel](#addpanel)|리본 범주를 새 패널을 추가합니다.|  
|[CMFCRibbonCategory::CopyFrom](#copyfrom)||  
|[CMFCRibbonCategory::FindByData](#findbydata)||  
|[CMFCRibbonCategory::FindByID](#findbyid)||  
|[CMFCRibbonCategory::FindPanelWithElem](#findpanelwithelem)||  
|[CMFCRibbonCategory::GetContextID](#getcontextid)|리본 범주의 컨텍스트 ID를 반환합니다.|  
|[CMFCRibbonCategory::GetData](#getdata)|리본 범주와 연결 된 사용자 정의 데이터를 반환 합니다.|  
|[CMFCRibbonCategory::GetDroppedDown](#getdroppeddown)||  
|[CMFCRibbonCategory::GetElements](#getelements)||  
|[CMFCRibbonCategory::GetElementsByID](#getelementsbyid)||  
|[CMFCRibbonCategory::GetFirstVisibleElement](#getfirstvisibleelement)|리본 범주에 속하는 보이는 첫 번째 요소를 가져옵니다.|  
|[CMFCRibbonCategory::GetFocused](#getfocused)|포커스가 지정된 요소를 반환합니다.|  
|[CMFCRibbonCategory::GetHighlighted](#gethighlighted)|강조 표시 된 요소를 반환합니다.|  
|[CMFCRibbonCategory::GetImageCount](#getimagecount)||  
|[CMFCRibbonCategory::GetImageSize](#getimagesize)||  
|[CMFCRibbonCategory::GetItemIDsList](#getitemidslist)||  
|[CMFCRibbonCategory::GetLastVisibleElement](#getlastvisibleelement)|리본 범주에 속하는 보이는 마지막 요소로 가져오려면|  
|[CMFCRibbonCategory::GetLargeImages](#getlargeimages)|리본 범주를 사용 하는 큰 이미지의 목록에 대 한 참조를 반환 합니다.|  
|[CMFCRibbonCategory::GetMaxHeight](#getmaxheight)||  
|[CMFCRibbonCategory::GetName](#getname)||  
|[CMFCRibbonCategory::GetPanel](#getpanel)|지정된 된 인덱스에 있는 리본 패널에 대 한 포인터를 반환 합니다.|  
|[CMFCRibbonCategory::GetPanelCount](#getpanelcount)|리본 범주에 있는 리본 패널 수를 반환합니다.|  
|[CMFCRibbonCategory::GetPanelFromPoint](#getpanelfrompoint)||  
|[CMFCRibbonCategory::GetPanelIndex](#getpanelindex)|지정 된 리본 패널의 인덱스를 반환합니다.|  
|[CMFCRibbonCategory::GetParentButton](#getparentbutton)||  
|[CMFCRibbonCategory::GetParentMenuBar](#getparentmenubar)||  
|[CMFCRibbonCategory::GetParentRibbonBar](#getparentribbonbar)||  
|[CMFCRibbonCategory::GetRect](#getrect)||  
|[CMFCRibbonCategory::GetSmallImages](#getsmallimages)|범주를 사용 하는 작은 이미지 목록에 대 한 참조를 반환 합니다.|  
|[CMFCRibbonCategory::GetTabColor](#gettabcolor)|리본 범주 탭에 현재 색을 반환합니다.|  
|[CMFCRibbonCategory::GetTabRect](#gettabrect)||  
|[CMFCRibbonCategory::GetTextTopLine](#gettexttopline)||  
|[CMFCRibbonCategory::GetVisibleElements](#getvisibleelements)|리본 범주에 속하는 모든 요소를 가져옵니다.|  
|[CMFCRibbonCategory::HighlightPanel](#highlightpanel)||  
|[CMFCRibbonCategory::HitTest](#hittest)||  
|[CMFCRibbonCategory::HitTestEx](#hittestex)||  
|[CMFCRibbonCategory::HitTestScrollButtons](#hittestscrollbuttons)||  
|[CMFCRibbonCategory::IsActive](#isactive)||  
|[CMFCRibbonCategory::IsVisible](#isvisible)|리본 범주에 표시 되는지 여부를 결정 합니다.|  
|[CMFCRibbonCategory::IsWindows7Look](#iswindows7look)|부모 리본 Windows 7 스타일 모양 (작은 사각형 응용 프로그램 단추)에 있는지 여부를 나타냅니다.|  
|[CMFCRibbonCategory::NotifyControlCommand](#notifycontrolcommand)||  
|[CMFCRibbonCategory::OnCancelMode](#oncancelmode)||  
|[CMFCRibbonCategory::OnDraw](#ondraw)||  
|[CMFCRibbonCategory::OnDrawImage](#ondrawimage)||  
|[CMFCRibbonCategory::OnDrawMenuBorder](#ondrawmenuborder)||  
|[CMFCRibbonCategory::OnKey](#onkey)|사용자가 키보드 단추를 누를 때 프레임 워크에서 호출 됩니다.|  
|[CMFCRibbonCategory::OnLButtonDown](#onlbuttondown)||  
|[CMFCRibbonCategory::OnLButtonUp](#onlbuttonup)||  
|[CMFCRibbonCategory::OnMouseMove](#onmousemove)||  
|[CMFCRibbonCategory::OnRTLChanged](#onrtlchanged)||  
|[CMFCRibbonCategory::OnScrollHorz](#onscrollhorz)||  
|[CMFCRibbonCategory::OnUpdateCmdUI](#onupdatecmdui)||  
|[CMFCRibbonCategory::RecalcLayout](#recalclayout)||  
|[CMFCRibbonCategory::RemovePanel](#removepanel)||  
|[CMFCRibbonCategory::ReposPanels](#repospanels)||  
|[CMFCRibbonCategory::SetCollapseOrder](#setcollapseorder)|리본 범주에 있는 리본 패널 축소 순서를 정의 합니다.|  
|[CMFCRibbonCategory::SetData](#setdata)|리본 범주에는 사용자 정의 데이터를 저장합니다.|  
|[CMFCRibbonCategory::SetKeys](#setkeys)|리본 범주에는 keytip을 할당합니다.|  
|[CMFCRibbonCategory::SetName](#setname)||  
|[Cmfcribboncategory:: Settabcolor](#settabcolor)|리본 범주의 색을 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 일반적으로 되지 리본 범주를 직접 호출 하 여 만든 [CMFCRibbonBar::AddCategory](../../mfc/reference/cmfcribbonbar-class.md#addcategory), 새로 생성된 된 리본 범주에 대 한 포인터를 반환 하는 합니다. 호출 하 여 범주에 패널 추가 [CMFCRibbonCategory::AddPanel](#addpanel)합니다.  
  
 `CMFCRibbonTab` 클래스 리본 범주를 그립니다. 파생 된 [CMFCRibbonBaseElement 클래스](../../mfc/reference/cmfcribbonbaseelement-class.md)합니다.  
  
 다음 예제에는 리본 범주를 만들고 패널에 추가 하는 방법을 보여 줍니다.  
  
 `// Create a new ribbon category and get a pointer to it`  
  
 `CMFCRibbonCategory* pCategory = m_wndRibbonBar.AddCategory`  
  
 `(_T("&Write"),           // Category name`  
  
 `IDB_WRITE,              // Category small images (16 x 16)`  
  
 `IDB_WRITE_LARGE);   // Category large images (32 x 32)`  
  
 `// Add a panel to the new category`  
  
 `CMFCRibbonPanel* pPanel = pCategory->AddPanel (`  
  
 `_T("Clipboard"),                       // Panel name`  
  
 `m_PanelIcons.ExtractIcon (0));  // Panel icon`  
  
 다음 다이어그램은 홈 범주에 속하는 RibbonApp 샘플 응용 프로그램에서 그림을 보여 줍니다.  
  
 ![CMFCRibbonCategory 이미지](../../mfc/reference/media/cmfcribboncategory.png "cmfcribboncategory")  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCRibbonCategory`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxribboncategory.h  
  
##  <a name="addhidden"></a>  CMFCRibbonCategory::AddHidden  
 사용자 지정 대화 상자에 표시 되는 리본 요소의 배열에 지정 된 리본 요소를 추가 합니다.  
  
```  
void AddHidden(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pElem*  
 리본 요소에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 대화 상자에 리본 요소는 빠른 실행 도구 모음에 추가할 수 있는 명령.  
  
##  <a name="addpanel"></a>  CMFCRibbonCategory::AddPanel  
 리본 범주에 대 한 리본 패널을 만듭니다.  
  
```  
CMFCRibbonPanel* AddPanel(
    LPCTSTR lpszPanelName,  
    HICON hIcon = 0,  
    CRuntimeClass* pRTI = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *lpszPanelName*  
 새 리본 패널의 이름에 대 한 포인터입니다.  
  
 [in] *hIcon*  
 새 리본 패널에 대 한 기본 아이콘에 대 한 핸들입니다.  
  
 [in] *pRTI*  
 사용자 지정 리본 패널에 대 한 런타임 클래스 정보에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 새 리본 패널에 대 한 포인터 그렇지 않으면 `NULL` 패널을 만들지 않은 경우.  
  
### <a name="remarks"></a>설명  
 사용자 지정 리본 패널을 만들려는 경우에 해당 런타임 클래스 정보에 지정 해야 *pRTI*합니다. 사용자 지정 리본 패널 클래스에서 파생 되어야 합니다는 `CMFCRibbonPanel` 클래스입니다.  
  
 리본 요소를 표시 하려면 공간이 부족 하 여 리본 패널에 대 한 기본 아이콘이 표시 됩니다.  
  
### <a name="example"></a>예  
 다음 예제에서는 사용 하는 `AddPanel` 에서 메서드는 `CMFCRibbonCategory` 클래스.  
  
 [!code-cpp[NVC_MFC_RibbonApp#10](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_1.cpp)]  
  
##  <a name="cmfcribboncategory"></a>  CMFCRibbonCategory::CMFCRibbonCategory  
 생성 하 고 초기화는 [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) 개체입니다.  
  
```  
CMFCRibbonCategory(
    CMFCRibbonBar* pParenrRibbonBar,  
    LPCTSTR lpszName,  
    UINT uiSmallImagesResID,  
    UINT uiLargeImagesResID,  
    CSize sizeSmallImage = CSize(16,
    16),  
    CSize sizeLargeImage = CSize(32,
    32));
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pParenrRibbonBar*  
 리본 범주에 속하는 부모 리본 표시줄에 대 한 포인터입니다.  
  
 [in] *lpszName*  
 리본 범주의 이름입니다.  
  
 [in] *uiSmallImagesResID*  
 이미지 목록의 리본 범주에 있는 리본 요소에 의해 사용 되는 작은 이미지에 대 한 리소스 ID입니다.  
  
 [in] *uiLargeImagesResID*  
 이미지 목록의 리본 범주에 있는 리본 요소에 의해 사용 되는 큰 이미지에 대 한 리소스 ID입니다.  
  
 [in] *sizeSmallImage*  
 기본 리본 범주에 있는 리본 요소에 대 한 작은 이미지의 크기입니다.  
  
 [in] *sizeLargeImage*  
 기본 리본 범주에 있는 리본 요소에 대 한 큰 이미지의 크기입니다.  
  
##  <a name="copyfrom"></a>  CMFCRibbonCategory::CopyFrom  
 지정된 된 상태의 복사 [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) 현재 [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) 개체입니다.  
  
```  
virtual void CopyFrom(CMFCRibbonCategory& src);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *src*  
 소스 `CMFCRibbonCategory` 개체입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="findbydata"></a>  CMFCRibbonCategory::FindByData  
 지정된 된 데이터와 연결 된 리본 요소를 검색 합니다.  
  
```  
CMFCRibbonBaseElement* FindByData(
    DWORD_PTR dwData,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *dwData*  
 리본 요소에 연결 된 데이터입니다.  
  
 [in] *bVisibleOnly*  
 `TRUE` 검색에 대 한 빠른 액세스 리본 요소를 포함 하려면 `FALSE` 검색에 대 한 빠른 액세스 리본 요소를 제외 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 리본 요소에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="findbyid"></a>  CMFCRibbonCategory::FindByID  
 지정한 명령 ID와 연결 된 리본 요소를 검색  
  
```  
CMFCRibbonBaseElement* FindByID(
    UINT uiCmdID,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *uiCmdID*  
 리본 요소에 연결 된 명령 ID입니다.  
  
 [in] *bVisibleOnly*  
 `TRUE` 검색에 대 한 빠른 액세스 리본 요소를 포함 하려면 `FALSE` 검색에 대 한 빠른 액세스 리본 요소를 제외 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 리본 요소에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="findpanelwithelem"></a>  CMFCRibbonCategory::FindPanelWithElem  
 지정 된 리본 요소를 포함 하는 리본 패널을 검색 합니다.  
  
```  
CMFCRibbonPanel* FindPanelWithElem(const CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pElement*  
 리본 요소에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 리본 패널에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getcontextid"></a>  CMFCRibbonCategory::GetContextID  
 리본 범주의 컨텍스트 ID를 검색합니다.  
  
```  
UINT GetContextID() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리본 범주의 컨텍스트 ID입니다.  
  
### <a name="remarks"></a>설명  
 컨텍스트 ID은 리본 범주 상황에 맞는 리본 범주를 없으면 0입니다.  
  
##  <a name="getdata"></a>  CMFCRibbonCategory::GetData  
 리본 범주와 연결 된 사용자 정의 데이터를 검색 합니다.  
  
```  
DWORD_PTR GetData() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리본 범주와 연결 된 사용자 정의 데이터입니다.  
  
##  <a name="getdroppeddown"></a>  CMFCRibbonCategory::GetDroppedDown  
 현재 표시 되는 팝업 메뉴에 있는 리본 요소에 대 한 포인터를 검색 합니다.  
  
```  
CMFCRibbonBaseElement* GetDroppedDown();
```  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 리본 요소에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getelements"></a>  CMFCRibbonCategory::GetElements  
 리본 범주에서 모든 리본 요소를 검색 합니다.  
  
```  
void GetElements(
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>매개 변수  
 [out에서] *arElements*  
 에 대 한 참조는 [CArray](../../mfc/reference/carray-class.md) 리본 요소의 합니다.  
  
### <a name="remarks"></a>설명  
 빠른 실행 도구 모음에서 사용 하도록 디자인 된 리본 요소 배열에 포함 됩니다.  
  
##  <a name="getelementsbyid"></a>  CMFCRibbonCategory::GetElementsByID  
 지정한 명령 ID와 연결 된 모든 리본 요소를 검색 합니다.  
  
```  
void GetElementsByID(
    UINT uiCmdID,  
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *uiCmdID*  
 리본 요소에 연결 된 명령 ID입니다.  
  
 [out에서] *arElements*  
 에 대 한 참조는 [CArray](../../mfc/reference/carray-class.md) 리본 요소의 합니다.  
  
### <a name="remarks"></a>설명  
 빠른 실행 도구 모음에서 사용 하도록 디자인 된 리본 요소 배열에 포함 됩니다.  
  
##  <a name="getfirstvisibleelement"></a>  CMFCRibbonCategory::GetFirstVisibleElement  
 리본 범주에 속하는 첫 번째 표시 요소를 검색 합니다.  
  
```  
CMFCRibbonBaseElement* GetFirstVisibleElement() const;  
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 표시 요소에 대 한 포인터 되었을 `NULL` 범주에 표시 된 요소 수 없는 경우.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getfocused"></a>  CMFCRibbonCategory::GetFocused  
 포커스가 지정된 요소를 반환합니다.  
  
```  
CMFCRibbonBaseElement* GetFocused();
```  
  
### <a name="return-value"></a>반환 값  
 포커스가 있는 요소에 대 한 포인터 또는 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="gethighlighted"></a>  CMFCRibbonCategory::GetHighlighted  
 강조 표시 된 요소를 반환합니다.  
  
```  
CMFCRibbonBaseElement* GetHighlighted();
```  
  
### <a name="return-value"></a>반환 값  
 강조 표시 된 요소에 대 한 포인터 또는 `NULL` 이면 요소가 강조 표시 됩니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getimagecount"></a>  CMFCRibbonCategory::GetImageCount  
 리본 범주에 포함 된 지정 된 이미지 목록의 이미지의 수를 검색 합니다.  
  
```  
int GetImageCount(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *bIsLargeImage*  
 `TRUE` 큰 이미지 목록의 이미지의 수에 대 한 `FALSE` 작은 이미지 목록의 이미지의 수에 대 한 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 이미지 목록의 이미지의 수입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getimagesize"></a>  CMFCRibbonCategory::GetImageSize  
 리본 범주에 포함 된 지정 된 이미지 목록의 이미지의 크기를 검색 합니다.  
  
```  
CSize GetImageSize(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *bIsLargeImage*  
 `TRUE` 큰 이미지;의 크기에 대 한 `FALSE` 작은 이미지의 크기에 대 한 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 이미지 목록의 이미지의 크기입니다.  
  
### <a name="remarks"></a>설명  
 검색 된 크기에는 전역 이미지 배율을 포함 됩니다.  
  
##  <a name="getitemidslist"></a>  CMFCRibbonCategory::GetItemIDsList  
 리본 범주에 포함 된 리본 요소에 대 한 명령 Id를 검색 합니다.  
  
```  
void GetItemIDsList(
    CList<UINT, UINT>& lstItems,  
    BOOL bHiddenOnly = FALSE) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] *lstItems*  
 리본 범주에 있는 리본 요소에 대 한 명령 Id의 목록.  
  
 [in] *bHiddenOnly*  
 `TRUE` 리본 범주;에 있는 리본 패널에 표시 되는 리본 요소를 제외 하려면 `FALSE` 리본 범주에 있는 모든 리본 요소를 포함 하도록 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getlargeimages"></a>  CMFCRibbonCategory::GetLargeImages  
 리본 범주에 포함 된 큰 이미지 목록을 검색 합니다.  
  
```  
CMFCToolBarImages& GetLargeImages();
```  
  
### <a name="return-value"></a>반환 값  
 리본 범주에 포함 된 큰 이미지의 목록.  
  
##  <a name="getlastvisibleelement"></a>  CMFCRibbonCategory::GetLastVisibleElement  
 리본 범주에 속하는 보이는 마지막 요소로 검색 합니다.  
  
```  
CMFCRibbonBaseElement* GetLastVisibleElement() const;  
```  
  
### <a name="return-value"></a>반환 값  
 보이는 마지막 요소로;에 대 한 포인터 되었을 `NULL` 범주에 표시 된 요소 수 없는 경우.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getmaxheight"></a>  CMFCRibbonCategory::GetMaxHeight  
 리본 범주에 포함 된 리본 패널의 최대 높이 검색 합니다.  
  
```  
int GetMaxHeight(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pDC*  
 리본 패널에 대 한 장치 컨텍스트에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 리본 범주에 포함 된 리본 패널의 최대 높이입니다.  
  
### <a name="remarks"></a>설명  
 검색 된 값에는 리본 패널에 대 한 위쪽 및 아래쪽 여백 높이 포함 됩니다.  
  
##  <a name="getname"></a>  CMFCRibbonCategory::GetName  
 리본 범주 이름을 검색합니다.  
  
```  
LPCTSTR GetName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리본 범주의 이름입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getpanel"></a>  CMFCRibbonCategory::GetPanel  
 지정된 된 인덱스에 있는 리본 패널에 대 한 포인터를 반환 합니다.  
  
```  
CMFCRibbonPanel* GetPanel(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *nIndex*  
 리본 패널의 0부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 인덱스에 있는 리본 패널에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 예외가 발생 하는 경우 *nIndex* 범위를 벗어났습니다.  
  
##  <a name="getpanelcount"></a>  CMFCRibbonCategory::GetPanelCount  
 리본 범주에 있는 리본 패널 수를 반환합니다.  
  
```  
int GetPanelCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리본 범주에 있는 리본 패널의 수입니다.  
  
##  <a name="getpanelfrompoint"></a>  CMFCRibbonCategory::GetPanelFromPoint  
 지정 된 위치에 있으면 리본 패널에 대 한 포인터를 검색 합니다.  
  
```  
CMFCRibbonPanel* GetPanelFromPoint(CPoint point) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *지점*  
 창의 왼쪽 위 모퉁이 기준으로 포인터의 x 및 y 좌표입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 리본 패널에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 리본 범주에 포함 된 리본 패널만 테스트 됩니다.  
  
##  <a name="getpanelindex"></a>  CMFCRibbonCategory::GetPanelIndex  
 지정 된 리본 패널의 0부터 시작 하는 인덱스를 검색합니다.  
  
```  
int GetPanelIndex(const CMFCRibbonPanel* pPanel) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pPanel*  
 리본 패널에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 지정 된 리본 패널의 0부터 시작 인덱스 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>설명  
 리본 범주에 포함 된 리본 패널만 검색 됩니다.  
  
##  <a name="getparentbutton"></a>  CMFCRibbonCategory::GetParentButton  
 리본 범주에 속하는 부모 리본 요소를 검색합니다.  
  
```  
CMFCRibbonBaseElement* GetParentButton() const;  
```  
  
### <a name="return-value"></a>반환 값  
 부모 리본 요소에 대 한 포인터를 반환 하거나 `NULL` 부모 요소가 없는 경우.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getparentmenubar"></a>  CMFCRibbonCategory::GetParentMenuBar  
 부모 메뉴 모음에 대 한 포인터를 반환 합니다.는 `CMFCRibbonCategory` 개체입니다.  
  
```  
CMFCRibbonPanelMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>반환 값  
 내용을 반환 합니다.는 `m_pParentMenuBar` 구성원을 보호 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getparentribbonbar"></a>  CMFCRibbonCategory::GetParentRibbonBar  
 리본 범주에 대 한 부모 리본 표시줄을 검색합니다.  
  
```  
CMFCRibbonBar* GetParentRibbonBar() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리본 범주에 대 한 부모 리본 표시줄에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getrect"></a>  CMFCRibbonCategory::GetRect  
 리본 범주에 대 한 표시 사각형을 검색합니다.  
  
```  
CRect GetRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리본 범주에 대 한 표시 사각형을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 리본 범주에 대 한 표시 사각형 범주 탭을 포함 되지 않습니다.  
  
##  <a name="getsmallimages"></a>  CMFCRibbonCategory::GetSmallImages  
 리본 범주에 포함 된 작은 이미지 목록을 검색 합니다.  
  
```  
CMFCToolBarImages& GetSmallImages();
```  
  
### <a name="return-value"></a>반환 값  
 리본 범주에 포함 된 작은 이미지의 목록.  
  
##  <a name="gettabcolor"></a>  CMFCRibbonCategory::GetTabColor  
 리본 범주 탭에 현재 색을 반환합니다.  
  
```  
AFX_RibbonCategoryColor GetTabColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 색 리본 범주 탭입니다.  
  
### <a name="remarks"></a>설명  
 반환 되는 값은 다음 열거형된 값 중 하나일 수 있습니다.  
  
-   AFX_CategoryColor_Red  
  
-   AFX_CategoryColor_Orange  
  
-   AFX_CategoryColor_Yellow  
  
-   AFX_CategoryColor_Green  
  
-   AFX_CategoryColor_Blue  
  
-   AFX_CategoryColor_Indigo  
  
-   AFX_CategoryColor_Violet  
  
##  <a name="gettabrect"></a>  CMFCRibbonCategory::GetTabRect  
 리본 범주 탭에 대 한 표시 사각형을 검색합니다.  
  
```  
CRect GetTabRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리본 범주 탭에 대 한 표시 사각형을 지정 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="gettexttopline"></a>  CMFCRibbonCategory::GetTextTopLine  
 큰 이미지를 표시 하는 리본 범주에 있는 리본 단추의 텍스트의 세로 위치를 검색 합니다.  
  
```  
int GetTextTopLine() const;  
```  
  
### <a name="return-value"></a>반환 값  
 픽셀, 큰 이미지를 표시 하는 리본 단추 텍스트의 세로 위치입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getvisibleelements"></a>  CMFCRibbonCategory::GetVisibleElements  
 리본 범주에 속하는 모든 요소를 검색 합니다.  
  
```  
void GetVisibleElements(
    CArray <CMFCRibbonBaseElement*,  
    CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>매개 변수  
 *arElements*  
 표시 된 모든 요소의 배열입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="highlightpanel"></a>  CMFCRibbonCategory::HighlightPanel  
 지정 된 리본 패널에 강조 표시합니다.  
  
```  
CMFCRibbonPanel* HighlightPanel(
    CMFCRibbonPanel* pHLPanel,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pHLPanel*  
 강조 표시를 리본 패널에 대 한 포인터입니다.  
  
 [in] *지점*  
 창의 왼쪽 위 모퉁이 기준으로 포인터의 x 및 y 좌표입니다.  
  
### <a name="return-value"></a>반환 값  
 이전에 강조 표시 된 리본 패널;에 대 한 포인터 그렇지 않으면 `NULL` 없는 리본 패널에는이 메서드가 호출 되 면 강조 표시 되 면입니다.  
  
### <a name="remarks"></a>설명  
 리본 패널에 강조 표시 하는 방법에 대 한 자세한 내용은 참조 [CMFCRibbonPanel::Highlight](../../mfc/reference/cmfcribbonpanel-class.md#highlight)합니다.  
  
##  <a name="hittest"></a>  CMFCRibbonCategory::HitTest  
 지정 된 위치에 있으면 리본 요소에 대 한 포인터를 검색 합니다.  
  
```  
CMFCRibbonBaseElement* HitTest(
    CPoint point,  
    BOOL bCheckPanelCaption = FALSE) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *지점*  
 창의 왼쪽 위 모퉁이 기준으로 마우스 포인터의 x 및 y 좌표입니다.  
  
 [in] *bCheckPanelCaption*  
 `TRUE` 리본 패널 캡션; 테스트 하려면 `FALSE` 를 리본 패널 캡션 제외 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 리본 요소에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 리본 요소에만 리본 범주에 포함 된 테스트 됩니다.  
  
##  <a name="hittestex"></a>  CMFCRibbonCategory::HitTestEx  
 지정 된 위치에 있으면 리본 요소의 0부터 시작 인덱스를 검색 합니다.  
  
```  
int HitTestEx(CPoint point) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *지점*  
 창의 왼쪽 위 모퉁이 기준으로 마우스 포인터의 x 및 y 좌표입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 리본 요소의 0부터 시작 인덱스 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>설명  
 리본 요소에만 리본 범주에 포함 된 테스트 됩니다.  
  
##  <a name="hittestscrollbuttons"></a>  CMFCRibbonCategory::HitTestScrollButtons  
 리본 범주를 왼쪽 또는 오른쪽 스크롤 단추 내에서 한 지점을 뒤쳐지면 단추에 대 한 포인터를 반환 합니다.  
  
```  
CMFCRibbonBaseElement* HitTestScrollButtons(CPoint point) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *지점*  
 테스트 지점입니다.  
  
### <a name="return-value"></a>반환 값  
 경우 *가리킨* 중 왼쪽의 경계 사각형 또는 오른쪽 스크롤 단추 리본 범주에 속하도록, 해당 단추에 대 한 포인터를 반환 또는 그렇지 않으면 반환 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="isactive"></a>  CMFCRibbonCategory::IsActive  
 리본 범주 리본 표시줄의 활성 범주 인지를 나타냅니다.  
  
```  
BOOL IsActive() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 리본 범주 활성 범주; 이면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 활성화 된 리본 범주는 리본 패널을 표시합니다.  
  
##  <a name="isvisible"></a>  CMFCRibbonCategory::IsVisible  
 리본 범주에 표시 되는지 여부를 나타냅니다.  
  
```  
BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 리본 범주에 표시 되 면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 표시 되는 리본 범주에 범주 탭이 표시 됩니다.  
  
##  <a name="iswindows7look"></a>  CMFCRibbonCategory::IsWindows7Look  
 부모 리본 (작은 사각형 응용 프로그램 단추)를 확인 하는 Windows 7에 있는지 여부를 나타냅니다.  
  
```  
BOOL IsWindows7Look() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 부모 리본에 Windows 7; 확인 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="notifycontrolcommand"></a>  CMFCRibbonCategory::NotifyControlCommand  
 모든 WM_NOTIFY 명령 메시지를 배달할 `CMFCRibbonPanel` 의 요소는 `CMFCRibbonCategory` 메시지 처리 될 때까지 합니다.  
  
```  
virtual BOOL NotifyControlCommand(
    BOOL bAccelerator,  
    int nNotifyCode,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *bAccelerator*  
 `TRUE` 이 명령은 액셀러레이터에서 생성 된 경우 또는 `FALSE` 그렇지 않은 경우.  
  
 [in] *nNotifyCode*  
 알림 코드입니다.  
  
 [in] *wParam*  
 메시지의 WPARAM 필드입니다.  
  
 [in] *lParam*  
 메시지의 LPARAM 필드입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 메시지가 처리 되는 경우 또는 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>설명  
  
##  <a name="oncancelmode"></a>  CMFCRibbonCategory::OnCancelMode  
 모든 취소 모드를 호출 하는 `CMFCRibbonPanel` 의 요소는 `CMFCRibbonCategory`합니다.  
  
```  
virtual void OnCancelMode();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="ondraw"></a>  CMFCRibbonCategory::OnDraw  
 리본 범주를 그리기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pDC*  
 리본 범주에 대 한 장치 컨텍스트에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="ondrawimage"></a>  CMFCRibbonCategory::OnDrawImage  
 리본 범주에 지정된 된 이미지를 그리기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnDrawImage(
    CDC* pDC,  
    CRect rect,  
    CMFCRibbonBaseElement* pElement,  
    BOOL bIsLargeImage,  
    BOOL nImageIndex,  
    BOOL bCenter);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pDC*  
 이미지에 대 한 장치 컨텍스트에 대 한 포인터입니다.  
  
 [in] *rect*  
 이미지에 대 한 사각형을 표시 합니다.  
  
 [in] *pElement*  
 이미지가 포함 된 리본 요소에 대 한 포인터입니다.  
  
 [in] *bIsLargeImage*  
 `TRUE` 이미지가; 크기가 큰 경우 `FALSE` 이미지가 크기가 작은 경우.  
  
 [in] *nImageIndex*  
 리본 범주에 포함 된 이미지 배열에 있는 이미지의 인덱스 0부터 시작 합니다.  
  
 [in] *bCenter*  
 `TRUE` 이미지의 표시 사각형; 센터로 `FALSE` 표시 사각형의 왼쪽 위 모퉁이에 이미지를 그릴 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="ondrawmenuborder"></a>  CMFCRibbonCategory::OnDrawMenuBorder  
 팝업 메뉴의 테두리를 그리는 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDrawMenuBorder(
    CDC* pDC,  
    CMFCRibbonPanelMenuBar* pMenuBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pDC*  
 이 매개 변수는 사용되지 않습니다.  
  
 [in] *pMenuBar*  
 이 매개 변수는 사용되지 않습니다.  
  
### <a name="remarks"></a>설명  
 기본적으로이 메서드는 아무 작업도 수행 하지 않습니다. 팝업 메뉴의 테두리를 그리는이 메서드를 재정의 합니다.  
  
##  <a name="onkey"></a>  CMFCRibbonCategory::OnKey  
 사용자가 키보드 단추를 누를 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>매개 변수  
 *nChar*  
 사용자가 누른 키에 대 한 가상 키 코드입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="onlbuttondown"></a>  CMFCRibbonCategory::OnLButtonDown  
 사용자가 왼쪽된 마우스 단추를 누를 때 지정된 된 지점 아래에 있는 리본 요소를 검색 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual CMFCRibbonBaseElement* OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *지점*  
 창의 왼쪽 위 모퉁이 기준으로 마우스 포인터의 x 및 y 좌표입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 리본 요소에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="onlbuttonup"></a>  CMFCRibbonCategory::OnLButtonUp  
 리본 범주 위에 포인터를 마우스 왼쪽된 단추를 놓을 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *지점*  
 창의 왼쪽 위 모퉁이 기준으로 포인터의 x 및 y 좌표입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="onmousemove"></a>  CMFCRibbonCategory::OnMouseMove  
 포인터를 움직이면 리본 표시줄에서 리본 범주 표시를 업데이트 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnMouseMove(CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *지점*  
 창의 왼쪽 위 모퉁이 기준으로 포인터의 x 및 y 좌표입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="onrtlchanged"></a>  CMFCRibbonCategory::OnRTLChanged  
 레이아웃 방향 변경 될 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *bIsRTL*  
 `TRUE` 레이아웃은 오른쪽에서 왼쪽; 경우 `FALSE` 경우 레이아웃은 왼쪽에서 오른쪽입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 모든 리본 패널 및 리본 범주에 포함 된 리본 요소의 레이아웃을 조정 합니다.  
  
##  <a name="onscrollhorz"></a>  CMFCRibbonCategory::OnScrollHorz  
 리본 범주에서 가로 방향으로 스크롤합니다.  
  
```  
virtual BOOL OnScrollHorz(
    BOOL bScrollLeft,  
    int nScrollOffset = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *bScrollLeft*  
 `TRUE` 왼쪽으로 스크롤하여 `FALSE` 오른쪽으로 스크롤해야 합니다.  
  
 [in] *nScrollOffset*  
 스크롤 거리 (픽셀)입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 리본 범주를 가로 방향으로;에서 이동 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="onupdatecmdui"></a>  CMFCRibbonCategory::OnUpdateCmdUI  
 호출 된 `OnUpdateCmdUI` 의 각 멤버 함수는 `CMFCRibbonPanel` 의 요소는 `CMFCRibbonCategory` 여기에 사용자 인터페이스 요소를 사용 하지 않도록 설정 하거나 설정 하려면.  
  
```  
virtual void OnUpdateCmdUI(
    CMFCRibbonCmdUI* pCmdUI,  
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pCmdUI*  
 에 대 한 포인터는 `CMFCRibbonCmdUI` 사용 하도록 설정 하는 사용자 인터페이스 요소가 고 어느을 비활성화할 수를 지정 하는 개체입니다.  
  
 [in] *pTarget*  
 설정 하거나 사용자 인터페이스 요소의 해제를 제어 하는 창에 대 한 포인터입니다.  
  
 [in] *bDisableIfNoHndler*  
 `TRUE` 메시지 맵;에 정의 되어 있는 경우 처리기 사용자 인터페이스 항목을 비활성화 하려면 있습니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="recalclayout"></a>  CMFCRibbonCategory::RecalcLayout  
 리본 범주에 있는 모든 컨트롤의 레이아웃을 조정합니다.  
  
```  
virtual void RecalcLayout(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pDC*  
 리본 범주에 대 한 장치 컨텍스트에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="removepanel"></a>  CMFCRibbonCategory::RemovePanel  
 리본 범주에서 리본 패널을 제거합니다.  
  
```cpp  
BOOL RemovePanel(
    int nIndex,  
    BOOL bDelete = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *nIndex*  
 제거할 패널의 인덱스 번호입니다. 호출 하 여 가져온는 [CMFCRibbonCategory::GetPanelIndex](#getpanelindex) 메서드.  
  
 [in] *b 삭제*  
 `TRUE` 메모리에서 패널 개체를 삭제 하려면 `FALSE` 삭제 하지 않고 패널 개체를 제거할 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공했으면 `TRUE`이고, 실패했으면 `FALSE`입니다.  
  
##  <a name="repospanels"></a>  CMFCRibbonCategory::ReposPanels  
 리본 범주에 포함 된 리본 패널에 있는 모든 컨트롤의 레이아웃을 조정 합니다.  
  
```  
virtual void ReposPanels(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pDC*  
 리본 범주에 포함 된 리본 패널에 대 한 장치 컨텍스트에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setcollapseorder"></a>  CMFCRibbonCategory::SetCollapseOrder  
 리본 범주의 리본 패널을 축소 하는 순서를 정의 합니다.  
  
```  
void SetCollapseOrder(const CArray<int,int>& arCollapseOrder);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *arCollapseOrder*  
 축소 순서를 지정합니다. 배열 리본 패널의 0부터 시작 인덱스를 포함합니다.  
  
### <a name="remarks"></a>설명  
 라이브러리는 축소 순서를 정의합니다. 그러나 범주 축소 순서를 지정 하는 인덱스 목록을 제공 하 여이 동작을 사용자 지정할 수 있습니다.  
  
 범주를 리본 패널을 축소 하려면 있다는 것을 감지 하면 지정 된 목록에에서 다음 요소를 찾습니다. 목록이 비어 또는 충분 한 요소를 지정 하지 않은 경우 범주는 내부 알고리즘을 사용 합니다.  
  
 예를 들어 범주 리본 패널 세 개 있으며 모든 패널 완전히 축소 된 상태로 될 때까지 여러 번 축소할 수 있습니다. 다음 축소 순서를 설정할 수 있습니다: 0, 0, 2, 2입니다. 이 경우 범주 0 패널 두 번 축소 됩니다, 그리고 2 패널 두 배입니다. Uncollapsed 패널 1의 인덱스에 유지 됩니다.  
  
### <a name="example"></a>예  
 다음 예제에서는 사용 하는 `SetCollapseOrder` 에서 메서드는 `CMFCRibbonCategory` 클래스. 이 예제에서는 리본 범주를 축소 순서를 설정 하는 방법 및 축소 주문에 대 한 배열을 생성 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#13](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_2.cpp)]  
  
##  <a name="setdata"></a>  CMFCRibbonCategory::SetData  
 리본 범주와 연결 되도록 사용자 지정 데이터를 설정 합니다.  
  
```  
void SetData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *dwData*  
 사용자 정의 데이터입니다.  
  
##  <a name="setkeys"></a>  CMFCRibbonCategory::SetKeys  
 리본 범주에는 keytip을 할당합니다.  
  
```  
void SetKeys(LPCTSTR lpszKeys);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *lpszKeys*  
 Keytip 텍스트입니다.  
  
### <a name="remarks"></a>설명  
 키 팁에는 사용자가 Alt 키 또는 F10 키를 누를 때 표시 됩니다.  
  
##  <a name="setname"></a>  CMFCRibbonCategory::SetName  
 이름 및 keytip 리본 범주에 할당합니다.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *lpszName*  
 이름과 리본 범주에 속하는 keytip입니다.  
  
### <a name="remarks"></a>설명  
 리본 범주에 대 한 keytip을 설정 하려면 추가를 keytip 문자로 이어지는 줄 바꿈 이스케이프 시퀀스 *lpszName*합니다.  
  
##  <a name="settabcolor"></a>  Cmfcribboncategory:: Settabcolor  
 리본 범주의 색을 설정 합니다.  
  
```  
void SetTabColor(AFX_RibbonCategoryColor color);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *색*  
 리본 범주의 새 색을 지정합니다.  
  
### <a name="remarks"></a>설명  
 색은 다음 값 중 하나일 수 있습니다.  
  
-   AFX_CategoryColor_None  
  
-   AFX_CategoryColor_Red  
  
-   AFX_CategoryColor_Orange  
  
-   AFX_CategoryColor_Yellow  
  
-   AFX_CategoryColor_Green  
  
-   AFX_CategoryColor_Blue  
  
-   AFX_CategoryColor_Indigo  
  
-   AFX_CategoryColor_Violet  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)
