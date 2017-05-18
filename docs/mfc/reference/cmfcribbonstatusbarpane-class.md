---
title: "CMFCRibbonStatusBarPane 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBarPane class
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
caps.latest.revision: 31
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
ms.openlocfilehash: a101e50f55efab44e4cb66d314b2426228dbc5c0
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFCRibbonStatusBarPane 클래스
`CMFCRibbonStatusBarPane` 리본 상태 표시줄에 추가할 수 있는 리본 요소를 구현 하는 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonStatusBarPane : public CMFCRibbonButton  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|`CMFCRibbonStatusBarPane` 개체를 생성하고 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|잘림 없이 창에 표시 될 수 있는 가장 긴 텍스트 문자열을 정의 하는 문자열을 반환 합니다.|  
|[CMFCRibbonStatusBarPane::GetTextAlign](#gettextalign)|텍스트 맞춤의 현재 설정을 반환합니다.|  
|[CMFCRibbonStatusBarPane::IsAnimation](#isanimation)|애니메이션 진행 중인지 여부를 결정 합니다.|  
|[CMFCRibbonStatusBarPane::IsExtended](#isextended)|창에서 리본 메뉴 상태 표시줄의 확장된 된 영역에 있는지 여부를 결정 합니다.|  
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|(재정의 [CMFCRibbonButton::OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder).)|  
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|(재정의 [CMFCRibbonButton::OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|  
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|잘림 없이 창에 표시 될 수 있는 가장 긴 텍스트 문자열을 정의 합니다.|  
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|애니메이션에 사용할 수 있는 이미지 목록 창에 할당 합니다.|  
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|텍스트 맞춤을 설정합니다.|  
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|창에 할당 하는 애니메이션을 시작 합니다.|  
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|창에 할당 하는 애니메이션을 중지 합니다. 입니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|창에 할당 하는 애니메이션 중지 될 때 프레임 워크에 의해 호출 됩니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CMFCRibbonStatusBarPane` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 예제를 생성 하는 방법을 보여 줍니다는 `CMFCRibbonStatusBarPane` 개체, 상태 표시줄 창의 레이블의 텍스트 맞춤을 설정 하 고, 잘림 없이 상태 표시줄 창에 표시 될 수 있습니다, 애니메이션을 시작 하 고 애니메이션에 사용할 수 있는 이미지 목록을 상태 표시줄 창에 연결 하는 가장 긴 텍스트를 정의 합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp #&2;](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxribbonstatusbarpane.h  
  
##  <a name="cmfcribbonstatusbarpane"></a>CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane  
 상태 표시줄에 창 개체를 생성 합니다.  
  
```  
CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    BOOL bIsStatic=FALSE,  
    HICON hIcon=NULL,  
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nCmdID`  
 창의 명령 ID를 지정합니다.  
  
 [in] `lpszText`  
 창에 표시 되는 텍스트 문자열을 지정 합니다.  
  
 [in] `bIsStatic`  
 경우 `TRUE`, 상태 창에 강조 표시 하거나 클릭 하 여 선택한 수 없습니다.  
  
 [in] `hIcon`  
 창에 표시 될 아이콘에 대 한 핸들을 지정 합니다.  
  
 [in] `lpszAlmostLargeText`  
 창에 표시 될 수 있는 가장 긴 텍스트 문자열을 지정 합니다.  
  
 [in] `hBmpAnimationList`  
 애니메이션에 사용 되는 이미지 목록에 대 한 핸들을 지정 합니다.  
  
 [in] `cxAnimation`  
 애니메이션에 사용 되는 이미지 목록에 있는 아이콘의 픽셀에서 너비를 지정 합니다.  
  
 [in] `clrTrnsp`  
 애니메이션에 사용 되는 이미지 목록에서 이미지의 투명색을 지정 합니다.  
  
 [in] `uiAnimationListResID`  
 애니메이션에 사용 되는 이미지 목록의 리소스 ID를 지정 합니다.  
  
##  <a name="getalmostlargetext"></a>CMFCRibbonStatusBarPane::GetAlmostLargeText  
 상태 표시줄 창에 표시할 수 있는 가장 긴 텍스트 문자열을 가져옵니다.  
  
```  
LPCTSTR GetAlmostLargeText() const;  
```  
  
### <a name="return-value"></a>반환 값  
 상태 표시줄 창에 표시할 수 있는 가장 긴 텍스트 문자열입니다.  
  
##  <a name="gettextalign"></a>CMFCRibbonStatusBarPane::GetTextAlign  
 상태 표시줄 창의 레이블의 텍스트 맞춤의 현재 설정을 가져옵니다.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>반환 값  
 다음 중 하나가 될 수 있는 현재 텍스트 맞춤:  
  
-   TA_LEFT  
  
-   TA_CENTER  
  
-   TA_RIGHT 합니다.  
  
##  <a name="isanimation"></a>CMFCRibbonStatusBarPane::IsAnimation  
 애니메이션 진행 중인지 여부를 결정 합니다.  
  
```  
BOOL IsAnimation() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`애니메이션은 진행 중인 경우 `FALSE` 그렇지 않은 경우.  
  
##  <a name="isextended"></a>CMFCRibbonStatusBarPane::IsExtended  
 창에서 리본 메뉴 상태 표시줄의 확장된 된 영역에 있는지 여부를 결정 합니다.  
  
```  
BOOL IsExtended() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`창 상태 표시줄 확장된 영역이 됩니다. 그렇지 않으면 `FALSE`입니다.  
  
##  <a name="ondrawborder"></a>CMFCRibbonStatusBarPane::OnDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBorder(CDC*);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `CDC*`  
  
### <a name="remarks"></a>주의  
  
##  <a name="onfillbackground"></a>CMFCRibbonStatusBarPane::OnFillBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="onfinishanimation"></a>CMFCRibbonStatusBarPane::OnFinishAnimation  
 프레임 워크의 창에 할당 된 애니메이션 종료 될 때이 메서드를 호출 합니다.  
  
```  
virtual void OnFinishAnimation();
```  
  
### <a name="remarks"></a>주의  
 `StopAnimation`메서드 호출의 `OnFinishAnimation` 애니메이션 종료 될 때 데이터를 정리 하는 데 사용할 수 있는 메서드.  
  
##  <a name="setalmostlargetext"></a>CMFCRibbonStatusBarPane::SetAlmostLargeText  
 잘림 없이 상태 표시줄 창에 표시 될 수 있는 가장 긴 텍스트를 정의 합니다.  
  
```  
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszAlmostLargeText`  
 잘림 없이 상태 표시줄 창에 표시 될 수 있는 가장 긴 문자열을 지정 합니다.  
  
### <a name="remarks"></a>주의  
 텍스트의 크기를 계산 하는 라이브러리를 `lpszAlmostLargeText` 지정 하 고 그에 따라 창 크기를 조정 합니다. 텍스트는 것도 맞지 않을 경우 창에서 잘립니다.  
  
##  <a name="setanimationlist"></a>CMFCRibbonStatusBarPane::SetAnimationList  
 애니메이션에 사용할 수 있는 이미지 목록 상태 표시줄 창에 연결 합니다.  
  
```  
void SetAnimationList(
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hBmpAnimationList`  
 이미지 목록에 대 한 핸들을 지정합니다.  
  
 [in] `cxAnimation`  
 이미지 목록에서 프레임의 픽셀에서 너비를 지정합니다.  
  
 [in] `clrTransp`  
 이미지 목록의 투명 한 색을 지정합니다.  
  
 [in] `uiAnimationListResID`  
 이미지 목록의 리소스 ID를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이미지 목록의 상태 표시줄 창;에 성공적으로 연결 된 경우 `FALSE` 그렇지 않은 경우.  
  
##  <a name="settextalign"></a>CMFCRibbonStatusBarPane::SetTextAlign  
 상태 표시줄 창의 레이블의 텍스트 맞춤을 설정합니다.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nAlign`  
 텍스트 맞춤을 지정합니다.  
  
### <a name="remarks"></a>주의  
 `nAlign`다음 값 중 하나일 수 있습니다.  
  
- `TA_LEFT`: 왼쪽 맞춤  
  
- `TA_CENTER:`가운데 맞춤  
  
- `TA_RIGHT:`오른쪽 맞춤  
  
##  <a name="startanimation"></a>CMFCRibbonStatusBarPane::StartAnimation  
 창에 할당 하는 애니메이션을 시작 합니다.  
  
```  
void StartAnimation(
    UINT nFrameDelay=500,  
    UINT nDuration=-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nFrameDelay`  
 애니메이션 프레임 속도 밀리초 단위로 지정합니다.  
  
 [in] `nDuration`  
 밀리초 단위로 애니메이션을 재생 시간을 지정 합니다. 무한 루프에 대 한-1을 사용 합니다.  
  
### <a name="remarks"></a>주의  
 호출 하기 전에 이미지 목록에 대 한 핸들을 지정 해야 `StartAnimation` 를 사용 하 여 `SetAnimationList`합니다.  
  
##  <a name="stopanimation"></a>CMFCRibbonStatusBarPane::StopAnimation  
 상태 표시줄 창에 할당 하는 애니메이션을 중지 합니다.  
  
```  
void StopAnimation();
```  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton 클래스](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonStatusBar 클래스](../../mfc/reference/cmfcribbonstatusbar-class.md)

