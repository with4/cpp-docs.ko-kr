---
title: "CMFCTabCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabCtrl
- AFXTABCTRL/CMFCTabCtrl
- AFXTABCTRL/CMFCTabCtrl::ActivateMDITab
- AFXTABCTRL/CMFCTabCtrl::AllowDestroyEmptyTabbedPane
- AFXTABCTRL/CMFCTabCtrl::AutoSizeWindow
- AFXTABCTRL/CMFCTabCtrl::CalcRectEdit
- AFXTABCTRL/CMFCTabCtrl::Create
- AFXTABCTRL/CMFCTabCtrl::EnableActiveTabCloseButton
- AFXTABCTRL/CMFCTabCtrl::EnableInPlaceEdit
- AFXTABCTRL/CMFCTabCtrl::EnableTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::EnsureVisible
- AFXTABCTRL/CMFCTabCtrl::GetDocumentIcon
- AFXTABCTRL/CMFCTabCtrl::GetFirstVisibleTabNum
- AFXTABCTRL/CMFCTabCtrl::GetResizeMode
- AFXTABCTRL/CMFCTabCtrl::GetScrollBar
- AFXTABCTRL/CMFCTabCtrl::GetTabArea
- AFXTABCTRL/CMFCTabCtrl::GetTabMaxWidth
- AFXTABCTRL/CMFCTabCtrl::GetTabsHeight
- AFXTABCTRL/CMFCTabCtrl::GetTabsRect
- AFXTABCTRL/CMFCTabCtrl::GetWndArea
- AFXTABCTRL/CMFCTabCtrl::HideActiveWindowHorzScrollBar
- AFXTABCTRL/CMFCTabCtrl::HideInactiveWindow
- AFXTABCTRL/CMFCTabCtrl::HideNoTabs
- AFXTABCTRL/CMFCTabCtrl::HideSingleTab
- AFXTABCTRL/CMFCTabCtrl::IsActiveInMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::IsActiveTabBoldFont
- AFXTABCTRL/CMFCTabCtrl::IsActiveTabCloseButton
- AFXTABCTRL/CMFCTabCtrl::IsDrawFrame
- AFXTABCTRL/CMFCTabCtrl::IsFlatFrame
- AFXTABCTRL/CMFCTabCtrl::IsFlatTab
- AFXTABCTRL/CMFCTabCtrl::IsLeftRightRounded
- AFXTABCTRL/CMFCTabCtrl::IsMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::IsOneNoteStyle
- AFXTABCTRL/CMFCTabCtrl::IsSharedScroll
- AFXTABCTRL/CMFCTabCtrl::IsTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::IsVS2005Style
- AFXTABCTRL/CMFCTabCtrl::ModifyTabStyle
- AFXTABCTRL/CMFCTabCtrl::OnDragEnter
- AFXTABCTRL/CMFCTabCtrl::OnDragOver
- AFXTABCTRL/CMFCTabCtrl::OnShowTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::SetActiveInMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::SetActiveTab
- AFXTABCTRL/CMFCTabCtrl::SetActiveTabBoldFont
- AFXTABCTRL/CMFCTabCtrl::SetDrawFrame
- AFXTABCTRL/CMFCTabCtrl::SetFlatFrame
- AFXTABCTRL/CMFCTabCtrl::SetImageList
- AFXTABCTRL/CMFCTabCtrl::SetResizeMode
- AFXTABCTRL/CMFCTabCtrl::SetTabMaxWidth
- AFXTABCTRL/CMFCTabCtrl::StopResize
- AFXTABCTRL/CMFCTabCtrl::SynchronizeScrollBar
- AFXTABCTRL/CMFCTabCtrl::m_bEnableActivate
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabCtrl::SwapTabs method
- CMFCTabCtrl constructor
- CMFCTabCtrl::MoveTab method
- CMFCTabCtrl::GetTabFromPoint method
- CMFCTabCtrl::PreTranslateMessage method
- CMFCTabCtrl::RecalcLayout method
- CMFCTabCtrl class
- CMFCTabCtrl::IsPtInTabArea method
ms.assetid: d441385d-2c72-4203-96fa-deae2273da35
caps.latest.revision: 33
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
ms.openlocfilehash: 595ff7fbcd55f3b756ce650e02b6247b898d7629
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctabctrl-class"></a>CMFCTabCtrl Class
`CMFCTabCtrl` 클래스 탭 컨트롤에 대 한 기능을 제공 합니다. 탭 컨트롤은 맨 위 또는 아래에 평면 또는&3;차원 탭이 포함된 도킹 가능한 창을 표시합니다. 탭은 텍스트와 이미지를 표시하고 활성화된 경우 색을 변경할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCTabCtrl::CMFCTabCtrl`|기본 생성자입니다.|  
|`CMFCTabCtrl::~CMFCTabCtrl`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCTabCtrl::ActivateMDITab](#activatemditab)|현재 탭 컨트롤의 지정 된 탭을 표시 하 고 해당 탭에 포커스를 설정 합니다.|  
|[CMFCTabCtrl::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)||  
|[CMFCTabCtrl::AutoSizeWindow](#autosizewindow)|프레임 워크 창의 모든 탭 컨트롤 때 해당 탭 컨트롤의 사용자 인터페이스 요소 클라이언트 영역의 크기를 조정 하는지 여부를 지정 합니다.|  
|[CMFCTabCtrl::CalcRectEdit](#calcrectedit)|지정 된 탭 영역의 크기를 압축 됩니다. (`CMFCBaseTabCtrl::CalcRectEdit`를 재정의합니다.)|  
|[CMFCTabCtrl::Create](#create)|탭 컨트롤을 만들고 연결 하는 `CMFCTabCtrl` 개체입니다.|  
|`CMFCTabCtrl::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|[CMFCTabCtrl::EnableActiveTabCloseButton](#enableactivetabclosebutton)|표시 하거나 닫기 단추를 숨깁니다 ( **X**) 활성 탭에 있습니다.|  
|[CMFCTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|레이블 편집 가능한 탭을 사용 하지 않도록 설정 하거나 사용 합니다. (재정의 [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|  
|[CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu)|두 개의 단추를 탭 창 메뉴를 여는 단추와 창의 탭을 스크롤 하는 대체 합니다.|  
|[CMFCTabCtrl::EnsureVisible](#ensurevisible)|탭에 표시 되는지 확인 합니다.|  
|[CMFCTabCtrl::GetDocumentIcon](#getdocumenticon)|연결 탭 창 팝업 메뉴에 탭 된 기호를 검색 합니다.|  
|[CMFCTabCtrl::GetFirstVisibleTabNum](#getfirstvisibletabnum)|현재 탭 컨트롤에 표시 되는 첫 번째 탭의 인덱스를 검색 합니다.|  
|[CMFCTabCtrl::GetResizeMode](#getresizemode)|현재 탭 컨트롤을 조정할 수 있는 방법을 지정 하는 값을 검색 합니다.|  
|[CMFCTabCtrl::GetScrollBar](#getscrollbar)|탭 컨트롤에 연관 된 스크롤 막대 개체에 대 한 포인터를 검색 합니다.|  
|[CMFCTabCtrl::GetTabArea](#gettabarea)|위쪽 또는 아래쪽의 탭 컨트롤의 탭 레이블 영역의 경계 사각형을 검색합니다. (재정의 [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|  
|`CMFCTabCtrl::GetTabFromPoint`|지정된 된 지점에 포함 된 탭을 검색 합니다. (재정의 [CMFCBaseTabCtrl::GetTabFromPoint](../../mfc/reference/cmfcbasetabctrl-class.md#gettabfrompoint).)|  
|[CMFCTabCtrl::GetTabMaxWidth](#gettabmaxwidth)|탭의 최대 너비를 검색합니다.|  
|[CMFCTabCtrl::GetTabsHeight](#gettabsheight)|현재 탭 컨트롤의 탭 영역의 높이 검색합니다.|  
|[CMFCTabCtrl::GetTabsRect](#gettabsrect)|현재 탭 컨트롤의 탭 영역 경계가 되는 사각형을 검색 합니다. (재정의 [CMFCBaseTabCtrl::GetTabsRect](../../mfc/reference/cmfcbasetabctrl-class.md#gettabsrect).)|  
|`CMFCTabCtrl::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식으로 연결 된 개체입니다.|  
|[CMFCTabCtrl::GetWndArea](#getwndarea)|현재 탭 컨트롤의 클라이언트 영역 경계를 검색합니다.|  
|[CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar)|현재 창의 있는 경우 가로 스크롤 막대를 숨깁니다.|  
|[CMFCTabCtrl::HideInactiveWindow](#hideinactivewindow)|프레임 워크 비활성 탭 컨트롤 창을 표시할 수 있는지 여부를 지정 합니다.|  
|[CMFCTabCtrl::HideNoTabs](#hidenotabs)|사용 하거나 볼 수 있는 탭이 없을 경우 탭 영역 그리기를 사용 하지 않도록 설정 합니다.|  
|[CMFCTabCtrl::HideSingleTab](#hidesingletab)|사용 하거나 단일 탭된 창 경우 탭 그리기를 사용 하지 않도록 설정 합니다. (재정의 [CMFCBaseTabCtrl::HideSingleTab](../../mfc/reference/cmfcbasetabctrl-class.md#hidesingletab).)|  
|[CMFCTabCtrl::IsActiveInMDITabGroup](#isactiveinmditabgroup)|탭 컨트롤의 현재 탭 다중 문서 인터페이스 탭 그룹에서 활성 탭 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsActiveTabBoldFont](#isactivetabboldfont)|활성 탭의 텍스트가 굵은 글꼴을 사용 하 여 표시 되는지 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsActiveTabCloseButton](#isactivetabclosebutton)|나타냅니다 여부 닫기 단추 ( **X**)는 활성 탭 또는 탭 영역의 오른쪽 위 모서리에 표시 됩니다.|  
|[CMFCTabCtrl::IsDrawFrame](#isdrawframe)|탭된 창에 포함 된 창 주위 프레임 사각형 그릴지 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsFlatFrame](#isflatframe)|평면 또는 3D 탭 영역 주위의 프레임 인지를 나타냅니다.|  
|[CMFCTabCtrl::IsFlatTab](#isflattab)|현재 탭 컨트롤의 탭의 모양 평평한 지 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsLeftRightRounded](#isleftrightrounded)|현재 탭 컨트롤의 탭의 왼쪽 및 오른쪽의 모양을 반올림 있는지 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsMDITabGroup](#ismditabgroup)|현재 탭 컨트롤은 다중 문서 인터페이스 창의 클라이언트 영역에 포함 되어 있는지 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle)|Microsoft OneNote의 스타일에서 현재 탭 컨트롤을 표시할지 여부를 나타냅니다.|  
|`CMFCTabCtrl::IsPtInTabArea`|영역 내부에 탭 지점을 인지 여부를 확인 합니다. (재정의 [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|  
|[CMFCTabCtrl::IsSharedScroll](#issharedscroll)|현재 탭 컨트롤에 탭 그룹으로 스크롤할 수 있는 스크롤 막대가 있는지 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsTabDocumentsMenu](#istabdocumentsmenu)|탭 컨트롤에서 스크롤 단추 또는 탭 창 메뉴를 표시 하는 단추를 표시할지 여부를 나타냅니다.|  
|[CMFCTabCtrl::IsVS2005Style](#isvs2005style)|Visual Studio.NET 2005의 스타일에서 탭 표시 되는지 여부를 나타냅니다.|  
|[CMFCTabCtrl::ModifyTabStyle](#modifytabstyle)|현재 탭 컨트롤의 탭의 모양을 지정합니다.|  
|`CMFCTabCtrl::MoveTab`|다른 탭 위치 탭을 이동합니다. (재정의 [CMFCBaseTabCtrl::MoveTab](../../mfc/reference/cmfcbasetabctrl-class.md#movetab).)|  
|[CMFCTabCtrl::OnDragEnter](#ondragenter)|커서를 먼저 탭 컨트롤 창으로 끌 때에 프레임 워크에서 호출 합니다.|  
|[CMFCTabCtrl::OnDragOver](#ondragover)|놓기 대상 창 위로 마우스를 이동할 때 프레임 워크에서 끌기 작업 중 호출. (재정의 [CMFCBaseTabCtrl::OnDragOver](../../mfc/reference/cmfcbasetabctrl-class.md#ondragover).)|  
|[CMFCTabCtrl::OnShowTabDocumentsMenu](#onshowtabdocumentsmenu)|사용자 탭을 선택 하 고 활성 탭 선택 된 탭을 사용 하면 될 때까지 대기, 탭 창 팝업 메뉴를 표시 합니다.|  
|`CMFCTabCtrl::PreTranslateMessage`|창 메시지를 변환 하 여으로 디스패치 되기 전에 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수입니다. (재정의 [CMFCBaseTabCtrl::PreTranslateMessage](../../mfc/reference/cmfcbasetabctrl-class.md#pretranslatemessage).)|  
|`CMFCTabCtrl::RecalcLayout`|탭 컨트롤의 내부 레이아웃이 다시 계산 됩니다. (재정의 [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|  
|[CMFCTabCtrl::SetActiveInMDITabGroup](#setactiveinmditabgroup)|탭 컨트롤의 현재 탭 다중 문서 인터페이스 탭 그룹에서 활성 탭으로 설정합니다.|  
|[CMFCTabCtrl::SetActiveTab](#setactivetab)|탭을 활성화합니다. (재정의 [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|  
|[CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont)|활성 탭에 굵은 글꼴을 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[CMFCTabCtrl::SetDrawFrame](#setdrawframe)|사용 하거나 drawinga 프레임 사각형 있는 포함 된 막대를 사용 하지 않도록 설정 합니다.|  
|[CMFCTabCtrl::SetFlatFrame](#setflatframe)|평면 또는 3D 프레임 탭 영역 주위에 그릴 것인지를 지정 합니다.|  
|[CMFCTabCtrl::SetImageList](#setimagelist)|이미지 목록을 지정합니다. (재정의 [CMFCBaseTabCtrl::SetImageList](../../mfc/reference/cmfcbasetabctrl-class.md#setimagelist).)|  
|[CMFCTabCtrl::SetResizeMode](#setresizemode)|다음 컨트롤을 다시 표시 되 고 현재 탭 컨트롤을 조정할 수 있는 방법을 지정 합니다.|  
|[CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth)|탭된 창에 최대 탭 너비를 지정합니다.|  
|[CMFCTabCtrl::StopResize](#stopresize)|탭 컨트롤의 현재 크기 조정 작업을 종료합니다.|  
|`CMFCTabCtrl::SwapTabs`|탭의 쌍을 바꿉니다. (재정의 [CMFCBaseTabCtrl::SwapTabs](../../mfc/reference/cmfcbasetabctrl-class.md#swaptabs).)|  
|[CMFCTabCtrl::SynchronizeScrollBar](#synchronizescrollbar)|플랫 탭을 표시 하는 탭 컨트롤에 가로 스크롤 막대를 그립니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCTabCtrl::m_bEnableActivate](#m_benableactivate)|현재 보기를에서 새 탭을 삽입 하 고 사용 포커스를 잃을 수 없습니다.|  
  
## <a name="remarks"></a>주의  
 `CMFCTabCtrl` 클래스는 지원 합니다.  
  
-   탭 컨트롤 스타일 등이 포함 된 3D에서 flat 플랫 공유 가로 스크롤 막대를 사용 합니다.  
  
-   위쪽 또는 아래쪽 창에 있는 탭입니다.  
  
-   텍스트, 이미지 또는 텍스트 및 이미지를 표시 하는 탭을 선택 합니다.  
  
-   탭이 활성화 하는 경우 색을 변경 하는 탭을 선택 합니다.  
  
-   테두리 크기를 조정할 수 있는 탭에 대 한 변경 합니다.  
  
-   분리 가능한 탭된 창입니다.  
  
 `CMFCTabCtrl` 클래스는 대화 상자를 사용 하 여 도킹을 사용 하는 응용 프로그램 제어와 같은 막대에 대 한 것은 [!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)] 및 [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]합니다. 자세한 내용은 참조 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md)합니다.  
  
 응용 프로그램의 탭 컨트롤을 도킹 한 크기 조정 가능한 추가 하려면 다음이 단계를 따르십시오.  
  
1.  인스턴스를 만들고 [CTabbedPane 클래스](../../mfc/reference/ctabbedpane-class.md)합니다.  
  
2.  호출 [CDockablePane::Create](../../mfc/reference/cdockablepane-class.md#create)합니다.  
  
3.  사용 하 여 [CBaseTabbedPane::AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) 또는 [CMFCBaseTabCtrl::InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) 새 탭을 추가 합니다.  
  
4.  호출 [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking) 현재 도킹 탭 컨트롤 주 프레임 창에 도킹할 수 있도록 합니다.  
  
5.  호출 [CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane) 은 탭된 창을 주 프레임에 도킹 합니다.  
  
 탭된 창으로 도킹 컨트롤 막대를 만드는 방법에 대 한 예제를 보려면 [CTabbedPane 클래스](../../mfc/reference/ctabbedpane-class.md)합니다. 사용 하 여 `CMFCTabCtrl` 비 도킹 컨트롤을 만드는 것이 한 `CMFCTabCtrl` 개체와 다음 호출 [CMFCTabCtrl::Create](#create)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)  
  
## <a name="example"></a>예제  
 다음 예제에서 다양 한 메서드를 사용 하는 방법을 보여 줍니다는 `CMFCTabCtrl` 를 구성 하는 클래스는 `CMFCTabCtrl` 개체입니다. 예제에는 탭을 추가, 활성 탭에 있는 닫기 단추를 표시, 편집 가능한 탭 레이블을 사용 및 탭된 창 레이블의 팝업 메뉴를 표시 하는 방법을 설명 합니다. 이 예제는의 일부는 [상태 컬렉션 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_StateCollection #&1;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection #&3;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_2.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtabctrl.h  
  
##  <a name="activatemditab"></a>CMFCTabCtrl::ActivateMDITab  
 현재 탭 컨트롤의 지정 된 탭을 표시 하 고 해당 탭에 포커스를 설정 합니다.  
  
```  
void ActivateMDITab(int nTab = -1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nTab`  
 표시 되는 또는 현재 활성 탭을 지정 하려면-1 인 탭의&0;부터 시작 하는 인덱스입니다.  
  
##  <a name="allowdestroyemptytabbedpane"></a>CMFCTabCtrl::AllowDestroyEmptyTabbedPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항상 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="autosizewindow"></a>CMFCTabCtrl::AutoSizeWindow  
 프레임 워크 창의 모든 탭 컨트롤 때 해당 탭 컨트롤의 사용자 인터페이스 요소 클라이언트 영역의 크기를 조정 하는지 여부를 지정 합니다.  
  
```  
void AutoSizeWindow(BOOL bAutoSize = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bAutoSize`  
 `TRUE`탭 컨트롤 창에 자동으로 크기를 조정 하려면 그렇지 않으면 `FALSE`합니다. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="create"></a>CMFCTabCtrl::Create  
 탭 컨트롤을 만들고 연결 하는 `CMFCTabCtrl` 개체입니다.  
  
```  
BOOL Create(
    Style style,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    Location location=LOCATION_BOTTOM,  
    BOOL bCloseBtn=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `style`  
 탭 컨트롤의 스타일입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
 [in] `rect`  
 탭 컨트롤의 경계를 설정 하는 사각형입니다.  
  
 [in] `pParentWnd`  
 부모 창에 대 한 포인터입니다. `NULL`이 아니어야 합니다.  
  
 [in] `nID`  
 탭 컨트롤의 ID입니다.  
  
 [in] `location`  
 탭의 위치입니다. 기본값은 `LOCATION_BOTTOM`입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
 [in] `bCloseBtn`  
 `TRUE`탭; 닫기 단추를 표시 하려면 그렇지 않으면 `FALSE`합니다. 기본값은 `FALSE`입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 `TRUE`이고, 그러지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 다음 표에서 설명에 지정할 수 있는 값은 `style` 매개 변수입니다.  
  
|스타일|설명|  
|-----------|-----------------|  
|STYLE_3D|3 차원 모양의 탭 컨트롤을 만듭니다.|  
|STYLE_FLAT|플랫 탭이 포함 된 탭 컨트롤을 만듭니다.|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|플랫 탭 및 부모 창에서 자르는 하는 경우에 탭을 스크롤할 수 있는 스크롤 막대를 사용 하 여 탭 컨트롤을 만듭니다.|  
|STYLE_3D_ONENOTE|Microsoft OneNote의 스타일에서 탭 컨트롤을 만듭니다.|  
|STYLE_3D_VS2005|Microsoft Visual Studio 2005의 스타일에서 탭 컨트롤을 만듭니다.|  
|STYLE_3D_ROUNDED|Microsoft Visual Studio 2005의 스타일에서 둥근된 탭이 포함 된 탭 컨트롤을 만듭니다.|  
|STYLE_3D_ROUNDED_SCROLL|둥근된 탭과 Microsoft Visual Studio 2005의 스타일에서 스크롤 단추 탭 컨트롤을 만듭니다.|  
  
 에 지정할 수 있는 값을 나열 하는 다음 표에 `location` 매개 변수입니다.  
  
|위치|설명|  
|--------------|-----------------|  
|LOCATION_BOTTOM|탭의 탭 컨트롤의 맨 아래에 나와 있습니다.|  
|LOCATION_TOP|탭의 탭 컨트롤의 위쪽에 나와 있습니다.|  
  
### <a name="example"></a>예제  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `Create` 에서 메서드는 `CMFCTabCtrl` 클래스입니다. 이 예제는의 일부는 [상태 컬렉션 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_StateCollection #&1;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection #&2;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_3.cpp)]  
  
##  <a name="calcrectedit"></a>CMFCTabCtrl::CalcRectEdit  
 지정 된 탭 영역의 크기를 압축 됩니다.  
  
```  
virtual void CalcRectEdit(CRect& rectEdit);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rectEdit`  
 탭의 영역을 지정 하는 사각형입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 탭의 레이블을 변경 하면 호출 됩니다. 이 메서드는&1;/2 현재 탭 높이 지정된 된 사각형의 왼쪽과 오른쪽을 수축 하 고 위쪽 및 아래쪽 단위로 한 단위씩 수축.  
  
##  <a name="enableactivetabclosebutton"></a>CMFCTabCtrl::EnableActiveTabCloseButton  
 표시 하거나 닫기 단추를 숨깁니다 ( **X**) 활성 탭에 있습니다.  
  
```  
void EnableActiveTabCloseButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`활성 탭;에 닫기 단추를 표시 하려면 `FALSE` 닫기 단추 탭 영역의 오른쪽 위 모서리를 표시 합니다. 기본값은 `TRUE`입니다.  
  
##  <a name="enableinplaceedit"></a>CMFCTabCtrl::EnableInPlaceEdit  
 레이블 편집 가능한 탭을 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`편집 가능한 탭 레이블,를 사용 하도록 설정 하려면 `FALSE` 편집 가능한 탭 레이블을 사용 하지 않으려면 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="enabletabdocumentsmenu"></a>CMFCTabCtrl::EnableTabDocumentsMenu  
 두 개의 단추를 사용 하 여 창의 탭 스크롤해야 하는 사용자 인터페이스와 탭 창 팝업 메뉴를 표시 하는 인터페이스 사이 전환 합니다.  
  
```  
void EnableTabDocumentsMenu(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`레이블 탭된 창,의 팝업 메뉴를 표시 하려면 `FALSE` 앞으로 및 뒤로 스크롤 단추를 표시할 수 있습니다. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
 사용자가 레이블 탭을 클릭 하면 해당 탭된 창 프레임 워크에 표시 됩니다. 탭 레이블이 표시 되 면, 해당 위치를 변경 하지 않고 탭된 창이 열립니다. 사용자가 팝업 메뉴에서 문서를 선택 하는 경우 해당 탭된 창 화면 꺼져 탭된 창에는 첫 번째 탭 됩니다.  
  
##  <a name="ensurevisible"></a>CMFCTabCtrl::EnsureVisible  
 탭에 표시 되는지 확인 합니다.  
  
```  
virtual BOOL EnsureVisible(int iTab);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iTab`  
 탭의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`성공 하면 `FALSE` 경우는 `iTab` 매개 변수 인덱스가 잘못 되었습니다.  
  
### <a name="remarks"></a>주의  
 지정 된 탭 표시 되는지 보장 하기 위해이 메서드를 사용 합니다. 필요한 경우 탭 컨트롤이 스크롤됩니다.  
  
##  <a name="getdocumenticon"></a>CMFCTabCtrl::GetDocumentIcon  
 팝업 메뉴 탭 창에 탭과 연관 된 이미지를 검색 합니다.  
  
```  
static HICON __stdcall GetDocumentIcon(UINT nCmdID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nCmdID`  
 팝업 메뉴 탭 창에서 탭의 명령 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 비트맵 이미지의 핸들입니다.  
  
##  <a name="getfirstvisibletabnum"></a>CMFCTabCtrl::GetFirstVisibleTabNum  
 현재 탭 컨트롤에 표시 되는 첫 번째 탭의 인덱스를 검색 합니다.  
  
```  
virtual int GetFirstVisibleTabNum() const;  
```  
  
### <a name="return-value"></a>반환 값  
 탭 컨트롤의 탭의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 Microsoft OneNote의 스타일에서 탭 컨트롤을 표시 하는 경우에이 메서드를 사용 합니다. 사용 된 [CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle) 메서드는 스타일을 결정 합니다.  
  
##  <a name="getresizemode"></a>CMFCTabCtrl::GetResizeMode  
 현재 탭 컨트롤을 조정할 수 있는 방법을 지정 하는 값을 검색 합니다.  
  
```  
ResizeMode GetResizeMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 중 하나는 `CMFCTabCtrl::ResizeMode` 탭 컨트롤을 조정할 수 있는 방법을 지정 하는 열거형 값입니다. 가능한 값 목록은 설명 부분을 참조 하십시오.는 [CMFCTabCtrl::SetResizeMode](#setresizemode) 메서드.  
  
##  <a name="getscrollbar"></a>CMFCTabCtrl::GetScrollBar  
 탭 컨트롤에 연관 된 스크롤 막대 개체에 대 한 포인터를 검색 합니다.  
  
```  
CScrollBar* GetScrollBar();
```  
  
### <a name="return-value"></a>반환 값  
 스크롤 하는 개체에 대 한 포인터 또는 `NULL` 탭 컨트롤 사용 하 여 만들지 않은 경우는 `STYLE_FLAT_SHARED_HORZ_SCROLL` 스타일입니다.  
  
### <a name="remarks"></a>주의  
 탭 컨트롤의 포함 된 스크롤 막대에 액세스 하려면이 메서드를 사용 합니다. 스크롤 막대 개체를 만들 때 탭 컨트롤에 있을 때만 `STYLE_FLAT_SHARED_HORZ_SCROLL` 스타일입니다.  
  
##  <a name="gettabarea"></a>CMFCTabCtrl::GetTabArea  
 위쪽 또는 아래쪽의 탭 컨트롤의 탭 레이블 영역의 경계 사각형을 검색합니다.  
  
```  
void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `rectTabAreaTop`  
 이 메서드가 반환 하는 경우이 참조는 맨 위 탭 레이블 영역 경계가 되는 사각형을 포함 합니다. 클라이언트 좌표에는 사각형은입니다. 이 참조가 없는 탭 레이블 영역 탭 컨트롤의 위쪽에 있는 경우 비어 있습니다.  
  
 [out] `rectTabAreaBottom`  
 이 메서드가 반환 하는 경우이 참조는 아래쪽 탭 레이블 영역 경계가 되는 사각형을 포함 합니다. 클라이언트 좌표에는 사각형은입니다. 이 참조가 없는 탭 레이블 영역 탭 컨트롤의 아래쪽에 있는 경우 비어 있습니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 크기와 탭된 창에 탭 영역 위치를 결정 합니다.  
  
##  <a name="gettabmaxwidth"></a>CMFCTabCtrl::GetTabMaxWidth  
 탭의 최대 너비를 검색합니다.  
  
```  
int GetTabMaxWidth() const;  
```  
  
### <a name="return-value"></a>반환 값  
 최대 너비 (픽셀)에서 탭입니다. 반환 값이 0 이면 탭 너비는 제한이 없습니다.  
  
### <a name="remarks"></a>주의  
 사용 된 [CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth) 최대 탭 너비를 설정 하는 방법입니다.  
  
##  <a name="gettabsheight"></a>CMFCTabCtrl::GetTabsHeight  
 현재 탭 컨트롤의 탭 영역의 높이 검색합니다.  
  
```  
virtual int GetTabsHeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
 모든 탭이 표시 또는 경우에는&0; 탭이 보이지 않을 경우 탭 영역의 높이입니다.  
  
##  <a name="gettabsrect"></a>CMFCTabCtrl::GetTabsRect  
 현재 탭 컨트롤의 탭 영역 경계가 되는 사각형을 검색 합니다.  
  
```  
virtual void GetTabsRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `rect`  
 이 메서드는 `rect` 매개 변수 탭 영역 경계를 설정 하는 사각형을 포함 합니다.  
  
##  <a name="getwndarea"></a>CMFCTabCtrl::GetWndArea  
 현재 탭 컨트롤의 클라이언트 영역 경계를 검색합니다.  
  
```  
void GetWndArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in, out] `rect`  
 이 메서드가 반환 하는 경우이 매개 변수는 현재 탭 컨트롤의 경계를 설정 하는 사각형을 포함 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="hideactivewindowhorzscrollbar"></a>CMFCTabCtrl::HideActiveWindowHorzScrollBar  
 활성 창에 있는 경우에 가로 스크롤 막대를 숨깁니다.  
  
```  
void HideActiveWindowHorzScrollBar();
```  
  
### <a name="remarks"></a>주의  
 탭 컨트롤 깜박이 사용자가 탭 컨트롤 페이지 간에 전환 되지 않도록 하려면이 메서드를 사용 합니다.  
  
##  <a name="hideinactivewindow"></a>CMFCTabCtrl::HideInactiveWindow  
 프레임 워크 비활성 탭 컨트롤 창에 표시 되는지 여부를 지정 합니다.  
  
```  
void HideInactiveWindow(BOOL bHide = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bHide`  
 `TRUE`나타내지 비활성 창입니다. `FALSE` 비활성 창에 표시 합니다. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="hidenotabs"></a>CMFCTabCtrl::HideNoTabs  
 사용 하거나 볼 수 있는 탭이 없을 경우 탭 영역 그리기를 사용 하지 않도록 설정 합니다.  
  
```  
void HideNoTabs(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bHide`  
 `TRUE`탭 영역이; 그리기를 사용 하도록 설정 하려면 `FALSE` 드로잉을 사용 하지 않도록 설정 하려면. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="hidesingletab"></a>CMFCTabCtrl::HideSingleTab  
 사용 하거나 단일 탭된 창 경우 탭 그리기를 사용 하지 않도록 설정 합니다.  
  
```  
virtual void HideSingleTab(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bHide`  
 `TRUE`단일 탭된 창;에 대 한 탭을 그리지를 `FALSE` 단일 탭을 그리는 데 있습니다. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="isactiveinmditabgroup"></a>CMFCTabCtrl::IsActiveInMDITabGroup  
 탭 컨트롤의 현재 탭 다중 문서 인터페이스 탭 그룹에서 활성 탭 여부를 나타냅니다.  
  
```  
BOOL IsActiveInMDITabGroup() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`탭 컨트롤의 현재 탭이 활성 탭 MDI 탭 그룹에 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 세로 또는 가로 탭 그룹 중 하나에 여러 개의 문서 창을 구성할 수 있으며 다른 탭 그룹에서 문서를 쉽게 이동할 수 있습니다.  
  
##  <a name="isactivetabboldfont"></a>CMFCTabCtrl::IsActiveTabBoldFont  
 활성 탭의 텍스트가 굵은 글꼴을 사용 하 여 표시 되는지 여부를 나타냅니다.  
  
```  
BOOL IsActiveTabBoldFont() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`활성 탭 굵은 글꼴;를 사용 하 여 표시 되 면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 사용 하는 [CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont) 메서드 활성 탭 글꼴을 변경 합니다.  
  
##  <a name="isactivetabclosebutton"></a>CMFCTabCtrl::IsActiveTabCloseButton  
 나타냅니다 여부 닫기 단추 ( **X**) 또는 탭 영역의 오른쪽 위 모서리는 활성 탭에 표시 됩니다.  
  
```  
virtual BOOL IsActiveTabCloseButton() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`활성 탭;에 표시 되 면 닫기 단추 `FALSE` 이면 닫기 단추 탭 영역의 오른쪽 위 모서리에 표시 됩니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="isdrawframe"></a>CMFCTabCtrl::IsDrawFrame  
 탭된 창에 포함 된 창 주위 프레임 사각형 그릴지 여부를 나타냅니다.  
  
```  
BOOL IsDrawFrame() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우에 프레임 사각형이 그려집니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 사용 된 [CMFCTabCtrl::SetDrawFrame](#setdrawframe) 사용할지 여부를 프레임에 사각형을 그려 메서드.  
  
##  <a name="isflatframe"></a>CMFCTabCtrl::IsFlatFrame  
 평면 또는 3D 탭 영역 주위의 프레임 인지를 나타냅니다.  
  
```  
BOOL IsFlatFrame() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`탭 영역 주위의 프레임 플랫; 인 경우 `FALSE` 프레임은&3; 차원 하는 경우.  
  
### <a name="remarks"></a>주의  
 사용 하 여 [CMFCTabCtrl::SetFlatFrame](#setflatframe) 프레임을 그리는 방법을 변경 하려면 메서드.  
  
##  <a name="isflattab"></a>CMFCTabCtrl::IsFlatTab  
 현재 탭 컨트롤의 탭의 모양 평평한 지 여부를 나타냅니다.  
  
```  
virtual BOOL IsFlatTab() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`현재 탭 컨트롤의 탭의 모양 플랫; 인 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="isleftrightrounded"></a>CMFCTabCtrl::IsLeftRightRounded  
 현재 탭 컨트롤의 탭의 왼쪽 및 오른쪽의 모양을 반올림 있는지 여부를 나타냅니다.  
  
```  
virtual BOOL IsLeftRightRounded() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`각 탭의 양쪽; 반올림 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="ismditabgroup"></a>CMFCTabCtrl::IsMDITabGroup  
 현재 탭 컨트롤은 다중 문서 인터페이스 창의 클라이언트 영역에 포함 되어 있는지 여부를 나타냅니다.  
  
```  
virtual BOOL IsMDITabGroup() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`현재 탭 컨트롤은 MDI 클라이언트 영역 창;에 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="isonenotestyle"></a>CMFCTabCtrl::IsOneNoteStyle  
 Microsoft OneNote의 스타일에서 현재 탭 컨트롤을 표시할지 여부를 나타냅니다.  
  
```  
virtual BOOL IsOneNoteStyle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`Microsoft OneNote;의 스타일 탭 컨트롤을 표시 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="issharedscroll"></a>CMFCTabCtrl::IsSharedScroll  
 현재 탭 컨트롤에 탭 그룹으로 스크롤할 수 있는 스크롤 막대가 있는지 여부를 나타냅니다.  
  
```  
BOOL IsSharedScroll() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`탭 컨트롤에는 공유 스크롤 막대. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드가 반환 `TRUE` 경우는 `style` 의 매개 변수는 [CMFCTabCtrl::Create](#create) 메서드는 STYLE_FLAT_SHARED_HORZ_SCROLL 합니다.  
  
##  <a name="istabdocumentsmenu"></a>CMFCTabCtrl::IsTabDocumentsMenu  
 탭 컨트롤에서 스크롤 단추 또는 탭 창 메뉴를 표시 하는 단추를 표시할지 여부를 나타냅니다.  
  
```  
BOOL IsTabDocumentsMenu() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`탭된 창의 레이블 탭된 창, 팝업 메뉴를 사용 하 여 스크롤됩니다 하는 경우 `FALSE` 경우 앞으로 및 뒤로 스크롤 단추를 사용 하 여 탭된 창 스크롤됩니다.  
  
### <a name="remarks"></a>주의  
 사용 된 [CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu) 스크롤 하는 방법을 지정 하는 메서드 탭 창입니다.  
  
##  <a name="isvs2005style"></a>CMFCTabCtrl::IsVS2005Style  
 Visual Studio 2005의 스타일을 사용 하 여 탭을 그리는 있는지 여부를 나타냅니다.  
  
```  
virtual BOOL IsVS2005Style() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`Visual Studio 2005;의 스타일을 사용 하 여 탭을 그리는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 사용 하는 `style` 의 매개 변수는 [CMFCTabCtrl::Create](#create) 탭을 그리는 방법을 지정 하는 방법입니다.  
  
##  <a name="m_benableactivate"></a>CMFCTabCtrl::m_bEnableActivate  
 현재 보기를에서 새 탭을 삽입 하 고 사용 포커스를 잃을 수 없습니다.  
  
```  
static BOOL m_bEnableActivate;  
```  
  
### <a name="remarks"></a>주의  
 포커스가 있는 탭을 삽입 하 고 활성화 하는 경우에 일반적으로 새 탭된 창에서 수행 됩니다. 설정의 `CMFCTabCtrl::m_bEnableActivate` 멤버 변수를 `FALSE` 원래 포커스를 유지할 수 있습니다. 기본값은 `TRUE`입니다.  
  
##  <a name="modifytabstyle"></a>CMFCTabCtrl::ModifyTabStyle  
 현재 탭 컨트롤의 탭의 모양을 지정합니다.  
  
```  
BOOL ModifyTabStyle(Style style);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `style`  
 탭 컨트롤의 모양을 지정 하는 열거형 값 중 하나입니다. 자세한 내용은 주의에 있는 표를 참조 하십시오.  
  
### <a name="return-value"></a>반환 값  
 항상 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
 값은 `style` 매개 변수는 다음 중 하나일 수 `CMFCTabCtrl::Style` 열거형입니다.  
  
|이름|설명|  
|----------|-----------------|  
|STYLE_3D|모서리가 둥근 사각형,&3; 차원 탭을 표시 합니다.|  
|STYLE_3D_ONENOTE|세로 한쪽 및 경사 한쪽 있고 둥근 모퉁이&3; 차원 탭이 표시 됩니다.|  
|STYLE_3D_ROUNDED|양쪽 기울어지게 되어 둥글게 있는&3; 차원 탭이 표시 됩니다.|  
|STYLE_3D_ROUNDED_SCROLL|양쪽 기울어지게 되어 둥글게 있는&3; 차원 탭이 표시 됩니다. 동시에 표시할 수 있는 것 보다 더 많은 탭에 있는 경우 프레임 워크 드롭다운 화살표 및 탭을 활성화 하려면 메뉴를 표시 합니다.|  
|STYLE_3D_SCROLLED|사각형,&3; 차원 탭이 표시 됩니다. 동시에 표시할 수 있는 것 보다 더 많은 탭에 있는 경우 프레임 워크 드롭다운 화살표 및 탭을 활성화 하려면 메뉴를 표시 합니다.|  
|STYLE_3D_VS2005|3 차원, 표시 경사 한쪽 및 세로 한쪽 있는 탭을 반올림 합니다.|  
|STYLE_FLAT|왼쪽과 오른쪽 기울어지게가 있는&2; 차원 탭이 표시 됩니다.|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|2 차원 탭이 표시 됩니다. 동시에 표시할 수 있는 것 보다 더 많은 탭에 있는 경우 프레임 워크 탭 영역의 끝에 스크롤 화살표를 표시 합니다.|  
  
##  <a name="ondragenter"></a>CMFCTabCtrl::OnDragEnter  
 처음 될 때 커서의 현재 탭 컨트롤의 창 프레임 워크에서 끌어서 놓기 작업 동안 호출 합니다.  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDataObject`  
 끌 데이터를 포함 하는 데이터 개체를 가리킵니다.  
  
 [in] `dwKeyState`  
 보조 키의 상태를 포함합니다. 이 매개 변수는 다음 값의 비트 조합 (OR): `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, 및 `MK_RBUTTON`합니다. 자세한 내용은 참조는 **메시지 매개 변수** 섹션 [마우스 입력에 대 한](http://msdn.microsoft.com/library/windows/desktop/ms645601)합니다.  
  
 [in] `point`  
 클라이언트 좌표에서 커서의 현재 위치를 포함합니다.  
  
### <a name="return-value"></a>반환 값  
 항상 `DROPEFFECT_NONE`, 즉, 놓기 대상 데이터를 받아들일 수 없습니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 끌어서 놓기 작업을 지원 합니다. 사용자 고유의 사용자 지정 동작을 구현 하려면이 메서드를 재정의 합니다.  
  
 기본적으로이 메서드가 호출 `CMFCTabCtrl::OnDragOver`는 항상 반환 `DROPEFFECT_NONE`합니다.  
  
##  <a name="ondragover"></a>CMFCTabCtrl::OnDragOver  
 놓기 대상 창 위로 마우스를 이동할 때 프레임 워크에서 끌기 작업 중 호출.  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDataObject`  
 에 대 한 포인터는 [COleDataObject](../../mfc/reference/coledataobject-class.md) 개체를 놓기 대상 위로 끄는입니다.  
  
 [in] `dwKeyState`  
 보조키 비트 조합 (또는 상태) `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, 및 `MK_RBUTTON`합니다. 자세한 내용은 "메시지 매개 변수"의 참조 [마우스 입력에 대 한](http://msdn.microsoft.com/library/windows/desktop/ms645601)합니다.  
  
 [in] `point`  
 현재 마우스 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 항상 `DROPEFFECT_NONE`입니다.  
  
### <a name="remarks"></a>주의  
 사용자 지정 구현으로이 메서드를 재정의 합니다. 자세한 내용은 참조는 [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover) 메서드.  
  
##  <a name="onshowtabdocumentsmenu"></a>CMFCTabCtrl::OnShowTabDocumentsMenu  
 사용자 탭을 선택 하 고 활성 탭 선택 된 탭을 사용 하면 될 때까지 대기, 탭 창 팝업 메뉴를 표시 합니다.  
  
```  
virtual void OnShowTabDocumentsMenu(CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `point`  
 팝업 메뉴를 표시할 곳을의 좌표를 지정 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="setactiveinmditabgroup"></a>CMFCTabCtrl::SetActiveInMDITabGroup  
 탭 컨트롤의 현재 탭 다중 문서 인터페이스 탭 그룹에서 활성 탭으로 설정합니다.  
  
```  
void SetActiveInMDITabGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bActive`  
 `TRUE`활성 탭을 현재 탭을 확인 하려면 `FALSE` 비활성을 현재 탭 수 있도록 합니다.  
  
### <a name="remarks"></a>주의  
 세로 또는 가로 탭 그룹 중 하나에 여러 개의 문서 창을 구성할 수 있으며 다른 탭 그룹에서 문서를 쉽게 이동할 수 있습니다.  
  
##  <a name="setactivetab"></a>CMFCTabCtrl::SetActiveTab  
 탭을 활성화합니다.  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iTab`  
 활성화 탭의&0;부터 시작 하는 인덱스를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`지정 된 탭이 활성; 수행 된 경우 `FALSE` 하는 경우 지정 된 `iTab` 매개 변수 값이 잘못 되었습니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 하지 않습니다는 `AFX_WM_CHANGE_ACTIVE_TAB` 탭 컨트롤의 부모 창에 알림.  
  
 `SetActiveTab` 메서드를 자동으로 호출 된 [CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar) 깜박이 화면을 방지 하기 위해.  
  
##  <a name="setactivetabboldfont"></a>CMFCTabCtrl::SetActiveTabBoldFont  
 활성 탭에 굵은 글꼴을 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
void SetActiveTabBoldFont(BOOL bIsBold=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bIsBold`  
 `TRUE`활성 탭;의 레이블을 표시 하려면 굵은 글꼴을 사용 하 여 `FALSE` 를 사용 하 여 표준 글꼴 레이블을 표시 합니다. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="setdrawframe"></a>CMFCTabCtrl::SetDrawFrame  
 프레임 사각형 포함 된 막대는 그릴지 여부를 지정 합니다.  
  
```  
void SetDrawFrame(BOOL bDraw=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bDraw`  
 `TRUE`포함 된 막대는; 주위에 프레임 영역을 표시 하려면 그렇지 않으면 `FALSE`합니다. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="setflatframe"></a>CMFCTabCtrl::SetFlatFrame  
 평면 또는 3D 프레임 탭 영역 주위에 그릴 것인지를 지정 합니다.  
  
```  
void SetFlatFrame(
    BOOL bFlat=TRUE,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bFlat`  
 `TRUE`탭 영역이; 주위 플랫 (2D) 프레임을 표시 하려면 `FALSE`&3; 차원 (3D) 프레임을 그리려면 합니다. 기본값은 `TRUE`입니다.  
  
 [in] `bRepaint`  
 `TRUE`창에 즉시 다시 그리게 그렇지 않으면 `FALSE`합니다. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="setimagelist"></a>CMFCTabCtrl::SetImageList  
 이미지 목록을 지정합니다.  
  
```  
virtual BOOL SetImageList(
    UINT uiID,  
    int cx=15,  
    COLORREF clrTransp=RGB(255, 0, 255));  
  
virtual BOOL SetImageList(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiID`  
 이미지 목록을 포함 하는 비트맵 리소스의 ID입니다.  
  
 [in] `cx`  
 픽셀 단위로 각 이미지의 너비입니다. 기본값은 15입니다.  
  
 [in] `clrTransp`  
 투명 한 이미지 색입니다. 이 색이 지정 된 이미지의 부품 투명 하 게 됩니다. 기본값은 색 자홍, RGB(255,0,255) 합니다.  
  
 [in] `hImageList`  
 미리 로드 된 이미지 목록에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드는 성공 하는 경우 `FALSE`탭 컨트롤의 평면 스타일을 사용 하 여 만들어집니다 또는 첫 번째 메서드 오버 로드로 지정 된 비트맵을 로드할 수 없는 경우는 `uiID` 매개 변수입니다.  
  
### <a name="remarks"></a>주의  
 탭 컨트롤에 대 한 이미지 목록 설정 하려면이 메서드를 사용 합니다. 이미지 목록에서 이미지 탭 레이블 옆에 표시 됩니다. 이 메서드는 탭 크기를 조정 이미지와 텍스트를 모두 포함할 수 있도록 탭 높이 다시 계산 합니다.  
  
 사용 하 여 [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) 표시할 이미지의 인덱스를 지정 하 고 탭 컨트롤에 상속 되는 메서드.  
  
##  <a name="setresizemode"></a>CMFCTabCtrl::SetResizeMode  
 다음 컨트롤을 다시 표시 되 고 현재 탭 컨트롤을 조정할 수 있는 방법을 지정 합니다.  
  
```  
void SetResizeMode(ResizeMode resizeMode);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `resizeMode`  
 중 하나는 `CMFCTabCtrl::ResizeMode` 탭 컨트롤을 조정할 수 있는 방법을 지정 하는 열거형 값입니다. 가능한 값 목록은 주의에 있는 표를 참조 하십시오.  
  
### <a name="remarks"></a>주의  
 `resizeMode` 매개 변수는 다음 중 하나일 수 `ResizeMode` 열거형 값입니다.  
  
|이름|설명|  
|----------|-----------------|  
|RESIZE_NO|탭 컨트롤의 크기를 조정할 수 없습니다.|  
|RESIZE_VERT|가로 변경 되지 않지만 세로로 탭 컨트롤을 조정할 수 있습니다.|  
|RESIZE_HORIZ|탭 컨트롤 가로로 하지만 하지 세로로 조정할 수 있습니다.|  
  
##  <a name="settabmaxwidth"></a>CMFCTabCtrl::SetTabMaxWidth  
 탭된 창에 최대 탭 너비를 지정합니다.  
  
```  
void SetTabMaxWidth(int nTabMaxWidth);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nTabMaxWidth`  
 최대 탭 너비 (픽셀)에서입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 탭된 창에 각 탭의 너비를 제한 합니다. 이 메서드는 탭에 매우 긴 레이블이 있는 경우에 유용 합니다. [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md) 클래스 생성자에서 최대 탭 너비를 0으로, 실제로 너비 제한 됨을 의미 합니다.  
  
##  <a name="stopresize"></a>CMFCTabCtrl::StopResize  
 탭 컨트롤의 현재 크기 조정 작업을 종료합니다.  
  
```  
void StopResize(BOOL bCancel);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bCancel`  
 `TRUE`현재 크기 조정 작업; 중단 `FALSE` 현재 크기 조정 작업을 완료 합니다. 두 경우 모두 프레임 워크는 크기 조정 직사각형을 그리기를 중지 합니다.  
  
##  <a name="synchronizescrollbar"></a>CMFCTabCtrl::SynchronizeScrollBar  
 플랫 탭을 표시 하는 탭 컨트롤에 가로 스크롤 막대를 그립니다.  
  
```  
BOOL SynchronizeScrollBar(SCROLLINFO* pScrollInfo = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `pScrollInfo`  
 에 대 한 포인터는 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) 구조 또는 `NULL`합니다. 이 메서드가 반환 하 고이 매개 변수가 없으면 `NULL`, 스크롤 막대의 모든 매개 변수를 포함 하는 구조입니다. 기본값은 `NULL`입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드가 성공 합니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 플랫 탭을 표시 하는 탭 컨트롤을 영향을 줍니다. 스크롤 막대를 동시에 모든 탭을 영향을 줍니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md)   
 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md)   
 [CMFCBaseTabCtrl 클래스](../../mfc/reference/cmfcbasetabctrl-class.md)

