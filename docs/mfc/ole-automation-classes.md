---
title: "OLE 자동화 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "자동화 클래스"
  - "자동화 클래스, OLE 클래스"
  - "자동화, 클래스"
  - "OLE 자동화"
  - "OLE 자동화, 클래스"
ms.assetid: 96e5372b-ff8a-4da1-933b-4d9bbf4dceb3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE 자동화 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

These classes support automation clients \(applications that control other applications\).  Automation servers \(applications that can be controlled by other applications\) are supported through [dispatch maps](../mfc/reference/dispatch-maps.md).  
  
 [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)  
 Used to call automation servers from your automation client.  When adding a class, this class is used to create type\-safe classes for automation servers that provide a type library.  
  
 [COleDispatchException](../mfc/reference/coledispatchexception-class.md)  
 An exception resulting from an error during OLE automation.  Automation exceptions are thrown by automation servers and caught by automation clients.  
  
## 참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)