---
title: "CMFCDropDownToolBar Class | Microsoft Docs"
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
  - "CMFCDropDownToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDropDownToolBar class"
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
caps.latest.revision: 37
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDropDownToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

최상위 도구 모음 단추 보유 때 나타나는 도구 모음입니다.  
  
## 구문  
  
```  
class CMFCDropDownToolBar : public CMFCToolBar  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCDropDownToolBar::AllowShowOnPaneMenu](../Topic/CMFCDropDownToolBar::AllowShowOnPaneMenu.md)|\(재정의 `CPane::AllowShowOnPaneMenu`.\)|  
|[CMFCDropDownToolBar::LoadBitmap](../Topic/CMFCDropDownToolBar::LoadBitmap.md)|\(재정의 [CMFCToolBar::LoadBitmap](../Topic/CMFCToolBar::LoadBitmap.md).\)|  
|[CMFCDropDownToolBar::LoadToolBar](../Topic/CMFCDropDownToolBar::LoadToolBar.md)|\(재정의 [CMFCToolBar::LoadToolBar](../Topic/CMFCToolBar::LoadToolBar.md).\)|  
|[CMFCDropDownToolBar::OnLButtonUp](../Topic/CMFCDropDownToolBar::OnLButtonUp.md)||  
|[CMFCDropDownToolBar::OnMouseMove](../Topic/CMFCDropDownToolBar::OnMouseMove.md)||  
|[CMFCDropDownToolBar::OnSendCommand](../Topic/CMFCDropDownToolBar::OnSendCommand.md)|\(재정의 `CMFCToolBar::OnSendCommand`.\)|  
|[CMFCDropDownToolBar::OnUpdateCmdUI](../Topic/CMFCDropDownToolBar::OnUpdateCmdUI.md)|\(재정의 [CMFCToolBar::OnUpdateCmdUI](http://msdn.microsoft.com/ko-kr/571a38ab-2a56-4968-9796-273516126f80).\)|  
  
### 설명  
 A `CMFCDropDownToolBar` 개체 모양을 도구 모음을 팝업 메뉴의 동작을 결합 합니다.  언제 고 보관 드롭다운 도구 모음 단추 \(참조 [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)\), 표시 되는 드롭다운 도구 모음 단추 도구 모음에서 드롭다운을 스크롤 하 고 마우스 단추를 놓으면 선택할 수 있습니다.  사용자가 단추 도구 모음에서 드롭다운 선택 후 최상위 도구 모음에서 현재 단추 단추 표시 됩니다.  
  
 드롭다운 도구 모음 사용자 지정 하거나 도킹, 수 및 분리 된 상태가 없습니다.  
  
 다음 그림과 `CMFCDropDownToolBar` 개체:  
  
 ![CMFCDropDownToolbar의 예제](../../mfc/reference/media/cmfcdropdown.png "CMFCDropDown")  
  
 만들는 `CMFCDropDownToolBar` 는 일반 도구 모음을 만들는 개체 \(참조 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)\).  
  
 부모 도구 모음에 드롭다운 도구 모음을 삽입 하려면:  
  
 1.  부모 리소스 도구 모음 단추에 대 한 더미 리소스 ID를 예약 합니다.  
  
 2.  만들기는 `CMFCDropDownToolBarButton` 드롭다운 도구 모음을 포함 하는 개체 \(자세한 내용은 [CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../Topic/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton.md)\).  
  
 3.  더미 단추와 바꾸기의 `CMFCDropDownToolBarButton` 개체를 사용 하 여 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md).  
  
 도구 모음 단추에 대 한 자세한 내용은 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md).  드롭다운 도구 모음에 대 한 예제에서는 VisualStudioDemo 예제 프로젝트를 참조 하십시오.  
  
## 예제  
 다음 예제에서는 `Create` 메서드에서 `CMFCDropDownToolBar` 클래스입니다.  이 코드 조각에 속해 있는  [Visual Studio 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/codesnippet/CPP/cmfcdropdowntoolbar-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/codesnippet/CPP/cmfcdropdowntoolbar-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)  
  
## 요구 사항  
 **헤더:** afxdropdowntoolbar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::Create](../Topic/CMFCToolBar::Create.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)   
 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)