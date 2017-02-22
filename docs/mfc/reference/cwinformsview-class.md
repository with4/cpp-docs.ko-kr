---
title: "CWinFormsView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinFormsView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinFormsView class"
  - "MFC[C++], Windows Forms 지원"
  - "Windows Forms[C++], MFC 지원"
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CWinFormsView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows Forms 컨트롤을 MFC 뷰로 호스팅에 대 한 제네릭 기능을 제공 합니다.  
  
## 구문  
  
```  
class CWinFormsView : public CView;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CWinFormsView::CWinFormsView](../Topic/CWinFormsView::CWinFormsView.md)|`CWinFormsView` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CWinFormsView::GetControl](../Topic/CWinFormsView::GetControl.md)|Windows Forms 컨트롤에 대 한 포인터를 검색합니다.|  
  
### Public 연산자  
  
|Name||  
|----------|-|  
|[CWinFormsView::operator Control^](../Topic/CWinFormsView::operator%20Control%5E.md)|형식에 Windows Forms 컨트롤에 대 한 포인터로 캐스팅합니다.|  
  
## 설명  
 MFC를 사용 하는 `CWinFormsView` 클래스는 MFC 뷰 내.NET Framework Windows Forms 컨트롤을 호스팅할 수 있습니다.  네이티브 뷰의 자식 컨트롤과 MFC 뷰의 전체 클라이언트 영역을 차지 합니다.  결과 유사는 `CFormView` 보기, Windows Forms 디자이너를 사용 하 여 런타임에 리치 폼 기반 뷰를 만들 수 있도록 합니다.  
  
 Windows Forms을 사용 하 여에 대 한 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
> [!NOTE]
>  MFC Windows Forms 통합의 작동 원리에 동적으로 MFC에 링크 하는 프로젝트 \(AFXDLL 정의 된 프로젝트\).  
  
> [!NOTE]
>  CWinFormsView MFC 분할자 창 지원 하지 않습니다 \([CSplitterWnd Class](../../mfc/reference/csplitterwnd-class.md)\).  현재는 Windows Forms Splitter 컨트롤 \(<xref:System.Windows.Forms.Splitter>\) 지원 됩니다.  
  
## 요구 사항  
 **헤더:** afxwinforms.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWinFormsControl Class](../../mfc/reference/cwinformscontrol-class.md)   
 [CWinFormsDialog Class](../../mfc/reference/cwinformsdialog-class.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)