---
title: "CMFCOutlookBarTabCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::AddControl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::Create
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableInPlaceEdit
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableScrollButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetVisiblePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsMode2003
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowOptions
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetActiveTab
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetToolbarImageList
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetVisiblePageButtons
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBarTabCtrl class
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
caps.latest.revision: 26
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
ms.openlocfilehash: 16de4287a2b3a6352fb4fc560b9c8eec2ba766d1
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Class
Microsoft Outlook의 **탐색 창** 과 시각적으로 유사한 탭 컨트롤입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|기본 생성자입니다.|  
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCOutlookBarTabCtrl::AddControl](#addcontrol)|Outlook 표시줄에서 새 탭으로 Windows 컨트롤을 추가합니다.|  
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|프레임 워크에서 호출의 사용자가 표시 되는 편집 상자 크기를 결정 하려면 이름을 바꿉니다 탭을. (`CMFCBaseTabCtrl::CalcRectEdit`를 재정의합니다.)|  
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](#canshowfewerpagebuttons)|크기 조정 작업은 현재 보이는 것 보다 더 적은 Outlook 표시줄 탭 페이지 단추를 표시할 수 있으면 확인 하는 동안 프레임 워크에 의해 호출 됩니다.|  
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](#canshowmorepagebuttons)|현재 표시 되어 있는 것 보다 더 많은 Outlook 표시줄 탭 페이지 단추 표시 될 수 있는지 확인 하려면 크기 조정 작업 동안 프레임 워크에서 호출 합니다.|  
|[CMFCOutlookBarTabCtrl::Create](#create)|Outlook 표시줄 탭 컨트롤을 만듭니다.|  
|`CMFCOutlookBarTabCtrl::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|[CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)|활성 탭 간에 전환 하는 동안 발생 하는 애니메이션 사용 되는지 여부를 지정 합니다.|  
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|사용자가 Outlook 표시줄의 탭 단추에 텍스트 레이블을 수정할 수 있는지 여부를 지정 합니다. (재정의 [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|  
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](#enablescrollbuttons)|사용자가 Outlook 표시줄 창에 단추를 통해 스크롤할 수 있는 단추를 사용 하도록 설정 하는 프레임 워크에서 호출 됩니다.|  
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|지정된 된 지점에 포함 된 창을 식별 합니다. (재정의 [CMFCBaseTabCtrl::FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd).)|  
|[CMFCOutlookBarTabCtrl::GetBorderSize](#getbordersize)|Outlook 탭 컨트롤의 테두리 크기를 반환합니다.|  
|`CMFCOutlookBarTabCtrl::GetTabArea`|탭 컨트롤의 탭 영역의 위치와 크기를 검색합니다. (재정의 [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|  
|`CMFCOutlookBarTabCtrl::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식으로 연결 된 개체입니다.|  
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](#getvisiblepagebuttons)||  
|[CMFCOutlookBarTabCtrl::IsAnimation](#isanimation)|활성 탭 간에 전환 하는 동안 발생 하는 애니메이션 사용 되는지 여부를 결정 합니다.|  
|[CMFCOutlookBarTabCtrl::IsMode2003](#ismode2003)|Microsoft Outlook 2003을 에뮬레이션 하는 모드에서 Outlook 표시줄 탭 컨트롤 인지 여부를 확인 합니다.|  
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|영역 내부에 탭 지점을 인지 여부를 확인 합니다. (재정의 [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|  
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|분리 가능한 탭 인지 확인 합니다. (재정의 [CMFCBaseTabCtrl::IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable).)|  
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|프레임 워크 탭은 삽입 되거나 제거 될 때 호출 됩니다. (`CMFCBaseTabCtrl::OnChangeTabs`를 재정의합니다.)|  
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](#onshowfewerpagebuttons)|표시 되는 탭 페이지 단추 수를 줄이려면 프레임 워크에 의해 호출 됩니다.|  
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](#onshowmorepagebuttons)|표시 되는 탭 페이지 단추 수를 늘리려면 프레임 워크에 의해 호출 됩니다.|  
|[CMFCOutlookBarTabCtrl::OnShowOptions](#onshowoptions)|표시는 **탐색 창 옵션** 대화 합니다.|  
|`CMFCOutlookBarTabCtrl::RecalcLayout`|탭 컨트롤의 내부 레이아웃이 다시 계산 됩니다. (재정의 [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|  
|[CMFCOutlookBarTabCtrl::SetActiveTab](#setactivetab)|활성 탭을 설정합니다. (재정의 [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|  
|[CMFCOutlookBarTabCtrl::SetBorderSize](#setbordersize)|Outlook 탭 컨트롤의 테두리 크기를 설정합니다.|  
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](#setpagebuttontextalign)|Outlook 표시줄의 탭 단추에 텍스트 레이블의 맞춤을 설정 합니다.|  
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](#settoolbarimagelist)|Outlook 2003 모드에서 Outlook 표시줄의 아래쪽에 표시 되는 아이콘이 포함 된 비트맵을 설정 (참조 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)).|  
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](#setvisiblepagebuttons)||  
  
## <a name="remarks"></a>주의  
 도킹 지원을 제공 하는 Outlook 표시줄을 만들려면 사용을 `CMFCOutlookBar` Outlook 표시줄 탭 컨트롤을 호스트 하는 개체입니다. 자세한 내용은 참조 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 초기화 하는 방법을 한 `CMFCOutlookBarTabCtrl` 개체의 다양 한 메서드를 사용 하는 `CMFCOutlookBarTabCtrl` 클래스입니다. Outlook 표시줄의 탭 페이지 단추 텍스트 레이블을의 내부 편집 사용, 애니메이션을 사용 하도록 설정, 사용자가 Outlook 표시줄 창에 단추, Outlook 탭 컨트롤의 테두리 크기를 설정 스크롤하고 Outlook 표시줄의 탭 단추에 텍스트 레이블의 맞춤을 설정할 수 있도록 스크롤 핸들을 사용 하도록 설정 하는 방법을 보여 줍니다. 이 코드 조각은의 일부인는 [Outlook 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_OutlookDemo #&1;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]  
[!code-cpp[NVC_MFC_OutlookDemo #&2;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxoutlookbartabctrl.h  
  
##  <a name="addcontrol"></a>CMFCOutlookBarTabCtrl::AddControl  
 Outlook 표시줄에서 새 탭으로 Windows 컨트롤을 추가합니다.  
  
```  
void AddControl(
    CWnd* pWndCtrl,  
    LPCTSTR lpszName,  
    int nImageID=-1,  
    BOOL bDetachable=TRUE,  
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndCtrl`  
 추가할 컨트롤에 대 한 포인터입니다.  
  
 [in] `lpszName`  
 탭의 이름을 지정합니다.  
  
 [in] `bDetachable`  
 경우 `TRUE`, 페이지와 분리 가능한 생성 됩니다.  
  
 [in] `nImageID`  
 새 탭에 표시할 이미지에 대 한 내부 이미지 목록의 이미지 인덱스입니다.  
  
 [in] `dwControlBarStyle`  
 지정 된 AFX_ `CBRS_`* 래핑된 도킹 창에 대 한 스타일입니다.  
  
### <a name="remarks"></a>주의  
 Outlook 표시줄의 새 페이지로 컨트롤을 추가 하려면이 함수를 사용 합니다.  
  
 이 함수에서 내부적으로 호출 [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)합니다.  
  
 설정한 경우 `bDetachable` 를 `TRUE`, `AddControl` 내부적으로 만들며는 `CDockablePaneAdapter` 개체를 추가 된 컨트롤을 래핑합니다. 탭된 창의 런타임 클래스의 런타임 클래스를 자동으로 설정 `CMFCOutlookBar` 부동 프레임의 런타임 클래스 및 `CMultiPaneFrameWnd`합니다.  
  
### <a name="example"></a>예제  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `AddControl` 에서 메서드는 `CMFCOutlookBarTabCtrl` 클래스입니다. 이 코드 조각은의 일부인는 [Outlook 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_OutlookDemo #&3;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]  
  
##  <a name="canshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::CanShowFewerPageButtons  
 크기 조정 작업 현재 표시 되어 보다 적은 Outlook 표시줄 탭 페이지 단추를 표시할 수 있는지 여부를 결정 하는 동안 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL CanShowFewerPageButtons() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`둘 이상의 단추가; 없는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 Outlook 표시줄 탭 컨트롤 동적으로 추가 하거나 공간 크기를 사용할 수에 따라 화면에서 탭을 제거 합니다. 이 메서드는 해당 프로세스를 지원 하기 위해 프레임 워크에 의해 사용 됩니다.  
  
##  <a name="canshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::CanShowMorePageButtons  
 크기 조정 작업은 현재 보이는 것 보다 Outlook 표시줄 탭 페이지 단추를 표시할 수 있는지 여부를 결정 하는 동안 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL CanShowMorePageButtons() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`현재 표시 되지 않는 단추가 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 Outlook 표시줄 탭 컨트롤 동적으로 추가 하거나 공간 크기를 사용할 수에 따라 디스플레이에서 탭을 제거 합니다. 이 메서드는 해당 프로세스를 지원 하기 위해 프레임 워크에 의해 사용 됩니다.  
  
##  <a name="create"></a>CMFCOutlookBarTabCtrl::Create  
 Outlook 표시줄 탭 컨트롤을 만듭니다.  
  
```  
virtual BOOL Create(
    const CRect& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 초기 크기와 위치 (픽셀) 지정합니다.  
  
 [in] `pParentWnd`  
 부모 창을 가리킵니다. `NULL`이 아니어야 합니다.  
  
 [in] `nID`  
 컨트롤 id입니다.  
  
### <a name="return-value"></a>반환 값  
 컨트롤 성공적으로 만들어진 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 일반적으로 outlook 표시줄 탭 컨트롤 만들어지는 경우 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md) 컨트롤은 `WM_CREATE` 프로세스의 메시지입니다.  
  
##  <a name="enableanimation"></a>CMFCOutlookBarTabCtrl::EnableAnimation  
 활성 탭 간에 전환 하는 동안 발생 하는 애니메이션 사용 되는지 여부를 지정 합니다.  
  
```  
static void EnableAnimation(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 애니메이션을 활성화 또는 비활성화를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 사용 하도록 설정 하 고 애니메이션을 사용 하지 않도록 설정 하려면이 함수를 호출 합니다. 사용자가 탭 페이지를 열 때 페이지의 캡션 슬라이드 위로 또는 아래로 애니메이션을 사용 하는 경우. 애니메이션을 사용 하지 않으면 페이지 즉시 활성화 됩니다.  
  
 기본적으로 애니메이션을 사용 합니다.  
  
##  <a name="enableinplaceedit"></a>CMFCOutlookBarTabCtrl::EnableInPlaceEdit  
 사용자가 Outlook 표시줄의 탭 페이지 단추 텍스트 레이블을 수정할 수 있는지 여부를 지정 합니다.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>매개 변수  
 `bEnable`  
 경우 `TRUE`, 텍스트 레이블의 내부 편집을 사용 하도록 설정 합니다. 경우 `FALSE`, 내부 편집을 사용 하지 않도록 설정 합니다.  
  
### <a name="remarks"></a>주의  
 내부의 탭 페이지 단추 텍스트 레이블을 편집을 사용 하지 않도록 설정 하거나 사용 하려면이 함수를 호출 합니다. 기본적으로 내부 편집 비활성화 됩니다.  
  
##  <a name="enablescrollbuttons"></a>CMFCOutlookBarTabCtrl::EnableScrollButtons  
 사용자가 Outlook 표시줄 창에 단추를 통해 스크롤할 수 있는 스크롤 핸들을 사용 하도록 설정 하는 프레임 워크에서 호출 됩니다.  
  
```  
void EnableScrollButtons(
    BOOL bEnable = TRUE,  
    BOOL bIsUp = TRUE,  
    BOOL bIsDown = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 스크롤 단추를 표시할지를 결정 합니다.  
  
 [in] `bIsUp`  
 상위 스크롤 막대가 표시 되는지 여부를 결정 합니다.  
  
 [in] `bIsDown`  
 하위 스크롤 막대가 표시 되는지 여부를 결정 합니다.  
  
### <a name="remarks"></a>주의  
 스크롤 단추 표시할 수 있습니다. 이 메서드는 활성 탭 스크롤 단추를 복원 하려면 변경 될 때 프레임 워크에 의해 호출 됩니다.  
  
##  <a name="getbordersize"></a>CMFCOutlookBarTabCtrl::GetBorderSize  
 Outlook 탭 컨트롤의 테두리 크기를 반환합니다.  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 테두리 크기 (픽셀)에서입니다.  
  
##  <a name="getvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::GetVisiblePageButtons  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetVisiblePageButtons() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="isanimation"></a>CMFCOutlookBarTabCtrl::IsAnimation  
 활성 탭 간에 전환 하는 동안 발생 하는 애니메이션 사용 되는지 여부를 지정 합니다.  
  
```  
static BOOL IsAnimation();
```  
  
### <a name="return-value"></a>반환 값  
 애니메이션을 사용 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 호출 된 [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation) 애니메이션 활성화 또는 비활성화 하는 함수입니다.  
  
##  <a name="ismode2003"></a>CMFCOutlookBarTabCtrl::IsMode2003  
 Outlook 표시줄 탭 컨트롤은 Microsoft Outlook 2003을 에뮬레이션 하는 모드에 있는지 여부를 결정 합니다.  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`탭 컨트롤 막대 Outlook Outlook 2003; 모드인 경우 그렇지 않으면 `FALSE`;  
  
### <a name="remarks"></a>주의  
 이 값을 설정한 [CMFCOutlookBar::SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003)합니다.  
  
##  <a name="onshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowFewerPageButtons  
 표시 되는 탭 페이지 단추 수를 줄이려면 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnShowFewerPageButtons();
```  
  
### <a name="remarks"></a>주의  
 이 메서드는 컨트롤의 크기를 조정할 때 표시 되는 페이지 탭 단추 수를 조정 합니다.  
  
##  <a name="onshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowMorePageButtons  
 표시 되는 탭 페이지 단추 수를 늘리려면 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnShowMorePageButtons();
```  
  
### <a name="remarks"></a>주의  
 이 메서드는 컨트롤의 크기를 조정할 때 표시 되는 탭 페이지 단추 수를 조정 합니다.  
  
##  <a name="onshowoptions"></a>CMFCOutlookBarTabCtrl::OnShowOptions  
 표시는 **탐색 창 옵션** 대화 상자입니다.  
  
```  
virtual void OnShowOptions();
```  
  
### <a name="remarks"></a>주의  
 **탐색 창 옵션** 대화 상자를 표시 되는 탭 페이지 단추를 선택 하 고 표시 되는 순서에 있습니다.  
  
 이 메서드는 프레임 워크에서 사용자가 선택 된 **탐색 창 옵션** 컨트롤의 사용자 지정 메뉴에서 메뉴 항목입니다.  
  
##  <a name="setactivetab"></a>CMFCOutlookBarTabCtrl::SetActiveTab  
 활성 탭을 설정합니다. 활성 탭 표시의 내용에 대해 열려 있는입니다.  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iTab`  
 열 탭의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 탭 성공적으로 열린 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 활성 탭 설정의 시각 효과 애니메이션 설정 여부에 따라 달라 집니다. 자세한 내용은 참조 [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)합니다.  
  
##  <a name="setbordersize"></a>CMFCOutlookBarTabCtrl::SetBorderSize  
 Outlook 탭 컨트롤의 테두리 크기를 설정합니다.  
  
```  
void SetBorderSize(int nBorderSize);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nBorderSize`  
 새 테두리 크기를 픽셀 단위로 지정 합니다.  
  
### <a name="remarks"></a>주의  
 새 테두리 크기를 설정 하 고 outlook 창 레이아웃을 다시 계산 됩니다.  
  
##  <a name="setpagebuttontextalign"></a>CMFCOutlookBarTabCtrl::SetPageButtonTextAlign  
 Outlook 표시줄의 탭 단추에 텍스트 레이블의 맞춤을 설정 합니다.  
  
```  
void SetPageButtonTextAlign(
    UINT uiAlign,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiAlign`  
 텍스트 맞춤을 지정합니다.  
  
 [in] `bRedraw`  
 경우 `TRUE`, outlook 창 다시 그려집니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 사용 하 여 페이지 단추에 대 한 텍스트 맞춤을 변경 합니다.  
  
 `uiAlign`다음 값 중 하나일 수 있습니다.  
  
|상수|의미|  
|--------------|-------------|  
|TA_LEFT|왼쪽된 맞춤|  
|TA_CENTER|가운데 맞춤|  
|TA_RIGHT|오른쪽 맞춤|  
  
 기본값은 TA_CENTER 합니다.  
  
##  <a name="settoolbarimagelist"></a>CMFCOutlookBarTabCtrl::SetToolbarImageList  
 Outlook 2003 모드에서 Outlook 표시줄의 아래쪽에 표시 되는 아이콘이 포함 된 비트맵을 설정 합니다.  
  
```  
BOOL SetToolbarImageList(
    UINT uiID,  
    int cx,  
    COLORREF clrTransp=RGB(255, 0, 255));
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiID`  
 로드 하는 이미지의 리소스 ID를 지정 합니다.  
  
 [in] `cx`  
 픽셀 단위로 이미지 목록의 이미지의 너비를 지정합니다.  
  
 [in] `clrTransp`  
 투명 한 색을 지정 하는 RGB 값입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 성공 합니다; 그렇지 않으면 반환 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 사용 하 여 이미지가 Microsoft Office 2003 모드에서 도구 모음 단추에 표시 될 이미지 목록을 연결 합니다. 이미지 인덱스 페이지 인덱스 일치 해야 합니다.  
  
 Microsoft Office 2003 모드에 없는 경우이 메서드를 호출 되어야 합니다. 자세한 내용은 참조 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)합니다.  
  
##  <a name="setvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::SetVisiblePageButtons  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetVisiblePageButtons(int nVisiblePageButtons);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nVisiblePageButtons`  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCBaseTabCtrl 클래스](../../mfc/reference/cmfcbasetabctrl-class.md)   
 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarPane 클래스](../../mfc/reference/cmfcoutlookbarpane-class.md)

