---
title: CMFCRibbonGalleryMenuButton 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CopyFrom
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CreatePopupMenu
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::GetPalette
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::HasButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonGalleryMenuButton [MFC], CMFCRibbonGalleryMenuButton
- CMFCRibbonGalleryMenuButton [MFC], CopyFrom
- CMFCRibbonGalleryMenuButton [MFC], CreatePopupMenu
- CMFCRibbonGalleryMenuButton [MFC], GetPalette
- CMFCRibbonGalleryMenuButton [MFC], HasButton
- CMFCRibbonGalleryMenuButton [MFC], IsEmptyMenuAllowed
ms.assetid: 4d459d9b-8b1a-4371-92f6-dc4ce6cc42c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27d2d4e95bffa3bd074ca1c6d4bf6d9c7e095a56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370909"
---
# <a name="cmfcribbongallerymenubutton-class"></a>CMFCRibbonGalleryMenuButton 클래스
리본 갤러리가 포함된 리본 메뉴 단추를 구현합니다.  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
   
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonGalleryMenuButton : public CMFCToolBarMenuButton  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton](#cmfcribbongallerymenubutton)|`CMFCRibbonGalleryMenuButton` 개체를 생성하고 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonGalleryMenuButton::CopyFrom](#copyfrom)|(재정의 [cmfctoolbarmenubutton:: Copyfrom](../../mfc/reference/cmfctoolbarmenubutton-class.md#copyfrom).)|  
|[CMFCRibbonGalleryMenuButton::CreatePopupMenu](#createpopupmenu)|(재정의 [cmfctoolbarmenubutton:: Createpopupmenu](../../mfc/reference/cmfctoolbarmenubutton-class.md#createpopupmenu).)|  
|[CMFCRibbonGalleryMenuButton::GetPalette](#getpalette)||  
|[CMFCRibbonGalleryMenuButton::HasButton](#hasbutton)|(`CMFCToolBarMenuButton::HasButton`를 재정의합니다.)|  
|[CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|(재정의 [cmfctoolbarmenubutton:: Isemptymenuallowed](../../mfc/reference/cmfctoolbarmenubutton-class.md#isemptymenuallowed).)|  
  
### <a name="remarks"></a>설명  
 갤러리 메뉴 단추가 팝업 메뉴로 화살표와 함께 표시됩니다. 사용자가 이 단추를 클릭하면 이미지 갤러리가 표시됩니다. 갤러리 메뉴 단추를 생성하는 경우 이러한 이미지를 포함하는 이미지 목록을 지정해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 메뉴 단추에 글머리 기호 갤러리를 표시하는 방법을 보여 줍니다.  
  
```  
BOOL CMainFrame::OnShowPopupMenu (CMFCPopupMenu* pMenuPopup)  
{  
    int nBulletIndex = pMenuBar->CommandToIndex (ID_PARA_BULLETS);

    if (nBulletIndex>= 0)  
 {  
    CMFCToolBarButton* pExButton = 
    pMenuBar->GetButton(nBulletIndex);
ASSERT_VALID (pExButton);

    CMFCRibbonGalleryMenuButton paletteBullet (
    pExButton->m_nID, 
    pExButton->GetImage (),  
    pExButton->m_strText);

 InitBulletPalette (&paletteBullet.GetPalette ());

    pMenuBar->ReplaceButton (ID_PARA_BULLETS,
    paletteBullet);

 }  
}  
```  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md) [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) [CMFCRibbonGalleryMenuButton](../../mfc/reference/cmfcribbongallerymenubutton-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxRibbonPaletteGallery.h  
  
##  <a name="copyfrom"></a>  CMFCRibbonGalleryMenuButton::CopyFrom  

  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `src`  
  
### <a name="remarks"></a>설명  
  
##  <a name="cmfcribbongallerymenubutton"></a>  CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton  
 생성 하 고 초기화는 [CMFCRibbonGalleryMenuButton](../../mfc/reference/cmfcribbongallerymenubutton-class.md) 개체입니다.  
  
```  
CMFCRibbonGalleryMenuButton(
    UINT uiID,  
    int iImage,  
    LPCTSTR lpszText,  
    CMFCToolBarImages& imagesPalette);

 
CMFCRibbonGalleryMenuButton(
    UINT uiID,  
    int iImage,  
    LPCTSTR lpszText,  
    UINT uiImagesPaletteResID = 0,  
    int cxPaletteImage = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `uiID`  
 단추의 명령 ID입니다. 전송 하는 값은 **WM_COMMAND** 이 단추를 클릭할 때 메시지입니다.  
  
 `iImage`  
 갤러리 메뉴 단추와 함께 표시할 이미지의 인덱스입니다. 에 저장 된 이미지는 `imagesPalette` 매개 변수입니다.  
  
 `lpszText`  
 메뉴 단추에 표시할 텍스트입니다.  
  
 `imagesPalette`  
 갤러리에 표시할 이미지의 목록을 포함 합니다.  
  
 `uiImagesPaletteResID`  
 갤러리에 표시할 이미지 목록의 이미지에 대 한 리소스 ID입니다.  
  
 `cxPaletteImage`  
 갤러리에 표시할 이미지의 픽셀에서 너비를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 갤러리 메뉴 단추가 팝업 메뉴로 화살표가 있는 표시 됩니다. 사용자가 이 단추를 클릭하면 이미지 갤러리가 표시됩니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는의 생성자를 사용 하 여 `CMFCRibbonGalleryMenuButton` 클래스입니다. 이 코드 조각은의 일부인는 [MS Office 2007 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#8](../../mfc/reference/codesnippet/cpp/cmfcribbongallerymenubutton-class_1.cpp)]  
  
##  <a name="createpopupmenu"></a>  CMFCRibbonGalleryMenuButton::CreatePopupMenu  

  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getpalette"></a>  CMFCRibbonGalleryMenuButton::GetPalette  

  
```  
CMFCRibbonGallery& GetPalette();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="hasbutton"></a>  CMFCRibbonGalleryMenuButton::HasButton  

  
```  
virtual BOOL HasButton() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="isemptymenuallowed"></a>  CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed  

  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarMenuButton 클래스](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [CMFCRibbonGallery 클래스](../../mfc/reference/cmfcribbongallery-class.md)
