---
title: "CDC::GrayString에 대한 콜백 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Callback Function for CDC::GrayString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "콜백 함수, CDC::GrayString"
ms.assetid: 5217e183-df48-426b-931b-6245022ca36f
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CDC::GrayString에 대한 콜백 함수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

*OutputFunc* is a placeholder for the application\-supplied callback function name.  
  
## 구문  
  
```  
  
      BOOL CALLBACK EXPORT OutputFunc(   
   HDC hDC,   
   LPARAM lpData,   
   int nCount    
);  
```  
  
#### 매개 변수  
 `hDC`  
 Identifies a memory device context with a bitmap of at least the width and height specified by `nWidth` and `nHeight` to `GrayString`.  
  
 `lpData`  
 Points to the character string to be drawn.  
  
 `nCount`  
 Specifies the number of characters to output.  
  
## 반환 값  
 The callback function's return value must be **TRUE** to indicate success; otherwise it is **FALSE**.  
  
## 설명  
 The callback function \(*OutputFunc*\) must draw an image relative to the coordinates \(0,0\) rather than \(*x*, *y*\).  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GrayString](../Topic/CDC::GrayString.md)