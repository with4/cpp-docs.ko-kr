---
title: CSliderCtrl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSliderCtrl
- AFXCMN/CSliderCtrl
- AFXCMN/CSliderCtrl::CSliderCtrl
- AFXCMN/CSliderCtrl::ClearSel
- AFXCMN/CSliderCtrl::ClearTics
- AFXCMN/CSliderCtrl::Create
- AFXCMN/CSliderCtrl::CreateEx
- AFXCMN/CSliderCtrl::GetBuddy
- AFXCMN/CSliderCtrl::GetChannelRect
- AFXCMN/CSliderCtrl::GetLineSize
- AFXCMN/CSliderCtrl::GetNumTics
- AFXCMN/CSliderCtrl::GetPageSize
- AFXCMN/CSliderCtrl::GetPos
- AFXCMN/CSliderCtrl::GetRange
- AFXCMN/CSliderCtrl::GetRangeMax
- AFXCMN/CSliderCtrl::GetRangeMin
- AFXCMN/CSliderCtrl::GetSelection
- AFXCMN/CSliderCtrl::GetThumbLength
- AFXCMN/CSliderCtrl::GetThumbRect
- AFXCMN/CSliderCtrl::GetTic
- AFXCMN/CSliderCtrl::GetTicArray
- AFXCMN/CSliderCtrl::GetTicPos
- AFXCMN/CSliderCtrl::GetToolTips
- AFXCMN/CSliderCtrl::SetBuddy
- AFXCMN/CSliderCtrl::SetLineSize
- AFXCMN/CSliderCtrl::SetPageSize
- AFXCMN/CSliderCtrl::SetPos
- AFXCMN/CSliderCtrl::SetRange
- AFXCMN/CSliderCtrl::SetRangeMax
- AFXCMN/CSliderCtrl::SetRangeMin
- AFXCMN/CSliderCtrl::SetSelection
- AFXCMN/CSliderCtrl::SetThumbLength
- AFXCMN/CSliderCtrl::SetTic
- AFXCMN/CSliderCtrl::SetTicFreq
- AFXCMN/CSliderCtrl::SetTipSide
- AFXCMN/CSliderCtrl::SetToolTips
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl [MFC], CSliderCtrl
- CSliderCtrl [MFC], ClearSel
- CSliderCtrl [MFC], ClearTics
- CSliderCtrl [MFC], Create
- CSliderCtrl [MFC], CreateEx
- CSliderCtrl [MFC], GetBuddy
- CSliderCtrl [MFC], GetChannelRect
- CSliderCtrl [MFC], GetLineSize
- CSliderCtrl [MFC], GetNumTics
- CSliderCtrl [MFC], GetPageSize
- CSliderCtrl [MFC], GetPos
- CSliderCtrl [MFC], GetRange
- CSliderCtrl [MFC], GetRangeMax
- CSliderCtrl [MFC], GetRangeMin
- CSliderCtrl [MFC], GetSelection
- CSliderCtrl [MFC], GetThumbLength
- CSliderCtrl [MFC], GetThumbRect
- CSliderCtrl [MFC], GetTic
- CSliderCtrl [MFC], GetTicArray
- CSliderCtrl [MFC], GetTicPos
- CSliderCtrl [MFC], GetToolTips
- CSliderCtrl [MFC], SetBuddy
- CSliderCtrl [MFC], SetLineSize
- CSliderCtrl [MFC], SetPageSize
- CSliderCtrl [MFC], SetPos
- CSliderCtrl [MFC], SetRange
- CSliderCtrl [MFC], SetRangeMax
- CSliderCtrl [MFC], SetRangeMin
- CSliderCtrl [MFC], SetSelection
- CSliderCtrl [MFC], SetThumbLength
- CSliderCtrl [MFC], SetTic
- CSliderCtrl [MFC], SetTicFreq
- CSliderCtrl [MFC], SetTipSide
- CSliderCtrl [MFC], SetToolTips
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c26df378c500b8c1384f7a357b93693b215ca10
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079618"
---
# <a name="csliderctrl-class"></a>CSliderCtrl 클래스
Windows의 공용 슬라이더 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSliderCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSliderCtrl::CSliderCtrl](#csliderctrl)|`CSliderCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSliderCtrl::ClearSel](#clearsel)|슬라이더 컨트롤의 현재 선택을 해제합니다.|  
|[CSliderCtrl::ClearTics](#cleartics)|슬라이더 컨트롤에서 현재 눈금 표시를 제거합니다.|  
|[CSliderCtrl::Create](#create)|슬라이더 컨트롤을 만들고에 연결 된 `CSliderCtrl` 개체입니다.|  
|[CSliderCtrl::CreateEx](#createex)|Windows는 지정 된 확장된 스타일을 사용 하 여 슬라이더 컨트롤을 만들고에 연결 된 `CSliderCtrl` 개체입니다.|  
|[CSliderCtrl::GetBuddy](#getbuddy)|지정 된 위치에 있는 슬라이더 컨트롤 버디 창에 대 한 핸들을 검색합니다.|  
|[CSliderCtrl::GetChannelRect](#getchannelrect)|슬라이더 컨트롤 채널의 크기를 검색합니다.|  
|[CSliderCtrl::GetLineSize](#getlinesize)|슬라이더 컨트롤의 선 크기를 검색합니다.|  
|[CSliderCtrl::GetNumTics](#getnumtics)|슬라이더 컨트롤의 눈금 표시의 수를 검색 합니다.|  
|[CSliderCtrl::GetPageSize](#getpagesize)|슬라이더 컨트롤의 페이지 크기를 검색합니다.|  
|[CSliderCtrl::GetPos](#getpos)|슬라이더의 현재 위치를 검색합니다.|  
|[CSliderCtrl::GetRange](#getrange)|슬라이더에 대 한 최소 및 최대 위치를 검색합니다.|  
|[CSliderCtrl::GetRangeMax](#getrangemax)|슬라이더에 대 한 최대 위치를 검색합니다.|  
|[CSliderCtrl::GetRangeMin](#getrangemin)|슬라이더에 대 한 최소 위치를 검색합니다.|  
|[CSliderCtrl::GetSelection](#getselection)|현재 선택 항목의 범위를 검색 합니다.|  
|[CSliderCtrl::GetThumbLength](#getthumblength)|현재 trackbar 컨트롤에서 슬라이더의 길이 검색합니다.|  
|[CSliderCtrl::GetThumbRect](#getthumbrect)|슬라이더 컨트롤의 엄지 단추 크기를 검색합니다.|  
|[CSliderCtrl::GetTic](#gettic)|지정 된 눈금 표시의 위치를 검색 합니다.|  
|[CSliderCtrl::GetTicArray](#getticarray)|슬라이더 컨트롤에 대 한 눈금 표시 위치 배열을 검색합니다.|  
|[CSliderCtrl::GetTicPos](#getticpos)|클라이언트 좌표에서 지정 된 눈금 표시의 위치를 검색합니다.|  
|[CSliderCtrl::GetToolTips](#gettooltips)|있는 경우 슬라이더 컨트롤에 할당 된 도구 설명 컨트롤에 대 한 핸들을 검색 합니다.|  
|[CSliderCtrl::SetBuddy](#setbuddy)|Slider 컨트롤의 버디 창으로 창을 할당합니다.|  
|[CSliderCtrl::SetLineSize](#setlinesize)|슬라이더 컨트롤의 선 크기를 설정합니다.|  
|[CSliderCtrl::SetPageSize](#setpagesize)|슬라이더 컨트롤의 페이지 크기를 설정합니다.|  
|[CSliderCtrl::SetPos](#setpos)|슬라이더의 현재 위치를 설정합니다.|  
|[CSliderCtrl::SetRange](#setrange)|슬라이더에 대 한 최소 및 최대 위치를 설정합니다.|  
|[CSliderCtrl::SetRangeMax](#setrangemax)|슬라이더에 대 한 최대 위치를 설정합니다.|  
|[CSliderCtrl::SetRangeMin](#setrangemin)|슬라이더에 대 한 최소 위치를 설정합니다.|  
|[CSliderCtrl::SetSelection](#setselection)|현재 선택 항목의 범위를 설정합니다.|  
|[CSliderCtrl::SetThumbLength](#setthumblength)|현재 trackbar 컨트롤에서 슬라이더의 길이 설정합니다.|  
|[CSliderCtrl::SetTic](#settic)|지정 된 눈금 표시의 위치를 설정 합니다.|  
|[CSliderCtrl::SetTicFreq](#setticfreq)|슬라이더 컨트롤 증가 당 표시가 눈금의 빈도 설정합니다.|  
|[CSliderCtrl::SetTipSide](#settipside)|위치가 trackbar 컨트롤에서 도구 설명 컨트롤 사용.|  
|[CSliderCtrl::SetToolTips](#settooltips)|슬라이더 컨트롤에 도구 설명 컨트롤을 할당합니다.|  
  
## <a name="remarks"></a>설명  
 "Slider 컨트롤" (trackbar 라고도 함)는 슬라이더 및 선택적 눈금 표시를 포함 하는 창입니다. 사용자가 마우스 또는 방향 키를 사용 하 여 슬라이더에서, 컨트롤 변경 내용을 나타내는 알림 메시지를 보냅니다.  
  
 슬라이더 컨트롤은 사용자 범위에 불연속 값 또는 연속 값 집합이 선택 하려는 경우에 유용 합니다. 예를 들어 사용자 지정된 눈금 표시로 슬라이더를 이동 하 여 키보드 반복 속도 설정 하도록 허용 하려면 슬라이더 컨트롤을 사용할 수 있습니다.  
  
 이 컨트롤 (및 따라서는 `CSliderCtrl` 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수는 있습니다.  
  
 슬라이더에서 만들 때 지정 하는 이동 합니다. 예를 들어 슬라이더 5의 범위에 있어야을 지정 하면 슬라이더 수만 자리를 차지 6: 범위에서 각 증가값에 대해 하나의 위치 및 슬라이더 컨트롤의 왼쪽에 위치 합니다. 일반적으로 이러한 각 위치를 눈금으로 식별 됩니다.  
  
 생성자를 사용 하 여 슬라이더를 만들면 및 `Create` 의 멤버 함수 `CSliderCtrl`합니다. 슬라이더 컨트롤을 만든 후에 멤버 함수에 사용할 수 있습니다 `CSliderCtrl` 다양 한 속성을 변경할 수 있습니다. 슬라이더에 대한 최소 및 최대 위치 설정, 눈금 표시 그리기, 선택 범위 설정 및 슬라이더 위치 조정을 변경할 수 있습니다.  
  
 사용 하 여 대 한 자세한 내용은 `CSliderCtrl`, 참조 [컨트롤](../../mfc/controls-mfc.md) 및 [CSliderCtrl 사용 하 여](../../mfc/using-csliderctrl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSliderCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="clearsel"></a>  CSliderCtrl::ClearSel  
 슬라이더 컨트롤의 현재 선택을 해제합니다.  
  
```  
void ClearSel(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 *bRedraw*  
 플래그를 다시 그립니다. 이 매개 변수가 **TRUE**, 선택이 취소 되는 슬라이더 다시 않습니다; 그렇지 않으면 슬라이더 다시 그려지지 않습니다.  
  
##  <a name="cleartics"></a>  CSliderCtrl::ClearTics  
 슬라이더 컨트롤에서 현재 눈금 표시를 제거합니다.  
  
```  
void ClearTics(BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 *bRedraw*  
 플래그를 다시 그립니다. 이 매개 변수가 **TRUE**, 슬라이더의 눈금 표시의 선택을 취소 한 후 다시 그려집니다; 그렇지 않으면 슬라이더 다시 그려지지 않습니다.  
  
##  <a name="create"></a>  CSliderCtrl::Create  
 슬라이더 컨트롤을 만들고에 연결 된 `CSliderCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwStyle*  
 슬라이더 컨트롤의 스타일을 지정합니다. 어떠한 조합의 적용 [슬라이더 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760147)컨트롤에는 Windows SDK에 설명 된 대로 합니다.  
  
 *rect*  
 슬라이더 컨트롤의 크기와 위치를 지정합니다. 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조입니다.  
  
 *pParentWnd*  
 슬라이더 컨트롤의 부모 창에 일반적으로 지정 된 `CDialog`합니다. 않아야 **NULL**합니다.  
  
 *nID*  
 슬라이더 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 초기화에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 생성 한 `CSliderCtrl` 두 단계를 수행에서 합니다. 먼저 생성자를 호출 하 고 호출 `Create`, 슬라이더 컨트롤을 만들고에 연결는 `CSliderCtrl` 개체입니다.  
  
 설정할 값에 따라 `dwStyle`, 슬라이더 컨트롤을 세로 또는 가로 방향을 가질 수 있습니다. 어느 쪽에 눈금을 가질 수 있습니다 면, 또는 모두 둘 다 합니다. 또한 연속 값의 범위를 지정 하려면 사용할 수 있습니다.  
  
 확장된 창 스타일을 슬라이더 컨트롤에 적용 하려면 호출 [CreateEx](#createex) 대신 `Create`합니다.  
  
##  <a name="createex"></a>  CSliderCtrl::CreateEx  
 에 연결 하 고 컨트롤 (자식 창)을 만듭니다.는 `CSliderCtrl` 개체입니다.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwExStyle*  
 만들 컨트롤의 확장된 스타일을 지정 합니다. 목록이 확장된 창 스타일에 대 한 참조는 *dwExStyle* 에 대 한 매개 변수 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows sdk에서입니다.  
  
 *dwStyle*  
 슬라이더 컨트롤의 스타일을 지정합니다. 어떠한 조합의 적용 [슬라이더 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760147)컨트롤에는 Windows SDK에 설명 된 대로 합니다.  
  
 *rect*  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와의 클라이언트 좌표에 만들어질 창 위치를 설명 하는 구조 *pParentWnd*합니다.  
  
 *pParentWnd*  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 *nID*  
 컨트롤의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 `CreateEx` 대신 [만들기](#create) Windows 확장된 스타일 접두사에 의해 지정 된 확장된 창 스타일을 적용할 **WS_EX_** 합니다.  
  
##  <a name="csliderctrl"></a>  CSliderCtrl::CSliderCtrl  
 `CSliderCtrl` 개체를 생성합니다.  
  
```  
CSliderCtrl();
```  
  
##  <a name="getbuddy"></a>  CSliderCtrl::GetBuddy  
 지정 된 위치에 있는 슬라이더 컨트롤 버디 창에 대 한 핸들을 검색합니다.  
  
```  
CWnd* GetBuddy(BOOL fLocation = TRUE) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *fLocation*  
 값 중 검색할 두 개의 버디 창 핸들을 나타내는 부울 값입니다. 다음 값 중 하나입니다.  
  
- **TRUE** 슬라이더의 왼쪽에 친구에 대 한 핸들을 검색 합니다. 슬라이더 컨트롤 사용 하는 경우는 `TBS_VERT` 스타일 메시지 슬라이더 위의 버디를 검색 합니다.  
  
- **FALSE** 오른쪽 슬라이더의 친구에 대 한 핸들을 검색 합니다. 슬라이더 컨트롤 사용 하는 경우는 `TBS_VERT` 스타일 메시지 슬라이더 아래 버디를 검색 합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 버디 창으로 지정 된 위치에 있는 개체 `fLocation`, 또는 **NULL** 해당 위치에 있을 때 버디 창이 없습니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TBM_GETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760178)Windows SDK에 설명 된 대로 합니다. 슬라이더 컨트롤 스타일에 대 한 참조 [Trackbar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760147) Windows sdk에서입니다.  
  
##  <a name="getchannelrect"></a>  CSliderCtrl::GetChannelRect  
 슬라이더 컨트롤의 채널에 대 한 경계 사각형의 위치와 크기를 검색합니다.  
  
```  
void GetChannelRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *lprc*  
 에 대 한 포인터는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 함수가 반환할 때 채널의 위치와 크기를 포함 하는 개체의 경계 사각형입니다.  
  
### <a name="remarks"></a>설명  
 채널 스타일러스가 영역에 있는 슬라이더를 이동 하 고 강조를 포함 하는 범위를 선택 합니다.  
  
##  <a name="getlinesize"></a>  CSliderCtrl::GetLineSize  
 슬라이더 컨트롤에 대 한 줄의 크기를 검색 합니다.  
  
```  
int GetLineSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 슬라이더 컨트롤에 대 한 줄의 크기입니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 크기 슬라이더를 이동 하는 선 크기에 영향을 줍니다는 **TB_LINEUP** 및 **TB_LINEDOWN** 알림입니다. 선 크기에 대 한 기본 설정은 1입니다.  
  
##  <a name="getnumtics"></a>  CSliderCtrl::GetNumTics  
 슬라이더 컨트롤의 눈금 표시의 수를 검색 합니다.  
  
```  
UINT GetNumTics() const;  
```  
  
### <a name="return-value"></a>반환 값  
 슬라이더 컨트롤의 눈금 표시의 수입니다.  
  
##  <a name="getpagesize"></a>  CSliderCtrl::GetPageSize  
 슬라이더 컨트롤에 대 한 페이지의 크기를 검색합니다.  
  
```  
int GetPageSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 슬라이더 컨트롤에 대 한 페이지의 크기입니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 크기 슬라이더를 이동 하는 페이지 크기에 영향을 줍니다는 **TB_PAGEUP** 및 **TB_PAGEDOWN** 알림입니다.  
  
##  <a name="getpos"></a>  CSliderCtrl::GetPos  
 슬라이더 컨트롤에서 슬라이더의 현재 위치를 검색합니다.  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 위치입니다.  
  
##  <a name="getrange"></a>  CSliderCtrl::GetRange  
 슬라이더 컨트롤에서 슬라이더에 대 한 최대 및 최소 위치를 검색합니다.  
  
```  
void GetRange(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *nMin*  
 최소 위치를 수신 하는 정수에 대 한 참조입니다.  
  
 *최대*  
 최대 위치를 수신 하는 정수에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 이 함수에서 참조 하는 정수에 값을 복사 *nMin* 및 *최대*합니다.  
  
##  <a name="getrangemax"></a>  CSliderCtrl::GetRangeMax  
 슬라이더 컨트롤에서 슬라이더에 대 한 최대 위치를 검색합니다.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>반환 값  
 컨트롤의 최대 위치입니다.  
  
##  <a name="getrangemin"></a>  CSliderCtrl::GetRangeMin  
 슬라이더 컨트롤에서 슬라이더에 대 한 최소 위치를 검색합니다.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>반환 값  
 컨트롤의 최소 위치입니다.  
  
##  <a name="getselection"></a>  CSliderCtrl::GetSelection  
 슬라이더 컨트롤의 현재 선택의 시작 및 끝 위치를 검색합니다.  
  
```  
void GetSelection(
    int& nMin,  
    int& nMax) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *nMin*  
 현재 선택의 시작 위치를 수신 하는 정수에 대 한 참조입니다.  
  
 *최대*  
 현재 선택 항목의 끝 위치를 수신 하는 정수에 대 한 참조입니다.  
  
##  <a name="getthumblength"></a>  CSliderCtrl::GetThumbLength  
 현재 trackbar 컨트롤에서 슬라이더의 길이 검색합니다.  
  
```  
int GetThumbLength() const;  
```  
  
### <a name="return-value"></a>반환 값  
 픽셀 단위로 슬라이더의 길이입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [TBM_GETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760201) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="getthumbrect"></a>  CSliderCtrl::GetThumbRect  
 슬라이더 컨트롤의 슬라이더 (thumb)에 대 한 경계 사각형의 위치와 크기를 검색합니다.  
  
```  
void GetThumbRect(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *lprc*  
 에 대 한 포인터는 `CRect` 함수가 반환할 때 슬라이더에 대 한 경계 사각형을 포함 하는 개체입니다.  
  
##  <a name="gettic"></a>  CSliderCtrl::GetTic  
 슬라이더 컨트롤의 눈금 표시의 위치를 검색 합니다.  
  
```  
int GetTic(int nTic) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *nTic*  
 눈금 표시를 식별 하는 0부터 시작 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 위치 지정된 눈금 표시 또는-1 이면 *nTic* 유효한 인덱스를 지정 하지 않습니다.  
  
##  <a name="getticarray"></a>  CSliderCtrl::GetTicArray  
 슬라이더 컨트롤에 대 한 눈금 표시의 위치를 포함 하는 배열 주소를 검색 합니다.  
  
```  
DWORD* GetTicArray() const;  
```  
  
### <a name="return-value"></a>반환 값  
 슬라이더 컨트롤에 대 한 눈금 표시 위치를 포함 하는 배열의 주소입니다.  
  
##  <a name="getticpos"></a>  CSliderCtrl::GetTicPos  
 슬라이더 컨트롤의 눈금 표시의 현재 실제 위치를 검색합니다.  
  
```  
int GetTicPos(int nTic) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *nTic*  
 눈금 표시를 식별 하는 0부터 시작 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 실제 위치를 클라이언트 좌표로 지정된 눈금 표시 또는-1 이면 *nTic* 유효한 인덱스를 지정 하지 않습니다.  
  
##  <a name="gettooltips"></a>  CSliderCtrl::GetToolTips  
 있는 경우 슬라이더 컨트롤에 할당 된 도구 설명 컨트롤에 대 한 핸들을 검색 합니다.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 개체 또는 **NULL** 도구 설명을 사용 하지 않는 경우. 슬라이더 컨트롤 사용 하지 않는 경우는 **TBS_TOOLTIPS** 스타일, 반환 값은 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TBM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760209)Windows SDK에 설명 된 대로 합니다. 이 멤버 함수를 반환 하는 `CToolTipCtrl` 컨트롤에 대 한 핸들 대신 개체입니다.  
  
 슬라이더 컨트롤 스타일에 대 한 참조 [Trackbar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760147) Windows sdk에서입니다.  
  
##  <a name="setbuddy"></a>  CSliderCtrl::SetBuddy  
 Slider 컨트롤의 버디 창으로 창을 할당합니다.  
  
```  
CWnd* SetBuddy(
    CWnd* pWndBuddy,  
    BOOL fLocation = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *pWndBuddy*  
 에 대 한 포인터는 `CWnd` 슬라이더 컨트롤의 버디도 설정 될 개체입니다.  
  
 *fLocation*  
 버디 창의 표시할 위치를 지정 하는 값입니다. 이 값은 다음 중 하나일 수 있습니다.  
  
- **True 이면** trackbar 컨트롤을 사용 하는 경우 버디 트랙 표시줄의 왼쪽에 표시 됩니다는 `TBS_HORZ` 스타일입니다. Trackbar에서 사용 하는 경우는 `TBS_VERT` 스타일을 버디 trackbar 컨트롤 위에 나타납니다.  
  
- **FALSE** trackbar 컨트롤을 사용 하는 경우 버디 트랙 표시줄의 오른쪽에 표시 됩니다는 `TBS_HORZ` 스타일입니다. Trackbar에서 사용 하는 경우는 `TBS_VERT` 스타일을 버디 trackbar 컨트롤 아래에 나타납니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 이전에 해당 위치에 있는 슬라이더 컨트롤에 할당 된 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TBM_SETBUDDY](http://msdn.microsoft.com/library/windows/desktop/bb760213)Windows SDK에 설명 된 대로 합니다. 이 멤버 함수에 대 한 포인터를 사용 한다는 점에 유의 `CWnd` 창 핸들의 반환 값 및 매개 변수 대신 개체입니다.  
  
 슬라이더 컨트롤 스타일에 대 한 참조 [Trackbar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760147) Windows sdk에서입니다.  
  
##  <a name="setlinesize"></a>  CSliderCtrl::SetLineSize  
 슬라이더 컨트롤에 대 한 줄의 크기를 설정합니다.  
  
```  
int SetLineSize(int nSize);
```  
  
### <a name="parameters"></a>매개 변수  
 *nSize*  
 슬라이더 컨트롤의 새 줄 크기입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 줄 크기입니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 크기 슬라이더를 이동 하는 선 크기에 영향을 줍니다는 **TB_LINEUP** 및 **TB_LINEDOWN** 알림입니다.  
  
##  <a name="setpagesize"></a>  CSliderCtrl::SetPageSize  
 슬라이더 컨트롤에 대 한 페이지의 크기를 설정합니다.  
  
```  
int SetPageSize(int nSize);
```  
  
### <a name="parameters"></a>매개 변수  
 *nSize*  
 슬라이더 컨트롤의 새 페이지 크기입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 페이지 크기입니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 크기 슬라이더를 이동 하는 페이지 크기에 영향을 줍니다는 **TB_PAGEUP** 및 **TB_PAGEDOWN** 알림입니다.  
  
##  <a name="setpos"></a>  CSliderCtrl::SetPos  
 슬라이더 컨트롤에서 슬라이더의 현재 위치를 설정합니다.  
  
```  
void SetPos(int nPos);
```  
  
### <a name="parameters"></a>매개 변수  
 *nPos*  
 새 슬라이더 위치를 지정합니다.  
  
##  <a name="setrange"></a>  CSliderCtrl::SetRange  
 슬라이더 컨트롤에서 슬라이더에 대 한 범위 (최소 및 최대 위치)를 설정합니다.  
  
```  
void SetRange(
    int nMin,  
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 *nMin*  
 슬라이더에 대 한 최소 위치입니다.  
  
 *최대*  
 슬라이더에 대 한 최대 위치입니다.  
  
 *bRedraw*  
 다시 그리기 플래그입니다. 이 매개 변수가 **TRUE**, 범위 설정 되어 슬라이더 다시 않습니다; 그리고 그렇지 않으면 슬라이더 다시 그려지지 않습니다.  
  
##  <a name="setrangemax"></a>  CSliderCtrl::SetRangeMax  
 슬라이더 컨트롤에서 슬라이더에 대 한 최대 범위를 설정합니다.  
  
```  
void SetRangeMax(
    int nMax,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 *최대*  
 슬라이더에 대 한 최대 위치입니다.  
  
 *bRedraw*  
 다시 그리기 플래그입니다. 이 매개 변수가 **TRUE**, 범위 설정 되어 슬라이더 다시 않습니다; 그리고 그렇지 않으면 슬라이더 다시 그려지지 않습니다.  
  
##  <a name="setrangemin"></a>  CSliderCtrl::SetRangeMin  
 슬라이더 컨트롤에서 슬라이더에 대 한 최소 범위를 설정합니다.  
  
```  
void SetRangeMin(
    int nMin,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 *nMin*  
 슬라이더에 대 한 최소 위치입니다.  
  
 *bRedraw*  
 다시 그리기 플래그입니다. 이 매개 변수가 **TRUE**, 범위 설정 되어 슬라이더 다시 않습니다; 그리고 그렇지 않으면 슬라이더 다시 그려지지 않습니다.  
  
##  <a name="setselection"></a>  CSliderCtrl::SetSelection  
 슬라이더 컨트롤에서 현재 선택 영역의 시작 및 끝 위치를 설정합니다.  
  
```  
void SetSelection(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>매개 변수  
 *nMin*  
 슬라이더에 대 한 시작 위치입니다.  
  
 *최대*  
 슬라이더에 대 한 끝 위치입니다.  
  
##  <a name="setthumblength"></a>  CSliderCtrl::SetThumbLength  
 현재 trackbar 컨트롤에서 슬라이더의 길이 설정합니다.  
  
```  
void SetThumbLength(int nLength);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] *nLength*|픽셀 단위로 슬라이더의 길이입니다.|  
  
### <a name="remarks"></a>설명  
 Trackbar 컨트롤을 설정할 수는이 메서드에 필요 [TBS_FIXEDLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760147) 스타일입니다.  
  
 이 메서드는 전송 된 [TBM_SETTHUMBLENGTH](http://msdn.microsoft.com/library/windows/desktop/bb760234) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 변수를 정의 `m_sliderCtrl`, 즉 현재 trackbar 컨트롤에 액세스 하는 데 사용 합니다. 이 예제에서는 변수를 정의 `thumbLength`, 즉 trackbar 컨트롤의 스크롤 상자 구성 요소가 기본 길이 저장 하는 데 사용 합니다. 이러한 변수는 다음 예제에서 사용 됩니다.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s1#1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 두 번의 기본 길이에 trackbar 컨트롤의 스크롤 상자 구성 요소를 설정 합니다.  
  
 [!code-cpp[NVC_MFC_CSliderCtrl_s1#2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]  
  
##  <a name="settic"></a>  CSliderCtrl::SetTic  
 슬라이더 컨트롤의 눈금 표시의 위치를 설정합니다.  
  
```  
BOOL SetTic(int nTic);
```  
  
### <a name="parameters"></a>매개 변수  
 *nTic*  
 눈금 표시의 위치입니다. 이 매개 변수는 양수 값을 지정 해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 눈금 표시; 설정 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="setticfreq"></a>  CSliderCtrl::SetTicFreq  
 슬라이더에는 눈금 표시가 표시 되는 빈도 설정 합니다.  
  
```  
void SetTicFreq(int nFreq);
```  
  
### <a name="parameters"></a>매개 변수  
 *nFreq*  
 눈금 표시의 빈도입니다.  
  
### <a name="remarks"></a>설명  
 예를 들어 간격을 2로 설정 하는 경우 슬라이더의 범위에 있는 다른 모든 증분에 대 한 눈금 표시 됩니다. 빈도 1에 대 한 기본 설정은 (즉, 각 증가 범위에 연관 된 눈금 표시).  
  
 컨트롤을 만들어야 합니다는 `TBS_AUTOTICKS` 이 함수를 사용 하는 스타일입니다. 자세한 내용은 참조 [CSliderCtrl::Create](#create)합니다.  
  
##  <a name="settipside"></a>  CSliderCtrl::SetTipSide  
 위치가 trackbar 컨트롤에서 도구 설명 컨트롤 사용.  
  
```  
int SetTipSide(int nLocation);
```  
  
### <a name="parameters"></a>매개 변수  
 *n 위치*  
 도구 설명 컨트롤을 표시 하는 위치를 나타내는 값입니다. 가능한 값 목록은 Win32 메시지를 참조 하십시오. [TBM_SETTIPSIDE](http://msdn.microsoft.com/library/windows/desktop/bb760240)Windows SDK에 설명 된 대로 합니다.  
  
### <a name="return-value"></a>반환 값  
 도구 설명 컨트롤의 이전 위치를 나타내는 값입니다. 반환 값에 대 한 가능한 값 중 하나를 equals *n 위치*합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 **TBM_SETTIPSIDE**Windows SDK에 설명 된 대로 합니다. 슬라이더를 사용 하는 제어는 **TBS_TOOLTIPS** 표시 도구 설명 스타일입니다. 슬라이더 컨트롤 스타일에 대 한 참조 [Trackbar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760147) Windows sdk에서입니다.  
  
##  <a name="settooltips"></a>  CSliderCtrl::SetToolTips  
 슬라이더 컨트롤에 도구 설명 컨트롤을 할당합니다.  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>매개 변수  
 *pWndTip*  
 에 대 한 포인터는 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 슬라이더 컨트롤과 함께 사용할 도구 설명을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TBM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb760242)Windows SDK에 설명 된 대로 합니다. 슬라이더 컨트롤을으로 만들 때의 **TBS_TOOLTIPS** 스타일 슬라이더의 현재 위치를 표시 하 고 슬라이더를 옆에 표시 되는 기본 도구 설명 컨트롤을 만듭니다. 슬라이더 컨트롤 스타일에 대 한 참조 [Trackbar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760147) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CProgressCtrl 클래스](../../mfc/reference/cprogressctrl-class.md)
