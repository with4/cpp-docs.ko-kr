---
title: "CMFCRibbonPanel 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonPanel
- AFXRIBBONPANEL/CMFCRibbonPanel
- AFXRIBBONPANEL/CMFCRibbonPanel::CMFCRibbonPanel
- AFXRIBBONPANEL/CMFCRibbonPanel::Add
- AFXRIBBONPANEL/CMFCRibbonPanel::AddSeparator
- AFXRIBBONPANEL/CMFCRibbonPanel::AddToolBar
- AFXRIBBONPANEL/CMFCRibbonPanel::FindByData
- AFXRIBBONPANEL/CMFCRibbonPanel::FindByID
- AFXRIBBONPANEL/CMFCRibbonPanel::GetCaptionHeight
- AFXRIBBONPANEL/CMFCRibbonPanel::GetCount
- AFXRIBBONPANEL/CMFCRibbonPanel::GetData
- AFXRIBBONPANEL/CMFCRibbonPanel::GetDefaultButton
- AFXRIBBONPANEL/CMFCRibbonPanel::GetDroppedDown
- AFXRIBBONPANEL/CMFCRibbonPanel::GetElement
- AFXRIBBONPANEL/CMFCRibbonPanel::GetElements
- AFXRIBBONPANEL/CMFCRibbonPanel::GetElementsByID
- AFXRIBBONPANEL/CMFCRibbonPanel::GetFocused
- AFXRIBBONPANEL/CMFCRibbonPanel::GetGalleryRect
- AFXRIBBONPANEL/CMFCRibbonPanel::GetHighlighted
- AFXRIBBONPANEL/CMFCRibbonPanel::GetIndex
- AFXRIBBONPANEL/CMFCRibbonPanel::GetItemIDsList
- AFXRIBBONPANEL/CMFCRibbonPanel::GetName
- AFXRIBBONPANEL/CMFCRibbonPanel::GetParentButton
- AFXRIBBONPANEL/CMFCRibbonPanel::GetParentCategory
- AFXRIBBONPANEL/CMFCRibbonPanel::GetParentMenuBar
- AFXRIBBONPANEL/CMFCRibbonPanel::GetPreferedMenuLocation
- AFXRIBBONPANEL/CMFCRibbonPanel::GetPressed
- AFXRIBBONPANEL/CMFCRibbonPanel::GetRect
- AFXRIBBONPANEL/CMFCRibbonPanel::GetVisibleElements
- AFXRIBBONPANEL/CMFCRibbonPanel::HasElement
- AFXRIBBONPANEL/CMFCRibbonPanel::HitTest
- AFXRIBBONPANEL/CMFCRibbonPanel::HitTestEx
- AFXRIBBONPANEL/CMFCRibbonPanel::Insert
- AFXRIBBONPANEL/CMFCRibbonPanel::InsertSeparator
- AFXRIBBONPANEL/CMFCRibbonPanel::IsCenterColumnVert
- AFXRIBBONPANEL/CMFCRibbonPanel::IsCollapsed
- AFXRIBBONPANEL/CMFCRibbonPanel::IsHighlighted
- AFXRIBBONPANEL/CMFCRibbonPanel::IsJustifyColumns
- AFXRIBBONPANEL/CMFCRibbonPanel::IsMainPanel
- AFXRIBBONPANEL/CMFCRibbonPanel::IsMenuMode
- AFXRIBBONPANEL/CMFCRibbonPanel::MakeGalleryItemVisible
- AFXRIBBONPANEL/CMFCRibbonPanel::OnKey
- AFXRIBBONPANEL/CMFCRibbonPanel::RecalcWidths
- AFXRIBBONPANEL/CMFCRibbonPanel::Remove
- AFXRIBBONPANEL/CMFCRibbonPanel::RemoveAll
- AFXRIBBONPANEL/CMFCRibbonPanel::Replace
- AFXRIBBONPANEL/CMFCRibbonPanel::ReplaceByID
- AFXRIBBONPANEL/CMFCRibbonPanel::SetCenterColumnVert
- AFXRIBBONPANEL/CMFCRibbonPanel::SetData
- AFXRIBBONPANEL/CMFCRibbonPanel::SetElementMenu
- AFXRIBBONPANEL/CMFCRibbonPanel::SetElementRTC
- AFXRIBBONPANEL/CMFCRibbonPanel::SetElementRTCByID
- AFXRIBBONPANEL/CMFCRibbonPanel::SetFocused
- AFXRIBBONPANEL/CMFCRibbonPanel::SetJustifyColumns
- AFXRIBBONPANEL/CMFCRibbonPanel::SetKeys
- AFXRIBBONPANEL/CMFCRibbonPanel::ShowPopup
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonPanel class
ms.assetid: 51d70749-1140-4386-b103-f14082049ba6
caps.latest.revision: 34
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
ms.openlocfilehash: 1f833e1fa59f733734da321718d5db73377fa4bd
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonpanel-class"></a>CMFCRibbonPanel 클래스
리본 요소 집합이 포함된 패널을 구현합니다. 패널을 그리면 지정된 패널 크기에 가능한 한 많은 요소를 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonPanel : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonPanel::CMFCRibbonPanel](#cmfcribbonpanel)|`CMFCRibbonPanel` 개체를 생성하고 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonPanel::Add](#add)|패널에는 리본 요소를 추가합니다.|  
|[CMFCRibbonPanel::AddSeparator](#addseparator)|리본 패널에 구분 기호를 추가 합니다.|  
|[CMFCRibbonPanel::AddToolBar](#addtoolbar)|도구 모음 리본 패널에 추가합니다.|  
|[CMFCRibbonPanel::FindByData](#findbydata)||  
|[CMFCRibbonPanel::FindByID](#findbyid)|지정 된 명령 ID로 식별 하는 요소를 반환 합니다.|  
|[CMFCRibbonPanel::GetCaptionHeight](#getcaptionheight)||  
|[CMFCRibbonPanel::GetCount](#getcount)|리본 패널의 요소 수를 반환합니다.|  
|[CMFCRibbonPanel::GetData](#getdata)|패널에 연결 된 사용자 정의 데이터를 반환 합니다.|  
|[CMFCRibbonPanel::GetDefaultButton](#getdefaultbutton)||  
|[CMFCRibbonPanel::GetDroppedDown](#getdroppeddown)||  
|[CMFCRibbonPanel::GetElement](#getelement)|지정된 된 인덱스에 있는 리본 요소를 반환 합니다.|  
|[CMFCRibbonPanel::GetElements](#getelements)|리본 패널에 포함 된 모든 요소를 검색 합니다.|  
|[CMFCRibbonPanel::GetElementsByID](#getelementsbyid)||  
|[CMFCRibbonPanel::GetFocused](#getfocused)|포커스가 지정된 요소를 반환합니다.|  
|[CMFCRibbonPanel::GetGalleryRect](#getgalleryrect)|갤러리 요소의 경계 사각형을 반환합니다.|  
|[CMFCRibbonPanel::GetHighlighted](#gethighlighted)||  
|[CMFCRibbonPanel::GetIndex](#getindex)||  
|[CMFCRibbonPanel::GetItemIDsList](#getitemidslist)||  
|[CMFCRibbonPanel::GetName](#getname)||  
|[CMFCRibbonPanel::GetParentButton](#getparentbutton)||  
|[CMFCRibbonPanel::GetParentCategory](#getparentcategory)|리본 패널의 부모 범주를 반환합니다.|  
|[CMFCRibbonPanel::GetParentMenuBar](#getparentmenubar)||  
|[CMFCRibbonPanel::GetPreferedMenuLocation](#getpreferedmenulocation)||  
|[CMFCRibbonPanel::GetPressed](#getpressed)||  
|[CMFCRibbonPanel::GetRect](#getrect)||  
|[CMFCRibbonPanel::GetVisibleElements](#getvisibleelements)|표시 된 요소의 배열을 가져옵니다.|  
|[CMFCRibbonPanel::HasElement](#haselement)||  
|[CMFCRibbonPanel::HitTest](#hittest)||  
|[CMFCRibbonPanel::HitTestEx](#hittestex)||  
|[CMFCRibbonPanel::Insert](#insert)|지정된 된 위치에는 리본 요소를 삽입합니다.|  
|[CMFCRibbonPanel::InsertSeparator](#insertseparator)|지정된 된 위치에는 구분 기호를 삽입합니다.|  
|[CMFCRibbonPanel::IsCenterColumnVert](#iscentercolumnvert)|열에 있는지 여부를 패널의 모든 요소에 맞춰야 (정렬)을 세로로 지정 합니다.|  
|[CMFCRibbonPanel::IsCollapsed](#iscollapsed)||  
|[CMFCRibbonPanel::IsHighlighted](#ishighlighted)||  
|[CMFCRibbonPanel::IsJustifyColumns](#isjustifycolumns)|패널의 모든 열 너비를 같게 만들기 하는지 여부를 지정 합니다.|  
|[CMFCRibbonPanel::IsMainPanel](#ismainpanel)||  
|[CMFCRibbonPanel::IsMenuMode](#ismenumode)||  
|[CMFCRibbonPanel::MakeGalleryItemVisible](#makegalleryitemvisible)|지정된 된 리본 요소를 표시 하려면 갤러리를 스크롤합니다.|  
|[CMFCRibbonPanel::OnKey](#onkey)||  
|[CMFCRibbonPanel::RecalcWidths](#recalcwidths)||  
|[CMFCRibbonPanel::Remove](#remove)|제거 하 고 필요에 따라 지정된 된 인덱스에 있는 요소를 삭제 합니다.|  
|[CMFCRibbonPanel::RemoveAll](#removeall)|리본 패널에서 모든 요소를 제거합니다.|  
|[CMFCRibbonPanel::Replace](#replace)|각 인덱스 값에 따라 다른 하나의 요소를 바꿉니다.|  
|[CMFCRibbonPanel::ReplaceByID](#replacebyid)|한 요소를 다른 지정 된 명령 ID를 기반으로 바꿉니다.|  
|[CMFCRibbonPanel::SetCenterColumnVert](#setcentercolumnvert)|패널에 요소를 세로로 정렬, 열으로 정렬 합니다.|  
|[CMFCRibbonPanel::SetData](#setdata)|리본 패널을 사용 하 여 사용자 정의 데이터 연결 합니다.|  
|[CMFCRibbonPanel::SetElementMenu](#setelementmenu)|팝업 메뉴는 지정한 명령 ID를 가진 요소에 할당|  
|[CMFCRibbonPanel::SetElementRTC](#setelementrtc)|리본 패널에 제공 된 런타임 클래스 정보로 지정 된 리본 요소를 추가 합니다.|  
|[CMFCRibbonPanel::SetElementRTCByID](#setelementrtcbyid)|리본 패널에 제공 된 런타임 클래스 정보로 지정 된 리본 요소를 추가 합니다.|  
|[CMFCRibbonPanel::SetFocused](#setfocused)|지정된 된 리본 요소에 포커스를 설정 합니다.|  
|[CMFCRibbonPanel::SetJustifyColumns](#setjustifycolumns)|열의 맞춤을 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[CMFCRibbonPanel::SetKeys](#setkeys)|리본 패널을 표시 하는 바로 가기 키를 설정 합니다.|  
|[CMFCRibbonPanel::ShowPopup](#showpopup)||  
  
## <a name="remarks"></a>주의  
 리본 패널은 리본 범주 내에서 만든 관련된 작업의 논리적 그룹화입니다. 리본 변경의 크기로 패널 레이아웃 하도록 자동으로 조정 가능한 많은 요소를 표시 합니다.  
  
 리본 메뉴를 호출 하 여 리본 범주에 포함 된 패널을 얻을 수는 [CMFCRibbonCategory::GetPanel](../../mfc/reference/cmfcribboncategory-class.md#getpanel) 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 구성 방법을 보여 줍니다.는 `CMFCRibbonPanel` 의 다양 한 메서드를 사용 하 여 개체의 `CMFCRibbonPanel` 클래스입니다. 리본 패널을 표시 하는 바로 가기 키를 설정 하 고 패널에 요소를 세로로 정렬 열로 열 양쪽 맞춤을 사용 하도록 설정 하는 방법을 보여 줍니다. 이 코드 조각은의 일부인는 [MS Office 2007 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo #&10;](../../mfc/reference/codesnippet/cpp/cmfcribbonpanel-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxRibbonPanel.h  
  
##  <a name="add"></a>CMFCRibbonPanel::Add  
 리본 패널에 포함 된 리본 요소의 배열에 지정 된 리본 요소를 추가 합니다.  
  
```  
virtual void Add(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>매개 변수  
 [in, out] `pElem`  
 리본 요소에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="addseparator"></a>CMFCRibbonPanel::AddSeparator  
 리본 패널에 구분 기호를 추가 합니다.  
  
```  
virtual void AddSeparator();
```  
  
### <a name="remarks"></a>주의  
 리본 패널에는 구분 기호를 추가 하려면이 메서드를 호출 합니다. 이전 호출에 의해 추가 된 리본 요소 옆에 있는 구분 기호를 추가할 [CMFCRibbonPanel::Add](#add)합니다. 지정된 된 위치에는 구분 기호를 삽입 하려면 호출 [CMFCRibbonPanel::InsertSeparator](#insertseparator)합니다.  
  
##  <a name="addtoolbar"></a>CMFCRibbonPanel::AddToolBar  
 도구 모음 리본 패널에 추가합니다.  
  
```  
CMFCRibbonButtonsGroup* AddToolBar(
UINT uiToolbarResID,  
UINT uiColdResID = 0,  
UINT uiHotResID = 0,  
UINT uiDisabledResID = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiToolbarResID`  
 추가할 도구 모음의 리소스 ID를 지정 합니다.  
  
 [in] `uiColdResID`  
 도구 모음의 콜드 이미지의 리소스 ID를 지정합니다.  
  
 [in] `uiHotResID`  
 도구 모음의 핫 이미지의 리소스 ID를 지정합니다.  
  
 [in] `uiDisabledResID`  
 도구 모음의 비활성화 된 이미지의 리소스 ID를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 도구 모음 리본 패널에 추가 하려면이 메서드를 호출 합니다. 이전 호출에 의해 추가 되는 리본 요소 옆에 있는 도구 모음을 추가할 [CMFCRibbonPanel::Add](#add)합니다.  
  
### <a name="remarks"></a>주의  
 도구 모음, 핫 이미지, 콜드 이미지 및 비활성화 된 이미지에 대 한 자세한 내용은 참조 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)합니다.  
  
##  <a name="cmfcribbonpanel"></a>CMFCRibbonPanel::CMFCRibbonPanel  
 생성 하 고 초기화는 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md) 개체입니다.  
  
```  
CMFCRibbonPanel(
LPCTSTR lpszName = NULL,  
HICON hIcon = NULL);  
  
CMFCRibbonPanel(CMFCRibbonGallery* pPaletteButton);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszName`  
 리본 패널의 이름입니다.  
  
 [in] `hIcon`  
 리본 패널에 대 한 기본 단추 아이콘에 대 한 핸들입니다.  
  
 [in] `pPaletteButton`  
 리본 패널에 대 한 리본 갤러리에 대 한 포인터입니다.  
  
##  <a name="findbydata"></a>CMFCRibbonPanel::FindByData  
 지정된 된 데이터와 관련이 있는 리본 요소를 검색 합니다.  
  
```  
CMFCRibbonBaseElement* FindByData(DWORD_PTR dwData) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwData`  
 리본 요소에 연결 된 데이터입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 리본 요소에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="findbyid"></a>CMFCRibbonPanel::FindByID  
 지정한 명령 ID로 식별 되는 리본 요소를 검색 합니다.  
  
```  
CMFCRibbonBaseElement* FindByID(UINT uiCmdID) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmdID`  
 리본 요소의 명령 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 지정한 명령 ID;로 식별 되는 리본 요소 그렇지 않으면 `NULL` 리본 요소가 지정 된 명령 id입니다.로 식별 되 면  
  
##  <a name="getcaptionheight"></a>CMFCRibbonPanel::GetCaptionHeight  
 리본 패널에 대 한 캡션 높이 검색합니다.  
  
```  
int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리본 패널에 대 한 캡션 픽셀 높이입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getcount"></a>CMFCRibbonPanel::GetCount  
 리본 패널에 포함 된 리본 요소 수를 검색 합니다.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리본 패널에 포함 된 리본 요소의 수입니다.  
  
##  <a name="getdata"></a>CMFCRibbonPanel::GetData  
 패널에 연결 된 사용자 정의 데이터를 반환 합니다.  
  
```  
DWORD_PTR GetData() const;  
```  
  
### <a name="return-value"></a>반환 값  
 패널에 연결 된 사용자 정의 데이터입니다.  
  
##  <a name="getdefaultbutton"></a>CMFCRibbonPanel::GetDefaultButton  
 리본 패널에 대 한 기본 단추를 검색합니다.  
  
```  
CMFCRibbonButton& GetDefaultButton();
```  
  
### <a name="return-value"></a>반환 값  
 리본 패널에 대 한 기본 단추입니다.  
  
### <a name="remarks"></a>주의  
 리본 패널에는 리본 요소를 표시할 공간이 부족 한 기본 단추가 표시 됩니다.  
  
##  <a name="getdroppeddown"></a>CMFCRibbonPanel::GetDroppedDown  
 의 팝업 메뉴를 삭제할 경우에 리본 요소에 대 한 포인터를 검색 합니다.  
  
```  
CMFCRibbonBaseElement* GetDroppedDown() const;  
```  
  
### <a name="return-value"></a>반환 값  
 내려가면;의 팝업 메뉴에 있는 리본 요소에 대 한 포인터 그렇지 않으면 `NULL` 리본 요소 내려가면 팝업 메뉴에 없으면 합니다.  
  
### <a name="remarks"></a>주의  
 리본 패널에 포함 된 리본 요소만 테스트 됩니다.  
  
##  <a name="getelement"></a>CMFCRibbonPanel::GetElement  
 지정된 된 인덱스에 있는 리본 요소를 반환 합니다.  
  
```  
CMFCRibbonBaseElement* GetElement(int nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 검색할 요소의&0;부터 시작 인덱스를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 기본 리본 요소에 대 한 유효한 포인터 위치에 있는 `nIndex` 리본 패널에서 또는 `NULL` 지정된 된 인덱스에 요소가 없는 경우.  
  
##  <a name="getelements"></a>CMFCRibbonPanel::GetElements  
 리본 패널에 포함 된 모든 리본 요소를 검색 합니다.  
  
```  
void GetElements(CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `arElements`  
 리본 패널에 포함 된 모든 리본 요소를 채울 배열입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getelementsbyid"></a>CMFCRibbonPanel::GetElementsByID  
 지정된 된 명령 ID를 지정 된 배열에 있는 리본 요소를 추가 합니다.  
  
```  
void GetElementsByID(
UINT uiCmdID,  
CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmdID`  
 리본 요소에 대 한 명령 ID입니다.  
  
 [in] `arElements`  
 리본 요소의 배열입니다.  
  
### <a name="remarks"></a>주의  
 리본 패널에 포함 된 리본 요소만 테스트 됩니다.  
  
##  <a name="gethighlighted"></a>CMFCRibbonPanel::GetHighlighted  
 리본 패널에 강조 표시 되어 있는 리본 요소를 검색 합니다.  
  
```  
CMFCRibbonBaseElement* GetHighlighted() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리본 패널에 강조 표시 되어 있는 리본 요소에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getindex"></a>CMFCRibbonPanel::GetIndex  
 리본 패널에 포함 된 리본 요소 배열에서 지정 된 리본 요소의&0;부터 시작 인덱스를 검색 합니다.  
  
```  
virtual int GetIndex(CMFCRibbonBaseElement* pElem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pElem`  
 리본 요소에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 지정 된 리본 요소의&0;부터 시작 인덱스 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getitemidslist"></a>CMFCRibbonPanel::GetItemIDsList  
 리본 패널의 모든 리본 요소에 대 한 명령 Id를 검색합니다.  
  
```  
void GetItemIDsList(CList<UINT, UINT>& lstItems) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `lstItems`  
 목록에는 리본 패널이 포함 되어 있는 리본 요소에 대 한 명령 Id입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getname"></a>CMFCRibbonPanel::GetName  
 리본 패널의 이름을 검색합니다.  
  
```  
LPCTSTR GetName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리본 패널의 이름입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getparentbutton"></a>CMFCRibbonPanel::GetParentButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonBaseElement* GetParentButton() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getparentcategory"></a>CMFCRibbonPanel::GetParentCategory  
 리본 패널의 부모 범주를 반환합니다.  
  
```  
CMFCRibbonCategory* GetParentCategory() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 리본 패널을 포함 하는 리본 범주에 대 한 포인터입니다.  
  
##  <a name="getparentmenubar"></a>CMFCRibbonPanel::GetParentMenuBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonPanelMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getpreferedmenulocation"></a>CMFCRibbonPanel::GetPreferedMenuLocation  
 리본 패널의 팝업 메뉴에 대 한 기본 표시 사각형을 검색합니다.  
  
```  
virtual BOOL GetPreferedMenuLocation(CRect& rect);
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `rect`  
 이 매개 변수는 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 항상 `FALSE`를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 항상 `FALSE`을 반환합니다. 리본 패널의 팝업 메뉴에 대 한 기본 표시 사각형을 검색 하려면이 메서드를 재정의 합니다.  
  
##  <a name="getpressed"></a>CMFCRibbonPanel::GetPressed  
 사용자가 현재 누를 경우에 리본 패널에는 리본 요소에 대 한 포인터를 검색 합니다.  
  
```  
CMFCRibbonBaseElement* GetPressed() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재를 누르는 경우, 리본 요소에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getrect"></a>CMFCRibbonPanel::GetRect  
 리본 패널에 대 한 표시 영역을 검색 합니다.  
  
```  
const CRect& GetRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리본 패널에 대 한 표시 사각형을 지정 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="haselement"></a>CMFCRibbonPanel::HasElement  
 지정 된 리본 요소 리본 패널에 포함 되는지 여부를 나타냅니다.  
  
```  
BOOL HasElement(const CMFCRibbonBaseElement* pElem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pElem`  
 리본 요소에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`리본 패널 지정 된 리본 요소를 포함 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="highlight"></a>CMFCRibbonPanel::Highlight  
 지점에서 지정 된 리본 요소에 대 한 선택 된 리본 패널에 강조 표시 색을 설정 합니다.  
  
```  
virtual void Highlight(
BOOL bHighlight,  
CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bHighlight`  
 `TRUE`리본 패널에 강조 표시 `FALSE` unhighlight 리본 패널에 있습니다.  
  
 [in] `point`  
 창의 왼쪽 위 모퉁이 기준으로 포인터의 x 및 y 좌표입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="hittest"></a>CMFCRibbonPanel::HitTest  
 지정 된 위치에 있으면 리본 요소를 검색 합니다.  
  
```  
virtual CMFCRibbonBaseElement* HitTest(
CPoint point,  
BOOL bCheckPanelCaption = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 창의 왼쪽 위 모퉁이 기준으로 포인터의 x 및 y 좌표입니다.  
  
 [in] `bCheckPanelCaption`  
 `TRUE`리본 패널 캡션;를 테스트 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 위치에 있으면, 리본 요소에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 리본 패널에 포함 된 리본 요소만 테스트 됩니다.  
  
##  <a name="hittestex"></a>CMFCRibbonPanel::HitTestEx  
 지정된 된 지점 그 안에 있는 리본 요소의&0;부터 시작 인덱스를 검색 합니다.  
  
```  
virtual int HitTestEx(CPoint point) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 창의 왼쪽 위 모퉁이 기준으로 포인터의 x 및 y 좌표입니다.  
  
### <a name="return-value"></a>반환 값  
 에 있는 지정된 된 점이 있는 리본 요소 인덱스 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>주의  
 리본 패널에 포함 된 리본 요소만 테스트 됩니다.  
  
##  <a name="insert"></a>CMFCRibbonPanel::Insert  
 지정된 된 위치에 배열에 있는 리본 요소에 리본 패널이 포함 되어 있는 지정 된 리본 요소를 삽입 합니다.  
  
```  
virtual BOOL Insert(
CMFCRibbonBaseElement* pElem,  
int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 [in, out] `pElem`  
 리본 요소에 대 한 포인터입니다.  
  
 [in] `nIndex`  
 배열에 포함 된 리본 요소 수까지-1에서&0;부터 시작 값입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`리본 요소를 성공적으로 삽입 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 경우의 값 `nIndex` -1 인 경우 `nIndex` 리본 배열의 요소 수와 같으면, 지정 된 리본 요소가 배열의 끝에 추가 됩니다. 하는 경우의 값 `nIndex` 는 범위를 벗어났거나 메서드가 실패 합니다.  
  
##  <a name="insertseparator"></a>CMFCRibbonPanel::InsertSeparator  
 지정된 된 위치에는 구분 기호를 삽입합니다.  
  
```  
virtual BOOL InsertSeparator(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 인덱스는 구분 기호를 삽입 하는 위치를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`구분 기호를 성공적으로 삽입 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 로 지정 된 위치에는 구분 기호를 삽입 하려면이 메서드를 호출 `nIndex`합니다. 가장 최근에 추가 된 리본 요소 옆에 있는 구분 기호를 삽입 하려면 호출 [CMFCRibbonPanel::AddSeparator](#addseparator)합니다.  
  
##  <a name="iscentercolumnvert"></a>CMFCRibbonPanel::IsCenterColumnVert  
 리본 요소의 세로 위치는 해당 표시 영역 내에서 가운데 정렬 여부를 나타냅니다.  
  
```  
BOOL IsCenterColumnVert() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`리본 요소의 표시 사각형;에서 가운데 맞춤 됩니다의 세로 위치 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="iscollapsed"></a>CMFCRibbonPanel::IsCollapsed  
 리본 패널의 표시 크기를 가로 방향으로 최소화 되었는지 여부를 나타냅니다.  
  
```  
BOOL IsCollapsed() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`가로 방향의 리본 패널의 표시 크기를 최소화 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 리본 패널을 축소 하는 경우만 해당 기본 단추, 해당 이름 및 드롭다운 화살표를 표시 합니다.  
  
##  <a name="ishighlighted"></a>CMFCRibbonPanel::IsHighlighted  
 리본 패널의 표시 강조 표시 되어 있는지 여부를 나타냅니다.  
  
```  
BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`리본 패널의 표시는 강조 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 리본 패널의 표시에 포인터 위로 가져갈 때 강조 표시 됩니다.  
  
##  <a name="isjustifycolumns"></a>CMFCRibbonPanel::IsJustifyColumns  
 리본 패널에 같은 열에 있는 리본 요소 디스플레이 크기 같은 너비로 설정 되었는지 여부를 나타냅니다.  
  
```  
BOOL IsJustifyColumns() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`리본 패널에 같은 열에 있는 리본 요소 디스플레이 크기; 동일한 너비로 설정 된 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="ismainpanel"></a>CMFCRibbonPanel::IsMainPanel  
 리본 패널 주 리본 패널 인지를 나타냅니다.  
  
```  
virtual BOOL IsMainPanel() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항상 `FALSE`를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 항상 `FALSE`을 반환합니다. 리본 패널 주 리본 패널 인지 지정 하려면이 메서드를 재정의 합니다.  
  
 사용자가 응용 프로그램 단추를 선택 하는 경우 주 리본 패널이 표시 됩니다.  
  
##  <a name="ismenumode"></a>CMFCRibbonPanel::IsMenuMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsMenuMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="onkey"></a>CMFCRibbonPanel::OnKey  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nChar`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="recalcwidths"></a>CMFCRibbonPanel::RecalcWidths  
 각 리본 패널에 대 한 레이아웃 구성 표시의 너비를 다시 계산합니다.  
  
```  
virtual void RecalcWidths(
CDC* pDC,  
int nHeight);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 리본 패널에 대 한 장치 컨텍스트에 대 한 포인터입니다.  
  
 [in] `nHeight`  
 리본 패널의 높이입니다.  
  
### <a name="remarks"></a>주의  
 리본 패널 사용 가능한 너비 변경 되 면 해당 레이아웃 구성을 변경합니다.  
  
##  <a name="remove"></a>CMFCRibbonPanel::Remove  
 제거 하 고 필요에 따라 지정된 된 인덱스에 있는 요소를 삭제 합니다.  
  
```  
BOOL Remove(
int nIndex,  
BOOL bDelete = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 리본 패널에서 제거 된 요소의&0;부터 시작 하는 인덱스를 지정 합니다.  
  
 [in] `bDelete`  
 `TRUE`제거 되 고 요소를 삭제 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`요소를 제거 하 고 삭제 된 경우 (경우 `bDelete` 는 `TRUE`); `FALSE` 경우 요소가 제거 되지 않은 또는 리본 요소에 있는 경우 `nIndex`합니다.  
  
### <a name="remarks"></a>주의  
 리본 패널에서 요소를 제거 하려면이 메서드를 호출 합니다.  
  
##  <a name="removeall"></a>CMFCRibbonPanel::RemoveAll  
 리본 패널에서 모든 리본 요소를 삭제합니다.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>주의  
 모든 리본 요소를 리본 패널에서 삭제 되 고 삭제 합니다.  
  
##  <a name="replace"></a>CMFCRibbonPanel::Replace  
 해당 인덱스 값에 따라 다른 하나의 요소를 바꿉니다.  
  
```  
BOOL Replace(
int nIndex,  
CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 바꿀 요소의 인덱스를 지정 합니다.  
  
 [in] [out]`pElem`  
 원래 요소로 대체 하는 요소에 대 한 유효한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`원래 리본 요소; 새 리본 요소에 의해 성공적으로 교체 된 경우 `FALSE` 리본 요소를 교체 하지 않았습니다 또는 지정된 된 인덱스에 요소가 없는 경우.  
  
### <a name="remarks"></a>주의  
 리본 요소를 명령 ID로 바꾸려면 호출 [CMFCRibbonPanel::ReplaceByID](#replacebyid)합니다.  
  
##  <a name="replacebyid"></a>CMFCRibbonPanel::ReplaceByID  
 한 요소를 다른 지정 된 명령 ID를 기반으로 바꿉니다.  
  
```  
BOOL ReplaceByID(
UINT uiCmdID,  
CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmdID`  
 바꿀 요소의 명령 ID를 지정 합니다.  
  
 [in] [out]`pElem`  
 유효한 포인터는 원래 요소를 대체 하는 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`원래 리본 요소; 새 리본 요소에 의해 성공적으로 교체 된 경우 `FALSE` 리본 요소를 교체 하지 않았습니다 또는 지정된 된 명령 ID 가진 요소가 실제로 존재 하는 경우.  
  
### <a name="remarks"></a>주의  
 위치에 따라 리본 요소를 바꾸려면 호출 [CMFCRibbonPanel::Replace](#replace)합니다.  
  
##  <a name="setcentercolumnvert"></a>CMFCRibbonPanel::SetCenterColumnVert  
 표시 사각형 내에 리본 요소의 세로 위치를 가운데 맞춤을 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
void SetCenterColumnVert(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bSet`  
 `TRUE`리본 메뉴의 표시 사각형; 요소로,의 세로 위치를 가운데 맞춤 하려면 `FALSE` 이 기능을 해제할 수 있습니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="setdata"></a>CMFCRibbonPanel::SetData  
 리본 패널을 사용 하 여 사용자 정의 데이터 연결 합니다.  
  
```  
void SetData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwData`  
 사용자 정의 설정할 데이터를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 리본 패널와 사용자 정의 데이터를 연결 하려면이 메서드를 호출 합니다.  
  
##  <a name="setelementmenu"></a>CMFCRibbonPanel::SetElementMenu  
 팝업 메뉴는 지정한 명령 ID를 가진 요소에 할당  
  
```  
BOOL SetElementMenu(
UINT uiCmdID,  
HMENU hMenu,  
BOOL bIsDefautCommand = FALSE,  
BOOL bRightAlign = FALSE);

 
BOOL SetElementMenu(
UINT uiCmdID,  
UINT uiMenuResID,  
BOOL bIsDefautCommand = FALSE,  
BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmdID`  
 명령 메뉴를 추가 하는 위치는 리본 요소 ID를 지정 합니다.  
  
 [in] `hMenu`  
 리본 패널에 추가 하기 위해 Windows 메뉴에 대 한 핸들을 지정 합니다.  
  
 [in] `bIsDefautCommand`  
 `TRUE`리본 요소를 클릭할 경우 리본 요소와 연결 된 명령 실행 않아야 함을 지정 합니다. 이 경우에 메뉴는 리본 요소 옆의 화살표를 클릭할 때 엽니다. `FALSE`리본 요소를 클릭할 경우 리본 요소와 관련 된 명령이 실행 되지 해야를 지정 합니다. 이 경우 요소에는 사용자가 클릭 하는 위치에 관계 없이 팝업 메뉴가 나타납니다.  
  
 [in] `bRightAlign`  
 `TRUE`지정 하는 팝업 메뉴가 오른쪽에 맞춰집니다. 그렇지 않으면 `FALSE`합니다.  
  
 [in] `uiMenuResID`  
 리본 패널에 추가할 메뉴의 리소스 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메뉴는 리본 요소에 할당 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 팝업 메뉴는 지정한 명령 ID를 가진 리본 요소에 할당 하려면이 메서드를 호출 합니다.  
  
##  <a name="setelementrtc"></a>CMFCRibbonPanel::SetElementRTC  
 리본 패널에 제공 된 런타임 클래스 정보로 지정 된 리본 요소를 추가 합니다.  
  
```  
CMFCRibbonBaseElement* SetElementRTC(
int nIndex,  
CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 리본 요소를 추가 하려면의&0;부터 시작 하는 인덱스를 지정 합니다.  
  
 [in] [out]`pRTC`  
 리본 패널에 추가 하는 리본 요소에 대 한 런타임 클래스 정보에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 런타임 클래스 정보를 사용 하 여 생성 된 리본 요소입니다.  
  
### <a name="remarks"></a>주의  
 리본 패널에는 사용자 지정 요소 (예를 들어, 색상 단추)를 추가 하려는 경우에 사용자 지정 요소의 런타임 클래스 정보를 지정 해야 합니다. 리본이이 정보를 저장 및 사용자 지정 요소를 만듭니다 (으로 식별 됨)은 기존 요소를 대체 합니다. 지정 된 명령 id입니다. 다음 리본 메뉴는 새로 만든된 요소에 대 한 포인터를 반환합니다.  
  
##  <a name="setelementrtcbyid"></a>CMFCRibbonPanel::SetElementRTCByID  
 리본 패널에 제공 된 런타임 클래스 정보로 지정 된 리본 요소를 추가 합니다.  
  
```  
CMFCRibbonBaseElement* SetElementRTCByID(
UINT uiCmdID,  
CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmdID`  
 리본 요소를 추가 하려면 명령 ID를 지정 합니다.  
  
 [in] [out]`pRTC`  
 리본 패널에 추가 하는 리본 요소와 관련 된 런타임 클래스 정보에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 런타임 클래스 정보를 사용 하 여 생성 된 리본 요소입니다.  
  
### <a name="remarks"></a>주의  
 리본 패널에는 사용자 지정 요소 (예를 들어, 색상 단추)를 추가 하려는 경우에 사용자 지정 요소의 런타임 클래스 정보를 지정 해야 합니다. 리본이이 정보를 저장, 사용자 지정 요소를 만듭니다 및 지정 된 명령 ID가 있는 기존 요소를 대체 합니다. 그런 다음 새로 만든된 요소에 대 한 포인터를 반환합니다.  
  
### <a name="example"></a>예제  
 다음 예제를 사용 하는 방법을 보여 줍니다는 `SetElementRTCByID` 메서드:  
  
```  
 
// Load and add toolbar with standard buttons. This toolbar  
// should display a custom color button with id ID_CHAR_COLOR:  
 
pPanel->AddToolBar(IDR_MAINFRAME,
    IDB_MAINFRAME256);

CMFCRibbonColorButton* pColorButton = 
(CMFCRibbonColorButton*)pPanel->SetElementRTCByID(
ID_CHAR_COLOR,
    RUNTIME_CLASS (CMFCRibbonColorButton));

 
// SetElementRTCByID sets runtime class and returns a pointer  
// to the newly created custom button,
    which can be set up immediately:  
pColorButton->EnableAutomaticButton(_T("Automatic"),
    RGB (0,
    0,
    0));  
```  
  
##  <a name="setjustifycolumns"></a>CMFCRibbonPanel::SetJustifyColumns  
 사용 하거나 리본 요소에 동일한 열 너비를 조정 하면 사용 하지 않도록 설정 합니다.  
  
```  
void SetJustifyColumns(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bSet`  
 `TRUE`리본 요소에 열을 가장 큰 리본 요소의 너비에 동일한 열 너비를 조정 하려면 `FALSE` 이 너비 조정을 해제 하려면.  
  
### <a name="remarks"></a>주의  
 를 리본 패널에서이 기능을 사용할 때 리본 요소에 동일한 열 너비의 같은 열에 가장 큰 리본 요소 너비를 조정 됩니다.  
  
##  <a name="setkeys"></a>CMFCRibbonPanel::SetKeys  
 리본 패널의 기본 단추에 대 한 keytip를 설정합니다.  
  
```  
void SetKeys(LPCTSTR lpszKeys);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszKeys`  
 리본 패널의 기본 단추에 대 한 keytip 합니다.  
  
### <a name="remarks"></a>주의  
 리본 패널에는 리본 요소를 표시할 공간이 부족 한 기본 단추가 표시 됩니다.  
  
##  <a name="showpopup"></a>CMFCRibbonPanel::ShowPopup  
 만들고 리본 패널에 대 한 팝업 메뉴를 표시 합니다.  
  
```  
CMFCRibbonPanelMenu* ShowPopup(CMFCRibbonDefaultPanelButton* pButton = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pButton`  
 리본 패널에 대 한 기본 단추에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 리본 패널에 대 한 팝업 메뉴에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 리본 패널에 대 한 팝업 메뉴는 리본 패널의 표시 축소 되는 경우에 사용할 수 있습니다.  
  
##  <a name="setfocused"></a>CMFCRibbonPanel::SetFocused  
 지정된 된 리본 요소에 포커스를 설정 합니다.  
  
```  
void SetFocused(CMFCRibbonBaseElement* pNewFocus);
```  
  
### <a name="parameters"></a>매개 변수  
 `pNewFocus`  
 포커스를 받을 수 있는 리본 요소에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="makegalleryitemvisible"></a>CMFCRibbonPanel::MakeGalleryItemVisible  
 지정된 된 리본 요소를 표시 하려면 갤러리를 스크롤합니다.  
  
```  
void MakeGalleryItemVisible(CMFCRibbonBaseElement* pItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 표시할 리본 요소에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="iswindows7look"></a>CMFCRibbonPanel::IsWindows7Look  
 부모 리본 (작은 사각형 응용 프로그램 단추)를 확인 하는 Windows 7에 있는지 여부를 나타냅니다.  
  
```  
BOOL IsWindows7Look() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`부모 리본에 Windows 7을 표시 합니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getvisibleelements"></a>CMFCRibbonPanel::GetVisibleElements  
 표시 된 요소의 배열을 검색합니다.  
  
```  
void GetVisibleElements(
CArray<CMFCRibbonBaseElement*,  
CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>매개 변수  
 `arElements`  
 함수가 반환 될 때이 매개 변수는 표시 된 요소의 배열이 포함 됩니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getgalleryrect"></a>CMFCRibbonPanel::GetGalleryRect  
 갤러리 요소의 경계 사각형을 반환합니다.  
  
```  
CRect GetGalleryRect();
```  
  
### <a name="return-value"></a>반환 값  
 크기와이 패널에 있는 갤러리 요소의 위치입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getfocused"></a>CMFCRibbonPanel::GetFocused  
 포커스가 지정된 요소를 반환합니다.  
  
```  
CMFCRibbonBaseElement* GetFocused() const;  
```  
  
### <a name="return-value"></a>반환 값  
 포커스가 있는 요소에 대 한 포인터 또는 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [CMFCRibbonCategory 클래스](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonBaseElement 클래스](../../mfc/reference/cmfcribbonbaseelement-class.md)

