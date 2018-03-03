---
title: "CMFCPropertySheet 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPage
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPageToTree
- AFXPROPERTYSHEET/CMFCPropertySheet::AddTreeCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::EnablePageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::GetHeaderHeight
- AFXPROPERTYSHEET/CMFCPropertySheet::GetLook
- AFXPROPERTYSHEET/CMFCPropertySheet::GetNavBarWidth
- AFXPROPERTYSHEET/CMFCPropertySheet::GetTab
- AFXPROPERTYSHEET/CMFCPropertySheet::InitNavigationControl
- AFXPROPERTYSHEET/CMFCPropertySheet::OnActivatePage
- AFXPROPERTYSHEET/CMFCPropertySheet::OnDrawPageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::OnRemoveTreePage
- AFXPROPERTYSHEET/CMFCPropertySheet::RemoveCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::RemovePage
- AFXPROPERTYSHEET/CMFCPropertySheet::SetIconsList
- AFXPROPERTYSHEET/CMFCPropertySheet::SetLook
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertySheet [MFC], CMFCPropertySheet
- CMFCPropertySheet [MFC], AddPage
- CMFCPropertySheet [MFC], AddPageToTree
- CMFCPropertySheet [MFC], AddTreeCategory
- CMFCPropertySheet [MFC], EnablePageHeader
- CMFCPropertySheet [MFC], GetHeaderHeight
- CMFCPropertySheet [MFC], GetLook
- CMFCPropertySheet [MFC], GetNavBarWidth
- CMFCPropertySheet [MFC], GetTab
- CMFCPropertySheet [MFC], InitNavigationControl
- CMFCPropertySheet [MFC], OnActivatePage
- CMFCPropertySheet [MFC], OnDrawPageHeader
- CMFCPropertySheet [MFC], OnRemoveTreePage
- CMFCPropertySheet [MFC], RemoveCategory
- CMFCPropertySheet [MFC], RemovePage
- CMFCPropertySheet [MFC], SetIconsList
- CMFCPropertySheet [MFC], SetLook
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e2684de5c72dcc755c2a75e2553eed509ce76533
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcpropertysheet-class"></a>CMFCPropertySheet 클래스
`CMFCPropertySheet` 클래스는 각 속성 페이지가 페이지 탭, 도구 모음 단추, 트리 컨트롤 노드 또는 목록 항목으로 표시되는 속성 시트를 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCPropertySheet : public CPropertySheet  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCPropertySheet::CMFCPropertySheet](#cmfcpropertysheet)|`CMFCPropertySheet` 개체를 생성합니다.|  
|`CMFCPropertySheet::~CMFCPropertySheet`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Cmfcpropertysheet:: Addpage](#addpage)|속성 시트에 페이지를 추가합니다.|  
|[CMFCPropertySheet::AddPageToTree](#addpagetotree)|트리 컨트롤에 새 속성 페이지를 추가합니다.|  
|[CMFCPropertySheet::AddTreeCategory](#addtreecategory)|트리 컨트롤에 새 노드를 추가합니다.|  
|[CMFCPropertySheet::EnablePageHeader](#enablepageheader)|각 페이지 위쪽에서 사용자 지정 머리글을 그릴 공간을 예약합니다.|  
|[CMFCPropertySheet::GetHeaderHeight](#getheaderheight)|현재 머리글의 높이를 검색합니다.|  
|[CMFCPropertySheet::GetLook](#getlook)|현재 속성 시트의 모양을 지정하는 열거형 값을 검색합니다.|  
|[Cmfcpropertysheet:: Getnavbarwidth](#getnavbarwidth)|탐색 모음의 너비(픽셀)를 검색합니다.|  
|[CMFCPropertySheet::GetTab](#gettab)|현재 속성 시트 컨트롤을 지원하는 내부 탭 컨트롤 개체를 검색합니다.|  
|`CMFCPropertySheet::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에서는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|  
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|현재 속성 시트 컨트롤의 모양을 초기화합니다.|  
|[CMFCPropertySheet::OnActivatePage](#onactivatepage)|속성 페이지를 사용하도록 설정한 경우 프레임워크에서 호출됩니다.|  
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|사용자 지정 속성 페이지 머리글을 그리기 위해 프레임워크에서 호출됩니다.|  
|`CMFCPropertySheet::OnInitDialog`|처리는 [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) 메시지입니다. (재정의 [cpropertysheet:: Oninitdialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|  
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|트리 컨트롤에서 속성 페이지를 제거하기 위해 프레임워크에서 호출됩니다.|  
|`CMFCPropertySheet::PreTranslateMessage`|창 메시지를 변환 하 여 디스패치 되기 전에 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수입니다. (`CPropertySheet::PreTranslateMessage`를 재정의합니다.)|  
|[CMFCPropertySheet::RemoveCategory](#removecategory)|트리 컨트롤에서 노드를 제거합니다.|  
|[CMFCPropertySheet::RemovePage](#removepage)|속성 시트에서 속성 페이지를 제거합니다.|  
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Outlook 창의 탐색 컨트롤에서 사용되는 이미지 목록을 지정합니다.|  
|[Cmfcpropertysheet:: Setlook](#setlook)|속성 시트의 모양을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 `CMFCPropertySheet` 클래스는 속성 시트(탭 대화 상자라고도 함)를 나타냅니다. `CMFCPropertySheet` 클래스는 다양한 방식으로 속성 페이지를 표시할 수 있습니다.  
  
 응용 프로그램에서 `CMFCPropertySheet` 클래스를 사용하려면 다음 단계를 수행합니다.  
  
1.  `CMFCPropertySheet` 클래스에서 클래스를 파생시키고 클래스 이름(예: CMyPropertySheet)을 지정합니다.  
  
2.  생성 된 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) 각 속성 페이지에 대 한 개체입니다.  
  
3.  호출 된 [cmfcpropertysheet:: Setlook](#setlook) CMyPropertySheet 생성자입니다. 이 메서드의 매개 변수는 속성 페이지가 속성 시트의 위쪽이나 왼쪽에 있는 탭, Microsoft OneNote 속성 시트 스타일의 탭, Microsoft Outlook 도구 모음 컨트롤의 단추, 트리 컨트롤의 노드 또는 속성 시트의 왼쪽에 있는 항목 목록으로 표시되도록 지정합니다.  
  
4.  Microsoft Outlook 도구 모음 스타일의 속성 시트를 만드는 경우에 호출 된 [CMFCPropertySheet::SetIconsList](#seticonslist) 속성 페이지와 함께 이미지 목록을 연결 하는 방법이 있습니다.  
  
5.  호출 된 [cmfcpropertysheet:: Addpage](#addpage) 메서드가 각 속성 페이지에 대 한 합니다.  
  
6.  `CMFCPropertySheet` 컨트롤을 만들고 해당 `DoModal` 메서드를 호출합니다.  
  
## <a name="illustrations"></a>그림  
 다음 그림에서는 포함된 Microsoft Outlook 도구 모음 스타일의 속성 시트를 보여 줍니다. Outlook 도구 모음은 속성 시트의 왼쪽에 나타납니다.  
  
 ![CMFCPropertySheet 색 컨트롤](../../mfc/reference/media/cmfcpropertysheet_color.png "cmfcpropertysheet_color")  
  
 다음 그림에서는 포함 된 속성 시트를 보여 줍니다.는 [CMFCPropertyGridCtrl 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md) 개체입니다. 해당 개체는 표준 공용 컨트롤 속성 시트 스타일의 속성 시트입니다.  
  
 ![CMFCPropertySheet 목록 및 속성 컨트롤](../../mfc/reference/media/cmfcpropertysheet_list.png "cmfcpropertysheet_list")  
  
 다음 그림에서는 트리 컨트롤 스타일의 속성 시트를 보여 줍니다.  
  
 ![속성 트리](../../mfc/reference/media/proptree.png "proptree")  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxpropertysheet.h  
  
##  <a name="addpage"></a>Cmfcpropertysheet:: Addpage  
 속성 시트에 페이지를 추가합니다.  
  
```  
void AddPage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pPage`  
 Page 개체에 대 한 포인터입니다. 이 매개 변수 여야 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 속성 시트의 오른쪽에 있는 탭으로 지정 된 속성 페이지를 추가합니다. 따라서 왼쪽에서 오른쪽 순서로 페이지를 추가 하려면이 메서드를 사용 합니다.  
  
 속성 시트 스타일 Microsoft Outlook의 경우 프레임 워크에 속성 시트의 왼쪽 탐색 단추 목록이 표시 됩니다. 이 메서드는 속성 페이지를 추가, 후 목록에 해당 하는 단추를 추가 합니다. 속성 페이지를 표시 하려면 해당 단추를 클릭 합니다. 속성 시트의 스타일에 대 한 자세한 내용은 참조 [cmfcpropertysheet:: Setlook](#setlook)합니다.  
  
##  <a name="addpagetotree"></a>CMFCPropertySheet::AddPageToTree  
 트리 컨트롤에 새 속성 페이지를 추가합니다.  
  
```  
void AddPageToTree(
    CMFCPropertySheetCategoryInfo* pCategory,  
    CMFCPropertyPage* pPage,  
    int nIconNum=-1,  
    int nSelIconNum=-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pCategory`  
 부모 트리 노드에 대 한 포인터 또는 `NULL` 지정된 된 페이지를 최상위 노드와 연관 시킬 합니다. 호출 된 [CMFCPropertySheet::AddTreeCategory](#addtreecategory) 이 포인터를 얻는 메서드를 합니다.  
  
 [in] `pPage`  
 속성 페이지 개체에 대 한 포인터입니다.  
  
 [in] `nIconNum`  
 아이콘 또는 아이콘이 사용 되는 경우-1의 0부터 시작 인덱스입니다. 페이지 선택 하지 않은 경우 트리 컨트롤 속성 페이지 옆에 아이콘이 표시 됩니다. 기본값은 -1입니다.  
  
 [in] `nSelIconNum`  
 아이콘 또는 아이콘이 사용 되는 경우-1의 0부터 시작 인덱스입니다. 페이지를 선택 트리 컨트롤 속성 페이지 옆에 아이콘이 표시 됩니다. 기본값은 -1입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 속성 페이지의 트리 컨트롤의 리프로 추가합니다. 속성 페이지를 추가 하려면 만듭니다는 `CMFCPropertySheet` 개체를 호출 하는 [cmfcpropertysheet:: Setlook](#setlook) 메서드를는 `look` 매개 변수 설정 `CMFCPropertySheet::PropSheetLook_Tree`, 한 다음 속성 페이지를 추가 하려면이 방법을 사용 합니다.  
  
##  <a name="addtreecategory"></a>CMFCPropertySheet::AddTreeCategory  
 트리 컨트롤에 새 노드를 추가합니다.  
  
```  
CMFCPropertySheetCategoryInfo* AddTreeCategory(
    LPCTSTR lpszLabel,  
    int nIconNum=-1,  
    int nSelectedIconNum=-1,  
    const CMFCPropertySheetCategoryInfo* pParentCategory=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszLabel`  
 노드의 이름입니다.  
  
 [in] `nIconNum`  
 아이콘 또는 아이콘이 사용 되는 경우-1의 0부터 시작 인덱스입니다. 페이지 선택 하지 않은 경우 트리 컨트롤 속성 페이지 옆에 아이콘이 표시 됩니다. 기본값은 -1입니다.  
  
 [in] `nSelectedIconNum`  
 아이콘 또는 아이콘이 사용 되는 경우-1의 0부터 시작 인덱스입니다. 페이지를 선택 트리 컨트롤 속성 페이지 옆에 아이콘이 표시 됩니다. 기본값은 -1입니다.  
  
 [in] `pParentCategory`  
 부모 트리 노드에 대 한 포인터 또는 `NULL` 지정된 된 페이지를 최상위 노드와 연관 시킬 합니다. 이 매개 변수를 설정의 [CMFCPropertySheet::AddTreeCategory](#addtreecategory) 메서드.  
  
### <a name="return-value"></a>반환 값  
 트리 컨트롤에서 새 노드에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 트리 컨트롤에는 또한 라고 하는 범주, 새 노드를 추가 하려면이 메서드를 사용 합니다. 노드를 추가 하려면 만듭니다는 `CMFCPropertySheet` 개체를 호출 하는 [cmfcpropertysheet:: Setlook](#setlook) 메서드를는 `look` 매개 변수 설정 `CMFCPropertySheet::PropSheetLook_Tree`, 다음이 메서드를 사용 하 여 노드를 추가 합니다.  
  
 이 메서드의 반환 값에 대 한 후속 호출에서 사용 하 여 [CMFCPropertySheet::AddPageToTree](#addpagetotree) 및 [CMFCPropertySheet::AddTreeCategory](#addtreecategory)합니다.  
  
##  <a name="cmfcpropertysheet"></a>CMFCPropertySheet::CMFCPropertySheet  
 `CMFCPropertySheet` 개체를 생성합니다.  
  
```  
CMFCPropertySheet(
    UINT nIDCaption,  
    CWnd* pParentWnd=NULL,  
    UINT iSelectPage=0);

CMFCPropertySheet(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd=NULL,  
    UINT iSelectPage=0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pszCaption`  
 속성 시트 캡션을 포함 하는 문자열입니다. 일 수 없습니다 `NULL`합니다.  
  
 [in] `nIDCaption`  
 속성 시트 캡션을 포함 하는 리소스 ID입니다.  
  
 [in] `pParentWnd`  
 속성 시트의 부모 창에 대 한 포인터 또는 `NULL` 경우 부모 응용 프로그램의 주 창입니다. 기본값은 `NULL`입니다.  
  
 [in] `iSelectPage`  
 Top 속성 페이지의 0부터 시작 하는 인덱스입니다. 기본값은 0입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조에 대 한 매개 변수는 [CPropertySheet::CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet) 생성자입니다.  
  
##  <a name="enablepageheader"></a>CMFCPropertySheet::EnablePageHeader  
 각 페이지 위쪽에서 사용자 지정 머리글을 그릴 공간을 예약합니다.  
  
```  
void EnablePageHeader(int nHeaderHeight);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nHeaderHeight`  
 픽셀 단위로 머리글의 높이입니다.  
  
### <a name="remarks"></a>설명  
 값을 사용 하는 `nHeaderHeight` 매개 변수를 사용자 지정 헤더를 그릴 재정의 [CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader) 메서드.  
  
##  <a name="getheaderheight"></a>CMFCPropertySheet::GetHeaderHeight  
 현재 머리글의 높이를 검색합니다.  
  
```  
int GetHeaderHeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
 픽셀 단위로 머리글의 높이입니다.  
  
### <a name="remarks"></a>설명  
 호출 된 [CMFCPropertySheet::EnablePageHeader](#enablepageheader) 이 메서드를 호출 하기 전에.  
  
##  <a name="getlook"></a>CMFCPropertySheet::GetLook  
 현재 속성 시트의 모양을 지정하는 열거형 값을 검색합니다.  
  
```  
PropSheetLook GetLook() const;  
```  
  
### <a name="return-value"></a>반환 값  
 속성 시트의 모양을 지정 하는 열거형 값 중 하나입니다. 가능한 값 목록은의 설명 섹션에 열거 테이블을 참조 하십시오. [cmfcpropertysheet:: Setlook](#setlook)합니다.  
  
##  <a name="getnavbarwidth"></a>Cmfcpropertysheet:: Getnavbarwidth  
 탐색 모음의 너비를 가져옵니다.  
  
```  
int GetNavBarWidth() const;  
```  
  
### <a name="return-value"></a>반환 값  
 탐색 모음의 너비(픽셀)입니다.  
  
##  <a name="gettab"></a>CMFCPropertySheet::GetTab  
 현재 속성 시트 컨트롤을 지원하는 내부 탭 컨트롤 개체를 검색합니다.  
  
```  
CMFCTabCtrl& GetTab() const;  
```  
  
### <a name="return-value"></a>반환 값  
 내부 탭 컨트롤 개체입니다.  
  
### <a name="remarks"></a>설명  
 속성 시트 탐색 단추 또는 탭된 페이지 집합 목록이 서로 다른 스타일 등의 트리 컨트롤에에서 표시 되도록 설정할 수 있습니다.  
  
 이 메서드를 호출 하기 전에 호출 된 [cmfcpropertysheet:: Setlook](#setlook) 속성 시트 컨트롤의 모양을 설정 하는 메서드. 그런 다음 호출에서 [CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol) 메서드 내부 탭 컨트롤 개체를 초기화 합니다. 탭 컨트롤 개체를 검색 한 다음 속성 시트에 탭과 작동 하도록 해당 개체를 사용 하려면이 메서드를 사용 합니다.  
  
 속성 시트 컨트롤 Microsoft OneNote 스타일에 표시 되도록 설정 되지 않은 경우이 메서드는 디버그 모드에서 어설션 합니다.  
  
##  <a name="initnavigationcontrol"></a>CMFCPropertySheet::InitNavigationControl  
 현재 속성 시트 컨트롤의 모양을 초기화합니다.  
  
```  
virtual CWnd* InitNavigationControl();
```  
  
### <a name="return-value"></a>반환 값  
 속성 시트 컨트롤의 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 속성 시트 컨트롤 탭된 페이지, 트리 컨트롤 또는 탐색 단추 목록이 집합 등의 여러 다른 형식으로 나타날 수 있습니다. 사용 하 여는 [cmfcpropertysheet:: Setlook](#setlook) 메서드 속성 시트 컨트롤의 모양을 지정할 수 있습니다.  
  
##  <a name="onactivatepage"></a>CMFCPropertySheet::OnActivatePage  
 속성 페이지를 사용하도록 설정한 경우 프레임워크에서 호출됩니다.  
  
```  
virtual void OnActivatePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pPage`  
 Enabled 속성 페이지를 나타내는 속성 page 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로이 메서드는 enabled 속성 페이지 스크롤해서 보이면 확인 합니다. 현재 속성 시트 스타일의 Microsoft Outlook 창 들어 있는 경우이 메서드는 해당 Outlook 단추 선택된 상태를 설정 합니다.  
  
##  <a name="ondrawpageheader"></a>CMFCPropertySheet::OnDrawPageHeader  
 사용자 지정 속성 페이지에 대 한 헤더를 그리기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDrawPageHeader(
    CDC* pDC,  
    int nPage,  
    CRect rectHeader);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `nPage`  
 0부터 시작 하는 속성 페이지 번호입니다.  
  
 [in] `rectHeader`  
 머리글을 그리는 위치를 지정 하는 경계 사각형입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로이 메서드는 아무 작업도 수행 하지 않습니다. 이 메서드를 재정의 하는 경우 호출 된 [CMFCPropertySheet::EnablePageHeader](#enablepageheader) 메서드 전에 프레임 워크는이 메서드를 호출 합니다.  
  
##  <a name="onremovetreepage"></a>CMFCPropertySheet::OnRemoveTreePage  
 트리 컨트롤에서 속성 페이지를 제거하기 위해 프레임워크에서 호출됩니다.  
  
```  
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pPage`  
 제거할 속성 페이지를 나타내는 속성 page 개체에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
##  <a name="removecategory"></a>CMFCPropertySheet::RemoveCategory  
 트리 컨트롤에서 노드를 제거합니다.  
  
```  
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pCategory`  
 제거 하는 범주 (노드)에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 또한 라고 하는 범주를 트리 컨트롤에서 노드를 제거 하려면이 메서드를 사용 합니다. 사용 하 여는 [CMFCPropertySheet::AddTreeCategory](#addtreecategory) 트리 컨트롤 노드를 추가 하는 메서드.  
  
##  <a name="removepage"></a>CMFCPropertySheet::RemovePage  
 속성 시트에서 속성 페이지를 제거합니다.  
  
```  
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pPage`  
 제거할 속성 페이지를 나타내는 속성 페이지 개체에 대 한 포인터입니다. 일 수 없습니다 `NULL`합니다.  
  
 [in] `nPage`  
 제거할 페이지의 0부터 시작 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 지정 된 속성 페이지를 제거 하 고 해당 창과 연결된을 제거 합니다. 속성 페이지는 개체는 `pPage` 매개 변수 지정 될 때까지 제거 되지 않습니다는 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) 창이 닫혀 있습니다.  
  
##  <a name="seticonslist"></a>CMFCPropertySheet::SetIconsList  
 Outlook 창의 탐색 컨트롤에서 사용되는 이미지 목록을 지정합니다.  
  
```  
BOOL SetIconsList(
    UINT uiImageListResID,  
    int cx,  
    COLORREF clrTransparent=RGB(255, 0, 255));
void SetIconsList(HIMAGELIST hIcons);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiImageListResID`  
 이미지 목록의 리소스 ID입니다.  
  
 [in] `cx`  
 픽셀 이미지 목록에 있는 아이콘의 너비입니다.  
  
 [in] `clrTransparent`  
 투명 한 이미지 색입니다. 이 색이 지정 된 이미지의 부품 투명 하 게 됩니다. 기본값은 색 자홍, RGB(255,0,255) 합니다.  
  
 [in] `hIcons`  
 기존 이미지 목록에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 방법은 구문, 오버 로드 `TRUE` 이 메서드가 성공적 이면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 속성 시트 스타일 Microsoft Outlook의 경우 프레임 워크 속성 시트의 왼쪽에 Outlook 창 컨트롤을 호출 하는 탐색 단추 목록이 표시 됩니다. 이 메서드를 사용 하 여 Outlook 창 컨트롤에서 사용할 이미지 목록을 설정 합니다.  
  
 이 메서드를 지원 하는 방법에 대 한 자세한 내용은 참조 [CImageList::Create](../../mfc/reference/cimagelist-class.md#create) 및 [CImageList::Add](../../mfc/reference/cimagelist-class.md#add)합니다. 속성 시트의 스타일을 설정 하는 방법에 대 한 자세한 내용은 참조 [cmfcpropertysheet:: Setlook](#setlook)합니다.  
  
##  <a name="setlook"></a>Cmfcpropertysheet:: Setlook  
 속성 시트의 모양을 지정합니다.  
  
```  
void SetLook(
    PropSheetLook look,  
    int nNavControlWidth=100);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `look`  
 속성 시트의 모양을 지정 하는 열거형 값 중 하나입니다. 속성 시트에 대 한 기본 스타일은 `CMFCPropertySheet::PropSheetLook_Tabs`합니다. 자세한 내용은이 항목의 주의 섹션의 표를 참조 하세요.  
  
 [in] `nNavControlWidth`  
 픽셀 단위로 탐색 컨트롤의 너비입니다. 기본값은 100입니다.  
  
### <a name="remarks"></a>설명  
 기본값이 아닌 스타일의 속성 시트를 표시 하려면 속성 시트 창을 만들기 전에이 메서드를 호출 합니다.  
  
 에 지정할 수 있는 열거 값을 나열 하는 다음 표에서 `look` 매개 변수입니다.  
  
|값|설명|  
|-----------|-----------------|  
|`CMFCPropertySheet::PropSheetLook_Tabs`|(기본값) 각 속성 페이지에 대 한 탭을 표시합니다. 탭 속성 시트의 위쪽에 표시 하 고 단일 행에 들어가는 것 보다 더 많은 탭에 있는 경우 누적 됩니다.|  
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|스타일 속성 시트의 왼쪽에 있는 Microsoft Outlook 표시줄의 탐색 단추 목록을 표시합니다. 각 단추는 목록에서 속성 페이지에 해당합니다. 프레임 워크 목록의 표시 영역에 들어가는 것 보다 더 많은 단추 있는 경우 스크롤 화살표를 표시 합니다.|  
|`CMFCPropertySheet::PropSheetLook_Tree`|트리 컨트롤을 속성 시트의 왼쪽에 표시 됩니다. 트리 컨트롤의 부모 또는 자식 노드 각 속성 페이지에 해당합니다. 프레임 워크의 트리 컨트롤의 표시 영역에 들어가는 것 보다 더 많은 노드가 있는 경우 스크롤 화살표를 표시 합니다.|  
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|각 속성 페이지에 대 한 Microsoft onenote 스타일의 탭을 표시합니다. 속성 시트의 위쪽에 있는 탭을 표시 하는 프레임 워크와 스크롤 화살표에 보다 더 많은 탭에 있는 경우는 단일 행에입니다.|  
|`CMFCPropertySheet::PropSheetLook_List`|속성 시트의 왼쪽에 표시 됩니다. 각 목록 항목 속성 페이지에 해당합니다. 프레임 워크 목록의 표시 영역에 들어가는 것 보다 더 많은 목록 항목이 있는 경우 스크롤 화살표를 표시 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyPage 클래스](../../mfc/reference/cmfcpropertypage-class.md)   
 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)
