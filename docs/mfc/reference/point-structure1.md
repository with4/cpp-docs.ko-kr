---
title: "POINT 구조체 | Microsoft Docs"
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
  - "POINT"
  - "LPPOINT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LPPOINT 구조체"
  - "POINT 구조체"
ms.assetid: 965736d8-4e53-41b6-9b8b-6961992dd21f
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# POINT 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**POINT** 구조는  x*\-* 및 점의 y 좌표를 정의합니다.  
  
## 구문  
  
```  
  
      typedef struct tagPOINT {  
   LONG x;  
   LONG y;  
} POINT;  
```  
  
#### 매개 변수  
 *x*  
 점의 x 좌표를 지정합니다.  
  
 *y*  
 점의 y 좌표를 지정합니다.  
  
## 예제  
 [!code-cpp[NVC_MFC_Utilities#37](../../mfc/codesnippet/CPP/point-structure1_1.cpp)]  
  
## 요구 사항  
 **헤더:** windef.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPoint Class](../../atl-mfc-shared/reference/cpoint-class.md)