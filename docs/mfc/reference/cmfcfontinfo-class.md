---
title: "CMFCFontInfo 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::GetFullName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nCharSet
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nPitchAndFamily
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nType
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strScript
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontInfo class
- CMFCFontInfo::CMFCFontInfo constructor
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
caps.latest.revision: 26
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
ms.openlocfilehash: ac1409bcfce389cbc334edd2b864f7505d7443c7
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcfontinfo-class"></a>CMFCFontInfo 클래스
`CMFCFontInfo` 클래스 이름 및 글꼴의 다른 특성을 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCFontInfo : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCFontInfo`|
          `CMFCFontInfo` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCFontInfo::GetFullName](#getfullname)|검색 글꼴과 문자의 연결 된 이름 (스크립트)을 설정합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCFontInfo::m_nCharSet](#m_ncharset)|연결 된 문자 집합 (스크립트)을 지정 하는 값입니다.|  
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|폭 및 글꼴 패밀리를 지정 하는 값입니다.|  
|[CMFCFontInfo::m_nType](#m_ntype)|글꼴의 유형을 지정 하는 값입니다.|  
|[CMFCFontInfo::m_strName](#m_strname)|글꼴;의 이름 예를 들어 **Arial**합니다.|  
|[CMFCFontInfo::m_strScript](#m_strscript)|연결 된 문자 집합 (스크립트)의 이름입니다.|  
  
## <a name="remarks"></a>주의  
 연결할 수는 `CMFCFontInfo` 개체의 항목에는 [CMFCToolBarFontComboBox 클래스](../../mfc/reference/cmfctoolbarfontcombobox-class.md) 클래스입니다. 호출 된 [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) 에 대 한 포인터를 검색 하는 메서드는 `CMFCFontInfo` 개체입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는의 다양 한 멤버를 사용 하는 방법을 `CMFCFontInfo` 클래스입니다. 가져오는 방법을 보여 줍니다는 `CMFCFontInfo` 에서 개체는 `CMFCRibbonFontComboBox`, 및 지역 변수를 액세스 하는 방법입니다. 이 예제는의 일부는 [MSOffice 2007 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo #&6;](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfcfontinfo"></a>CMFCFontInfo::CMFCFontInfo  
 `CMFCFontInfo` 개체를 생성합니다.  
  
```  
CMFCFontInfo(
    LPCTSTR lpszName,  
    LPCTSTR lpszScript,  
    BYTE nCharSet,  
    BYTE nPitchAndFamily,  
    int nType);  
  
CMFCFontInfo(const CMFCFontInfo& src);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszName`  
 글꼴의 이름입니다. 자세한 내용은 참조는 `lfFaceName` 의 멤버는 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) 구조입니다.  
  
 [in] `lpszScript`  
 글꼴의 스크립트 (문자 집합)의 이름입니다.  
  
 [in] `nCharSet`  
 글꼴의 문자 집합 (스크립트)을 지정 하는 값입니다. 자세한 내용은 참조는 `lfCharSet` 의 멤버는 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) 구조입니다.  
  
 [in] `nPitchAndFamily`  
 폭 및 글꼴 패밀리를 지정 하는 값입니다. 자세한 내용은 참조는 `lfPitchAndFamily` 의 멤버는 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) 구조입니다.  
  
 [in] `nType`  
 글꼴 종류를 지정 하는 값입니다. 이 매개 변수는 DEVICE_FONTTYPE, RASTER_FONTTYPE, 및 TRUETYPE_FONTTYPE의 비트 조합 (OR) 일 수 있습니다.  
  
 [in] `src`  
 기존 `CMFCFontInfo` 해당 멤버는이 생성 하는 데 사용 되는 개체 `CMFCFontInfo` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
 이 설명서는 용어를 사용 하 여 *문자 집합* 및 *스크립트* 서로 교환해 서입니다. A *스크립트*, 하며 라고도 쓰기 시스템의 문자 및 하나 이상의 언어에 해당 문자를 작성 하는 것에 대 한 규칙의 컬렉션입니다. 에 알파벳 및 스크립트에 사용 되는 문장 부호 문자 컬렉션에 포함 되어 있습니다. 예를 들어 라틴 스크립트는 미국에서 사용 되는 것과 a ~ Z 문자를 포함 하는 해당 알파벳 영어에 사용 됩니다. `lfCharSet` 의 멤버는 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) 구조 문자 집합을 지정 합니다. 예를 들어, 값 `ANSI_CHARSET` 지정는 [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] 라틴어 스크립트의 알파벳을 포함 하는 문자 집합입니다.  
  
##  <a name="getfullname"></a>CMFCFontInfo::GetFullName  
 검색 글꼴과 문자의 연결 된 이름 (스크립트)을 설정합니다.  
  
```  
CString GetFullName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 글꼴 이름 및 스크립트를 포함 하는 문자열입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 글꼴의 전체 이름을 가져옵니다. 예를 들어 글꼴 이름을 경우 `Arial` 글꼴 스크립트는 `Cyrillic`,이 메서드는 "Arial (키릴 자모)"를 반환 합니다.  
  
##  <a name="m_ncharset"></a>CMFCFontInfo::m_nCharSet  
 연결 된 문자 집합 (스크립트)을 지정 하는 값입니다.  
  
```  
const BYTE m_nCharSet;  
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조는 `nCharSet` 의 매개 변수는 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) 생성자입니다.  
  
##  <a name="m_npitchandfamily"></a>CMFCFontInfo::m_nPitchAndFamily  
 피치 (포인트 크기) 및 글꼴의 제품군 (예: serif, 굴림, 및 고정 폭)을 지정 하는 값입니다.  
  
```  
const BYTE m_nPitchAndFamily;  
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조는 `nPitchAndFamily` 의 매개 변수는 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) 생성자입니다.  
  
##  <a name="m_ntype"></a>CMFCFontInfo::m_nType  
 글꼴의 유형을 지정 하는 값입니다.  
  
```  
const int m_nType;  
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조는 `nType` 의 매개 변수는 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) 생성자입니다.  
  
##  <a name="m_strname"></a>CMFCFontInfo::m_strName  
 글꼴의 이름이: 예를 들어 **Arial**합니다.  
  
```  
const CString m_strName;  
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조는 `lpszName` 의 매개 변수는 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) 생성자입니다.  
  
##  <a name="m_strscript"></a>CMFCFontInfo::m_strScript  
 연결 된 문자 집합 (스크립트)의 이름입니다.  
  
```  
const CString m_strScript;  
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조는 `lpszScript` 의 매개 변수는 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) 생성자입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox 클래스](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCToolBarFontSizeComboBox 클래스](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)

