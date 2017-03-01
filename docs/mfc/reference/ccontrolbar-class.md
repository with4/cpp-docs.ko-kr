---
title: "CControlBar 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CControlBar
dev_langs:
- C++
helpviewer_keywords:
- CControlBar class
- OLE resize bars
- OLE resize bars, base class
- dialog bars, base class
- toolbars [C++], base class
- control bars [C++], base class
- status bars, base class
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
caps.latest.revision: 22
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
ms.openlocfilehash: 9720c4c11656834923c0e42a2017d51543c08f53
ms.lasthandoff: 02/24/2017

---
# <a name="ccontrolbar-class"></a>CControlBar Class
컨트롤 막대 클래스에 대 한 기본 클래스 [CStatusBar](../../mfc/reference/cstatusbar-class.md), [CToolBar](../../mfc/reference/ctoolbar-class.md), [CDialogBar](../../mfc/reference/cdialogbar-class.md), [CReBar](../../mfc/reference/crebar-class.md), 및 [COleResizeBar](../../mfc/reference/coleresizebar-class.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CControlBar : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CControlBar::CControlBar](#ccontrolbar)|`CControlBar` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CControlBar::CalcDynamicLayout](#calcdynamiclayout)|로 동적 컨트롤 막대의 크기를 반환 하는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.|  
|[CControlBar::CalcFixedLayout](#calcfixedlayout)|로 컨트롤 막대의 크기를 반환 하는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.|  
|[CControlBar::CalcInsideRect](#calcinsiderect)|컨트롤 막대 영역;의 현재 크기를 반환합니다. 테두리를 포함합니다.|  
|[CControlBar::DoPaint](#dopaint)|테두리 및 컨트롤 막대의 위치 조정 막대를 렌더링합니다.|  
|[CControlBar::DrawBorders](#drawborders)|컨트롤 막대의 테두리를 렌더링합니다.|  
|[CControlBar::DrawGripper](#drawgripper)|컨트롤 막대의 위치 조정 막대를 렌더링합니다.|  
|[CControlBar::EnableDocking](#enabledocking)|고정 또는 부동 소수점 수에 있는 컨트롤 막대를 수 있습니다.|  
|[CControlBar::GetBarStyle](#getbarstyle)|컨트롤 막대 스타일 설정을 검색합니다.|  
|[CControlBar::GetBorders](#getborders)|컨트롤 막대의 테두리 값을 검색합니다.|  
|[CControlBar::GetCount](#getcount)|비-의 수를 반환 `HWND` 은 컨트롤 막대에 있는 요소입니다.|  
|[CControlBar::GetDockingFrame](#getdockingframe)|컨트롤 막대 도킹 프레임에 대 한 포인터를 반환 합니다.|  
|[CControlBar::IsFloating](#isfloating)|문제의 컨트롤 막대 부동 컨트롤 막대는&0;이 아닌 값을 반환 합니다.|  
|[CControlBar::OnUpdateCmdUI](#onupdatecmdui)|명령 UI 처리기를 호출합니다.|  
|[CControlBar::SetBarStyle](#setbarstyle)|컨트롤 막대 스타일 설정을 수정합니다.|  
|[CControlBar::SetBorders](#setborders)|컨트롤 막대의 테두리 값을 설정합니다.|  
|[CControlBar::SetInPlaceOwner](#setinplaceowner)|컨트롤 막대의 위치에서 소유자를 변경합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CControlBar::m_bAutoDelete](#m_bautodelete)|0이 아니면는 `CControlBar` Windows 컨트롤 막대 소멸 될 때 개체가 삭제 됩니다.|  
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|컨트롤 막대의 위치에서 소유자입니다.|  
  
## <a name="remarks"></a>주의  
 컨트롤 막대는 왼쪽 또는 오른쪽 프레임 창에 일반적으로 정렬 되는 창입니다. 자식 항목 중 하나를 포함할 수 있습니다 `HWND`기반 컨트롤을 생성 하 고는 Windows 메시지 또는 비 응답 창인- `HWND`-windows 및 응용 프로그램 코드 또는 프레임 워크 코드에서 관리 되는 항목을 기반으로 합니다. 목록 상자 편집 컨트롤의 예는 `HWND`-기반된 컨트롤, 창 상태 표시줄 및 비트맵 단추는의 예 비- `HWND`-컨트롤을 기반으로 합니다.  
  
 컨트롤 막대 windows는 일반적으로 부모 프레임 창의 자식 창 고 일반적으로 형제 클라이언트 뷰 또는 MDI 프레임 창은 클라이언트입니다. A `CControlBar` 개체 부모 창의 클라이언트 영역에 대 한 정보를 사용 하 여 자체 위치 합니다. 그런 다음 부모 창의 클라이언트 영역에 공간 할당 되지 않은 유지에 대 한 부모 창을 알립니다.  
  
 대 한 자세한 내용은 `CControlBar`를 참조 하십시오.  
  
- [컨트롤 막대](../../mfc/control-bars.md)  
  
- [기술 참고 31: 컨트롤 막대](../../mfc/tn031-control-bars.md)합니다.  
  
-   기술 자료 문서 Q242577: PRB: 업데이트 명령 UI 처리기 않습니다 작동 하지 않는다 메뉴 대화 상자에 연결  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CControlBar`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxext.h  
  
##  <a name="a-namecalcdynamiclayouta--ccontrolbarcalcdynamiclayout"></a><a name="calcdynamiclayout"></a>CControlBar::CalcDynamicLayout  
 프레임 워크의 동적 도구 모음 크기를 계산 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual CSize CalcDynamicLayout(
    int nLength,  
    DWORD nMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `nLength`  
 가로 또는 세로에 따라 컨트롤 막대의 요청 된 차원 `dwMode`합니다.  
  
 `nMode`  
 다음과 같은 미리 정의 된 플래그는 동적 컨트롤 막대의 너비와 높이 결정 하는 데 사용 됩니다. 비트 OR (|) 연산자를 사용 하 여 플래그를 조합 합니다.  
  
|레이아웃 모드 플래그|어떤 의미 인지 확인|  
|-----------------------|-------------------|  
|`LM_STRETCH`|컨트롤 막대를 프레임의 크기를 확장할 수 있는지 여부를 나타냅니다. 막대는 하지는 도킹 모음 (도킹 사용할 수 없음)을 설정 합니다. 설정 하지 막대가 되어 있는 경우 고정 또는 부동 소수점 (도킹에 대 한 사용 가능). 경우 설정, `LM_STRETCH` 무시 `nLength` 에 따라 크기를 반환 하 고는 `LM_HORZ` 상태입니다. `LM_STRETCH`비슷하게 작동 하는 `bStretch` 에 사용 된 매개 변수 [CalcFixedLayout](#calcfixedlayout); 사이의 상관 관계 늘이기 방향에 대 한 자세한 내용은 해당 멤버 함수를 참조 하십시오.|  
|`LM_HORZ`|막대 방향을 가로 또는 세로로 임을 나타냅니다. 경우에 모음은 가로 방향의 설정 되지 않은 세로 방향의 인 경우 설정 합니다. `LM_HORZ`비슷하게 작동 하는 `bHorz` 에 사용 된 매개 변수 [CalcFixedLayout](#calcfixedlayout); 사이의 상관 관계 늘이기 방향에 대 한 자세한 내용은 해당 멤버 함수를 참조 하십시오.|  
|**LM_MRUWIDTH**|가장 최근에 동적 너비를 사용합니다. 무시 `nLength` 매개 변수는 기억된 사용 하 여 가장 최근에 너비를 사용 합니다.|  
|`LM_HORZDOCK`|가로 도킹 차원입니다. 무시 `nLength` 매개 변수 최대 너비와 동적 크기를 반환 합니다.|  
|`LM_VERTDOCK`|세로 도킹 차원입니다. 무시 `nLength` 매개 변수 최대 높이와 동적 크기를 반환 합니다.|  
|`LM_LENGTHY`|경우에 설정 `nLength` 너비 대신 높이 (Y 방향)을 나타냅니다.|  
|`LM_COMMIT`|다시 설정 **LM_MRUWIDTH** 부동 컨트롤 막대의 현재 너비를 합니다.|  
  
### <a name="return-value"></a>반환 값  
 컨트롤 막대 크기 (픽셀)의 한 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 파생 클래스에서 직접 동적 레이아웃을 제공 하려면이 멤버 함수 재정의 `CControlBar`합니다. MFC 클래스에서 파생 된 `CControlBar`, 예: [CToolbar](../../mfc/reference/ctoolbar-class.md)이 멤버 함수를 재정의 하 고 고유한 구현을 제공 합니다.  
  
##  <a name="a-namecalcfixedlayouta--ccontrolbarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CControlBar::CalcFixedLayout  
 컨트롤 막대의 가로 크기를 계산 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>매개 변수  
 `bStretch`  
 모음을 프레임의 크기를 확장할 수 있는지 여부를 나타냅니다. `bStretch` 매개 변수는 0이 아닌 막대는 도킹 모음 (도킹 사용할 수 없음) 아니며 경우 0이 도킹 또는 부동 (도킹에 대 한 사용 가능) 하는 경우.  
  
 `bHorz`  
 막대 방향을 가로 또는 세로로 임을 나타냅니다. `bHorz` 막대는 가로 방향 인지 하 고 0은 세로 방향 인지 하는 경우 매개 변수는 0이 아닌 값입니다.  
  
### <a name="return-value"></a>반환 값  
 컨트롤 막대 크기 (픽셀)의 한 `CSize` 개체입니다.  
  
### <a name="remarks"></a>주의  
 예: 도구 모음 컨트롤 막대 가로 방향으로 늘릴 수 있는 또는 세로로 단추를 수용 하기에 포함 된 컨트롤 막대입니다.  
  
 경우 `bStretch` 는 **TRUE**, 확장에서 제공 하는 방향에 따라 차원 `bHorz`합니다. 즉, 경우 `bHorz` 는 **FALSE**, 컨트롤 막대 세로로 늘어납니다. 경우 `bStretch` 는 **FALSE**, 늘이기 발생 합니다. 다음 표에서 가능한 순열 및 결과 컨트롤 막대 스타일의 `bStretch` 및 `bHorz`합니다.  
  
|bStretch|bHorz|늘이기|방향|도킹/Not 도킹|  
|--------------|-----------|----------------|-----------------|--------------------------|  
|**TRUE**|**TRUE**|수평 확장|가로로 조정|도킹 하지|  
|**TRUE**|**FALSE**|수직 확장|세로 방향|도킹 하지|  
|**FALSE**|**TRUE**|사용 가능한 늘이기 없음|가로로 조정|도킹|  
|**FALSE**|**FALSE**|사용 가능한 늘이기 없음|세로 방향|도킹|  
  
##  <a name="a-namecalcinsiderecta--ccontrolbarcalcinsiderect"></a><a name="calcinsiderect"></a>CControlBar::CalcInsideRect  
 프레임 워크는 컨트롤 막대의 클라이언트 영역을 계산 하려면이 함수를 호출 합니다.  
  
```  
virtual void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 컨트롤 막대;의 현재 크기를 포함합니다. 테두리를 포함합니다.  
  
 `bHorz`  
 막대 방향을 가로 또는 세로로 임을 나타냅니다. `bHorz` 막대는 가로 방향 인지 하 고 0은 세로 방향 인지 하는 경우 매개 변수는 0이 아닌 값입니다.  
  
### <a name="remarks"></a>주의  
 컨트롤 막대가 칠 해지기 전에이 함수가 호출 됩니다.  
  
 테두리 및 컨트롤 막대의 위치 조정 막대의 렌더링을 사용자 지정 하려면이 함수를 재정의 합니다.  
  
##  <a name="a-nameccontrolbara--ccontrolbarccontrolbar"></a><a name="ccontrolbar"></a>CControlBar::CControlBar  
 `CControlBar` 개체를 생성합니다.  
  
```  
CControlBar();
```  
  
##  <a name="a-namedopainta--ccontrolbardopaint"></a><a name="dopaint"></a>CControlBar::DoPaint  
 테두리 및 컨트롤 막대의 위치 조정 막대를 렌더링 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 테두리 및 컨트롤 막대의 위치 조정 막대를 렌더링 하는 데 사용할 장치 컨텍스트를 가리킵니다.  
  
### <a name="remarks"></a>주의  
 컨트롤 막대의 그리기 동작을 사용자 지정 하려면이 함수를 재정의 합니다.  
  
 다른 사용자 지정 메서드를 재정의 하는 `DrawBorders` 및 `DrawGripper` 함수 및 테두리 및 위치 조정 막대에 대 한 사용자 지정 그리기 코드를 추가 합니다. 기본적으로 이러한 메서드를 호출 하기 때문에 `DoPaint` 메서드를 재정의 하는 `DoPaint` 필요 하지 않습니다.  
  
##  <a name="a-namedrawbordersa--ccontrolbardrawborders"></a><a name="drawborders"></a>CControlBar::DrawBorders  
 컨트롤 막대의 테두리를 렌더링 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual void DrawBorders(
    CDC* pDC,  
    CRect& rect);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 컨트롤 막대의 테두리를 렌더링 하는 데 사용할 장치 컨텍스트를 가리킵니다.  
  
 `rect`  
 A `CRect` 은 컨트롤 막대의 크기를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 컨트롤 막대 테두리의 모양을 사용자 지정 하려면이 함수를 재정의 합니다.  
  
##  <a name="a-namedrawgrippera--ccontrolbardrawgripper"></a><a name="drawgripper"></a>CControlBar::DrawGripper  
 컨트롤 막대의 위치 조정 막대를 렌더링 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual void DrawGripper(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 컨트롤 막대 위치 조정 막대를 렌더링 하는 데 사용할 장치 컨텍스트를 가리킵니다.  
  
 `rect`  
 A `CRect` 컨트롤 막대 위치 조정 막대의 크기를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 컨트롤 막대 위치 조정 막대의 모양을 사용자 지정 하려면이 함수를 재정의 합니다.  
  
##  <a name="a-nameenabledockinga--ccontrolbarenabledocking"></a><a name="enabledocking"></a>CControlBar::EnableDocking  
 도킹 컨트롤 막대를 사용 하도록 설정 하려면이 함수를 호출 합니다.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDockStyle`  
 지원 되는 경우 컨트롤 막대 도킹을 지원 하는지 여부 및 해당 부모 창 있는 컨트롤 막대 도킹할 수의 양쪽 측면을 지정 합니다. 다음 중 하나 이상이 될 수 있습니다.  
  
- `CBRS_ALIGN_TOP`클라이언트 영역의 위쪽에 도킹 수 있습니다.  
  
- `CBRS_ALIGN_BOTTOM`클라이언트 영역의 맨 아래에 도킹 수 있습니다.  
  
- `CBRS_ALIGN_LEFT`클라이언트 영역의 왼쪽에 도킹할 수 있습니다.  
  
- `CBRS_ALIGN_RIGHT`클라이언트 영역 오른쪽에 도킹 수 있습니다.  
  
- `CBRS_ALIGN_ANY`클라이언트 영역의 모든 면에 도킹할 수 있습니다.  
  
- `CBRS_FLOAT_MULTI`여러 컨트롤 막대를를 단일 미니 프레임 창에서 이동할 수 있습니다.  
  
 0 인 경우 (즉, 나타내는 플래그가 없는)은 컨트롤 막대 도킹 하지 것입니다.  
  
### <a name="remarks"></a>주의  
 지정 된 면 대상 프레임 창에서 도킹 가능한 면 중 하 나와 일치 해야 하거나 컨트롤 막대 해당 프레임 창에 도킹할 수 없습니다.  
  
##  <a name="a-namegetbarstylea--ccontrolbargetbarstyle"></a><a name="getbarstyle"></a>CControlBar::GetBarStyle  
 이 함수를 결정 하기 위해 호출 **CBRS_** (컨트롤 막대 스타일) 설정을 컨트롤 막대에 대 한 현재 설정 되어 있습니다.  
  
```  
DWORD GetBarStyle();
```  
  
### <a name="return-value"></a>반환 값  
 현재 **CBRS_** 은 컨트롤 막대에 대 한 (컨트롤 막대 스타일) 설정 합니다. 참조 [CControlBar::SetBarStyle](#setbarstyle) 전체 목록은 사용 가능한 스타일입니다.  
  
### <a name="remarks"></a>주의  
 처리 하지 않는 **WS_** (창 스타일) 스타일입니다.  
  
##  <a name="a-namegetbordersa--ccontrolbargetborders"></a><a name="getborders"></a>CControlBar::GetBorders  
 컨트롤 막대에 대 한 현재 테두리 값을 반환합니다.  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `CRect` 현재 너비 (픽셀 단위)는 컨트롤 막대 개체의 각 면의 포함 개체입니다. 예를 들어, 값은 `left` 멤버의 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체, 왼쪽 테두리의 너비입니다.  
  
##  <a name="a-namegetcounta--ccontrolbargetcount"></a><a name="getcount"></a>CControlBar::GetCount  
 비-의 수를 반환 `HWND` 항목에 `CControlBar` 개체입니다.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 수가 아닌 `HWND` 항목에 `CControlBar` 개체입니다. 에 대 한 0을 반환 하는이 함수는 [CDialogBar](../../mfc/reference/cdialogbar-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 파생된 개체에 따라 항목의 형식: 창에 [CStatusBar](../../mfc/reference/cstatusbar-class.md) 개체와 단추 및 구분 기호에 대 한 [CToolBar](../../mfc/reference/ctoolbar-class.md) 개체입니다.  
  
##  <a name="a-namegetdockingframea--ccontrolbargetdockingframe"></a><a name="getdockingframe"></a>CControlBar::GetDockingFrame  
 현재 프레임 창은 컨트롤 막대 도킹에 대 한 포인터를 가져오려면이 함수를 호출 합니다.  
  
```  
CFrameWnd* GetDockingFrame() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 프레임 창에 대 한 포인터 그렇지 않으면 **NULL**합니다.  
  
 경우 (즉, 하는 경우 컨트롤 막대 부동 창인)은 컨트롤 막대는 프레임 창에 도킹 되지 않고,이 함수는 해당 부모에 대 한 포인터를 반환 하는 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)합니다.  
  
### <a name="remarks"></a>주의  
 도킹 컨트롤 막대에 대 한 자세한 내용은 참조 [CControlBar::EnableDocking](#enabledocking) 및 [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar)합니다.  
  
##  <a name="a-nameisfloatinga--ccontrolbarisfloating"></a><a name="isfloating"></a>CControlBar::IsFloating  
 컨트롤 막대 부동 또는 도킹 되는지 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>반환 값  
 컨트롤 막대; 부동 창인 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 부동에 도킹 컨트롤 막대에서의 상태를 변경 하려면 호출 [CFrameWnd::FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar)합니다.  
  
##  <a name="a-namembautodeletea--ccontrolbarmbautodelete"></a><a name="m_bautodelete"></a>CControlBar::m_bAutoDelete  
 0이 아니면는 `CControlBar` Windows 컨트롤 막대 소멸 될 때 개체가 삭제 됩니다.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>주의  
 `m_bAutoDelete`형식의 공용 변수 **BOOL**합니다.  
  
 컨트롤 막대 개체는 일반적으로 프레임 창 개체에 포함 됩니다. 이 경우 `m_bAutoDelete` 프레임 창 소멸 될 때 포함 된 컨트롤 막대 개체가 소멸 되기 때문에 0입니다.  
  
 할당 하는 경우이 변수를&0;이 아닌 값으로 설정 된 `CControlBar` 개체 힙 및 수에 호출 하지 않으려는 **삭제**합니다.  
  
##  <a name="a-namempinplaceownera--ccontrolbarmpinplaceowner"></a><a name="m_pinplaceowner"></a>CControlBar::m_pInPlaceOwner  
 컨트롤 막대의 위치에서 소유자입니다.  
  
```  
CWnd* m_pInPlaceOwner;  
```  
  
##  <a name="a-nameonupdatecmduia--ccontrolbaronupdatecmdui"></a><a name="onupdatecmdui"></a>CControlBar::OnUpdateCmdUI  
 이 멤버 함수는 도구 모음이 나 상태 표시줄의 상태를 업데이트 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler) = 0;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pTarget`  
 응용 프로그램의 주 프레임 창을 가리킵니다. 이 포인터는 업데이트 메시지 라우팅에 사용 됩니다.  
  
 `bDisableIfNoHndler`  
 업데이트 처리기가 있는 컨트롤 함으로 자동으로 표시할지 여부를 나타내는 플래그입니다.  
  
### <a name="remarks"></a>주의  
 개별 단추 또는 창을 업데이트 하려면 사용는 `ON_UPDATE_COMMAND_UI` 메시지 맵에 업데이트 처리기를 적절 하 게 설정 하는 매크로입니다. 참조 [ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4) 이 매크로 사용 하는 방법에 대 한 자세한 내용은 합니다.  
  
 `OnUpdateCmdUI`응용 프로그램이 유휴 상태일 때에 프레임 워크에 의해 호출 됩니다. 업데이트할 프레임 창을 해제 되어야 합니다 자식 창에는 적어도 직접 표시 프레임 창의. `OnUpdateCmdUI`고급 재정의할 수 있습니다.  
  
##  <a name="a-namesetbarstylea--ccontrolbarsetbarstyle"></a><a name="setbarstyle"></a>CControlBar::SetBarStyle  
 원하는 설정 하려면이 함수를 호출 **CBRS_** 은 컨트롤 막대에 대 한 스타일입니다.  
  
```  
void SetBarStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 컨트롤 막대에 대 한 원하는 스타일입니다. 다음 중 하나 이상이 될 수 있습니다.  
  
- `CBRS_ALIGN_TOP`컨트롤 막대를를 프레임 창의 클라이언트 영역 위쪽에 도킹 될 수 있습니다.  
  
- `CBRS_ALIGN_BOTTOM`컨트롤 막대를 프레임 창의 클라이언트 영역 아래쪽에 도킹 될 수 있습니다.  
  
- `CBRS_ALIGN_LEFT`컨트롤 막대를를 왼쪽 프레임 창의 클라이언트 영역에 도킹할 수 있습니다.  
  
- `CBRS_ALIGN_RIGHT`컨트롤 막대를 프레임 창의 클라이언트 영역 오른쪽에 도킹 될 수 있습니다.  
  
- `CBRS_ALIGN_ANY`모든 면 프레임 창의 클라이언트 영역에 도킹 컨트롤 막대를 수 있습니다.  
  
- `CBRS_BORDER_TOP`테두리는 것이 표시 하는 경우 컨트롤 막대의 위쪽 가장자리에 그릴 수를 하면 됩니다.  
  
- `CBRS_BORDER_BOTTOM`것이 표시 하는 경우 컨트롤 막대의 아래쪽 가장자리에 그려질 테두리를 하면 됩니다.  
  
- `CBRS_BORDER_LEFT`것이 표시 하는 경우 컨트롤 막대의 왼쪽된 가장자리에 그려질 테두리를 하면 됩니다.  
  
- `CBRS_BORDER_RIGHT`것이 표시 하는 경우 컨트롤 막대의 오른쪽 가장자리에 그려질 테두리를 하면 됩니다.  
  
- `CBRS_FLOAT_MULTI`여러 컨트롤 막대를를 단일 미니 프레임 창에서 이동할 수 있습니다.  
  
- `CBRS_TOOLTIPS`컨트롤 막대에 대해 표시할 도구 설명 하면 됩니다.  
  
- `CBRS_FLYBY`도구 설명으로 동시에 업데이트할 메시지 텍스트를입니다.  
  
- **CBRS_GRIPPER** 위치 조정 막대, 밴드에 사용한 것과 비슷한 하면는 **CReBar** 개체에 대해 그릴 `CControlBar`-클래스를 파생 합니다.  
  
### <a name="remarks"></a>주의  
 영향을 주지 않습니다는 **WS_** (창 스타일) 설정 합니다.  
  
##  <a name="a-namesetbordersa--ccontrolbarsetborders"></a><a name="setborders"></a>CControlBar::SetBorders  
 컨트롤 막대의 테두리의 크기를 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetBorders(
    int cxLeft = 0,  
    int cyTop = 0,  
    int cxRight = 0,  
    int cyBottom = 0);  
  
void SetBorders(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>매개 변수  
 *cxLeft*  
 픽셀 단위로 컨트롤 막대의 왼쪽된 테두리의 너비입니다.  
  
 *cyTop*  
 픽셀 단위로 컨트롤 막대의 위쪽 테두리의 높이입니다.  
  
 *cxRight*  
 픽셀 단위로 컨트롤 막대의 오른쪽 테두리의 너비입니다.  
  
 *cyBottom*  
 컨트롤 막대의 아래쪽 테두리의 높이 (픽셀 단위)에입니다.  
  
 `lpRect`  
 에 대 한 포인터는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 현재 너비 (픽셀 단위)의 각 개체의 테두리는 컨트롤 막대를 포함 하는 개체입니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 2 개의 픽셀을 5 픽셀은 컨트롤 막대의 위쪽 및 아래쪽 테두리와 왼쪽 및 오른쪽 테두리를 설정합니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog #&61;](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]  
  
##  <a name="a-namesetinplaceownera--ccontrolbarsetinplaceowner"></a><a name="setinplaceowner"></a>CControlBar::SetInPlaceOwner  
 컨트롤 막대의 위치에서 소유자를 변경합니다.  
  
```  
void SetInPlaceOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 에 대 한 포인터는 `CWnd` 개체입니다.  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CTRLBARS](../../visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CToolBar 클래스](../../mfc/reference/ctoolbar-class.md)   
 [CDialogBar 클래스](../../mfc/reference/cdialogbar-class.md)   
 [CStatusBar 클래스](../../mfc/reference/cstatusbar-class.md)   
 [CReBar 클래스](../../mfc/reference/crebar-class.md)

