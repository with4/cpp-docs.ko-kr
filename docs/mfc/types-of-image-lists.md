---
title: "이미지 목록 형식 | Microsoft Docs"
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
  - "CImageList 클래스, 형식"
  - "이미지 목록[C++], 형식"
  - "목록[C++], 이미지"
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 이미지 목록 형식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

There are two types of image lists \([CImageList](../mfc/reference/cimagelist-class.md)\): nonmasked and masked.  A "nonmasked image list" consists of a color bitmap that contains one or more images.  A "masked image list" consists of two bitmaps of equal size.  The first is a color bitmap that contains the images, and the second is a monochrome bitmap that contains a series of masks — one for each image in the first bitmap.  
  
 One of the overloads of the **Create** member function takes a flag to indicate whether or not the image list is masked. \(The other overloads create masked image lists.\)  
  
 When a nonmasked image is drawn, it is simply copied into the target device context; that is, it is drawn over the existing background color of the device context.  When a masked image is drawn, the bits of the image are combined with the bits of the mask, typically producing transparent areas in the bitmap where the background color of the target device context shows through.  You can specify several drawing styles when drawing a masked image.  For example, you can specify that the image be dithered to indicate a selected object.  
  
## 참고 항목  
 [CImageList 사용](../mfc/using-cimagelist.md)   
 [컨트롤](../mfc/controls-mfc.md)