---
title: "CMFCPropertyGridFontProperty Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPropertyGridFontProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridFontProperty class"
  - "CMFCPropertyGridFontProperty::FormatProperty method"
  - "CMFCPropertyGridFontProperty::OnClickButton method"
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMFCPropertyGridFontProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCPropertyGridFileProperty` 클래스가 지 원하는 속성 목록 컨트롤 항목 글꼴 선택 대화 상자가 열립니다.  
  
## 구문  
  
```  
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty](../Topic/CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty.md)|`CMFCPropertyGridFontProperty` 개체를 생성합니다.|  
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|`CMFCPropertyGridFontProperty::FormatProperty`|속성 값의 텍스트 표현과 서식을 지정합니다.  \(재정의 [CMFCPropertyGridProperty::FormatProperty](../Topic/CMFCPropertyGridProperty::FormatProperty.md).\)|  
|[CMFCPropertyGridFontProperty::GetColor](../Topic/CMFCPropertyGridFontProperty::GetColor.md)|글꼴 대화 상자에서 사용자가 선택한 글꼴 색을 검색 합니다.|  
|[CMFCPropertyGridFontProperty::GetLogFont](../Topic/CMFCPropertyGridFontProperty::GetLogFont.md)|글꼴 대화 상자에서 사용자가 선택한 글꼴을 검색 합니다.|  
|`CMFCPropertyGridFontProperty::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|`CMFCPropertyGridFontProperty::OnClickButton`|속성에 포함 된 단추를 클릭할 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CMFCPropertyGridProperty::OnClickButton](../Topic/CMFCPropertyGridProperty::OnClickButton.md).\)|  
  
## 설명  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)  
  
## 요구 사항  
 **헤더:** afxpropertygridctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty Class](../../mfc/reference/cmfcpropertygridproperty-class.md)