---
title: "CMFCRibbonCheckBox 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetCompactSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetIntermediateSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetRegularSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::IsDrawTooltipImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDraw
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawMenuImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawOnList
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::SetACCData
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCheckBox class
ms.assetid: 3a6c3891-c8d1-4af0-b954-7b9ab048782a
caps.latest.revision: 30
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
ms.openlocfilehash: 9efe04a8e79835b8e51b7045cb86ab2dba68b675
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncheckbox-class"></a>CMFCRibbonCheckBox 클래스
`CMFCRibbonCheckBox` 클래스는 리본 패널, 빠른 실행 도구 모음 또는 팝업 메뉴에 추가할 수 있는 확인란을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonCheckBox : public CMFCRibbonButton  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](#cmfcribboncheckbox)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonCheckBox::GetCompactSize](#getcompactsize)|(재정의 [CMFCRibbonButton::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|  
|[CMFCRibbonCheckBox::GetIntermediateSize](#getintermediatesize)|(재정의 [CMFCRibbonButton::GetIntermediateSize](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize).)|  
|[CMFCRibbonCheckBox::GetRegularSize](#getregularsize)|(재정의 [CMFCRibbonButton::GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|  
|[CMFCRibbonCheckBox::IsDrawTooltipImage](#isdrawtooltipimage)|(`CMFCRibbonButton::IsDrawTooltipImage`를 재정의합니다.)|  
|[CMFCRibbonCheckBox::OnDraw](#ondraw)|(재정의 [CMFCRibbonButton::OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|  
|[CMFCRibbonCheckBox::OnDrawMenuImage](#ondrawmenuimage)|(재정의 [CMFCRibbonBaseElement::OnDrawMenuImage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|  
|[CMFCRibbonCheckBox::OnDrawOnList](#ondrawonlist)|(`CMFCRibbonButton::OnDrawOnList`를 재정의합니다.)|  
|[CMFCRibbonCheckBox::SetACCData](#setaccdata)|(재정의 [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|  
  
## <a name="remarks"></a>주의  
 응용 프로그램에서 `CMFCRibbonCheckBox`를 사용하려면 코드에 다음 생성자를 추가합니다.  
  
```  
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)  
```  
여기서 `nID`는 확인란 명령 ID이고 `lpszText`는 확인란의 텍스트 레이블입니다.  
  
 사용 하 여 리본 패널에는 확인란을 추가할 수 [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxribboncheckbox.h  
  
##  <a name="cmfcribboncheckbox"></a>CMFCRibbonCheckBox::CMFCRibbonCheckBox  
 리본 확인란 개체의 생성자  
  
```  
CMFCRibbonCheckBox(
    UINT nID,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nID`  
 명령 ID를 지정 합니다.  
  
 [in] `lpszText`  
 텍스트 레이블을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 리본 확인란 개체를 만듭니다.  
  
### <a name="example"></a>예제  
 개체를 생성 하는 방법은 다음 예제는 `CMFCRibbonCheckBox` 클래스입니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp #&17;](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]  
  
##  <a name="getcompactsize"></a>CMFCRibbonCheckBox::GetCompactSize  
 재정의 된 경우, checkbox의 압축 크기를 가져옵니다.  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 에 대 한 포인터는 `CDC` 확인란과 관련 된 합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 된 `CSize` checkbox의 압축 크기를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 재정의 되지 않는 경우이 확인란의 중간 크기를 반환 합니다.  
  
##  <a name="getintermediatesize"></a>CMFCRibbonCheckBox::GetIntermediateSize  
 Checkbox의 중간 크기를 가져옵니다.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 에 대 한 포인터는 `CDC` 관련 된이 확인란을이 선택 합니다.  
  
### <a name="return-value"></a>반환 값  
 A `CSize` checkbox의 중간 크기를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 재정의 되지 않으면 기본 확인란 크기로 중간 크기를 계산 ( `AFX_CHECK_BOX_DEFAULT_SIZE`) 및 텍스트 크기 및 여백입니다.  
  
##  <a name="getregularsize"></a>CMFCRibbonCheckBox::GetRegularSize  
 Checkbox의 일반적인 크기를 가져옵니다.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 에 대 한 포인터는 `CDC` 이 확인란 연관 된 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 된 `CSize` checkbox의 일반적인 크기를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 재정의 되지 않는 경우이 확인란의 중간 크기를 반환 합니다.  
  
##  <a name="isdrawtooltipimage"></a>CMFCRibbonCheckBox::IsDrawTooltipImage  
 확인란과 관련 된 도구 설명 이미지를 여부를 나타냅니다.  
  
```  
virtual BOOL IsDrawTooltipImage() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 는 확인란과 관련 된 도구 설명 이미지가 하는 경우 또는 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="ondraw"></a>CMFCRibbonCheckBox::OnDraw  
 지정 된 장치 컨텍스트를 사용 하는 확인란을 그리는 데 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 에 대 한 포인터는 `CDC` 를 그릴는 확인란을 선택 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="ondrawmenuimage"></a>CMFCRibbonCheckBox::OnDrawMenuImage  
 확인란의 메뉴 이미지를 그릴 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `CDC*`  
 에 대 한 포인터는 `CDC` 확인란과 관련 된 합니다.  
  
 [in] `CRect`  
 A `CRect` 메뉴 이미지를 그릴 사각형을 지정 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `TRUE` 이미지를 그릴 경우 또는 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 재정의 되지 않으면 반환 `FALSE`합니다.  
  
##  <a name="ondrawonlist"></a>CMFCRibbonCheckBox::OnDrawOnList  
 명령 목록 상자에서 확인란을 그리는 데 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnDrawOnList(
    CDC* pDC,  
    CString strText,  
    int nTextOffset,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 에 있는 확인란을 그릴 장치 컨텍스트에 대 한 포인터입니다.  
  
 [in] `strText`  
 표시 텍스트입니다.  
  
 [in] `nTextOffset`  
 왼쪽의 텍스트를 표시할 목록 상자에서 픽셀 거리입니다.  
  
 [in] `rect`  
 확인란의 표시 사각형을 지정 합니다.  
  
 [in] `bIsSelected`  
 `TRUE`이 확인란을 선택 하는 경우 또는 `FALSE` 그렇지 않은 경우.  
  
 [in] `bHighlighted`  
 `TRUE`이 확인란을 강조 표시 된 경우 또는 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="setaccdata"></a>CMFCRibbonCheckBox::SetACCData  
 확인란에 대 한 내게 필요한 옵션 데이터를 설정합니다.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>매개 변수  
 `pParent`  
 이 확인란의 부모 창입니다.  
  
 `data`  
 확인란에 대 한 내게 필요한 옵션 데이터입니다.  
  
### <a name="return-value"></a>반환 값  
 항상 `TRUE`를 반환합니다.  
  
### <a name="remarks"></a>주의  
 기본적으로이 메서드는 내게 필요한 옵션 데이터 설정의 확인란을 선택 하 고 항상 반환 `TRUE`합니다. 내게 필요한 옵션 데이터를 설정하고 성공 또는 실패를 나타내는 값을 반환하려면 이 메서드를 재정의합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonPanel 클래스](../../mfc/reference/cmfcribbonpanel-class.md)

