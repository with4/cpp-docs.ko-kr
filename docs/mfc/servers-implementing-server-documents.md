---
title: "서버: 서버 문서 구현 | Microsoft Docs"
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
  - "OLE 서버 응용 프로그램, OLE 서버 구현"
  - "OLE 서버 응용 프로그램, 서버 문서 관리"
  - "서버 문서, 구현"
  - "서버, 서버 문서"
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 서버: 서버 문서 구현
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article explains the steps you must take to successfully implement a server document if you did not specify the OLE Server option in the application wizard.  
  
#### To define a server document class  
  
1.  Derive your document class from `COleServerDoc` instead of **CDocument**.  
  
2.  Create a server item class derived from `COleServerItem`.  
  
3.  Implement the `OnGetEmbeddedItem` member function of your server document class.  
  
     `OnGetEmbeddedItem` is called when the user of a container application creates or edits an embedded item.  It should return an item representing the entire document.  This should be an object of your `COleServerItem`\-derived class.  
  
4.  Override the `Serialize` member function to serialize the contents of the document.  You do not need to serialize the list of server items unless you are using them to represent the native data in your document.  For more information, see *Implementing Server Items* in the article [Servers: Server Items](../mfc/servers-server-items.md).  
  
 When a server document is created, the framework automatically registers the document with the OLE system DLLs.  This allows the DLLs to identify the server documents.  
  
 For more information, see [COleServerItem](../mfc/reference/coleserveritem-class.md) and [COleServerDoc](../mfc/reference/coleserverdoc-class.md) in the *Class Library Reference*.  
  
## 참고 항목  
 [서버](../mfc/servers.md)   
 [서버: 서버 항목](../mfc/servers-server-items.md)   
 [서버: 서버 구현](../mfc/servers-implementing-a-server.md)   
 [서버: 내부 프레임 창 구현](../mfc/servers-implementing-in-place-frame-windows.md)