---
title: "속성 페이지(MFC) | Microsoft Docs"
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
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC의 속성 페이지 데이터 전송 함수"
  - "속성 페이지, 전역 MFC 함수"
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
caps.latest.revision: 14
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 속성 페이지(MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Property pages display the current values of specific OLE control properties in a customizable, graphical interface for viewing and editing by supporting a data\-mapping mechanism based on dialog data exchange \(DDX\).  
  
 This data\-mapping mechanism maps property page controls to the individual properties of the OLE control.  The value of the control property reflects the status or content of the property page control.  The mapping between property page controls and properties is specified by **DDP\_** function calls in the property page's `DoDataExchange` member function.  The following is a list of **DDP\_** functions that exchange data entered using the property page of your control:  
  
### Property Page Data Transfer  
  
|||  
|-|-|  
|[DDP\_CBIndex](../Topic/DDP_CBIndex.md)|Links the selected string's index in a combo box with a control's property.|  
|[DDP\_CBString](../Topic/DDP_CBString.md)|Links the selected string in a combo box with a control's property.  The selected string can begin with the same letters as the property's value but does not need to match it fully.|  
|[DDP\_CBStringExact](../Topic/DDP_CBStringExact.md)|Links the selected string in a combo box with a control's property.  The selected string and the property's string value must match exactly.|  
|[DDP\_Check](../Topic/DDP_Check.md)|Links a check box in the control's property page with a control's property.|  
|[DDP\_LBIndex](../Topic/DDP_LBIndex.md)|Links the selected string's index in a list box with a control's property.|  
|[DDP\_LBString](../Topic/DDP_LBString.md)|Links the selected string in a list box with a control's property.  The selected string can begin with the same letters as the property's value but need not match it fully.|  
|[DDP\_LBStringExact](../Topic/DDP_LBStringExact.md)|Links the selected string in a list box with a control's property.  The selected string and the property's string value must match exactly.|  
|[DDP\_PostProcessing](../Topic/DDP_PostProcessing.md)|Finishes the transfer of property values from your control.|  
|[DDP\_Radio](../Topic/DDP_Radio.md)|Links a radio button group in the control's property page with a control's property.|  
|[DDP\_Text](../Topic/DDP_Text.md)|Links a control in the control's property page with a control's property.  This function handles several different types of properties, such as **double**, **short**, `BSTR`, and **long**.|  
  
 For more information about the `DoDataExchange` function and property pages, see the article [ActiveX Controls: Property Pages](../../mfc/mfc-activex-controls-property-pages.md).  
  
 The following is a list of macros used to create and manage property pages for an OLE control:  
  
### 속성 페이지  
  
|||  
|-|-|  
|[BEGIN\_PROPPAGEIDS](../Topic/BEGIN_PROPPAGEIDS.md)|Begins the list of property page IDs.|  
|[END\_PROPPAGEIDS](../Topic/END_PROPPAGEIDS.md)|Ends the list of property page IDs.|  
|[PROPPAGEID](../Topic/PROPPAGEID.md)|Declares a property page of the control class.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)