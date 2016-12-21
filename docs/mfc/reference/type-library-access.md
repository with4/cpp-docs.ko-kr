---
title: "형식 라이브러리 액세스 | Microsoft Docs"
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
  - "형식 라이브러리, 액세스"
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: 14
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 형식 라이브러리 액세스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Type libraries expose the interfaces of an OLE control to other OLE\-aware applications.  Each OLE control must have a type library if one or more interfaces are to be exposed.  
  
 The following macros allow an OLE control to provide access to its own type library:  
  
### Type Library Access  
  
|||  
|-|-|  
|[DECLARE\_OLETYPELIB](../Topic/DECLARE_OLETYPELIB.md)|Declares a `GetTypeLib` member function of an OLE control \(must be used in the class declaration\).|  
|[IMPLEMENT\_OLETYPELIB](../Topic/IMPLEMENT_OLETYPELIB.md)|Implements a `GetTypeLib` member function of an OLE control \(must be used in the class implementation\).|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)