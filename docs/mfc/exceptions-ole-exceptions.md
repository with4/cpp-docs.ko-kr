---
title: "예외: OLE 예외 | Microsoft Docs"
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
  - "예외 처리, OLE"
  - "예외, OLE"
  - "OLE 예외"
  - "OLE 예외, 처리 클래스"
  - "OLE, 예외"
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 예외: OLE 예외
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The techniques and facilities for handling exceptions in OLE are the same as those for handling other exceptions.  For further information on exception handling, see the article [C\+\+ 예외 처리](../cpp/cpp-exception-handling.md).  
  
 All exception objects are derived from the abstract base class `CException`.  MFC provides two classes for handling OLE exceptions:  
  
-   [COleException](../mfc/reference/coleexception-class.md) For handling general OLE exceptions.  
  
-   [COleDispatchException](../mfc/reference/coledispatchexception-class.md) For generating and handling OLE dispatch \(automation\) exceptions.  
  
 The difference between these two classes is the amount of information they provide and where they are used.  `COleException` has a public data member that contains the OLE status code for the exception.  `COleDispatchException` supplies more information, including the following:  
  
-   An application\-specific error code  
  
-   An error description, such as "Disk full"  
  
-   A Help context that your application can use to provide additional information for the user  
  
-   The name of your application's Help file  
  
-   The name of the application that generated the exception  
  
 `COleDispatchException` provides more information so that it can be used with products like Microsoft Visual Basic.  The verbal error description can be used in a message box or other notification; the Help information can be used to help the user respond to the conditions that caused the exception.  
  
 Two global functions correspond to the two OLE exception classes: [AfxThrowOleException](../Topic/AfxThrowOleException.md) and [AfxThrowOleDispatchException](../Topic/AfxThrowOleDispatchException.md).  Use them to throw general OLE exceptions and OLE dispatch exceptions, respectively.  
  
## 참고 항목  
 [예외 처리](../mfc/exception-handling-in-mfc.md)