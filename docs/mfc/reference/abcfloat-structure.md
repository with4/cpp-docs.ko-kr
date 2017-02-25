---
title: "ABCFLOAT 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ABCFLOAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ABCFLOAT 구조체"
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# ABCFLOAT 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `ABCFLOAT` structure contains the A, B, and C widths of a font character.  
  
## 구문  
  
```  
  
      typedef struct _ABCFLOAT { /* abcf */  
   FLOAT abcfA;  
   FLOAT abcfB;  
   FLOAT abcfC;  
} ABCFLOAT;  
```  
  
#### 매개 변수  
 *abcfA*  
 Specifies the A spacing of the character.  The A spacing is the distance to add to the current position before drawing the character glyph.  
  
 *abcfB*  
 Specifies the B spacing of the character.  The B spacing is the width of the drawn portion of the character glyph.  
  
 *abcfC*  
 Specifies the C spacing of the character.  The C spacing is the distance to add to the current position to provide white space to the right of the character glyph.  
  
## 설명  
 The A, B, and C widths are measured along the base line of the font.  The character increment \(total width\) of a character is the sum of the A, B, and C spaces.  Either the A or the C space can be negative to indicate underhangs or overhangs.  
  
## 요구 사항  
 **Header:** wingdi.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)