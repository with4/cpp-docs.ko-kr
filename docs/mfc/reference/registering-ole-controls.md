---
title: "OLE 컨트롤 등록 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE 컨트롤, 등록"
  - "OLE 컨트롤 등록"
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# OLE 컨트롤 등록
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE controls, like other OLE server objects, can be accessed by other OLE\-aware applications.  This is achieved by registering the control's type library and class.  
  
 The following functions allow you to add and remove the control's class, property pages, and type library in the Windows registration database:  
  
### Registering OLE Controls  
  
|||  
|-|-|  
|[AfxOleRegisterControlClass](../Topic/AfxOleRegisterControlClass.md)|Adds the control's class to the registration database.|  
|[AfxOleRegisterPropertyPageClass](../Topic/AfxOleRegisterPropertyPageClass.md)|Adds a control property page to the registration database.|  
|[AfxOleRegisterTypeLib](../Topic/AfxOleRegisterTypeLib.md)|Adds the control's type library to the registration database.|  
|[AfxOleUnregisterClass](../Topic/AfxOleUnregisterClass.md)|Removes a control class or a property page class from the registration database.|  
|[AfxOleUnregisterTypeLib](../Topic/AfxOleUnregisterTypeLib.md)|Removes the control's type library from the registration database.|  
  
 `AfxOleRegisterTypeLib` is typically called in a control DLL's implementation of `DllRegisterServer`.  Similarly, `AfxOleUnregisterTypeLib` is called by `DllUnregisterServer`.  `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass`, and `AfxOleUnregisterClass` are typically called by the `UpdateRegistry` member function of a control's class factory or property page.  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)