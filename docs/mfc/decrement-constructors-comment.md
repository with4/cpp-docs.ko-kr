---
title: "// 생성자 주석 | Microsoft Docs"
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
  - "주석, 생성자 주석"
  - "주석, MFC"
  - "생성자[C++], 선언"
  - "생성자 주석"
  - "선언, 생성자"
  - "생성자 선언, 코드 주석"
  - "인스턴스 생성자, 코드 주석"
  - "MFC 소스 파일, 생성자 주석"
ms.assetid: f400774e-ba85-49ed-85b7-70ef2f7dcb2b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# // 생성자 주석
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The `// Constructors` section of an MFC class declaration declares constructors \(in the C\+\+ sense\) as well as any initialization functions required to really use the object.  For example, `CWnd::Create` is in the constructors section because before you use the `CWnd` object, it must be "fully constructed" by first calling the C\+\+ constructor and then calling the **Create** function.  Typically, these members are public.  
  
 For example, class `CStdioFile` has three constructors, one of which is shown in the listing under [An Example of the Comments](../mfc/an-example-of-the-comments.md).  
  
## 참고 항목  
 [MFC 소스 파일 사용](../mfc/using-the-mfc-source-files.md)   
 [\/\/ 구현 주석](../mfc/decrement-implementation-comment.md)   
 [\/\/ 특성 주석](../mfc/decrement-attributes-comment.md)   
 [\/\/ 작업 주석](../mfc/decrement-operations-comment.md)   
 [\/\/ 재정의 가능 주석](../mfc/decrement-overridables-comment.md)