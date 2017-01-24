---
title: "응용 프로그램 컨트롤 | Microsoft Docs"
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
  - "응용 프로그램 컨트롤"
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 응용 프로그램 컨트롤
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE requires substantial control over applications and their objects.  The OLE system DLLs must be able to launch and release applications automatically, coordinate their production and modification of objects, and so on.  The functions in this topic meet those requirements.  In addition to being called by the OLE system DLLs, these functions must sometimes be called by applications as well.  
  
### Application Control  
  
|||  
|-|-|  
|[AfxOleCanExitApp](../Topic/AfxOleCanExitApp.md)|Indicates whether the application can terminate.|  
|[AfxOleGetMessageFilter](../Topic/AfxOleGetMessageFilter.md)|Retrieves the application's current message filter.|  
|[AfxOleGetUserCtrl](../Topic/AfxOleGetUserCtrl.md)|Retrieves the current user\-control flag.|  
|[AfxOleSetUserCtrl](../Topic/AfxOleSetUserCtrl.md)|Sets or clears the user\-control flag.|  
|[AfxOleLockApp](../Topic/AfxOleLockApp.md)|Increments the framework's global count of the number of active objects in an application.|  
|[AfxOleUnlockApp](../Topic/AfxOleUnlockApp.md)|Decrements the framework's count of the number of active objects in an application.|  
|[AfxOleRegisterServerClass](../Topic/AfxOleRegisterServerClass.md)|Registers a server in the OLE system registry.|  
|[AfxOleSetEditMenu](../Topic/AfxOleSetEditMenu.md)|Implements the user interface for the *typename* Object command.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)