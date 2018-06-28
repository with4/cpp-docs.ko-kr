---
title: CMFCToolBarsCustomizeDialog 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillAllCommandsList
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillCategoriesComboBox
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillCategoriesListBox
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetCommandName
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetCountInCategory
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetFlags
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::OnInitDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::PostNcDestroy
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarsCustomizeDialog [MFC], CMFCToolBarsCustomizeDialog
- CMFCToolBarsCustomizeDialog [MFC], FillAllCommandsList
- CMFCToolBarsCustomizeDialog [MFC], FillCategoriesComboBox
- CMFCToolBarsCustomizeDialog [MFC], FillCategoriesListBox
- CMFCToolBarsCustomizeDialog [MFC], GetCommandName
- CMFCToolBarsCustomizeDialog [MFC], GetCountInCategory
- CMFCToolBarsCustomizeDialog [MFC], GetFlags
- CMFCToolBarsCustomizeDialog [MFC], OnInitDialog
- CMFCToolBarsCustomizeDialog [MFC], PostNcDestroy
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b4c2d7de8c9be8aa33cd5849c089a2caac1271b
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041879"
---
# <a name="cmfctoolbarscustomizedialog-class"></a>CMFCToolBarsCustomizeDialog 클래스
모덜리스 탭 대화 상자 ( [CPropertySheet 클래스](../../mfc/reference/cpropertysheet-class.md)) 하는 도구 모음, 메뉴, 바로 가기 키, 사용자 정의 도구 및 응용 프로그램에서 비주얼 스타일을 사용자 지정할 수 있습니다. 일반적으로 사용자가 **도구** 메뉴에서 **사용자 지정** 을 선택하여 이 대화 상자에 액세스합니다.  
  
 **사용자 지정** 대화 상자에 6 개의 탭: **명령을**, **도구 모음**, **도구**, **키보드**,  **메뉴**, 및 **옵션**합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCToolBarsCustomizeDialog : public CPropertySheet  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](#cmfctoolbarscustomizedialog)|`CMFCToolBarsCustomizeDialog` 개체를 생성합니다.|  
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)|도구 모음 단추 명령 목록에 삽입 된 **명령을** 페이지|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)|리소스 및 호출에서 메뉴를 로드 [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) 에서 해당 메뉴 명령 목록에 추가 하는 **명령을** 페이지.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)|리소스 및 호출에서 메뉴를 로드 [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) 에서 해당 메뉴 명령 목록에 추가 하는 **명령을** 페이지.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)|리소스에서 도구 모음을 로드합니다. 메뉴 호출의 각 명령에 대해 다음의 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) 에 명령 목록에 있는 단추를 삽입 하는 메서드는 **명령을** 지정한 범주 아래 페이지입니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::Create](#create)|표시는 **사용자 지정** 대화 상자.|  
|`CMFCToolBarsCustomizeDialog::EnableTools`|나중에 사용하기 위해 예약되어 있습니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|사용 하 여 새 도구 모음 만들기를 사용할지는 **사용자 지정** 대화 상자.|  
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|제공 된 정보를 표시 `CListBox` 의 명령과 개체는 **모든 명령을** 범주입니다.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)|제공 된 정보를 표시 `CComboBox` 에 있는 각 명령 범주 이름 가진 개체는 **사용자 지정** 대화 상자.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)|제공 된 정보를 표시 `CListBox` 에 있는 각 명령 범주 이름 가진 개체는 **사용자 지정** 대화 상자.|  
|[CMFCToolBarsCustomizeDialog::GetCommandName](#getcommandname)|지정한 명령 ID와 연결 된 이름을 검색합니다|  
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](#getcountincategory)|제공된 된 목록에서 지정 된 텍스트 레이블이 있는 항목의 수를 검색 합니다.|  
|[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)|대화 상자의 동작에 영향을 주는 플래그 집합을 검색 합니다.|  
|`CMFCToolBarsCustomizeDialog::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에서는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|사용자 도구 모음 단추 또는 메뉴 항목 아이콘을 사용자 지정할 수 있도록 이미지 편집기를 시작 합니다.|  
|[CMFCToolBarsCustomizeDialog::OnInitDialog](#oninitdialog)|속성 시트 초기화를 확대를 재정의 합니다. (재정의 [cpropertysheet:: Oninitdialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|  
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](#postncdestroy)|창이 제거 된 후 프레임 워크에서 호출 됩니다. (`CPropertySheet::PostNcDestroy`를 재정의합니다.)|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RemoveButton](#removebutton)|지정된 된 범주 또는 모든 범주에서 지정한 명령 ID 가진 단추를 제거합니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)|범주 목록 상자에서 범주에서 이름을 바꿉니다.는 **명령을** 탭 합니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)|명령 목록에 있는 단추에 대체는 **명령을** 새 도구 모음 단추 개체를 탭 합니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::SetUserCategory](#setusercategory)|범주 목록에 표시 되는 범주에 추가 된 **명령을** 탭 합니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)|사용자 정의 도구 목록이 올바른지 여부를 결정 하기 위해 프레임 워크에서 호출 됩니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|사용자 정의 도구 속성이 변경 될 때 프레임 워크에서 호출 됩니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAssignKey](#onassignkey)|지정 된 바로 가기 키 작업에 할당할 수 있는지 여부를 결정 합니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|사용자 정의 도구를 변경할 수 있는지 여부를 결정 합니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnInitToolsPage](#oninittoolspage)|사용자가 선택할 때 프레임 워크에서 호출는 **도구** 탭을 요청 합니다.|  
  
## <a name="remarks"></a>설명  
 표시 하는 **사용자 지정** 대화 상자에서 만들는 `CMFCToolBarsCustomizeDialog` 개체와 호출은 [CMFCToolBarsCustomizeDialog::Create](#create) 메서드.  
  
 반면는 **사용자 지정** 대화 상자가 활성화 되어, 응용 프로그램이 사용자 사용자 지정 작업을 제한 하는 특수 모드에서 작동 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 `CMFCToolBarsCustomizeDialog` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 명령의 목록 상자에서 도구 모음 단추에서 대체 하는 방법을 보여 줍니다는 **명령을** 페이지에서 사용 하 여 새 도구 모음을 만들 수 있도록는 **사용자 지정** 대화 상자 및 표시는  **사용자 지정** 대화 상자. 이 코드 조각은의 일부인는 [IE 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 `CMFCToolBarsCustomizeDialog`   
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxToolBarsCustomizeDialog.h  
  
##  <a name="addbutton"></a>  CMFCToolBarsCustomizeDialog::AddButton  
 도구 모음 단추 명령 목록에 삽입 된 **명령을** 페이지.  
  
```  
void AddButton(
    UINT uiCategoryId,  
    const CMFCToolBarButton& button,  
    int iInsertBefore=-1);

void AddButton(
    LPCTSTR lpszCategory,  
    const CMFCToolBarButton& button,  
    int iInsertBefore=-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *uiCategoryId*  
 단추를 삽입할 대상 범주 ID를 지정 합니다.  
  
 [in] *단추*  
 삽입할 단추에 지정 합니다.  
  
 [in] *iInsertBefore*  
 되기까지의 삽입 된 도구 모음 단추의 인덱스를 지정 합니다.  
  
 [in] *lpszCategory*  
 단추를 삽입할 범주 문자열을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 `AddButton` 메서드 (예: ID_FILE_MRU_FILE1) 표준 명령 Id가 지정 된 단추 무시, 허용 되지 않는 명령 (참조 [CMFCToolBar::IsCommandPermitted](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) 단추는 dummy 및 합니다.  
  
 이 메서드는와 동일한 형식의 새 개체를 만듭니다 `button` (일반적으로 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)) 단추의 런타임 클래스를 사용 하 여 합니다. 그런 다음 연속 호출 [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom) 단추의 데이터 멤버를 복사할 복사에 지정된 된 범주를 삽입 합니다.  
  
 새로 만들기 단추를 삽입할 때 받은 `OnAddToCustomizePage` 알림입니다.  
  
 경우 `iInsertBefore` -1 이면 단추 범주 목록에 추가 됩니다; 그렇지 않으면 지정된 된 인덱스를 가진 항목 앞 삽입 됩니다.  
  
### <a name="example"></a>예  
 다음 예제에서는 사용 하는 `AddButton` 의 메서드는 `CMFCToolBarsCustomizeDialog` 클래스. 이 코드 조각은의 일부인는 [슬라이더 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_Slider#1](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]  
  
##  <a name="addmenu"></a>  CMFCToolBarsCustomizeDialog::AddMenu  
 리소스 및 호출에서 메뉴를 로드 [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) 에서 해당 메뉴 명령 목록에 추가 하는 **명령을** 페이지.  
  
```  
BOOL AddMenu(UINT uiMenuResId);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *uiMenuResId*  
 로드 하는 메뉴의 리소스 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 메뉴 성공적으로 추가 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 호출에서 `AddMenuCommands`, *bPopup* 은 `FALSE`합니다. 결과적으로, 해당 메서드는 하위 메뉴 명령 목록에 포함 된 메뉴 항목 추가 되지 않습니다. 이 메서드는 명령 목록에 하위 메뉴에 메뉴 항목 추가지 않습니다.  
  
##  <a name="addmenucommands"></a>  CMFCToolBarsCustomizeDialog::AddMenuCommands  
 명령 목록에 항목을 추가 **명령을** 페이지를 지정된 된 메뉴에 있는 모든 항목을 나타냅니다.  
  
```  
void AddMenuCommands(
    const CMenu* pMenu,  
    BOOL bPopup,  
    LPCTSTR lpszCategory=NULL,  
    LPCTSTR lpszMenuPath=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pMenu*  
 추가할 CMenu 개체에 대 한 포인터입니다.  
  
 [in] *bPopup*  
 명령 목록에 팝업 메뉴 항목을 삽입할 것인지 지정 합니다.  
  
 [in] *lpszCategory*  
 메뉴를 삽입 하는 범주 이름입니다.  
  
 [in] *lpszMenuPath*  
 명령에 표시 될 때 이름에 추가 하는 접두사는 **모든 범주** 목록입니다.  
  
### <a name="remarks"></a>설명  
 `AddMenuCommands` 메서드 루프의 모든 메뉴 항목에 대해 *pMenu*합니다. 이 메서드는 하위 메뉴를 포함 하지 않는 각 메뉴 항목을 만듭니다는 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md) 개체와 호출 된 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) 도구 모음으로 메뉴 항목을 추가 하는 메서드 단추 명령 목록에는 **명령을** 페이지. 구분 기호는이 과정에서 무시 됩니다.  
  
 경우 *bPopup* 은 `TRUE`,이 메서드는 하위 메뉴가 있는 각 메뉴 항목에 대 한 만듭니다는 [CMFCToolBarMenuButton 클래스](../../mfc/reference/cmfctoolbarmenubutton-class.md) 개체를 호출 하 여 명령 목록에 삽입 `AddButton` . 그렇지 않으면 하위 메뉴를 포함 하는 메뉴 항목 명령 목록에 표시 되지 않습니다. 두 경우 모두 때 `AddMenuCommands` 메뉴 항목을 발견 하위 메뉴가 호출 자체으로 하위 메뉴에 대 한 포인터를 전달 하는 재귀적으로 *pMenu* 매개 변수를 하위 메뉴의 레이블을 추가 하 고 *lpszMenuPath*.  
  
##  <a name="addtoolbar"></a>  CMFCToolBarsCustomizeDialog::AddToolBar  
 리소스에서 도구 모음을 로드합니다. 메뉴 호출의 각 명령에 대해 다음의 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) 에 명령 목록에 있는 단추를 삽입 하는 메서드는 **명령을** 지정한 범주 아래 페이지입니다.  
  
```  
BOOL AddToolBar(
    UINT uiCategoryId,  
    UINT uiToolbarResId);

BOOL AddToolBar(
    LPCTSTR lpszCategory,  
    UINT uiToolbarResId);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *uiCategoryId*  
 도구 모음을 추가 하는 범주 리소스 ID를 지정 합니다.  
  
 [in] *uiToolbarResId*  
 명령을 명령 목록에 삽입 되는 도구 모음 리소스 ID를 지정 합니다.  
  
 [in] *lpszCategory*  
 추가할 도구 모음 범주의 이름을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="example"></a>예  
 다음 예제에서는 사용 하는 `AddToolBar` 에서 메서드는 `CMFCToolBarsCustomizeDialog` 클래스. 이 코드 조각은 [워드 패드 샘플](../../visual-cpp-samples.md)의 일부입니다.  
  
 [!code-cpp[NVC_MFC_WordPad#11](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]  
  
### <a name="remarks"></a>설명  
 각 명령을 나타내는 데 사용 되는 컨트롤은 한 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md) 개체입니다. 도구 모음을 추가한 후으로 바꿀 수 있습니다 단추 파생 형식의 컨트롤 호출 하 여 [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)합니다.  
  
##  <a name="checktoolsvalidity"></a>  CMFCToolBarsCustomizeDialog::CheckToolsValidity  
 사용자 도구 목록의 유효성을 확인 합니다.  
  
```  
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *lstTools*  
 목록 확인 하는 사용자 정의 도구입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 사용자 정의 도구 목록에 유효한 상태가 아니면 `FALSE`합니다. 기본 구현에서는 항상 `TRUE`을 반환합니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크에서 반환 하는 사용자 지정 도구를 나타내는 개체의 유효성을 확인 하려면이 메서드를 호출 [CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)합니다.  
  
 재정의 `CheckToolsValidity` 에서 파생 된 클래스에서 메서드가 `CMFCToolBarsCustomizeDialog` 사용자 대화 상자를 닫기 전에 사용자 도구를 유효성을 검사 하려는 경우. 이 메서드가 반환 하는 경우 `FALSE` 클릭 하면 중 하나는 **닫기** 대화 상자나 단추 오른쪽 위 모퉁이의 단추 **닫기** 대화 상자의 오른쪽 아래 모서리에는 대화 상자에 표시 된 **도구** 닫는 대신 탭 합니다. 이 메서드가 반환 하는 경우 `FALSE` 에서 멀리 이동 하는 탭을 클릭 하면는 **도구** 탭 탐색 발생 하지 않습니다. 유효성 검사에 실패 원인이 된 문제를 사용자에 게 알리는 적절 한 메시지 상자가 표시 해야 합니다.  
  
##  <a name="cmfctoolbarscustomizedialog"></a>  CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog  
 `CMFCToolBarsCustomizeDialog` 개체를 생성합니다.  
  
```  
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,  
    BOOL bAutoSetFromMenus = FALSE,  
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),  
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pWndParentFrame*  
 부모 프레임에 대 한 포인터입니다. 이 매개 변수는 `NULL`이 아니어야 합니다.  
  
 [in] *bAutoSetFromMenus*  
 에 메뉴 명령을 메뉴에서 명령 목록을 추가할지 여부를 지정 하는 부울 값은 **명령을** 페이지. 이 매개 변수가 `TRUE`, 메뉴 명령을 추가 됩니다. 그렇지 않으면 메뉴 명령은 추가 되지 않습니다.  
  
 [in] *uiFlags*  
 대화 상자의 동작에 영향을 주는 플래그의 조합입니다. 이 매개 변수는 다음 값 중 하나 이상을 하나일 수 있습니다.  
  
- `AFX_CUSTOMIZE_MENU_SHADOWS`  
  
- `AFX_CUSTOMIZE_TEXT_LABELS`  
  
- `AFX_CUSTOMIZE_MENU_ANIMATIONS`  
  
- `AFX_CUSTOMIZE_NOHELP`  
  
- `AFX_CUSTOMIZE_CONTEXT_HELP`  
  
- `AFX_CUSTOMIZE_NOTOOLS`  
  
- `AFX_CUSTOMIZE_MENUAMPERS`  
  
- `AFX_CUSTOMIZE_NO_LARGE_ICONS`  
  
 [in] *plistCustomPages*  
 목록에 대 한 포인터 `CRuntimeClass` 추가 사용자 지정 페이지를 지정 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 *plistCustomPages* 매개 변수 목록에 참조 `CRuntimeClass` 추가 사용자 지정 페이지를 지정 하는 개체입니다. 생성자를 사용 하 여 더 많은 페이지 대화 상자에 추가 된 [CRuntimeClass::CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject) 메서드. CustomPages 샘플 더 많은 페이지를 추가 하는 예제에 대 한 참조는 **사용자 지정** 대화 상자.  
  
 에 전달할 수 있는 값에 대 한 자세한 내용은 *uiFlags* 매개 변수를 참조 [CMFCToolBarsCustomizeDialog::GetFlags](#getflags)합니다.  
  
### <a name="example"></a>예  
 다음 예제에서는의 개체를 생성 하는 `CMFCToolBarsCustomizeDialog` 클래스입니다. 이 코드 조각은의 일부인는 [사용자 지정 페이지 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_CustomPages#3](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]  
  
##  <a name="create"></a>  CMFCToolBarsCustomizeDialog::Create  
 표시는 **사용자 지정** 대화 상자.  
  
```  
virtual BOOL Create();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 사용자 지정 속성 시트를 성공적으로 만들 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 호출 된 `Create` 메서드는 클래스를 완전히 초기화 된 후에 합니다.  
  
##  <a name="enableuserdefinedtoolbars"></a>  CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars  
 사용 하 여 새 도구 모음 만들기를 사용할지는 **사용자 지정** 대화 상자.  
  
```  
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *bEnable*  
 `TRUE` 사용자 정의 도구 모음;를 사용 하도록 설정 하려면 `FALSE` 하려면 도구 모음을 사용 하지 않도록 설정 합니다.  
  
### <a name="remarks"></a>설명  
 경우 *bEnable* 은 `TRUE`, **새로**, **이름 바꾸기** 및 **삭제** 단추에 표시 되는 **도구 모음**  페이지.  
  
 기본적으로 또는 *bEnable* 은 `FALSE`, 이러한 단추 표시 되지 않으며 사용자는 새 도구 모음을 정의할 수 없습니다.  
  
##  <a name="fillallcommandslist"></a>  CMFCToolBarsCustomizeDialog::FillAllCommandsList  
 제공 된 정보를 표시 `CListBox` 의 명령과 개체는 **모든 명령을** 범주입니다.  
  
```  
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `wndListOfCommands`  
 에 대 한 참조는 `CListBox` 채울 개체입니다.  
  
### <a name="remarks"></a>설명  
 **모든 명령을** 범주에는 모든 범주의 명령을 포함 합니다. [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) 에 제공 된 단추와 연결 하는 명령을 추가 하는 메서드는 **모든 명령을** 범주에 있습니다.  
  
 이 메서드는 제공 된 콘텐츠를 지웁니다 `CListBox` 의 명령과 채우기 전에 개체는 **모든 명령을** 범주입니다.  
  
 `CMFCMousePropertyPage` 클래스가이 메서드를 사용 하 여 두 번 클릭 이벤트 목록 상자를 채웁니다.  
  
##  <a name="fillcategoriescombobox"></a>  CMFCToolBarsCustomizeDialog::FillCategoriesComboBox  
 제공 된 정보를 표시 `CComboBox` 에 있는 각 명령 범주 이름 가진 개체는 **사용자 지정** 대화 상자.  
  
```  
void FillCategoriesComboBox(
    CComboBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] *wndCategory*  
 에 대 한 참조는 `CComboBox` 채울 개체입니다.  
  
 [in] *bAddEmpty*  
 명령을 갖지 않는 콤보 상자에 범주를 추가할 것인지를 지정 하는 부울 값입니다. 이 매개 변수가 `TRUE`, 빈 범주 콤보 상자에 추가 됩니다. 그렇지 않으면 빈 범주 추가 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 이 방법은 [CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox) 메서드 제외 하 고이 방법은 한 `CComboBox` 개체입니다.  
  
 이 메서드는의 내용을 지우지 않습니다는 `CComboBox` 채우지 하기 전에 개체입니다. 보장 하는 **모든 명령을** 범주는 콤보 상자에 있는 마지막 항목입니다.  
  
 사용 하 여 새 명령 범주를 추가할 수는 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) 메서드. 사용 하 여 기존 범주의 이름을 변경할 수 있습니다는 [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) 메서드.  
  
 `CMFCToolBarsKeyboardPropertyPage` 및 `CMFCKeyMapDialog` 키보드 매핑 분류 하려면이 메서드를 사용 하는 클래스입니다.  
  
##  <a name="fillcategorieslistbox"></a>  CMFCToolBarsCustomizeDialog::FillCategoriesListBox  
 제공 된 정보를 표시 `CListBox` 에 있는 각 명령 범주 이름 가진 개체는 **사용자 지정** 대화 상자.  
  
```  
void FillCategoriesListBox(
    CListBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] *wndCategory*  
 에 대 한 참조는 `CListBox` 채울 개체입니다.  
  
 [in] *bAddEmpty*  
 명령을 갖지 않는 목록 상자에 범주를 추가할 것인지를 지정 하는 부울 값입니다. 이 매개 변수가 `TRUE`, 빈 범주 목록 상자에 추가 됩니다. 그렇지 않으면 빈 범주 추가 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 이 방법은 [CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox) 메서드 제외 하 고이 방법은 한 `CListBox` 개체입니다.  
  
 이 메서드는의 내용을 지우지 않습니다는 `CListBox` 채우지 하기 전에 개체입니다. 보장 하는 **모든 명령을** 범주는 목록 상자에 있는 마지막 항목입니다.  
  
 사용 하 여 새 명령 범주를 추가할 수는 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) 메서드. 사용 하 여 기존 범주의 이름을 변경할 수 있습니다는 [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) 메서드.  
  
 `CMFCToolBarsCommandsPropertyPage` 클래스가이 메서드를 사용 하 여 각 명령 범주와 관련 된 명령 목록을 표시 합니다.  
  
