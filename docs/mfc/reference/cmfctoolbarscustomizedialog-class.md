---
title: "CMFCToolBarsCustomizeDialog 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CMFCToolBarsCustomizeDialog class
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
caps.latest.revision: 28
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
ms.openlocfilehash: 069498d958dd5d9c3befc2a179c67636ce0ac9ae
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarscustomizedialog-class"></a>CMFCToolBarsCustomizeDialog 클래스
모덜리스 탭 대화 상자 ( [CPropertySheet 클래스](../../mfc/reference/cpropertysheet-class.md)) 하는 도구 모음, 메뉴, 바로 가기 키, 사용자 정의 형식 및 응용 프로그램에서 비주얼 스타일을 사용자 지정할 수 있습니다. 일반적으로 사용자가 **도구** 메뉴에서 **사용자 지정** 을 선택하여 이 대화 상자에 액세스합니다.  
  
 **사용자 지정** 대화 상자에 여섯 개의 탭: **명령을**, **도구 모음**, **도구**, **키보드**, **메뉴**, 및 **옵션**합니다.  
  
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
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddButton](#addbutton)|도구 모음 단추 명령 목록에 삽입 된 **명령을** 페이지|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)|리소스 및 호출에서 메뉴를 로드 [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) 에서 해당 메뉴 명령 목록에 추가 하는 **명령을** 페이지입니다.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)|리소스 및 호출에서 메뉴를 로드 [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) 에서 해당 메뉴 명령 목록에 추가 하는 **명령을** 페이지입니다.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)|리소스 로부터 도구 모음을 로드합니다. 메뉴 호출의 각 명령에 대해 다음의 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) 에 명령 목록에 있는 단추를 삽입 하는 메서드는 **명령을** 지정된 된 범주에는 페이지입니다.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::Create](#create)|표시는 **사용자 지정** 대화 상자입니다.|  
|`CMFCToolBarsCustomizeDialog::EnableTools`|나중에 사용하기 위해 예약되어 있습니다.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|사용 하 여 새 도구 모음 만들기를 사용할지는 **사용자 지정** 대화 상자입니다.|  
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|제공 된 정보를 표시 `CListBox` 에서 명령 사용 하 여 개체의 **모든 명령을** 범주입니다.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)|제공 된 정보를 표시 `CComboBox` 의 각 명령 범주 이름 가진 개체는 **사용자 지정** 대화 상자입니다.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)|제공 된 정보를 표시 `CListBox` 의 각 명령 범주 이름 가진 개체는 **사용자 지정** 대화 상자입니다.|  
|[CMFCToolBarsCustomizeDialog::GetCommandName](#getcommandname)|지정한 명령 ID와 연결 된 이름을 검색합니다|  
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](#getcountincategory)|주어진된 텍스트 레이블을 추가 하는 제공된 된 목록에 있는 항목의 수를 가져옵니다.|  
|[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)|대화 상자의 동작에 영향을 주는 플래그 집합을 검색 합니다.|  
|`CMFCToolBarsCustomizeDialog::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식으로 연결 된 개체입니다.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|사용자는 도구 모음 단추 또는 메뉴 항목 아이콘을 사용자 지정할 수 있도록 이미지 편집기를 시작 합니다.|  
|[CMFCToolBarsCustomizeDialog::OnInitDialog](#oninitdialog)|재정의 속성 시트 초기화를 보강할 수 있습니다. (재정의 [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|  
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](#postncdestroy)|창 소멸 된 후에 프레임 워크에 의해 호출 됩니다. (`CPropertySheet::PostNcDestroy`를 재정의합니다.)|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::RemoveButton](#removebutton)|모든 범주 또는 지정된 된 범주에서 지정한 명령 id를 제거합니다.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)|범주 목록 상자에서 범주에서 이름을 바꿉니다.는 **명령을** 탭 합니다.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)|명령 목록에 있는 단추에 대체는 **명령을** 새 도구 모음 단추 개체를 사용 하 여 탭 합니다.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::SetUserCategory](#setusercategory)|목록에 표시 되는 범주에 범주를 추가 **명령을** 탭 합니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)|사용자 정의 도구 목록에 유효한 지 여부를 결정 하는 프레임 워크에서 호출 됩니다.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|사용자 정의 도구의 속성이 변경 될 때 프레임 워크에 의해 호출 됩니다.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnAssignKey](#onassignkey)|지정 된 바로 가기 키 작업에 할당할 수 있는지 여부를 결정 합니다.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|사용자 정의 도구를 변경할 수 있는지 여부를 결정 합니다.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnInitToolsPage](#oninittoolspage)|사용자가 선택 된 프레임 워크에서 호출는 **도구** 탭 요청 됩니다.|  
  
## <a name="remarks"></a>주의  
 표시 하는 **사용자 지정** 대화 상자에서 만들는 `CMFCToolBarsCustomizeDialog` 개체와 호출은 [CMFCToolBarsCustomizeDialog::Create](#create) 메서드.  
  
 반면는 **사용자 지정** 대화 상자가 활성화 되어, 응용 프로그램이 사용자 지정 작업에 사용자를 제한 하는 특수 모드에서 작동 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CMFCToolBarsCustomizeDialog` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 명령의 목록 상자에서 도구 모음 단추에서 대체 하는 방법을 보여는 **명령을** 페이지에서 사용 하 여 새 도구 모음을 만들 수 있도록는 **사용자 지정** 대화 상자 및 표시는 **사용자 지정** 대화 상자입니다. 이 코드 조각은의 일부인는 [IE 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_IEDemo #&4;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 `CMFCToolBarsCustomizeDialog`   
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxToolBarsCustomizeDialog.h  
  
##  <a name="addbutton"></a>CMFCToolBarsCustomizeDialog::AddButton  
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
 [in] `uiCategoryId`  
 단추를 삽입할 대상 범주 ID를 지정 합니다.  
  
 [in] `button`  
 삽입할 단추를 지정 합니다.  
  
 [in] `iInsertBefore`  
 전에 삽입 된 도구 모음 단추의 인덱스를 지정 합니다.  
  
 [in] `lpszCategory`  
 단추를 삽입할 범주 문자열을 지정 합니다.  
  
### <a name="remarks"></a>주의  
 `AddButton` 메서드 (예: ID_FILE_MRU_FILE1) 표준 명령 Id가 지정 된 단추 무시, 허용 되지 않는 명령 (참조 [CMFCToolBar::IsCommandPermitted](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) 및 더미 단추입니다.  
  
 이 메서드는 동일한 형식의 새 개체를 만듭니다 `button` (일반적으로 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)) 단추의 런타임 클래스를 사용 하 여 합니다. 그런 다음 호출 [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom) 단추, 데이터 멤버를 복사 하려면 지정된 된 범주에 복사본을 삽입 합니다.  
  
 새로 만들기 단추를 삽입할 때 수신한는 `OnAddToCustomizePage` 알림.  
  
 경우 `iInsertBefore` -1 이면 단추 범주 목록에 추가 되 고, 그렇지 않으면 지정된 된 인덱스를 가진 항목 앞 삽입 됩니다.  
  
### <a name="example"></a>예제  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `AddButton` 의 메서드는 `CMFCToolBarsCustomizeDialog` 클래스입니다. 이 코드 조각은의 일부인는 [슬라이더 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_Slider #&1;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]  
  
##  <a name="addmenu"></a>CMFCToolBarsCustomizeDialog::AddMenu  
 리소스 및 호출에서 메뉴를 로드 [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) 에서 해당 메뉴 명령 목록에 추가 하는 **명령을** 페이지입니다.  
  
```  
BOOL AddMenu(UINT uiMenuResId);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiMenuResId`  
 로드 하는 메뉴의 리소스 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메뉴 추가 되었으면; 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 에 대 한 호출에서 `AddMenuCommands`, `bPopup` 는 `FALSE`합니다. 결과적으로,이 메서드는 하위 메뉴에 명령 목록이 포함 된 메뉴 항목을 추가 하지 않습니다. 이 메서드는 명령 목록에 하위 메뉴에 메뉴 항목 추가지 않습니다.  
  
##  <a name="addmenucommands"></a>CMFCToolBarsCustomizeDialog::AddMenuCommands  
 명령 목록에 항목을 추가 **명령을** 페이지를 지정한 메뉴에 있는 모든 항목을 나타냅니다.  
  
```  
void AddMenuCommands(
    const CMenu* pMenu,  
    BOOL bPopup,  
    LPCTSTR lpszCategory=NULL,  
    LPCTSTR lpszMenuPath=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMenu`  
 추가할 CMenu 개체에 대 한 포인터입니다.  
  
 [in] `bPopup`  
 명령 목록에 팝업 메뉴 항목을 삽입할 것인지 지정 합니다.  
  
 [in] `lpszCategory`  
 메뉴를 삽입 하는 범주의 이름입니다.  
  
 [in] `lpszMenuPath`  
 명령에 표시 될 때 이름에 추가 하는 접두사는 **모든 범주** 목록입니다.  
  
### <a name="remarks"></a>주의  
 `AddMenuCommands` 메서드 루프의 모든 메뉴 항목에 대해 `pMenu`합니다. 이 메서드는 하위 메뉴를 포함 하지 않는 각 메뉴 항목을 만듭니다는 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md) 개체와 호출 된 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) 에 명령 목록이를 도구 모음 단추와 메뉴 항목을 추가 하려면 메서드는 **명령을** 페이지. 구분 기호는이 과정에서 무시 됩니다.  
  
 경우 `bPopup` 는 `TRUE`,이 메서드는 하위 메뉴가 있는 각 메뉴 항목에 대 한 만듭니다는 [CMFCToolBarMenuButton 클래스](../../mfc/reference/cmfctoolbarmenubutton-class.md) 개체를 호출 하 여 명령 목록에 삽입 합니다 `AddButton`합니다. 그렇지 않으면 하위 메뉴를 포함 하는 메뉴 항목의 명령 목록에 표시 되지 않습니다. 두 경우 모두 때 `AddMenuCommands` 메뉴 항목을 발견 하위 메뉴가 호출 자체와 하위 메뉴에 대 한 포인터를 전달 하는 재귀적으로 `pMenu` 매개 변수 및 하위 메뉴를의 레이블을 추가 `lpszMenuPath`합니다.  
  
