---
title: "CDC::EnumObjects에 대한 콜백 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Callback Function for CDC::EnumObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "콜백 함수, CDC::EnumObjects의 경우"
ms.assetid: 380088b1-88a5-4fb4-bbb5-dd9e8386572b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CDC::EnumObjects에 대한 콜백 함수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The *ObjectFunc* name is a placeholder for the application\-supplied function name.  
  
## 구문  
  
```  
  
      int CALLBACK EXPORT ObjectFunc(   
   LPSTR lpszLogObject,   
   LPSTR* lpData    
);  
```  
  
#### 매개 변수  
 *lpszLogObject*  
 Points to a [LOGPEN](../../mfc/reference/logpen-structure.md) or [LOGBRUSH](../../mfc/reference/logbrush-structure.md) data structure that contains information about the logical attributes of the object.  
  
 `lpData`  
 Points to the application\-supplied data passed to the `EnumObjects` function.  
  
## 반환 값  
 The callback function returns an `int`.  The value of this return is user\-defined.  If the callback function returns 0, `EnumObjects` stops enumeration early.  
  
## 설명  
 The actual name must be exported.  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::EnumObjects](../Topic/CDC::EnumObjects.md)