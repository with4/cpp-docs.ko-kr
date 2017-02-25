---
title: "CMFCRibbonGalleryMenuButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonGalleryMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonGalleryMenuButton class"
ms.assetid: 4d459d9b-8b1a-4371-92f6-dc4ce6cc42c8
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMFCRibbonGalleryMenuButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

리본 갤러리가 포함된 리본 메뉴 단추를 구현합니다.  
  
## 구문  
  
```  
class CMFCRibbonGalleryMenuButton : public CMFCToolBarMenuButton  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton](../Topic/CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton.md)|`CMFCRibbonGalleryMenuButton` 개체를 생성하고 초기화합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonGalleryMenuButton::CopyFrom](../Topic/CMFCRibbonGalleryMenuButton::CopyFrom.md)|\([CMFCToolBarMenuButton::CopyFrom](../Topic/CMFCToolBarMenuButton::CopyFrom.md) 재정의\)|  
|[CMFCRibbonGalleryMenuButton::CreatePopupMenu](../Topic/CMFCRibbonGalleryMenuButton::CreatePopupMenu.md)|\([CMFCToolBarMenuButton::CreatePopupMenu](../Topic/CMFCToolBarMenuButton::CreatePopupMenu.md) 재정의\)|  
|[CMFCRibbonGalleryMenuButton::GetPalette](../Topic/CMFCRibbonGalleryMenuButton::GetPalette.md)||  
|[CMFCRibbonGalleryMenuButton::HasButton](../Topic/CMFCRibbonGalleryMenuButton::HasButton.md)|\(`CMFCToolBarMenuButton::HasButton`을 재정의합니다.\)|  
|[CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed](../Topic/CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed.md)|\([CMFCToolBarMenuButton::IsEmptyMenuAllowed](../Topic/CMFCToolBarMenuButton::IsEmptyMenuAllowed.md) 재정의\)|  
  
### 설명  
 갤러리 메뉴 단추가 팝업 메뉴로 화살표와 함께 표시됩니다.  사용자가 이 단추를 클릭하면 이미지 갤러리가 표시됩니다.  갤러리 메뉴 단추를 생성하는 경우 이러한 이미지를 포함하는 이미지 목록을 지정해야 합니다.  
  
## 예제  
 다음 예제에서는 메뉴 단추에 글머리 기호 갤러리를 표시하는 방법을 보여 줍니다.  
  
```  
BOOL CMainFrame::OnShowPopupMenu (CMFCPopupMenu* pMenuPopup)  
{  
    int nBulletIndex = pMenuBar->CommandToIndex (ID_PARA_BULLETS);  
    if (nBulletIndex >= 0)  
    {  
        CMFCToolBarButton* pExButton =  
            pMenuBar->GetButton(nBulletIndex);  
        ASSERT_VALID (pExButton);  
        CMFCRibbonGalleryMenuButton paletteBullet (  
            pExButton->m_nID,  
            pExButton->GetImage (),  
            pExButton->m_strText);  
        InitBulletPalette (&paletteBullet.GetPalette ());  
        pMenuBar->ReplaceButton (ID_PARA_BULLETS, paletteBullet);  
    }  
}  
```  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md) [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) [CMFCRibbonGalleryMenuButton](../../mfc/reference/cmfcribbongallerymenubutton-class.md)  
  
## 요구 사항  
 **헤더:** afxRibbonPaletteGallery.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [CMFCRibbonGallery Class](../../mfc/reference/cmfcribbongallery-class.md)