---
title: "런타임 개체 모델 서비스 | Microsoft Docs"
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
  - "런타임 개체 모델 서비스 매크로"
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
caps.latest.revision: 15
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 런타임 개체 모델 서비스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The classes [CObject](../../mfc/reference/cobject-class.md) and [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) encapsulate several object services, including access to run\-time class information, serialization, and dynamic object creation.  All classes derived from `CObject` inherit this functionality.  
  
 Access to run\-time class information enables you to determine information about an object's class at run time.  The ability to determine the class of an object at run time is useful when you need extra type\-checking of function arguments and when you must write special\-purpose code based on the class of an object.  Run\-time class information is not supported directly by the C\+\+ language.  
  
 Serialization is the process of writing or reading an object's contents to or from a file.  You can use serialization to store an object's contents even after the application exits.  The object can then be read from the file when the application is restarted.  Such data objects are said to be "persistent."  
  
 Dynamic object creation enables you to create an object of a specified class at run time.  For example, document, view, and frame objects must support dynamic creation because the framework needs to create them dynamically.  
  
 The following table lists the MFC macros that support run\-time class information, serialization, and dynamic creation.  
  
 For more information on these run\-time object services and serialization, see the article [CObject Class: Accessing Run\-Time Class Information](../../mfc/accessing-run-time-class-information.md).  
  
### Run\-Time Object Model Services Macros  
  
|||  
|-|-|  
|[DECLARE\_DYNAMIC](../Topic/DECLARE_DYNAMIC.md)|Enables access to run\-time class information \(must be used in the class declaration\).|  
|[DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md)|Enables dynamic creation and access to run\-time class information \(must be used in the class declaration\).|  
|[DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md)|Enables serialization and access to run\-time class information \(must be used in the class declaration\).|  
|[IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md)|Enables access to run\-time class information \(must be used in the class implementation\).|  
|[IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md)|Enables dynamic creation and access to run\-time information \(must be used in the class implementation\).|  
|[IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md)|Permits serialization and access to run\-time class information \(must be used in the class implementation\).|  
|[RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md)|Returns the `CRuntimeClass` structure that corresponds to the named class.|  
  
 OLE frequently requires the dynamic creation of objects at run time.  For example, an OLE server application must be able to create OLE items dynamically in response to a request from a client.  Similarly, an automation server must be able to create items in response to requests from automation clients.  
  
 The Microsoft Foundation Class Library provides two macros specific to OLE.  
  
### Dynamic Creation of OLE Objects  
  
|||  
|-|-|  
|[DECLARE\_OLECREATE](../Topic/DECLARE_OLECREATE.md)|Enables objects to be created through OLE automation.|  
|[IMPLEMENT\_OLECREATE](../Topic/IMPLEMENT_OLECREATE.md)|Enables objects to be created by the OLE system.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)