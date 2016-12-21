---
title: "OLE 컨트롤의 지속성 | Microsoft Docs"
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
  - "vc.mfc.macros.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE 컨트롤, 지속성"
  - "지속성, OLE 컨트롤"
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
caps.latest.revision: 17
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE 컨트롤의 지속성
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

One capability of OLE controls is property persistence \(or serialization\), which allows the OLE control to read or write property values to and from a file or stream.  A container application can use serialization to store a control's property values even after the application has destroyed the control.  The property values of the OLE control can then be read from the file or stream when a new instance of the control is created at a later time.  
  
### Persistence of OLE Controls  
  
|||  
|-|-|  
|[PX\_Blob](../Topic/PX_Blob.md)|Exchanges a control property that stores binary large object \(BLOB\) data.|  
|[PX\_Bool](../Topic/PX_Bool.md)|Exchanges a control property of type **BOOL**.|  
|[PX\_Color](../Topic/PX_Color.md)|Exchanges a color property of a control.|  
|[PX\_Currency](../Topic/PX_Currency.md)|Exchanges a control property of type **CY**.|  
|[PX\_DataPath](../Topic/PX_DataPath.md)|Exchanges a control property of type `CDataPathProperty`.|  
|[PX\_Double](../Topic/PX_Double.md)|Exchanges a control property of type **double**.|  
|[PX\_Font](../Topic/PX_Font.md)|Exchanges a font property of a control.|  
|[PX\_Float](../Topic/PX_Float.md)|Exchanges a control property of type **float**.|  
|[PX\_IUnknown](../Topic/PX_IUnknown.md)|Exchanges a control property of undefined type.|  
|[PX\_Long](../Topic/PX_Long.md)|Exchanges a control property of type **long**.|  
|[PX\_Picture](../Topic/PX_Picture.md)|Exchanges a picture property of a control.|  
|[PX\_Short](../Topic/PX_Short.md)|Exchanges a control property of type **short**.|  
|[PX\_ULong](../Topic/PX_ULong.md)|Exchanges a control property of type **ULONG**.|  
|[PX\_UShort](../Topic/PX_UShort.md)|Exchanges a control property of type **USHORT**.|  
|[PX\_String](../Topic/PX_String.md)|Exchanges a character string control property.|  
|[PX\_VBXFontConvert](../Topic/PX_VBXFontConvert.md)|Exchanges a VBX control's font\-related properties into an OLE control font property.|  
  
 In addition, the `AfxOleTypeMatchGuid` global function is provided to test for a match between a `TYPEDESC` and a given GUID.  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)