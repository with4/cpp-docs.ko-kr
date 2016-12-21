---
title: "컨테이너: 클라이언트 항목 | Microsoft Docs"
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
  - "클라이언트 항목 및 OLE 컨테이너"
  - "OLE 컨테이너, 클라이언트 항목"
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 컨테이너: 클라이언트 항목
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article explains what client items are and from what classes your application should derive its client items.  
  
 Client items are data items belonging to another application that are either contained in or referenced by an OLE container application's document.  Client items whose data is contained within the document are embedded; those whose data is stored in another location referenced by the container document are linked.  
  
 The document class in an OLE application is derived from the class [COleDocument](../mfc/reference/coledocument-class.md) rather than from **CDocument**.  The `COleDocument` class inherits from **CDocument** all the functionality necessary for using the document\/view architecture on which MFC applications are based.  `COleDocument` also defines an interface that treats a document as a collection of `CDocItem` objects.  Several `COleDocument` member functions are provided for adding, retrieving, and deleting elements of that collection.  
  
 Every container application should derive at least one class from `COleClientItem`.  Objects of this class represent items, embedded or linked, in the OLE document.  These objects exist for the life of the document containing them, unless they are deleted from the document.  
  
 `CDocItem`는 `COleClientItem` 및 `COleServerItem`에 대한 기본 클래스입니다.  Objects of classes derived from these two act as intermediaries between the OLE item and the client and server applications, respectively.  Each time a new OLE item is added to the document, the MFC framework adds a new object of your client application's `COleClientItem`\-derived class to the document's collection of `CDocItem` objects.  
  
## 참고 항목  
 [컨테이너](../mfc/containers.md)   
 [컨테이너: 복합 파일](../mfc/containers-compound-files.md)   
 [컨테이너: 사용자 인터페이스 문제](../mfc/containers-user-interface-issues.md)   
 [컨테이너: 고급 기능](../mfc/containers-advanced-features.md)   
 [COleClientItem Class](../mfc/reference/coleclientitem-class.md)   
 [COleServerItem Class](../mfc/reference/coleserveritem-class.md)