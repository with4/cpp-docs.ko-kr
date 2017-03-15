---
title: "CBaseTabbedPane 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBaseTabbedPane
dev_langs:
- C++
helpviewer_keywords:
- CBaseTabbedPane class
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b72804dd8b2ca2253caff4cebf5b0631ae6040c6
ms.lasthandoff: 02/24/2017

---
# <a name="cbasetabbedpane-class"></a>CBaseTabbedPane 클래스
기능을 확장 된 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md) 탭 창 만들기를 지원 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CBaseTabbedPane : public CDockablePane  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CBaseTabbedPane::CBaseTabbedPane`|기본 생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CBaseTabbedPane::AddTab](#addtab)|탭된 창에 새 탭을 추가합니다.|  
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|가 빈 탭된 창을 소멸 될 수 있는지 여부를 지정 합니다.|  
|[CBaseTabbedPane::ApplyRestoredTabInfo](#applyrestoredtabinfo)|레지스트리에서 탭된 창에 로드 되는 탭 설정을 적용 합니다.|  
|[CBaseTabbedPane::CanFloat](#canfloat)|창에서 부동 상태로 있을 수 있는지 여부를 결정 합니다. (재정의 [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|  
|[CBaseTabbedPane::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|탭된 창 캡션의 활성 탭으로 동일한 텍스트를 표시할지 여부를 결정 합니다.|  
|[CBaseTabbedPane::ConvertToTabbedDocument](#converttotabbeddocument)|(재정의 [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).)|  
|[CBaseTabbedPane::DetachPane](#detachpane)|하나 이상의 도킹 가능한 창을 MDI 탭 문서로 변환합니다.|  
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|활성 탭에 있는 레이블 텍스트 캡션 텍스트를 동기화 하는 탭된 창의 기능을 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[CBaseTabbedPane::FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|내부 탭 순서를 기본 상태로 복원합니다.|  
|[CBaseTabbedPane::FindBarByTabNumber](#findbarbytabnumber)|탭은&0;부터 시작 하는 탭 인덱스에 의해 식별 될 때 탭에 있는 창을 반환 합니다.|  
|||  
|[CBaseTabbedPane::FindPaneByID](#findpanebyid)|창 ID로 식별 되는 창을 반환합니다|  
|[CBaseTabbedPane::FloatTab](#floattab)|창이 현재 분리 가능한 탭에 있는 경우에만 창을 부동합니다.|  
|[CBaseTabbedPane::GetDefaultTabsOrder](#getdefaulttabsorder)|창에서 탭의 기본 순서를 반환합니다.|  
|[CBaseTabbedPane::GetFirstVisibleTab](#getfirstvisibletab)|첫 번째 표시 된 탭에 대 한 포인터를 검색합니다.|  
|[CBaseTabbedPane::GetMinSize](#getminsize)|창 크기에 허용 되는 최소값을 검색 합니다. (재정의 [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|  
|[CBaseTabbedPane::GetPaneIcon](#getpaneicon)|창 아이콘에 대 한 핸들을 반환합니다. (재정의 [CBasePane::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon).)|  
|[CBaseTabbedPane::GetPaneList](#getpanelist)|탭된 창에 포함 된 창 목록을 반환 합니다.|  
|[CBaseTabbedPane::GetTabArea](#gettabarea)|위쪽 및 아래쪽 탭 영역에 대 한 경계 사각형을 반환합니다.|  
|[CBaseTabbedPane::GetTabsNum](#gettabsnum)|탭 창의 탭의 수를 반환 합니다.|  
|[CBaseTabbedPane::GetUnderlyingWindow](#getunderlyingwindow)|기본 (래핑된) 탭 창을 가져옵니다.|  
|[CBaseTabbedPane::GetVisibleTabsNum](#getvisibletabsnum)|표시 된 탭의 수를 반환 합니다.|  
|[CBaseTabbedPane::HasAutoHideMode](#hasautohidemode)|탭된 창에 자동 숨김 모드로 전환할 수 수 있는지 여부를 결정 합니다.|  
|[CBaseTabbedPane::IsHideSingleTab](#ishidesingletab)|탭된 창에 탭이 표시 되는지 숨겨지는지 여부를 결정 합니다.|  
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Serialization 도중에 내부적으로 사용 합니다.|  
|[CBaseTabbedPane::RecalcLayout](#recalclayout)|창에 대 한 레이아웃 정보를 다시 계산합니다. (재정의 [CPane::RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|  
|[CBaseTabbedPane::RemovePane](#removepane)|창이 탭된 창에서 제거합니다.|  
|`CBaseTabbedPane::SaveSiblingBarIDs`|Serialization 도중에 내부적으로 사용 합니다.|  
|`CBaseTabbedPane::Serialize`|(재정의 [CDockablePane::Serialize](http://msdn.microsoft.com/en-us/09787e59-e446-4e76-894b-206d303dcfd6).)|  
|`CBaseTabbedPane::SerializeTabWindow`|Serialization 도중에 내부적으로 사용 합니다.|  
|[CBaseTabbedPane::SetAutoDestroy](#setautodestroy)|탭된 컨트롤 막대를 자동으로 소멸 됩니다 여부를 결정 합니다.|  
|[CBaseTabbedPane::SetAutoHideMode](#setautohidemode)|도킹 창 사이 표시 설정/해제 하 고 자동 숨김 모드입니다. (재정의 [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode).)|  
|[CBaseTabbedPane::ShowTab](#showtab)|표시 하거나 탭을 숨깁니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 추상 클래스 이며 인스턴스화할 수 없습니다. 모든 종류의 탭된 창에 공통 되는 서비스를 구현 합니다.  
  
 라이브러리에서 두 개의 파생된 탭된 창 클래스를 포함 하는 현재: [CTabbedPane 클래스](../../mfc/reference/ctabbedpane-class.md) 및 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)합니다.  
  
 A `CBaseTabbedPane` 개체에 대 한 포인터를 래핑하는 [CMFCBaseTabCtrl 클래스](../../mfc/reference/cmfcbasetabctrl-class.md) 개체입니다. [CMFCBaseTabCtrl 클래스](../../mfc/reference/cmfcbasetabctrl-class.md) 탭 창의 자식 창 됩니다.  
  
 탭된 창을 만드는 방법에 대 한 자세한 내용은 참조 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md), [CTabbedPane 클래스](../../mfc/reference/ctabbedpane-class.md), 및 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 `CBaseTabbedPane`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxBaseTabbedPane.h  
  
##  <a name="a-nameaddtaba--cbasetabbedpaneaddtab"></a><a name="addtab"></a>CBaseTabbedPane::AddTab  
 탭된 창에 새 탭을 추가합니다.  
  
```  
virtual BOOL AddTab(
    CWnd* pNewBar,  
    BOOL bVisible = TRUE,  
    BOOL bSetActive = TRUE,  
    BOOL bDetachable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] [out]`pNewBar`  
 추가 하 고 창에 대 한 포인터입니다. 이 메서드를 호출한 후이 포인터는 잘못 될 수 있습니다. 자세한 내용은 설명 섹션을 참조하세요.  
  
 [in] `bVisible`  
 `TRUE`볼 수 있게 하려면 탭입니다. 그렇지 않으면 `FALSE`합니다.  
  
 [in] `bSetActive`  
 `TRUE`활성 탭;는 탭을 그렇지 않으면 `FALSE`합니다.  
  
 [in] `bDetachable`  
 `TRUE`분리 가능한 탭을 확인 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 탭으로 성공적으로 추가 되었는지 있고 없기 프로세스에서 삭제 합니다. `FALSE`추가 되 고 창 형식의 개체인 경우 `CBaseTabbedPane`합니다. 자세한 내용은 설명 섹션을 참조하세요.  
  