##  <a name="addtoolbar"></a>CMFCToolBarsCustomizeDialog::AddToolBar  
 리소스 로부터 도구 모음을 로드합니다. 메뉴 호출의 각 명령에 대해 다음의 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) 에 명령 목록에 있는 단추를 삽입 하는 메서드는 **명령을** 지정된 된 범주에는 페이지입니다.  
  
```  
BOOL AddToolBar(
    UINT uiCategoryId,  
    UINT uiToolbarResId);

BOOL AddToolBar(
    LPCTSTR lpszCategory,  
    UINT uiToolbarResId);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCategoryId`  
 도구 모음을 추가 하려면 범주 리소스 ID를 지정 합니다.  
  
 [in] `uiToolbarResId`  
 해당 명령을 명령 목록에 삽입 되는 도구 모음의 리소스 ID를 지정 합니다.  
  
 [in] `lpszCategory`  
 도구 모음에 추가할 범주의 이름을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="example"></a>예제  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `AddToolBar` 에서 메서드는 `CMFCToolBarsCustomizeDialog` 클래스입니다. 이 코드 조각은의 일부인는 [워드 패드 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_WordPad #&11;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]  
  
### <a name="remarks"></a>주의  
 각 명령을 나타내는 데 사용 되는 컨트롤은 한 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md) 개체입니다. 도구 모음에 추가한 후 바꿀 수 있습니다 단추는 파생 된 형식으로 제어 하 여 호출 하 여 [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)합니다.  
  
