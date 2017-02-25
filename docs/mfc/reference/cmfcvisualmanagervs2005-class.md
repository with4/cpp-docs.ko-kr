---
title: "CMFCVisualManagerVS2005 Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCVisualManagerVS2005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManagerVS2005 class"
ms.assetid: ea39b9ae-327e-4a51-bce7-dc84c78f005b
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCVisualManagerVS2005 Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCVisualManagerVS2005`응용 프로그램이 Microsoft Visual Studio 2005 모양을 제공합니다.  
  
## 구문  
  
```  
class CMFCVisualManagerVS2005 : public CMFCVisualManagerOffice2003  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCVisualManagerVS2005::GetDockingTabsBordersSize](../Topic/CMFCVisualManagerVS2005::GetDockingTabsBordersSize.md)|도킹 하며 탭 창을 그릴 때 프레임 워크가이 메서드를 호출 합니다.  \(재정의 [CMFCVisualManager::GetDockingTabsBordersSize](../Topic/CMFCVisualManager::GetDockingTabsBordersSize.md).\)|  
|[CMFCVisualManagerVS2005::GetMDITabsBordersSize](../Topic/CMFCVisualManagerVS2005::GetMDITabsBordersSize.md)|프레임 워크는이 창을 그립니다 전에 MDITabs 창 테두리 크기를 결정 하려면이 메서드를 호출 합니다.  \(재정의 [CMFCVisualManager::GetMDITabsBordersSize](../Topic/CMFCVisualManager::GetMDITabsBordersSize.md).\)|  
|[CMFCVisualManagerVS2005::GetPropertyGridGroupColor](../Topic/CMFCVisualManagerVS2005::GetPropertyGridGroupColor.md)|\(재정의 [CMFCVisualManagerOffice2003::GetPropertyGridGroupColor](../Topic/CMFCVisualManagerOffice2003::GetPropertyGridGroupColor.md).\)|  
|[CMFCVisualManagerVS2005::GetTabFrameColors](../Topic/CMFCVisualManagerVS2005::GetTabFrameColors.md)|\(재정의 [CMFCVisualManagerOffice2003::GetTabFrameColors](../Topic/CMFCVisualManagerOffice2003::GetTabFrameColors.md).\)|  
|[CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons](../Topic/CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons.md)|자동 숨기기 단추 현재 비주얼 관리자에서 겹치는 지 여부를 반환 합니다.  \(재정의 [CMFCVisualManager::HasOverlappedAutoHideButtons](../Topic/CMFCVisualManager::HasOverlappedAutoHideButtons.md).\)|  
|[CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder](../Topic/CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder.md)|\(재정의 [CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder.md).\)|  
|[CMFCVisualManagerVS2005::OnDrawCaptionButton](../Topic/CMFCVisualManagerVS2005::OnDrawCaptionButton.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawCaptionButton`.\)|  
|[CMFCVisualManagerVS2005::OnDrawPaneCaption](../Topic/CMFCVisualManagerVS2005::OnDrawPaneCaption.md)|\(재정의 [CMFCVisualManagerOffice2003::OnDrawPaneCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawPaneCaption.md).\)|  
|[CMFCVisualManagerVS2005::OnDrawSeparator](../Topic/CMFCVisualManagerVS2005::OnDrawSeparator.md)|\(재정의 [CMFCVisualManagerOffice2003::OnDrawSeparator](../Topic/CMFCVisualManagerOffice2003::OnDrawSeparator.md).\)|  
|[CMFCVisualManagerVS2005::OnDrawTab](../Topic/CMFCVisualManagerVS2005::OnDrawTab.md)|\(재정의 [CMFCVisualManagerOffice2003::OnDrawTab](../Topic/CMFCVisualManagerOffice2003::OnDrawTab.md).\)|  
|[CMFCVisualManagerVS2005::OnDrawToolBoxFrame](../Topic/CMFCVisualManagerVS2005::OnDrawToolBoxFrame.md)|\(재정의 [CMFCVisualManager::OnDrawToolBoxFrame](../Topic/CMFCVisualManager::OnDrawToolBoxFrame.md).\)|  
|[CMFCVisualManagerVS2005::OnEraseTabsArea](../Topic/CMFCVisualManagerVS2005::OnEraseTabsArea.md)|\(재정의 [CMFCVisualManagerOffice2003::OnEraseTabsArea](../Topic/CMFCVisualManagerOffice2003::OnEraseTabsArea.md).\)|  
|[CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground](../Topic/CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground.md)|\(재정의 [CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground](../Topic/CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground.md).\)|  
|[CMFCVisualManagerVS2005::OnFillHighlightedArea](../Topic/CMFCVisualManagerVS2005::OnFillHighlightedArea.md)|\(재정의 [CMFCVisualManagerOffice2003::OnFillHighlightedArea](../Topic/CMFCVisualManagerOffice2003::OnFillHighlightedArea.md).\)|  
|[CMFCVisualManagerVS2005::OnFillMiniFrameCaption](../Topic/CMFCVisualManagerVS2005::OnFillMiniFrameCaption.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption`.\)|  
|[CMFCVisualManagerVS2005::OnUpdateSystemColors](../Topic/CMFCVisualManagerVS2005::OnUpdateSystemColors.md)|\(재정의 [CMFCVisualManagerOffice2003::OnUpdateSystemColors](../Topic/CMFCVisualManagerOffice2003::OnUpdateSystemColors.md).\)|  
  
## 설명  
 CMFCVisualManagerVS2005 클래스를 사용 하 여 유사의 응용 프로그램의 시각적 모양을 변경 하는 [!INCLUDE[vsprvsext](../../mfc/reference/includes/vsprvsext_md.md)].  
  
 이 클래스의 멤버는이 클래스의 상위 항목에서 파생 된 가상 함수를 모두 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md).  
  
## 예제  
 다음 예제에서는 비주얼 관리자 VS 2005를 사용 하는 방법을 보여 줍니다.  이 코드 조각에 속하지는  [바탕 화면 경고 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#9](../../mfc/reference/codesnippet/CPP/cmfcvisualmanagervs2005-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)  
  
 [CMFCVisualManagerVS2005](../../mfc/reference/cmfcvisualmanagervs2005-class.md)  
  
## 요구 사항  
 **헤더:** afxvisualmanagervs2005.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerOfficeXP Class](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)   
 [CMFCVisualManagerWindows Class](../../mfc/reference/cmfcvisualmanagerwindows-class.md)   
 [CMFCVisualManagerOffice2003 Class](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)   
 [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)