### <a name="remarks"></a>주의  
 창 탭된 창에 새 탭으로 추가 하려면이 메서드를 호출 합니다. 경우 `pNewBar` 형식의 개체를 가리키는 `CBaseTabbedPane`, 모든 탭 탭된 창에 복사 됩니다 차례로 `pNewBar` 소멸 됩니다. 따라서 `pNewBar` 잘못 된 포인터를 되 고 사용할 수 없습니다.  
  
##  <a name="a-nameallowdestroyemptytabbedpanea--cbasetabbedpaneallowdestroyemptytabbedpane"></a><a name="allowdestroyemptytabbedpane"></a>CBaseTabbedPane::AllowDestroyEmptyTabbedPane  
 가 빈 탭된 창을 소멸 될 수 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`탭 비어 있는 경우 창 소멸 될 수 있습니다. 그렇지 않으면 `FALSE`합니다. 기본 구현에서는 항상 반환 `TRUE`합니다.  
  
### <a name="remarks"></a>주의  
 가 빈 탭된 창을 소멸 되도록 허용 되지 않은 경우 프레임 워크 대신 창을 숨깁니다.  
  
##  <a name="a-nameapplyrestoredtabinfoa--cbasetabbedpaneapplyrestoredtabinfo"></a><a name="applyrestoredtabinfo"></a>CBaseTabbedPane::ApplyRestoredTabInfo  
 레지스트리에서 탭의 설정을 로드 하 고 탭된 창에 적용 합니다.  
  
```  
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bUseTabIndexes`  
 이 매개 변수는 프레임 워크에 의해 내부적으로 사용 됩니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 레지스트리에서 도킹 상태 정보를 다시 로드 하는 경우 프레임 워크에 의해 호출 됩니다. 메서드는 탭 순서 및 탭된 창에 대 한 탭 이름에 대 한 정보를 가져옵니다.  
  
##  <a name="a-namecanfloata--cbasetabbedpanecanfloat"></a><a name="canfloat"></a>CBaseTabbedPane::CanFloat  
 탭된 창 부동 상태로 있을 수 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 창에서 부동 상태로 있을 수 있습니다. 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-namecansetcaptiontexttotabnamea--cbasetabbedpanecansetcaptiontexttotabname"></a><a name="cansetcaptiontexttotabname"></a>CBaseTabbedPane::CanSetCaptionTextToTabName  
 탭된 창 캡션의 활성 탭으로 동일한 텍스트를 표시할지 여부를 결정 합니다.  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`탭 창의 캡션 텍스트의 활성 탭; 텍스트로 설정 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 텍스트에 표시할지 여부 탭된 창 캡션 중복 활성 탭의 레이블을 결정 하는 메서드를 사용 됩니다. 호출 하 여이 기능을 해제 하거나 설정할 수 있습니다 [CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)합니다.  
  
