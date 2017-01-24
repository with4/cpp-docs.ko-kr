---
title: "Rich Edit 컨트롤의 단어 분리 | Microsoft Docs"
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
  - "CRichEditCtrl의 단어 분리"
  - "CRichEditCtrl 클래스, 단어 분리"
  - "rich edit 컨트롤, 단어 분리"
  - "단어 분리"
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Rich Edit 컨트롤의 단어 분리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A rich edit control \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) calls a function called a "word break procedure" to find breaks between words and to determine where it can break lines.  The control uses this information when performing word\-wrap operations and when processing the CTRL\+LEFT and CTRL\+RIGHT key combinations.  An application can send messages to a rich edit control to replace the default word\-break procedure, to retrieve word\-break information, and to determine what line a given character falls on.  
  
## 참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)