##  <a name="getcommandname"></a>  CMFCToolBarsCustomizeDialog::GetCommandName  
 지정한 명령 ID와 연결 된 이름을 검색합니다  
  
```  
LPCTSTR GetCommandName(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *uiCmd*  
 ID 검색 하기 위한 명령입니다.  
  
### <a name="return-value"></a>반환 값  
 지정한 명령 ID와 연결 된 이름 또는 `NULL` 명령이 존재 하지 않는 경우.  
  
##  <a name="getcountincategory"></a>  CMFCToolBarsCustomizeDialog::GetCountInCategory  
 제공된 된 목록에서 지정 된 텍스트 레이블이 있는 항목의 수를 검색 합니다.  
  
```  
int GetCountInCategory(
    LPCTSTR lpszItemName,  
    const CObList& lstCommands) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *lpszItemName*  
 일치 하는 텍스트 레이블.  
  
 [in] *lstCommands*  
 포함 하는 목록에 대 한 참조 `CMFCToolBarButton` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 항목을 제공 된 개수 인 텍스트 레이블 equals 목록 *lpszItemName*합니다.  
  
### <a name="remarks"></a>설명  
 제공 된 개체 목록에서 각 요소 형식 이어야 합니다 `CMFCToolBarButton`합니다. 이 메서드는 비교 *lpszItemName* 와 [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext) 데이터 멤버입니다.  
  
