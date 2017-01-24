---
title: "파일 읽기 및 쓰기 | Microsoft Docs"
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
  - "CFile 클래스, 개체"
  - "CFile 클래스, CFile 개체 읽기 및 쓰기"
  - "예제[MFC], 파일 읽기"
  - "예제[MFC], 파일에 쓰기"
  - "파일[C++], 읽기"
  - "파일[C++], 쓰기"
  - "MFC[C++], 파일 작업"
  - "파일 읽기"
  - "파일에 쓰기[C++]"
ms.assetid: cac0c826-ba56-495f-99b3-ce6336f65763
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 파일 읽기 및 쓰기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

If you've used the C run\-time library file\-handling functions, MFC reading and writing operations will appear familiar.  This article describes reading directly from and writing directly to a `CFile` object.  You can also do buffered file I\/O with the [CArchive](../mfc/reference/carchive-class.md) class.  
  
#### To read from and write to the file  
  
1.  Use the **Read** and **Write** member functions to read and write data in the file.  
  
     또는  
  
2.  The `Seek` member function is also available for moving to a specific offset within the file.  
  
 **Read** takes a pointer to a buffer and the number of bytes to read and returns the actual number of bytes that were read.  If the required number of bytes could not be read because end\-of\-file \(EOF\) is reached, the actual number of bytes read is returned.  If any read error occurs, an exception is thrown.  **Write** is similar to **Read**, but the number of bytes written is not returned.  If a write error occurs, including not writing all the bytes specified, an exception is thrown.  If you have a valid `CFile` object, you can read from it or write to it as shown in the following example:  
  
 [!code-cpp[NVC_MFCFiles#2](../mfc/codesnippet/CPP/reading-and-writing-files_1.cpp)]  
  
> [!NOTE]
>  You should normally carry out input\/output operations within a **try**\/**catch** exception handling block.  For more information, see [Exception Handling \(MFC\)](../mfc/exception-handling-in-mfc.md).  
  
## 참고 항목  
 [파일](../mfc/files-in-mfc.md)