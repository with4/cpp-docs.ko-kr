---
title: "COleResizeBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleResizeBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleResizeBar class"
  - "control bars, 크기 조정"
  - "in-place items"
  - "in-place items, 크기 조정"
  - "OLE items, 크기 조정"
  - "resizing in-place OLE items"
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleResizeBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 내부 OLE 항목의 크기 조정을 지원함 컨트롤 막대입니다.  
  
## 구문  
  
```  
class COleResizeBar : public CControlBar  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleResizeBar::COleResizeBar](../Topic/COleResizeBar::COleResizeBar.md)|`COleResizeBar` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleResizeBar::Create](../Topic/COleResizeBar::Create.md)|만듭니다 Windows 자식 창을 초기화 및 연결 하는 `COleResizeBar` 개체입니다.|  
  
## 설명  
 `COleResizeBar`개체 표시는  [CRectTracker](../../mfc/reference/crecttracker-class.md) 빗금된 테두리 및 외부 핸들 크기 조정.  
  
 `COleResizeBar`개체는 일반적으로 포함 된 멤버의 프레임 창 개체에서 파생 된  [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) 클래스.  
  
 자세한 내용은  [정품](../../mfc/activation-cpp.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `COleResizeBar`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [SUPERPAD MFC 샘플](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleServerDoc Class](../../mfc/reference/coleserverdoc-class.md)