##  <a name="getflags"></a>  CMFCToolBarsCustomizeDialog::GetFlags  
 대화 상자의 동작에 영향을 주는 플래그 집합을 검색 합니다.  
  
```  
UINT GetFlags() const;  
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자의 동작에 영향을 주는 플래그 집합이 있습니다.  
  
### <a name="remarks"></a>설명  
 값을 검색 하는이 메서드는 *uiFlags* 생성자에 전달 되는 매개 변수입니다. 반환 값은 다음 값 중 하나 이상을 하나일 수 있습니다.  
  
 `AFX_CUSTOMIZE_MENU_SHADOWS`  
 메뉴의 그림자 모양을 지정할 수 있습니다.  
  
 `AFX_CUSTOMIZE_TEXT_LABELS`  
 도구 모음 단추 이미지 아래 텍스트 레이블을 표시할지 여부를 지정할 수 있습니다.  
  
 `AFX_CUSTOMIZE_MENU_ANIMATIONS`  
 메뉴 애니메이션 스타일을 지정할 수 있습니다.  
  
 `AFX_CUSTOMIZE_NOHELP`  
 사용자 지정 대화 상자에서 도움말 단추를 제거합니다.  
  
 `AFX_CUSTOMIZE_CONTEXT_HELP`  
 사용 하도록 설정 된 `WS_EX_CONTEXTHELP` 비주얼 스타일입니다.  
  
 `AFX_CUSTOMIZE_NOTOOLS`  
 제거는 **도구** 사용자 지정 대화 상자에서 페이지. 이 플래그는 응용 프로그램에서 사용 하는 경우에 유효는 `CUserToolsManager` 클래스입니다.  
  
 `AFX_CUSTOMIZE_MENUAMPERS`  
 단추 캡션을 앰퍼샌드를 포함 하도록 허용 ( **&**) 문자.  
  
 `AFX_CUSTOMIZE_NO_LARGE_ICONS`  
 제거는 **큰 아이콘** 사용자 지정 대화 상자에서 옵션입니다.  
  
 에 대 한 자세한 내용은 `WS_EX_CONTEXTHELP` 비주얼 스타일 참조 [확장 창 스타일](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)합니다.  
  
##  <a name="onafterchangetool"></a>  CMFCToolBarsCustomizeDialog::OnAfterChangeTool  
 이 발생 된 후에 즉시 변경 하는 사용자 도구에 응답 합니다.  
  
```  
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>매개 변수  
 [out에서] *pSelTool*  
 변경 된 사용자 도구 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 사용자가 사용자 정의 도구의 속성을 변경할 때 프레임 워크에서 호출 됩니다. 기본 구현은 아무 작업도 수행하지 않습니다. 파생 된 클래스에서이 메서드를 재정의 `CMFCToolBarsCustomizeDialog` 사용자 도구에 대 한 변경 발생 한 후 처리를 수행 합니다.  
  
