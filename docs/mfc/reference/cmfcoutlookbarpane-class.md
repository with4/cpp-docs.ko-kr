---
title: "CMFCOutlookBarPane 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::AddButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::CanBeAttached
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::ClearAll
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::Create
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnablePageScrollMode
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::GetRegularColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsBackgroundTexture
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsDrawShadedHighlight
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackImage
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetDefaultState
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetExtraSpace
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTextColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTransparentColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnableContextMenuItems
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveAllButtons
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBarPane [MFC], AddButton
- CMFCOutlookBarPane [MFC], CanBeAttached
- CMFCOutlookBarPane [MFC], ClearAll
- CMFCOutlookBarPane [MFC], Create
- CMFCOutlookBarPane [MFC], EnablePageScrollMode
- CMFCOutlookBarPane [MFC], GetRegularColor
- CMFCOutlookBarPane [MFC], IsBackgroundTexture
- CMFCOutlookBarPane [MFC], IsDrawShadedHighlight
- CMFCOutlookBarPane [MFC], RemoveButton
- CMFCOutlookBarPane [MFC], SetBackColor
- CMFCOutlookBarPane [MFC], SetBackImage
- CMFCOutlookBarPane [MFC], SetDefaultState
- CMFCOutlookBarPane [MFC], SetExtraSpace
- CMFCOutlookBarPane [MFC], SetTextColor
- CMFCOutlookBarPane [MFC], SetTransparentColor
- CMFCOutlookBarPane [MFC], EnableContextMenuItems
- CMFCOutlookBarPane [MFC], RemoveAllButtons
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 59eb92e44a26577866a797243f3a32d53b854365
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcoutlookbarpane-class"></a>CMFCOutlookBarPane 클래스
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 파생 되는 컨트롤 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md) Outlook 표시줄에 삽입할 수 있는 ( [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)). Outlook 표시줄 창에 큰 단추의 열이 포함되어 있습니다. 단추 목록이 창보다 크면 위 아래로 스크롤할 수 있습니다. 사용자가 Outlook 표시줄 창을 Outlook 표시줄에서 분리하면 기본 프레임 창에서 이동하거나 도킹할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCOutlookBarPane : public CMFCToolBar  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|기본 생성자입니다.|  
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCOutlookBarPane::AddButton](#addbutton)|Outlook 표시줄 창에 단추를 추가 합니다.|  
|[CMFCOutlookBarPane::CanBeAttached](#canbeattached)|창에서 다른 창이 나 프레임 창에 도킹할 수 있는지 여부를 결정 합니다. (재정의 [CBasePane::CanBeAttached](../../mfc/reference/cbasepane-class.md#canbeattached).)|  
|`CMFCOutlookBarPane::CanBeRestored`|있는지 여부를 시스템 복원할 수는 도구 모음을 원래 상태로 사용자 지정 후 결정 합니다. (재정의 [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|  
|[CMFCOutlookBarPane::ClearAll](#clearall)|Outlook 표시줄 창에 이미지에서 사용 하는 리소스를 해제 합니다.|  
|[CMFCOutlookBarPane::Create](#create)|Outlook 표시줄 창을 만듭니다.|  
|`CMFCOutlookBarPane::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|`CMFCOutlookBarPane::Dock`|Outlook 표시줄 창을 도킹 하기 위해 프레임 워크에서 호출 됩니다. (`CPane::Dock`를 재정의합니다.)|  
|[CMFCOutlookBarPane::EnablePageScrollMode](#enablepagescrollmode)|이동할지 여부 Outlook 표시줄 창에 있는 스크롤 화살표 단추 목록 페이지에서 또는 단추를 클릭 합니다.|  
|[CMFCOutlookBarPane::GetRegularColor](#getregularcolor)|Outlook 표시줄 창의 일반 (비 선택) 텍스트 색을 반환 합니다.|  
|`CMFCOutlookBarPane::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에서는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|  
|[CMFCOutlookBarPane::IsBackgroundTexture](#isbackgroundtexture)|Outlook 표시줄 창에 대해 로드 된 배경 이미지 인지 확인 합니다.|  
|`CMFCOutlookBarPane::IsChangeState`|부동 창 도킹 될 수 있는지 여부를 결정 합니다. (`CPane::IsChangeState`를 재정의합니다.)|  
|[CMFCOutlookBarPane::IsDrawShadedHighlight](#isdrawshadedhighlight)|단추가 강조 표시 하 고 배경 이미지를 표시 된 단추 테두리 음영 처리 된 인지 확인 합니다.|  
|`CMFCOutlookBarPane::OnBeforeFloat`|Float에 대 한이 되 면 프레임 워크에서 호출 됩니다. (재정의 [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|  
|[CMFCOutlookBarPane::RemoveButton](#removebutton)|단추는 지정한 명령 ID를 제거 합니다.|  
|`CMFCOutlookBarPane::RestoreOriginalstate`|도구 모음의 원래 상태를 복원합니다. (재정의 [cmfctoolbar:: Restoreoriginalstate](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate).)|  
|[CMFCOutlookBarPane::SetBackColor](#setbackcolor)|명령 프롬프트 창의 배경색을 설정합니다.|  
|[CMFCOutlookBarPane::SetBackImage](#setbackimage)|배경 이미지를 설정합니다.|  
|[CMFCOutlookBarPane::SetDefaultState](#setdefaultstate)|Outlook 표시줄 창을 원래 단추 집합을 다시 설정합니다.|  
|[CMFCOutlookBarPane::SetExtraSpace](#setextraspace)|Outlook 표시줄 창에 단추 주위에 사용 되는 패딩 픽셀 수를 설정 합니다.|  
|[CMFCOutlookBarPane::SetTextColor](#settextcolor)|Outlook 표시줄 창에 일반적인 및 강조 표시 된 텍스트의 색을 설정합니다.|  
|[CMFCOutlookBarPane::SetTransparentColor](#settransparentcolor)|Outlook 표시줄 창에 대 한 투명 한 색을 설정합니다.|  
|`CMFCOutlookBarPane::SmartUpdate`|Outlook 표시줄을 업데이트 하려면 내부적으로 사용 합니다. (`CMFCToolBar::SmartUpdate`를 재정의합니다.)|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCOutlookBarPane::EnableContextMenuItems](#enablecontextmenuitems)|사용자 지정 모드에 표시 되는 바로 가기 메뉴 항목을 지정 합니다.|  
|[CMFCOutlookBarPane::RemoveAllButtons](#removeallbuttons)|Outlook 표시줄 창에서 모든 단추를 제거합니다. (재정의 [CMFCToolBar::RemoveAllButtons](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons).)|  
  
## <a name="remarks"></a>설명  
 Outlook 표시줄을 구현 하는 방법에 대 한 정보를 참조 하십시오. [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)합니다.  
  
 Outlook 표시줄의 예로, OutlookDemo 샘플 프로젝트를 참조 하세요.  
  
## <a name="example"></a>예  
 다음 예제에서는의 다양 한 메서드를 사용 하 여 `CMFCOutlookBarPane` 클래스입니다. 예제에는 Outlook 표시줄 창을 만들, 페이지 스크롤 모드를 사용 하도록 설정, 도킹, 설정 및 Outlook 표시줄의 배경색을 설정 하는 방법을 보여 줍니다. 이 코드 조각은의 일부인는 [Outlook 다중 보기 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxoutlookbarpane.h  
  
##  <a name="addbutton"></a>CMFCOutlookBarPane::AddButton  
 Outlook 표시줄 창에 단추를 추가 합니다.  
  
```  
BOOL AddButton(
    UINT uiImage,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    UINT uiImage,  
    UINT uiLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    LPCTSTR szBmpFileName,  
    LPCTSTR szLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    HBITMAP hBmp,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    HICON hIcon,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1,  
    BOOL bAlphaBlend=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiImage`  
 비트맵의 리소스 식별자를 지정합니다.  
  
 [in] `lpszLabel`  
 단추의 텍스트를 지정합니다.  
  
 [in] `iIdCommand`  
 단추 컨트롤의 ID를 지정 합니다.  
  
 [in] `iInsertAt`  
 Outlook 표시줄 페이지 단추를 삽입할 0부터 시작 하는 인덱스를 지정 합니다.  
  
 [in] `uiLabel`  
 문자열 리소스 id입니다.  
  
 [in] `szBmpFileName`  
 로드할 디스크 이미지 파일의 이름을 지정 합니다.  
  
 [in] `szLabel`  
 단추의 텍스트를 지정합니다.  
  
 [in] `hBmp`  
 단추 비트맵에 대 한 핸들입니다.  
  
 [in] `hIcon`  
 버튼의 아이콘에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`단추 성공적으로 추가 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 Outlook 표시줄의 페이지에 새 단추를 삽입 합니다. 응용 프로그램 리소스 또는 디스크 파일에서 단추의 이미지를 로드할 수 있습니다.  
  
 페이지 ID를 지정 하는 경우 `uiPageID` 은-1, 단추는 첫 번째 페이지에 삽입 됩니다.  
  
 지정 된 인덱스의 경우 `iInsertAt` 은-1, 단추 페이지의 끝에 추가 됩니다.  
  
##  <a name="canbeattached"></a>CMFCOutlookBarPane::CanBeAttached  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="clearall"></a>CMFCOutlookBarPane::ClearAll  
 Outlook 표시줄 창의 이미지를 사용 하는 리소스를 해제 합니다.  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>설명  
 이 메서드를 직접 호출 [CMFCToolBarImages::Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear)는 Outlook 표시줄 창에서 사용 되는 이미지에 대해 호출 됩니다.  
  
##  <a name="create"></a>CMFCOutlookBarPane::Create  
 Outlook 표시줄 창을 만듭니다.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle=AFX_DEFAULT_TOOLBAR_STYLE,  
    UINT uiID=(UINT)-1,  
    DWORD dwControlBarStyle=0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParentWnd`  
 Outlook 표시줄 창 컨트롤의 부모 창을 지정합니다. `NULL`이 아니어야 합니다.  
  
 [in] `dwStyle`  
 창 스타일입니다.  창 스타일의 목록이 참조 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)합니다.  
  
 [in] `uiID`  
 컨트롤 id입니다. 사용할 수 있도록 고유 해야 컨트롤의 상태를 저장 합니다.  
  
 [in] `dwControlBarStyle`  
 Outlook 표시줄에서 분리 될 때 Outlook 표시줄 창 컨트롤의 동작을 정의 하는 특별 한 스타일을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 생성 하는 `CMFCOutlookBarPane` 개체 먼저 생성자를 호출 하 고, 호출 하 `Create`, Outlook 표시줄 창 컨트롤을 만들고에 연결 하는 `CMFCOutlookBarPane` 개체입니다.  
  
 에 대 한 자세한 내용은 `dwControlBarStyle` 참조 [cbasepane:: Createex](../../mfc/reference/cbasepane-class.md#createex)합니다.  
  
##  <a name="enablecontextmenuitems"></a>CMFCOutlookBarPane::EnableContextMenuItems  
 사용자 지정 모드에 표시 되는 바로 가기 메뉴 항목을 지정 합니다.  
  
```  
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,  
    CMenu* pPopup);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pButton`  
 사용자를 클릭 하는 도구 모음 단추에 대 한 포인터입니다.  
  
 [in] `pPopup`  
 바로 가기 메뉴에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 바로 가기 메뉴는 표시 되지 않으면 해야 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 모드에는 프레임 워크가 표시 하는 프레임 워크 표준 바로 가기 메뉴를 수정 하려면이 메서드를 재정의 합니다.  
  
 기본 구현에서는 사용자 지정 모드를 확인 ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode))로 설정 된 경우 `TRUE`를 제외한 모든 바로 가기 메뉴 항목을 사용 하지 않도록 설정 **삭제**합니다. 그런 다음 입력된 매개 변수를 바로 전달 `CMFCToolBar::EnableContextMenuItems`합니다.  
  
> [!NOTE]
> *상황에 맞는 메뉴* 바로 가기 메뉴에 대 한 동의어.  
  
##  <a name="enablepagescrollmode"></a>CMFCOutlookBarPane::EnablePageScrollMode  
 Outlook 표시줄 창에 있는 스크롤 화살표 단추 하 여 단추 또는 페이지 별로 단추의 목록을 이동할지 여부.  
  
```  
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bPageScroll`  
 경우 `TRUE`, 페이지 스크롤 모드를 사용 하도록 설정 합니다. 경우 `FALSE`, 페이지 스크롤 모드를 사용 하지 않도록 설정 합니다.  
  
##  <a name="getregularcolor"></a>CMFCOutlookBarPane::GetRegularColor  
 일반적인 반환 (즉, 선택 되지 않은) Outlook 표시줄 창의 텍스트 색입니다.  
  
```  
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 RGB 색 값으로 현재 텍스트 색입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 [CMFCOutlookBarPane::SetTextColor](#settextcolor) Outlook 표시줄의 현재 (일반 및 선택한) 텍스트 색을 설정 합니다. 호출 하 여 기본 텍스트 색을 가져올 수 있습니다는 [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) 작동는 `COLOR_WINDOW` 인덱스입니다.  
  
##  <a name="isbackgroundtexture"></a>CMFCOutlookBarPane::IsBackgroundTexture  
 Outlook 표시줄 창에 대해 로드 된 배경 이미지 인지 확인 합니다.  
  
```  
BOOL IsBackgroundTexture() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이면; 표시 되도록 배경 이미지 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 호출 하 여 배경 이미지를 추가할 수 있습니다 [CMFCOutlookBarPane::SetBackImage](#setbackimage) 함수입니다.  
  
 사용 하 여 지정 된 색으로 백그라운드를 그리는 배경 이미지가 없습니다 이면 [CMFCOutlookBarPane::SetBackColor](#setbackcolor)합니다.  
  
##  <a name="isdrawshadedhighlight"></a>CMFCOutlookBarPane::IsDrawShadedHighlight  
 단추가 강조 표시 하 고 배경 이미지를 표시 된 단추 테두리 음영 처리 된 인지 확인 합니다.  
  
```  
BOOL IsDrawShadedHighlight() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`단추의 테두리; 회색으로 표시 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="removeallbuttons"></a>CMFCOutlookBarPane::RemoveAllButtons  
 Outlook 표시줄 창에서 모든 단추를 제거합니다.  
  
```  
virtual void RemoveAllButtons();
```  
  
##  <a name="removebutton"></a>CMFCOutlookBarPane::RemoveButton  
 단추는 지정한 명령 ID를 제거 합니다.  
  
```  
BOOL RemoveButton(UINT iIdCommand);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iIdCommand`  
 제거할 단추의 명령 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`단추는 성공적으로 제거 되었으면; `FALSE` 경우 지정한 명령 ID가 올바르지 않습니다.  
  
##  <a name="setbackcolor"></a>CMFCOutlookBarPane::SetBackColor  
 Outlook 표시줄의 배경색을 설정합니다.  
  
```  
void SetBackColor(COLORREF color);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `color`  
 새 배경 색을 지정합니다.  
  
### <a name="remarks"></a>설명  
 Outlook 표시줄에 대 한 현재 배경색을 설정 하려면이 함수를 호출 합니다. 명령 프롬프트 창의 배경색 배경 이미지가 없는 경우에 사용 됩니다.  
  
##  <a name="setbackimage"></a>CMFCOutlookBarPane::SetBackImage  
 배경 이미지를 설정합니다.  
  
```  
void SetBackImage(UINT uiImageID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiImageID`  
 이미지 리소스 ID를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 Outlook을 설정 하려면이 메서드를 호출 표시줄의 배경 이미지입니다. 배경 이미지 목록은 관리 되는 포함 된 여 [CMFCToolBarImages 클래스](../../mfc/reference/cmfctoolbarimages-class.md) 개체입니다.  
  
##  <a name="setdefaultstate"></a>CMFCOutlookBarPane::SetDefaultState  
 Outlook 표시줄 창을 원래 단추 집합을 다시 설정합니다.  
  
```  
void SetDefaultState();
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 원래 집합에 Outlook 표시줄 단추를 복원합니다. 이 방법은 `CMFCOutlookBarPane::RestoreOriginalstate`제외 하 고 Outlook 표시줄 창의 다시 그리기를 트리거하지 않습니다.  
  
##  <a name="setextraspace"></a>CMFCOutlookBarPane::SetExtraSpace  
 Outlook 표시줄 창에 단추 주위에 사용 되는 패딩 픽셀 수를 설정 합니다.  
  
```  
void SetExtraSpace()  
```  
  
##  <a name="settextcolor"></a>CMFCOutlookBarPane::SetTextColor  
 Outlook 표시줄 창에 일반적인 및 강조 표시 된 텍스트의 색을 설정합니다.  
  
```  
void SetTextColor(
    COLORREF clrRegText,  
    COLORREF clrSelText=0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `clrRegText`  
 선택 되지 않은 텍스트에 대 한 새로운 색을 지정합니다.  
  
 [in] `clrSelText`  
 선택한 텍스트에 대 한 새로운 색을 지정합니다.  
  
##  <a name="settransparentcolor"></a>CMFCOutlookBarPane::SetTransparentColor  
 Outlook 표시줄 창에 대 한 투명 한 색을 설정합니다.  
  
```  
void SetTransparentColor(COLORREF color);
```  
  
### <a name="parameters"></a>매개 변수  
 `color`  
 새로운 투명 색을 지정합니다.  
  
### <a name="remarks"></a>설명  
 투명 한 색은 투명 한 이미지를 표시 해야 합니다. 이 이미지의이 색상의 모든 항목은 대신 배경색으로 그려집니다.  배경 및 전경 이미지의 혼합을 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarTabCtrl 클래스](../../mfc/reference/cmfcoutlookbartabctrl-class.md)
