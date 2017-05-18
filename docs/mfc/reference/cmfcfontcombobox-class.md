---
title: "CMFCFontComboBox 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontComboBox::DrawItem method
- CMFCFontComboBox::PreTranslateMessage method
- CMFCFontComboBox::MeasureItem method
- CMFCFontComboBox class
- CMFCFontComboBox::CompareItem method
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
caps.latest.revision: 29
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
ms.openlocfilehash: 1252f5ca102637e70cc384afd723464aec4144b4
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcfontcombobox-class"></a>CMFCFontComboBox 클래스
`CMFCFontComboBox` 클래스 글꼴 목록이 포함 된 콤보 상자 컨트롤을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCFontComboBox : public CComboBox  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|`CMFCFontComboBox` 개체를 생성합니다.|  
|`CMFCFontComboBox::~CMFCFontComboBox`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCFontComboBox::CompareItem`|현재 글꼴 콤보 상자 컨트롤의 정렬 된 목록 상자에 새 항목의 상대 위치를 결정 하는 프레임 워크에서 호출 됩니다. (재정의 [CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem).)|  
|`CMFCFontComboBox::DrawItem`|현재 글꼴 콤보 상자 컨트롤에서 지정된 된 항목을 그리는 데 프레임 워크에 의해 호출 됩니다. (재정의 [CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem).)|  
|[CMFCFontComboBox::GetSelFont](#getselfont)|현재 선택 된 글꼴에 대 한 정보를 검색합니다.|  
|`CMFCFontComboBox::MeasureItem`|현재 글꼴 콤보 상자 컨트롤에 목록 상자의 치수 Windows 알리기 위해 프레임 워크에 의해 호출 됩니다. (재정의 [CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).)|  
|`CMFCFontComboBox::PreTranslateMessage`|창 메시지를 변환 하 여으로 디스패치 되기 전에 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수입니다. (재정의 [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCFontComboBox::SelectFont](#selectfont)|글꼴 콤보 상자에서 지정된 된 조건과 일치 하는 글꼴을 선택 합니다.|  
|[CMFCFontComboBox::Setup](#setup)|글꼴 콤보 상자에 있는 항목의 목록을 초기화합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|현재 글꼴 콤보 상자에서 항목 레이블을 그리는 데 사용할 글꼴을 프레임 워크를 나타냅니다.|  
  
## <a name="remarks"></a>주의  
 사용 하는 `CMFCFontComboBox` 대화 상자에서 개체를 추가 `CMFCFontComboBox` 변수 대화 상자 클래스를 합니다. 그런 다음는 `OnInitDialog` 호출 대화 상자 클래스의 메서드는 [CMFCFontComboBox::Setup](#setup) 콤보 상자 컨트롤에서 항목의 목록을 초기화 하는 메서드.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 [CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxfontcombobox.h  
  
##  <a name="cmfcfontcombobox"></a>CMFCFontComboBox::CMFCFontComboBox  
 `CMFCFontComboBox` 개체를 생성합니다.  
  
```  
CMFCFontComboBox();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getselfont"></a>CMFCFontComboBox::GetSelFont  
 현재 선택 된 글꼴에 대 한 정보를 검색합니다.  
  
```  
CMFCFontInfo* GetSelFont() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터 [CMFCFontInfo 클래스](../../mfc/reference/cmfcfontinfo-class.md) 글꼴을 설명 하는 개체입니다. 수 `NULL` 없는 글꼴 콤보 상자에서 선택 됩니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="m_bdrawusingfont"></a>CMFCFontComboBox::m_bDrawUsingFont  
 현재 글꼴 콤보 상자에서 항목 레이블을 그리는 데 사용할 글꼴을 프레임 워크를 나타냅니다.  
  
```  
static BOOL m_bDrawUsingFont;  
```  
  
### <a name="remarks"></a>주의  
 이 멤버를 설정 `TRUE` 동일한 글꼴을 그리는 데 사용할 각 항목 레이블 프레임 워크를 보내도록 합니다. 이 멤버를 설정 `FALSE` 프레임 워크 이름이 레이블로 같습니다 글꼴을 사용 하 여 각 항목 레이블을 그리기에 지시 합니다. 이 멤버의 기본값은 `FALSE`합니다.  
  
##  <a name="selectfont"></a>CMFCFontComboBox::SelectFont  
 글꼴 콤보 상자에서 지정된 된 조건과 일치 하는 글꼴을 선택 합니다.  
  
```  
BOOL SelectFont(CMFCFontInfo* pDesc);

 
BOOL SelectFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDesc`  
 글꼴 설명 개체를 가리킵니다.  
  
 [in] `lpszName`  
 글꼴 이름을 지정합니다.  
  
 [in] `nCharSet`  
 문자 집합을 지정합니다. 기본값은 DEFAULT_CHARSET 합니다. 자세한 내용은 참조는 `lfCharSet` 의 멤버는 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`글꼴 콤보 상자의 항목 설명 개체를 지정 된 글꼴 또는 글꼴 이름 및 문자 집합입니다; 일치 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 선택 하 고 지정된 된 글꼴에 해당 하는 글꼴 콤보 상자에 있는 항목으로 스크롤합니다.  
  
### <a name="example"></a>예제  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `SelectFont` 에서 메서드는 `CMFCFontComboBox` 클래스입니다. 이 예제는의 일부는 [새 컨트롤 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_NewControls #&34;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls #&35;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]  
  
##  <a name="setup"></a>CMFCFontComboBox::Setup  
 글꼴 콤보 상자에 있는 항목의 목록을 초기화합니다.  
  
```  
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nFontType`  
 글꼴 종류를 지정합니다. 기본값은 DEVICE_FONTTYPE, RASTER_FONTTYPE, 및 TRUETYPE_FONTTYPE의 비트 조합 (OR)입니다.  
  
 [in] `nCharSet`  
 글꼴 문자 집합을 지정합니다. 기본값은 DEFAULT_CHARSET 합니다.  
  
 [in] `nPitchAndFamily`  
 글꼴 피치 및 제품군을 지정합니다. 기본값은 DEFAULT_PITCH 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`글꼴 콤보 상자 성공적으로 초기화 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 지정된 된 매개 변수와 일치 하는 현재 설치 된 글꼴 열거 하 고 글꼴 콤보 상자에서 해당 글꼴 이름을 삽입 하 여 글꼴 콤보 상자를 초기화 합니다.  
  
### <a name="example"></a>예제  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `Setup` 에서 메서드는 `CMFCFontComboBox` 클래스입니다. 이 예제는의 일부는 [새 컨트롤 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_NewControls #&34;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls #&36;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox 클래스](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCFontInfo 클래스](../../mfc/reference/cmfcfontinfo-class.md)