##  <a name="checktoolsvalidity"></a>CMFCToolBarsCustomizeDialog::CheckToolsValidity  
 사용자 도구 목록의 유효성을 확인 합니다.  
  
```  
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lstTools`  
 목록 확인 하는 사용자 지정 도구입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 유효 하 고, 그렇지 않으면 사용자 정의 도구 목록에 있으면 `FALSE`합니다. 기본 구현에서는 항상 반환 `TRUE`합니다.  
  
### <a name="remarks"></a>주의  
 반환 하는 사용자 정의 도구를 나타내는 개체의 유효성을 확인 하려면이 메서드를 호출 하는 프레임 워크 [CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)합니다.  
  
 재정의 `CheckToolsValidity` 에서 파생 된 클래스에서 메서드 `CMFCToolBarsCustomizeDialog` 사용자 대화 상자를 닫기 전에 사용자 도구의 유효성을 검사 하려는 경우. 이 메서드가 반환 하는 경우 `FALSE` 사용자가 하나는 **닫기** 대화 상자 또는 단추 오른쪽 위 모퉁이의 단추 **닫기** 대화 상자 대화 상자의 오른쪽 아래 구석에 표시는 **도구** 닫는 대신 탭 합니다. 이 메서드가 반환 하는 경우 `FALSE` 에서 멀리 이동 하려면 탭을 클릭 하면는 **도구** 탭 탐색 발생 하지 않습니다. 유효성 검사에 실패 원인이 된 문제를 사용자에 게 알리는 적절 한 메시지 상자가 표시 됩니다.  
  
