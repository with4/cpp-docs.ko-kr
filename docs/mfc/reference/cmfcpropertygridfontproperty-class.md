---
title: "CMFCPropertyGridFontProperty 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetLogFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridFontProperty::OnClickButton method
- CMFCPropertyGridFontProperty class
- CMFCPropertyGridFontProperty::FormatProperty method
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
caps.latest.revision: 23
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
ms.openlocfilehash: 05d1db7e7de2ee72244e885d8a083ac3cda20142
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridfontproperty-class"></a>CMFCPropertyGridFontProperty 클래스
`CMFCPropertyGridFileProperty` 클래스 글꼴 선택 대화 상자를 여는 속성 목록 컨트롤 항목을 지원 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty](#cmfcpropertygridfontproperty)|`CMFCPropertyGridFontProperty` 개체를 생성합니다.|  
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCPropertyGridFontProperty::FormatProperty`|속성 값의 텍스트 표현에 서식을 지정합니다. (재정의 [CMFCPropertyGridProperty::FormatProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|  
|[CMFCPropertyGridFontProperty::GetColor](#getcolor)|글꼴 대화 상자에서 사용자가 선택한 글꼴 색을 검색 합니다.|  
|[CMFCPropertyGridFontProperty::GetLogFont](#getlogfont)|글꼴 대화 상자에서 사용자가 선택한 글꼴을 가져옵니다.|  
|`CMFCPropertyGridFontProperty::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식으로 연결 된 개체입니다.|  
|`CMFCPropertyGridFontProperty::OnClickButton`|사용자가 속성에 포함된 단추를 클릭하면 프레임워크에서 호출됩니다. (재정의 [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
  
## <a name="remarks"></a>주의  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridfontproperty"></a>CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty  
 `CMFCPropertyGridFontProperty` 개체를 생성합니다.  
  
```  
CMFCPropertyGridFontProperty(
    const CString& strName,  
    LOGFONT& lf,  
    DWORD dwFontDialogFlags = CF_EFFECTS | CF_SCREENFONTS,  
    LPCTSTR lpszDescr = NULL,  
    DWORD_PTR dwData = 0,  
    COLORREF color = (COLORREF)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strName`  
 속성의 이름입니다.  
  
 [in] `lf`  
 글꼴의 특성을 지정 하는 논리 글꼴 구조입니다.  
  
 [in] `dwFontDialogFlags`  
 속성 값 드롭다운 단추를 클릭할 때 표시 되는 글꼴 대화 상자에 적용 되는 스타일입니다. 기본값은 CF_EFFECTS 및 CF_SCREENFONTS의 비트 조합 (OR)입니다. 자세한 내용은 참조는 `Flags` 의 매개 변수는 [CHOOSEFONT 구조](http://msdn.microsoft.com/library/windows/desktop/ms646832)합니다.  
  
 [in] `lpszDescr`  
 Font 속성의 설명입니다. 기본값은 `NULL`입니다.  
  
 [in] `dwData`  
 정수 또는 속성에 연결된 된 기타 데이터에 대 한 포인터와 같은 응용 프로그램 관련 데이터입니다. 기본값은 0입니다.  
  
 [in] `color`  
 글꼴의 색입니다. 기본값은 기본 색입니다.  
  
### <a name="remarks"></a>주의  
 A `CMFCPropertyGridFontProperty` 개체 속성 표 글꼴 컨트롤의 글꼴 속성을 나타냅니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는의 개체를 생성 하는 방법을 `CMFCPropertyGridFontProperty` 클래스입니다. 이 예제는의 일부는 [새 컨트롤 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_NewControls #&26;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]  
  
##  <a name="getcolor"></a>CMFCPropertyGridFontProperty::GetColor  
 글꼴 대화 상자에서 사용자가 선택한 글꼴 색을 검색 합니다.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 선택한 글꼴 색을 나타내는 RGB 색상 값입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getlogfont"></a>CMFCPropertyGridFontProperty::GetLogFont  
 글꼴 대화 상자에서 사용자가 선택한 글꼴을 가져옵니다.  
  
```  
LPLOGFONT GetLogFont();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) 선택한 글꼴을 설명 하는 구조입니다.  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty 클래스](../../mfc/reference/cmfcpropertygridproperty-class.md)