##  <a name="a-nameconverttotabbeddocumenta--cbasetabbedpaneconverttotabbeddocument"></a><a name="converttotabbeddocument"></a>CBaseTabbedPane::ConvertToTabbedDocument  
 하나 이상의 도킹 가능한 창을 MDI 탭 문서로 변환합니다.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bActiveTabOnly`  
 탭된 창으로 변환 하면 지정 `TRUE` 활성 탭만 변환 합니다. 지정 `FALSE` 창의 모든 탭을 변환할 수 있습니다.  
  
##  <a name="a-namedetachpanea--cbasetabbedpanedetachpane"></a><a name="detachpane"></a>CBaseTabbedPane::DetachPane  
 창이 탭된 창에서 분리합니다.  
  
```  
virtual BOOL DetachPane(
    CWnd* pBar,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 분리 하 고 창에 대 한 포인터입니다.  
  
 [in] `bHide`  
 분리 된 후 프레임 워크 창을 숨깁니다 있는지 여부를 지정 하는 부울 매개 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`프레임 워크는 창을;를 성공적으로 분리 하는 경우 `FALSE` 경우 `pBar` 는 `NULL` 하거나 참조 하는 탭된 창에 있지 않은 창입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 가능한 경우 분리 된 창을 배치 됩니다. 자세한 내용은 참조 [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat)합니다.  
  
##  <a name="a-nameenablesetcaptiontexttotabnamea--cbasetabbedpaneenablesetcaptiontexttotabname"></a><a name="enablesetcaptiontexttotabname"></a>CBaseTabbedPane::EnableSetCaptionTextToTabName  
 활성 탭에 있는 레이블 텍스트 캡션 텍스트를 동기화 하는 탭된 창의 기능을 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`활성 탭 캡션이; 탭된 창 캡션을 동기화 하려면 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-namefilldefaulttabsorderarraya--cbasetabbedpanefilldefaulttabsorderarray"></a><a name="filldefaulttabsorderarray"></a>CBaseTabbedPane::FillDefaultTabsOrderArray  
 내부 탭 순서를 기본 상태로 복원합니다.  
  
```  
void FillDefaultTabsOrderArray();
```  
  
### <a name="remarks"></a>주의  
 이 메서드는 프레임 워크를 초기 상태로 Outlook 표시줄을 복원 하는 경우 호출 됩니다.  
  
##  <a name="a-namefindpanebyida--cbasetabbedpanefindpanebyid"></a><a name="findpanebyid"></a>CBaseTabbedPane::FindPaneByID  
 창 ID로 식별 되는 창을 반환합니다  
  
```  
virtual CWnd* FindPaneByID(UINT uBarID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uBarID`  
 검색할 창 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 발견 창에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 창의 모든 탭을 비교 하 고로 지정 된 ID 가진 항목을 반환 하는이 메서드는 `uBarID` 매개 변수입니다.  
  
##  <a name="a-namefindbarbytabnumbera--cbasetabbedpanefindbarbytabnumber"></a><a name="findbarbytabnumber"></a>CBaseTabbedPane::FindBarByTabNumber  
 탭에 있는 창을 반환 합니다.  
  
```  
virtual CWnd* FindBarByTabNumber(
    int nTabNum,  
    BOOL bGetWrappedBar = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nTabNum`  
 검색 탭의&0;부터 시작 하는 인덱스를 지정 합니다.  
  
 [in] `bGetWrappedBar`  
 `TRUE`자체 창 대신 창의 기본 (래핑된) 창이 되돌리려면 그렇지 않으면 `FALSE`합니다. 이 창에서 파생에 적용 [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)합니다.  
  
### <a name="return-value"></a>반환 값  
 창 없는 경우 검색 되는 창에 대 한 유효한 포인터를 반환 됩니다. 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 호출 하 여 지정 된 탭에 있는 창에서 검색할는 `nTabNum` 매개 변수입니다.  
  
##  <a name="a-namefloattaba--cbasetabbedpanefloattab"></a><a name="floattab"></a>CBaseTabbedPane::FloatTab  
 창이 현재 분리 가능한 탭에 있는 경우에만 창을 부동합니다.  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] [out]`pBar`  
 Float로의 창에 대 한 포인터입니다.  
  
 [in] `nTabID`  
 Float로 탭의&0;부터 시작 인덱스를 지정합니다.  
  
 [in] `dockMethod`  
 창을 분리 하는 데 사용할 방법을 지정 합니다. 자세한 내용은 설명 섹션을 참조하세요.  
  
 [in] `bHide`  
 `TRUE`창을 부동; 전에 숨기려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 확장 되 면; 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 분리 가능한 탭에 있는 현재 창에 배치 하려면이 메서드를 호출 합니다.  
  
 창을 프로그래밍 방식으로 분리 하려면 지정 `DM_SHOW` 에 대 한는 `dockMethod` 매개 변수입니다. 이전에 떠 있는 동일한 위치에 있는 창 부동 소수점을 지정 하려는 경우 `DM_DBL_CLICK` 으로 `dockMethod` 매개 변수입니다.  
  