##  <a name="onassignkey"></a>  CMFCToolBarsCustomizeDialog::OnAssignKey  
 사용자 정의 바로 가기 키의 유효성을 검사 합니다.  
  
```  
virtual BOOL OnAssignKey(ACCEL* pAccel);
```  
  
### <a name="parameters"></a>매개 변수  
 [out에서] *pAccel*  
 로 표시 되는 제안 된 키보드 할당에 대 한 포인터는 [가속](http://msdn.microsoft.com/library/windows/desktop/ms646340) 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 키에 할당 한 경우 또는 `FALSE` 키를 할당할 수 없는 경우. 기본 구현에서는 항상 `TRUE`을 반환합니다.  
  
### <a name="remarks"></a>설명  
 사용자는 새 바로 가기 키를 지정 하거나 정의 하는 사용자와 바로 가기 키 유효성을 검사 하는 경우 추가 처리를 수행 하는 파생된 클래스에서이 메서드를 재정의 합니다. 바로 가기를 할당 되지 않도록 하려면 반환 `FALSE`합니다. 또한 메시지 상자를 표시 하거나 그렇지 않으면 바로 가기 키 거부 된 이유는 이유는 사용자에 게 알리는 해야 합니다.  
  
##  <a name="onbeforechangetool"></a>  CMFCToolBarsCustomizeDialog::OnBeforeChangeTool  
 사용자 지정 때 처리를 수행 하는 사용자 도구에 대 한 변경 사용자가 변경 내용을 적용 하려고 합니다.  
  
```  
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>매개 변수  
 [out에서] *pSelTool*  
 교체 하려고 하는 사용자 도구 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 사용자 정의 도구의 속성 변경 되려고 할 때 프레임 워크에서 호출 됩니다. 기본 구현은 아무 작업도 수행하지 않습니다. 재정의 `OnBeforeChangeTool` 에서 파생 된 클래스에서 메서드가 `CMFCToolBarsCustomizeDialog` 리소스 해제와 같은 사용자 도구에 대 한 변경 발생 전에 처리 작업을 수행 하려는 경우는 *pSelTool* 사용 합니다.  
  
##  <a name="onedittoolbarmenuimage"></a>  CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage  
 사용자 도구 모음 단추 또는 메뉴 항목 아이콘을 사용자 지정할 수 있도록 이미지 편집기를 시작 합니다.  
  
```  
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,  
    CBitmap& bitmap,  
    int nBitsPerPixel);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pWndParent*  
 부모 창에 대 한 포인터입니다.  
  
 [in] *비트맵*  
 Bitmap 개체 편집에 대 한 참조입니다.  
  
 [in] *nBitsPerPixel*  
 비트 / 픽셀 색 해상도 비트맵입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 변경 내용이 커밋되; 경우 그렇지 않으면 `FALSE`합니다. 대화 상자를 표시 하 고 반환 하는 기본 구현은 `TRUE` 클릭 하면 **확인**, 또는 `FALSE` 클릭 하면 **취소** 또는 **닫기** 단추입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 사용자 이미지 편집기를 실행할 때 프레임 워크에서 호출 됩니다. 기본 구현 표시 [CMFCImageEditorDialog 클래스](../../mfc/reference/cmfcimageeditordialog-class.md) 대화 상자. 재정의 `OnEditToolbarMenuImage` 사용자 지정 이미지 편집기를 사용 하려면 파생된 클래스에서.  
  
