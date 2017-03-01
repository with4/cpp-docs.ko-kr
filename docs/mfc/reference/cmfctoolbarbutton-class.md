---
title: "CMFCToolBarButton 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarButton class
ms.assetid: 8a6ecffb-86b0-4f5c-8211-a9146b463efd
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
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 0139779cd00a514684c20b2c589d96247a532733
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarbutton-class"></a>CMFCToolBarButton 클래스
도구 모음 단추 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCToolBarButton : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarButton::CMFCToolBarButton](#cmfctoolbarbutton)|`CMFCToolBarButton` 개체를 생성하고 초기화합니다.|  
|`CMFCToolBarButton::~CMFCToolBarButton`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarButton::CanBeDropped](#canbedropped)|사용자 사용자 지정 하는 동안 도구 모음이 나 메뉴에 있는 단추를 배치할 수 있는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::CanBeStored](#canbestored)|단추를 저장할 수 있는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::CanBeStretched](#canbestretched)|사용자가 사용자 지정 하는 동안 단추를 늘릴 수 있는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::CompareWith](#comparewith)|이 인스턴스를 제공 된 `CMFCToolBarButton` 개체입니다.|  
|[CMFCToolBarButton::CopyFrom](#copyfrom)|현재 단추에 다른 도구 모음 단추의 속성을 복사합니다.|  
|[CMFCToolBarButton::CreateFromOleData](#createfromoledata)|만듭니다는 `CMFCToolBarButton` 개체에서 제공 된 `COleDataObject` 개체입니다.|  
|`CMFCToolBarButton::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|[CMFCToolBarButton::EnableWindow](#enablewindow)|마우스 및 키보드 입력을 사용하거나 사용하지 않도록 설정합니다.|  
|[CMFCToolBarButton::ExportToMenuButton](#exporttomenubutton)|도구 모음 단추를 클릭 하 여 메뉴에 텍스트를 복사 합니다.|  
|[CMFCToolBarButton::GetClipboardFormat](#getclipboardformat)|응용 프로그램에 대 한 전역 클립보드 형식을 검색합니다.|  
|[CMFCToolBarButton::GetHwnd](#gethwnd)|도구 모음 단추와 연결 된 창 핸들을 검색 합니다.|  
|[CMFCToolBarButton::GetImage](#getimage)|단추의 이미지 인덱스를 검색합니다.|  
|[CMFCToolBarButton::GetInvalidateRect](#getinvalidaterect)|다시 그려야 하는 단추의 클라이언트 영역의 영역을 검색 합니다.|  
|[CMFCToolBarButton::GetParentWnd](#getparentwnd)|단추의 부모 창을 검색합니다.|  
|[CMFCToolBarButton::GetProtectedCommands](#getprotectedcommands)|사용자를 사용자 지정할 수 있는 명령의 목록을 검색 합니다.|  
|[CMFCToolBarButton::GetTextSize](#gettextsize)|단추 텍스트의 크기를 검색 합니다.|  
|[CMFCToolBarButton::HasFocus](#hasfocus)|단추는 현재 입력된 포커스를가지고 있는지 여부를 결정 합니다.|  
|[CMFCToolBarButton::HaveHotBorder](#havehotborder)|사용자가 단추를 선택 단추의 테두리 표시 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsDrawImage](#isdrawimage)|이미지 단추에 표시 되는지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsDrawText](#isdrawtext)|단추 텍스트 레이블을 표시 되는지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsDroppedDown](#isdroppeddown)|단추는 하위 메뉴를 표시 하는지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsEditable](#iseditable)|단추를 사용자 지정할 수 있는지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsExtraSize](#isextrasize)|단추는 확장 된 테두리 함께 표시 될 수 있는지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsFirstInGroup](#isfirstingroup)|해당 단추 그룹의 첫 번째 위치에 있는 단추 인지 확인 합니다.|  
|[CMFCToolBarButton::IsHidden](#ishidden)|단추를 숨길지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsHorizontal](#ishorizontal)|가로 도구 모음 단추는 있는 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsLastInGroup](#islastingroup)|단추 단추 그룹의 마지막 위치에 있는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::IsLocked](#islocked)|잠긴 (비-사용자 지정 가능) 도구 모음 단추 인지 확인 합니다.|  
|[CMFCToolBarButton::IsOwnerOf](#isownerof)|단추는 제공 된 창 핸들의 소유자 인지 확인 합니다.|  
|[CMFCToolBarButton::IsVisible](#isvisible)|도구 모음 단추가 표시 되는지 여부를 결정 합니다.|  
|[CMFCToolBarButton::IsWindowVisible](#iswindowvisible)|단추의 내부 창 핸들이 표시 되는지 여부를 결정 합니다.|  
|[CMFCToolBarButton::NotifyCommand](#notifycommand)|단추를 처리 하는 여부를 지정 된 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 메시지입니다.|  
|[CMFCToolBarButton::OnAddToCustomizePage](#onaddtocustomizepage)|단추에 추가 되는 프레임 워크에서 호출 된 **사용자 지정** 대화 상자입니다.|  
|[CMFCToolBarButton::OnBeforeDrag](#onbeforedrag)|단추를 놓을 수 있는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::OnBeforeDrop](#onbeforedrop)|사용자를 대상 도구 모음 단추를 삭제할 수 있는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::OnCalculateSize](#oncalculatesize)|지정 된 장치 컨텍스트와 도킹 상태에 대 한 단추의 크기를 계산 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCToolBarButton::OnCancelMode](#oncancelmode)|처리 하는 프레임 워크에서 호출 된 [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) 메시지입니다.|  
|[CMFCToolBarButton::OnChangeParentWnd](#onchangeparentwnd)|새 도구 모음 단추를 삽입할 경우에 프레임 워크에서 호출 합니다.|  
|[CMFCToolBarButton::OnClick](#onclick)|사용자가 마우스 단추를 클릭할 때 프레임 워크에서 호출 합니다.|  
|[CMFCToolBarButton::OnClickUp](#onclickup)|마우스 단추를 놓을 때 프레임 워크에서 호출 합니다.|  
|[CMFCToolBarButton::OnContextHelp](#oncontexthelp)|부모 도구 모음에서 처리 하는 경우에 프레임 워크에서 호출 된 `WM_HELPHITTEST` 메시지입니다.|  
|[CMFCToolBarButton::OnCtlColor](#onctlcolor)|부모 도구 모음에서 처리 하는 경우에 프레임 워크에서 호출 된 `WM_CTLCOLOR` 메시지입니다.|  
|[CMFCToolBarButton::OnCustomizeMenu](#oncustomizemenu)|부모 도구 모음에서 응용 프로그램 바로 가기 메뉴를 표시 하는 경우 제공 된 메뉴를 수정 하려면 단추를 수 있습니다.|  
|[CMFCToolBarButton::OnDblClk](#ondblclk)|부모 도구 모음에서 처리 하는 경우에 프레임 워크에서 호출 된 [WM_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) 메시지입니다.|  
|[CMFCToolBarButton::OnDraw](#ondraw)|지정 된 스타일 및 옵션을 사용 하 여 단추를 그리기 위해 프레임 워크에서 호출 됩니다.|  
|[CMFCToolBarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|단추를 그리기 위해 프레임 워크에 의해 호출 된 **명령을** 의 창은 **사용자 지정** 대화 상자입니다.|  
|[CMFCToolBarButton::OnGetCustomToolTipText](#ongetcustomtooltiptext)|단추에 대 한 사용자 지정 도구 설명 텍스트를 검색 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCToolBarButton::OnGlobalFontsChanged](#onglobalfontschanged)|전역 글꼴 변경 된 경우에 프레임 워크에 의해 호출 됩니다.|  
|[CMFCToolBarButton::OnMove](#onmove)|부모 도구 모음에서 이동 하면 프레임 워크에 의해 호출 됩니다.|  
|[CMFCToolBarButton::OnShow](#onshow)|프레임 워크에 의해 때 호출 단추 수 표시 되거나 표시 되지 않습니다.|  
|[CMFCToolBarButton::OnSize](#onsize)|부모 도구 모음에서 변경 크기 또는 위치와 이러한 변경 단추 크기를 변경 하려면 필요한 경우는 프레임 워크에서 호출 합니다.|  
|[CMFCToolBarButton::OnToolHitTest](#ontoolhittest)|부모 도구 모음 단추의 경계 사각형에는 점이 인지 여부를 결정 해야 할 때에 프레임 워크에서 호출 합니다.|  
|[CMFCToolBarButton::OnUpdateToolTip](#onupdatetooltip)|부모 도구 모음에서 도구 설명 텍스트를 업데이트 하는 경우에 프레임 워크에서 호출 합니다.|  
|[CMFCToolBarButton::PrepareDrag](#preparedrag)|단추는 끌어서 놓기 작업을 수행 하려고 할 때에 프레임 워크에서 호출 합니다.|  
|[CMFCToolBarButton::Rect](#rect)|단추에 대 한 경계 사각형을 검색합니다.|  
|[CMFCToolBarButton::ResetImageToDefault](#resetimagetodefault)|단추와 연결 되는 이미지의 기본값을 설정 합니다.|  
|[CMFCToolBarButton::SaveBarState](#savebarstate)|도구 모음 단추의 상태를 저장합니다.|  
|[CMFCToolBarButton::Serialize](#serialize)|이 개체는 보관 파일에서 읽거나 보관 파일에 씁니다. (재정의 [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CMFCToolBarButton::SetACCData](#setaccdata)|제공 된 정보를 표시 `CAccessibilityData` 도구 모음 단추에서 내게 필요한 옵션 데이터는 개체입니다.|  
|[CMFCToolBarButton::SetClipboardFormatName](#setclipboardformatname)|전역 클립보드 형식을 이름을 바꿉니다.|  
|[CMFCToolBarButton::SetImage](#setimage)|단추의 이미지 인덱스를 설정합니다.|  
|[CMFCToolBarButton::SetProtectedCommands](#setprotectedcommands)|사용자를 사용자 지정할 수 있는 명령의 목록을 설정 합니다.|  
|[CMFCToolBarButton::SetRadio](#setradio)|단추의 선택된 상태가 변경 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCToolBarButton::SetRect](#setrect)|단추에 대 한 경계 사각형을 설정합니다.|  
|[CMFCToolBarButton::SetStyle](#setstyle)|단추 스타일을 설정합니다.|  
|[CMFCToolBarButton::SetVisible](#setvisible)|단추가 표시 되는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::Show](#show)|표시 하거나 단추를 숨깁니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarButton::m_bImage](#m_bimage)|이미지 단추에 표시 되는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::m_bText](#m_btext)|단추 텍스트 레이블을 표시 되는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::m_bTextBelow](#m_btextbelow)|단추 이미지 아래 텍스트 레이블을 표시 되는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::m_bUserButton](#m_buserbutton)|단추는 사용자 지정 이미지에 있는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::m_bWholeText](#m_bwholetext)|단추는 경계 사각형에 맞지 않을 경우에 전체 텍스트 레이블을 표시할지 여부를 지정 합니다.|  
|[CMFCToolBarButton::m_bWrap](#m_bwrap)|구분 기호 옆에 있는 단추 다음 행에 넣을 있는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::m_bWrapText](#m_bwraptext)|여러 줄 텍스트 레이블을 사용 되는지 여부를 지정 합니다.|  
|[CMFCToolBarButton::m_nID](#m_nid)|단추의 명령 ID입니다.|  
|[CMFCToolBarButton::m_nStyle](#m_nstyle)|단추 스타일입니다.|  
|[CMFCToolBarButton::m_strText](#m_strtext)|단추의 텍스트 레이블입니다.|  
  
## <a name="remarks"></a>주의  
 A `CMFCToolbarButton` 개체가 도구 모음에 있는 컨트롤입니다. 동작 하는 일반 단추 유사합니다. 이 개체에는 이미지와 텍스트 레이블을 할당할 수 있습니다. 도구 모음 단추의 명령 id입니다. 있을 수도 있습니다. 사용자가 도구 모음 단추를 클릭 하면 프레임 워크는이 ID를 지정 하는 명령을 실행 합니다.  
  
 일반적으로 도구 모음 단추 사용자 지정할 수 있습니다: 사용자 수, 다른 하나는 도구 모음에서 단추를 끌어서 및 복사, 붙여넣기, 삭제 및 텍스트 레이블 및 이미지를 편집 합니다. 사용자는 도구 모음 사용자 지정 되지 않도록 하려면 두 가지 방법 중 하나에 도구 모음을 잠글 수 있습니다. 집합 중 하나는 `bLocked` 플래그를 `TRUE` 호출 하는 경우 [CMFCToolBar::LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar), 개별 단추의 명령 ID를 사용 하 여 보호 된 명령의 전체 목록에 추가할는 [CMFCToolBarButton::SetProtectedCommands](#setprotectedcommands) 메서드.  
  
 `CMFCToolBarButton`응용 프로그램에서 도구 모음 이미지의 전역 컬렉션에서 이미지를 표시 하는 개체입니다. 이러한 컬렉션은 부모 도구 모음에서 유지 관리 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)합니다. 자세한 내용은 참조 [CMFCToolBarImages 클래스](../../mfc/reference/cmfctoolbarimages-class.md)합니다.  
  
 사용자가 도구 모음 단추를 클릭 하면 해당 부모 도구 모음에서 마우스 메시지를 처리 단추에 적절 한 조치를 통신 합니다. 부모 도구 모음에서 전송 단추에 유효한 명령 ID는 `WM_COMMAND` 메시지 부모 프레임입니다.  
  
 `CMFCToolBarButton` 클래스는 다른 도구 모음 단추 클래스에 대 한 기본 클래스와 같은 [CMFCToolBarMenuButton 클래스](../../mfc/reference/cmfctoolbarmenubutton-class.md), [CMFCToolBarEditBoxButton 클래스](../../mfc/reference/cmfctoolbareditboxbutton-class.md), 및 [CMFCToolBarComboBoxButton 클래스](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 구성 방법을 보여 줍니다.는 `CMFCToolBarButton` 의 다양 한 메서드를 사용 하 여 개체의 `CMFCToolBarButton` 클래스입니다. 예제에는 마우스를 사용 하도록 설정 하 고 키보드 입력, 단추 이미지 인덱스 설정 단추를의 경계 사각형을 설정한 단추를 보이게 하는 방법을 보여 줍니다. 이 코드 조각은의 일부인는 [탭 컨트롤 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_TabControl #&1;](../../mfc/reference/codesnippet/cpp/cmfctoolbarbutton-class_1.cpp)]  
[!code-cpp[NVC_MFC_TabControl #&2;](../../mfc/reference/codesnippet/cpp/cmfctoolbarbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtoolbarbutton.h  
  
##  <a name="a-namecanbedroppeda--cmfctoolbarbuttoncanbedropped"></a><a name="canbedropped"></a>CMFCToolBarButton::CanBeDropped  
 사용자 사용자 지정 하는 동안 도구 모음이 나 메뉴에 있는 단추를 배치할 수 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL CanBeDropped(CMFCToolBar* pToolbar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pToolbar`  
 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `TRUE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 기본적으로 도구 모음 단추를 놓을 수에 모든 사용자 지정 가능한 (즉, 잠겨 있지 않은) 도구 모음입니다.  
  
 이 메서드의 기본 구현에서는 반환 `TRUE`합니다. 이 메서드를 재정의 하 고 반환 `FALSE` 사용자가 단추 위치를 변경 하지 못하도록 하려는 경우.  
  
##  <a name="a-namecanbestoreda--cmfctoolbarbuttoncanbestored"></a><a name="canbestored"></a>CMFCToolBarButton::CanBeStored  
 단추를 저장할 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL CanBeStored() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `TRUE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 단추를 끌어서 놓기 작업에 참여할 수 있는지 여부를 결정 하는 프레임 워크입니다.  
  
 기본 구현은 `TRUE`를 반환합니다. 단추를 끌어서 놓기 작업의 일부로 저장할 수 없을 경우이 메서드를 재정의 합니다. 끌어서 놓기 작업에 대 한 자세한 내용은 참조 [끌어서 놓기 (OLE)](../../mfc/drag-and-drop-ole.md)합니다.  
  
##  <a name="a-namecanbestretcheda--cmfctoolbarbuttoncanbestretched"></a><a name="canbestretched"></a>CMFCToolBarButton::CanBeStretched  
 사용자가 사용자 지정 하는 동안 단추를 늘릴 수 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `FALSE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 사용자 지정 모드에 있는 단추를 확장할 수 있는지 여부를 결정 하는 프레임 워크에서 사용 됩니다.  
  
 이 메서드의 기본 구현에서는 반환 `FALSE`합니다. 이 메서드가 반환 하도록 재정의 `TRUE` 콤보 상자 또는 슬라이더와 같은 가변 너비 컨트롤에 대 한 합니다.  
  
 사용자 지정 모드에 대 한 자세한 내용은 참조 [CMFCToolBar::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode)합니다.  
  
##  <a name="a-namecmfctoolbarbuttona--cmfctoolbarbuttoncmfctoolbarbutton"></a><a name="cmfctoolbarbutton"></a>CMFCToolBarButton::CMFCToolBarButton  
 `CMFCToolBarButton` 개체를 생성하고 초기화합니다.  
  
```  
CMFCToolBarButton(
    UINT uiID,  
    int iImage,  
    LPCTSTR lpszText=NULL,  
    BOOL bUserButton=FALSE,  
    BOOL bLocked=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiID`  
 단추의 명령 ID입니다.  
  
 [in] `iImage`  
 이미지의 컬렉션의 단추 이미지 인덱스입니다.  
  
 [in] `lpszText`  
 단추의 텍스트 레이블입니다. 수 `NULL`합니다.  
  
 [in] `bUserButton`  
 사용자 지정 단추 인지를 결정 하는 부울 값입니다. 이 매개 변수가 `TRUE`, 단추는 사용자 정의 합니다. 그렇지 않으면, 단추 이미지 리소스에서 로드 됩니다.  
  
 [in] `bLocked`  
 단추를 사용자 지정할 수 있는지 여부를 결정 하는 부울 값입니다. 이 매개 변수가 `TRUE`, 단추를 사용자 지정할 수 없습니다. 그렇지 않으면 단추를 사용자 지정할 수 있습니다.  
  
##  <a name="a-namecomparewitha--cmfctoolbarbuttoncomparewith"></a><a name="comparewith"></a>CMFCToolBarButton::CompareWith  
 이 인스턴스를 제공 된 `CMFCToolBarButton` 개체입니다.  
  
```  
virtual BOOL CompareWith(const CMFCToolBarButton& other) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `other`  
 이 인스턴스와 비교할 개체에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 제공된 된 개체와이 인스턴스의; 값이 일치 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현에서는 제공된 된 개체의 명령 ID와이 인스턴스의 명령 ID를 같은지 여부를 결정 합니다. 이 메서드를 재정의 하 여 두 개의 지 여부를 결정 하는 추가 처리를 수행 해야 하는 경우 `CMFCToolBarButton` 개체는 동일 합니다.  
  
##  <a name="a-namecopyfroma--cmfctoolbarbuttoncopyfrom"></a><a name="copyfrom"></a>CMFCToolBarButton::CopyFrom  
 현재 단추에 다른 도구 모음 단추의 속성을 복사합니다.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `src`  
 복사할 소스 단추에 대 한 참조입니다.  
  
### <a name="remarks"></a>주의  
 이 도구 모음 단추를 도구 모음 단추 복사 하려면이 메서드를 호출 합니다.  
  
##  <a name="a-namecreatefromoledataa--cmfctoolbarbuttoncreatefromoledata"></a><a name="createfromoledata"></a>CMFCToolBarButton::CreateFromOleData  
 만듭니다는 `CMFCToolBarButton` 개체에서 제공 된 `COleDataObject` 개체입니다.  
  
```  
static CMFCToolBarButton* __stdcall CreateFromOleData(COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDataObject`  
 원본 OLE 데이터 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 만든 `CMFCToolBarButton` 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 다양 한 형식에서 데이터 전송을 수행 하는 프레임 워크에서 사용 됩니다. 예를 들어는 `CMFCOutlookBarPane::OnDragOver` 메서드가이 메서드를 사용 하 여 끌어서 놓기 작업을 수행 합니다.  
  
##  <a name="a-nameenablewindowa--cmfctoolbarbuttonenablewindow"></a><a name="enablewindow"></a>CMFCToolBarButton::EnableWindow  
 마우스 및 키보드 입력을 사용하거나 사용하지 않도록 설정합니다.  
  
```  
virtual void EnableWindow(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 이 매개 변수를 설정 `TRUE` 입력을 사용할 수 있도록 또는 `FALSE` 에 입력을 사용 하지 않도록 설정 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 호출의 `EnableWindow` 함수를 사용 하도록 설정 하거나 입력을 사용 하지 않도록 합니다. 자세한 내용은 참조 [EnableWindow](http://msdn.microsoft.com/library/windows/desktop/ms646291) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameexporttomenubuttona--cmfctoolbarbuttonexporttomenubutton"></a><a name="exporttomenubutton"></a>CMFCToolBarButton::ExportToMenuButton  
 도구 모음 단추를 클릭 하 여 메뉴에 텍스트를 복사 합니다.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `menuButton`  
 대상 메뉴 단추에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `TRUE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크 메뉴 단추를 도구 모음 단추에서 텍스트를 복사 하려면이 메서드를 호출 합니다. 기본 구현은 단추의 텍스트 레이블을 복사합니다. 텍스트 레이블을 비어 있으면이 메서드는 단추의 도구 설명 텍스트를 복사 합니다.  
  
 이 메서드의 기본 구현에서는 반환 `TRUE`합니다. 프레임 워크에서 파생 된 개체를 변환 하는 경우 추가 작업을 수행 하려는 경우이 메서드를 재정의 [CMFCToolbarButton](../../mfc/reference/cmfctoolbarbutton-class.md) 메뉴 단추에 있습니다.  
  
##  <a name="a-namegetclipboardformata--cmfctoolbarbuttongetclipboardformat"></a><a name="getclipboardformat"></a>CMFCToolBarButton::GetClipboardFormat  
 응용 프로그램에 대 한 전역 클립보드 형식을 검색합니다.  
  
```  
static CLIPFORMAT __stdcall GetClipboardFormat();
```  
  
### <a name="return-value"></a>반환 값  
 전역 `CLIPFORMAT` 응용 프로그램에 대 한 값입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 OLE 데이터 전송 작업에 대 한 클립보드 형식을 검색 하려면이 메서드를 호출 합니다. 예를 들어는 [CMFCToolBarButton::CreateFromOleData](#createfromoledata) 메서드가이 메서드를 사용 하 여 소스 OLE 데이터 개체에서 데이터를 복사 합니다.  
  
 이 메서드는 전역 설정 `CLIPFORMAT` 처음으로이 메서드는 값입니다. 모든 후속 호출에이 메서드는이 값을 반환 합니다.  
  
 끌어서 놓기 작업이 응용 프로그램 간에 발생할 수 있도록 호출의 [CMFCToolBarButton::SetClipboardFormatName](#setclipboardformatname) 메서드.  
  
 MFC에서 클립보드에 대 한 자세한 내용은 참조 [클립보드](../../mfc/clipboard.md)합니다.  
  
##  <a name="a-namegethwnda--cmfctoolbarbuttongethwnd"></a><a name="gethwnd"></a>CMFCToolBarButton::GetHwnd  
 도구 모음 단추와 연결 된 창 핸들을 검색 합니다.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>반환 값  
 도구 모음 단추와 연결 된 창 핸들 또는 `NULL` 도구 모음 단추에 연결 된 창 핸들이 없습니다.  
  
### <a name="remarks"></a>주의  
 이 메서드의 기본 구현에서는 반환 `NULL`합니다. 특정 컨트롤의 창 핸들을 반환 하려면이 메서드를 재정의 합니다.  
  
##  <a name="a-namegetimagea--cmfctoolbarbuttongetimage"></a><a name="getimage"></a>CMFCToolBarButton::GetImage  
 단추의 이미지 인덱스를 검색합니다.  
  
```  
int GetImage() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 단추와 연결 된 이미지의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 단추에 사용자 지정 이미지를 사용 하는 경우 (즉, `bUserButton` 가 `TRUE` 생성자에서), 사용자 지정 이미지의 컬렉션에서 이미지를 지정 하는 반환 된 인덱스 (참조 [CMFCToolBar::GetUserImages](../../mfc/reference/cmfctoolbar-class.md#getuserimages)). 인덱스를 리소스 파일에서 로드 되는 이미지의 컬렉션에서 이미지를 지정 하는 그렇지 않은 경우 (참조 [CMFCToolBar::GetImages](../../mfc/reference/cmfctoolbar-class.md#getimages)). 리소스 파일에 대 한 자세한 내용은 참조 [리소스 파일에 대해 작업](../../windows/working-with-resource-files.md)합니다.  
  
##  <a name="a-namegetinvalidaterecta--cmfctoolbarbuttongetinvalidaterect"></a><a name="getinvalidaterect"></a>CMFCToolBarButton::GetInvalidateRect  
 다시 그려야 하는 단추의 클라이언트 영역의 영역을 검색 합니다.  
  
```  
virtual const CRect GetInvalidateRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `CRect` 다시 그려야 하는 지역을 지정 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드의 기본 구현은 전체 클라이언트 영역을 반환 합니다. 다시 그릴 다른 영역을 사용 하려는 경우이 메서드를 재정의 합니다.  
  
##  <a name="a-namegetparentwnda--cmfctoolbarbuttongetparentwnd"></a><a name="getparentwnd"></a>CMFCToolBarButton::GetParentWnd  
 단추의 부모 창을 검색합니다.  
  
```  
CWnd* GetParentWnd() const;  
```  
  
### <a name="return-value"></a>반환 값  
 단추의 부모 창입니다.  
  
##  <a name="a-namegetprotectedcommandsa--cmfctoolbarbuttongetprotectedcommands"></a><a name="getprotectedcommands"></a>CMFCToolBarButton::GetProtectedCommands  
 사용자를 사용자 지정할 수 있는 명령의 목록을 검색 합니다.  
  
```  
static const CList<UINT,UINT>& GetProtectedCommands();
```  
  
### <a name="return-value"></a>반환 값  
 보호 된 명령 목록입니다.  
  
### <a name="remarks"></a>주의  
 사용자 지정 모드는 프레임 워크는 보호 되는 도구 모음 단추 명령을 해제 합니다. 사용자는 끌어서 놓기 수행 하 고 사용할 수 없는 도구 모음 단추에 대 한 작업을 편집할 수 없습니다.  
  
 사용 된 [CMFCToolBarButton::SetProtectedCommands](#setprotectedcommands) 의 목록을 정의 하는 메서드는 명령을 보호 합니다.  
  
##  <a name="a-namegettextsizea--cmfctoolbarbuttongettextsize"></a><a name="gettextsize"></a>CMFCToolBarButton::GetTextSize  
 단추 텍스트의 크기를 검색 합니다.  
  
```  
SIZE GetTextSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `SIZE` 단추 텍스트를 픽셀 단위로 크기를 포함 하는 개체입니다.  
  
##  <a name="a-namehasfocusa--cmfctoolbarbuttonhasfocus"></a><a name="hasfocus"></a>CMFCToolBarButton::HasFocus  
 단추는 현재 입력된 포커스를가지고 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>반환 값  
 단추에 입력된 포커스가; 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드의 기본 구현은 없으면&0;이 아닌 입력된 포커스를가지고 단추나는 자식 또는 하위 항목 창에 입력된 포커스가 있는 창입니다. 이 동작을 사용자 지정 하려면이 함수를 재정의할 수 있습니다.  
  
##  <a name="a-namehavehotbordera--cmfctoolbarbuttonhavehotborder"></a><a name="havehotborder"></a>CMFCToolBarButton::HaveHotBorder  
 사용자가 단추를 선택 단추의 테두리 표시 여부를 결정 합니다.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `TRUE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 사용자가 선택할 때 도구 모음 단추에서 테두리를 표시 되는지 여부를 확인 하려면이 메서드를 호출 합니다.  
  
 기본 구현은 `TRUE`를 반환합니다. 이 동작을 사용자 지정 하려면이 메서드를 재정의할 수 있습니다.  
  
##  <a name="a-nameisdrawimagea--cmfctoolbarbuttonisdrawimage"></a><a name="isdrawimage"></a>CMFCToolBarButton::IsDrawImage  
 이미지 단추에 표시 되는지 여부를 결정 합니다.  
  
```  
BOOL IsDrawImage() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이미지 단추;에 표시 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드가 반환 `FALSE` 경우 도구 모음 단추에 연결 된 이미지가 없습니다 ( [CMFCToolBarButton::GetImage](#getimage) -1을 반환) 또는 [CMFCToolBarButton::m_bImage](#m_bimage) 로 설정 된 `FALSE`합니다.  
  
##  <a name="a-nameisdrawtexta--cmfctoolbarbuttonisdrawtext"></a><a name="isdrawtext"></a>CMFCToolBarButton::IsDrawText  
 단추 텍스트 레이블을 표시 되는지 여부를 결정 합니다.  
  
```  
BOOL IsDrawText() const;  
```  
  
### <a name="return-value"></a>반환 값  
 텍스트 레이블이 표시 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드가 반환 `FALSE` 도구 모음 단추에 연결 된 텍스트 레이블이 없는 경우 ( [CMFCToolBarButton::m_strText](#m_strtext) 비어) 또는 [CMFCToolBarButton::m_bText](#m_btext) 로 설정 된 `FALSE`합니다.  
  
##  <a name="a-nameisdroppeddowna--cmfctoolbarbuttonisdroppeddown"></a><a name="isdroppeddown"></a>CMFCToolBarButton::IsDroppedDown  
 단추는 하위 메뉴를 표시 하는지 여부를 결정 합니다.  
  
```  
virtual BOOL IsDroppedDown() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `FALSE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드의 기본 구현에서는 반환 `FALSE`합니다. 이 메서드가 반환 하도록 재정의 `TRUE` 컨트롤 하위 메뉴를 표시 하는 경우.  
  
##  <a name="a-nameiseditablea--cmfctoolbarbuttoniseditable"></a><a name="iseditable"></a>CMFCToolBarButton::IsEditable  
 단추를 사용자 지정할 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL IsEditable() const;  
```  
  
### <a name="return-value"></a>반환 값  
 사용자가 단추를 사용자 지정할 수 있습니다 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 끌어서 놓기 사용 하 여 도구 모음 단추를 사용자 지정 하거나 작업을 편집할 수 있는지 여부를 확인 하려면이 메서드를 호출 합니다.  
  
 기본 구현에서는 반환 `FALSE` 단추의 명령 ID가 표준 명령 (호출 하 여이 확인할 수 있습니다는 `IsStandardCommand` 함수) 되거나 ID 목록에는 명령 명령을 보호 합니다. 보호 된 명령에 대 한 자세한 내용은 참조 [CMFCToolBarButton::GetProtectedCommands](#getprotectedcommands) 및 [CMFCToolBarButton::SetProtectedCommands](#setprotectedcommands)합니다.  
  
 해당 동작을 사용자 지정 하려면이 메서드를 재정의 합니다.  
  
##  <a name="a-nameisextrasizea--cmfctoolbarbuttonisextrasize"></a><a name="isextrasize"></a>CMFCToolBarButton::IsExtraSize  
 단추는 확장 된 테두리 함께 표시 될 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL IsExtraSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 확장 된 테두리; 도구 모음 단추를 표시할 수 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 여러 개의 스킨 테두리 도구 모음 단추 (예를 들어 원형 단추)에 대 한 추가 크기를 사용합니다.  
  
 프레임 워크를 호출 하는 경우이 단추 도구 모음에서 다른 위치로 이동 하는 사용자는 [CMFCToolBarButton::OnChangeParentWnd](#onchangeparentwnd) 메서드. [CMFCToolBarButton::OnChangeParentWnd](#onchangeparentwnd) 메서드를 새 부모 도구 모음에서의 추가 크기 플래그를 설정 합니다 (자세한 내용은 참조 [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable)).  
  
##  <a name="a-nameisfirstingroupa--cmfctoolbarbuttonisfirstingroup"></a><a name="isfirstingroup"></a>CMFCToolBarButton::IsFirstInGroup  
 해당 단추 그룹의 첫 번째 위치에 있는 단추 인지 확인 합니다.  
  
```  
virtual BOOL IsFirstInGroup() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`해당 단추 그룹;에 있는 첫 번째 단추의 경우 단추 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 정의 *단추 그룹* 으로 인접 단추 집합을 같은 행에 위치 하는 구분 기호 또는 테두리 도구 모음에 의해 제한 됩니다. 이 메서드가 반환 `FALSE` 도구 모음 단추에서 참조 하는 경우는 **사용자 지정** 단추입니다. 에 대 한 자세한 내용은 **사용자 지정** 단추, 참조 [CMFCToolBar::GetCustomizeButton](../../mfc/reference/cmfctoolbar-class.md#getcustomizebutton)합니다.  
  
 호출의 [CMFCToolBarButton::IsLastInGroup](#islastingroup) 메서드 단추 그룹의 마지막 위치에 있는 단추 인지 여부를 확인 합니다.  
  
##  <a name="a-nameishiddena--cmfctoolbarbuttonishidden"></a><a name="ishidden"></a>CMFCToolBarButton::IsHidden  
 단추를 숨길지 여부를 결정 합니다.  
  
```  
BOOL IsHidden() const;  
```  
  
### <a name="return-value"></a>반환 값  
 단추 (보이지 않음); 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 부모 도구 모음에서 도구 모음 단추가 표시 되는지 확인 하려면 확장 하는 경우이 메서드를 호출 하는 프레임 워크입니다.  
  
 사용 하 여 표시 되지 않도록 하려면 단추를 설정 하는 경우는 [CMFCToolBarButton::SetVisible](#setvisible) 메서드를 사용 하 여 [CMFCToolBarButton::IsVisible](#isvisible) 도구 모음 단추가 표시 되는지 확인 하려면.  
  
 기본적으로 모든 도구 모음 단추가 표시 됩니다. 사용 된 [CMFCToolBarButton::Show](#show) 메서드를 숨기 거 나 도구 모음 단추를 표시 합니다.  
  
##  <a name="a-nameishorizontala--cmfctoolbarbuttonishorizontal"></a><a name="ishorizontal"></a>CMFCToolBarButton::IsHorizontal  
 가로 도구 모음 단추는 있는 여부를 결정 합니다.  
  
```  
BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>반환 값  
 도구 모음 단추의 가로 도구 모음;에 있는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크 도구 모음 단추의 레이아웃을 결정 하려면이 메서드를 호출 합니다.  
  
 이 메서드는 반환 된 `m_bHorz` 데이터 멤버입니다. 기본값은 `m_bHorz` 데이터 멤버는 `TRUE`;를 호출할 때마다 다시 설정 되는 [CMFCToolBarButton::OnDraw](#ondraw) 메서드.  
  
##  <a name="a-nameislastingroupa--cmfctoolbarbuttonislastingroup"></a><a name="islastingroup"></a>CMFCToolBarButton::IsLastInGroup  
 단추 단추 그룹의 마지막 위치에 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL IsLastInGroup() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`단추를 해당 단추 그룹;의 마지막 단추 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 정의 *단추 그룹* 인접가 같은 행에 위치 하 고 구분 기호 또는 테두리 도구 모음에 의해 제한 되는 단추 집합으로이 메서드는 다음과 같이 반환 됩니다. `FALSE` 도구 모음 단추에는 부모 도구 모음 없음 또는 도구 모음 단추를 참조 하는 경우는 **사용자 지정** 단추입니다. 에 대 한 자세한 내용은 **사용자 지정** 단추, 참조 [CMFCToolBar::GetCustomizeButton](../../mfc/reference/cmfctoolbar-class.md#getcustomizebutton)합니다.  
  
 호출의 [CMFCToolBarButton::IsFirstInGroup](#isfirstingroup) 메서드 단추 그룹의 첫 번째 위치에 있는 단추 인지 여부를 확인 합니다.  
  
##  <a name="a-nameislockeda--cmfctoolbarbuttonislocked"></a><a name="islocked"></a>CMFCToolBarButton::IsLocked  
 잠긴 (비-사용자 지정 가능) 도구 모음 단추 인지 확인 합니다.  
  
```  
BOOL IsLocked() const;  
```  
  
### <a name="return-value"></a>반환 값  
 단추, 잠긴된 도구 모음에 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 끌어서 놓기 사용 하 여 도구 모음 단추를 사용자 지정 하거나 작업을 편집할 수 있는지 여부를 확인 하려면이 메서드를 호출 합니다. 잠긴된 특성을 사용 하 여 부모 도구 모음에서 설정 된 [CMFCToolBar::LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar) 메서드. 각 도구 모음 단추의 생성자에이 특성의 값을 전달 하는 프레임 워크 ( [CMFCToolbarButton](../../mfc/reference/cmfctoolbarbutton-class.md)) 부모 도구 모음에 삽입 하는 것입니다.  
  
##  <a name="a-nameisownerofa--cmfctoolbarbuttonisownerof"></a><a name="isownerof"></a>CMFCToolBarButton::IsOwnerOf  
 단추는 제공 된 창 핸들의 소유자 인지 확인 합니다.  
  
```  
virtual BOOL IsOwnerOf(HWND hwnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hwnd`  
 창 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 단추는 제공 된 창 핸들;의 소유자 인 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드가&0;이 아닌 경우 반환 `hwnd` 직접 창 핸들을 참조 하거나 자식 단추와 연결 된 창 핸들입니다. 이 메서드는 경우 0을 반환 `hwnd` 는 `NULL`합니다.  
  
##  <a name="a-nameisvisiblea--cmfctoolbarbuttonisvisible"></a><a name="isvisible"></a>CMFCToolBarButton::IsVisible  
 도구 모음 단추가 표시 되는지 여부를 결정 합니다.  
  
```  
BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>반환 값  
 도구 모음 단추가 표시 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 표시 하거나 도구 모음 단추를 사용 하 여 숨길 수는 [CMFCToolBarButton::SetVisible](#setvisible) 메서드. 호출 된 [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate) 메서드를 호출한 후 부모 도구 모음에서 [CMFCToolBarButton::SetVisible](#setvisible) 를 부모 도구 모음에서 레이아웃을 다시 계산 합니다.  
  
##  <a name="a-nameiswindowvisiblea--cmfctoolbarbuttoniswindowvisible"></a><a name="iswindowvisible"></a>CMFCToolBarButton::IsWindowVisible  
 단추의 내부 창 핸들이 표시 되는지 여부를 결정 합니다.  
  
```  
virtual BOOL IsWindowVisible();
```  
  
### <a name="return-value"></a>반환 값  
 단추의 내부 창 핸들이 표시 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 기본 창 핸들의 스타일 특성을 포함 하는 경우&0;이 아닌 반환는 `WS_VISIBLE` 스타일입니다. 이 메서드가 반환 `FALSE` 단추의 내부 창 핸들이 `NULL`합니다.  
  
##  <a name="a-namembimagea--cmfctoolbarbuttonmbimage"></a><a name="m_bimage"></a>CMFCToolBarButton::m_bImage  
 이미지 단추에 표시 되는지 여부를 지정 합니다.  
  
```  
BOOL m_bImage;  
```  
  
### <a name="remarks"></a>주의  
 이 데이터 멤버 설정 된 경우 `TRUE`, 프레임 워크 도구 모음 단추와 연결 된 이미지를 표시 하며 그렇지 않으면 프레임 워크 이미지가 표시 되지 않습니다. 이 멤버의 반환 값에 영향을 줍니다는 [CMFCToolBarButton::m_bImage](#m_bimage) 메서드.  
  
##  <a name="a-namembtexta--cmfctoolbarbuttonmbtext"></a><a name="m_btext"></a>CMFCToolBarButton::m_bText  
 단추 텍스트 레이블을 표시 되는지 여부를 지정 합니다.  
  
```  
BOOL m_bText;  
```  
  
### <a name="remarks"></a>주의  
 이 데이터 멤버 설정 된 경우 `TRUE`, 프레임 워크에는 도구 모음 단추의 텍스트 레이블이 표시 됩니다; 그렇지 않으면 프레임 워크 텍스트 레이블을 표시 하지 않습니다. 이 멤버의 반환 값에 영향을 줍니다는 [CMFCToolBarButton::m_bText](#m_btext) 메서드.  
  
##  <a name="a-namembtextbelowa--cmfctoolbarbuttonmbtextbelow"></a><a name="m_btextbelow"></a>CMFCToolBarButton::m_bTextBelow  
 단추 이미지 아래 텍스트 레이블을 표시 되는지 여부를 지정 합니다.  
  
```  
BOOL m_bTextBelow;  
```  
  
### <a name="remarks"></a>주의  
 이 멤버 변수로 설정 된 경우 `TRUE`, 프레임 워크가 이미지 아래에 있는 단추의 텍스트를 표시 합니다. 이 멤버의 기본값은 `FALSE`합니다.  
  
##  <a name="a-namembuserbuttona--cmfctoolbarbuttonmbuserbutton"></a><a name="m_buserbutton"></a>CMFCToolBarButton::m_bUserButton  
 단추는 사용자 지정 이미지에 있는지 여부를 지정 합니다.  
  
```  
BOOL m_bUserButton;  
```  
  
### <a name="remarks"></a>주의  
 이 데이터 멤버가로 설정 된 `TRUE` 때 단추에 연결 된 사용자 지정 이미지가 있습니다.  
  
##  <a name="a-namembwholetexta--cmfctoolbarbuttonmbwholetext"></a><a name="m_bwholetext"></a>CMFCToolBarButton::m_bWholeText  
 단추는 경계 사각형에 맞지 않을 경우에 전체 텍스트 레이블을 표시할지 여부를 지정 합니다.  
  
```  
BOOL m_bWholeText;  
```  
  
### <a name="remarks"></a>주의  
 이 데이터 멤버 설정 된 경우 `TRUE`, 프레임 워크는 단추를 확대 하 여 전체 텍스트 레이블을 표시 합니다. 프레임 워크 잘라서는 줄임표 (...)를 추가 합니다. 그렇지 않으면 ( **... **) 텍스트 레이블에 합니다.  
  
##  <a name="a-namembwrapa--cmfctoolbarbuttonmbwrap"></a><a name="m_bwrap"></a>CMFCToolBarButton::m_bWrap  
 구분 기호 옆에 있는 단추 다음 행에 넣을 있는지 여부를 지정 합니다.  
  
```  
BOOL m_bWrap;  
```  
  
### <a name="remarks"></a>주의  
 이 데이터 멤버 설정 하는 프레임 워크 `TRUE` 하거나 레이아웃 (예를 들어 한 특정 개수의 행 마다 도구 모음 단추)를 지정 하는 경우 현재 행에 있는 도구 모음 단추 맞지 않는 경우.  
  
 이 데이터 멤버가로 설정 된 경우 다음 행에서이 단추는 프레임 워크 배치 `TRUE` 가로로 도킹 또는 부동 도구 모음을 하 고 있습니다.  
  
 이 데이터 멤버의 기본값은 `FALSE`합니다.  
  
##  <a name="a-namembwraptexta--cmfctoolbarbuttonmbwraptext"></a><a name="m_bwraptext"></a>CMFCToolBarButton::m_bWrapText  
 여러 줄 텍스트 레이블을 사용 되는지 여부를 지정 합니다.  
  
```  
AFX_IMPORT_DATA static BOOL m_bWrapText;  
```  
  
### <a name="remarks"></a>주의  
 이 정적 멤버 변수가 `TRUE`, 프레임 워크 도구 모음 단추에 여러 줄 텍스트 레이블을 표시 하려면 도구 모음을 모두 사용 합니다.  
  
 이 데이터 멤버의 기본값은 `FALSE`합니다.  
  
##  <a name="a-namemnida--cmfctoolbarbuttonmnid"></a><a name="m_nid"></a>CMFCToolBarButton::m_nID  
 단추의 명령 ID입니다.  
  
```  
UINT m_nID;  
```  
  
### <a name="remarks"></a>주의  
 -1의 명령 ID 단추는 구분을 나타냅니다. 모든 단추 구분 기호는는 `TBBS_SEPARATOR` 스타일입니다. 참조 [CMFCToolBarButton::m_nStyle](#m_nstyle) 단추 스타일에 대 한 자세한 내용은 합니다.  
  
##  <a name="a-namemnstylea--cmfctoolbarbuttonmnstyle"></a><a name="m_nstyle"></a>CMFCToolBarButton::m_nStyle  
 단추 스타일입니다.  
  
```  
UINT m_nStyle;  
```  
  
### <a name="remarks"></a>주의  
 참조 [ToolBar 컨트롤 스타일](../../mfc/reference/toolbar-control-styles.md) 목록은 사용 가능한 도구 모음 단추 스타일입니다.  
  
##  <a name="a-namemstrtexta--cmfctoolbarbuttonmstrtext"></a><a name="m_strtext"></a>CMFCToolBarButton::m_strText  
 단추의 텍스트 레이블입니다.  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>주의  
 이 데이터 멤버에는 단추의 텍스트 레이블을 포함합니다. 텍스트 레이블을 비어 있을 수 있습니다.  
  
##  <a name="a-namenotifycommanda--cmfctoolbarbuttonnotifycommand"></a><a name="notifycommand"></a>CMFCToolBarButton::NotifyCommand  
 단추를 처리 하는 여부를 지정 된 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 메시지입니다.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iNotifyCode`  
 명령과 사용 하 여 연결 된 알림 메시지입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `FALSE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크 보내려는 경우이 메서드를 호출을 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 메시지를 부모 창입니다.  
  
 기본적으로이 메서드는 다음과 같이 반환 됩니다. `FALSE`합니다. 반환 하려면이 메서드를 재정의 `TRUE` 처리 하려는 경우는 `WM_COMMAND` 메시지 또는 `FALSE` 부모 도구 모음에서 메시지를 처리 해야 함을 나타냅니다.  
  
##  <a name="a-nameonaddtocustomizepagea--cmfctoolbarbuttononaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBarButton::OnAddToCustomizePage  
 단추에 추가 되는 프레임 워크에서 호출 된 **사용자 지정** 대화 상자입니다.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>주의  
 이 메서드의 기본 구현은 아무 작업도 수행합니다. 단추에 추가 될 때 어떤 작업을 수행 하려는 경우이 메서드를 재정의 하는 **사용자 지정** 대화 상자입니다.  
  
##  <a name="a-nameonbeforedraga--cmfctoolbarbuttononbeforedrag"></a><a name="onbeforedrag"></a>CMFCToolBarButton::OnBeforeDrag  
 단추를 놓을 수 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL OnBeforeDrag() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이면 단추를 끌 수 있습니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 사용자가 단추를 끌기 시작 하기 전에이 메서드를 호출 합니다.  
  
 이 메서드의 기본 구현에서는 반환 `TRUE`합니다. 이 메서드가 반환 하도록 재정의 `FALSE` 단추 끌기를 사용 하지 않으려면 합니다.  
  
##  <a name="a-nameonbeforedropa--cmfctoolbarbuttononbeforedrop"></a><a name="onbeforedrop"></a>CMFCToolBarButton::OnBeforeDrop  
 사용자를 대상 도구 모음 단추를 삭제할 수 있는지 여부를 지정 합니다.  
  
```  
virtual BOOL OnBeforeDrop(CMFCToolBar* pTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pTarget`  
 끌어서 놓기 작업의 대상입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`제공 된 대상 모음에 단추 끌어 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 단추는 도구 모음으로 끌어 놓으면 전에이 메서드를 호출 하는 프레임 워크.  
  
 이 메서드의 기본 구현에서는 반환 `TRUE`합니다. 반환 하려면이 메서드를 재정의 `FALSE` 에 지정된 된 대상에서 놓기 작업을 사용 하지 않도록 설정 합니다.  
  
##  <a name="a-nameoncalculatesizea--cmfctoolbarbuttononcalculatesize"></a><a name="oncalculatesize"></a>CMFCToolBarButton::OnCalculateSize  
 지정 된 장치 컨텍스트와 도킹 상태에 대 한 단추의 크기를 계산 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 단추를 표시 하는 장치 컨텍스트.  
  
 [in] `sizeDefault`  
 단추의 기본 크기입니다.  
  
 [in] `bHorz`  
 부모 도구 모음에서의 도킹 상태입니다. 이 매개 변수는 `TRUE` 도구 모음 가로로 도킹 하거나, 부동 또는 `FALSE` 도구 모음에서 세로로 고정 되어 있는 경우.  
  
### <a name="return-value"></a>반환 값  
 A `SIZE` 픽셀 단위로 단추의 크기를 포함 하는 구조입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 지정 된 장치 컨텍스트에 대 한 도구 모음 단추의 크기를 결정 하 고 상태를 고정 하려면이 메서드를 호출 합니다.  
  
 기본 구현 (표시 된) 경우 텍스트와 이미지 크기, 텍스트 및 이미지 위치 (텍스트 또는 이미지의 오른쪽 아래), 및 도구 모음 도킹 상태를 고려 합니다.  
  
 크기의 비표준 단추 (예를 들어 편집 상자 단추)를 제공 하려는 경우이 메서드를 재정의 합니다.  
  
##  <a name="a-nameoncancelmodea--cmfctoolbarbuttononcancelmode"></a><a name="oncancelmode"></a>CMFCToolBarButton::OnCancelMode  
 처리 하는 프레임 워크에서 호출 된 [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) 메시지입니다.  
  
```  
virtual void OnCancelMode();
```  
  
### <a name="remarks"></a>주의  
 이 메서드의 기본 구현은 아무 작업도 수행합니다. 이 메서드를 재정의 하 여 처리 하려는 경우는 [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) 메시지입니다.  
  
##  <a name="a-nameonchangeparentwnda--cmfctoolbarbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarButton::OnChangeParentWnd  
 새 도구 모음 단추를 삽입할 경우에 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndParent`  
 새 부모 창입니다.  
  
### <a name="remarks"></a>주의  
 사용자가 끌어올 하나의 도구 모음에서 다른 도구 모음에 단추가 예를 들어 도구 모음에 삽입 됩니다.  
  
 이 메서드의 기본 구현은 아무 작업도 수행합니다.  
  
##  <a name="a-nameonclicka--cmfctoolbarbuttononclick"></a><a name="onclick"></a>CMFCToolBarButton::OnClick  
 사용자가 마우스 단추를 클릭할 때 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 도구 모음 단추의 부모 창입니다.  
  
 [in] `bDelay`  
 `TRUE`경우 지연 된 메시지를 처리 합니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `FALSE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 도구 모음 단추를 클릭할 때 프레임 워크에서이 메서드를 호출 합니다.  
  
 기본 구현은 없으며 반환 `FALSE`합니다. 단추 클릭 하 여 메시지를 처리 하는 경우&0;이 아닌 값을 반환 하려면이 메서드를 재정의 합니다.  
  
##  <a name="a-nameonclickupa--cmfctoolbarbuttononclickup"></a><a name="onclickup"></a>CMFCToolBarButton::OnClickUp  
 마우스 단추를 놓을 때 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnClickUp();
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `FALSE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 도구 모음 단추를 놓을 때이 메서드를 호출 하는 프레임 워크입니다.  
  
 기본 구현은 없으며 반환 `FALSE`합니다. 단추 클릭 하 여 메시지를 처리 하는 경우&0;이 아닌 값을 반환 하려면이 메서드를 재정의 합니다.  
  
##  <a name="a-nameoncontexthelpa--cmfctoolbarbuttononcontexthelp"></a><a name="oncontexthelp"></a>CMFCToolBarButton::OnContextHelp  
 부모 도구 모음에서 처리 하는 경우에 프레임 워크에서 호출 된 `WM_HELPHITTEST` 메시지입니다.  
  
```  
virtual BOOL OnContextHelp(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 도구 모음 단추의 부모 창입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `FALSE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드의 기본 구현은 없으며 반환 `FALSE`합니다. 단추 도움말 메시지를 처리 하는 경우&0;이 아닌 값을 반환 하려면이 메서드를 재정의 합니다.  
  
 에 대 한 자세한 내용은 `WM_HELPHITTEST` 메시지에서 참조 [TN028: 상황에 맞는 도움말 지원](../../mfc/tn028-context-sensitive-help-support.md)합니다.  
  
##  <a name="a-nameonctlcolora--cmfctoolbarbuttononctlcolor"></a><a name="onctlcolor"></a>CMFCToolBarButton::OnCtlColor  
 부모 도구 모음에서 처리 하는 경우에 프레임 워크에서 호출 된 `WM_CTLCOLOR` 메시지입니다.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 단추를 표시 하는 장치 컨텍스트.  
  
 [in] `nCtlColor`  
 특정 색 알림입니다.  
  
### <a name="return-value"></a>반환 값  
 프레임 워크를 사용 하 여 단추의 배경을 그릴 brush 개체에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 부모 도구 모음에서 처리 하는 경우이 메서드를 호출 프레임 워크는 `WM_CTLCOLOR` Windows 컨트롤을 포함 하는 도구 모음 단추에 대 한 메시지입니다. 프레임 워크 도구 모음 단추가 창 없는 경우이 메서드를 호출 하지 않습니다.  
  
 프레임 워크는 사용자 지정 모드에는 도구 모음 프레임 워크 및 도구 모음 단추 잠금이 해제 하는 경우이 메서드를 호출 합니다. 사용자 지정 모드에 대 한 자세한 내용은 참조 [CMFCToolBar::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode)합니다. 도구 모음 단추 잠금에 대 한 자세한 내용은 참조 [CMFCToolBarButton::IsLocked](#islocked)합니다.  
  
 기본 구현은 없으며 반환 `NULL`합니다.  
  
##  <a name="a-nameoncustomizemenua--cmfctoolbarbuttononcustomizemenu"></a><a name="oncustomizemenu"></a>CMFCToolBarButton::OnCustomizeMenu  
 부모 도구 모음에서 응용 프로그램 바로 가기 메뉴를 표시 하는 경우 제공 된 메뉴를 수정 하려면 단추를 수 있습니다.  
  
```  
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMenu`  
 메뉴 사용자 지정입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `FALSE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 없으며 반환 `FALSE`합니다. 이 메서드를 재정의 하 고 제공 된 메뉴의 내용을 수정 하려는 경우&0;이 아닌 값을 반환 합니다.  
  
##  <a name="a-nameondblclka--cmfctoolbarbuttonondblclk"></a><a name="ondblclk"></a>CMFCToolBarButton::OnDblClk  
 부모 도구 모음에서 처리 하는 경우에 프레임 워크에서 호출 된 [WM_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) 메시지입니다.  
  
```  
virtual void OnDblClk(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 -   단추의 부모 창입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 `CMFCToolBar::OnLButtonDblClk` 부모 도구 모음에서 처리 하는 경우 메서드는 [WM_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) 메시지입니다.  
  
 이 메서드의 기본 구현은 아무 작업도 수행합니다.  
  
##  <a name="a-nameondrawa--cmfctoolbarbuttonondraw"></a><a name="ondraw"></a>CMFCToolBarButton::OnDraw  
 지정 된 스타일 및 옵션을 사용 하 여 단추를 그리기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz=TRUE,  
    BOOL bCustomizeMode=FALSE,  
    BOOL bHighlight=FALSE,  
    BOOL bDrawBorder=TRUE,  
    BOOL bGrayDisabledButtons=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 단추를 표시 하는 장치 컨텍스트.  
  
 [in] `rect`  
 단추는 경계 사각형입니다.  
  
 [in] `pImages`  
 단추와 연결 된 도구 모음 이미지의 컬렉션입니다.  
  
 [in] `bHorz`  
 부모 도구 모음에서의 도킹 상태입니다. 이 매개 변수는 `TRUE` 단추는 가로로 도킹 된 경우 및 `FALSE` 단추를 세로로 도킹 됩니다.  
  
 [in] `bCustomizeMode`  
 도구 모음 사용자 지정 모드에 있는지 여부를 지정 합니다. 이 매개 변수는 `TRUE` 도구 모음에서이 사용자 지정 모드에 있을 때와 `FALSE` 는 도구 모음을 사용자 지정 모드 없습니다.  
  
 [in] `bHighlight`  
 단추가 강조 표시 되는지 여부를 지정 합니다. 이 매개 변수는 `TRUE` 는 단추가 강조 표시 되 면 및 `FALSE` 때 단추 강조 표시 되지 않습니다.  
  
 [in] `bDrawBorder`  
 단추 테두리를 표시할지 여부를 지정 합니다. 이 매개 변수는 `TRUE` 때 단추 테두리를 표시할지 및 `FALSE` 단추 테두리를 표시 되지 않아야 합니다.  
  
 [in] `bGrayDisabledButtons`  
 비활성화 된 단추 음영을 적용 하거나 비활성화 된 이미지 컬렉션을 사용 하 여 것인지 지정 합니다. 이 매개 변수는 `TRUE` 때 비활성화 된 단추를 회색으로 표시 되어야 하 고 `FALSE` 이 메서드는 비활성화 된 이미지 컬렉션을 사용 해야 합니다.  
  
### <a name="remarks"></a>주의  
 도구 모음 단추 그리기를 사용자 지정 하려면이 메서드를 재정의 합니다.  
  
##  <a name="a-nameondrawoncustomizelista--cmfctoolbarbuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>CMFCToolBarButton::OnDrawOnCustomizeList  
 단추를 그리기 위해 프레임 워크에 의해 호출 된 **명령을** 의 창은 **사용자 지정** 대화 상자입니다.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 단추를 표시 하는 장치 컨텍스트.  
  
 [in] `rect`  
 단추는 경계 사각형입니다.  
  
 [in] `bSelected`  
 단추가 선택 되어 있는지 여부를 지정 합니다. 이 매개 변수가 `TRUE`, 단추를 선택 합니다. 이 매개 변수가 `FALSE`, 단추를 선택 하지 않으면.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 장치 컨텍스트에에서 단추의 픽셀 너비입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 사용자 지정 대화 상자 ( **명령을** 탭) 되는 단추 소유자 그리기 목록 상자에 표시 되도록 할 때입니다.  
  
 이 메서드의 기본 구현을 사용할 수 있는 경우 단추의 이미지 및 텍스트 레이블을 표시 합니다. 단추의 텍스트 레이블을 사용할 수 없는 경우 메서드는 도구 설명 텍스트를 표시 합니다.  
  
 사용자 지정 그리기를 수행 하려면이 메서드를 재정의 합니다.  
  
##  <a name="a-nameongetcustomtooltiptexta--cmfctoolbarbuttonongetcustomtooltiptext"></a><a name="ongetcustomtooltiptext"></a>CMFCToolBarButton::OnGetCustomToolTipText  
 단추에 대 한 사용자 지정 도구 설명 텍스트를 검색 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnGetCustomToolTipText(CString& strToolTip);
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `strToolTip`  
 A `CString` 사용자 지정 도구 설명 텍스트를 받는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `FALSE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 도구 모음 단추에 대 한 도구 설명을 표시할 때이 메서드를 호출 하는 프레임 워크입니다. 이 메서드가 반환 하는 경우 `FALSE`, 프레임 워크에서는 기본 도구 설명 합니다.  
  
 기본 구현은 없으며 반환 `FALSE`합니다. 이 메서드를 재정의 하 고 도구 모음 단추에 대 한 사용자 지정 도구 설명 텍스트를 제공 하는&0;이 아닌 값을 반환 합니다.  
  
##  <a name="a-nameonglobalfontschangeda--cmfctoolbarbuttononglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBarButton::OnGlobalFontsChanged  
 전역 글꼴 변경 된 경우에 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>주의  
 이 메서드의 기본 구현은 아무 작업도 수행합니다. 단추 텍스트를 표시 하는 데 사용 되는 글꼴을 업데이트 하려면이 메서드를 재정의 합니다.  
  
##  <a name="a-nameonmovea--cmfctoolbarbuttononmove"></a><a name="onmove"></a>CMFCToolBarButton::OnMove  
 부모 도구 모음에서 이동 하면 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>주의  
 이 메서드의 기본 구현은 아무 작업도 수행합니다. 부모 도구 모음에서 이동할 때 단추 위치를 변경 하려면이 메서드를 재정의 합니다.  
  
##  <a name="a-nameonshowa--cmfctoolbarbuttononshow"></a><a name="onshow"></a>CMFCToolBarButton::OnShow  
 프레임 워크에 의해 때 호출 단추 수 표시 되거나 표시 되지 않습니다.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bShow`  
 단추가 표시 되는지 여부를 지정 합니다. 이 매개 변수가 `TRUE`, 단추에 표시 됩니다. 그렇지 않으면 단추 표시 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 이 메서드의 기본 구현은 아무 작업도 수행합니다. 단추의 표시 여부를 업데이트 하려면이 메서드를 재정의 합니다.  
  
##  <a name="a-nameonsizea--cmfctoolbarbuttononsize"></a><a name="onsize"></a>CMFCToolBarButton::OnSize  
 부모 도구 모음에서 크기가 변경 되거나 위치와 이러한 변경 하면 크기를 변경 하려면 단추가 될 때 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iSize`  
 새 단추의 너비입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드의 기본 구현은 아무 작업도 수행합니다. 크기 또는 부모 도구 모음에서의 위치 변경 될 때 단추 크기를 조정 하려면이 메서드를 재정의 합니다.  
  
##  <a name="a-nameontoolhittesta--cmfctoolbarbuttonontoolhittest"></a><a name="ontoolhittest"></a>CMFCToolBarButton::OnToolHitTest  
 부모 도구 모음 단추의 경계 사각형에는 점이 인지 여부를 결정 해야 할 때에 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnToolHitTest(
    const CWnd* pWnd,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 단추의 부모 창입니다. 수 `NULL`합니다.  
  
 [in] `pTI`  
 A `TOOLINFO` 도구 설명 컨트롤에 도구에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 결과 `OnMenuButtonToolHitTest` 단추 부모 프레임 창;에 대 한 포인터를 검색할 수 있으면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 유효한 frame 개체에 부모 창 변환할 수 있으면 다음 방법 중 하나를 호출 합니다.  
  
- [CMDIFrameWndEx::OnMenuButtonToolHitTest](../../mfc/reference/cmdiframewndex-class.md#onmenubuttontoolhittest)  
  
- [CFrameWndEx::OnMenuButtonToolHitTest](../../mfc/reference/cframewndex-class.md#onmenubuttontoolhittest)  
  
- [COleIPFrameWndEx::OnMenuButtonToolHitTest](../../mfc/reference/coleipframewndex-class.md#onmenubuttontoolhittest)  
  
##  <a name="a-nameonupdatetooltipa--cmfctoolbarbuttononupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBarButton::OnUpdateToolTip  
 부모 도구 모음에서 도구 설명 텍스트를 업데이트 하는 경우에 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndParent`  
 부모 창입니다.  
  
 [in] `iButtonIndex`  
 부모 단추 컬렉션에 있는 단추의&0;부터 시작 하는 인덱스입니다.  
  
 [in] `wndToolTip`  
 도구 설명 텍스트를 표시 하는 컨트롤입니다.  
  
 [out] `str`  
 A `CString` 업데이트 된 도구 설명 텍스트를 받는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `FALSE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드의 기본 구현은 없으며 반환 `FALSE`합니다. 도구 설명 텍스트 문자열을 제공 하는 경우&0;이 아닌 값을 반환 하려면이 메서드를 재정의 합니다.  
  
##  <a name="a-namepreparedraga--cmfctoolbarbuttonpreparedrag"></a><a name="preparedrag"></a>CMFCToolBarButton::PrepareDrag  
 단추는 끌어서 놓기 작업을 수행 하려고 할 때에 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL PrepareDrag(COleDataSource& srcItem);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `srcItem`  
 A `COleDataSource` 끌어서 놓기 작업에 대 한 상태 정보를 저장 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`작업이 성공 합니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크에 제공 된 상태를 저장 하려면 도구 모음 단추를 준비 하려면이 메서드를 호출 `COleDataSource` 개체입니다. 공유 파일에 대 한 직렬화 자체와 해당 파일을 전달 하 여 해당 상태를 저장 하는이 메서드는 [COleDataSource::CacheGlobalData](../../mfc/reference/coledatasource-class.md#cacheglobaldata) 메서드. 도구 모음 단추 serialization에 대 한 자세한 내용은 참조 [CMFCToolBarButton::Serialize](#serialize)합니다.  
  
 이 메서드는 아무 작업도 수행 하 고 반환 `TRUE` 단추를 저장할 수 없을 경우 (의 [CMFCToolBarButton::CanBeStored](#canbestored) 메서드 반환 `FALSE`). 반환 `FALSE` 개체 직렬화 하는 동안 예외가 발생 합니다.  
  
 OLE 끌어서 놓기 작업에 대 한 자세한 내용은 참조 [끌어서 놓기 (OLE)](../../mfc/drag-and-drop-ole.md)합니다.  
  
##  <a name="a-namerecta--cmfctoolbarbuttonrect"></a><a name="rect"></a>CMFCToolBarButton::Rect  
 단추에 대 한 경계 사각형을 검색합니다.  
  
```  
const CRect& Rect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `CRect` 단추의 경계 사각형을 포함 하는 개체입니다.  
  
##  <a name="a-nameresetimagetodefaulta--cmfctoolbarbuttonresetimagetodefault"></a><a name="resetimagetodefault"></a>CMFCToolBarButton::ResetImageToDefault  
 단추와 연결 되는 이미지의 기본값을 설정 합니다.  
  
```  
virtual void ResetImageToDefault();
```  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 해당 부모 도구 모음에서 기본 이미지를 검색 된 [CMFCToolBar::GetDefaultImage](../../mfc/reference/cmfctoolbar-class.md#getdefaultimage) 메서드. 이 메서드를 사용 하 여 해당 문자열 리소스에 따라 단추의 텍스트 레이블을 설정 단추에 연결 된 기본 이미지가 있는 경우는 [CStringT::LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring) 메서드. 문자열 리소스에 대 한 자세한 내용은 참조 [리소스 파일에 대해 작업](../../windows/working-with-resource-files.md)합니다.  
  
 단추에 사용자 지정 이미지를 사용 하는 경우이 메서드는 아무 것도 않습니다.  
  
##  <a name="a-namesavebarstatea--cmfctoolbarbuttonsavebarstate"></a><a name="savebarstate"></a>CMFCToolBarButton::SaveBarState  
 도구 모음 단추의 상태를 저장합니다.  
  
```  
virtual void SaveBarState();
```  
  
### <a name="remarks"></a>주의  
 프레임 워크를 만들 때이 메서드를 호출을 `CMFCToolBarButton` 끌어서 놓기 작업의 결과로 개체입니다.  
  
 이 메서드의 기본 구현은 아무 작업도 수행합니다. 외부 데이터 원본에 도구 모음 단추의 상태를 저장 하려면이 메서드를 재정의 합니다.  
  
##  <a name="a-nameserializea--cmfctoolbarbuttonserialize"></a><a name="serialize"></a>CMFCToolBarButton::Serialize  
 이 개체는 보관 파일에서 읽거나 보관 파일에 씁니다.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `ar`  
 `CArchive` 개체를 serialize 또는입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 클립보드 또는 끌어 놓기 작업과 같은 데이터 전송 프로세스를 지원합니다. 읽거나 씁니다 ID, 텍스트 레이블 및 이미지 ID 등 단추의 속성에서 제공 된 `CArchive` 개체입니다.  
  
 Serialization 예제를 보려면 [Serialization: 개체를 직렬화 하는 작업](../../mfc/serialization-serializing-an-object.md)합니다.  
  
##  <a name="a-namesetaccdataa--cmfctoolbarbuttonsetaccdata"></a><a name="setaccdata"></a>CMFCToolBarButton::SetACCData  
 제공 된 정보를 표시 `CAccessibilityData` 도구 모음 단추에서 내게 필요한 옵션 데이터는 개체입니다.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParent`  
 도구 모음 단추의 부모 창입니다.  
  
 [in] `data`  
 A `CAccessibilityData` 도구 모음 단추의 내게 필요한 옵션 데이터로 채워지는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `TRUE`을 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드가 반환 하도록 재정의 `FALSE` 도구 모음 단추는 내게 필요한 옵션 데이터를 제공 하지 않는 경우.  
  
##  <a name="a-namesetclipboardformatnamea--cmfctoolbarbuttonsetclipboardformatname"></a><a name="setclipboardformatname"></a>CMFCToolBarButton::SetClipboardFormatName  
 전역 클립보드 형식을 이름을 바꿉니다.  
  
```  
static void __stdcall SetClipboardFormatName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszName`  
 전역 클립보드 형식의 새 이름입니다. 안 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하면 끌어서 놓기 작업이 여러 응용 프로그램에서 발생할 수 있습니다. 각 응용 프로그램에는 동일한 클립보드 형식 이름을 제공 해야 합니다.  
  
 프레임 워크 호출 하기 전에이 메서드를 호출 해야 [CMFCToolBarButton::GetClipboardFormat](#getclipboardformat)합니다.  
  
##  <a name="a-namesetimagea--cmfctoolbarbuttonsetimage"></a><a name="setimage"></a>CMFCToolBarButton::SetImage  
 단추의 이미지 인덱스를 설정합니다.  
  
```  
virtual void SetImage(int iImage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iImage`  
 도구 모음 이미지의 컬렉션에 있는 이미지의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 도구 모음 단추는 구분 기호 이면 `iImage` 구분 기호 단추의 새 너비를 참조 합니다.  
  
 경우 `iImage` 작으면&0; 보다이 방법을 이미지를 그리는 비활성화 하 고 단추의 텍스트 레이블의 그리기가 허용 합니다.  
  
##  <a name="a-namesetprotectedcommandsa--cmfctoolbarbuttonsetprotectedcommands"></a><a name="setprotectedcommands"></a>CMFCToolBarButton::SetProtectedCommands  
 사용자를 사용자 지정할 수 있는 명령의 목록을 설정 합니다.  
  
```  
static void SetProtectedCommands(const CList<UINT,UINT>& lstCmds);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lstCmds`  
 보호 된 명령 목록입니다.  
  
### <a name="remarks"></a>주의  
 사용자 지정 모드는 프레임 워크는 보호 되는 도구 모음 단추 명령을 해제 합니다. 사용자는 끌어서 놓기 수행 하 고 사용할 수 없는 도구 모음 단추에 대 한 작업을 편집할 수 없습니다.  
  
 사용 된 [CMFCToolBarButton::GetProtectedCommands](#getprotectedcommands) 의 목록을 검색 하려면 메서드 명령을 보호 합니다.  
  
##  <a name="a-namesetradioa--cmfctoolbarbuttonsetradio"></a><a name="setradio"></a>CMFCToolBarButton::SetRadio  
 단추의 선택된 상태가 변경 될 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void SetRadio();
```  
  
### <a name="remarks"></a>주의  
 이 메서드의 기본 구현은 아무 작업도 수행합니다. 단추의 선택된 상태가 변경 될 때 사용자 지정 작업을 수행 하려면이 메서드를 재정의 합니다.  
  
##  <a name="a-namesetrecta--cmfctoolbarbuttonsetrect"></a><a name="setrect"></a>CMFCToolBarButton::SetRect  
 단추에 대 한 경계 사각형을 설정합니다.  
  
```  
void SetRect(const CRect rect);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 단추의 새 경계 사각형입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 호출의 [CMFCToolBarButton::OnMove](#onmove) 메서드 후 새 경계 사각형을 설정 합니다.  
  
##  <a name="a-namesetstylea--cmfctoolbarbuttonsetstyle"></a><a name="setstyle"></a>CMFCToolBarButton::SetStyle  
 단추 스타일을 설정합니다.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nStyle`  
 새 스타일 단추입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현에서는 설정 된 [CMFCToolBarButton::m_nStyle](#m_nstyle) 데이터 멤버를 `nStyle`합니다. 스타일의 변경을 처리 하는 추가 처리를 수행 하려는 경우이 메서드를 재정의 합니다. 참조 [ToolBar 컨트롤 스타일](toolbar-control-styles.md) 유효한 스타일 플래그의 목록은 합니다.  
  
##  <a name="a-namesetvisiblea--cmfctoolbarbuttonsetvisible"></a><a name="setvisible"></a>CMFCToolBarButton::SetVisible  
 단추가 표시 되는지 여부를 지정 합니다.  
  
```  
void SetVisible(BOOL bShow=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bShow`  
 단추를 표시할지 여부를 지정 하는 부울 값입니다. 이 매개 변수가 `TRUE`, 단추가 나와 있습니다. 매개 변수가 `FALSE`, 단추가 숨겨집니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 사용 하 여 숨기 거 나 특정 도구 모음 단추를 표시 합니다. 호출의 [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate) 메서드가이 메서드를 호출 합니다.  
  
##  <a name="a-nameshowa--cmfctoolbarbuttonshow"></a><a name="show"></a>CMFCToolBarButton::Show  
 표시 하거나 단추를 숨깁니다.  
  
```  
void Show(BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bShow`  
 단추를 표시할지 여부를 지정 하는 부울 값입니다. 이 매개 변수가 `TRUE`, 단추가 나와 있습니다. 매개 변수가 `FALSE`, 단추가 숨겨집니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 해당 부모 도구 모음에서 크기를 조정할 때 도구 모음 단추의 표시 여부를 업데이트 하려면이 메서드를 호출 합니다. 이 메서드를 호출 하는 프레임 워크 `bShow` 로 설정 `FALSE` 단추 도구 모음 범위 내에서 더 이상 맞지 때. 이 메서드를 호출 하는 프레임 워크 `bShow` 로 설정 `TRUE` 크기를 조정한 후 단추 다시 적합 한 도구 모음 범위 내에서 하는 경우.  
  
 사용 하 여는 [CMFCToolBarButton::SetVisible](#setvisible) 메서드를 일반 단추의 표시 여부를 설정 합니다.  
  
 이 메서드는 [CMFCToolBarButton::OnShow](#onshow) 단추의 표시 여부 상태를 업데이트 한 후에 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarImages 클래스](../../mfc/reference/cmfctoolbarimages-class.md)

