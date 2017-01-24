---
title: "클래스 팩터리 및 라이선스 | Microsoft Docs"
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
  - "vc.mfc.macros.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클래스 팩터리, 및 라이선스"
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
caps.latest.revision: 13
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 클래스 팩터리 및 라이선스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

To create an instance of your OLE control, a container application calls a member function of the control's class factory.  Because your control is an actual OLE object, the class factory is responsible for creating instances of your control.  Every OLE control class must have a class factory.  
  
 Another important feature of OLE controls is their ability to enforce a license.  ControlWizard allows you to incorporate licensing during the creation of your control project.  For more information on control licensing, see the article [ActiveX Controls: Licensing An ActiveX Control](../../mfc/mfc-activex-controls-licensing-an-activex-control.md).  
  
 The following table lists several macros and functions used to declare and implement your control's class factory and to license of your control.  
  
### Class Factories and Licensing  
  
|||  
|-|-|  
|[DECLARE\_OLECREATE\_EX](../Topic/DECLARE_OLECREATE_EX.md)|Declares the class factory for an OLE control or property page.|  
|[IMPLEMENT\_OLECREATE\_EX](../Topic/IMPLEMENT_OLECREATE_EX.md)|Implements the control's `GetClassID` function and declares an instance of the class factory.|  
|[BEGIN\_OLEFACTORY](../Topic/BEGIN_OLEFACTORY.md)|Begins the declaration of any licensing functions.|  
|[END\_OLEFACTORY](../Topic/END_OLEFACTORY.md)|Ends the declaration of any licensing functions.|  
|[AfxVerifyLicFile](../Topic/AfxVerifyLicFile.md)|Verifies whether a control is licensed for use on a particular computer.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)