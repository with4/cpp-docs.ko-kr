---
title: "MINMAXINFO 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MINMAXINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MINMAXINFO 구조체"
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# MINMAXINFO 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `MINMAXINFO` structure contains information about a window's maximized size and position and its minimum and maximum tracking size.  
  
## 구문  
  
```  
  
      typedef struct tagMINMAXINFO {  
   POINT ptReserved;  
   POINT ptMaxSize;  
   POINT ptMaxPosition;  
   POINT ptMinTrackSize;  
   POINT ptMaxTrackSize;  
} MINMAXINFO;  
```  
  
#### 매개 변수  
 *ptReserved*  
 내부용으로 예약됩니다.  
  
 *ptMaxSize*  
 Specifies the maximized width \(point.x\) and the maximized height \(point.y\) of the window.  
  
 `ptMaxPosition`  
 Specifies the position of the left side of the maximized window \(point.x\) and the position of the top of the maximized window \(point.y\).  
  
 *ptMinTrackSize*  
 Specifies the minimum tracking width \(point.x\) and the minimum tracking height \(point.y\) of the window.  
  
 *ptMaxTrackSize*  
 Specifies the maximum tracking width \(point.x\) and the maximum tracking height \(point.y\) of the window.  
  
## 요구 사항  
 **Header:** winuser.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../Topic/CWnd::OnGetMinMaxInfo.md)