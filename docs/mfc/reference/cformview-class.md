---
title: "CFormView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFormView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFormView class"
  - "form views"
  - "뷰, containing controls"
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CFormView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

폼 뷰에 사용되는 기본 클래스입니다.  
  
## 구문  
  
```  
class CFormView : public CScrollView  
```  
  
## 멤버  
  
### Protected 생성자  
  
|이름|설명|  
|--------|--------|  
|[CFormView::CFormView](../Topic/CFormView::CFormView.md)|`CFormView` 개체를 생성합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CFormView::IsInitDlgCompleted](../Topic/CFormView::IsInitDlgCompleted.md)|초기화하는 동안 동기화에 사용됩니다.|  
  
## 설명  
 폼 뷰는 기본적으로 컨트롤을 포함하는 뷰입니다.  이러한 컨트롤은 대화 상자 템플릿 리소스에 따라 배치됩니다.  응용 프로그램에서 폼을 사용하려면 `CFormView`를 사용합니다.  이러한 뷰는 필요에 따라 [CScrollView](../../mfc/reference/cscrollview-class.md) 기능을 사용하여 스크롤을 지원합니다.  
  
 [폼 기반 응용 프로그램을 만드는](../../mfc/reference/creating-a-forms-based-mfc-application.md) 경우 해당 뷰 클래스의 기반을 `CFormView`로 설정하여 폼 기반 응용 프로그램을 만들 수 있습니다.  
  
 새 [폼 항목](../../mfc/form-views-mfc.md)을 문서 뷰 기반 응용 프로그램에 삽입할 수도 있습니다.  응용 프로그램이 초기에 폼을 지원하지 않은 경우에도 새 폼을 삽입하면 Visual C\+\+에서 이 지원 기능을 추가합니다.  
  
 폼 기반 응용 프로그램을 만들 때는 MFC 응용 프로그램 마법사 및 클래스 추가 명령을 사용하는 것이 좋습니다.  이러한 방법을 사용하지 않고 폼 기반 응용 프로그램을 만들려면 [폼 기반 응용 프로그램 만들기](../../mfc/reference/creating-a-forms-based-mfc-application.md)를 참조하세요.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 `CFormView`  
  
## 요구 사항  
 **헤더:** afxext.h  
  
## 참고 항목  
 [MFC 샘플 SNAPVW](../../top/visual-cpp-samples.md)   
 [MFC 샘플 VIEWEX](../../top/visual-cpp-samples.md)   
 [CScrollView Class](../../mfc/reference/cscrollview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [CScrollView Class](../../mfc/reference/cscrollview-class.md)   
 [CView::OnUpdate](../Topic/CView::OnUpdate.md)   
 [CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md)   
 [CView::OnPrint](../Topic/CView::OnPrint.md)   
 [CWnd::UpdateData](../Topic/CWnd::UpdateData.md)   
 [CScrollView::ResizeParentToFit](../Topic/CScrollView::ResizeParentToFit.md)