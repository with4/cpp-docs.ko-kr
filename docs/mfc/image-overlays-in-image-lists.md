---
title: "이미지 목록의 이미지 오버레이 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CImageList 클래스, 이미지 오버레이"
  - "이미지 목록[C++], 이미지 오버레이"
  - "오버레이"
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 이미지 목록의 이미지 오버레이
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Every image list \([CImageList](../mfc/reference/cimagelist-class.md)\) includes a list of images to use as overlay masks.  An "overlay mask" is an image drawn transparently over another image.  Any image can be used as an overlay mask.  You can specify up to four overlay masks per image list.  
  
 You add the index of an image to the list of overlay masks by using the [SetOverlayImage](../Topic/CImageList::SetOverlayImage.md) member function, the index of an image, and the index of an overlay mask.  Note that the indices for the overlay masks are one\-based rather than zero\-based.  
  
 You draw an overlay mask over an image using a single call to **Draw**.  The parameters include the index of the image to draw and the index of an overlay mask.  You must use the [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) macro to specify the index of the overlay mask.  You can also specify an overlay image when calling the [DrawIndirect](../Topic/CImageList::DrawIndirect.md) member function.  
  
## 참고 항목  
 [CImageList 사용](../mfc/using-cimagelist.md)   
 [컨트롤](../mfc/controls-mfc.md)