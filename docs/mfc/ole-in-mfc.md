---
title: "MFC의 OLE | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "응용 프로그램[OLE], OLE 정보"
  - "MFC[C++], OLE 및"
  - "OLE[C++]"
  - "OLE 응용 프로그램[C++], OLE 정보"
  - "OLE 구성 요소 개체 모델(COM)"
  - "OLE 컨테이너, OLE 정보"
  - "OLE 항목"
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC의 OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

These articles explain the fundamentals of OLE programming using MFC.  MFC provides the easiest way to write programs that use OLE:  
  
-   To use OLE visual editing \(in\-place activation\).  
  
-   To work as OLE containers or servers.  
  
-   To implement drag\-and\-drop functionality.  
  
-   To work with date and time data.  
  
-   To manage the state data of MFC modules, including exported DLL function entry points, OLE\/COM interface entry points, and window procedure entry points.  
  
 You can also use [Automation](../mfc/automation.md) or [Remote Automation](../mfc/remote-automation.md) to operate another program from your program.  
  
> [!NOTE]
>  The term OLE denotes the technologies associated with linking and embedding, including OLE containers, OLE servers, OLE items, in\-place activation \(or visual editing\), trackers, drag and drop, and menu merging.  The term Active applies to the Component Object Model \(COM\) and COM\-based objects such as ActiveX controls.  OLE Automation is now called Automation.  
  
## 단원 내용  
 [OLE Background](../mfc/ole-background.md)  
 Discusses OLE and provides conceptual information about how it works.  
  
 [활성화](../mfc/activation-cpp.md)  
 Describes the role of activation in editing OLE items.  
  
 [컨테이너](../mfc/containers.md)  
 Provides links to using containers in OLE.  
  
 [Data Objects and Data Sources](../mfc/data-objects-and-data-sources-ole.md)  
 Provides links to topics discussing the use of the `COleDataObject` and `COleDataSource` classes.  
  
 [끌어서 놓기](../mfc/drag-and-drop-ole.md)  
 Discusses using copying and pasting with OLE.  
  
 [OLE Menus and Resources](../mfc/menus-and-resources-ole.md)  
 Explains the use of menus and resources in MFC OLE document applications.  
  
 [등록](../mfc/registration.md)  
 Discusses server installation and initialization.  
  
 [서버](../mfc/servers.md)  
 Describes how to create OLE items \(or components\) for use by container applications.  
  
 [Trackers](../mfc/trackers.md)  
 Provides information about the `CRectTracker` class, which provides a graphical interface to enable users to interact with OLE client items.  
  
## 관련 단원  
 [연결 지점](../mfc/connection-points.md)  
 Explains how to implement connection points \(formerly known as OLE connection points\) using the MFC classes `CCmdTarget` and `CConnectionPoint`.  
  
 [Container\/Server COM Components](../mfc/containers-advanced-features.md)  
 Describes the steps necessary to incorporate optional advanced features into existing container applications.  
  
 [The Component Object Model](http://msdn.microsoft.com/library/windows/desktop/ms694363)  
 Describes using OLE without MFC.  
  
## 참고 항목  
 [개념](../mfc/mfc-concepts.md)