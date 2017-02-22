---
title: "CHtmlEditView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHtmlEditView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditView class"
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CHtmlEditView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC의 문서\/뷰 아키텍처의 컨텍스트 내에서 WebBrowser 편집 플랫폼의 기능을 제공합니다.  
  
## 구문  
  
```  
  
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase< CHtmlEditView >  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CHtmlEditView::CHtmlEditView](../Topic/CHtmlEditView::CHtmlEditView.md)|`CHtmlEditView` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CHtmlEditView::Create](../Topic/CHtmlEditView::Create.md)|새 창 개체를 만듭니다.|  
|[CHtmlEditView::GetDHtmlDocument](../Topic/CHtmlEditView::GetDHtmlDocument.md)|반환 된  **IHTMLDocument2** 인터페이스는 현재 문서에서.|  
|[CHtmlEditView::GetStartDocument](../Topic/CHtmlEditView::GetStartDocument.md)|이 보기의 기본 문서 이름을 검색합니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CHtmlView](../../mfc/reference/chtmlview-class.md)  
  
 `CHtmlEditView`  
  
## 요구 사항  
 **헤더:** afxhtml.h  
  
## 참고 항목  
 [HTMLEdit 샘플](../../top/visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)