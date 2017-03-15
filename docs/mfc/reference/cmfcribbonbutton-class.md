---
title: "CMFCRibbonButton 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonButton class
ms.assetid: 732e941c-9504-4b83-a691-d18075965d53
caps.latest.revision: 42
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
ms.openlocfilehash: 08672f10cf67a773f2af8d12130c4e3f5b497e11
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonbutton-class"></a>CMFCRibbonButton 클래스
`CMFCRibbonButton` 클래스는 패널, 빠른 실행 도구 모음 및 팝업 메뉴와 같은 리본 막대 요소에 배치할 수 있는 단추를 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonButton : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonButton::CMFCRibbonButton](#cmfcribbonbutton)|리본 단추 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonButton::AddSubItem](#addsubitem)|단추와 연결되는 메뉴 항목을 팝업 메뉴에 추가합니다.|  
|[CMFCRibbonButton::CanBeStretched](#canbestretched)|(재정의 [CMFCRibbonBaseElement::CanBeStretched](../../mfc/reference/cmfcribbonbaseelement-class.md#canbestretched).)|  
|[CMFCRibbonButton::CleanUpSizes](#cleanupsizes)|(재정의 [CMFCRibbonBaseElement::CleanUpSizes](../../mfc/reference/cmfcribbonbaseelement-class.md#cleanupsizes).)|  
|[CMFCRibbonButton::ClosePopupMenu](#closepopupmenu)|(재정의 [CMFCRibbonBaseElement::ClosePopupMenu](../../mfc/reference/cmfcribbonbaseelement-class.md#closepopupmenu).)|  
|[CMFCRibbonButton::DrawBottomText](#drawbottomtext)||  
|[CMFCRibbonButton::DrawImage](#drawimage)|(재정의 [CMFCRibbonBaseElement::DrawImage](../../mfc/reference/cmfcribbonbaseelement-class.md#drawimage).)|  
|[CMFCRibbonButton::DrawRibbonText](#drawribbontext)||  
|[CMFCRibbonButton::FindSubItemIndexByID](#findsubitemindexbyid)|지정된 명령 ID와 연결된 팝업 메뉴 항목의 인덱스를 반환합니다.|  
|[CMFCRibbonButton::GetCommandRect](#getcommandrect)||  
|[CMFCRibbonButton::GetCompactSize](#getcompactsize)|리본 요소의 압축 크기를 반환합니다. (재정의 [CMFCRibbonBaseElement::GetCompactSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getcompactsize).)|  
|[CMFCRibbonButton::GetIcon](#geticon)||  
|[CMFCRibbonButton::GetImageIndex](#getimageindex)|단추와 연결된 이미지의 인덱스를 반환합니다.|  
|[CMFCRibbonButton::GetImageSize](#getimagesize)|리본 요소의 이미지 크기를 반환합니다. (재정의 [CMFCRibbonBaseElement::GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|  
|[CMFCRibbonButton::GetIntermediateSize](#getintermediatesize)|중간 상태인 리본 요소의 크기를 반환합니다. (재정의 [CMFCRibbonBaseElement::GetIntermediateSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getintermediatesize).)|  
|[CMFCRibbonButton::GetMenu](#getmenu)|리본 단추에 할당된 Windows 메뉴에 대한 핸들을 반환합니다.|  
|[CMFCRibbonButton::GetMenuRect](#getmenurect)||  
|[CMFCRibbonButton::GetRegularSize](#getregularsize)|리본 요소의 보통 크기를 반환합니다. (재정의 [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonButton::GetSubItems](#getsubitems)||  
|[CMFCRibbonButton::GetTextRowHeight](#gettextrowheight)||  
|[CMFCRibbonButton::GetToolTipText](#gettooltiptext)|리본 요소의 도구 설명 텍스트를 반환합니다. (재정의 [CMFCRibbonBaseElement::GetToolTipText](../../mfc/reference/cmfcribbonbaseelement-class.md#gettooltiptext).)|  
|[CMFCRibbonButton::HasCompactMode](#hascompactmode)|리본 요소에 압축 모드가 있는지 여부를 지정합니다. (재정의 [CMFCRibbonBaseElement::HasCompactMode](../../mfc/reference/cmfcribbonbaseelement-class.md#hascompactmode).)|  
|[CMFCRibbonButton::HasIntermediateMode](#hasintermediatemode)|리본 요소에 중간 모드가 있는지 여부를 지정합니다. (재정의 [CMFCRibbonBaseElement::HasIntermediateMode](../../mfc/reference/cmfcribbonbaseelement-class.md#hasintermediatemode).)|  
|[CMFCRibbonButton::HasLargeMode](#haslargemode)|리본 요소에 큰 모드가 있는지 여부를 결정합니다. (재정의 [CMFCRibbonBaseElement::HasLargeMode](../../mfc/reference/cmfcribbonbaseelement-class.md#haslargemode).)|  
|[CMFCRibbonButton::HasMenu](#hasmenu)|(재정의 [CMFCRibbonBaseElement::HasMenu](../../mfc/reference/cmfcribbonbaseelement-class.md#hasmenu).)|  
|[CMFCRibbonButton::IsAlwaysDrawBorder](#isalwaysdrawborder)||  
|[CMFCRibbonButton::IsAlwaysLargeImage](#isalwayslargeimage)|(재정의 [CMFCRibbonBaseElement::IsAlwaysLargeImage](../../mfc/reference/cmfcribbonbaseelement-class.md#isalwayslargeimage).)|  
|[CMFCRibbonButton::IsApplicationButton](#isapplicationbutton)||  
|[CMFCRibbonButton::IsCommandAreaHighlighted](#iscommandareahighlighted)||  
|[CMFCRibbonButton::IsDefaultCommand](#isdefaultcommand)|리본 단추에 대한 기본 명령을 사용하도록 설정했는지 여부를 확인합니다.|  
|[CMFCRibbonButton::IsDefaultPanelButton](#isdefaultpanelbutton)||  
|[CMFCRibbonButton::IsDrawTooltipImage](#isdrawtooltipimage)||  
|[CMFCRibbonButton::IsLargeImage](#islargeimage)||  
|[CMFCRibbonButton::IsMenuAreaHighlighted](#ismenuareahighlighted)||  
|[CMFCRibbonButton::IsMenuOnBottom](#ismenuonbottom)||  
|[CMFCRibbonButton::IsPopupDefaultMenuLook](#ispopupdefaultmenulook)||  
|[CMFCRibbonButton::IsRightAlignMenu](#isrightalignmenu)|메뉴가 오른쪽 맞춤인지 여부를 확인합니다.|  
|[CMFCRibbonButton::IsSingleLineText](#issinglelinetext)||  
|[CMFCRibbonButton::OnCalcTextSize](#oncalctextsize)|(재정의 [CMFCRibbonBaseElement::OnCalcTextSize](../../mfc/reference/cmfcribbonbaseelement-class.md#oncalctextsize).)|  
|[CMFCRibbonButton::OnDrawBorder](#ondrawborder)||  
|[CMFCRibbonButton::OnDraw](#ondraw)|리본 요소를 그리기 위해 프레임워크에서 호출됩니다. (재정의 [CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonButton::OnFillBackground](#onfillbackground)||  
|[CMFCRibbonButton::RemoveAllSubItems](#removeallsubitems)|팝업 메뉴에서 모든 메뉴 항목을 제거합니다.|  
|[CMFCRibbonButton::RemoveSubItem](#removesubitem)|팝업 메뉴에서 메뉴 항목을 제거합니다.|  
|[CMFCRibbonButton::SetACCData](#setaccdata)|(재정의 [CMFCRibbonBaseElement::SetACCData](../../mfc/reference/cmfcribbonbaseelement-class.md#setaccdata).)|  
|[CMFCRibbonButton::SetAlwaysLargeImage](#setalwayslargeimage)|사용자가 단추를 축소하면 단추가 큰 이미지나 작은 이미지 중 어느 것을 표시하는지를 지정합니다.|  
|[CMFCRibbonButton::SetDefaultCommand](#setdefaultcommand)|리본 단추에 대한 기본 명령을 사용하도록 설정합니다.|  
|[CMFCRibbonButton::SetDescription](#setdescription)|리본 요소에 대한 설명을 설정합니다. (재정의 [CMFCRibbonBaseElement::SetDescription](../../mfc/reference/cmfcribbonbaseelement-class.md#setdescription).)|  
|[CMFCRibbonButton::SetImageIndex](#setimageindex)|단추 이미지에 인덱스를 할당합니다.|  
|[CMFCRibbonButton::SetMenu](#setmenu)|리본 단추에 팝업 메뉴를 할당합니다.|  
|[CMFCRibbonButton::SetParentCategory](#setparentcategory)|(재정의 [CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|  
|[CMFCRibbonButton::SetRightAlignMenu](#setrightalignmenu)|팝업 메뉴를 단추 오른쪽에 맞춥니다.|  
|[CMFCRibbonButton::SetText](#settext)|리본 요소의 텍스트를 설정합니다. (재정의 [CMFCRibbonBaseElement::SetText](../../mfc/reference/cmfcribbonbaseelement-class.md#settext).)|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonButton::OnClick](#onclick)|사용자가 단추를 클릭하면 프레임워크에서 호출됩니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CMFCRibbonButton` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 예제에서는     `CMFCRibbonButton` 클래스의 개체를 생성하고, 리본 단추에 팝업 메뉴를 할당하고, 단추 설명을 설정하고, 팝업 메뉴에서 메뉴 항목을 제거하고, 팝업 메뉴를 단추 가장자리로 오른쪽 맞춤하는 방법을 설명합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp #&7;](../../mfc/reference/codesnippet/cpp/cmfcribbonbutton-class_1.cpp)]  
  
## <a name="remarks"></a>주의  
 응용 프로그램에서 리본 메뉴 단추를 사용 하 여 단추 개체를 생성 하 고 적절 한 리본 메뉴에 추가 [패널](../../mfc/reference/cmfcribbonpanel-class.md)합니다.  
  
```  
CMFCRibbonPanel* pPanel = pCategory->AddPanel (
    _T("Clipboard"), // Panel name  
    m_PanelIcons.ExtractIcon (0)); // Panel icon  

// Create the first button ("Paste"):  
CMFCRibbonButton* pPasteButton = 
    new CMFCRibbonButton (ID_EDIT_PASTE, _T("Paste"), -1, 0);

// The third parameter (-1) disables small images for button.  
// This button is always displayed with a large image  
// Associate a pop-up menu with the "Paste" button:  
pPasteButton->SetMenu (IDR_CONTEXT_MENU);

// Add buttons to the panel. These buttons have only small images.  
pPanel->Add (new CMFCRibbonButton (ID_EDIT_CUT, _T("Cut"), 1));
pPanel->Add (new CMFCRibbonButton (ID_EDIT_COPY, _T("Copy"), 2));
pPanel->Add (new CMFCRibbonButton (ID_EDIT_PAINT, _T("Paint"), 9));
```  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxribbonbutton.h  
  
##  <a name="a-nameaddsubitema--cmfcribbonbuttonaddsubitem"></a><a name="addsubitem"></a>CMFCRibbonButton::AddSubItem  
 단추와 연결되는 메뉴 항목을 팝업 메뉴에 추가합니다.  
  
```  
void AddSubItem(
    CMFCRibbonBaseElement* pSubItem,  
    int nIndex=-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pSubItem`  
 추가할 새 요소에 대 한 포인터를 지정 합니다.  
  
 [in] `nIndex`  
 단추, 메뉴 항목의 배열에 요소를 추가 하는 인덱스를 지정 합니다. 메뉴 항목의 배열 끝에 요소를 추가 하려면-1입니다.  
  
##  <a name="a-namecanbestretcheda--cmfcribbonbuttoncanbestretched"></a><a name="canbestretched"></a>CMFCRibbonButton::CanBeStretched  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namecleanupsizesa--cmfcribbonbuttoncleanupsizes"></a><a name="cleanupsizes"></a>CMFCRibbonButton::CleanUpSizes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void CleanUpSizes();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameclosepopupmenua--cmfcribbonbuttonclosepopupmenu"></a><a name="closepopupmenu"></a>CMFCRibbonButton::ClosePopupMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ClosePopupMenu();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namecmfcribbonbuttona--cmfcribbonbuttoncmfcribbonbutton"></a><a name="cmfcribbonbutton"></a>CMFCRibbonButton::CMFCRibbonButton  
 리본 단추 개체를 생성합니다.  
  
```  
CMFCRibbonButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex=-1,  
    int nLargeImageIndex=-1,  
    BOOL bAlwaysShowDescription=FALSE);

CMFCRibbonButton(
    UINT nID,  
    LPCTSTR lpszText,  
    HICON hIcon,  
    BOOL bAlwaysShowDescription=FALSE,  
    HICON hIconSmall=NULL,  
    BOOL bAutoDestroyIcon=FALSE,  
    BOOL bAlphaBlendIcon=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nID`  
 단추의 명령 ID를 지정합니다.  
  
 [in] `lpszText`  
 단추의 텍스트 레이블을 지정합니다.  
  
 [in] `nSmallImageIndex`  
 부모 범주의 이미지 목록에서 단추의 작은 이미지의 인덱스를 지정합니다.  
  
 [in] `nLargeImageIndex`  
 부모 범주의 이미지 목록에서 단추의 큰 이미지의 인덱스를 지정합니다.  
  
 [in] `hIcon`  
 단추의 이미지와 응용 프로그램이 사용 되는 아이콘에 대 한 핸들을 지정 합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 생성 하는 방법을 한 `CMFCRibbonButton` 개체입니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp #&6;](../../mfc/reference/codesnippet/cpp/cmfcribbonbutton-class_2.cpp)]  
  
##  <a name="a-namedrawbottomtexta--cmfcribbonbuttondrawbottomtext"></a><a name="drawbottomtext"></a>CMFCRibbonButton::DrawBottomText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CSize DrawBottomText(
    CDC* pDC,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `bCalcOnly`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namedrawimagea--cmfcribbonbuttondrawimage"></a><a name="drawimage"></a>CMFCRibbonButton::DrawImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void DrawImage(
    CDC* pDC,  
    RibbonImageType type,  
    CRect rectImage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `type`  
 [in] `rectImage`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namedrawribbontexta--cmfcribbonbuttondrawribbontext"></a><a name="drawribbontext"></a>CMFCRibbonButton::DrawRibbonText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int DrawRibbonText(
    CDC* pDC,  
    const CString& strText,  
    CRect rectText,  
    UINT uiDTFlags,  
    COLORREF clrText = (COLORREF)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `strText`  
 [in] `rectText`  
 [in] `uiDTFlags`  
 [in] `clrText`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namefindsubitemindexbyida--cmfcribbonbuttonfindsubitemindexbyid"></a><a name="findsubitemindexbyid"></a>CMFCRibbonButton::FindSubItemIndexByID  
 지정된 명령 ID와 연결된 팝업 메뉴 항목의 인덱스를 반환합니다.  
  
```  
int FindSubItemIndexByID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiID`  
 팝업 메뉴 항목의 명령 ID를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 와 연결 된 하위 항목의&0;부터 시작 하는 인덱스는 `uiID`합니다. 이러한 하위 항목이 없는 경우-1입니다.  
  
##  <a name="a-namegetcommandrecta--cmfcribbonbuttongetcommandrect"></a><a name="getcommandrect"></a>CMFCRibbonButton::GetCommandRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetCommandRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetcompactsizea--cmfcribbonbuttongetcompactsize"></a><a name="getcompactsize"></a>CMFCRibbonButton::GetCompactSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegeticona--cmfcribbonbuttongeticon"></a><a name="geticon"></a>CMFCRibbonButton::GetIcon  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
HICON GetIcon(BOOL bLargeIcon = TRUE) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bLargeIcon`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetimageindexa--cmfcribbonbuttongetimageindex"></a><a name="getimageindex"></a>CMFCRibbonButton::GetImageIndex  
 단추와 연결된 이미지의 인덱스를 반환합니다.  
  
```  
int GetImageIndex(BOOL bLargeImage) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bLargeImage`  
 경우 `TRUE`, 큰 이미지를 포함 하 고, 그렇지 않으면 작은 이미지를 포함 하는 이미지 목록에서 이미지 인덱스를 반환 하는 이미지 목록의 이미지 인덱스를 반환 합니다.  
  
### <a name="return-value"></a>반환 값  
 연결 된 이미지 목록에 있는 단추 이미지의 인덱스입니다.  
  
##  <a name="a-namegetimagesizea--cmfcribbonbuttongetimagesize"></a><a name="getimagesize"></a>CMFCRibbonButton::GetImageSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetImageSize(RibbonImageType type) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `type`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetintermediatesizea--cmfcribbonbuttongetintermediatesize"></a><a name="getintermediatesize"></a>CMFCRibbonButton::GetIntermediateSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetmenua--cmfcribbonbuttongetmenu"></a><a name="getmenu"></a>CMFCRibbonButton::GetMenu  
 리본 단추에 할당된 Windows 메뉴에 대한 핸들을 반환합니다.  
  
```  
HMENU GetMenu() const;  
```  
  
### <a name="return-value"></a>반환 값  
 단추;에 지정 된 Windows 메뉴에 대 한 핸들 `NULL` 메뉴를 지정이 없는 경우.  
  
##  <a name="a-namegetmenurecta--cmfcribbonbuttongetmenurect"></a><a name="getmenurect"></a>CMFCRibbonButton::GetMenuRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetMenuRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetregularsizea--cmfcribbonbuttongetregularsize"></a><a name="getregularsize"></a>CMFCRibbonButton::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetsubitemsa--cmfcribbonbuttongetsubitems"></a><a name="getsubitems"></a>CMFCRibbonButton::GetSubItems  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& GetSubItems() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegettextrowheighta--cmfcribbonbuttongettextrowheight"></a><a name="gettextrowheight"></a>CMFCRibbonButton::GetTextRowHeight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTextRowHeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegettooltiptexta--cmfcribbonbuttongettooltiptext"></a><a name="gettooltiptext"></a>CMFCRibbonButton::GetToolTipText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CString GetToolTipText() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namehascompactmodea--cmfcribbonbuttonhascompactmode"></a><a name="hascompactmode"></a>CMFCRibbonButton::HasCompactMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namehasintermediatemodea--cmfcribbonbuttonhasintermediatemode"></a><a name="hasintermediatemode"></a>CMFCRibbonButton::HasIntermediateMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasIntermediateMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namehaslargemodea--cmfcribbonbuttonhaslargemode"></a><a name="haslargemode"></a>CMFCRibbonButton::HasLargeMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namehasmenua--cmfcribbonbuttonhasmenu"></a><a name="hasmenu"></a>CMFCRibbonButton::HasMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameisalwaysdrawbordera--cmfcribbonbuttonisalwaysdrawborder"></a><a name="isalwaysdrawborder"></a>CMFCRibbonButton::IsAlwaysDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsAlwaysDrawBorder() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameisalwayslargeimagea--cmfcribbonbuttonisalwayslargeimage"></a><a name="isalwayslargeimage"></a>CMFCRibbonButton::IsAlwaysLargeImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsAlwaysLargeImage() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameisapplicationbuttona--cmfcribbonbuttonisapplicationbutton"></a><a name="isapplicationbutton"></a>CMFCRibbonButton::IsApplicationButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsApplicationButton() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameiscommandareahighlighteda--cmfcribbonbuttoniscommandareahighlighted"></a><a name="iscommandareahighlighted"></a>CMFCRibbonButton::IsCommandAreaHighlighted  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsCommandAreaHighlighted() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameisdefaultcommanda--cmfcribbonbuttonisdefaultcommand"></a><a name="isdefaultcommand"></a>CMFCRibbonButton::IsDefaultCommand  
 리본 메뉴 단추에 대 한 기본 명령 사용 되는지 여부를 지정 합니다.  
  
```  
BOOL IsDefaultCommand() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`리본 메뉴 단추;에 대 한 기본 명령을 사용 하는 경우 `FALSE` 그렇지 않은 경우.  
  
##  <a name="a-nameisdefaultpanelbuttona--cmfcribbonbuttonisdefaultpanelbutton"></a><a name="isdefaultpanelbutton"></a>CMFCRibbonButton::IsDefaultPanelButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsDefaultPanelButton() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameisdrawtooltipimagea--cmfcribbonbuttonisdrawtooltipimage"></a><a name="isdrawtooltipimage"></a>CMFCRibbonButton::IsDrawTooltipImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsDrawTooltipImage() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameislargeimagea--cmfcribbonbuttonislargeimage"></a><a name="islargeimage"></a>CMFCRibbonButton::IsLargeImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsLargeImage() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameismenuareahighlighteda--cmfcribbonbuttonismenuareahighlighted"></a><a name="ismenuareahighlighted"></a>CMFCRibbonButton::IsMenuAreaHighlighted  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsMenuAreaHighlighted() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameismenuonbottoma--cmfcribbonbuttonismenuonbottom"></a><a name="ismenuonbottom"></a>CMFCRibbonButton::IsMenuOnBottom  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsMenuOnBottom() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameispopupdefaultmenulooka--cmfcribbonbuttonispopupdefaultmenulook"></a><a name="ispopupdefaultmenulook"></a>CMFCRibbonButton::IsPopupDefaultMenuLook  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsPopupDefaultMenuLook() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameisrightalignmenua--cmfcribbonbuttonisrightalignmenu"></a><a name="isrightalignmenu"></a>CMFCRibbonButton::IsRightAlignMenu  
 메뉴에 오른쪽 맞춤 인지 여부를 지정 합니다.  
  
```  
BOOL IsRightAlignMenu() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`오른쪽 맞춤; 메뉴 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-nameissinglelinetexta--cmfcribbonbuttonissinglelinetext"></a><a name="issinglelinetext"></a>CMFCRibbonButton::IsSingleLineText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsSingleLineText() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameoncalctextsizea--cmfcribbonbuttononcalctextsize"></a><a name="oncalctextsize"></a>CMFCRibbonButton::OnCalcTextSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnCalcTextSize(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonclicka--cmfcribbonbuttononclick"></a><a name="onclick"></a>CMFCRibbonButton::OnClick  
 사용자가 단추를 클릭하면 프레임워크에서 호출됩니다.  
  
```  
virtual void OnClick(CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 마우스 클릭의 위치를 지정합니다.  
  
### <a name="remarks"></a>주의  
 이 이벤트를 처리 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="a-nameondrawa--cmfcribbonbuttonondraw"></a><a name="ondraw"></a>CMFCRibbonButton::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameondrawbordera--cmfcribbonbuttonondrawborder"></a><a name="ondrawborder"></a>CMFCRibbonButton::OnDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBorder(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameonfillbackgrounda--cmfcribbonbuttononfillbackground"></a><a name="onfillbackground"></a>CMFCRibbonButton::OnFillBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameremoveallsubitemsa--cmfcribbonbuttonremoveallsubitems"></a><a name="removeallsubitems"></a>CMFCRibbonButton::RemoveAllSubItems  
 팝업 메뉴에서 모든 메뉴 항목을 제거합니다.  
  
```  
void RemoveAllSubItems();
```  
  
##  <a name="a-nameremovesubitema--cmfcribbonbuttonremovesubitem"></a><a name="removesubitem"></a>CMFCRibbonButton::RemoveSubItem  
 팝업 메뉴에서 메뉴 항목을 제거합니다.  
  
```  
BOOL RemoveSubItem(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 제거 하려는 메뉴 항목의&0;부터 시작 하는 인덱스를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`지정된 된 항목이 성공적으로 제거 된 경우 그렇지 않으면 `FALSE` 경우 `nIndex` 가 음수 이거나 팝업 메뉴에서 메뉴 항목의 수를 초과 합니다.  
  
##  <a name="a-namesetaccdataa--cmfcribbonbuttonsetaccdata"></a><a name="setaccdata"></a>CMFCRibbonButton::SetACCData  
 리본 단추에 대한 내게 필요한 옵션 데이터를 설정합니다.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pParent`  
 리본 요소에 대한 부모 창입니다.  
  
 `data`  
 리본 요소에 대한 내게 필요한 옵션 데이터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 `TRUE` 를 반환하고, 실패하면 FALSE를 반환합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namesetalwayslargeimagea--cmfcribbonbuttonsetalwayslargeimage"></a><a name="setalwayslargeimage"></a>CMFCRibbonButton::SetAlwaysLargeImage  
 사용자가 단추를 축소하면 단추가 큰 이미지나 작은 이미지 중 어느 것을 표시하는지를 지정합니다.  
  
```  
void SetAlwaysLargeImage(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bSet`  
 경우 `TRUE`, 단추는 큰 이미지를 표시 합니다. 그렇지 않으면 단추는 작은 이미지를 표시 합니다.  
  
##  <a name="a-namesetdefaultcommanda--cmfcribbonbuttonsetdefaultcommand"></a><a name="setdefaultcommand"></a>CMFCRibbonButton::SetDefaultCommand  
 리본 단추에 대한 기본 명령을 사용하도록 설정합니다.  
  
```  
void SetDefaultCommand(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bSet`  
 경우 `TRUE`, 단추는 기본 명령을 실행할 수 있습니다. 경우 `FALSE`, 단추는 해당 기본 명령을 실행할 수 없습니다.  
  
### <a name="remarks"></a>주의  
 `bSet`관련이 단추 메뉴에 있습니다. 경우 `bSet` 는 `TRUE`, 단추를 누르면 해당 기본 명령 실행 수 및 사용자 단추의 오른쪽 모서리에 있는 화살표를 클릭 하는 경우에 할당된 된 팝업 메뉴가 나타납니다. 그렇지 않으면 단추는 기본 명령을 실행할 수 없습니다 하 고 팝업 메뉴 단추의 어떤 영역에 관계 없이 사용자가 클릭 나타납니다.  
  
##  <a name="a-namesetdescriptiona--cmfcribbonbuttonsetdescription"></a><a name="setdescription"></a>CMFCRibbonButton::SetDescription  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetDescription(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszText`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namesetimageindexa--cmfcribbonbuttonsetimageindex"></a><a name="setimageindex"></a>CMFCRibbonButton::SetImageIndex  
 단추 이미지에 인덱스를 할당합니다.  
  
```  
void SetImageIndex(
    int nIndex,  
    BOOL bLargeImage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 이미지 인덱스를 지정 합니다.  
  
 [in] `bLargeImage`  
 경우 `TRUE`, 큰 이미지의 목록에 지정된 된 인덱스를 참조 합니다. 그렇지 않은 경우 인덱스 작은 이미지의 목록으로 참조합니다.  
  
##  <a name="a-namesetmenua--cmfcribbonbuttonsetmenu"></a><a name="setmenu"></a>CMFCRibbonButton::SetMenu  
 리본 단추에 팝업 메뉴를 할당합니다.  
  
```  
void SetMenu(
    HMENU hMenu,  
    BOOL bIsDefaultCommand=FALSE,  
    BOOL bRightAlign=FALSE);

void SetMenu(
    UINT uiMenuResID,  
    BOOL bIsDefaultCommand=FALSE,  
    BOOL bRightAlign=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `hMenu`  
 창 메뉴에 대 한 핸들입니다.  
  
 `bIsDefaultCommand`  
 경우 `TRUE`, 단추는 기본 명령을 실행할 수 있습니다. 즉, 단추 팝업 메뉴를 표시 하는 그렇지 않은 경우.  
  
 `bRightAlign`  
 경우 `TRUE`, 메뉴는 오른쪽 정렬 합니다. 그렇지 않은 경우 메뉴에는 왼쪽에 맞춰집니다.  
  
 `uiMenuResID`  
 메뉴 리소스 id입니다.  
  
### <a name="remarks"></a>주의  
 응용 프로그램의 메뉴 단추에 할당 단추 오른쪽 면에 화살표가 표시 됩니다. 경우 `bIsDefaultCommand` 는 `TRUE`, 메뉴 사용자의 화살표를 클릭 하는 경우에 나타납니다. 사용자가 단추를 클릭 하면 해당 기본 명령이 실행 됩니다. 경우 `bIsDefaultCommand` 는 `FALSE`, 버튼을 클릭 하 여의 메뉴가 나타납니다.  
  
##  <a name="a-namesetparentcategorya--cmfcribbonbuttonsetparentcategory"></a><a name="setparentcategory"></a>CMFCRibbonButton::SetParentCategory  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pParent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParent`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namesetrightalignmenua--cmfcribbonbuttonsetrightalignmenu"></a><a name="setrightalignmenu"></a>CMFCRibbonButton::SetRightAlignMenu  
 팝업 메뉴 단추의 가장자리에 맞춥니다.  
  
```  
void SetRightAlignMenu(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bSet`  
 경우 `TRUE`, 메뉴는 오른쪽 정렬 합니다. 그렇지 않으면 메뉴에는 왼쪽 맞춤  
  
##  <a name="a-namesettexta--cmfcribbonbuttonsettext"></a><a name="settext"></a>CMFCRibbonButton::SetText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszText`  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)