##  <a name="oninitdialog"></a>  CMFCToolBarsCustomizeDialog::OnInitDialog  
 속성 시트 초기화를 확대를 재정의 합니다.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>반환 값  
 호출의 결과 [cpropertysheet:: Oninitdialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog) 메서드.  
  
### <a name="remarks"></a>설명  
 이 메서드가 기본 클래스 구현을 확장 [cpropertysheet:: Oninitdialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog)를 표시 하 여는 **닫기** 대화 상자 현재 화면 크기에 맞는지 확인 하 여를 이동 하 여 단추는 **도움말** 단추 대화 상자의 왼쪽 아래 모서리를 합니다.  
  
##  <a name="oninittoolspage"></a>  CMFCToolBarsCustomizeDialog::OnInitToolsPage  
 프레임 워크에서 알림을 처리 하는 **도구** 페이지를 초기화 하려고 합니다.  
  
```  
virtual void OnInitToolsPage();
```  
  
### <a name="remarks"></a>설명  
 기본 구현은 아무 작업도 수행하지 않습니다. 이 알림을 처리 하는 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="postncdestroy"></a>  CMFCToolBarsCustomizeDialog::PostNcDestroy  
 창이 제거 된 후 프레임 워크에서 호출 됩니다.  
  
```  
virtual void PostNcDestroy();
```  
  
