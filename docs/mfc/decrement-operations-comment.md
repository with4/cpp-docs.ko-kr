---
title: "// 작업 주석 | Microsoft Docs"
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
  - "주석, MFC"
  - "MFC 소스 파일, 작업 주석"
  - "MFC 소스 파일의 작업 주석"
ms.assetid: f3bff48d-26be-4db6-8435-9e4d079838c9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# // 작업 주석
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The `// Operations` section of an MFC class declaration contains member functions that you can call on the object to make it do things or perform actions \(perform operations\).  These functions are typically non\-**const** because they usually have side effects.  They may be virtual or nonvirtual depending on the needs of the class.  Typically, these members are public.  
  
 In the sample listing from class `CStdioFile`, in [An Example of the Comments](../mfc/an-example-of-the-comments.md), the list includes two member functions under this comment: `ReadString` and `WriteString`.  
  
 As with attributes, operations can be further subdivided.  
  
## 참고 항목  
 [MFC 소스 파일 사용](../mfc/using-the-mfc-source-files.md)   
 [주석 예](../mfc/an-example-of-the-comments.md)   
 [\/\/ 구현 주석](../mfc/decrement-implementation-comment.md)   
 [\/\/ 생성자 주석](../mfc/decrement-constructors-comment.md)   
 [\/\/ 특성 주석](../mfc/decrement-attributes-comment.md)   
 [\/\/ 재정의 가능 주석](../mfc/decrement-overridables-comment.md)