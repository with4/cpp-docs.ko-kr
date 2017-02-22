---
title: "CTreeView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTreeView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeView class"
  - "CTreeView class, 공용 컨트롤"
  - "directory lists"
  - "file lists [C++]"
  - "tree view controls"
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CTreeView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

트리 컨트롤의 사용을 단순화  [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), MFC의 문서 보기 아키텍처와 트리 컨트롤 기능을 캡슐화 하는 클래스입니다.  
  
## 구문  
  
```  
class CTreeView : public CCtrlView  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CTreeView::CTreeView](../Topic/CTreeView::CTreeView.md)|`CTreeView` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CTreeView::GetTreeCtrl](../Topic/CTreeView::GetTreeCtrl.md)|트리 뷰와 연결 된 컨트롤을 반환 합니다.|  
  
## 설명  
 이 아키텍처에 대 한 자세한 내용은 개요를 참조 하십시오의  [CView](../../mfc/reference/cview-class.md) 클래스 및 여기에 언급 된 상호 참조 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CTreeView`  
  
## 요구 사항  
 **헤더:**  afxcview.h  
  
## 참고 항목  
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [CTreeCtrl Class](../../mfc/reference/ctreectrl-class.md)