### <a name="remarks"></a>설명  
 이 메서드가 기본 클래스 구현을 확장 `CPropertySheet::PostNcDestroy`, 이전 모드로 응용 프로그램을 복원 하 여 합니다.  
  
 [CMFCToolBarsCustomizeDialog::Create](#create) 메서드는 사용자 지정 작업에 사용자를 제한 하는 특수 모드에서 응용 프로그램을 넣습니다.  
  
##  <a name="removebutton"></a>  CMFCToolBarsCustomizeDialog::RemoveButton  
 지정된 된 범주 또는 모든 범주에서 지정한 명령 ID 가진 단추를 제거합니다.  
  
```  
int RemoveButton(
    UINT uiCategoryId,  
    UINT uiCmdId);

int RemoveButton(
    LPCTSTR lpszCategory,  
    UINT uiCmdId);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *uiCategoryId*  
 단추를 제거 하는 범주 ID를 지정 합니다.  
  
 [in] *uiCmdId*  
 단추의 명령 ID를 지정합니다.  
  
 [in] *lpszCategory*  
 단추를 제거 하는 범주의 이름을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 제거 단추 또는 지정된 된 명령 ID가 지정한 범주에 없는 경우-1의 0부터 시작 하는 인덱스입니다. 경우 *uiCategoryId* -1 이면 반환 값은 0입니다.  
  
### <a name="remarks"></a>설명  
 모든 범주에서 단추를 제거 하려면이 메서드와 집합의 첫 번째 오버 로드를 호출 *uiCategoryId* 를-1입니다.  
  
##  <a name="renamecategory"></a>  CMFCToolBarsCustomizeDialog::RenameCategory  
 범주 목록 상자에서 범주에서 이름을 바꿉니다.는 **명령을** 페이지.  
  
```  
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,  
    LPCTSTR lpszCategoryNew);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *lpszCategoryOld*  
 변경 하려면 범주 이름입니다.  
  
 [in] *lpszCategoryNew*  
 새 범주 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 범주 이름은 고유 해야 합니다.  
  
