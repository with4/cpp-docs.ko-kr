---
title: "자동화 서버: 개체 수명 문제 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "자동화 서버, 개체 수명"
  - "수명, 자동화 서버"
  - "개체[C++], 수명"
  - "서버, 자동화 수명"
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 자동화 서버: 개체 수명 문제
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When an Automation client creates or activates an OLE item, the server passes the client a pointer to that object.  The client establishes a reference to the object through a call to the OLE function [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379).  This reference is in effect until the client calls [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317). \(Client applications written with the Microsoft Foundation Class Library's OLE classes need not make these calls; the framework does so.\) The OLE system and the server itself may establish references to the object.  A server should not destroy an object as long as external references to the object remain in effect.  
  
 The framework maintains an internal count of the number of references to any server object derived from [CCmdTarget](../mfc/reference/ccmdtarget-class.md).  This count is updated when an Automation client or other entity adds or releases a reference to the object.  
  
 When the reference count becomes 0, the framework calls the virtual function [CCmdTarget::OnFinalRelease](../Topic/CCmdTarget::OnFinalRelease.md).  The default implementation of this function calls the **delete** operator to delete this object.  
  
 The Microsoft Foundation Class Library provides additional facilities for controlling application behavior when external clients have references to the application's objects.  Besides maintaining a count of references to each object, servers maintain a global count of active objects.  The global functions [AfxOleLockApp](../Topic/AfxOleLockApp.md) and [AfxOleUnlockApp](../Topic/AfxOleUnlockApp.md) update the application's count of active objects.  If this count is nonzero, the application does not terminate when the user chooses Close from the system menu or Exit from the File menu.  Instead, the application's main window is hidden \(but not destroyed\) until all pending client requests have been completed.  Typically, `AfxOleLockApp` and `AfxOleUnlockApp` are called in the constructors and destructors, respectively, of classes that support Automation.  
  
 Sometimes circumstances force the server to terminate while a client still has a reference to an object.  For example, a resource on which the server depends may become unavailable, causing the server to encounter an error.  The user may also close a server document that contains objects to which other applications have references.  
  
 In the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)], see `IUnknown::AddRef` and `IUnknown::Release`.  
  
## 참고 항목  
 [자동화 서버](../mfc/automation-servers.md)   
 [AfxOleCanExitApp](../Topic/AfxOleCanExitApp.md)