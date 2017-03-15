---
title: "추적기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램[OLE], 추적기"
  - "CDC 클래스, 추적기"
  - "CRectTracker 클래스, 추적기 구현"
  - "OLE 응용 프로그램[C++], 추적기"
  - "OLE 컨테이너, 추적기"
  - "OLE 서버 응용 프로그램, 추적기"
  - "추적기"
  - "OLE 항목 추적"
ms.assetid: dcd09399-6637-4621-80e5-d12670429787
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 추적기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The [CRectTracker](../mfc/reference/crecttracker-class.md) class provides a user interface between rectangular items in your application and your user by providing a variety of display styles.  These styles include solid, hatched, or dashed borders; a hatched pattern that covers the item; and resize handles that can be located on the outside or inside of a border.  Trackers are often used in conjunction with OLE items, that is, objects derived from `COleClientItem`.  The tracker rectangles give visual cues on the current status of the item.  
  
 The MFC OLE sample [OCLIENT](../top/visual-cpp-samples.md) demonstrates a common interface using trackers and OLE client items from the viewpoint of a container application.  For a demonstration of the different styles and abilities of a tracker object, see the MFC general sample [TRACKER](../top/visual-cpp-samples.md).  
  
 For more information on implementing trackers in your OLE application, see [Trackers: Implementing Trackers in Your OLE Application](../mfc/trackers-implementing-trackers-in-your-ole-application.md)  
  
## 참고 항목  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleClientItem Class](../mfc/reference/coleclientitem-class.md)