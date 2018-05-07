---
title: CMFCToolBarFontSizeComboBox 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox [MFC], CMFCToolBarFontSizeComboBox
- CMFCToolBarFontSizeComboBox [MFC], GetTwipSize
- CMFCToolBarFontSizeComboBox [MFC], RebuildFontSizes
- CMFCToolBarFontSizeComboBox [MFC], SetTwipSize
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b2c5734618bf1bedc72fe78dbeaada8c437391f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox 클래스
글꼴 크기를 선택할 수 있도록 해 주는 콤보 상자 컨트롤을 포함 하는 도구 모음 단추입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|`CMFCToolBarFontSizeComboBox` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|트윕에 선택한 글꼴 크기를 반환합니다.|  
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|콤보 상자 목록에 지정 된 글꼴에 대 한 모든 지원 되는 글꼴 크기를 채웁니다.|  
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|트윕에서 글꼴 크기를 설정합니다.|  
  
## <a name="remarks"></a>설명  
 사용할 수는 `CMFCToolBarFontSizeComboBox` 와 함께 개체는 [CMFCToolBarFontComboBox 클래스](../../mfc/reference/cmfctoolbarfontcombobox-class.md) 사용자 글꼴 및 글꼴 크기를 선택할 수 있도록 하는 개체입니다.  
  
 글꼴 콤보 상자 단추를 추가할 것 처럼 글꼴 크기 콤보 상자 단추를 도구 모음에 추가할 수 있습니다. 자세한 내용은 참조 [CMFCToolBarFontComboBox 클래스](../../mfc/reference/cmfctoolbarfontcombobox-class.md)합니다.  
  
 사용자가 새 글꼴을 선택 하는 경우는 `CMFCToolBarFontComboBox` 개체를 사용 하 여 지원 되는 크기를 글꼴에 대 한 글꼴 크기 콤보 상자를 채울 수 있습니다는 [CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes) 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서 다양 한 메서드를 사용 하는 방법을 보여 줍니다는 `CMFCToolBarFontSizeComboBox` 구성 하는 클래스는 `CMFCToolBarFontSizeComboBox` 개체입니다. 이 예제에서는 트윕의 글꼴 크기, 텍스트 상자에서 검색 하 고 모든 유효한 크기가 지정 된 글꼴의 글꼴 크기 콤보 상자 채우기 트윕에서 글꼴 크기를 지정 하는 방법을 보여 줍니다. 이 코드 조각은 [워드 패드 샘플](../../visual-cpp-samples.md)의 일부입니다.  
  
 [!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfctoolbarfontsizecombobox"></a>  CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox  
 `CMFCToolBarFontSizeComboBox` 개체를 생성합니다.  
  
```  
CMFCToolBarFontSizeComboBox();
```  
  
##  <a name="gettwipsize"></a>  CMFCToolBarFontSizeComboBox::GetTwipSize  
 글꼴 크기 콤보 상자의 텍스트 상자에서 트윕의 글꼴 크기를 검색합니다.  
  
```  
int GetTwipSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 값이 양수 일 경우 트윕에서 글꼴 크기입니다. 것은 콤보 상자의 텍스트 상자가 비어 있으면-1입니다. -2는 오류가 발생 하는 경우.  
  
##  <a name="rebuildfontsizes"></a>  CMFCToolBarFontSizeComboBox::RebuildFontSizes  
 모든 유효한 크기 지정 된 글꼴의 글꼴 크기 콤보 상자를 채웁니다.  
  
```  
void RebuildFontSizes(const CString& strFontName);
```  
  
### <a name="parameters"></a>매개 변수  
 `[in] strFontName`  
 글꼴 이름을 지정합니다.  
  
### <a name="remarks"></a>설명  
 글꼴 콤보 상자에서 선택 하 고 글꼴 크기 콤보 상자와 같은 동기화 하려는 경우이 함수를 호출는 [CMFCToolBarFontComboBox 클래스](../../mfc/reference/cmfctoolbarfontcombobox-class.md)합니다.  
  
##  <a name="settwipsize"></a>  CMFCToolBarFontSizeComboBox::SetTwipSize  
 라운드 지정된 된 크기 (트윕) 점 및 다음 집합에서 가장 가까운 크기를 해당 값에 콤보 상자에서 선택한 크기입니다.  
  
```  
void SetTwipSize(int nSize);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nSize`  
 설정 하려면 (트윕)에서 글꼴 크기를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 호출 하 여 나중에 이전 유효한 글꼴 크기를 검색할 수 있습니다는 [CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton 클래스](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo 클래스](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)



