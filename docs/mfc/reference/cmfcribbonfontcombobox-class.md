---
title: "CMFCRibbonFontComboBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonFontComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonFontComboBox class"
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMFCRibbonFontComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

글꼴 목록이 포함된 콤보 상자를 구현합니다.  콤보 상자를 리본 패널에 배치합니다.  
  
## 구문  
  
```  
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|소멸자|  
  
### Protected 생성자  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](../Topic/CMFCRibbonFontComboBox::CMFCRibbonFontComboBox.md)|`CMFCRibbonFontComboBox` 개체를 생성하고 초기화합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonFontComboBox::BuildFonts](../Topic/CMFCRibbonFontComboBox::BuildFonts.md)|지정된 글꼴 종류, 문자 집합, 피치 및 패밀리의 글꼴로 리본 글꼴 콤보 상자를 채웁니다.|  
|`CMFCRibbonFontComboBox::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|[CMFCRibbonFontComboBox::GetCharSet](../Topic/CMFCRibbonFontComboBox::GetCharSet.md)|지정된 문자 집합을 반환합니다.|  
|[CMFCRibbonFontComboBox::GetFontDesc](../Topic/CMFCRibbonFontComboBox::GetFontDesc.md)||  
|[CMFCRibbonFontComboBox::GetFontType](../Topic/CMFCRibbonFontComboBox::GetFontType.md)|콤보 상자에 표시할 글꼴 종류를 반환합니다.  유효한 옵션 DEVICE\_FONTTYPE, RASTER\_FONTTYPE, TRUETYPE\_FONTTYPE 또는 이러한 옵션의 비트 조합입니다.|  
|[CMFCRibbonFontComboBox::GetPitchAndFamily](../Topic/CMFCRibbonFontComboBox::GetPitchAndFamily.md)|콤보 상자에 표시되는 글꼴의 피치 및 패밀리를 반환합니다.|  
|`CMFCRibbonFontComboBox::GetThisClass`|프레임워크에서 이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 가져오는 데 사용합니다.|  
|[CMFCRibbonFontComboBox::RebuildFonts](../Topic/CMFCRibbonFontComboBox::RebuildFonts.md)|이전에 지정한 글꼴 종류, 문자 집합, 피치 및 패밀리의 글꼴로 리본 글꼴 콤보 상자를 채웁니다.|  
|[CMFCRibbonFontComboBox::SetFont](../Topic/CMFCRibbonFontComboBox::SetFont.md)|콤보 상자에서 지정된 글꼴을 선택합니다.|  
  
## 설명  
 `CMFCRibbonFontComboBox` 개체를 만든 후 [CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md)를 호출하여 리본 패널에 추가합니다.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
 [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)  
  
## 요구 사항  
 **헤더:** afxRibbonComboBox.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonComboBox Class](../../mfc/reference/cmfcribboncombobox-class.md)