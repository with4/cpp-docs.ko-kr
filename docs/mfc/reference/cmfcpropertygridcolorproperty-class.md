---
title: "CMFCPropertyGridColorProperty Class | Microsoft Docs"
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
  - "CMFCPropertyGridColorProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridColorProperty class"
  - "CMFCPropertyGridColorProperty::FormatProperty method"
  - "CMFCPropertyGridColorProperty::OnClickButton method"
  - "CMFCPropertyGridColorProperty::OnDrawValue method"
  - "CMFCPropertyGridColorProperty::OnEdit method"
  - "CMFCPropertyGridColorProperty::OnUpdateValue method"
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
caps.latest.revision: 33
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyGridColorProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCPropertyGridColorProperty` 클래스는 색 선택 항목 대화 상자를 여는 속성 목록 컨트롤 항목을 지원합니다.  
  
## 구문  
  
```  
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](../Topic/CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty.md)|`CMFCPropertyGridColorProperty` 개체를 생성합니다.|  
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](../Topic/CMFCPropertyGridColorProperty::EnableAutomaticButton.md)|색 선택 대화 상자에서 *자동* 단추를 사용하도록 설정합니다.  \(표준 자동 단추에는 **자동** 레이블이 지정됩니다.\)|  
|[CMFCPropertyGridColorProperty::EnableOtherButton](../Topic/CMFCPropertyGridColorProperty::EnableOtherButton.md)|색 선택 대화 상자에서 *기타* 단추를 사용하도록 설정합니다.  \(표준 기타 단추에는 **다른 색...** 레이블이 지정됩니다.\)|  
|`CMFCPropertyGridColorProperty::FormatProperty`|속성 값의 텍스트 표현에 서식을 지정합니다.  \([CMFCPropertyGridProperty::FormatProperty](../Topic/CMFCPropertyGridProperty::FormatProperty.md)를 재정의합니다.\)|  
|[CMFCPropertyGridColorProperty::GetColor](../Topic/CMFCPropertyGridColorProperty::GetColor.md)|속성의 현재 색을 가져옵니다.|  
|`CMFCPropertyGridColorProperty::GetThisClass`|프레임워크에서 이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 가져오는 데 사용합니다.|  
|`CMFCPropertyGridColorProperty::OnClickButton`|사용자가 속성에 포함된 단추를 클릭하면 프레임워크에서 호출됩니다.  \([CMFCPropertyGridProperty::OnClickButton](../Topic/CMFCPropertyGridProperty::OnClickButton.md)을 재정의합니다.\)|  
|`CMFCPropertyGridColorProperty::OnDrawValue`|속성 값을 표시하기 위해 프레임워크에서 호출됩니다.  \([CMFCPropertyGridProperty::OnDrawValue](../Topic/CMFCPropertyGridProperty::OnDrawValue.md)를 재정의합니다.\)|  
|`CMFCPropertyGridColorProperty::OnEdit`|사용자가 속성 값을 수정하려고 할 때 프레임워크에서 호출됩니다.  \([CMFCPropertyGridProperty::OnEdit](../Topic/CMFCPropertyGridProperty::OnEdit.md)을 재정의합니다.\)|  
|`CMFCPropertyGridColorProperty::OnUpdateValue`|편집 가능한 속성 값이 변경되었을 때 프레임워크에서 호출됩니다.  \([CMFCPropertyGridProperty::OnUpdateValue](../Topic/CMFCPropertyGridProperty::OnUpdateValue.md)를 재정의합니다.\)|  
|[CMFCPropertyGridColorProperty::SetColor](../Topic/CMFCPropertyGridColorProperty::SetColor.md)|속성에 대한 새로운 색을 설정합니다.|  
|[CMFCPropertyGridColorProperty::SetColumnsNumber](../Topic/CMFCPropertyGridColorProperty::SetColumnsNumber.md)|현재 색 속성 표의 열 수를 지정합니다.|  
|[CMFCPropertyGridColorProperty::SetOriginalValue](../Topic/CMFCPropertyGridColorProperty::SetOriginalValue.md)|편집 가능한 속성의 원래 값을 설정합니다.|  
  
## 설명  
 `CMFCPropertyGridColorProperty` 클래스는 속성 목록 컨트롤에 추가할 수 있는 색 속성을 지원합니다.  자세한 내용은 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md)를 참조하세요.  
  
## 예제  
 다음 예제에서는 `CMFCPropertyGridColorProperty` 클래스의 개체를 생성하고 `CMFCPropertyGridColorProperty` 클래스의 다양한 메서드를 사용하여 이 개체를 구성하는 방법을 보여 줍니다.  코드에서는 자동 및 기타 단추를 사용하도록 설정하는 방법과 색 및 열 번호를 설정하는 방법을 설명합니다.  이 예제는 [새 컨트롤 샘플](../../top/visual-cpp-samples.md)의 일부입니다.  
  
 [!code-cpp[NVC_MFC_NewControls#13](../../mfc/reference/codesnippet/CPP/cmfcpropertygridcolorproperty-class_1.cpp)]  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)  
  
## 요구 사항  
 **헤더:** afxpropertygridctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty Class](../../mfc/reference/cmfcpropertygridproperty-class.md)