##  <a name="cmfctoolbarscustomizedialog"></a>CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog  
 `CMFCToolBarsCustomizeDialog` 개체를 생성합니다.  
  
```  
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,  
    BOOL bAutoSetFromMenus = FALSE,  
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),  
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndParentFrame`  
 상위 프레임에 대 한 포인터입니다. 이 매개 변수는 `NULL`이 아니어야 합니다.  
  
 [in] `bAutoSetFromMenus`  
 모든 메뉴에서 메뉴 명령을 명령의 목록을 추가할 것인지를 지정 하는 부울 값은 **명령을** 페이지입니다. 이 매개 변수가 `TRUE`, 메뉴 명령에 추가 됩니다. 그렇지 않으면 메뉴 명령은 추가 되지 않습니다.  
  
 [in] `uiFlags`  
 대화 상자의 동작에 영향을 주는 플래그의 조합입니다. 이 매개 변수는 다음 값 중 하나 이상을 하나일 수 있습니다.  
  
- `AFX_CUSTOMIZE_MENU_SHADOWS`  
  
- `AFX_CUSTOMIZE_TEXT_LABELS`  
  
- `AFX_CUSTOMIZE_MENU_ANIMATIONS`  
  
- `AFX_CUSTOMIZE_NOHELP`  
  
- `AFX_CUSTOMIZE_CONTEXT_HELP`  
  
- `AFX_CUSTOMIZE_NOTOOLS`  
  
- `AFX_CUSTOMIZE_MENUAMPERS`  
  
