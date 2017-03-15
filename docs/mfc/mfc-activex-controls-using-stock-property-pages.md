---
title: "MFC ActiveX 컨트롤: 스톡 속성 페이지 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CLSID_CPicturePropPage"
  - "CLSID_CColorPropPage"
  - "CLSID_CFontPropPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLSID_CColorPropPage"
  - "CLSID_CFontPropPage"
  - "CLSID_CPicturePropPage"
  - "색상 스톡 속성 페이지"
  - "글꼴, ActiveX 컨트롤"
  - "MFC ActiveX 컨트롤, 속성 페이지"
  - "그림 스톡 속성 페이지"
  - "스톡 속성, 스톡 속성 페이지"
ms.assetid: 22638d86-ff3e-4124-933e-54b7c2a25968
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC ActiveX 컨트롤: 스톡 속성 페이지 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article discusses the stock property pages available for ActiveX controls and how to use them.  
  
 For more information on using property pages in an ActiveX control, see the following articles:  
  
-   [MFC ActiveX Controls: Property Pages](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [MFC ActiveX Controls: Adding Another Custom Property Page](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
 MFC provides three stock property pages for use with ActiveX controls: **CLSID\_CColorPropPage**, **CLSID\_CFontPropPage**, and **CLSID\_CPicturePropPage**.  These pages display a user interface for stock color, font, and picture properties, respectively.  
  
 To incorporate these property pages into a control, add their IDs to the code that initializes the control's array of property page IDs.  In the following example, this code, located in the control implementation file \(.CPP\), initializes the array to contain all three stock property pages and the default property page \(named `CMyPropPage` in this example\):  
  
 [!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/CPP/mfc-activex-controls-using-stock-property-pages_1.cpp)]  
  
 Note that the count of property pages, in the `BEGIN_PROPPAGEIDS` macro, is 4.  This represents the number of property pages supported by the ActiveX control.  
  
 After these modifications have been made, rebuild your project.  Your control now has property pages for the font, picture, and color properties.  
  
> [!NOTE]
>  If the control stock property pages cannot be accessed, it may be because the MFC DLL \(MFCxx.DLL\) has not been properly registered with the current operating system.  This usually results from installing Visual C\+\+ under an operating system different from the one currently running.  
  
> [!TIP]
>  If your stock property pages are not visible \(see previous Note\), register the DLL by running RegSvr32.exe from the command line with the full path name to the DLL.  
  
## 참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX 컨트롤: 스톡 속성 추가](../mfc/mfc-activex-controls-adding-stock-properties.md)