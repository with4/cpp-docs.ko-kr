---
title: "CMFCRibbonSlider 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonSlider
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSlider class
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
caps.latest.revision: 43
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
ms.openlocfilehash: 9f05ae7d0f3e1775a3321928867471749e11e679
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonslider-class"></a>CMFCRibbonSlider 클래스
`CMFCRibbonSlider` 클래스는 리본 또는 리본 상태 표시줄에 추가할 수 있는 슬라이더 컨트롤을 구현 합니다. 리본 슬라이더 컨트롤은 Office 2007 응용 프로그램의 확대/축소 슬라이더와 유사합니다.  
  
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
|[CMFCRibbonSlider::GetRangeMin](#getrangemin)|슬라이더의 최소값을 반환합니다.|  
|[CMFCRibbonSlider::GetRegularSize](#getregularsize)|리본 요소의 보통 크기를 반환합니다. (재정의 [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonSlider::GetZoomIncrement](#getzoomincrement)|확대/축소 슬라이더 컨트롤에 대 한 증가값의 크기를 반환 합니다.|  
|[CMFCRibbonSlider::HasZoomButtons](#haszoombuttons)|슬라이더 확대/축소 단추에 있는지 여부를 지정 합니다.|  
|[CMFCRibbonSlider::OnDraw](#ondraw)|리본 요소를 그리기 위해 프레임워크에서 호출됩니다. (재정의 [CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonSlider::SetPos](#setpos)|슬라이더 컨트롤의 현재 위치를 설정합니다.|  
|[CMFCRibbonSlider::SetRange](#setrange)|최소값과 최대값을 설정 하 여 슬라이더 컨트롤의 범위를 지정 합니다.|  
|[CMFCRibbonSlider::SetZoomButtons](#setzoombuttons)|표시 하거나 확대/축소 단추를 숨깁니다.|  
|[CMFCRibbonSlider::SetZoomIncrement](#setzoomincrement)|확대/축소 슬라이더 컨트롤에 대 한 증가값의 크기를 설정합니다.|  
  
## <a name="remarks"></a>주의  
 사용할 수는 `SetRange` 슬라이더에 대 한 확대/축소 간격의 범위를 구성 하는 방법입니다. 사용 하 여 슬라이더의 현재 위치를 설정할 수는 `SetPos` 메서드.  
  
 사용 하 여 슬라이더 컨트롤의 왼쪽 및 오른쪽에 순환 확대/축소 단추를 표시할 수는 `SetZoomButtons` 메서드. 기본적으로 가로 슬라이더는, 왼쪽된 확대/축소 단추를 사용 하는 빼기 기호를 표시 하 고 오른쪽 확대/축소 단추를 사용 하는 더하기 기호를 표시 합니다.  
  
 `SetZoomIncrement` 메서드 정의에 추가 하거나 확대/축소 단추를 클릭할 때 현재 위치에서 뺄 증가 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 다양 한 메서드를 사용 하는 방법의 `CMFCRibbonSlider` 슬라이더의 속성을 설정 하는 클래스입니다. 예제를 생성 하는 방법을 보여 줍니다는 `CMFCRibbonSlider` 개체, 확대/축소 단추를 표시 하 고 슬라이더 컨트롤의 현재 위치를 설정 및 슬라이더 컨트롤에 대 한 값의 범위를 설정 합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp #&12;](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxribbonslider.h  
  
##  <a name="a-namecmfcribbonslidera--cmfcribbonslidercmfcribbonslider"></a><a name="cmfcribbonslider"></a>CMFCRibbonSlider::CMFCRibbonSlider  
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
  
### <a name="remarks"></a>주의  
 생성 되는 리본 슬라이더 `nWidth` 픽셀로 슬라이더를 추가 하는 위치 패널 범주에 있습니다. 기본적으로 슬라이더를 가로로 표시 됩니다.  
  
##  <a name="a-namegetposa--cmfcribbonslidergetpos"></a><a name="getpos"></a>CMFCRibbonSlider::GetPos  
 슬라이더 컨트롤의 현재 위치를 반환합니다.  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>반환 값  
 슬라이더의 시작 부분에 상대적인 위치를 나타내는 슬라이더 컨트롤의 현재 위치입니다.  
  
##  <a name="a-namegetrangemaxa--cmfcribbonslidergetrangemax"></a><a name="getrangemax"></a>CMFCRibbonSlider::GetRangeMax  
 슬라이더 컨트롤에 슬라이더를 이동할 수 있는 슬라이더의 최대 증가 가져옵니다.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>반환 값  
 슬라이더 컨트롤에 슬라이더를 이동할 수 있는 슬라이더의 최대 증가 합니다.  
  
##  <a name="a-namegetrangemina--cmfcribbonslidergetrangemin"></a><a name="getrangemin"></a>CMFCRibbonSlider::GetRangeMin  
 슬라이더 컨트롤에 슬라이더를 이동할 수 있는 최소 증분을 반환 합니다.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>반환 값  
 최소 증가값을 슬라이더 컨트롤에 슬라이더를 이동할 수 있습니다.  
  
##  <a name="a-namegetregularsizea--cmfcribbonslidergetregularsize"></a><a name="getregularsize"></a>CMFCRibbonSlider::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetzoomincrementa--cmfcribbonslidergetzoomincrement"></a><a name="getzoomincrement"></a>CMFCRibbonSlider::GetZoomIncrement  
 확대/축소 슬라이더 컨트롤에 대 한 증가값을 가져옵니다.  
  
```  
int GetZoomIncrement() const;  
```  
  
### <a name="return-value"></a>반환 값  
 슬라이더 컨트롤에 대 한 확대/축소 증가 합니다.  
  
##  <a name="a-namehaszoombuttonsa--cmfcribbonsliderhaszoombuttons"></a><a name="haszoombuttons"></a>CMFCRibbonSlider::HasZoomButtons  
 슬라이더 확대/축소 단추에 있는지 여부를 지정 합니다.  
  
```  
BOOL HasZoomButtons() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`슬라이더에 확대/축소 단추가 있습니다. `FALSE` 그렇지 않은 경우.  
  
##  <a name="a-nameondrawa--cmfcribbonsliderondraw"></a><a name="ondraw"></a>CMFCRibbonSlider::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namesetposa--cmfcribbonslidersetpos"></a><a name="setpos"></a>CMFCRibbonSlider::SetPos  
 슬라이더 컨트롤의 현재 위치를 설정 합니다.  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nPos`  
 슬라이더에 대 한 설정 위치를 지정 합니다. 슬라이더의 시작 부분에 상대적인 위치가입니다.  
  
 [in] `bRedraw`  
 경우 `TRUE`, 슬라이더 다시 그려집니다.  
  
##  <a name="a-namesetrangea--cmfcribbonslidersetrange"></a><a name="setrange"></a>CMFCRibbonSlider::SetRange  
 슬라이더 컨트롤에 대 한 값의 범위를 설정 합니다.  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nMin`  
 슬라이더 컨트롤의 최소 값을 지정합니다.  
  
 [in] `nMax`  
 슬라이더 컨트롤의 최대값을 지정합니다.  
  
### <a name="remarks"></a>주의  
 최소값과 최대값을 설정 하 여 슬라이더 컨트롤에 대 한 값의 범위를 지정 합니다.  
  
##  <a name="a-namesetzoombuttonsa--cmfcribbonslidersetzoombuttons"></a><a name="setzoombuttons"></a>CMFCRibbonSlider::SetZoomButtons  
 표시 하거나 확대/축소 단추를 숨깁니다.  
  
```  
void SetZoomButtons(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in]. `bSet`  
 `TRUE`확대/축소 단추;를 표시 하려면 `FALSE` 아이콘을 숨기려면 합니다.  
  
##  <a name="a-namesetzoomincrementa--cmfcribbonslidersetzoomincrement"></a><a name="setzoomincrement"></a>CMFCRibbonSlider::SetZoomIncrement  
 슬라이더 컨트롤에 대 한 확대/축소 증분을 설정 합니다.  
  
```  
void SetZoomIncrement(int nZoomIncrement);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nZoomIncrement`  
 슬라이더 컨트롤의 확대/축소 증분을 지정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement 클래스](../../mfc/reference/cmfcribbonbaseelement-class.md)