- `AFX_CUSTOMIZE_NO_LARGE_ICONS`  
  
 [in] `plistCustomPages`  
 목록에 대 한 포인터 `CRuntimeClass` 추가 사용자 지정 페이지를 지정 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 `plistCustomPages` 매개 변수 목록에는 참조 `CRuntimeClass` 추가 사용자 지정 페이지를 지정 하는 개체입니다. 생성자를 사용 하 여 더 많은 페이지 대화 상자에 추가 된 [CRuntimeClass::CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject) 메서드. CustomPages 샘플을 더 많은 페이지를 추가 하는 예제에 대 한 참조는 **사용자 지정** 대화 상자입니다.  
  
 에 전달할 수 있는 값에 대 한 자세한 내용은 `uiFlags` 매개 변수를 참조 하십시오 [CMFCToolBarsCustomizeDialog::GetFlags](#getflags)합니다.  
  
### <a name="example"></a>예제  
 개체를 생성 하는 방법은 다음 예제는 `CMFCToolBarsCustomizeDialog` 클래스입니다. 이 코드 조각은의 일부인는 [사용자 지정 페이지 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_CustomPages #&3;](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]  
  
##  <a name="create"></a>CMFCToolBarsCustomizeDialog::Create  
 표시는 **사용자 지정** 대화 상자입니다.  
  
```  
virtual BOOL Create();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`사용자 지정 속성 시트를 성공적으로 만들면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 호출 된 `Create` 메서드는 클래스를 완전히 초기화 된 후에 합니다.  
  
##  <a name="enableuserdefinedtoolbars"></a>CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars  
 사용 하 여 새 도구 모음 만들기를 사용할지는 **사용자 지정** 대화 상자입니다.  
  
```  
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`사용자 지정 도구 모음;를 사용 하도록 설정 하려면 `FALSE` 를 도구 모음을 사용 하지 않도록 설정 합니다.  
  
### <a name="remarks"></a>주의  
 경우 `bEnable` 는 `TRUE`, **새로**, **이름 바꾸기** 및 **삭제** 단추에 표시 되는 **도구 모음** 페이지입니다.  
  
 기본적으로, 또는 `bEnable` 는 `FALSE`, 이러한 단추 표시 되지 않으며 사용자는 새 도구 모음을 정의할 수 없습니다.  
  
##  <a name="fillallcommandslist"></a>CMFCToolBarsCustomizeDialog::FillAllCommandsList  
 제공 된 정보를 표시 `CListBox` 에서 명령 사용 하 여 개체의 **모든 명령을** 범주입니다.  
  
```  
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `wndListOfCommands`  
 에 대 한 참조는 `CListBox` 채울 개체입니다.  
  
### <a name="remarks"></a>주의  
 **모든 명령을** 범주에는 모든 범주의 명령이 포함 되어 있습니다. [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) 에 제공 된 단추와 연결 하는 명령을 추가 하는 메서드는 **모든 명령을** 범주에 있습니다.  
  
 이 메서드는 제공 된 콘텐츠를 지웁니다 `CListBox` 개체에서 명령을 사용 하 여 채우기 전에 **모든 명령을** 범주입니다.  
  
 `CMFCMousePropertyPage` 클래스가이 메서드를 사용 하 여 두 번 클릭 이벤트 목록 상자를 채웁니다.  
  
##  <a name="fillcategoriescombobox"></a>CMFCToolBarsCustomizeDialog::FillCategoriesComboBox  
 제공 된 정보를 표시 `CComboBox` 의 각 명령 범주 이름 가진 개체는 **사용자 지정** 대화 상자입니다.  
  
```  
void FillCategoriesComboBox(
    CComboBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `wndCategory`  
 에 대 한 참조는 `CComboBox` 채울 개체입니다.  
  
 [in] `bAddEmpty`  
 명령을 갖지 않는 콤보 상자에 범주를 추가할 것인지를 지정 하는 부울 값입니다. 이 매개 변수가 `TRUE`, 빈 범주 콤보 상자에 추가 됩니다. 그렇지 않으면 빈 범주 추가 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 이 방법은 [CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox) 메서드가이 방법은 작동 한다는 점을 제외 하면는 `CComboBox` 개체입니다.  
  
 이 메서드는의 내용을 지우지 않습니다는 `CComboBox` 채우지 하기 전에 개체입니다. **모든 명령을** 범주는 콤보 상자에서 마지막 항목입니다.  
  
 사용 하 여 새 명령 범주를 추가할 수는 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) 메서드. 사용 하 여 기존 범주의 이름을 변경할 수는 [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) 메서드.  
  
 `CMFCToolBarsKeyboardPropertyPage` 및 `CMFCKeyMapDialog` 키보드 매핑을 분류 하는이 메서드를 사용 하는 클래스입니다.  
  
##  <a name="fillcategorieslistbox"></a>CMFCToolBarsCustomizeDialog::FillCategoriesListBox  
 제공 된 정보를 표시 `CListBox` 의 각 명령 범주 이름 가진 개체는 **사용자 지정** 대화 상자입니다.  
  
```  
void FillCategoriesListBox(
    CListBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `wndCategory`  
 에 대 한 참조는 `CListBox` 채울 개체입니다.  
  
 [in] `bAddEmpty`  
 명령을 갖지 않는 목록 상자에 범주를 추가할 것인지를 지정 하는 부울 값입니다. 이 매개 변수가 `TRUE`, 빈 범주 목록 상자에 추가 됩니다. 그렇지 않으면 빈 범주 추가 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 이 방법은 [CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox) 메서드가이 방법은 작동 한다는 점을 제외 하면는 `CListBox` 개체입니다.  
  
 이 메서드는의 내용을 지우지 않습니다는 `CListBox` 채우지 하기 전에 개체입니다. **모든 명령을** 범주 목록 상자에서 마지막 항목입니다.  
  
 사용 하 여 새 명령 범주를 추가할 수는 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) 메서드. 사용 하 여 기존 범주의 이름을 변경할 수는 [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) 메서드.  
  
 `CMFCToolBarsCommandsPropertyPage` 클래스에서이 메서드를 사용 하 여 각 명령 범주와 관련 된 명령 목록이 표시 됩니다.  
  
##  <a name="getcommandname"></a>CMFCToolBarsCustomizeDialog::GetCommandName  
 지정한 명령 ID와 연결 된 이름을 검색합니다  
  
```  
LPCTSTR GetCommandName(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmd`  
 ID를 검색 하는 명령입니다.  
  
### <a name="return-value"></a>반환 값  
 지정한 명령 ID와 연결 되는 이름을 또는 `NULL` 명령이 존재 하지 않는 경우.  
  
##  <a name="getcountincategory"></a>CMFCToolBarsCustomizeDialog::GetCountInCategory  
 주어진된 텍스트 레이블을 추가 하는 제공된 된 목록에 있는 항목의 수를 가져옵니다.  
  
```  
int GetCountInCategory(
    LPCTSTR lpszItemName,  
    const CObList& lstCommands) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszItemName`  
 일치 하는 텍스트 레이블.  
  
 [in] `lstCommands`  
 포함 하는 목록에 대 한 참조 `CMFCToolBarButton` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 제공 된의 항목 수가 목록 인 텍스트 레이블 equals `lpszItemName`합니다.  
  
### <a name="remarks"></a>주의  
 제공 된 개체 목록에서 각 요소 형식 이어야 합니다 `CMFCToolBarButton`합니다. 이 메서드는 비교 `lpszItemName` 와 [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext) 데이터 멤버입니다.  
  
##  <a name="getflags"></a>CMFCToolBarsCustomizeDialog::GetFlags  
 대화 상자의 동작에 영향을 주는 플래그 집합을 검색 합니다.  
  
```  
UINT GetFlags() const;  
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자의 동작에 영향을 주는 플래그 집합이 있습니다.  
  
### <a name="remarks"></a>주의  
 값을 검색 하는이 메서드는 `uiFlags` 생성자에 전달 되는 매개 변수입니다. 반환 값은 다음 값 중 하나 이상을 하나일 수 있습니다.  
  
 `AFX_CUSTOMIZE_MENU_SHADOWS`  
 사용자를 메뉴의 그림자 모양을 지정할 수 있습니다.  
  
 `AFX_CUSTOMIZE_TEXT_LABELS`  
 사용자를 도구 모음 단추 이미지 아래 텍스트 레이블을 표시 되는지 여부를 지정할 수 있습니다.  
  
 `AFX_CUSTOMIZE_MENU_ANIMATIONS`  
 메뉴 애니메이션 스타일을 지정할 수 있습니다.  
  
 `AFX_CUSTOMIZE_NOHELP`  
 사용자 지정 대화 상자에서 도움말 단추를 제거합니다.  
  
 `AFX_CUSTOMIZE_CONTEXT_HELP`  
 사용 된 `WS_EX_CONTEXTHELP` 비주얼 스타일입니다.  
  
 `AFX_CUSTOMIZE_NOTOOLS`  
 제거는 **도구** 사용자 지정 대화 상자에서 페이지입니다. 이 플래그는 응용 프로그램에서 사용 하는 경우에 유효는 `CUserToolsManager` 클래스입니다.  
  
 `AFX_CUSTOMIZE_MENUAMPERS`  
 단추 캡션을 앰퍼샌드를 포함 하도록 허용 ( ** & **) 문자입니다.  
  
 `AFX_CUSTOMIZE_NO_LARGE_ICONS`  
 제거는 **큰 아이콘** 사용자 지정 대화 상자에서 옵션입니다.  
  
 에 대 한 자세한 내용은 `WS_EX_CONTEXTHELP` 비주얼 스타일 참조 [확장 창 스타일](../../mfc/reference/extended-window-styles.md)합니다.  
  
##  <a name="onafterchangetool"></a>CMFCToolBarsCustomizeDialog::OnAfterChangeTool  
 발생 된 후 즉시 변경 하는 사용자 도구에 응답 합니다.  
  
```  
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>매개 변수  
 [in, out] `pSelTool`  
 변경 된 사용자 도구 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 사용자의 사용자 지정 도구 속성을 변경 하는 경우 프레임 워크에 의해 호출 됩니다. 기본 구현은 아무 작업도 수행하지 않습니다. 파생 된 클래스에서이 메서드를 재정의 `CMFCToolBarsCustomizeDialog` 사용자 도구에 대 한 변경을 발생 한 후 처리를 수행 합니다.  
  
##  <a name="onassignkey"></a>CMFCToolBarsCustomizeDialog::OnAssignKey  
 사용자 정의 바로 가기 키의 유효성을 검사 합니다.  
  
```  
virtual BOOL OnAssignKey(ACCEL* pAccel);
```  
  
### <a name="parameters"></a>매개 변수  
 [in, out] `pAccel`  
 로 표시 되는 제안 된 키보드 할당에 대 한 포인터는 [가속도](http://msdn.microsoft.com/library/windows/desktop/ms646340) 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`키를 할당 하는 경우 또는 `FALSE` 키를 할당할 수 없는 경우. 기본 구현에서는 항상 반환 `TRUE`합니다.  
  
### <a name="remarks"></a>주의  
 사용자는 새 바로 가기 키를 할당 하거나 정의 하는 사용자와 바로 가기 키 유효성을 검사 하는 경우 추가 처리를 수행 하는 파생된 클래스에서이 메서드를 재정의 합니다. 바로 가기를 할당 되지 않도록 하려면 반환 `FALSE`합니다. 메시지 상자도 표시할 하거나 그렇지 않은 경우 바로 가기 키 거부 된 이유는 이유는 사용자에 게 알리는 해야 합니다.  
  
##  <a name="onbeforechangetool"></a>CMFCToolBarsCustomizeDialog::OnBeforeChangeTool  
 사용자 지정 때 처리를 수행 하는 사용자 도구에 대 한 변경 하면 변경 내용을 적용 하려고 할 때입니다.  
  
```  
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>매개 변수  
 [in, out] `pSelTool`  
 교체 하는 사용자 도구 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 사용자 지정 도구의 속성을 변경 하려고 할 때 프레임 워크에 의해 호출 됩니다. 기본 구현은 아무 작업도 수행하지 않습니다. 재정의 `OnBeforeChangeTool` 에서 파생 된 클래스에서 메서드 `CMFCToolBarsCustomizeDialog` 같은 리소스를 해제 하는 사용자 도구에 대 한 변경을 발생 하기 전에 처리를 수행 하려는 경우를 `pSelTool` 사용 합니다.  
  
##  <a name="onedittoolbarmenuimage"></a>CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage  
 사용자는 도구 모음 단추 또는 메뉴 항목 아이콘을 사용자 지정할 수 있도록 이미지 편집기를 시작 합니다.  
  
```  
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,  
    CBitmap& bitmap,  
    int nBitsPerPixel);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndParent`  
 부모 창에 대 한 포인터입니다.  
  
 [in] `bitmap`  
 편집할 수는 비트맵 개체에 대 한 참조입니다.  
  
 [in] `nBitsPerPixel`  
 픽셀 당 비트에서 컬러 해상도 비트맵입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`변경 내용을 커밋하고; 하는 경우 그렇지 않으면 `FALSE`합니다. 대화 상자를 표시 하 고 반환 하는 기본 구현은 `TRUE` 클릭 하면 **확인**, 또는 `FALSE` 클릭 하면 **취소** 또는 **닫기** 단추입니다.  
  
### <a name="remarks"></a>주의  
 사용자 이미지 편집기를 실행할 때이 메서드는 프레임 워크에 의해 호출 됩니다. 기본 구현 표시 [CMFCImageEditorDialog 클래스](../../mfc/reference/cmfcimageeditordialog-class.md) 대화 상자입니다. 재정의 `OnEditToolbarMenuImage` 사용자 지정 이미지 편집기를 사용 하려면 파생된 클래스에서.  
  
##  <a name="oninitdialog"></a>CMFCToolBarsCustomizeDialog::OnInitDialog  
 재정의 속성 시트 초기화를 보강할 수 있습니다.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>반환 값  
 호출의 결과 [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog) 메서드.  
  
### <a name="remarks"></a>주의  
 이 메서드는 기본 클래스 구현을 확장 [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog)를 표시 하 여는 **닫기** 단추, 대화 상자 현재 화면 크기에 맞는지 확인 하 여 및 이동 하 여는 **도움말** 대화 상자의 왼쪽 아래 모서리에 있는 단추입니다.  
  
##  <a name="oninittoolspage"></a>CMFCToolBarsCustomizeDialog::OnInitToolsPage  
 프레임 워크에서 알림을 처리 하는 **도구** 페이지를 초기화할 수는 있습니다.  
  
```  
virtual void OnInitToolsPage();
```  
  
### <a name="remarks"></a>주의  
 기본 구현은 아무 작업도 수행하지 않습니다. 이 알림을 처리 하는 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="postncdestroy"></a>CMFCToolBarsCustomizeDialog::PostNcDestroy  
 창 소멸 된 후에 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void PostNcDestroy();
```  
  
### <a name="remarks"></a>주의  
 이 메서드는 기본 클래스 구현을 확장 `CPropertySheet::PostNcDestroy`, 이전 모드에 응용 프로그램을 복원 하 여 합니다.  
  
 [CMFCToolBarsCustomizeDialog::Create](#create) 메서드는 사용자 지정 작업에 사용자를 제한 하는 특수 모드에서 응용 프로그램을 배치 합니다.  
  
##  <a name="removebutton"></a>CMFCToolBarsCustomizeDialog::RemoveButton  
 모든 범주 또는 지정된 된 범주에서 지정한 명령 id를 제거합니다.  
  
```  
int RemoveButton(
    UINT uiCategoryId,  
    UINT uiCmdId);

int RemoveButton(
    LPCTSTR lpszCategory,  
    UINT uiCmdId);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCategoryId`  
 단추를 제거 하는 범주 ID를 지정 합니다.  
  
 [in] `uiCmdId`  
 단추의 명령 ID를 지정합니다.  
  
 [in] `lpszCategory`  
 단추를 제거 하는 범주의 이름을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 제거 단추 또는 지정된 된 명령 ID가 지정된 된 범주에 없는 경우-1의&0;부터 시작 하는 인덱스입니다. 경우 `uiCategoryId` -1 이면 반환 값은 0입니다.  
  
### <a name="remarks"></a>주의  
 단추에서 모든 범주를 제거 하려면이 메서드 및 집합의 첫 번째 오버 로드를 호출 `uiCategoryId` 를-1입니다.  
  
##  <a name="renamecategory"></a>CMFCToolBarsCustomizeDialog::RenameCategory  
 범주 목록 상자에서 범주에서 이름을 바꿉니다.는 **명령을** 페이지입니다.  
  
```  
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,  
    LPCTSTR lpszCategoryNew);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszCategoryOld`  
 변경 하려면 범주 이름입니다.  
  
 [in] `lpszCategoryNew`  
 새 범주 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 범주 이름은 고유 해야 합니다.  
  
##  <a name="replacebutton"></a>CMFCToolBarsCustomizeDialog::ReplaceButton  
 명령의 목록 상자에서 도구 모음 단추에서 대체는 **명령을** 페이지입니다.  
  
```  
void ReplaceButton(
    UINT uiCmd,  
    const CMFCToolBarButton& button);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmd`  
 교체 단추의 명령을 지정 합니다.  
  
 [in] `button`  
 A `const` 이전 단추를 대체 하는 도구 모음 단추 개체에 대 한 참조입니다.  
  
### <a name="remarks"></a>주의  
 때 [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu), [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands), 또는 [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar) 하는 명령을 추가 **명령을** 페이지, 명령 형식으로 인지는 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md) 개체 (또는 [CMFCToolBarMenuButton 클래스](../../mfc/reference/cmfctoolbarmenubutton-class.md) 으로 추가 하는 하위 메뉴를 포함 하는 메뉴 항목에 대 한 개체 `AddMenuCommands`). 또한 프레임 워크 명령을 자동으로 추가 하려면이 세 가지 메서드를 호출 합니다. 대신 파생된 된 형식으로 나타내야 하는 명령을 호출 `ReplaceButton` 파생 형식의 단추에 전달 합니다.  
  
### <a name="example"></a>예제  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `ReplaceButton` 에서 메서드는 `CMFCToolBarsCustomizeDialog` 클래스입니다. 이 코드 조각은의 일부인는 [Visual Studio 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&34;](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]  
  
##  <a name="setusercategory"></a>CMFCToolBarsCustomizeDialog::SetUserCategory  
 범주 목록에서 범주를 지정는 **명령을** 페이지는 사용자의 범주입니다. 호출 하기 전에이 함수를 호출 해야 [CMFCToolBarsCustomizeDialog::Create](#create)합니다.  
  
```  
BOOL SetUserCategory(LPCTSTR lpszCategory);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszCategory`  
 범주 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 사용자 범주 설정 프레임 워크에서 현재 사용 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPropertySheet 클래스](../../mfc/reference/cpropertysheet-class.md)

