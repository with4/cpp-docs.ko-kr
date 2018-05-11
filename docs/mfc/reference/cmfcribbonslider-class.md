---
title: CMFCRibbonSlider 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMax
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMin
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRegularSize
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetZoomIncrement
- AFXRIBBONSLIDER/CMFCRibbonSlider::HasZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::OnDraw
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetRange
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomIncrement
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSlider [MFC], CMFCRibbonSlider
- CMFCRibbonSlider [MFC], GetPos
- CMFCRibbonSlider [MFC], GetRangeMax
- CMFCRibbonSlider [MFC], GetRangeMin
- CMFCRibbonSlider [MFC], GetRegularSize
- CMFCRibbonSlider [MFC], GetZoomIncrement
- CMFCRibbonSlider [MFC], HasZoomButtons
- CMFCRibbonSlider [MFC], OnDraw
- CMFCRibbonSlider [MFC], SetPos
- CMFCRibbonSlider [MFC], SetRange
- CMFCRibbonSlider [MFC], SetZoomButtons
- CMFCRibbonSlider [MFC], SetZoomIncrement
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a4264f26028db4c581fe1dc143905ac0ffc8f66
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribbonslider-class"></a>CMFCRibbonSlider 클래스
`CMFCRibbonSlider` 클래스는 리본 표시줄 또는 리본 메뉴 상태 표시줄에 추가할 수 있는 슬라이더 컨트롤을 구현 합니다. 리본 슬라이더 컨트롤은 Office 2007 응용 프로그램의 확대/축소 슬라이더와 유사합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonSlider : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonSlider::CMFCRibbonSlider](#cmfcribbonslider)|생성 하 고 리본 슬라이더 컨트롤을 초기화 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonSlider::GetPos](#getpos)|슬라이더 컨트롤의 현재 위치를 반환합니다.|  
|[CMFCRibbonSlider::GetRangeMax](#getrangemax)|슬라이더의 최대값을 반환 합니다.|  
|[CMFCRibbonSlider::GetRangeMin](#getrangemin)|슬라이더의 최소값을 반환 합니다.|  
|[CMFCRibbonSlider::GetRegularSize](#getregularsize)|리본 요소의 보통 크기를 반환합니다. (재정의 [cmfcribbonbaseelement:: Getregularsize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonSlider::GetZoomIncrement](#getzoomincrement)|슬라이더 컨트롤에 대 한 확대/축소 증가값의 크기를 반환합니다.|  
|[CMFCRibbonSlider::HasZoomButtons](#haszoombuttons)|에 있는 슬라이더 확대/축소 단추에 있는지 여부를 지정 합니다.|  
|[CMFCRibbonSlider::OnDraw](#ondraw)|리본 요소를 그리기 위해 프레임워크에서 호출됩니다. (재정의 [cmfcribbonbaseelement:: Ondraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonSlider::SetPos](#setpos)|슬라이더 컨트롤의 현재 위치를 설정합니다.|  
|[CMFCRibbonSlider::SetRange](#setrange)|최소값과 최대값을 설정 하 여 슬라이더 컨트롤의 범위를 지정 합니다.|  
|[CMFCRibbonSlider::SetZoomButtons](#setzoombuttons)|표시 하거나 확대/축소 단추를 숨깁니다.|  
|[CMFCRibbonSlider::SetZoomIncrement](#setzoomincrement)|슬라이더 컨트롤에 대 한 확대/축소 증가값의 크기를 설정합니다.|  
  
## <a name="remarks"></a>설명  
 사용할 수는 `SetRange` 슬라이더에 대 한 확대/축소 단위로 범위를 구성 하는 메서드. 슬라이더의 현재 위치를 사용 하 여 설정할 수 있습니다는 `SetPos` 메서드.  
  
 사용 하 여 슬라이더 컨트롤의 왼쪽 및 오른쪽에 순환 확대/축소 단추를 표시할 수 있습니다는 `SetZoomButtons` 메서드. 기본적으로는 가로 슬라이더, 왼쪽된 확대/축소 단추 빼기 기호를 표시 하 고 오른쪽 확대/축소 단추를 사용 하는 더하기 기호를 표시 합니다.  
  
 `SetZoomIncrement` 메서드 정의를 추가 하거나 확대/축소 단추를 클릭 하면 현재 위치에서 뺄 증가 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는에서 다양 한 메서드를 사용 하는 `CMFCRibbonSlider` 슬라이더의 속성을 설정 하는 클래스입니다. 이 예제에서는 작성 방법을 보여 주는 `CMFCRibbonSlider` 개체, 확대/축소 단추를 표시 하 고 슬라이더 컨트롤의 현재 위치를 설정 및 슬라이더 컨트롤에 대 한 값의 범위를 설정 합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxribbonslider.h  
  
##  <a name="cmfcribbonslider"></a>  CMFCRibbonSlider::CMFCRibbonSlider  
 리본 슬라이더를 생성 합니다.  
  
```  
CMFCRibbonSlider(
    UINT nID,  
    int nWidth=100);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nID`  
 슬라이더의 id입니다.  
  
 [in]. `nWidth`  
 슬라이더 너비 (픽셀)에서입니다.  
  
### <a name="remarks"></a>설명  
 생성 되는 리본 슬라이더 `nWidth` 픽셀로 패널 범주 슬라이더 추가 됩니다. 기본적으로 슬라이더는 가로입니다.  
  
##  <a name="getpos"></a>  CMFCRibbonSlider::GetPos  
 슬라이더 컨트롤의 현재 위치를 반환합니다.  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>반환 값  
 슬라이더의 시작 부분에 상대적인 위치를 나타내는 슬라이더 컨트롤의 현재 위치입니다.  
  
##  <a name="getrangemax"></a>  CMFCRibbonSlider::GetRangeMax  
 슬라이더 컨트롤에 있는 슬라이더 이동할 수 있는 슬라이더의 최대 증가 가져옵니다.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>반환 값  
 슬라이더 컨트롤에 있는 슬라이더 이동할 수 있는 슬라이더의 최대 증가 합니다.  
  
##  <a name="getrangemin"></a>  CMFCRibbonSlider::GetRangeMin  
 슬라이더 슬라이더 컨트롤에 이동할 수 있는 최소 간격은 반환 합니다.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>반환 값  
 최소 증가값을 슬라이더 슬라이더 컨트롤에 이동할 수 있습니다.  
  
##  <a name="getregularsize"></a>  CMFCRibbonSlider::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getzoomincrement"></a>  CMFCRibbonSlider::GetZoomIncrement  
 슬라이더 컨트롤에 대 한 확대/축소 증가값을 가져옵니다.  
  
```  
int GetZoomIncrement() const;  
```  
  
### <a name="return-value"></a>반환 값  
 슬라이더 컨트롤에 대 한 확대/축소 증가 합니다.  
  
##  <a name="haszoombuttons"></a>  CMFCRibbonSlider::HasZoomButtons  
 에 있는 슬라이더 확대/축소 단추에 있는지 여부를 지정 합니다.  
  
```  
BOOL HasZoomButtons() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 에 있는 슬라이더 확대/축소 단추가;의 경우 `FALSE` 그렇지 않은 경우.  
  
##  <a name="ondraw"></a>  CMFCRibbonSlider::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
  
### <a name="remarks"></a>설명  
  
##  <a name="setpos"></a>  CMFCRibbonSlider::SetPos  
 슬라이더 컨트롤의 현재 위치를 설정 합니다.  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nPos`  
 슬라이더에 대해 설정할 위치를 지정 합니다. 슬라이더의 시작 부분에 상대적인 위치가입니다.  
  
 [in] `bRedraw`  
 경우 `TRUE`, 슬라이더 다시 그려집니다.  
  
##  <a name="setrange"></a>  CMFCRibbonSlider::SetRange  
 슬라이더 컨트롤에 대 한 값의 범위를 설정 합니다.  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nMin`  
 슬라이더 컨트롤의 최소값을 지정합니다.  
  
 [in] `nMax`  
 슬라이더 컨트롤의 최대값을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 최소값과 최대값을 설정 하 여 슬라이더 컨트롤에 대 한 값의 범위를 지정 합니다.  
  
##  <a name="setzoombuttons"></a>  CMFCRibbonSlider::SetZoomButtons  
 확대/축소 단추의 표시 또는 숨기기  
  
```  
void SetZoomButtons(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in]. `bSet`  
 `TRUE` 확대/축소 단추를 표시 하려면 `FALSE` 을 숨기기 위해.  
  
##  <a name="setzoomincrement"></a>  CMFCRibbonSlider::SetZoomIncrement  
 슬라이더 컨트롤에 대 한 확대/축소 증분을 설정 합니다.  
  
```  
void SetZoomIncrement(int nZoomIncrement);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nZoomIncrement`  
 슬라이더 컨트롤의 확대/축소 증분 값을 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement 클래스](../../mfc/reference/cmfcribbonbaseelement-class.md)
