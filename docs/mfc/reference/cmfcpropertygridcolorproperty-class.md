---
title: CMFCPropertyGridColorProperty 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableAutomaticButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableOtherButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColumnsNumber
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetOriginalValue
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridColorProperty [MFC], CMFCPropertyGridColorProperty
- CMFCPropertyGridColorProperty [MFC], EnableAutomaticButton
- CMFCPropertyGridColorProperty [MFC], EnableOtherButton
- CMFCPropertyGridColorProperty [MFC], GetColor
- CMFCPropertyGridColorProperty [MFC], SetColor
- CMFCPropertyGridColorProperty [MFC], SetColumnsNumber
- CMFCPropertyGridColorProperty [MFC], SetOriginalValue
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de336692a821ba374996fac9ee7d282d2990bd08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367996"
---
# <a name="cmfcpropertygridcolorproperty-class"></a>CMFCPropertyGridColorProperty 클래스
`CMFCPropertyGridColorProperty` 클래스는 색 선택 항목 대화 상자를 여는 속성 목록 컨트롤 항목을 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](#cmfcpropertygridcolorproperty)|`CMFCPropertyGridColorProperty` 개체를 생성합니다.|  
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|사용 하도록 설정 된 *자동* 색 선택 대화 상자에서 단추입니다. (표준 자동 단추 레이블이 **자동**.)|  
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|사용 하도록 설정 된 *다른* 색 선택 대화 상자에서 단추입니다. (표준 기타 단추 레이블이 **다른 색**.)|  
|`CMFCPropertyGridColorProperty::FormatProperty`|속성 값의 텍스트 표현에 서식을 지정합니다. (재정의 [cmfcpropertygridproperty:: Formatproperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|  
|[CMFCPropertyGridColorProperty::GetColor](#getcolor)|속성의 현재 색을 가져옵니다.|  
|`CMFCPropertyGridColorProperty::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에서는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|  
|`CMFCPropertyGridColorProperty::OnClickButton`|사용자가 속성에 포함된 단추를 클릭하면 프레임워크에서 호출됩니다. (재정의 [cmfcpropertygridproperty:: Onclickbutton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
|`CMFCPropertyGridColorProperty::OnDrawValue`|속성 값을 표시하기 위해 프레임워크에서 호출됩니다. (재정의 [cmfcpropertygridproperty:: Ondrawvalue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue).)|  
|`CMFCPropertyGridColorProperty::OnEdit`|사용자가 속성 값을 수정하려고 할 때 프레임워크에서 호출됩니다. (재정의 [cmfcpropertygridproperty:: Onedit](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit).)|  
|`CMFCPropertyGridColorProperty::OnUpdateValue`|편집 가능한 속성 값이 변경되었을 때 프레임워크에서 호출됩니다. (재정의 [cmfcpropertygridproperty:: Onupdatevalue](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue).)|  
|[CMFCPropertyGridColorProperty::SetColor](#setcolor)|속성에 대한 새로운 색을 설정합니다.|  
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|현재 색 속성 표의 열 수를 지정합니다.|  
|[Cmfcpropertygridcolorproperty:: Setoriginalvalue](#setoriginalvalue)|편집 가능한 속성의 원래 값을 설정합니다.|  
  
## <a name="remarks"></a>설명  
 `CMFCPropertyGridColorProperty` 클래스는 속성 목록 컨트롤에 추가할 수 있는 색 속성을 지원합니다. 자세한 내용은 참조는 [CMFCPropertyGridCtrl 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CMFCPropertyGridColorProperty` 클래스의 개체를 생성하고 `CMFCPropertyGridColorProperty` 클래스의 다양한 메서드를 사용하여 이 개체를 구성하는 방법을 보여 줍니다. 코드에서는 자동 및 기타 단추를 사용하도록 설정하는 방법과 색 및 열 번호를 설정하는 방법을 설명합니다. 이 예제는의 일부는 [새 컨트롤 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_NewControls#13](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridcolorproperty"></a>  CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty  
 `CMFCPropertyGridColorProperty` 개체를 생성합니다.  
  
```  
CMFCPropertyGridColorProperty(
    const CString& strName,  
    const COLORREF& color,  
    CPalette* pPalette = NULL,  
    LPCTSTR lpszDescr = NULL,  
    DWORD_PTR dwData = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strName`  
 속성의 이름입니다.  
  
 [in] `color`  
 속성의 색상 값입니다.  
  
 [in] `pPalette`  
 색의 팔레트에 대 한 포인터입니다. 기본값은 `NULL`입니다.  
  
 [in] `lpszDescr`  
 속성 설명입니다. 기본값은 `NULL`입니다.  
  
 [in] `dwData`  
 정수 또는 속성에 연관 된 다른 데이터에 대 한 포인터 등 응용 프로그램별 데이터입니다. 기본값은 0입니다.  
  
##  <a name="enableautomaticbutton"></a>  CMFCPropertyGridColorProperty::EnableAutomaticButton  
 사용 하도록 설정 된 *자동* 색 선택 대화 상자에서 단추입니다. (표준 자동 단추 레이블이 **자동**.)  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszLabel`  
 자동 단추 레이블 텍스트입니다.  
  
 [in] `colorAutomatic`  
 자동 (기본) 색의 RGB 색상 값입니다.  
  
 [in] `bEnable`  
 `TRUE` 자동 단추를 사용 하도록 설정 하려면 그렇지 않으면 `FALSE`합니다. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="enableotherbutton"></a>  CMFCPropertyGridColorProperty::EnableOtherButton  
 사용 하도록 설정 된 *다른* 색 선택 대화 상자에서 단추입니다. (표준 기타 단추 레이블이 **다른 색**.)  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg = TRUE,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszLabel`  
 다른 단추 레이블 텍스트입니다.  
  
 [in] `bAltColorDlg`  
 `TRUE` 표시 하는 `CMFCColorDialog` 대화 상자 `FALSE` 표준 색 선택 대화 상자를 표시 합니다. 기본값은 `TRUE`입니다.  
  
 [in] `bEnable`  
 `TRUE` 다른 단추를 표시 하려면 그렇지 않으면 `FALSE`합니다.  기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getcolor"></a>  CMFCPropertyGridColorProperty::GetColor  
 속성의 현재 색을 가져옵니다.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 RGB 색상 값입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setcolor"></a>  CMFCPropertyGridColorProperty::SetColor  
 속성에 대한 새로운 색을 설정합니다.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `color`  
 RGB 색상 값입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setcolumnsnumber"></a>  CMFCPropertyGridColorProperty::SetColumnsNumber  
 현재 색 속성 표의 열 수를 지정합니다.  
  
```  
void SetColumnsNumber(int nColumnsNumber);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nColumnsNumber`  
 기본 색 속성 표의 열 수입니다.  
  
### <a name="remarks"></a>설명  
 값을 설정 하는이 메서드는 `m_nColumnsNumber` 데이터 멤버를 보호 합니다.  
  
##  <a name="setoriginalvalue"></a>  Cmfcpropertygridcolorproperty:: Setoriginalvalue  
 편집 가능한 속성의 원래 값을 설정합니다.  
  
```  
virtual void SetOriginalValue(const COleVariant& varValue);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `varValue`  
 값입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여는 [cmfcpropertygridproperty:: Resetoriginalvalue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue) 메서드를 편집된 된 속성의 원래 값을 다시 설정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty 클래스](../../mfc/reference/cmfcpropertygridproperty-class.md)
