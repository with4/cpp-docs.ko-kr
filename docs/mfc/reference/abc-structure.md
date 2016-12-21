---
title: "ABC 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ABC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ABC 구조체"
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ABC 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The **ABC** structure contains the width of a character in a TrueType font.  
  
## 구문  
  
```  
  
      typedef struct _ABC { /* abc */  
   int abcA;  
   UINT abcB;  
   int abcC;  
} ABC;  
```  
  
#### 매개 변수  
 *abcA*  
 Specifies the A spacing of the character.  The A spacing is the distance to add to the current position before drawing the character glyph.  
  
 *abcB*  
 Specifies the B spacing of the character.  The B spacing is the width of the drawn portion of the character glyph.  
  
 *abcC*  
 Specifies the C spacing of the character.  The C spacing is the distance to add to the current position to provide white space to the right of the character glyph.  
  
## 설명  
 The total width of a character is the summation of the A, B, and C spaces.  Either the A or the C space can be negative to indicate underhangs or overhangs.  
  
## 요구 사항  
 **Header:** wingdi.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)