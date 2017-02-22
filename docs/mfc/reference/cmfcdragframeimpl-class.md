---
title: "CMFCDragFrameImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCDragFrameImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDragFrameImpl class"
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMFCDragFrameImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCDragFrameImpl` 클래스는 창 표준 도킹 모드로 사용자를 끌 때 끌어서 사각형을 그립니다.  
  
## 구문  
  
```  
class CMFCDragFrameImpl  
```  
  
## 설명  
 이 클래스의 개체에 포함 된 [CPane Class](../../mfc/reference/cpane-class.md) 개체입니다.  따라서 사용 하 여 각 창에 `CanFloat` 메서드는 사용자를 끌 때 끌어서 사각형 표시.  
  
 끌기 사각형의 두께 사용 하 여 제어할 수 있습니다 [AFX\_GLOBAL\_DATA::m\_nDragFrameThicknessFloat](../Topic/AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat.md) 및 [AFX\_GLOBAL\_DATA::m\_nDragFrameThicknessDock](../Topic/AFX_GLOBAL_DATA::m_nDragFrameThicknessDock.md).  
  
## 상속 계층 구조  
 [CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)  
  
## 요구 사항  
 **헤더:** afxdragframeimpl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)   
 [AFX\_GLOBAL\_DATA::m\_nDragFrameThicknessFloat](../Topic/AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat.md)   
 [AFX\_GLOBAL\_DATA::m\_nDragFrameThicknessDock](../Topic/AFX_GLOBAL_DATA::m_nDragFrameThicknessDock.md)