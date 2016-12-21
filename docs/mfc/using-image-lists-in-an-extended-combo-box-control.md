---
title: "확장 콤보 상자 컨트롤에서 이미지 목록 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "확장된 콤보 상자, 이미지"
  - "이미지 목록[C++], 콤보 상자"
  - "이미지[C++], 콤보 상자 항목"
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 확장 콤보 상자 컨트롤에서 이미지 목록 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The main feature of extended combo box controls is the ability to associate images from an image list with individual items in a combo box control.  Each item is able to display three different images: one for its selected state, one for its nonselected state, and a third for an overlay image.  
  
 The following procedure associates an image list with an extended combo box control:  
  
### To associate an image list with an extended combo box control  
  
1.  Construct a new image list \(or use an existing image list object\), using the [CImageList](../mfc/reference/cimagelist-class.md) constructor and storing the resultant pointer.  
  
2.  Initialize the new image list object by calling [CImageList::Create](../Topic/CImageList::Create.md).  The following code is one example of this call.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/CPP/using-image-lists-in-an-extended-combo-box-control_1.cpp)]  
  
3.  Add optional images for each possible state: selected or nonselected, and an overlay.  The following code adds three predefined images.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/CPP/using-image-lists-in-an-extended-combo-box-control_2.cpp)]  
  
4.  Associate the image list with the control with a call to [CComboBoxEx::SetImageList](../Topic/CComboBoxEx::SetImageList.md).  
  
 Once the image list has been associated with the control, you can individually specify the images each item will use for the three possible states.  For more information, see [Setting the Images for an Individual Item](../mfc/setting-the-images-for-an-individual-item.md).  
  
## 참고 항목  
 [CComboBoxEx 사용](../mfc/using-ccomboboxex.md)   
 [컨트롤](../mfc/controls-mfc.md)