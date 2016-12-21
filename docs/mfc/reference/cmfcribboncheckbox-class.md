---
title: "CMFCRibbonCheckBox Class | Microsoft Docs"
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
  - "CMFCRibbonCheckBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonCheckBox class"
ms.assetid: 3a6c3891-c8d1-4af0-b954-7b9ab048782a
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonCheckBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonCheckBox` 클래스는 리본 패널, 빠른 실행 도구 모음 또는 팝업 메뉴에 추가할 수 있는 확인란을 구현합니다.  
  
## 구문  
  
```  
class CMFCRibbonCheckBox : public CMFCRibbonButton  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](../Topic/CMFCRibbonCheckBox::CMFCRibbonCheckBox.md)|생성자입니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonCheckBox::GetCompactSize](../Topic/CMFCRibbonCheckBox::GetCompactSize.md)|\([CMFCRibbonButton::GetCompactSize](../Topic/CMFCRibbonButton::GetCompactSize.md)를 재정의합니다.\)|  
|[CMFCRibbonCheckBox::GetIntermediateSize](../Topic/CMFCRibbonCheckBox::GetIntermediateSize.md)|\([CMFCRibbonButton::GetIntermediateSize](../Topic/CMFCRibbonButton::GetIntermediateSize.md)를 재정의합니다.\)|  
|[CMFCRibbonCheckBox::GetRegularSize](../Topic/CMFCRibbonCheckBox::GetRegularSize.md)|\([CMFCRibbonButton::GetRegularSize](../Topic/CMFCRibbonButton::GetRegularSize.md)를 재정의합니다.\)|  
|[CMFCRibbonCheckBox::IsDrawTooltipImage](../Topic/CMFCRibbonCheckBox::IsDrawTooltipImage.md)|\(`CMFCRibbonButton::IsDrawTooltipImage`를 재정의합니다.\)|  
|[CMFCRibbonCheckBox::OnDraw](../Topic/CMFCRibbonCheckBox::OnDraw.md)|\([CMFCRibbonButton::OnDraw](../Topic/CMFCRibbonButton::OnDraw.md)를 재정의합니다.\)|  
|[CMFCRibbonCheckBox::OnDrawMenuImage](../Topic/CMFCRibbonCheckBox::OnDrawMenuImage.md)|\([CMFCRibbonBaseElement::OnDrawMenuImage](../Topic/CMFCRibbonBaseElement::OnDrawMenuImage.md)를 재정의합니다.\)|  
|[CMFCRibbonCheckBox::OnDrawOnList](../Topic/CMFCRibbonCheckBox::OnDrawOnList.md)|\(`CMFCRibbonButton::OnDrawOnList`를 재정의합니다.\)|  
|[CMFCRibbonCheckBox::SetACCData](../Topic/CMFCRibbonCheckBox::SetACCData.md)|\([CMFCRibbonButton::SetACCData](../Topic/CMFCRibbonButton::SetACCData.md)를 재정의합니다.\)|  
  
## 설명  
 응용 프로그램에서 `CMFCRibbonCheckBox`를 사용하려면 코드에 다음 생성자를 추가합니다.  
  
```  
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)  
```  
  
 여기서 `nID`는 확인란 명령 ID이고 `lpszText`는 확인란의 텍스트 레이블입니다.  
  
 [CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md)를 사용하여 리본 패널에 확인란을 추가할 수 있습니다.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)  
  
## 요구 사항  
 **헤더:** afxribboncheckbox.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonPanel Class](../../mfc/reference/cmfcribbonpanel-class.md)