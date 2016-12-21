---
title: "// 특성 주석 | Microsoft Docs"
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
  - "MFC 소스 파일의 특성 주석"
  - "주석, 특성"
  - "MFC 소스 파일, 특성 주석"
  - "공용 특성 주석"
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# // 특성 주석
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The `// Attributes` section of an MFC class declaration contains the public attributes \(or properties\) of the object.  Typically these are member variables, or Get\/Set functions.  The "Get" and "Set" functions may or may not be virtual.  The "Get" functions are usually **const**, because in most cases they do not have side effects.  These members are normally public; protected and private attributes are typically found in the implementation section.  
  
 In the sample listing from class `CStdioFile`, under [An Example of the Comments](../mfc/an-example-of-the-comments.md), the list includes one member variable, `m_pStream`.  Class `CDC` lists nearly 20 members under this comment.  
  
> [!NOTE]
>  Large classes, such as `CDC` and `CWnd`, may have so many members that simply listing all the attributes in one group would not add much to clarity.  In such cases, the class library uses other comments as headings to further delineate the members.  For example, `CDC` uses `// Device-Context Functions`, `// Drawing Tool Functions`, `// Drawing Attribute Functions`, and more.  Groups that represent attributes will follow the usual syntax described above.  Many OLE classes have an implementation section called `// Interface Maps`.  
  
## 참고 항목  
 [MFC 소스 파일 사용](../mfc/using-the-mfc-source-files.md)   
 [주석 예](../mfc/an-example-of-the-comments.md)   
 [\/\/ 구현 주석](../mfc/decrement-implementation-comment.md)   
 [\/\/ 생성자 주석](../mfc/decrement-constructors-comment.md)   
 [\/\/ 작업 주석](../mfc/decrement-operations-comment.md)   
 [\/\/ 재정의 가능 주석](../mfc/decrement-overridables-comment.md)