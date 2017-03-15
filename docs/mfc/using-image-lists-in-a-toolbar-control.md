---
title: "도구 모음 컨트롤에서 이미지 목록 사용 | Microsoft Docs"
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
  - "CToolBarCtrl 클래스, 이미지 목록"
  - "이미지 목록[C++], 도구 모음 컨트롤"
  - "도구 모음 컨트롤[MFC], 이미지"
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 도구 모음 컨트롤에서 이미지 목록 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

By default, the images used by the buttons in a toolbar control are stored as a single bitmap.  However, you can also store button images in a set of image lists.  The toolbar control object can use up to three separate image lists:  
  
-   Enabled image list   Contains images for toolbar buttons that are currently enabled.  
  
-   Disabled image list   Contains images for toolbar buttons that are currently disabled.  
  
-   Highlighted image list   Contains images for toolbar buttons that are currently highlighted.  This image list is used only when the toolbar uses the **TBSTYLE\_FLAT** style.  
  
 These image lists are used by the toolbar control when you associate them with the `CToolBarCtrl` object.  This association is accomplished by making calls to [CToolBarCtrl::SetImageList](../Topic/CToolBarCtrl::SetImageList.md), [SetDisabledImageList](../Topic/CToolBarCtrl::SetDisabledImageList.md), and [SetHotImageList](../Topic/CToolBarCtrl::SetHotImageList.md).  
  
 By default, MFC uses the `CToolBar` class to implement MFC application toolbars.  However, the `GetToolBarCtrl` member function can be used to retrieve the embedded `CToolBarCtrl` object.  You can then make calls to `CToolBarCtrl` member functions using the returned object.  
  
 The following example demonstrates this technique by assigning an enabled \(`m_ToolBarImages`\) and disabled \(`m_ToolBarDisabledImages`\) image list to a `CToolBarCtrl` object \(`m_ToolBarCtrl`\).  
  
 [!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/CPP/using-image-lists-in-a-toolbar-control_1.cpp)]  
  
> [!NOTE]
>  The image lists used by the toolbar object must be permanent objects.  For this reason, they are commonly data members of an MFC class; in this example, the main frame window class.  
  
 Once the image lists are associated with the `CToolBarCtrl` object, the framework automatically displays the proper button image.  
  
## 참고 항목  
 [CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)