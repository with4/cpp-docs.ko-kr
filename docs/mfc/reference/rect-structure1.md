---
title: "RECT 구조체 | Microsoft Docs"
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
  - "LPRECT"
  - "RECT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LPRECT 구조체"
  - "RECT 구조체"
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RECT 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`RECT`  구조체는 사각형의 왼쪽 위 모퉁이 오른쪽 아래 모퉁이의 좌표를 정의 합니다.  
  
## 구문  
  
```  
  
      typedef struct tagRECT {   
   LONG left;  
   LONG top;  
   LONG right;  
   LONG bottom;  
} RECT;  
```  
  
## 멤버  
 `left`  
 사각형의 왼쪽 위 모퉁이의 x좌표를 그립니다.  
  
 `top`  
 사각형의 왼쪽 위 모퉁이의 y좌표를 그립니다.  
  
 `right`  
 사각형의 오른쪽 아래 모퉁이의 x좌표를 그립니다.  
  
 `bottom`  
 사각형의 오른쪽 아래 모퉁이의 y좌표를 그립니다.  
  
## 예제  
 [!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/CPP/rect-structure1_1.cpp)]  
  
## 요구 사항  
 **헤더:** windef.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRect Class](../../atl-mfc-shared/reference/crect-class.md)