---
title: "CMFCCaptionButton 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCCaptionButton class
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
caps.latest.revision: 28
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
ms.openlocfilehash: 9d6342f87622c34b671ad5ea443eb78ffd8c3838
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccaptionbutton-class"></a>CMFCCaptionButton 클래스
`CMFCCaptionButton` 클래스는 도킹 창 또는 미니 프레임 창의 캡션 표시줄에 표시 되는 단추를 구현 합니다. 일반적으로 프레임워크는 캡션 단추를 자동으로 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="constructors"></a>생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|CMFCCaptionButton 개체를 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCCaptionButton::GetHit](#gethit)|단추에 표시 되는 명령을 반환 합니다.|  
|[CMFCCaptionButton::GetIconID](#geticonid)|단추와 연결 된 이미지 ID를 반환 합니다.|  
|[CMFCCaptionButton::GetRect](#getrect)|단추의 사각형을 반환 합니다.|  
|[CMFCCaptionButton::GetSize](#getsize)|단추의 높이 너비를 반환합니다.|  
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|제목 표시줄 높이 미니 크기로 설정 되어 있는지 여부를 나타냅니다.|  
|[CMFCCaptionButton::Move](#move)|단추 그리기 위치와 상태를 표시 하는 창 설정합니다.|  
|[CMFCCaptionButton::OnDraw](#ondraw)|캡션 단추를 그립니다.|  
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|제목 표시줄의 미니 크기를 설정합니다.|  
  
## <a name="remarks"></a>주의  
 클래스를 파생할 수 [CPaneFrameWnd 클래스](../../mfc/reference/cpaneframewnd-class.md) 보호 된 메서드를 사용 하 여 `AddButton`에 미니 프레임 창의 캡션 단추를 추가 합니다.  
  
 CPaneFrameWnd.h 두 가지 유형의 캡션 단추에 대 한 명령 Id를 정의합니다.  
  
- `AFX_CAPTION_BTN_PIN`핀 단추를 표시 하는 경우 도킹 창 자동 숨기기 모드를 지원 합니다.  
  
- `AFX_CAPTION_BTN_CLOSE`를 표시 하는 **닫기** 단추는 창 종료 하거나 숨길 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 생성 하는 방법을 한 `CMFCCaptionButton` 개체 및 제목 표시줄의 미니 크기를 설정 합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp #&43;](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcaptionbutton.h  
  
##  <a name="cmfccaptionbutton"></a>CMFCCaptionButton::CMFCCaptionButton  
 `CMFCCaptionButton` 개체를 생성합니다.  
  
```  
CMFCCaptionButton();

 
CMFCCaptionButton(
    UINT nHit,  
    BOOL bLeftAlign = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nHit`  
 단추와 연결된 명령입니다.  
  
 [in] `bLeftAlign`  
 단추는 왼쪽으로 정렬 되는지 여부를 지정 합니다.  
  
 다음 표에서 가능한 값은 `nHit` 매개 변수입니다.  
  
|값|명령|  
|-----------|-------------|  
|`AFX_HTCLOSE`|닫기 단추입니다.|  
|`HTMINBUTTON`|단추를 최소화 합니다.|  
|`HTMAXBUTTON`|최대화 단추입니다.|  
|`AFX_HTLEFTBUTTON`|왼쪽된 화살표 단추입니다.|  
|`AFX_HTRIGHTBUTTON`|오른쪽 화살표 단추입니다.|  
|`AFX_HTMENU`|아래쪽 화살표 메뉴 단추입니다.|  
|`HTNOWHERE`|기본값입니다. 없는 명령을 나타냅니다.|  
  
### <a name="remarks"></a>주의  
 기본적으로는 캡션 단추 명령에 연결 되지 않습니다.  
  
 캡션 단추의 오른쪽 또는 왼쪽에 정렬 됩니다.  
  
##  <a name="gethit"></a>CMFCCaptionButton::GetHit  
 단추에 표시 되는 명령을 반환 합니다.  
  
```  
UINT GetHit() const;  
```  
  
### <a name="return-value"></a>반환 값  
 단추에 표시 되는 명령입니다.  
  
 다음 표에서 가능한 반환 값을 보여 줍니다.  
  
|값|명령|  
|-----------|-------------|  
|`AFX_HTCLOSE`|닫기 단추입니다.|  
|`HTMINBUTTON`|단추를 최소화 합니다.|  
|`HTMAXBUTTON`|최대화 단추입니다.|  
|`AFX_HTLEFTBUTTON`|왼쪽된 화살표 단추입니다.|  
|`AFX_HTRIGHTBUTTON`|오른쪽 화살표 단추입니다.|  
|`AFX_HTMENU`|아래쪽 화살표 메뉴 단추입니다.|  
|`HTNOWHERE`|기본값입니다. 없는 명령을 나타냅니다.|  
  
##  <a name="geticonid"></a>CMFCCaptionButton::GetIconID  
 단추와 연결 된 이미지 ID를 반환 합니다.  
  
```  
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,  
    BOOL bMaximized = FALSE) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bHorz`  
 `TRUE`왼쪽 또는 오른쪽 화살표 이미지 Id입니다. `FALSE` 위쪽 또는 아래쪽 화살표 이미지 Id입니다.  
  
 [in] `bMaximized`  
 `TRUE`최대화 이미지 ID입니다. `FALSE` 는 최소화 이미지 id입니다.  
  
### <a name="return-value"></a>반환 값  
 이미지 id입니다.  
  
### <a name="remarks"></a>주의  
 매개 변수는 최소화에 대 한 이미지 Id를 지정 하거나 캡션 단추를 최대화 합니다.  
  
##  <a name="getrect"></a>CMFCCaptionButton::GetRect  
 단추의 사각형을 반환 합니다.  
  
```  
virtual CRect GetRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 단추 위치를 나타내는 사각형입니다.  
  
### <a name="remarks"></a>주의  
 단추는 표시 되지 않는 경우 반환 되는 크기는 0입니다.  
  
##  <a name="getsize"></a>CMFCCaptionButton::GetSize  
 단추의 높이 너비를 반환합니다.  
  
```  
static CSize GetSize();
```  
  
### <a name="return-value"></a>반환 값  
 단추의 외부 크기입니다.  
  
### <a name="remarks"></a>주의  
 반환 되는 크기 단추 여백 및 테두리를 포함 합니다.  
  
##  <a name="isminiframebutton"></a>CMFCCaptionButton::IsMiniFrameButton  
 제목 표시줄 높이 미니 크기로 설정 되어 있는지 여부를 나타냅니다.  
  
```  
BOOL IsMiniFrameButton() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`캡션이 미니 size;로 설정 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="move"></a>CMFCCaptionButton::Move  
 단추 그리기 위치와 상태를 표시 하는 창 설정합니다.  
  
```  
void Move(
    const CPoint& ptTo,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `ptTo`  
 새 위치입니다.  
  
 [in] `bHide`  
 [] 단추의 표시 여부를 나타냅니다.  
  
##  <a name="ondraw"></a>CMFCCaptionButton::OnDraw  
 캡션 단추를 그립니다.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    BOOL bActive,  
    BOOL bHorz = TRUE,  
    BOOL bMaximized = TRUE,  
    BOOL bDisabled = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 단추에 대 한 장치 컨텍스트에 대 한 포인터입니다.  
  
 [in] `bActive`  
 활성 단추 이미지를 그릴 것인지 지정 합니다.  
  
 [in] `bHorz`  
 파생된 클래스에서 사용 하기 위해 예약 되어 있습니다.  
  
 [in] `bMaximized`  
 최대화 단추 이미지를 그릴 것인지 지정 합니다.  
  
 [in] `bDisabled`  
 활성화 된 단추 이미지를 그릴 것인지 지정 합니다.  
  
### <a name="remarks"></a>주의  
 `bMaximized` 매개 변수는 단추는 최대화 때 사용 또는 최소화 단추입니다.  
  
##  <a name="setminiframebutton"></a>CMFCCaptionButton::SetMiniFrameButton  
 제목 표시줄의 미니 크기를 설정합니다.  
  
```  
void SetMiniFramebutton(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bSet`  
 `TRUE`미니 제목 표시줄 높이 대 한 `FALSE` 기본 제목 표시줄 높이 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPaneFrameWnd 클래스](../../mfc/reference/cpaneframewnd-class.md)   
 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md)