##  <a name="a-namegetdefaulttabsordera--cbasetabbedpanegetdefaulttabsorder"></a><a name="getdefaulttabsorder"></a>CBaseTabbedPane::GetDefaultTabsOrder  
 창에서 탭의 기본 순서를 반환합니다.  
  
```  
const CArray<int,int>& GetDefaultTabsOrder();
```  
  
### <a name="return-value"></a>반환 값  
 A `CArray` 창에서 탭의 기본 순서를 지정 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 Outlook 표시줄은 초기 상태로 다시 설정 하는 경우이 메서드를 호출 하는 프레임 워크입니다.  
  
##  <a name="a-namegetfirstvisibletaba--cbasetabbedpanegetfirstvisibletab"></a><a name="getfirstvisibletab"></a>CBaseTabbedPane::GetFirstVisibleTab  
 첫 번째 표시 된 탭에 대 한 포인터를 검색합니다.  
  
```  
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iTabNum`  
 정수에 대 한 참조입니다. 이 메서드 첫 번째 표시 된 탭의&0;부터 시작 하는 인덱스를 기록이 매개 변수를 그렇지 않으면-1 표시 선택 하지 않으면 탭이 발견 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우 첫 번째 표시 된 탭;에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
##  <a name="a-namegetminsizea--cbasetabbedpanegetminsize"></a><a name="getminsize"></a>CBaseTabbedPane::GetMinSize  
 창 크기에 허용 되는 최소값을 검색 합니다.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `size`  
 A `CSize` 크기가 허용 되는 최소값으로 채워진 개체입니다.  
  
