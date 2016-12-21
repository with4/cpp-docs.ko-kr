---
title: "디스패치 맵 | Microsoft Docs"
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
  - "vc.mfc.macros.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "디스패치 맵 매크로"
  - "디스패치 맵"
  - "디스패치 맵 매크로"
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
caps.latest.revision: 14
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 디스패치 맵
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE Automation provides ways to call methods and to access properties across applications.  The mechanism supplied by the Microsoft Foundation Class Library for dispatching these requests is the "dispatch map," which designates the internal and external names of object functions and properties, as well as the data types of the properties themselves and of function arguments.  
  
### Dispatch Maps  
  
|||  
|-|-|  
|[DECLARE\_DISPATCH\_MAP](../Topic/DECLARE_DISPATCH_MAP.md)|Declares that a dispatch map will be used to expose a class's methods and properties \(must be used in the class declaration\).|  
|[BEGIN\_DISPATCH\_MAP](../Topic/BEGIN_DISPATCH_MAP.md)|Starts the definition of a dispatch map.|  
|[END\_DISPATCH\_MAP](../Topic/END_DISPATCH_MAP.md)|Ends the definition of a dispatch map.|  
|[DISP\_FUNCTION](../Topic/DISP_FUNCTION.md)|Used in a dispatch map to define an OLE automation function.|  
|[DISP\_PROPERTY](../Topic/DISP_PROPERTY.md)|Defines an OLE automation property.|  
|[DISP\_PROPERTY\_EX](../Topic/DISP_PROPERTY_EX.md)|Defines an OLE automation property and names the Get and Set functions.|  
|[DISP\_PROPERTY\_NOTIFY](../Topic/DISP_PROPERTY_NOTIFY.md)|Defines an OLE automation property with notification.|  
|[DISP\_PROPERTY\_PARAM](../Topic/DISP_PROPERTY_PARAM.md)|Defines an OLE automation property that takes parameters and names the Get and Set functions.|  
|[DISP\_DEFVALUE](../Topic/DISP_DEFVALUE.md)|Makes an existing property the default value of an object.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)