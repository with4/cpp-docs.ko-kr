---
title: "CRectTracker 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRectTracker
- AFXEXT/CRectTracker
- AFXEXT/CRectTracker::CRectTracker
- AFXEXT/CRectTracker::AdjustRect
- AFXEXT/CRectTracker::Draw
- AFXEXT/CRectTracker::DrawTrackerRect
- AFXEXT/CRectTracker::GetHandleMask
- AFXEXT/CRectTracker::GetTrueRect
- AFXEXT/CRectTracker::HitTest
- AFXEXT/CRectTracker::NormalizeHit
- AFXEXT/CRectTracker::OnChangedRect
- AFXEXT/CRectTracker::SetCursor
- AFXEXT/CRectTracker::Track
- AFXEXT/CRectTracker::TrackRubberBand
- AFXEXT/CRectTracker::m_nHandleSize
- AFXEXT/CRectTracker::m_nStyle
- AFXEXT/CRectTracker::m_rect
- AFXEXT/CRectTracker::m_sizeMin
dev_langs:
- C++
helpviewer_keywords:
- CRectTracker [MFC], CRectTracker
- CRectTracker [MFC], AdjustRect
- CRectTracker [MFC], Draw
- CRectTracker [MFC], DrawTrackerRect
- CRectTracker [MFC], GetHandleMask
- CRectTracker [MFC], GetTrueRect
- CRectTracker [MFC], HitTest
- CRectTracker [MFC], NormalizeHit
- CRectTracker [MFC], OnChangedRect
- CRectTracker [MFC], SetCursor
- CRectTracker [MFC], Track
- CRectTracker [MFC], TrackRubberBand
- CRectTracker [MFC], m_nHandleSize
- CRectTracker [MFC], m_nStyle
- CRectTracker [MFC], m_rect
- CRectTracker [MFC], m_sizeMin
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f870ef92296636c8d27fc166d41cdefc54d1585
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="crecttracker-class"></a>CRectTracker 클래스
항목을을 표시, 이동, 다른 방식에서 크기를 조정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CRectTracker  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CRectTracker::CRectTracker](#crecttracker)|`CRectTracker` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRectTracker::AdjustRect](#adjustrect)|사각형의 크기를 조정할 때 호출 됩니다.|  
|[CRectTracker::Draw](#draw)|사각형을 렌더링합니다.|  
|[CRectTracker::DrawTrackerRect](#drawtrackerrect)|테두리를 그릴 때 호출 된 `CRectTracker` 개체입니다.|  
|[CRectTracker::GetHandleMask](#gethandlemask)|마스크를 가져오기 위해 호출 됩니다는 `CRectTracker` 항목의 크기 조정 핸들입니다.|  
|[CRectTracker::GetTrueRect](#gettruerect)|크기 조정 핸들을 포함 하 여 사각형의 너비와 높이 반환 합니다.|  
|[CRectTracker::HitTest](#hittest)|와 관련 된 커서의 현재 위치를 반환 하는 `CRectTracker` 개체입니다.|  
|[CRectTracker::NormalizeHit](#normalizehit)|적중 테스트 코드를 정규화합니다.|  
|[CRectTracker::OnChangedRect](#onchangedrect)|사각형 크기가 조정 되었거나 이동 되었음을 때 호출 됩니다.|  
|[CRectTracker::SetCursor](#setcursor)|사각형을 통해 해당 위치에 따라 커서를 설정합니다.|  
|[CRectTracker::Track](#track)|사각형을 조작할 수 있습니다.|  
|[Crecttracker:: Trackrubberband](#trackrubberband)|사용자 "고무 밴드"를 선택할 수 있습니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CRectTracker::m_nHandleSize](#m_nhandlesize)|크기 조정 핸들의 크기를 결정 합니다.|  
|[CRectTracker::m_nStyle](#m_nstyle)|현재 style(s) 추적기입니다.|  
|[M_rect](#m_rect)|현재 위치 (픽셀) 사각형입니다.|  
|[CRectTracker::m_sizeMin](#m_sizemin)|최소 너비와 높이 결정합니다.|  
  
## <a name="remarks"></a>설명  
 `CRectTracker`기본 클래스는 없습니다.  
  
 하지만 `CRectTracker` 클래스는 사용자가 그래픽 인터페이스를 사용 하 여 OLE 항목와 상호 작용할 수 있도록 설계 되었습니다, 용도 OLE 지원 응용 프로그램 제한 되지 않습니다. 사용할 수 있도록 사용자 인터페이스가 필요한 모든 곳에서 합니다.  
  
 `CRectTracker`테두리 단색 수 또는 점선입니다. 항목을 교차 무늬 테두리를 지정 또는 항목의 다양 한 상태를 나타내기 위해 빗살 무늬로로 중첩 수 있습니다. 외부 또는 내부에 8 개의 크기 조정 핸들을 배치할 수 있습니다 항목의 테두리입니다. (참조에 대 한 크기 조정 핸들 설명은 [GetHandleMask](#gethandlemask).) 마지막으로, 한 `CRectTracker` 항목의 크기를 조정 하는 동안 방향을 변경할 수 있습니다.  
  
 사용 하도록 `CRectTracker`, 생성 한 `CRectTracker` 개체와 표시 상태를 확인할 초기화 된 지정 합니다. 와 연결 된 OLE 항목의 현재 상태에 사용자 시각적 피드백을 제공 하려면이 인터페이스를 유도할 수 있습니다는 `CRectTracker` 개체입니다.  
  
 사용 하 여 대 한 자세한 내용은 `CRectTracker`, 문서를 참조 [추적기](../../mfc/trackers.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CRectTracker`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxext.h  
  
##  <a name="adjustrect"></a>CRectTracker::AdjustRect  
 추적 사각형 크기 조정 핸들을 사용 하 여 크기를 조정할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void AdjustRect(
    int nHandle,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>매개 변수  
 `nHandle`  
 사용 되는 핸들의 인덱스입니다.  
  
 `lpRect`  
 사각형의 현재 크기에 대 한 포인터입니다. (사각형의 크기는 해당 높이 너비에 의해 제공 됩니다.)  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 동작 사각형의 방향을 변경할 경우에만 통해 `Track` 및 `TrackRubberBand` 허용 반전 된 호출 됩니다.  
  
 끌기 작업 중 추적 사각형의 조정 제어 하려면이 함수를 재정의 합니다. 으로 지정 된 좌표를 조정 하는 한 가지 방법은 `lpRect` 반환 하기 전에.  
  
 직접 지원 하지 않는 특수 기능 `CRectTracker`와 같은 눈금에 또는 유지-가로 세로 비율,이 함수를 재정의 하 여 구현할 수 있습니다.  
  
##  <a name="crecttracker"></a>CRectTracker::CRectTracker  
 만들고 초기화는 `CRectTracker` 개체입니다.  
  
```  
CRectTracker();

 
CRectTracker(
    LPCRECT lpSrcRect,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpSrcRect`  
 사각형 개체의 좌표를 지정 합니다.  
  
 `nStyle`  
 스타일을 지정 된 `CRectTracker` 개체입니다. 다음과 같은 스타일 지원 됩니다.  
  
- **CRectTracker::solidLine** 실선 사각형 테두리에 대 한 사용 합니다.  
  
- **CRectTracker::dottedLine** 점선 사각형 테두리에 대 한 사용 합니다.  
  
- **CRectTracker::hatchedBorder** 사각형 테두리에 대 한 교차 무늬 패턴을 사용 합니다.  
  
- **CRectTracker::resizeInside** 크기 조정 핸들을 사각형 안에 배치 합니다.  
  
- **CRectTracker::resizeOutside** 영역 밖에 있는 핸들의 크기를 조정 합니다.  
  
- **CRectTracker::hatchInside** Hatched 패턴에서는 전체 사각형에 설명 합니다.  
  
### <a name="remarks"></a>설명  
 기본 생성자는 초기화는 `CRectTracker` 개체의 값으로 `lpSrcRect` 다른 크기 시스템 기본값으로 초기화 합니다. 매개 변수가 없는 개체가 생성 되는 경우는 `m_rect` 및 `m_nStyle` 데이터 멤버는 초기화 되지 않습니다.  
  
##  <a name="draw"></a>CRectTracker::Draw  
 사각형의 외부 선과 내부 영역을 그리는이 함수를 호출 합니다.  
  
```  
void Draw(CDC* pDC) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 그릴 장치 컨텍스트에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 추적기 스타일 그리기 수행 하는 방법을 결정 합니다. 에 대 한 생성자를 참조 하십시오. `CRectTracker` 사용할 수 있는 스타일에 대 한 자세한 내용은 합니다.  
  
##  <a name="drawtrackerrect"></a>CRectTracker::DrawTrackerRect  
 추적기의 위치가 변경 될 때마다 프레임 워크에서 호출 하는 동안 내부는 `Track` 또는 `TrackRubberBand` 멤버 함수입니다.  
  
```  
virtual void DrawTrackerRect(
    LPCRECT lpRect,  
    CWnd* pWndClipTo,  
    CDC* pDC,  
    CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect`  
 에 대 한 포인터는 `RECT` 그릴 사각형을 포함 하 합니다.  
  
 `pWndClipTo`  
 사각형 오려낸에서 사용 하 여 창에 대 한 포인터입니다.  
  
 `pDC`  
 그릴 장치 컨텍스트에 대 한 포인터입니다.  
  
 `pWnd`  
 그리기는 발생 하는 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 기본 구현에 대 한 호출에서는 `CDC::DrawFocusRect`는 점선으로 표시 된 사각형을 그립니다.  
  
 작업을 추적 하는 동안 다른 피드백을 제공 하려면이 함수를 재정의 합니다.  
  
##  <a name="gethandlemask"></a>CRectTracker::GetHandleMask  
 프레임 워크는 사각형의 크기 조정 핸들에 대 한 마스크를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual UINT GetHandleMask() const;  
```  
  
### <a name="return-value"></a>반환 값  
 마스크는 `CRectTracker` 항목의 크기 조정 핸들입니다.  
  
### <a name="remarks"></a>설명  
 크기 조정 핸들 양쪽 및 사각형의 모퉁이에 표시 됨을 셰이프 및 사각형의 크기를 제어 하려면 사용자입니다.  
  
 사각형에는 번호가 0-7 8 크기 조정 핸들에 있습니다. 각 크기 조정 핸들 나타내는 비트 마스크;에 해당 비트의 값은 2 ^  *n* 여기서  *n*  크기 조정 핸들 수입니다. 0-3 비트 이동 왼쪽 상단 시계 반대 방향으로 시작 하는 모퉁이 크기 조정 핸들에 해당 합니다. 크기 조정 핸들 시계 방향으로 맨 위부터 bits 4-7 측면에 해당 합니다. 다음 그림에는 사각형의 크기 조정 핸들 및 핸들 번호 및 값 크기 조정의 해당 보여 줍니다.  
  
 ![크기 조정 핸들 번호](../../mfc/reference/media/vc35dp1.gif "vc35dp1")  
  
 기본 구현은 **GetHandleMask** 크기 조정 핸들을 표시 하는 비트 마스크를 반환 합니다. 단일 비트에 있으면 해당 크기 조정 핸들에 그려집니다.  
  
 숨기 거 나 표시 된 크기 조정 핸들을 표시 하려면이 멤버 함수를 재정의 합니다.  
  
##  <a name="gettruerect"></a>CRectTracker::GetTrueRect  
 사각형의 좌표를 검색 하려면이 함수를 호출 합니다.  
  
```  
void GetTrueRect(LPRECT lpTrueRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpTrueRect`  
 에 대 한 포인터는 `RECT` 에서 장치를 포함할 구조 좌표는 `CRectTracker` 개체입니다.  
  
### <a name="remarks"></a>설명  
 사각형의 크기 높이 너비의 바깥쪽 테두리에 있는 모든 크기 조정 핸들을 포함 합니다. 를 반환 하면 `lpTrueRect` 는 항상 정규화 된 장치 좌표로 사각형입니다.  
  
##  <a name="hittest"></a>CRectTracker::HitTest  
 사용자가 크기 조정 핸들을 잡고 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
int HitTest(CPoint point) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `point`  
 테스트 하려면 장치 좌표 점입니다.  
  
### <a name="return-value"></a>반환 값  
 열거 형식에 따라 반환 되는 값 **CRectTracker::TrackerHit** 다음 값 중 하나일 수 있습니다.  
  
- **CRectTracker::hitNothing** -1  
  
- **CRectTracker::hitTopLeft** 0  
  
- **CRectTracker::hitTopRight** 1  
  
- **CRectTracker::hitBottomRight** 2  
  
- **CRectTracker::hitBottomLeft** 3  
  
- **CRectTracker::hitTop** 4  
  
- **CRectTracker::hitRight** 5  
  
- **CRectTracker::hitBottom** 6  
  
- **CRectTracker::hitLeft** 7  
  
- **CRectTracker::hitMiddle** 8  
  
##  <a name="m_nhandlesize"></a>CRectTracker::m_nHandleSize  
 크기를 픽셀 단위로는 `CRectTracker` 크기 조정 핸들입니다.  
  
```  
int m_nHandleSize;  
```  
  
### <a name="remarks"></a>설명  
 시스템 기본값을 사용 하 여 초기화 합니다.  
  
##  <a name="m_rect"></a>M_rect  
 사각형의 현재 위치를 클라이언트 좌표 (픽셀)입니다.  
  
```  
CRect m_rect;  
```  
  
##  <a name="m_sizemin"></a>CRectTracker::m_sizeMin  
 사각형의 최소 크기입니다.  
  
```  
CSize m_sizeMin;  
```  
  
### <a name="remarks"></a>설명  
 두 기본 값, **cx** 및 **cy**, 테두리 너비에 대 한 기본 시스템 값에서 계산 됩니다. 이 데이터 멤버에만 사용 되는 `AdjustRect` 멤버 함수입니다.  
  
##  <a name="m_nstyle"></a>CRectTracker::m_nStyle  
 사각형의 현재 스타일입니다.  
  
```  
UINT m_nStyle;  
```  
  
### <a name="remarks"></a>설명  
 참조 [CRectTracker::CRectTracker](#crecttracker) 가능한 스타일의 목록에 대 한 합니다.  
  
##  <a name="normalizehit"></a>CRectTracker::NormalizeHit  
 잠재적으로 반전 된 핸들을 변환 하려면이 함수를 호출 합니다.  
  
```  
int NormalizeHit(int nHandle) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nHandle`  
 사용자가 선택한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 정규화 된 핸들의 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 때 `CRectTracker::Track` 또는 `CRectTracker::TrackRubberBand` 라고 허용 반전와 x 축, y 축, 또는 둘 다 반전 사각형입니다. 이 경우 `HitTest` 사각형에 대해 반전도 되며 핸들을 반환 합니다. 이 피드백은 수정할 수는 데이터 구조를 사각형 부분의 사각형의 화면 위치에 따라 달라 지므로 그리기 커서 피드백에 대 한 적합 하지 않습니다.  
  
##  <a name="onchangedrect"></a>CRectTracker::OnChangedRect  
 추적기 사각형을 호출 하는 동안 변경 될 때마다 프레임 워크에서 호출 `Track`합니다.  
  
```  
virtual void OnChangedRect(const CRect& rectOld);
```  
  
### <a name="parameters"></a>매개 변수  
 *rectOld*  
 이전 장치 좌표가 포함 되어는 `CRectTracker` 개체입니다.  
  
### <a name="remarks"></a>설명  
 시간에이 함수가 호출 될 모든 피드백을 사용 하 여 그린 `DrawTrackerRect` 제거 되었습니다. 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다.  
  
 사각형의 크기가 조정 후 모든 작업을 수행 하려는 경우이 함수를 재정의 합니다.  
  
##  <a name="setcursor"></a>CRectTracker::SetCursor  
 위에 있는 동안 커서 모양을 변경 하려면이 함수 호출의 `CRectTracker` 개체의 영역입니다.  
  
```  
BOOL SetCursor(
    CWnd* pWnd,  
    UINT nHitTest) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 현재 커서를 포함 하는 창을를 가리킵니다.  
  
 `nHitTest`  
 이전 적중 횟수 테스트의 결과에서 `WM_SETCURSOR` 메시지입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 결과 추적기 사각형; 통해 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 사용자가 창 처리 하는 함수 내에서이 함수 호출의 `WM_SETCURSOR` 메시지 (일반적으로 `OnSetCursor`).  
  
##  <a name="track"></a>CRectTracker::Track  
 사각형의 크기를 조정 하는 것에 대 한 사용자 인터페이스를 표시 하려면이 함수를 호출 합니다.  
  
```  
BOOL Track(
    CWnd* pWnd,  
    CPoint point,  
    BOOL bAllowInvert = FALSE,  
    CWnd* pWndClipTo = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 사각형을 포함 하는 창 개체입니다.  
  
 `point`  
 장치 좌표 클라이언트 영역을 기준으로 현재 마우스 위치입니다.  
  
 `bAllowInvert`  
 경우 **TRUE**, 사각형 수 x 축 또는 y 축을 따라 반전 없으면 **FALSE**합니다.  
  
 `pWndClipTo`  
 이 창에 맞게 그리기 작업입니다. 경우 **NULL**, `pWnd` 클리핑 사각형으로 사용 됩니다.  
  
### <a name="return-value"></a>반환 값  
 ESC 키를 누르면 추적 프로세스는 중지 추적기에 저장 된 사각형은 변경 되지 않습니다 및 0이 반환 됩니다. 변경 내용이 커밋되고 추적기의 사각형에 새 위치 및/또는 크기는 마우스를 이동 하 고 마우스 왼쪽된 단추에서 손을 떼기를 기록 하 고 0이 아닌 값이 반환 됩니다.  
  
### <a name="remarks"></a>설명  
 이 일반적으로 호출에서 처리 하는 응용 프로그램의 함수 내에서 `WM_LBUTTONDOWN` 메시지 (일반적으로 `OnLButtonDown`).  
  
 이 함수는 사용자가 왼쪽된 마우스 단추를 놓을, ESC 키를 누르는 또는 오른쪽 마우스 단추를 누를 때까지 마우스가 캡처됩니다. 마우스 커서를 이동할 피드백 호출 하 여 업데이트 되어 `DrawTrackerRect` 및 `OnChangedRect`합니다.  
  
 경우 `bAllowInvert` 은 **TRUE**, x 축 또는 y 축에서 추적 사각형을 반전 시킬 수 있습니다.  
  
##  <a name="trackrubberband"></a>Crecttracker:: Trackrubberband  
 고무 밴드 선택을 수행 하려면이 함수를 호출 합니다.  
  
```  
BOOL TrackRubberBand(
    CWnd* pWnd,  
    CPoint point,  
    BOOL bAllowInvert = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 사각형을 포함 하는 창 개체입니다.  
  
 `point`  
 장치 좌표 클라이언트 영역을 기준으로 현재 마우스 위치입니다.  
  
 `bAllowInvert`  
 경우 **TRUE 이면** 사각형 수 x 축 또는 y 축을 따라 반전 없으면 **FALSE**합니다.  
  
### <a name="return-value"></a>반환 값  
 마우스를 이동 하 고 사각형 비어 있지 않으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 일반적으로 처리 하는 응용 프로그램의 함수 내에서 호출 됩니다는 `WM_LBUTTONDOWN` 메시지 (일반적으로 `OnLButtonDown`).  
  
 이 함수는 사용자가 왼쪽된 마우스 단추를 놓을, ESC 키를 누르는 또는 오른쪽 마우스 단추를 누를 때까지 마우스가 캡처됩니다. 마우스 커서를 이동할 피드백 호출 하 여 업데이트 되어 `DrawTrackerRect` 및 `OnChangedRect`합니다.  
  
 추적의 오른쪽 핸들에서 고무 밴드 형식 항목을 선택 하 여 수행 됩니다. 반전 허용 되는 경우 사각형 중 하나를 왼쪽 또는 아래쪽 및 오른쪽으로 끌어서 크기를 조정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 추적기](../../visual-cpp-samples.md)   
 [MFC 샘플 DRAWCLI](../../visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleResizeBar 클래스](../../mfc/reference/coleresizebar-class.md)   
 [CRect 클래스](../../atl-mfc-shared/reference/crect-class.md)