### <a name="remarks"></a>주의  
 최소 창 크기의 일관 된 처리 중인 경우 ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), `size` 활성 탭에 대 한 크기에 허용 되는 최소값으로 채워집니다. 그렇지 않으면 `size` 의 반환 값으로 채워지는 [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize)합니다.  
  
##  <a name="a-namegetpaneicona--cbasetabbedpanegetpaneicon"></a><a name="getpaneicon"></a>CBaseTabbedPane::GetPaneIcon  
 창 크기에 허용 되는 최소값을 검색 합니다.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `size`  
 A `CSize` 크기가 허용 되는 최소값으로 채워진 개체입니다.  
  
### <a name="remarks"></a>주의  
 최소 창 크기의 일관 된 처리 중인 경우 ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), `size` 활성 탭에 대 한 크기에 허용 되는 최소값으로 채워집니다. 그렇지 않으면 `size` 의 반환 값으로 채워지는 [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize)합니다.  
  
##  <a name="a-namegetpanelista--cbasetabbedpanegetpanelist"></a><a name="getpanelist"></a>CBaseTabbedPane::GetPaneList  
 탭된 창에 포함 된 창 목록을 반환 합니다.  
  
```  
virtual void GetPaneList(
    CObList& lst,  
    CRuntimeClass* pRTCFilter = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `lst`  
 A `CObList` 하는 탭된 창에 포함 된 창이 채워집니다.  
  
 [in] `pRTCFilter`  
 없는 경우 `NULL`, 반환된 된 목록에 지정된 된 런타임 클래스를 가지는 창이 합니다.  
  
##  <a name="a-namegettabareaa--cbasetabbedpanegettabarea"></a><a name="gettabarea"></a>CBaseTabbedPane::GetTabArea  
 위쪽 및 아래쪽 탭 영역에 대 한 경계 사각형을 반환합니다.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const = 0;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `rectTabAreaTop`  
 위 탭 영역이의 화면 좌표를 받습니다.  
  
 [out] `rectTabAreaBottom`  
 아래 탭 영역의 화면 좌표를 받습니다.  
  
### <a name="remarks"></a>주의  
 화면 좌표로 상한 및 하 한 탭 영역에 대 한 경계 사각형을 확인 하려면이 메서드를 호출 합니다.  
  
##  <a name="a-namegettabsnuma--cbasetabbedpanegettabsnum"></a><a name="gettabsnum"></a>CBaseTabbedPane::GetTabsNum  
 탭 창의 탭의 수를 반환 합니다.  
  
```  
virtual int GetTabsNum() const;  
```  
  
### <a name="return-value"></a>반환 값  
 탭된 창에 탭의 수입니다.  
  
##  <a name="a-namegetunderlyingwindowa--cbasetabbedpanegetunderlyingwindow"></a><a name="getunderlyingwindow"></a>CBaseTabbedPane::GetUnderlyingWindow  
 기본 (래핑된) 탭 창을 가져옵니다.  
  
```  
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```  
  
### <a name="return-value"></a>반환 값  
 기본 탭 창에 대 한 포인터입니다.  
  
##  <a name="a-namegetvisibletabsnuma--cbasetabbedpanegetvisibletabsnum"></a><a name="getvisibletabsnum"></a>CBaseTabbedPane::GetVisibleTabsNum  
 표시 탭의 수를 반환 합니다.  
  
```  
virtual int GetVisibleTabsNum() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이&0; 보다 크거나 됩니다 표시 탭의 수입니다.  
  
