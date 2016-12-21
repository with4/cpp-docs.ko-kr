---
title: "CListView Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CListView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListView class"
  - "뷰, and common controls"
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CListView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

간단 하 게 사용 및 목록 컨트롤의  [CListCtrl](../../mfc/reference/clistctrl-class.md), MFC의 문서 보기 아키텍처 목록 컨트롤 기능을 캡슐화 하는 클래스입니다.  
  
## 구문  
  
```  
class CListView : public CCtrlView  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CListView::CListView](../Topic/CListView::CListView.md)|`CListView` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CListView::GetListCtrl](../Topic/CListView::GetListCtrl.md)|목록 보기에 연결 컨트롤을 반환 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CListView::RemoveImageList](../Topic/CListView::RemoveImageList.md)|지정 된 이미지 목록 보기 목록에서 제거합니다.|  
  
## 설명  
 이 아키텍처에 대 한 자세한 내용은 개요를 참조 하십시오의  [CView](../../mfc/reference/cview-class.md) 클래스 및 여기에 언급 된 상호 참조 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CListView`  
  
## 요구 사항  
 **헤더:**  afxcview.h  
  
## 참고 항목  
 [Rowlist에서는 MFC 샘플](../../top/visual-cpp-samples.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)