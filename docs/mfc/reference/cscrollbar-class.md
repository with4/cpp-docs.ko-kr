---
title: "CScrollBar 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CScrollBar
- AFXWIN/CScrollBar
- AFXWIN/CScrollBar::CScrollBar
- AFXWIN/CScrollBar::Create
- AFXWIN/CScrollBar::EnableScrollBar
- AFXWIN/CScrollBar::GetScrollBarInfo
- AFXWIN/CScrollBar::GetScrollInfo
- AFXWIN/CScrollBar::GetScrollLimit
- AFXWIN/CScrollBar::GetScrollPos
- AFXWIN/CScrollBar::GetScrollRange
- AFXWIN/CScrollBar::SetScrollInfo
- AFXWIN/CScrollBar::SetScrollPos
- AFXWIN/CScrollBar::SetScrollRange
- AFXWIN/CScrollBar::ShowScrollBar
dev_langs:
- C++
helpviewer_keywords:
- CScrollBar class
- SCROLLBAR window class
- scroll bars
- Windows common controls [C++], CScrollBar
- controls [MFC], scroll bar
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
caps.latest.revision: 21
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
ms.openlocfilehash: 84b59f041f1a6cf73843c303e1a6b71adffc2101
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cscrollbar-class"></a>CScrollBar 클래스
Windows 스크롤 막대 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CScrollBar : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CScrollBar::CScrollBar](#cscrollbar)|`CScrollBar` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CScrollBar::Create](#create)|Windows 스크롤 막대를 만들고 연결 하는 `CScrollBar` 개체입니다.|  
|[CScrollBar::EnableScrollBar](#enablescrollbar)|스크롤 막대의 화살표 하나 또는 둘 다를 사용하거나 사용하지 않도록 설정합니다.|  
|[CScrollBar::GetScrollBarInfo](#getscrollbarinfo)|스크롤 막대를 사용 하는 방법에 대 한 정보를 검색 한 `SCROLLBARINFO` 구조입니다.|  
|[CScrollBar::GetScrollInfo](#getscrollinfo)|스크롤 막대에 대 한 정보를 검색합니다.|  
|[CScrollBar::GetScrollLimit](#getscrolllimit)|스크롤 막대의 한도 검색합니다.|  
|[CScrollBar::GetScrollPos](#getscrollpos)|스크롤 상자의 현재 위치를 검색합니다.|  
|[CScrollBar::GetScrollRange](#getscrollrange)|지정한 스크롤 막대에 대 한 현재 최소 및 최대 스크롤 막대 위치를 검색합니다.|  
|[CScrollBar::SetScrollInfo](#setscrollinfo)|스크롤 막대에 대한 정보를 설정합니다.|  
|[CScrollBar::SetScrollPos](#setscrollpos)|스크롤 상자의 현재 위치를 설정합니다.|  
|[CScrollBar::SetScrollRange](#setscrollrange)|지정된 스크롤 막대에 대한 최소 및 최대 위치 값을 설정합니다.|  
|[CScrollBar::ShowScrollBar](#showscrollbar)|표시 하거나 스크롤 막대를 숨깁니다.|  
  
## <a name="remarks"></a>주의  
 2 단계를 거쳐에서 스크롤 막대 컨트롤을 만듭니다. 먼저 생성자를 호출 `CScrollBar` 생성 하는 `CScrollBar` 개체를 만든 다음 호출에서 [만들기](#create) Windows 스크롤 막대 컨트롤을 만들고에 연결 하는 멤버 함수는 `CScrollBar` 개체입니다.  
  
 만드는 경우는 `CScrollBar` (대화 상자 리소스의 경우)를 통해 대화 상자 내에서 개체는 `CScrollBar` 는 사용자가 대화 상자를 닫을 때 자동으로 삭제 됩니다.  
  
 만드는 경우는 `CScrollBar` 창으로 개체를 파기 해야 할 수도 있습니다.  
  
 만드는 경우는 `CScrollBar` 개체 스택에 자동으로 소멸 됩니다. 만드는 경우는 `CScrollBar` 개체를 사용 하 여 힙에 **새** 호출 해야 함수를 **삭제** 사용자 Windows 스크롤 막대를 종료 될 때 소멸 시킬 개체에 있습니다.  
  
 에 메모리를 할당 하는 경우는 `CScrollBar` 개체, 재정의 `CScrollBar` 의 할당을 삭제 하는 소멸자입니다.  
  
 사용 하는 방법에 대 한 관련된 정보에 대 한 `CScrollBar`, 참조 [컨트롤](../../mfc/controls-mfc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CScrollBar`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="create"></a>CScrollBar::Create  
 Windows 스크롤 막대를 만들고 연결 하는 `CScrollBar` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 지정 된 스크롤 막대의 스타일입니다. 모든 조합의 적용 [스크롤 막대 스타일](../../mfc/reference/scroll-bar-styles.md) 스크롤 막대를 합니다.  
  
 `rect`  
 스크롤 막대의 크기와 위치를 지정합니다. 일 수는 `RECT` 구조 또는 `CRect` 개체입니다.  
  
 `pParentWnd`  
 지정 스크롤 막대의 부모 창, 일반적으로 `CDialog` 개체입니다. 않아야 **NULL**합니다.  
  
 `nID`  
 스크롤 막대 컨트롤 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 생성 한 `CScrollBar` 두 단계에서는 개체입니다. 먼저를 생성 하는 생성자를 호출의 `CScrollBar` 개체; 다음 호출 **만들기**는 및 연결 된 Windows 스크롤 막대를 초기화를 만들고 연결 하는 `CScrollBar` 개체입니다.  
  
 다음 적용 [창 스타일](../../mfc/reference/window-styles.md) 스크롤 막대를:  
  
- **WS_CHILD** 항상  
  
- **WS_VISIBLE** 일반적으로  
  
- **WS_DISABLED** 거의  
  
- **WS_GROUP** 컨트롤을 그룹화  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CScrollBar #&1;](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]  
  
##  <a name="cscrollbar"></a>CScrollBar::CScrollBar  
 `CScrollBar` 개체를 생성합니다.  
  
```  
CScrollBar();
```  
  
### <a name="remarks"></a>주의  
 개체를 생성 한 후 호출 하는 **만들기** 멤버 함수를 만들고 Windows 스크롤 막대를 초기화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CScrollBar #&2;](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]  
  
##  <a name="enablescrollbar"></a>CScrollBar::EnableScrollBar  
 스크롤 막대의 화살표 하나 또는 둘 다를 사용하거나 사용하지 않도록 설정합니다.  
  
```  
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```  
  
### <a name="parameters"></a>매개 변수  
 `nArrowFlags`  
 화살표를 사용 및 스크롤 화살표는의 사용 여부 지정 합니다. 이 매개 변수는 다음 값 중 하나일 수 있습니다.  
  
- **ESB_ENABLE_BOTH** 스크롤 막대의 양쪽 화살표를 사용 합니다.  
  
- **ESB_DISABLE_LTUP** 가로 스크롤 막대의 왼쪽된 화살표 또는 세로 스크롤 막대의 위쪽 화살표를 사용 하지 않도록 설정 합니다.  
  
- **ESB_DISABLE_RTDN** 가로 스크롤 막대의 오른쪽 화살표 또는 세로 스크롤 막대의 아래쪽 화살표를 사용 하지 않도록 설정 합니다.  
  
- **ESB_DISABLE_BOTH** 스크롤 막대의 양쪽 화살표를 사용 하지 않도록 설정 합니다.  
  
### <a name="return-value"></a>반환 값  
 화살표를; 지정 된 대로 사용 하는 경우 0이 아닌 그렇지 않으면 0으로, 화살표는 이미 요청 된 상태 또는 오류가 발생 했음을 나타냅니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CScrollBar::SetScrollRange](#setscrollrange)합니다.  
  
##  <a name="getscrollbarinfo"></a>CScrollBar::GetScrollBarInfo  
 정보를 검색 하는 **SCROLLBARINFO** 스크롤 막대에 대 한 구조를 유지 관리 합니다.  
  
```  
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *pScrollInfo*  
 에 대 한 포인터는 [SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787535) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [SBM_SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787545) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getscrollinfo"></a>CScrollBar::GetScrollInfo  
 `SCROLLINFO` 구조체에서 스크롤 막대에 대해 유지 관리하는 정보를 검색합니다.  
  
```  
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,  
    UINT nMask = SIF_ALL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpScrollInfo`  
 에 대 한 포인터는 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) 구조입니다. 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 이 구조에 대 한 자세한 내용은 합니다.  
  
 `nMask`  
 검색할 스크롤 막대 매개 변수를 지정 합니다. 일반적인 사용, SIF_ALL, SIF_PAGE, SIF_POS, SIF_TRACKPOS, 및 SIF_RANGE의 조합을 지정합니다. 참조 `SCROLLINFO` nMask 값에 대 한 자세한 내용은 합니다.  
  
### <a name="return-value"></a>반환 값  
 메시지가 검색 된 값을 반환이 **TRUE**합니다. 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 `GetScrollInfo`32 비트 스크롤 위치를 사용 하 여 응용 프로그램이 있습니다.  
  
 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) 스크롤 막대의 최소값 및 최대값 스크롤 위치, 페이지 크기와 스크롤 상자 (thumb)의 위치를 포함 하는 방법에 대 한 정보를 포함 하는 구조입니다. 참조는 `SCROLLINFO` 구조 항목에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 구조 기본값을 변경 하는 방법에 대 한 자세한 내용은 합니다.  
  
 MFC Windows 메시지 처리기를 나타내는 스크롤 막대 위치 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) 및 [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll), 16 비트만 위치 데이터를 제공 합니다. `GetScrollInfo`및 `SetScrollInfo` 32 비트의 스크롤 막대의 위치 데이터를 제공 합니다. 따라서 응용 프로그램이 호출할 수 `GetScrollInfo` 중 하나를 처리 하는 동안 `CWnd::OnHScroll` 또는 `CWnd::OnVScroll` 32 비트 스크롤 막대 위치 데이터를 가져옵니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)합니다.  
  
##  <a name="getscrolllimit"></a>CScrollBar::GetScrollLimit  
 스크롤 막대의 위치를 스크롤 하는 최대를 검색 합니다.  
  
```  
int GetScrollLimit();
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 스크롤 막대의 최대 위치 지정 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)합니다.  
  
##  <a name="getscrollpos"></a>CScrollBar::GetScrollPos  
 스크롤 상자의 현재 위치를 검색합니다.  
  
```  
int GetScrollPos() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 스크롤 상자의 현재 위치를 지정 합니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 현재 위치는 현재 스크롤 범위에 의존 하는 상대 값입니다. 예를 들어 스크롤 범위는 100-200 경우 스크롤 상자 막대 중에 현재 위치가 150 지정 됩니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)합니다.  
  
##  <a name="getscrollrange"></a>CScrollBar::GetScrollRange  
 지정한 스크롤 막대에 대 한 현재 최소 및 최대 스크롤 막대 위치에 지정 된 위치에 복사 `lpMinPos` 및 `lpMaxPos`합니다.  
  
```  
void GetScrollRange(
    LPINT lpMinPos,  
    LPINT lpMaxPos) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpMinPos`  
 최소 위치를 수신 하는 정수 변수를 가리킵니다.  
  
 `lpMaxPos`  
 최대 위치를 수신 하는 정수 변수를 가리킵니다.  
  
### <a name="remarks"></a>주의  
 스크롤 막대 컨트롤에 대 한 기본 범위는 빈 (두 값은 0).  
  
### <a name="example"></a>예제  
  예를 참조 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)합니다.  
  
##  <a name="setscrollinfo"></a>CScrollBar::SetScrollInfo  
 정보를 설정 하는 `SCROLLINFO` 스크롤 막대에 대 한 구조를 유지 관리 합니다.  
  
```  
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpScrollInfo`  
 에 대 한 포인터는 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) 구조입니다.  
  
 `bRedraw`  
 새로운 정보를 반영 스크롤 막대가 다시 그려져 야 하는지 여부를 지정 합니다. 경우 `bRedraw` 는 **TRUE**, 스크롤 막대를 다시 그려집니다. 있으면 **FALSE**, 다시 그려지지 않습니다. 스크롤 막대를 기본적으로 그려집니다.  
  
### <a name="return-value"></a>반환 값  
 성공이 반환 됩니다 **TRUE**합니다. 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 에 필요한 값을 제공 해야는 `SCROLLINFO` 플래그 값을 포함 하 여 매개 변수를 구성 합니다.  
  
 `SCROLLINFO` 스크롤 막대의 최소값 및 최대값 스크롤 위치, 페이지 크기와 스크롤 상자 (thumb)의 위치를 포함 하는 방법에 대 한 정보를 포함 하는 구조입니다. 참조는 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) 구조 항목에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 구조 기본값을 변경 하는 방법에 대 한 자세한 내용은 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CScrollBar #&3;](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]  
  
##  <a name="setscrollpos"></a>CScrollBar::SetScrollPos  
 스크롤 상자의 현재 위치에 지정 된 설정 `nPos` 고를 지정 하는 경우에 새 위치를 반영 하도록 스크롤 막대를 다시 그립니다.  
  
```  
int SetScrollPos(
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 스크롤 상자에 대 한 새 위치를 지정합니다. 스크롤 사이 여야 합니다.  
  
 `bRedraw`  
 새 위치를 반영 스크롤 막대가 다시 그려져 야 하는지 여부를 지정 합니다. 경우 `bRedraw` 는 **TRUE**, 스크롤 막대를 다시 그려집니다. 있으면 **FALSE**, 다시 그려지지 않습니다. 스크롤 막대를 기본적으로 그려집니다.  
  
### <a name="return-value"></a>반환 값  
 스크롤 상자 성공 하면 이전 위치 지정 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 설정 `bRedraw` 를 **FALSE** 짧은 기간 내에서 두 번 다시 그릴 스크롤 막대를 하지 않으려면 이후에 다른 함수를 호출 하 여 스크롤 막대를 다시 그릴 때마다 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CScrollBar::SetScrollRange](#setscrollrange)합니다.  
  
##  <a name="setscrollrange"></a>CScrollBar::SetScrollRange  
 지정된 스크롤 막대에 대한 최소 및 최대 위치 값을 설정합니다.  
  
```  
void SetScrollRange(
    int nMinPos,  
    int nMaxPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `nMinPos`  
 최소 스크롤 위치를 지정 합니다.  
  
 `nMaxPos`  
 최대 스크롤 위치를 지정 합니다.  
  
 `bRedraw`  
 변경 내용을 반영 스크롤 막대가 다시 그려져 야 하는지 여부를 지정 합니다. 경우 `bRedraw` 는 **TRUE**, 스크롤 막대를 다시 그릴; 경우 **FALSE**, 다시 그려지지 않습니다. 기본적으로 두는 것이 그려집니다.  
  
### <a name="remarks"></a>주의  
 설정 `nMinPos` 및 `nMaxPos` 표준 스크롤 막대를 숨기려면 0입니다.  
  
 스크롤 막대 알림 메시지를 처리 하는 동안 스크롤 막대를 숨기려면이 함수를 호출 하지 마십시오.  
  
 호출 하는 경우 `SetScrollRange` 에 대 한 호출 바로 뒤에 `SetScrollPos` 멤버 함수가 설정 `bRedraw` 에서 `SetScrollPos` 스크롤 막대를 두 번 다시 그려지는 하지 않도록 설정 하려면 0으로 합니다.  
  
 지정 된 값 간의 차이 `nMinPos` 및 `nMaxPos` 32, 767 보다 크지 않아야 합니다. 스크롤 막대 컨트롤에 대 한 기본 범위는 빈 (둘 다 `nMinPos` 및 `nMaxPos` 0).  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CScrollBar #&4;](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]  
  
##  <a name="showscrollbar"></a>CScrollBar::ShowScrollBar  
 표시 하거나 스크롤 막대를 숨깁니다.  
  
```  
void ShowScrollBar(BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bShow`  
 스크롤 막대가 표시 되는지 또는 숨겨지는지 여부를 지정 합니다. 이 매개 변수가 **TRUE**, 스크롤 막대가 표시 되는지, 숨겨져 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 응용 프로그램을 스크롤 막대 알림 메시지를 처리 하는 동안 스크롤 막대를 숨기려면이 함수를 호출 해야 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CScrollBar::Create](#create)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CButton 클래스](../../mfc/reference/cbutton-class.md)   
 [CComboBox 클래스](../../mfc/reference/ccombobox-class.md)   
 [CEdit 클래스](../../mfc/reference/cedit-class.md)   
 [CListBox 클래스](../../mfc/reference/clistbox-class.md)   
 [CStatic 클래스](../../mfc/reference/cstatic-class.md)   
 [CDialog 클래스](../../mfc/reference/cdialog-class.md)

