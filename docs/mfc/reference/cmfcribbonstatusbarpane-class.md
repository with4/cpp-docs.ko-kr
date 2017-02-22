---
title: "CMFCRibbonStatusBarPane Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonStatusBarPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonStatusBarPane class"
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
caps.latest.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 33
---
# CMFCRibbonStatusBarPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonStatusBarPane` 클래스를 구현 하는 리본 요소 리본 상태 표시줄에 추가할 수 있습니다.  
  
## 구문  
  
```  
class CMFCRibbonStatusBarPane : public CMFCRibbonButton  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](../Topic/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane.md)|생성 및 초기화는 `CMFCRibbonStatusBarPane` 개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](../Topic/CMFCRibbonStatusBarPane::GetAlmostLargeText.md)|잘라내지 않고 창에 표시 되는 긴 텍스트 문자열을 정의 하는 문자열을 반환 합니다.|  
|[CMFCRibbonStatusBarPane::GetTextAlign](../Topic/CMFCRibbonStatusBarPane::GetTextAlign.md)|텍스트 맞춤의 현재 설정을 반환합니다.|  
|[CMFCRibbonStatusBarPane::IsAnimation](../Topic/CMFCRibbonStatusBarPane::IsAnimation.md)|애니메이션 진행 중인지 여부를 결정 합니다.|  
|[CMFCRibbonStatusBarPane::IsExtended](../Topic/CMFCRibbonStatusBarPane::IsExtended.md)|창에서 리본 상태 표시줄의 확장된 영역에 있는지 여부를 결정 합니다.|  
|[CMFCRibbonStatusBarPane::OnDrawBorder](../Topic/CMFCRibbonStatusBarPane::OnDrawBorder.md)|\(재정의 [CMFCRibbonButton::OnDrawBorder](../Topic/CMFCRibbonButton::OnDrawBorder.md).\)|  
|[CMFCRibbonStatusBarPane::OnFillBackground](../Topic/CMFCRibbonStatusBarPane::OnFillBackground.md)|\(재정의 [CMFCRibbonButton::OnFillBackground](../Topic/CMFCRibbonButton::OnFillBackground.md).\)|  
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](../Topic/CMFCRibbonStatusBarPane::SetAlmostLargeText.md)|잘라내지 않고 창에 표시 되는 긴 텍스트 문자열을 정의 합니다.|  
|[CMFCRibbonStatusBarPane::SetAnimationList](../Topic/CMFCRibbonStatusBarPane::SetAnimationList.md)|애니메이션에 사용할 수 있는 이미지 목록 창에을 할당 합니다.|  
|[CMFCRibbonStatusBarPane::SetTextAlign](../Topic/CMFCRibbonStatusBarPane::SetTextAlign.md)|텍스트 맞춤을 설정합니다.|  
|[CMFCRibbonStatusBarPane::StartAnimation](../Topic/CMFCRibbonStatusBarPane::StartAnimation.md)|창에 할당 된 애니메이션을 시작 합니다.|  
|[CMFCRibbonStatusBarPane::StopAnimation](../Topic/CMFCRibbonStatusBarPane::StopAnimation.md)|창에 할당 된 애니메이션을 중지 합니다.  .|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonStatusBarPane::OnFinishAnimation](../Topic/CMFCRibbonStatusBarPane::OnFinishAnimation.md)|창에 할당 된 애니메이션을 중지 하면 프레임 워크에서 호출 됩니다.|  
  
## 예제  
 다음 예제에서는 다양 한 메서드를 사용 하는 방법의 `CMFCRibbonStatusBarPane` 클래스입니다.  예제 작성 하는 방법을 보여 줍니다.는 `CMFCRibbonStatusBarPane` 개체, 상태 표시줄 창 레이블의 텍스트 맞춤 설정을 잘라내지 않고 상태 표시줄 창에 표시 될, 애니메이션을 사용할 수 있으며 애니메이션을 시작 하는 이미지 목록을 상태 표시줄 창에 연결 하는 가장 긴 텍스트를 정의 합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/CPP/cmfcribbonstatusbarpane-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)  
  
## 요구 사항  
 **헤더:** afxribbonstatusbarpane.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonStatusBar Class](../../mfc/reference/cmfcribbonstatusbar-class.md)