---
title: "CMFCRibbonEdit Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonEdit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonEdit class"
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CMFCRibbonEdit Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

리본 메뉴 모음에 있는 편집 컨트롤을 구현 합니다.  
  
## 구문  
  
```  
class CMFCRibbonEdit : public CMFCRibbonButton  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonEdit::CMFCRibbonEdit](../Topic/CMFCRibbonEdit::CMFCRibbonEdit.md)|`CMFCRibbonEdit` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonEdit::CanBeStretched](../Topic/CMFCRibbonEdit::CanBeStretched.md)|나타냅니다 여부의 높이 `CMFCRibbonEdit` 컨트롤 수 증가 세로 리본 행 높이를.|  
|[CMFCRibbonEdit::CMFCRibbonEdit](../Topic/CMFCRibbonEdit::CMFCRibbonEdit.md)|`CMFCRibbonEdit` 개체를 생성합니다.|  
|[CMFCRibbonEdit::CopyFrom](../Topic/CMFCRibbonEdit::CopyFrom.md)|지정 된 상태의 복사 `CMFCRibbonEdit` 개체에는 현재 `CMFCRibbonEdit` 개체.|  
|[CMFCRibbonEdit::CreateEdit](../Topic/CMFCRibbonEdit::CreateEdit.md)|새 텍스트 상자를 만들고는 `CMFCRibbonEdit` 개체입니다.|  
|[CMFCRibbonEdit::DestroyCtrl](../Topic/CMFCRibbonEdit::DestroyCtrl.md)|`CMFCRibbonEdit` 개체를 소멸시킵니다.|  
|[CMFCRibbonEdit::DropDownList](../Topic/CMFCRibbonEdit::DropDownList.md)|목록 상자를 삭제합니다.|  
|[CMFCRibbonEdit::EnableSpinButtons](../Topic/CMFCRibbonEdit::EnableSpinButtons.md)|스핀 단추 텍스트 상자에 대 한 범위를 설정 하 고 있습니다.|  
|[CMFCRibbonEdit::GetCompactSize](../Topic/CMFCRibbonEdit::GetCompactSize.md)|압축 크기를 검색에 `CFMCRibbonEdit` 개체입니다.|  
|[CMFCRibbonEdit::GetEditText](../Topic/CMFCRibbonEdit::GetEditText.md)|텍스트 상자에서 텍스트를 검색합니다.|  
|[CMFCRibbonEdit::GetIntermediateSize](../Topic/CMFCRibbonEdit::GetIntermediateSize.md)|중간 크기의 검색은 `CMFCRibbonEdit` 개체입니다.|  
|[CMFCRibbonEdit::GetTextAlign](../Topic/CMFCRibbonEdit::GetTextAlign.md)|텍스트 상자에서 텍스트의 맞춤을 검색합니다.|  
|[CMFCRibbonEdit::GetWidth](../Topic/CMFCRibbonEdit::GetWidth.md)|너비를 픽셀 단위로 검색은 `CMFCRibbonEdit` 제어 합니다.|  
|[CMFCRibbonEdit::HasCompactMode](../Topic/CMFCRibbonEdit::HasCompactMode.md)|나타내는 표시의 크기 여부는 `CMFCRibbonEdit` 컨트롤 압축 될 수 있습니다.|  
|[CMFCRibbonEdit::HasFocus](../Topic/CMFCRibbonEdit::HasFocus.md)|나타냅니다 여부는 `CMFCRIbbonEdit` 컨트롤에 포커스가 있습니다.|  
|[CMFCRibbonEdit::HasLargeMode](../Topic/CMFCRibbonEdit::HasLargeMode.md)|나타내는 표시의 크기 여부는 `CMFCRibbonEdit` 큰 제어 될 수 있습니다.|  
|[CMFCRibbonEdit::HasSpinButtons](../Topic/CMFCRibbonEdit::HasSpinButtons.md)|텍스트 상자는 스핀 단추를 포함할지 여부를 나타냅니다.|  
|[CMFCRibbonEdit::IsHighlighted](../Topic/CMFCRibbonEdit::IsHighlighted.md)|나타냅니다 여부는 `CMFCRibbonEdit` 컨트롤을 강조 표시 합니다.|  
|[CMFCRibbonEdit::OnAfterChangeRect](../Topic/CMFCRibbonEdit::OnAfterChangeRect.md)|프레임 워크에서 호출 하면 표시 사각형의 크기는 `CMFCRibbonEdit` 제어 변경.|  
|[CMFCRibbonEdit::OnDraw](../Topic/CMFCRibbonEdit::OnDraw.md)|그리려면 프레임 워크에서 호출을 `CMFCRibbonEdit` 제어 합니다.|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](../Topic/CMFCRibbonEdit::OnDrawLabelAndImage.md)|레이블을 그리기 및 이미지에 대 한 프레임 워크에 의해 호출 된 `CMFCRibbonEdit` 컨트롤.|  
|[CMFCRibbonEdit::OnDrawOnList](../Topic/CMFCRibbonEdit::OnDrawOnList.md)|그리려면 프레임 워크에서 호출을 `CMFCRibbonEdit` 명령 목록 상자에서 컨트롤입니다.|  
|[CMFCRibbonEdit::OnEnable](../Topic/CMFCRibbonEdit::OnEnable.md)|활성화 또는 비활성화 하 여 프레임 워크에서 호출을 `CMFCRibbonEdit` 제어 합니다.|  
|[CMFCRibbonEdit::OnHighlight](../Topic/CMFCRibbonEdit::OnHighlight.md)|포인터 입력 하거나 범위를 벗어날 때 프레임 워크에 의해 호출 된 `CMFCRibbonEdit` 컨트롤.|  
|[CMFCRibbonEdit::OnKey](../Topic/CMFCRibbonEdit::OnKey.md)|Keytip을 누를 때 프레임 워크에서 호출 하는 `CMFCRibbonEdit` 컨트롤에 포커스가 있습니다.|  
|[CMFCRibbonEdit::OnLButtonDown](../Topic/CMFCRibbonEdit::OnLButtonDown.md)|업데이트 프레임 워크에서 호출을 `CMFCRibbonEdit` 제어할 때 사용자 컨트롤에서 마우스 왼쪽된 단추를 누를.|  
|[CMFCRibbonEdit::OnLButtonUp](../Topic/CMFCRibbonEdit::OnLButtonUp.md)|왼쪽된 마우스 단추를 놓을 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCRibbonEdit::OnRTLChanged](../Topic/CMFCRibbonEdit::OnRTLChanged.md)|업데이트 프레임 워크에서 호출의 `CMFCRibbonEdit` 레이아웃 방향을 변경 하는 시기를 제어 합니다.|  
|[CMFCRibbonEdit::OnShow](../Topic/CMFCRibbonEdit::OnShow.md)|표시 하거나 숨길 수 있는 프레임 워크에서 호출을 `CMFCRibbonEdit` 제어 합니다.|  
|[CMFCRibbonEdit::Redraw](../Topic/CMFCRibbonEdit::Redraw.md)|디스플레이의 업데이트는 `CMFCRibbonEdit` 제어 합니다.|  
|[CMFCRibbonEdit::SetACCData](../Topic/CMFCRibbonEdit::SetACCData.md)|내게 필요한 옵션 데이터를 설정 하는 `CMFCRibbonEdit` 개체입니다.|  
|[CMFCRibbonEdit::SetEditText](../Topic/CMFCRibbonEdit::SetEditText.md)|텍스트 상자에 텍스트를 설정합니다.|  
|[CMFCRibbonEdit::SetTextAlign](../Topic/CMFCRibbonEdit::SetTextAlign.md)|텍스트 상자의 텍스트 맞춤을 설정합니다.|  
|[CMFCRibbonEdit::SetWidth](../Topic/CMFCRibbonEdit::SetWidth.md)|텍스트 상자의 너비는 `CMFCRibbonEdit` 컨트롤입니다.|  
  
## 설명  
  
## 예제  
 다음 예제에서는 생성 하는 방법을 보여 줍니다.를 `CMFCRibbonEdit` 개체, 편집 컨트롤 옆에 있는 스핀 단추를 표시 및 편집 컨트롤의 텍스트를 설정 합니다.  이 코드 조각에 속해 있는  [MS Office 2007 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/CPP/cmfcribbonedit-class_1.cpp)]  
  
## 요구 사항  
 **헤더:** afxRibbonEdit.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)