##  <a name="replacebutton"></a>  CMFCToolBarsCustomizeDialog::ReplaceButton  
 명령 목록 상자에서 도구 모음 단추에서 대체는 **명령을** 페이지.  
  
```  
void ReplaceButton(
    UINT uiCmd,  
    const CMFCToolBarButton& button);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *uiCmd*  
 교체 단추의 명령을 지정 합니다.  
  
 [in] *단추*  
 A **const** 이전 단추를 대체 하는 도구 모음 단추 개체에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 때 [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu), [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands), 또는 [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar) 추가 명령의 **명령을** 페이지의 형태로 명령 인지는 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md) 개체 (또는 [CMFCToolBarMenuButton 클래스](../../mfc/reference/cmfctoolbarmenubutton-class.md) 메뉴에 대 한 개체 항목으로 추가 하는 하위 메뉴가 있는 `AddMenuCommands`). 프레임 워크는 또한 명령을 자동으로 추가 하려면 다음 세 가지 방법을 호출 합니다. 대신 파생된 된 형식으로 나타내야 하는 명령을 호출 `ReplaceButton` 파생 형식의 단추에 전달 합니다.  
  
### <a name="example"></a>예  
 다음 예제에서는 사용 하는 `ReplaceButton` 에서 메서드는 `CMFCToolBarsCustomizeDialog` 클래스. 이 코드 조각은의 일부인는 [Visual Studio 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#34](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]  
  
##  <a name="setusercategory"></a>  CMFCToolBarsCustomizeDialog::SetUserCategory  
 범주 목록에서 범주를 지정는 **명령을** 페이지는 사용자의 범주입니다. 호출 하기 전에이 함수를 호출 해야 [CMFCToolBarsCustomizeDialog::Create](#create)합니다.  
  
```  
BOOL SetUserCategory(LPCTSTR lpszCategory);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *lpszCategory*  
 범주 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 사용자 범주 설정 프레임 워크에서 현재 사용 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPropertySheet 클래스](../../mfc/reference/cpropertysheet-class.md)
