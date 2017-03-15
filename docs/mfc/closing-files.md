---
title: "파일 닫기 | Microsoft Docs"
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
  - "파일[C++], 닫기"
  - "MFC[C++], 파일 작업"
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 파일 닫기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

As usual in I\/O operations, once you finish with a file, you must close it.  
  
#### To close a file  
  
1.  Use the **Close** member function.  This function closes the file\-system file and flushes buffers if necessary.  
  
 If you allocated the [CFile](../mfc/reference/cfile-class.md) object on the frame \(as in the example shown in [Opening Files](../mfc/opening-files.md)\), the object will automatically be closed and then destroyed when it goes out of scope.  Note that deleting the `CFile` object does not delete the physical file in the file system.  
  
## 참고 항목  
 [파일](../mfc/files-in-mfc.md)