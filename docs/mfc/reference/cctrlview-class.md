---
title: "CCtrlView Class | Microsoft Docs"
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
  - "CCtrlView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCtrlView class"
  - "컨트롤[MFC], common"
  - "뷰, and common controls"
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCtrlView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문서 뷰 아키텍처 Windows NT 및 Windows 98에서 3.51 이상 버전에서는 지원 되는 공용 컨트롤에 적응 합니다.  
  
## 구문  
  
```  
class CCtrlView : public CView  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CCtrlView::CCtrlView](../Topic/CCtrlView::CCtrlView.md)|`CCtrlView` 개체를 생성합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CCtrlView::OnDraw](../Topic/CCtrlView::OnDraw.md)|지정 된 디바이스 컨텍스트를 사용 하 여 그리려면 프레임 워크에서 호출 됩니다.|  
|[CCtrlView::PreCreateWindow](../Topic/CCtrlView::PreCreateWindow.md)|Windows 창에이 연결을 만들기 전에 호출 `CCtrlView` 개체입니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CCtrlView::m\_dwDefaultStyle](../Topic/CCtrlView::m_dwDefaultStyle.md)|뷰 클래스의 기본 스타일을 포함 합니다.|  
|[CCtrlView::m\_strClass](../Topic/CCtrlView::m_strClass.md)|Windows 클래스 이름 뷰 클래스를 포함 합니다.|  
  
## 설명  
 클래스 `CCtrlView` 와 그 파생물  [CEditView](../../mfc/reference/ceditview-class.md),  [CListView](../../mfc/reference/clistview-class.md),  [CTreeView](../../mfc/reference/ctreeview-class.md), 및  [CRichEditView](../../mfc/reference/cricheditview-class.md), Windows NT 및 Windows 95\/98에서 3.51 이상 버전을 지 원하는 일반적인 컨트롤 새 문서 보기 아키텍처를 적용 합니다.  문서 뷰 아키텍처에 대 한 자세한 내용은  [문서\/뷰 아키텍처](../../mfc/document-view-architecture.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CCtrlView`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CView Class](../../mfc/reference/cview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CTreeView Class](../../mfc/reference/ctreeview-class.md)   
 [CListView Class](../../mfc/reference/clistview-class.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)