---
title: "CMFCRibbonLabel Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonLabel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonLabel class"
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CMFCRibbonLabel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

리본 메뉴에 대 한 레이블을 클릭할 텍스트를 구현합니다.  
  
## 구문  
  
```  
class CMFCRibbonLabel : public CMFCRibbonButton  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonLabel::CMFCRibbonLabel](../Topic/CMFCRibbonLabel::CMFCRibbonLabel.md)|생성 및 초기화는 `CMFCRibbonLabel` 개체와 지정 된 텍스트 문자열입니다.|  
|`CMFCRibbonLabel::~CMFCRibbonLabel`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|`CMFCRibbonLabel::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|`CMFCRibbonLabel::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCRibbonLabel::SetACCData](../Topic/CMFCRibbonLabel::SetACCData.md)|현재 리본 label 요소에 대 한 내게 필요한 옵션 데이터를 결정합니다.  \(재정의 [CMFCRibbonButton::SetACCData](../Topic/CMFCRibbonButton::SetACCData.md).\)|  
  
### 설명  
 리본 레이블을 만들면이 패널에 호출 하 여 추가 [CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md).  
  
 리본 레이블 빠른 액세스 도구 모음에 추가할 수 없습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)  
  
## 요구 사항  
 **헤더:** afxRibbonLabel.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)