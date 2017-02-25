---
title: "CMFCRibbonLinkCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonLinkCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonLinkCtrl class"
ms.assetid: 77ae1941-e0ab-4a9d-911e-1752d34c079b
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMFCRibbonLinkCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

리본에 배치되는 하이퍼링크를 구현합니다.  하이퍼링크를 클릭하면 웹 페이지가 열립니다.  
  
## 구문  
  
```  
class CMFCRibbonLinkCtrl : public CMFCRibbonButton  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl](../Topic/CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl.md)|`CMFCRibbonLinkCtrl` 개체를 생성하고 초기화합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonLinkCtrl::CopyFrom](../Topic/CMFCRibbonLinkCtrl::CopyFrom.md)|\(`CMFCRibbonButton::CopyFrom`을 재정의합니다.\)|  
|[CMFCRibbonLinkCtrl::GetCompactSize](../Topic/CMFCRibbonLinkCtrl::GetCompactSize.md)|\([CMFCRibbonButton::GetCompactSize](../Topic/CMFCRibbonButton::GetCompactSize.md)를 재정의합니다.\)|  
|[CMFCRibbonLinkCtrl::GetLink](../Topic/CMFCRibbonLinkCtrl::GetLink.md)|하이퍼링크의 값을 반환합니다.|  
|[CMFCRibbonLinkCtrl::GetRegularSize](../Topic/CMFCRibbonLinkCtrl::GetRegularSize.md)|\([CMFCRibbonButton::GetRegularSize](../Topic/CMFCRibbonButton::GetRegularSize.md)를 재정의합니다.\)|  
|[CMFCRibbonLinkCtrl::GetToolTipText](../Topic/CMFCRibbonLinkCtrl::GetToolTipText.md)|\([CMFCRibbonButton::GetToolTipText](../Topic/CMFCRibbonButton::GetToolTipText.md)를 재정의합니다.\)|  
|[CMFCRibbonLinkCtrl::IsDrawTooltipImage](../Topic/CMFCRibbonLinkCtrl::IsDrawTooltipImage.md)|\(`CMFCRibbonButton::IsDrawTooltipImage`를 재정의합니다.\)|  
|[CMFCRibbonLinkCtrl::OnDraw](../Topic/CMFCRibbonLinkCtrl::OnDraw.md)|\([CMFCRibbonButton::OnDraw](../Topic/CMFCRibbonButton::OnDraw.md)를 재정의합니다.\)|  
|[CMFCRibbonLinkCtrl::OnDrawMenuImage](../Topic/CMFCRibbonLinkCtrl::OnDrawMenuImage.md)|\([CMFCRibbonBaseElement::OnDrawMenuImage](../Topic/CMFCRibbonBaseElement::OnDrawMenuImage.md)를 재정의합니다.\)|  
|[CMFCRibbonLinkCtrl::OnMouseMove](../Topic/CMFCRibbonLinkCtrl::OnMouseMove.md)|\(`CMFCRibbonButton::OnMouseMove`를 재정의합니다.\)|  
|[CMFCRibbonLinkCtrl::OnSetIcon](../Topic/CMFCRibbonLinkCtrl::OnSetIcon.md)||  
|[CMFCRibbonLinkCtrl::OpenLink](../Topic/CMFCRibbonLinkCtrl::OpenLink.md)|하이퍼링크에 지정된 웹 페이지를 엽니다.|  
|[CMFCRibbonLinkCtrl::SetLink](../Topic/CMFCRibbonLinkCtrl::SetLink.md)|하이퍼링크의 값을 설정합니다.|  
  
## 설명  
 하이퍼링크를 만든 후에는 [CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md)를 호출하여 패널에 추가합니다.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md) [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md) [CMFCRibbonLinkCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md)  
  
## 요구 사항  
 **헤더:** afxRibbonLinkCtrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)