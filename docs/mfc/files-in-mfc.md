---
title: "MFC의 파일 | Microsoft Docs"
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
  - "이진 액세스"
  - "이진 액세스, MFC의 이진 파일 작업"
  - "파일 I/O 클래스[C++]"
  - "파일[C++], 조작"
  - "파일[C++], MFC"
  - "파일[C++], serialization"
  - "I/O[C++], MFC 클래스"
  - "I/O[MFC]"
  - "MFC[C++], 파일 작업"
  - "지속성[C++]"
  - "serialization[C++], MFC 파일"
ms.assetid: ae25e2c5-2859-4679-ab97-438824e93ce1
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# MFC의 파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In the Microsoft Foundation Class Library \(MFC\), class [CFile](../mfc/reference/cfile-class.md) handles normal file I\/O operations.  This family of articles explains how to open and close files as well as read and write data to those files.  It also discusses file status operations.  For a description of how to use the object\-based serialization features of MFC as an alternative way of reading and writing data in files, see the article [Serialization](../mfc/serialization-in-mfc.md).  
  
> [!NOTE]
>  When you use MFC **CDocument** objects, the framework does much of the serialization work for you.  In particular, the framework creates and uses the `CFile` object.  You only have to write code in your override of the `Serialize` member function of class **CDocument**.  
  
 The `CFile` class provides an interface for general\-purpose binary file operations.  The `CStdioFile` and `CMemFile` classes derived from `CFile` and the `CSharedFile` class derived from `CMemFile` supply more specialized file services.  
  
 For more information about alternatives to MFC file handling, see [File Handling](../c-runtime-library/file-handling.md) in the *Run\-Time Library Reference*.  
  
 For information about derived `CFile` classes, see the [MFC hierarchy chart](../mfc/hierarchy-chart.md).  
  
## 수행할 작업  
 *Use CFile*  
  
-   [Open a file with CFile](../mfc/opening-files.md)  
  
-   [Read and write a file with CFile](../mfc/reading-and-writing-files.md)  
  
-   [Close a file with CFile](../mfc/closing-files.md)  
  
-   [Access file status with CFile](../mfc/accessing-file-status.md)  
  
 *Use MFC Serialization \(Object Persistence\)*  
  
-   [Create a serializable class](../mfc/serialization-making-a-serializable-class.md)  
  
-   [Serialize an object via a CArchive object](../mfc/serialization-serializing-an-object.md)  
  
-   [Create a CArchive object](../mfc/two-ways-to-create-a-carchive-object.md)  
  
-   [Use CArchive \<\< and \>\> operators](../mfc/using-the-carchive-output-and-input-operators.md)  
  
-   [Store and load CObjects and CObject\-derived objects via an archive](../mfc/storing-and-loading-cobjects-via-an-archive.md)  
  
## 참고 항목  
 [개념](../mfc/mfc-concepts.md)   
 [일반 MFC 항목](../mfc/general-mfc-topics.md)   
 [CArchive Class](../mfc/reference/carchive-class.md)   
 [CObject Class](../mfc/reference/cobject-class.md)   
 [How Do I: Use the CFile Class?](http://go.microsoft.com/fwlink/?LinkId=128046)