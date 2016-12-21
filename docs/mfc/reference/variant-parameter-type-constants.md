---
title: "가변 매개 변수 형식 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VTS_YPOS_HIMETRIC"
  - "VTS_PICTURE"
  - "VTS_FONT"
  - "VTS_XPOS_HIMETRIC"
  - "VTS_XPOS_PIXELS"
  - "VTS_XSIZE_HIMETRIC"
  - "VTS_YPOS_PIXELS"
  - "VTS_TRISTATE"
  - "VTS_HANDLE"
  - "VTS_YSIZE_HIMETRIC"
  - "VTS_COLOR"
  - "VTS_OPTEXCLUSIVE"
  - "VTS_YSIZE_PIXELS"
  - "VTS_XSIZE_PIXELS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "가변 데이터 상수"
  - "Variants"
  - "Variants, 매개 변수 형식 상수"
  - "VTS_COLOR 상수"
  - "VTS_FONT 상수"
  - "VTS_HANDLE 상수"
  - "VTS_OPTEXCLUSIVE 상수"
  - "VTS_PICTURE 상수"
  - "VTS_TRISTATE 상수"
  - "VTS_XPOS_HIMETRIC 상수"
  - "VTS_XPOS_PIXELS 상수"
  - "VTS_XSIZE_HIMETRIC 상수"
  - "VTS_XSIZE_PIXELS 상수"
  - "VTS_YPOS_HIMETRIC 상수"
  - "VTS_YPOS_PIXELS 상수"
  - "VTS_YSIZE_HIMETRIC 상수"
  - "VTS_YSIZE_PIXELS 상수"
ms.assetid: de99c7a9-7aae-4dc4-b723-40c6380543ab
caps.latest.revision: 14
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 가변 매개 변수 형식 상수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

This topic lists new constants that indicate variant parameter types designed for use with the OLE control classes of the Microsoft Foundation Class Library.  
  
 The following is a list of class constants:  
  
##  <a name="_mfc_variant_data_constants"></a> Variant Data Constants  
  
-   **VTS\_COLOR** A 32\-bit integer used to represent a RGB color value.  
  
-   **VTS\_FONT** A pointer to the **IFontDisp** interface of an OLE font object.  
  
-   **VTS\_HANDLE** A Windows handle value.  
  
-   **VTS\_PICTURE** A pointer to the `IPictureDisp` interface of an OLE picture object.  
  
-   **VTS\_OPTEXCLUSIVE** A 16\-bit value used for a control that is intended to be used in a group of controls, such as radio buttons.  This type tells the container that if one control in a group has a **TRUE** value, all others must be **FALSE**.  
  
-   **VTS\_TRISTATE** A 16\-bit signed integer used for properties that can have one of three possible values \(selected, cleared, unavailable\), for example, a check box.  
  
-   **VTS\_XPOS\_HIMETRIC** A 32\-bit unsigned integer used to represent a position along the x\-axis in **HIMETRIC** units.  
  
-   **VTS\_YPOS\_HIMETRIC** A 32\-bit unsigned integer used to represent a position along the y\-axis in **HIMETRIC** units.  
  
-   **VTS\_XPOS\_PIXELS** A 32\-bit unsigned integer used to represent a position along the x\-axis in pixels.  
  
-   **VTS\_YPOS\_PIXELS** A 32\-bit unsigned integer used to represent a position along the y\-axis in pixels.  
  
-   **VTS\_XSIZE\_PIXELS** A 32\-bit unsigned integer used to represent the width of a screen object in pixels.  
  
-   **VTS\_YSIZE\_PIXELS** A 32\-bit unsigned integer used to represent the height of a screen object in pixels.  
  
-   **VTS\_XSIZE\_HIMETRIC** A 32\-bit unsigned integer used to represent the width of a screen object in **HIMETRIC** units.  
  
-   **VTS\_YSIZE\_HIMETRIC** A 32\-bit unsigned integer used to represent the height of a screen object in **HIMETRIC** units.  
  
    > [!NOTE]
    >  Additional variant constants have been defined for all variant types, with the exception of **VTS\_FONT** and **VTS\_PICTURE**, that provide a pointer to the variant data constant.  These constants are named using the **VTS\_P**`constantname` convention.  For example, **VTS\_PCOLOR** is a pointer to a **VTS\_COLOR** constant.  
  
## 요구 사항  
 **헤더:** afxdisp.h  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)