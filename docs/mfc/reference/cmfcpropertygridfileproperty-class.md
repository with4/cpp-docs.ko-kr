---
title: "CMFCPropertyGridFileProperty Class | Microsoft Docs"
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
  - "CMFCPropertyGridFileProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridFileProperty class"
  - "CMFCPropertyGridFileProperty::OnClickButton method"
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
caps.latest.revision: 25
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyGridFileProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCPropertyGridFileProperty` 클래스가 지 원하는 속성 목록 컨트롤 항목 파일 선택 대화 상자가 열립니다.  
  
## 구문  
  
```  
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty](../Topic/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty.md)|`CMFCPropertyGridFileProperty` 개체를 생성합니다.|  
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|`CMFCPropertyGridFileProperty::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|`CMFCPropertyGridFileProperty::OnClickButton`|\(재정의 [CMFCPropertyGridProperty::OnClickButton](../Topic/CMFCPropertyGridProperty::OnClickButton.md).\)|  
  
### 설명  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)  
  
## 요구 사항  
 **헤더:** afxpropertygridctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty Class](../../mfc/reference/cmfcpropertygridproperty-class.md)