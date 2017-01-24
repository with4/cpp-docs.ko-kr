---
title: "예외: 예외 내용 검사 | Microsoft Docs"
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
  - "catch 블록, MFC 함수 예외"
  - "CException 클래스, 클래스 예외"
  - "예외 처리, MFC"
  - "예외 throw, 예외 내용"
  - "try-catch 예외 처리, 예외 내용"
  - "try-catch 예외 처리, MFC 함수 예외"
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 예외: 예외 내용 검사
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Although a **catch** block's argument can be of almost any data type, the MFC functions throw exceptions of types derived from the class `CException`.  To catch an exception thrown by an MFC function, then, you write a **catch** block whose argument is a pointer to a `CException` object \(or an object derived from `CException`, such as `CMemoryException`\).  Depending on the exact type of the exception, you can examine the data members of the exception object to gather information about the specific cause of the exception.  
  
 For example, the `CFileException` type has the `m_cause` data member, which contains an enumerated type that specifies the cause of the file exception.  Some examples of the possible return values are **CFileException::fileNotFound** and **CFileException::readOnly**.  
  
 The following example shows how to examine the contents of a `CFileException`.  Other exception types can be examined similarly.  
  
 [!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/CPP/exceptions-examining-exception-contents_1.cpp)]  
  
 For more information, see [Exceptions: Freeing Objects in Exceptions](../mfc/exceptions-freeing-objects-in-exceptions.md) and [Exceptions: Catching and Deleting Exceptions](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## 참고 항목  
 [예외 처리](../mfc/exception-handling-in-mfc.md)