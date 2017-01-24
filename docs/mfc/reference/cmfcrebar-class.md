---
title: "CMFCReBar Class | Microsoft Docs"
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
  - "CMFCReBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCReBar class"
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCReBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

A `CMFCReBar` 개체 레이아웃, 지 속성 및 rebar 컨트롤에 대 한 상태 정보를 제공 하는 컨트롤 모음입니다.  
  
## 구문  
  
```  
class CMFCReBar : public CPane  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCReBar::AddBar](../Topic/CMFCReBar::AddBar.md)|밴드를 rebar를 추가합니다.|  
|[CMFCReBar::CalcFixedLayout](../Topic/CMFCReBar::CalcFixedLayout.md)|\(재정의 [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CMFCReBar::CanFloat](../Topic/CMFCReBar::CanFloat.md)|\(재정의 [CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md).\)|  
|[CMFCReBar::Create](../Topic/CMFCReBar::Create.md)|Rebar 컨트롤을 만들고이에 연결 된 `CMFCReBar` 개체입니다.|  
|[CMFCReBar::EnableDocking](../Topic/CMFCReBar::EnableDocking.md)|\(재정의 [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md).\)|  
|[CMFCReBar::GetReBarBandInfoSize](../Topic/CMFCReBar::GetReBarBandInfoSize.md)||  
|[CMFCReBar::GetReBarCtrl](../Topic/CMFCReBar::GetReBarCtrl.md)|직접 액세스 하는 기본 제공  [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) 공용 컨트롤.|  
|[CMFCReBar::OnShowControlBarMenu](../Topic/CMFCReBar::OnShowControlBarMenu.md)|\(재정의 [CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md).\)|  
|[CMFCReBar::OnToolHitTest](../Topic/CMFCReBar::OnToolHitTest.md)|\(재정의 [CWnd::OnToolHitTest](../Topic/CWnd::OnToolHitTest.md).\)|  
|[CMFCReBar::OnUpdateCmdUI](../Topic/CMFCReBar::OnUpdateCmdUI.md)|\(재정의 [CBasePane::OnUpdateCmdUI](http://msdn.microsoft.com/ko-kr/e139f06a-9793-4ee2-bc3d-517389368c77).\)|  
|[CMFCReBar::SetPaneAlignment](../Topic/CMFCReBar::SetPaneAlignment.md)|\(재정의 [CBasePane::SetPaneAlignment](../Topic/CBasePane::SetPaneAlignment.md).\)|  
  
## 설명  
 A `CMFCReBar` 다양 한 자식 창 개체를 포함할 수 있습니다.  도구 모음, 입력란, 목록 상자를 포함 합니다.  Rebar를 프로그래밍 방식으로 조정할 수 있습니다 또는 사용자가 수동으로 rebar의 그리퍼 막대를 드래그 하 여 조정할 수 있습니다.  Rebar 개체의 배경에 원하는 비트맵을 설정할 수도 있습니다.  
  
 Rebar 개체는 마찬가지로 도구 모음 개체를 작동합니다.  Rebar 컨트롤에서 밴드를 하나 이상 포함 될 수 있습니다 및 각 밴드는 그리퍼 막대, 비트맵, 텍스트 레이블 및 자식 창을 포함할 수 있습니다.  
  
## 예제  
 다음 예제에서는 다양 한 방법에 있는 `CMFCReBar` 클래스입니다.  이 예제에서는 rebar 컨트롤 밴드를 추가 하는 방법을 보여 줍니다.  밴드 함수는 내부 도구 모음입니다.  이 코드 조각에 속하지는  [검정 Rebar](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/CPP/cmfcrebar-class_1.h)]  
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/CPP/cmfcrebar-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)  
  
## 요구 사항  
 **헤더:** afxRebar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CReBarCtrl Class](../../mfc/reference/crebarctrl-class.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)