### <a name="remarks"></a>주의  
 탭된 창에 표시 탭 수를 확인 하려면이 메서드를 호출 합니다.  
  
##  <a name="a-namehasautohidemodea--cbasetabbedpanehasautohidemode"></a><a name="hasautohidemode"></a>CBaseTabbedPane::HasAutoHideMode  
 탭 창을 자동 숨기기 모드로 전환할 수 있는지 여부를 결정합니다.  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창 자동 숨기기; 모드로 전환 될 수 있습니다 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 자동 숨기기 모드를 비활성화 한 경우 탭된 창 캡션에 없습니다 pin 단추가 표시 됩니다.  
  
##  <a name="a-nameishidesingletaba--cbasetabbedpaneishidesingletab"></a><a name="ishidesingletab"></a>CBaseTabbedPane::IsHideSingleTab  
 탭된 창에 탭이 표시 되는지 숨겨지는지 여부를 결정 합니다.  
  
```  
virtual BOOL IsHideSingleTab() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`표시 탭이 하나 뿐입니다; 없는 경우에 탭 창이 표시 되지 않는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 창에서 탭 하나만 열려 있기 때문에 표시 되지 않으면 탭된 창 제대로 작동 하는지 확인 하려면이 메서드를 호출할 수 있습니다.  
  
##  <a name="a-nameremovepanea--cbasetabbedpaneremovepane"></a><a name="removepane"></a>CBaseTabbedPane::RemovePane  
 창이 탭된 창에서 제거합니다.  
  
```  
virtual BOOL RemovePane(CWnd* pBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] [out]`pBar`  
 탭된 창에서 제거 하 고 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창에서 탭된 창에서 제거 되 고 탭된 창 여전히 유효 합니다. `FALSE`마지막 창 탭된 창에서 제거 되었습니다 고 탭된 창이 소멸 될 예정입니다. 반환 값이 `FALSE`, 탭된 창을 더 이상 사용 하지 마십시오.  
  
### <a name="remarks"></a>주의  
 지정 된 창에서 제거 하려면이 메서드를 호출 하는 `pBar` 탭된 창에서 매개 변수입니다.  
  
##  <a name="a-namesetautodestroya--cbasetabbedpanesetautodestroy"></a><a name="setautodestroy"></a>CBaseTabbedPane::SetAutoDestroy  
 탭된 컨트롤 막대를 자동으로 소멸 됩니다 여부를 결정 합니다.  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bAutoDestroy`  
 `TRUE`탭된 창이 동적으로 생성 하지; 수명을 제어 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 설정의 자동 소멸 모드를 `TRUE` 탭된 창을 동적으로 만드는 고 하지는 수명을 제어 하는 경우. 하는 경우 자동 소멸 모드는 `TRUE`, 탭된 창 프레임 워크에 의해 자동으로 소멸 됩니다.  
  
