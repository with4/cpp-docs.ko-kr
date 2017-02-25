---
title: "CMFCRibbonComboBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonComboBox class"
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMFCRibbonComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonComboBox` 리본 표시줄, 리본 패널 또는 리본 팝업 메뉴에 추가할 수 있는 콤보 상자 컨트롤 클래스를 구현 합니다.  
  
## 구문  
  
```  
class CMFCRibbonComboBox : public CMFCRibbonEdit  
```  
  
## Members  
  
### 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonComboBox::CMFCRibbonComboBox](../Topic/CMFCRibbonComboBox::CMFCRibbonComboBox.md)|CMFCRibbonComboBox 개체를 만듭니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonComboBox::AddItem](../Topic/CMFCRibbonComboBox::AddItem.md)|고유 항목을 목록 상자에 추가합니다.|  
|[CMFCRibbonComboBox::DeleteItem](../Topic/CMFCRibbonComboBox::DeleteItem.md)|목록 상자에서 지정 된 항목을 삭제합니다.|  
|[CMFCRibbonComboBox::EnableDropDownListResize](../Topic/CMFCRibbonComboBox::EnableDropDownListResize.md)|그 떨어지면 목록 상자의 크기를 변경할 수 있는지 여부를 지정 합니다.|  
|[CMFCRibbonComboBox::FindItem](../Topic/CMFCRibbonComboBox::FindItem.md)|목록 상자에는 지정 된 문자열과 일치 하는 첫 번째 항목의 인덱스를 반환 합니다.|  
|[CMFCRibbonComboBox::GetCount](../Topic/CMFCRibbonComboBox::GetCount.md)|목록 상자에서 항목 수를 반환합니다.|  
|[CMFCRibbonComboBox::GetCurSel](../Topic/CMFCRibbonComboBox::GetCurSel.md)|목록 상자에서 현재 선택한 항목의 인덱스를 가져옵니다.|  
|[CMFCRibbonComboBox::GetDropDownHeight](../Topic/CMFCRibbonComboBox::GetDropDownHeight.md)|목록 상자를 놓을 때 목록 상자의 높이를 가져옵니다.|  
|[CMFCRibbonComboBox::GetIntermediateSize](../Topic/CMFCRibbonComboBox::GetIntermediateSize.md)|콤보 상자의 크기를 중간 모드에 표시 된 대로 반환 합니다.|  
|[CMFCRibbonComboBox::GetItem](../Topic/CMFCRibbonComboBox::GetItem.md)|항목 목록 상자에서 지정 된 인덱스와 연결 된 문자열을 반환 합니다.|  
|[CMFCRibbonComboBox::GetItemData](../Topic/CMFCRibbonComboBox::GetItemData.md)|목록 상자에서 지정 된 인덱스의 항목에 연결 된 데이터를 반환 합니다.|  
|[CMFCRibbonComboBox::HasEditBox](../Topic/CMFCRibbonComboBox::HasEditBox.md)|편집 상자 컨트롤에 있는지 여부를 나타냅니다.|  
|[CMFCRibbonComboBox::IsResizeDropDownList](../Topic/CMFCRibbonComboBox::IsResizeDropDownList.md)|목록 상자의 크기를 조정할 수 있는지 여부를 나타냅니다.|  
|[CMFCRibbonComboBox::OnSelectItem](../Topic/CMFCRibbonComboBox::OnSelectItem.md)|사용자 목록 상자에서 항목을 선택 하면 프레임 워크에서 호출 됩니다.|  
|[CMFCRibbonComboBox::RemoveAllItems](../Topic/CMFCRibbonComboBox::RemoveAllItems.md)|목록 상자에서 모든 항목을 삭제 하 고 편집 상자를 지웁니다.|  
|[CMFCRibbonComboBox::SelectItem](../Topic/CMFCRibbonComboBox::SelectItem.md)|목록 상자에서 항목을 선택합니다.|  
|[CMFCRibbonComboBox::SetDropDownHeight](../Topic/CMFCRibbonComboBox::SetDropDownHeight.md)|삭제 하면 목록 상자의 높이를 설정 합니다.|  
  
## 설명  
 리본 콤보 상자 목록 상자는 정적 레이블 또는 레이블 사용자가 편집할 수와 함께 구성 됩니다.  리본 콤보 상자를 만들 때 원하는 형식을 지정 해야 합니다.  
  
## 예제  
 다음 예제에서는 개체를 생성 하는 방법을 보여 줍니다.을 `CMFCRibbonComboBox` 클래스, 콤보 상자에 항목을 추가, 콤보 상자에서 항목을 선택 하 고 패널에 콤보 상자를 추가 합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/CPP/cmfcribboncombobox-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
## 요구 사항  
 **헤더:** afxribboncombobox.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonEdit Class](../../mfc/reference/cmfcribbonedit-class.md)