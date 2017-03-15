---
title: "CMFCImagePaintArea::IMAGE_EDIT_MODE 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IMAGE_EDIT_MODE Enumeration"
  - "CMFCImagePaintArea::IMAGE_EDIT_MODE Enumeration"
  - "CMFCImagePaintArea.IMAGE_EDIT_MODE Enumeration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IMAGE_EDIT_MODE 열거형 메서드"
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# CMFCImagePaintArea::IMAGE_EDIT_MODE 열거형
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Specifies a drawing mode that you use to modify an image in an image editor dialog box.  
  
## 구문  
  
```  
enum IMAGE_EDIT_MODE  
{  
   IMAGE_EDIT_MODE_PEN = 0,  
   IMAGE_EDIT_MODE_FILL,  
   IMAGE_EDIT_MODE_LINE,  
   IMAGE_EDIT_MODE_RECT,  
   IMAGE_EDIT_MODE_ELLIPSE,  
   IMAGE_EDIT_MODE_COLOR  
};  
```  
  
## 멤버  
  
|||  
|-|-|  
|Name|설명|  
|`IMAGE_EDIT_MODE_PEN`|Used to draw individual pixels.|  
|`IMAGE_EDIT_MODE_FILL`|Used to fill all adjacent areas that contain the color at the current cursor location.|  
|`IMAGE_EDIT_MODE_LINE`|Used to draw a line.|  
|`IMAGE_EDIT_MODE_RECT`|Used to draw a rectangle.|  
|`IMAGE_EDIT_MODE_ELLIPSE`|Used to draw an ellipse.|  
|`IMAGE_EDIT_MODE_COLOR`|Used to set the current color to the color at the current cursor location.|  
  
### 설명  
 The `CMFCImagePaintArea` and `CMFCImageEditorDialog` classes use this enumeration to set the current drawing mode.  The drawing mode and current color are used to modify the picture area in an image editor dialog box.  `CMFCImagePaintArea` 및 `CMFCImageEditorDialog`에 대한 자세한 내용은 [CMFCImagePaintArea Class](../../mfc/reference/cmfcimagepaintarea-class.md) 및 [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md)을 참조하십시오.  
  
 When you select a color from an image by using the `IMAGE_EDIT_MODE_COLOR` drawing mode, the framework sets the current drawing mode to `IMAGE_EDIT_MODE_PEN`.  
  
## 요구 사항  
 **Header:** afximagepaintarea.h  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCImagePaintArea Class](../../mfc/reference/cmfcimagepaintarea-class.md)   
 [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md)