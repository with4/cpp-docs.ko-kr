---
title: "이미지 목록 사용 | Microsoft Docs"
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
  - "CImageList 클래스, using"
  - "이미지 목록[C++]"
  - "목록[C++], 이미지"
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 이미지 목록 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Typical usage of an image list follows the pattern below:  
  
-   Construct a [CImageList](../mfc/reference/cimagelist-class.md) object and call one of the overloads of its [Create](../Topic/CImageList::Create.md) function to create an image list and attach it to the `CImageList` object.  
  
-   If you didn't add images when you created the image list, add images to the image list by calling the [Add](../Topic/CImageList::Add.md) or [Read](../Topic/CImageList::Read.md) member function.  
  
-   Associate the image list with a control by calling the appropriate member function of that control, or draw images from the image list yourself using the image list's [Draw](../Topic/CImageList::Draw.md) member function.  
  
-   Perhaps allow the user to drag an image, using the image list's built\-in support for dragging.  
  
> [!NOTE]
>  If the image list was created with the **new** operator, you must destroy the `CImageList` object when you are done with it.  
  
## 참고 항목  
 [CImageList 사용](../mfc/using-cimagelist.md)   
 [컨트롤](../mfc/controls-mfc.md)