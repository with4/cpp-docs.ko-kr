---
title: "CMFCRibbonContextCaption Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonContextCaption"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonContextCaption class"
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMFCRibbonContextCaption Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

리본 범주 맨 위 또는 컨텍스트 범주에 나타나는 색 지정된 캡션을 구현합니다.  
  
## 구문  
  
```  
class CMFCRibbonContextCaption : public CMFCRibbonButton  
```  
  
## 멤버  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|`CMFCRibbonContextCaption::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|[CMFCRibbonContextCaption::GetColor](../Topic/CMFCRibbonContextCaption::GetColor.md)|캡션 색을 반환합니다.|  
|[CMFCRibbonContextCaption::GetRightTabX](../Topic/CMFCRibbonContextCaption::GetRightTabX.md)||  
|`CMFCRibbonContextCaption::GetThisClass`|프레임워크에서 이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 가져오는 데 사용합니다.|  
  
## 설명  
 이 클래스는 직접 인스턴스화할 수 없습니다.  [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md) 클래스는 이 클래스를 내부적으로 사용하여 리본 범주에 색을 추가합니다.  
  
 리본 범주에 대한 색을 설정하려면 [CMFCRibbonCategory::SetTabColor](../Topic/CMFCRibbonCategory::SetTabColor.md)를 호출합니다.  컨텍스트 범주에 대한 색을 설정하려면 [CMFCRibbonBar::AddContextCategory](../Topic/CMFCRibbonBar::AddContextCategory.md)를 호출합니다.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)  
  
## 요구 사항  
 **헤더:** afxRibbonBar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonCategory Class](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)