##  <a name="a-nameshowtaba--cbasetabbedpaneshowtab"></a><a name="showtab"></a>CBaseTabbedPane::ShowTab  
 표시 하거나 탭을 숨깁니다.  
  
```  
virtual BOOL ShowTab(
    CWnd* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
 표시 하거나 숨기려면 창에 대 한 포인터입니다.  
  
 [in] `bShow`  
 `TRUE`창을 표시 하려면 `FALSE` 창을 숨기려면 합니다.  
  
 [in] `bDelay`  
 `TRUE`탭 레이아웃; 조정 지연 그렇지 않으면 `FALSE`합니다.  
  
 [in] `bActivate`  
 `TRUE`활성 탭;는 탭을 그렇지 않으면 `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`탭 표시 또는 숨김 성공적으로 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 호출 하면 창을 표시 되거나 값에 따라 숨겨진는 `bShow` 매개 변수입니다. 탭을 숨기고 기본 탭 창의 마지막 표시 탭에는 탭된 창이 숨겨집니다. 표시 탭 이전에 경우에 탭을 표시 하는 경우에 탭된 창 표시 됩니다.  
  
##  <a name="a-namerecalclayouta--cbasetabbedpanerecalclayout"></a><a name="recalclayout"></a>CBaseTabbedPane::RecalcLayout  
 창에 대 한 레이아웃 정보를 다시 계산합니다.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>주의  
 창 부동 창인 경우이 메서드는 프레임 워크를 미니 프레임의 현재 크기를 창 크기 조정에 알립니다.  
  
 창에서 고정 되어 있는 경우이 메서드는 아무 작업도 수행 하지 않습니다.  
  
##  <a name="a-namesetautohidemodea--cbasetabbedpanesetautohidemode"></a><a name="setautohidemode"></a>CBaseTabbedPane::SetAutoHideMode  
 탭된 창에 분리 가능한 창에 대 한 자동 숨김 모드를 설정합니다.  
  
```  
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bMode`  
 `TRUE`자동 숨김 모드를 사용 하도록 설정 하려면 `FALSE` 일반 도킹 모드를 사용 하도록 합니다.  
  
 [in] `dwAlignment`  
 만들 되는 자동 숨기기 창 정렬을 지정 합니다. 가능한 값 목록은 참조 하십시오. [CPane::MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment)합니다.  
  
 [in] [out]`pCurrAutoHideBar`  
 현재 자동 숨김 도구 모음에 대 한 포인터입니다. 수 `NULL`합니다.  
  
 [in] `bUseTimer`  
 즉시 창을 숨기려면 또는 창에서 자동 숨김 모드로 전환할 때 자동 숨기기 효과 사용 하 여 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 자동 숨김 모드로 전환할 때 만들어지는 자동 숨김 도구 모음에 대 한 포인터 또는 `NULL` 없는 도구 모음을 만들면 됩니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 사용자가 탭된 창 자동 숨기기 모드로 일반 도킹 모드로 전환할 수 있는 핀 단추를 선택 하는 경우이 메서드를 호출 합니다.  
  
 탭된 창에 분리 가능한 각 창에 대 한 자동 숨김 모드로 설정 됩니다. 분리 가능한 비는 창에는 무시 됩니다. 자세한 내용은 참조 [CMFCBaseTabCtrl::EnableTabDetach](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach)합니다.  
  
 프로그래밍 방식으로 탭된 창 자동 숨기기 모드로 전환 하려면이 메서드를 호출 합니다. 창을 주 프레임 창에 도킹할 수 해야 ( [CDockablePane::GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider) 에 대 한 유효한 포인터를 반환 해야는 [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md)

