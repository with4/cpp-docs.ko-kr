---
title: "CTabView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTabView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabView class"
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
caps.latest.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 34
---
# CTabView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CTabView` 클래스 탭 컨트롤 클래스의 사용을 단순화 \([CMFCTabCtrl](../../mfc/reference/ctabview-class.md)\)에서 MFC의 문서\/뷰 아키텍처를 사용 하는 응용 프로그램.  
  
## 구문  
  
```  
class CTabbedView : public CView  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CTabView::AddView](../Topic/CTabView::AddView.md)|새 보기를 탭 컨트롤에 추가합니다.|  
|[CTabView::FindTab](../Topic/CTabView::FindTab.md)|탭 컨트롤에 지정 된 보기의 인덱스를 반환합니다.|  
|[CTabView::GetActiveView](../Topic/CTabView::GetActiveView.md)|현재 활성 보기에 대 한 포인터를 반환|  
|[CTabView::GetTabControl](../Topic/CTabView::GetTabControl.md)|뷰와 연결 된 탭 컨트롤에 대 한 참조를 반환 합니다.|  
|[CTabView::RemoveView](../Topic/CTabView::RemoveView.md)|보기 탭에서 컨트롤을 제거합니다.|  
|[CTabView::SetActiveView](../Topic/CTabView::SetActiveView.md)|보기를 활성화 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CTabView::IsScrollBar](../Topic/CTabView::IsScrollBar.md)|프레임 워크에서 탭 보기 공유 가로 스크롤 막대가 있는지 여부를 확인 하는 탭 뷰를 만들 때 호출 됩니다.|  
|[CTabView::OnActivateView](../Topic/CTabView::OnActivateView.md)|보기 탭을 활성 또는 비활성 될 때 프레임 워크에 의해 호출 됩니다.|  
  
## 설명  
 이 클래스 보기 탭된의 문서\/뷰 응용 프로그램에 넣을 수 있습니다.  `CTabView`되는 `CView`\-포함 된 포함 하는 클래스를 파생 `CMFCTabCtrl` 개체입니다.  `CTabView`지 원하는 데 필요한 메시지를 모두 처리 하는 `CMFCTabCtrl` 개체입니다.  단순히 클래스에서 파생 `CTabView` 응용 프로그램에 연결 하 고 추가 `CView`\-를 사용 하 여 파생 클래스의 `AddView` 메서드.  탭 컨트롤 보기 탭으로 표시 됩니다.  
  
 예를 들어, 다른 방식으로 나타낼 수 있는 문서 해야: 스프레드시트, 차트, 편집 가능한 폼 및 등.  개별 뷰의 데이터를 필요에 따라 드로잉을 만들면 삽입에 `CTabView`\-파생 개체 및 해당 탭 추가 코딩 없이 해야 합니다.  
  
 [TabbedView 샘플: MFC 탭 보기 응용 프로그램](../../top/visual-cpp-samples.md) 의 사용법을 보여 줍니다. `CTabView`.  
  
## 예제  
 다음 예제는 `CTabView` TabbedView 샘플에 사용 됩니다.  
  
 [!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/CPP/ctabview-class_1.h)]  
  
## 요구 사항  
 **헤더:** afxTabView.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CTabView Class](../../mfc/reference/ctabview-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)