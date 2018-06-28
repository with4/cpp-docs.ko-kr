---
title: CMFCRibbonButtonsGroup 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButtons
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetCount
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetImageSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetRegularSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::HasImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::OnDrawImage
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::RemoveAll
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetParentCategory
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonButtonsGroup [MFC], CMFCRibbonButtonsGroup
- CMFCRibbonButtonsGroup [MFC], AddButton
- CMFCRibbonButtonsGroup [MFC], AddButtons
- CMFCRibbonButtonsGroup [MFC], GetButton
- CMFCRibbonButtonsGroup [MFC], GetCount
- CMFCRibbonButtonsGroup [MFC], GetImageSize
- CMFCRibbonButtonsGroup [MFC], GetRegularSize
- CMFCRibbonButtonsGroup [MFC], HasImages
- CMFCRibbonButtonsGroup [MFC], OnDrawImage
- CMFCRibbonButtonsGroup [MFC], RemoveAll
- CMFCRibbonButtonsGroup [MFC], SetImages
- CMFCRibbonButtonsGroup [MFC], SetParentCategory
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 23f3672a3b78b1bf86c481b6991c003267e6b0bf
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037436"
---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGroup 클래스
`CMFCRibbonButtonsGroup` 클래스 리본 단추 집합을 그룹으로 구성할 수 있습니다. 그룹의 모든 단추는 가로로 서로 직접 인접해 있으며 테두리로 둘러싸여 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|`CMFCRibbonButtonsGroup` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::AddButton](#addbutton)|단추 그룹에 추가합니다.|  
|[CMFCRibbonButtonsGroup::AddButtons](#addbuttons)|단추 목록이 그룹에 추가합니다.|  
|[CMFCRibbonButtonsGroup::GetButton](#getbutton)|지정된 된 인덱스에 있는 단추에 대 한 포인터를 반환 합니다.|  
|[CMFCRibbonButtonsGroup::GetCount](#getcount)|그룹의 단추 수를 반환합니다.|  
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|리본 그룹의 일반 이미지의 이미지 크기를 반환 합니다 (재정의 [cmfcribbonbaseelement:: Getimagesize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|  
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|리본 요소의 보통 크기를 반환 합니다 (재정의 [cmfcribbonbaseelement:: Getregularsize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|보고서 여부는 `CMFCRibbonButtonsGroup` 도구 모음 이미지를 포함 하는 개체입니다.|  
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|보통, 강조 표시 된 또는 사용 안 함 단추 인지에 따라의 지정 된 단추에 대 한 적절 한 이미지를 그립니다.|  
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|모든 단추를 제거는 `CMFCRibbonButtonsGroup` 개체입니다.|  
|[CMFCRibbonButtonsGroup::SetImages](#setimages)|이미지 그룹에 할당합니다.|  
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|부모를 설정 `CMFCRibbonCategory` 의 `CMFCRibbonButtonsGroup` 개체와 그 안에 모든 단추 (재정의 [cmfcribbonbaseelement:: Setparentcategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|  
  
## <a name="remarks"></a>설명  
 파생 되는 그룹 [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) 있으며 단일 엔터티로 조작할 수 있습니다. 패널 또는 팝업 메뉴에는 그룹을 배치할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 `CMFCRibbonButtonsGroup` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 생성 하는 방법을 보여 줍니다는 `CMFCRibbonButtonsGroup` 개체 하 고, 리본 단추를 그룹에 이미지를 할당 한 다음 리본 메뉴 단추 그룹에 단추를 추가 합니다. 이 코드 조각은 [클라이언트 그리기 샘플](../../visual-cpp-samples.md)의 일부입니다.  
  
 [!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxribbonbuttonsgroup.h  
  
##  <a name="addbutton"></a>  CMFCRibbonButtonsGroup::AddButton  
 단추 그룹에 추가합니다.  
  
```  
void AddButton(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pButton*  
 추가 하는 단추에 대 한 포인터입니다.  
  
##  <a name="addbuttons"></a>  CMFCRibbonButtonsGroup::AddButtons  
 단추 목록이 그룹에 추가합니다.  
  
```  
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *lstButtons*  
 목록 추가 하려는 하는 단추에 대 한 포인터입니다.  
  
##  <a name="cmfcribbonbuttonsgroup"></a>  CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup  
 `CMFCRibbonButtonsGroup` 개체를 생성합니다.  
  
```  
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pButton*  
 새로 만든에 추가 하려면 단추를 지정 `CMFCRibbonButtonsGroup` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getbutton"></a>  CMFCRibbonButtonsGroup::GetButton  
 지정된 된 인덱스에 있는 단추에 대 한 포인터를 반환 합니다.  
  
```  
CMFCRibbonBaseElement* GetButton(int i) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *i*  
 반환할 단추는 0부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 인덱스에 있는 단추에 대 한 포인터입니다. `NULL` 지정된 된 인덱스 범위를 벗어난 경우.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getcount"></a>  CMFCRibbonButtonsGroup::GetCount  
 그룹의 단추 수를 반환합니다.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 그룹의 단추 수를 지정 합니다.  
  
##  <a name="getimagesize"></a>  CMFCRibbonButtonsGroup::GetImageSize  
 보호 된 원본 이미지 크기를 검색 `CMFCToolBarImages` 멤버 `m_Images`합니다.  
  
```  
const CSize GetImageSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 하나라도 있는, 또는 도구 모음 이미지의 원본 이미지 크기를 반환 `CSize` 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getregularsize"></a>  CMFCRibbonButtonsGroup::GetRegularSize  
 리본 그룹 요소의 가능한 최대 크기를 검색합니다.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pDC*  
 리본 그룹의 장치 컨텍스트에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="hasimages"></a>  CMFCRibbonButtonsGroup::HasImages  
 보고서 여부는 `CMFCRibbonButtonsGroup` 도구 모음 이미지를 포함 하는 개체입니다.  
  
```  
BOOL HasImages() const;  
```  
  
### <a name="return-value"></a>반환 값  
 경우 TRUE를 반환 합니다. 보호 된 `CMFCToolBarImages` 멤버 `m_Images` 하지 모든 이미지 또는 이면 FALSE를 포함 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="ondrawimage"></a>  CMFCRibbonButtonsGroup::OnDrawImage  
 보통, 강조 표시 된 또는 사용 안 함 단추 인지에 따라의 지정 된 단추에 대 한 적절 한 이미지를 그립니다.  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rectImage,  
    CMFCRibbonBaseElement* pButton,  
    int nImageIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pDC*  
 장치 컨텍스트에 대 한 포인터는 `CMFCRibbonButtonsGroup` 개체입니다.  
  
 [in] *rectImage*  
 이미지를 그릴 사각형입니다.  
  
 [in] *pButton*  
 단추를 그릴 이미지입니다.  
  
 [in] *nImageIndex*  
 보통, 강조 표시 된 또는 사용 안 함 단추에 대 한 3 개의 이미지 배열 중 하나) (의 단추에 그릴 이미지의 인덱스입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="removeall"></a>  CMFCRibbonButtonsGroup::RemoveAll  
 모든 단추를 제거는 `CMFCRibbonButtonsGroup` 개체입니다.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="setimages"></a>  CMFCRibbonButtonsGroup::SetImages  
 리본 단추 그룹에 이미지를 할당합니다.  
  
```  
void SetImages(
    CMFCToolBarImages* pImages,  
    CMFCToolBarImages* pHotImages,  
    CMFCToolBarImages* pDisabledImages);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pImages*  
 일반 이미지입니다.  
  
 [in] *pHotImages*  
 핫 이미지입니다.  
  
 [in] *pDisabledImages*  
 비활성화 된 이미지입니다.  
  
### <a name="remarks"></a>설명  
 호출 `SetImages` 단추 그룹에 추가 하기 전에. 이미지의 수는 단추를 그룹에 추가할 수 보다 크거나 같아야 합니다.  
  
> [!NOTE]
>  핫 이미지는 단추를 가리킬 때 표시 되는 이미지입니다. 비활성화 된 이미지는 단추가 비활성화 되는 경우 표시 되는 이미지입니다.  
  
##  <a name="setparentcategory"></a>  CMFCRibbonButtonsGroup::SetParentCategory  
 부모를 설정 `CMFCRibbonCategory` 의 `CMFCRibbonButtonsGroup` 개체와 그 안에 모든 단추입니다.  
  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pCategory*  
 부모 범주 설정에 대 한 포인터 (리본 컨트롤에 탭된 그룹의 범주 이라고 함).  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)
