---
title: "CMFCToolBarComboBoxButton 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarComboBoxButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarComboBoxButton class
ms.assetid: 32fa39f7-8e4e-4f0a-a31d-7b540d969a6c
caps.latest.revision: 30
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
ms.openlocfilehash: 43369e8869f9dd58543016bd74547b24fbe183a5
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarcomboboxbutton-class"></a>CMFCToolBarComboBoxButton 클래스
콤보 상자 컨트롤을 포함 하는 도구 모음 단추 ( [CComboBox 클래스](../../mfc/reference/ccombobox-class.md)).  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCToolBarComboBoxButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton](#cmfctoolbarcomboboxbutton)|`CMFCToolBarComboBoxButton`를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarComboBoxButton::AddItem](#additem)|콤보 상자 목록 끝에 항목을 추가 합니다.|  
|[CMFCToolBarComboBoxButton::AddSortedItem](#addsorteditem)|콤보 상자 목록에 항목을 추가 합니다. 목록에서 항목 순서에서 지정 된 `Compare`합니다.|  
|[CMFCToolBarComboBoxButton::Compare](#compare)|두 항목을 비교합니다. 호출을 정렬 하는 항목 `AddSortedItems` 콤보 상자 목록에 추가 합니다.|  
|[CMFCToolBarComboBoxButton::CreateEdit](#createedit)|콤보 상자 단추에 대 한 새 편집 컨트롤을 만듭니다.|  
|[CMFCToolBarComboBoxButton::DeleteItem](#deleteitem)|콤보 상자 목록에서 항목을 삭제합니다.|  
|[CMFCToolBarComboBoxButton::FindItem](#finditem)|지정된 된 문자열을 포함 하는 항목의 인덱스를 반환 합니다.|  
|[CMFCToolBarComboBoxButton::GetByCmd](#getbycmd)|지정한 명령 ID 가진 콤보 상자 단추에 대 한 포인터를 반환|  
|[CMFCToolBarComboBoxButton::GetComboBox](#getcombobox)|콤보 상자 단추에 포함 된 콤보 상자 컨트롤에 대 한 포인터를 반환 합니다.|  
|[CMFCToolBarComboBoxButton::GetCount](#getcount)|상자 목록 콤보에서 항목의 수를 반환합니다.|  
|[CMFCToolBarComboBoxButton::GetCountAll](#getcountall)|콤보 상자 단추를 지정한 명령 id를 찾습니다. 단추에 상자 목록 콤보에서 항목의 수를 반환합니다.|  
|[CMFCToolBarComboBoxButton::GetCurSel](#getcursel)|콤보 상자 목록 선택된 된 항목의 인덱스를 반환 합니다.|  
|[CMFCToolBarComboBoxButton::GetCurSelAll](#getcurselall)|콤보 상자 단추를 지정한 명령 id 및 해당 단추의 상자 목록을 콤보에서 선택한 항목의 인덱스를 반환 하는 찾습니다.|  
|[CMFCToolBarComboBoxButton::GetEditCtrl](#geteditctrl)|콤보 상자 단추에 포함 된 편집 컨트롤에 대 한 포인터를 반환 합니다.|  
|[CMFCToolBarComboBoxButton::GetItem](#getitem)|상자 목록을 콤보에서 지정 된 인덱스와 연결 된 문자열을 반환 합니다.|  
|[CMFCToolBarComboBoxButton::GetItemAll](#getitemall)|콤보 상자 단추를 단추에 콤보 상자 목록에는 인덱스와 연결 된 문자열을 반환 하 고는 지정 된 명령 id를 찾습니다.|  
|[CMFCToolBarComboBoxButton::GetItemData](#getitemdata)|상자 목록을 콤보에서 지정된 된 인덱스와 연관 된 32 비트 값을 반환 합니다.|  
|[CMFCToolBarComboBoxButton::GetItemDataAll](#getitemdataall)|콤보 상자 단추를 단추에 콤보 상자 목록에서 인덱스와 연관 된 32 비트 값을 반환 하는 지정 된 명령 id를 찾습니다.|  
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](#getitemdataptrall)|콤보 상자 단추를 지정한 명령 id를 찾습니다. 검색 연결 된 단추와 32 비트 포인터로 값을 반환 하는 콤보 상자 목록에서 인덱스를 32 비트 값입니다.|  
|[CMFCToolBarComboBoxButton::GetText](#gettext)|콤보 상자의 편집 컨트롤에서 텍스트를 반환합니다.|  
|[CMFCToolBarComboBoxButton::GetTextAll](#gettextall)|콤보 상자 단추를 지정한 명령 id 및 해당 단추의 편집 컨트롤에서 텍스트를 반환 하는 찾습니다.|  
|[CMFCToolBarComboBoxButton::IsCenterVert](#iscentervert)|응용 프로그램에서 콤보 상자 단추 가운데는 도구 모음의 위쪽에 정렬 되는지 결정 됩니다.|  
|[CMFCToolBarComboBoxButton::IsFlatMode](#isflatmode)|응용 프로그램에서 콤보 상자 단추를 평면 모양 있는지 여부를 결정 합니다.|  
|[CMFCToolBarComboBoxButton::RemoveAllItems](#removeallitems)|목록에서 항목을 모두 상자 및 콤보 상자 컨트롤을 편집할 제거 합니다.|  
|[CMFCToolBarComboBoxButton::SelectItem](#selectitem)|해당 인덱스, 32 비트 값 또는 문자열에 따라 콤보 상자에서 항목을 선택 하 고 선택 항목에 대 한 콤보 상자 컨트롤에 알립니다.|  
|[CMFCToolBarComboBoxButton::SelectItemAll](#selectitemall)|콤보 상자 단추를 지정한 명령 id를 찾습니다. 호출 `SelectItem` 하는 문자열, 인덱스 또는 32 비트 값에 따라 해당 단추의 콤보 상자에서 항목을 선택 합니다.|  
|[CMFCToolBarComboBoxButton::SetCenterVert](#setcentervert)|응용 프로그램에서 콤보 상자 단추 세로 가운데 맞춤 되는지 또는 도구 모음의 위쪽에 맞춰집니다를 지정 합니다.|  
|[CMFCToolBarComboBoxButton::SetDropDownHeight](#setdropdownheight)|드롭다운 목록 상자의 높이 설정합니다.|  
|[CMFCToolBarComboBoxButton::SetFlatMode](#setflatmode)|응용 프로그램에서 콤보 상자 단추를 평면 모양 하는지 여부를 지정 합니다.|  
  
## <a name="remarks"></a>주의  
 도구 모음에 콤보 상자 단추를 추가 하려면 다음이 단계를 수행 합니다.  
  
 1. 부모 도구 모음 리소스의 단추에 대한 더미 리소스 ID를 예약합니다.  
  
 2. 생성 된 `CMFCToolBarComboBoxButton` 개체입니다.  
  
 3. 처리 하는 메시지 처리기에는 `AFX_WM_RESETTOOLBAR` 메시지를 사용 하 여 새 콤보 상자 단추 더미 단추 바꿉니다 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)합니다.  
  
 자세한 내용은 참조 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)합니다. 콤보 상자 도구 모음 단추의 예를 들어 VisualStudioDemo 예제 프로젝트를 참조 하십시오.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CMFCToolBarComboBoxButton` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 편집 및 콤보 상자, 콤보의 세로 위치 상자 단추 응용 프로그램 설정, 응용 프로그램에서 콤보 상자 단추의 평면 스타일 모양을 설정 하 고 콤보 상자 단추의 편집 상자에 텍스트를 설정, 놓을 때 목록 상자의 높이 설정 하는 방법을 보여 줍니다. 이 코드 조각은의 일부인는 [Visual Studio 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&36;](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo #&37;](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtoolbarcomboboxbutton.h  
  
##  <a name="a-nameadditema--cmfctoolbarcomboboxbuttonadditem"></a><a name="additem"></a>CMFCToolBarComboBoxButton::AddItem  
 목록 상자에 고유한 항목을 추가합니다.  
  
```  
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszItem`  
 목록 상자에 추가할 항목의 텍스트입니다.  
  
 [in] `dwData`  
 목록 상자에 추가할 항목에 연결 된 데이터입니다.  
  
### <a name="return-value"></a>반환 값  
 목록 상자에 있는 마지막 항목의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 목록 상자 스타일 정렬 될 때이 메서드를 사용 하지 마십시오.  
  
 항목 텍스트의 목록 상자에 이미 있으면 새 데이터가 기존 항목과 함께 저장 됩니다. 항목에 대 한 검색은 대 소문자를 구분 합니다.  
  
##  <a name="a-nameaddsorteditema--cmfctoolbarcomboboxbuttonaddsorteditem"></a><a name="addsorteditem"></a>CMFCToolBarComboBoxButton::AddSortedItem  
 목록 상자에서 정의 된 순서에서에 항목을 추가 [비교](#compare) 메서드.  
  
```  
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszItem`  
 목록 상자에 추가할 항목의 텍스트입니다.  
  
 [in] `dwData`  
 목록 상자에 추가할 항목에 연결 된 데이터입니다.  
  
### <a name="return-value"></a>반환 값  
 목록 상자에 추가 된 항목의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 사용 하 여 특정 순서에 따라 목록 상자에 항목을 추가 합니다.  
  
##  <a name="a-namecanbestretcheda--cmfctoolbarcomboboxbuttoncanbestretched"></a><a name="canbestretched"></a>CMFCToolBarComboBoxButton::CanBeStretched  
 콤보 상자 단추 크기를 변경할 수 있는지 여부를 나타냅니다.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`를 반환합니다.  
  
##  <a name="a-namecmfctoolbarcomboboxbuttona--cmfctoolbarcomboboxbuttoncmfctoolbarcomboboxbutton"></a><a name="cmfctoolbarcomboboxbutton"></a>CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton  
 생성 된 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) 개체입니다.  
  
```  
CMFCToolBarComboBoxButton(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=CBS_DROPDOWNLIST,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiID`  
 새 단추의 명령 ID입니다.  
  
 [in] `iImage`  
 새 단추와 연결 된 이미지의 이미지 인덱스입니다.  
  
 [in] `dwStyle`  
 새로 만들기 단추의 스타일입니다.  
  
 [in] `iWidth`  
 새로 만들기 단추를 픽셀 단위로 너비입니다.  
  
### <a name="remarks"></a>주의  
 기본 너비는 150 픽셀입니다.  
  
 도구 모음 단추 스타일의 목록에 대 한 참조 [ToolBar 컨트롤 스타일](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="a-namecleardataa--cmfctoolbarcomboboxbuttoncleardata"></a><a name="cleardata"></a>CMFCToolBarComboBoxButton::ClearData  
 사용자 정의 데이터를 삭제 합니다.  
  
```  
virtual void ClearData();
```  
  
### <a name="remarks"></a>주의  
 기본적으로이 메서드는 아무 작업도 수행 하지 않습니다. 모든 사용자 정의 데이터를 삭제 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="a-namecomparea--cmfctoolbarcomboboxbuttoncompare"></a><a name="compare"></a>CMFCToolBarComboBoxButton::Compare  
 두 문자열을 비교합니다.  
  
```  
virtual int Compare(
    LPCTSTR lpszItem1,  
    LPCTSTR lpszItem2);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszItem1`  
 비교할 첫째 문자열입니다.  
  
 [in] `lpszItem2`  
 비교할 둘째 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 문자열의 대/소문자 구분 사전적 관계를 나타내는 값입니다. 다음 표에 가능한 값을 보여 줍니다.  
  
|값|설명|  
|-----------|-----------------|  
|\<0|첫 번째 문자열이 두 번째 인스턴스보다 합니다.|  
|0|첫 번째 문자열이 두 번째를 같습니다.|  
|>0|첫 번째 문자열이 두 번째 보다 큽니다.|  
  
### <a name="remarks"></a>주의  
 항목 목록 상자에서 정렬 되는 방법을 변경 하려면이 메서드를 재정의 합니다.  
  
 비교는 대 소문자를 구분 합니다.  
  
 에서만이 메서드는 [AddSortedItem](#addsorteditem) 메서드.  
  
##  <a name="a-namecopyfroma--cmfctoolbarcomboboxbuttoncopyfrom"></a><a name="copyfrom"></a>CMFCToolBarComboBoxButton::CopyFrom  
 지정 된 상태 복사 `CMFCToolBarComboBoxButton` 현재 개체입니다.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `src`  
 소스 `CMFCToolBarComboBoxButton` 개체입니다.  
  
##  <a name="a-namecreatecomboa--cmfctoolbarcomboboxbuttoncreatecombo"></a><a name="createcombo"></a>CMFCToolBarComboBoxButton::CreateCombo  
 콤보 상자 단추에 대 한 새 콤보 상자를 만듭니다.  
  
```  
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndParent`  
 단추의 부모 창에 대 한 포인터입니다.  
  
 [in] `rect`  
 콤보 상자의 경계 사각형입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 새 콤보 상자에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
##  <a name="a-namecreateedita--cmfctoolbarcomboboxbuttoncreateedit"></a><a name="createedit"></a>CMFCToolBarComboBoxButton::CreateEdit  
 콤보 상자 단추에 대 한 새 편집 상자를 만듭니다.  
  
```  
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndParent`  
 단추의 부모 창에 대 한 포인터입니다.  
  
 [in] `rect`  
 새 입력란의 경계 사각형입니다.  
  
 [in] `dwEditStyle`  
 새 입력란의 스타일을 제어 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 새 편집 상자에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 콤보 상자 단추에 대 한 새 편집 상자를 만들 때이 메서드를 호출 합니다. 변경 하려면이 메서드를 재정의 방법을 [CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md) 만들어집니다.  
  
##  <a name="a-namedeleteitema--cmfctoolbarcomboboxbuttondeleteitem"></a><a name="deleteitem"></a>CMFCToolBarComboBoxButton::DeleteItem  
 목록 상자에서 지정된 된 항목을 삭제합니다.  
  
```  
BOOL DeleteItem(int iIndex);  
BOOL DeleteItem(DWORD_PTR dwData);  
  BOOL DeleteItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iIndex`  
 삭제할 항목의&0;부터 시작 하는 인덱스입니다.  
  
 [in] `dwData`  
 삭제할 항목에 연결 된 데이터입니다.  
  
 [in] `lpszText`  
 삭제할 항목의 텍스트입니다. 동일한 텍스트를 가진 여러 항목이 있으면 첫 번째 항목이 삭제 됩니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`항목이 있고 성공적으로 삭제 합니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameduplicatedataa--cmfctoolbarcomboboxbuttonduplicatedata"></a><a name="duplicatedata"></a>CMFCToolBarComboBoxButton::DuplicateData  
 중복 된 사용자 정의 데이터입니다.  
  
```  
virtual void DuplicateData();
```  
  
### <a name="remarks"></a>주의  
 기본적으로이 메서드는 아무 작업도 수행 하지 않습니다. 모든 사용자 정의 데이터를 복사 하려는 경우에 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="a-nameenablewindowa--cmfctoolbarcomboboxbuttonenablewindow"></a><a name="enablewindow"></a>CMFCToolBarComboBoxButton::EnableWindow  
 편집 및 콤보 상자를 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
virtual void EnableWindow(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`편집 및 콤보 상자를 사용 하도록 설정 하려면 `FALSE` 를 편집 및 콤보 상자를 사용 하지 않도록 설정 합니다.  
  
### <a name="remarks"></a>주의  
 를 사용할 수 없을 때 활성화 될 수 없습니다 컨트롤과 사용자 입력을 받아들일 수 없습니다.  
  
##  <a name="a-nameexporttomenubuttona--cmfctoolbarcomboboxbuttonexporttomenubutton"></a><a name="exporttomenubutton"></a>CMFCToolBarComboBoxButton::ExportToMenuButton  
 복사 콤보 상자 단추 명령을 사용 하 여 지정 된 메뉴에 응용 프로그램 문자열 테이블에서 문자열 id입니다.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `menuButton`  
 메뉴 단추에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 항상 `TRUE`입니다.  
  
##  <a name="a-namefinditema--cmfctoolbarcomboboxbuttonfinditem"></a><a name="finditem"></a>CMFCToolBarComboBoxButton::FindItem  
 지정된 된 문자열을 포함 하는 목록 상자에서 첫 번째 항목의 인덱스를 반환 합니다.  
  
```  
int FindItem(LPCTSTR lpszText) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszText`  
 목록 상자에 검색할 텍스트입니다.  
  
### <a name="return-value"></a>반환 값  
 항목의 인덱스 또는 `CB_ERR` 항목이 없는 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetbycmda--cmfctoolbarcomboboxbuttongetbycmd"></a><a name="getbycmd"></a>CMFCToolBarComboBoxButton::GetByCmd  
 지정 된 명령 id 콤보 상자 단추에 대 한 포인터를 가져옵니다.  
  
```  
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,  
    BOOL bIsFocus=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmd`  
 콤보 상자 단추의 명령 ID입니다.  
  
 [in] `bIsFocus`  
 `TRUE`포커스가 있는 단추;만 검색 하려면 `FALSE` 단추를 모두 검색 합니다.  
  
### <a name="return-value"></a>반환 값  
 콤보 상자 단추;에 대 한 포인터 또는 `NULL` 단추를 찾을 수 없는 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetcomboboxa--cmfctoolbarcomboboxbuttongetcombobox"></a><a name="getcombobox"></a>CMFCToolBarComboBoxButton::GetComboBox  
 포인터를 반환 콤보 상자에서 콤보 상자 단추입니다.  
  
```  
CComboBox* GetComboBox() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CComboBox 클래스](../../mfc/reference/ccombobox-class.md) 객체 메서드는 성공 하 고, 그렇지 않으면 경우 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetcontextmenuida--cmfctoolbarcomboboxbuttongetcontextmenuid"></a><a name="getcontextmenuid"></a>CMFCToolBarComboBoxButton::GetContextMenuID  
 콤보 상자 단추에 대 한 바로 가기 메뉴 리소스 ID를 가져옵니다.  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>반환 값  
 바로 가기 메뉴 리소스 id입니다.  
  
##  <a name="a-namegetcounta--cmfctoolbarcomboboxbuttongetcount"></a><a name="getcount"></a>CMFCToolBarComboBoxButton::GetCount  
 목록 상자에서 항목의 수를 반환합니다.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 목록 상자에 있는 항목의 수입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetcountalla--cmfctoolbarcomboboxbuttongetcountall"></a><a name="getcountall"></a>CMFCToolBarComboBoxButton::GetCountAll  
 지정한 명령 id 있는 콤보 상자 단추의 목록 상자에서 항목 수를 가져옵니다.  
  
```  
static int GetCountAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmd`  
 콤보 상자 단추의 명령 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 목록 상자에서 항목의 수 그렇지 않으면 `CB_ERR` 콤보 상자 단추를 찾을 수 없는 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetcursela--cmfctoolbarcomboboxbuttongetcursel"></a><a name="getcursel"></a>CMFCToolBarComboBoxButton::GetCurSel  
 목록 상자에서 현재 선택 된 항목의 인덱스를 가져옵니다.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>반환 값  
 목록 상자에서 현재 선택 된 항목의 인덱스 또는 `CB_ERR` 선택 된 항목이 없는 경우.  
  
### <a name="remarks"></a>주의  
 목록 상자 인덱스는&0;부터 시작 합니다.  
  
##  <a name="a-namegetcurselalla--cmfctoolbarcomboboxbuttongetcurselall"></a><a name="getcurselall"></a>CMFCToolBarComboBoxButton::GetCurSelAll  
 지정 된 명령 id 상자 단추는 콤보 목록 상자에서 현재 선택 된 항목의 인덱스를 반환  
  
```  
static int GetCurSelAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmd`  
 콤보 상자 단추의 명령 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 목록 상자에서 현재 선택 된 항목의 인덱스 그렇지 않으면 `CB_ERR` 선택 된 항목이 없는 경우 콤보 상자 단추를 찾을 수 없습니다.  
  
### <a name="remarks"></a>주의  
 목록 상자 인덱스는&0;부터 시작 합니다.  
  
##  <a name="a-namegeteditctrla--cmfctoolbarcomboboxbuttongeteditctrl"></a><a name="geteditctrl"></a>CMFCToolBarComboBoxButton::GetEditCtrl  
 포인터를 반환 편집 상자에서 콤보 상자 단추입니다.  
  
```  
virtual CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 편집 상자에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegethwnda--cmfctoolbarcomboboxbuttongethwnd"></a><a name="gethwnd"></a>CMFCToolBarComboBoxButton::GetHwnd  
 콤보 상자에 대 한 창 핸들을 반환합니다.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>반환 값  
 창 핸들 또는 `NULL` 콤보 상자는 창 개체와 연결 되지 않은 경우.  
  
##  <a name="a-namegetitema--cmfctoolbarcomboboxbuttongetitem"></a><a name="getitem"></a>CMFCToolBarComboBoxButton::GetItem  
 목록 상자에 지정된 된 인덱스에 항목에 연결 된 문자열을 반환 합니다.  
  
```  
LPCTSTR GetItem(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iIndex`  
 목록 상자에 있는 항목의&0;부터 시작 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 항목이 연결 되는 문자열에 대 한 포인터 그렇지 않으면 `NULL` index 매개 변수가 올바르지 않습니다. 또는 index 매개 변수는-1 및 콤보 상자에서 선택 된 항목이 없는 경우.  
  
### <a name="remarks"></a>주의  
 -1 인덱스 매개 변수는 현재 선택 된 항목의 문자열을 반환 합니다.  
  
##  <a name="a-namegetitemalla--cmfctoolbarcomboboxbuttongetitemall"></a><a name="getitemall"></a>CMFCToolBarComboBoxButton::GetItemAll  
 지정 된 명령 id 있는 콤보 상자 단추의 목록 상자에 지정된 된 인덱스에 항목에 연결 된 문자열을 반환 합니다.  
  
```  
static LPCTSTR GetItemAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmd`  
 콤보 상자 단추의 명령 ID입니다.  
  
 [in] `iIndex`  
 목록 상자에 있는 항목의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 항목의 문자열에 대 한 포인터 그렇지 않으면 `NULL` 인덱스 유효한 경우 콤보 상자 단추는 발견 이거나 인덱스-1이 고 콤보 상자에서 선택 된 항목이 없는 경우.  
  
### <a name="remarks"></a>주의  
 현재 선택 된 항목의 문자열을 반환 하는 인덱스 값이-1입니다.  
  
##  <a name="a-namegetitemdataa--cmfctoolbarcomboboxbuttongetitemdata"></a><a name="getitemdata"></a>CMFCToolBarComboBoxButton::GetItemData  
 목록 상자에서 특정 인덱스에 항목에 연결 된 데이터를 반환 합니다.  
  
```  
DWORD_PTR GetItemData(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iIndex`  
 목록 상자에 있는 항목의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 항목;에 연결 된 데이터 또는 항목이 존재 하지 않는 경우 0을 지정 합니다.  
  
### <a name="remarks"></a>주의  
 -1 인덱스 매개 변수는 현재 선택 된 항목과 연결 된 데이터를 반환 합니다.  
  
##  <a name="a-namegetitemdataalla--cmfctoolbarcomboboxbuttongetitemdataall"></a><a name="getitemdataall"></a>CMFCToolBarComboBoxButton::GetItemDataAll  
 특정 명령 id 있는 콤보 상자 단추의 목록 상자에서 특정 인덱스에 항목에 연결 된 데이터를 반환 합니다.  
  
```  
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmd`  
 콤보 상자 단추의 명령 ID입니다.  
  
 [in] `iIndex`  
 목록 상자에 있는 항목의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 항목과 연결 된 데이터 지정된 된 인덱스 유효 하지 않거나 콤보 상자 단추 경우 CB_ERR가 없는 경우, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 -1 인덱스 매개 변수는 현재 선택 된 항목과 연결 된 데이터를 반환 합니다.  
  
##  <a name="a-namegetitemdataptralla--cmfctoolbarcomboboxbuttongetitemdataptrall"></a><a name="getitemdataptrall"></a>CMFCToolBarComboBoxButton::GetItemDataPtrAll  
 특정 명령 id 있는 콤보 상자 단추의 목록 상자에서 특정 인덱스에 항목에 연결 된 데이터를 반환 합니다. 이 데이터는 포인터로 반환 됩니다.  
  
```  
static void* GetItemDataPtrAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmd`  
 콤보 상자 단추의 명령 ID입니다.  
  
 [in] `iIndex`  
 목록 상자에 있는 항목의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 항목과 연결 된 포인터 오류가 발생 하는 경우, 그렇지 않으면-1 또는 `NULL` 콤보 상자 단추를 찾을 수 없는 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetprompta--cmfctoolbarcomboboxbuttongetprompt"></a><a name="getprompt"></a>CMFCToolBarComboBoxButton::GetPrompt  
 콤보 상자 단추 프롬프트 문자열을 반환합니다.  
  
```  
virtual CString GetPrompt() const;  
```  
  
### <a name="return-value"></a>반환 값  
 프롬프트 문자열입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드가 현재 구현 되지 않았습니다.  
  
##  <a name="a-namegettexta--cmfctoolbarcomboboxbuttongettext"></a><a name="gettext"></a>CMFCToolBarComboBoxButton::GetText  
 편집 상자에 텍스트를 가져옵니다.  
  
```  
LPCTSTR GetText() const;  
```  
  
### <a name="return-value"></a>반환 값  
 편집 상자에 텍스트입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegettextalla--cmfctoolbarcomboboxbuttongettextall"></a><a name="gettextall"></a>CMFCToolBarComboBoxButton::GetTextAll  
 지정 된 명령 id 있는 콤보 상자 단추의 편집 상자에 텍스트를 가져옵니다.  
  
```  
static LPCTSTR GetTextAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmd`  
 특정 콤보 상자 단추의 명령 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 편집 상자에 텍스트 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namehasfocusa--cmfctoolbarcomboboxbuttonhasfocus"></a><a name="hasfocus"></a>CMFCToolBarComboBoxButton::HasFocus  
 콤보 상자에서 현재 포커스를가지고 있는지 여부를 나타냅니다.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`콤보 상자에는 현재 포커스를가지고 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 또한이 메서드 반환 `TRUE` 콤보 상자의 모든 자식 창에 현재 포커스를가지고 있습니다.  
  
##  <a name="a-nameiscenterverta--cmfctoolbarcomboboxbuttoniscentervert"></a><a name="iscentervert"></a>CMFCToolBarComboBoxButton::IsCenterVert  
 응용 프로그램에서 콤보 상자 단추의 세로 위치를 반환합니다.  
  
```  
static BOOL IsCenterVert();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`단추 가운데에 정렬 되 고 하는 경우 `FALSE` 이면 단추 위쪽에 맞춥니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameisflatmodea--cmfctoolbarcomboboxbuttonisflatmode"></a><a name="isflatmode"></a>CMFCToolBarComboBoxButton::IsFlatMode  
 콤보 상자 단추의 평면 스타일 모양을 응용 프로그램에 반환합니다.  
  
```  
static BOOL IsFlatMode();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`단추를 평면 스타일; 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 콤보 상자 단추에 대 한 기본 플랫 스타일은`FALSE.`  
  
##  <a name="a-nameisownerofa--cmfctoolbarcomboboxbuttonisownerof"></a><a name="isownerof"></a>CMFCToolBarComboBoxButton::IsOwnerOf  
 지정된 된 핸들과 연결 된 콤보 상자 단추 또는 해당 자식 중 여부를 나타냅니다.  
  
```  
virtual BOOL IsOwnerOf(HWND hwnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hwnd`  
 창 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`핸들은 콤보 상자 단추 또는 해당 자식; 중 그리드의 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-nameisribbonbuttona--cmfctoolbarcomboboxbuttonisribbonbutton"></a><a name="isribbonbutton"></a>CMFCToolBarComboBoxButton::IsRibbonButton  
 콤보 상자 단추 리본 패널에 있는지 여부를 나타냅니다.  
  
```  
BOOL IsRibbonButton() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항상 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로이 메서드는 항상 반환 `FALSE`를 의미 하는 콤보 상자 단추를 리본 패널에 표시 되지 않습니다.  
  
##  <a name="a-nameiswindowvisiblea--cmfctoolbarcomboboxbuttoniswindowvisible"></a><a name="iswindowvisible"></a>CMFCToolBarComboBoxButton::IsWindowVisible  
 상자 단추 콤보의 표시 여부 상태를 반환합니다.  
  
```  
virtual BOOL IsWindowVisible();
```  
  
### <a name="return-value"></a>반환 값  
 콤보 상자 단추의 표시 여부 상태입니다.  
  
##  <a name="a-namenotifycommanda--cmfctoolbarcomboboxbuttonnotifycommand"></a><a name="notifycommand"></a>CMFCToolBarComboBoxButton::NotifyCommand  
 콤보 상자 단추 메시지를 처리 하는지 여부를 나타냅니다.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iNotifyCode`  
 명령과 사용 하 여 연결 된 알림 메시지입니다.  
  
### <a name="return-value"></a>반환 값  
 여부 콤보 상자 단추는 메시지를 처리 합니다.  
  
##  <a name="a-nameonaddtocustomizepagea--cmfctoolbarcomboboxbuttononaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBarComboBoxButton::OnAddToCustomizePage  
 단추에 추가 되는 프레임 워크에서 호출 된 **사용자 지정** 대화 상자입니다.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
##  <a name="a-nameoncalculatesizea--cmfctoolbarcomboboxbuttononcalculatesize"></a><a name="oncalculatesize"></a>CMFCToolBarComboBoxButton::OnCalculateSize  
 단추의 크기를 계산 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 콤보 상자 단추를 표시 하는 장치 컨텍스트.  
  
 [in] `sizeDefault`  
 콤보 상자 단추의 기본 크기입니다.  
  
 [in] `bHorz`  
 부모 도구 모음에서의 도킹 상태입니다. `TRUE`가로 도구 모음 도킹 된 경우 및 `FALSE` 세로로 도구 모음 도킹 된 경우.  
  
### <a name="return-value"></a>반환 값  
 A `SIZE` 픽셀 단위로 콤보 상자 단추의 크기를 포함 하는 구조입니다.  
  
##  <a name="a-nameonchangeparentwnda--cmfctoolbarcomboboxbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarComboBoxButton::OnChangeParentWnd  
 새 도구 모음에 콤보 상자 단추를 삽입 하면 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndParent`  
 새 부모 도구 모음에 대 한 포인터입니다.  
  
##  <a name="a-nameonclicka--cmfctoolbarcomboboxbuttononclick"></a><a name="onclick"></a>CMFCToolBarComboBoxButton::OnClick  
 콤보 상자 단추를 클릭할 때 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 콤보 상자 단추의 부모 창에 대 한 포인터입니다.  
  
 [in] `bDelay`  
 파생된 클래스에서 사용 하기 위해 예약 되어 있습니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드는 이벤트를 처리 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-nameonctlcolora--cmfctoolbarcomboboxbuttononctlcolor"></a><a name="onctlcolor"></a>CMFCToolBarComboBoxButton::OnCtlColor  
 사용자는 콤보 상자 단추 색을 설정 하려면 부모 도구 모음 색을 변경할 때 프레임 워크에서 호출 합니다.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 콤보 상자 단추를 표시 하는 장치 컨텍스트.  
  
 [in] `nCtlColor`  
 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 프레임 워크를 사용 하 여 콤보 상자 단추의 배경을 그리는 브러시에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 또한 콤보 상자 단추의 텍스트 색을 설정합니다.  
  
##  <a name="a-nameondrawa--cmfctoolbarcomboboxbuttonondraw"></a><a name="ondraw"></a>CMFCToolBarComboBoxButton::OnDraw  
 지정 된 스타일 및 옵션을 사용 하 여 콤보 상자 단추를 그리기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz = TRUE,  
    BOOL bCustomizeMode = FALSE,  
    BOOL bHighlight = FALSE,  
    BOOL bDrawBorder = TRUE,  
    BOOL bGrayDisabledButtons = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `Pdc`  
 단추를 표시 하는 장치 컨텍스트.  
  
 [in] `rect`  
 단추는 경계 사각형입니다.  
  
 [in] `pImages`  
 단추와 연결 된 이미지의 컬렉션입니다.  
  
 [in] `bHorz`  
 부모 도구 모음에서의 도킹 상태입니다. `TRUE`가로 도구 모음 도킹 된 경우 및 `FALSE` 세로로 도구 모음 도킹 된 경우.  
  
 [in] `bCustomizeMode`  
 사용자 지정 모드는 응용 프로그램 인지 여부  
  
 [in] `bHighlight`  
 강조 표시 된 콤보 상자 단추를 그릴 것인지 지정 합니다.  
  
 [in] `bDrawBorder`  
 테두리가 있는 콤보 상자 단추를 그릴 것인지 지정 합니다.  
  
 [in] `bGrayDisabledButtons`  
 `TRUE`비활성화 된 단추가 흐리게 표시; 그리려면 `FALSE` 사용 안 함을 사용 하 여 이미지 컬렉션입니다.  
  
##  <a name="a-nameondrawoncustomizelista--cmfctoolbarcomboboxbuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>CMFCToolBarComboBoxButton::OnDrawOnCustomizeList  
 콤보 상자 단추를 그리기 위해 프레임 워크에 의해 호출 된 **명령을** 의 창은 **사용자 지정** 대화 상자입니다.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 콤보 상자 단추를 표시 하는 장치 컨텍스트.  
  
 [in] `rect`  
 콤보 상자 단추의 경계 사각형입니다.  
  
 [in] `bSelected`  
 `TRUE`콤보 상자 단추 선택 됩니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 콤보 상자 단추의 픽셀 너비입니다.  
  
##  <a name="a-nameonglobalfontschangeda--cmfctoolbarcomboboxbuttononglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBarComboBoxButton::OnGlobalFontsChanged  
 응용 프로그램 글꼴이 변경 될 때 콤보 상자 단추 글꼴을 설정 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
##  <a name="a-nameonmovea--cmfctoolbarcomboboxbuttononmove"></a><a name="onmove"></a>CMFCToolBarComboBoxButton::OnMove  
 부모 도구 모음에서 이동할 때 콤보 상자 단추의 위치를 변경 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnMove();
```  
  
##  <a name="a-nameonshowa--cmfctoolbarcomboboxbuttononshow"></a><a name="onshow"></a>CMFCToolBarComboBoxButton::OnShow  
 콤보 상자 단추 숨기 거 나 표시 하는 경우에 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bShow`  
 콤보 상자 단추를 표시 하거나 숨기려면 여부를 나타냅니다.  
  
##  <a name="a-nameonsizea--cmfctoolbarcomboboxbuttononsize"></a><a name="onsize"></a>CMFCToolBarComboBoxButton::OnSize  
 부모 도구 모음에서 크기를 변경 하는 경우 콤보 상자 단추의 크기를 변경 하려면 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iSize`  
 콤보 상자 단추의 새 너비입니다.  
  
##  <a name="a-nameonupdatetooltipa--cmfctoolbarcomboboxbuttononupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBarComboBoxButton::OnUpdateToolTip  
 콤보 상자 단추에 대 한 도구 설명, 사용자가 변경할 때 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndParent`  
 콤보 상자 단추에 대 한 부모 창에 대 한 포인터입니다.  
  
 [in] `iButtonIndex`  
 콤보 상자 단추의 ID입니다.  
  
 [in] `wndToolTip`  
 콤보 상자 단추와 연결할 도구 설명입니다.  
  
 [in] `str`  
 도구 설명 텍스트입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드는 이벤트를 처리 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-nameremoveallitemsa--cmfctoolbarcomboboxbuttonremoveallitems"></a><a name="removeallitems"></a>CMFCToolBarComboBoxButton::RemoveAllItems  
 목록 및 편집 상자에서 모든 항목을 삭제합니다.  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>주의  
 목록에서 항목을 모두 상자 및 콤보 상자 컨트롤을 편집할 제거 합니다.  
  
##  <a name="a-nameselectitema--cmfctoolbarcomboboxbuttonselectitem"></a><a name="selectitem"></a>CMFCToolBarComboBoxButton::SelectItem  
 목록 상자에서 항목을 선택합니다.  
  
```  
BOOL SelectItem(
    int iIndex,  
    BOOL bNotify=TRUE);  
  
BOOL SelectItem(DWORD_PTR dwData);  
BOOL SelectItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iIndex`  
 목록 상자에 있는 항목의&0;부터 시작 하는 인덱스입니다.  
  
 [in] `bNotify`  
 `TRUE`선택 된; 콤보 상자 단추에 알리기 위해 그렇지 않으면 `FALSE`합니다.  
  
 [in] `dwData`  
 목록 상자에서 항목에 연결 된 데이터입니다.  
  
 [in] `lpszText`  
 목록 상자에 있는 항목의 텍스트입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameselectitemalla--cmfctoolbarcomboboxbuttonselectitemall"></a><a name="selectitemall"></a>CMFCToolBarComboBoxButton::SelectItemAll  
 지정 된 명령 id 있는 콤보 상자 단추의 목록 상자에서 항목을 선택 합니다.  
  
```  
static BOOL SelectItemAll(
    UINT uiCmd,  
    int iIndex);

 
static BOOL SelectItemAll(
    UINT uiCmd,  
    DWORD_PTR dwData);

 
static BOOL SelectItemAll(
    UINT uiCmd,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmd`  
 목록 상자를 포함 하는 콤보 상자 단추의 명령 ID입니다.  
  
 [in] `iIndex`  
 목록 상자에 있는 항목의&0;부터 시작 하는 인덱스입니다. 값이-1 목록 상자에서 모든 현재 선택 영역을 제거 하 고 편집 상자를 지웁니다.  
  
 [in] `dwData`  
 목록 상자에 있는 항목의 데이터입니다.  
  
 [in] `lpszText`  
 목록 상자에 있는 항목의 텍스트입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameserializea--cmfctoolbarcomboboxbuttonserialize"></a><a name="serialize"></a>CMFCToolBarComboBoxButton::Serialize  
 이 개체는 보관 파일에서 읽거나 보관 파일에 씁니다.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in, out] `ar`  
 `CArchive` serialize 할 개체입니다.  
  
### <a name="remarks"></a>주의  
 설정에는 `CArchive` 개체가이 메서드를 읽습니다 보관 파일에 기록 하는지 여부를 확인 합니다.  
  
##  <a name="a-namesetaccdataa--cmfctoolbarcomboboxbuttonsetaccdata"></a><a name="setaccdata"></a>CMFCToolBarComboBoxButton::SetACCData  
 지정 된 채웁니다 `CAccessibilityData` 콤보 상자 단추에서 내게 필요한 옵션 데이터를 사용 하 여 개체입니다.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParent`  
 콤보 상자 단추의 부모 창입니다.  
  
 [out] `data`  
 A `CAccessibilityData` 콤보 상자 단추에서 내게 필요한 옵션 데이터를 받는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-namesetcenterverta--cmfctoolbarcomboboxbuttonsetcentervert"></a><a name="setcentervert"></a>CMFCToolBarComboBoxButton::SetCenterVert  
 응용 프로그램에서 콤보 상자 단추의 세로 위치를 설정합니다.  
  
```  
static void SetCenterVert(BOOL bCenterVert=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bCenterVert`  
 `TRUE`센터에서 도구 모음의 콤보 상자 단추 `FALSE` 위쪽 도구 모음에 콤보 상자 단추에 맞게 합니다.  
  
### <a name="remarks"></a>주의  
 기본적으로 콤보 상자 단추 위에 정렬 됩니다.  
  
##  <a name="a-namesetcontextmenuida--cmfctoolbarcomboboxbuttonsetcontextmenuid"></a><a name="setcontextmenuid"></a>CMFCToolBarComboBoxButton::SetContextMenuID  
 콤보 상자 단추 바로 가기 메뉴 리소스 ID를 설정합니다.  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiResID`  
 바로 가기 메뉴 리소스 id입니다.  
  
##  <a name="a-namesetdropdownheighta--cmfctoolbarcomboboxbuttonsetdropdownheight"></a><a name="setdropdownheight"></a>CMFCToolBarComboBoxButton::SetDropDownHeight  
 놓을 때 목록 상자의 높이 설정 합니다.  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nHeight`  
 목록 상자를 픽셀 단위로 높이입니다.  
  
### <a name="remarks"></a>주의  
 기본 높이 150 픽셀입니다.  
  
##  <a name="a-namesetflatmodea--cmfctoolbarcomboboxbuttonsetflatmode"></a><a name="setflatmode"></a>CMFCToolBarComboBoxButton::SetFlatMode  
 응용 프로그램에서 콤보 상자 단추의 평면 스타일 모양을 설정합니다.  
  
```  
static void SetFlatMode(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bFlat`  
 `TRUE`평면 스타일 모양을;에 대 한 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 콤보 상자 단추에 대 한 기본 플랫 스타일은 `FALSE`합니다.  
  
##  <a name="a-namesetstylea--cmfctoolbarcomboboxbuttonsetstyle"></a><a name="setstyle"></a>CMFCToolBarComboBoxButton::SetStyle  
 콤보 상자 단추 지정된 된 스타일 설정 하 고 하지 않는 경우에 컨트롤을 다시 그립니다.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nStyle`  
 Toolbar 스타일의 비트 조합 (OR)입니다.  
  
### <a name="remarks"></a>주의  
 도구 모음 단추 스타일의 목록에 대 한 참조 [ToolBar 컨트롤 스타일](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="a-namesettexta--cmfctoolbarcomboboxbuttonsettext"></a><a name="settext"></a>CMFCToolBarComboBoxButton::SetText  
 상자 단추 콤보의 편집 상자에 텍스트를 설정 합니다.  
  
```  
void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszText`  
 편집 상자에 대 한 텍스트를 포함 하는 문자열에 대 한 포인터입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CComboBox 클래스](../../mfc/reference/ccombobox-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)




