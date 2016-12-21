---
title: "// 구현 주석 | Microsoft Docs"
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
  - "주석, 구현 주석"
  - "주석, MFC"
  - "MFC 소스 파일의 구현 주석"
  - "MFC 소스 파일, 구현 주석"
ms.assetid: 4d799c07-8e71-4a6b-90ab-8282d6ff48ce
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# // 구현 주석
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The `// Implementation` section is the most important part of any MFC class declaration.  
  
 This section houses all implementation details.  Both member variables and member functions can appear in this section.  Everything below this line could change in a future release of MFC.  Unless you cannot avoid it, you should not rely on details below the `// Implementation` line.  In addition, members declared below the implementation line are not documented, although some implementation is discussed in technical notes.  Overrides of virtual functions in the base class reside in this section, regardless of which section the base class function is defined in, because the fact that a function overrides the base class implementation is considered an implementation detail.  Typically, these members are protected, but not always.  
  
 Notice from the `CStdioFile` listing under [An Example of the Comments](../mfc/an-example-of-the-comments.md) that members declared below the `// Implementation` comment may be declared as **public**, `protected`, or `private`.  You should only use these members with caution, because they may change in the future.  Declaring a group of members as **public** may be necessary for the class library implementation to work correctly.  However, this does not mean that you may safely use the members so declared.  
  
> [!NOTE]
>  You may find comments of the remaining types either above or below the `// Implementation` comment.  In either case, they describe the kinds of members declared below them.  If they occur below the `// Implementation` comment, you should assume that the members may change in future versions of MFC.  
  
## 참고 항목  
 [MFC 소스 파일 사용](../mfc/using-the-mfc-source-files.md)   
 [주석 예](../mfc/an-example-of-the-comments.md)   
 [\/\/ 생성자 주석](../mfc/decrement-constructors-comment.md)   
 [\/\/ 특성 주석](../mfc/decrement-attributes-comment.md)   
 [\/\/ 작업 주석](../mfc/decrement-operations-comment.md)   
 [\/\/ 재정의 가능 주석](../mfc/decrement-overridables-comment.md)