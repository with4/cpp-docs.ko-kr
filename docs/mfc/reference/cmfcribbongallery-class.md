---
title: "CMFCRibbonGallery Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonGallery"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonGallery class"
ms.assetid: 9734c9c9-981c-4b3f-8c59-264fd41811b4
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CMFCRibbonGallery Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Office 2007 스타일 리본 갤러리를 구현 합니다.  
  
## 구문  
  
```  
class CMFCRibbonGallery : public CMFCRibbonButton  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonGallery::CMFCRibbonGallery](../Topic/CMFCRibbonGallery::CMFCRibbonGallery.md)|생성 및 초기화는 `CMFCRibbonGallery` 개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonGallery::AddGroup](../Topic/CMFCRibbonGallery::AddGroup.md)|갤러리에 새 그룹을 추가합니다.|  
|[CMFCRibbonGallery::AddSubItem](../Topic/CMFCRibbonGallery::AddSubItem.md)|드롭다운 메뉴에 새 메뉴 항목을 추가합니다.|  
|[CMFCRibbonGallery::Clear](../Topic/CMFCRibbonGallery::Clear.md)|갤러리의 내용을 지웁니다.|  
|[CMFCRibbonGallery::EnableMenuResize](../Topic/CMFCRibbonGallery::EnableMenuResize.md)|\[메뉴\] 패널의 크기 조정에 사용할 수 있거나.|  
|[CMFCRibbonGallery::EnableMenuSideBar](../Topic/CMFCRibbonGallery::EnableMenuSideBar.md)|세로 막대에는 팝업 메뉴의 왼쪽에 사용할 수 있거나.|  
|[CMFCRibbonGallery::GetCompactSize](../Topic/CMFCRibbonGallery::GetCompactSize.md)|\(재정의 [CMFCRibbonButton::GetCompactSize](../Topic/CMFCRibbonButton::GetCompactSize.md).\)|  
|[CMFCRibbonGallery::GetDroppedDown](../Topic/CMFCRibbonGallery::GetDroppedDown.md)|\(재정의 [CMFCRibbonBaseElement::GetDroppedDown](../Topic/CMFCRibbonBaseElement::GetDroppedDown.md).\)|  
|[CMFCRibbonGallery::GetGroupName](../Topic/CMFCRibbonGallery::GetGroupName.md)|지정 된 인덱스에 있는 그룹의 이름을 반환 합니다.|  
|[CMFCRibbonGallery::GetGroupOffset](../Topic/CMFCRibbonGallery::GetGroupOffset.md)||  
|[CMFCRibbonGallery::GetIconsInRow](../Topic/CMFCRibbonGallery::GetIconsInRow.md)|리본 갤러리의 행에서 항목 수를 반환합니다.|  
|[CMFCRibbonGallery::GetItemToolTip](../Topic/CMFCRibbonGallery::GetItemToolTip.md)|갤러리에서 항목에 연결 된 도구 설명 텍스트를 반환 합니다.|  
|[CMFCRibbonGallery::GetLastSelectedItem](../Topic/CMFCRibbonGallery::GetLastSelectedItem.md)|갤러리에는 사용자가 선택한 마지막 항목의 인덱스를 반환 합니다.|  
|[CMFCRibbonGallery::GetPaletteID](../Topic/CMFCRibbonGallery::GetPaletteID.md)|현재 갤러리의 명령 ID를 반환 합니다.|  
|[CMFCRibbonGallery::GetRegularSize](../Topic/CMFCRibbonGallery::GetRegularSize.md)|\(재정의 [CMFCRibbonButton::GetRegularSize](../Topic/CMFCRibbonButton::GetRegularSize.md).\)|  
|[CMFCRibbonGallery::GetSelectedItem](../Topic/CMFCRibbonGallery::GetSelectedItem.md)||  
|[CMFCRibbonGallery::HasMenu](../Topic/CMFCRibbonGallery::HasMenu.md)|\(재정의 [CMFCRibbonButton::HasMenu](../Topic/CMFCRibbonButton::HasMenu.md).\)|  
|[CMFCRibbonGallery::IsButtonMode](../Topic/CMFCRibbonGallery::IsButtonMode.md)|갤러리 갤러리 단추에 포함 되어 있는지 여부를 지정 합니다.|  
|[CMFCRibbonGallery::IsMenuResizeEnabled](../Topic/CMFCRibbonGallery::IsMenuResizeEnabled.md)|메뉴 크기 조정을 사용할지 여부를 지정 합니다.|  
|[CMFCRibbonGallery::IsMenuResizeVertical](../Topic/CMFCRibbonGallery::IsMenuResizeVertical.md)||  
|[CMFCRibbonGallery::IsMenuSideBar](../Topic/CMFCRibbonGallery::IsMenuSideBar.md)|측면 표시줄의 활성화 여부를 지정 합니다.|  
|[CMFCRibbonGallery::OnAfterChangeRect](../Topic/CMFCRibbonGallery::OnAfterChangeRect.md)|\(재정의 `CMFCRibbonButton::OnAfterChangeRect`.\)|  
|[CMFCRibbonGallery::OnDraw](../Topic/CMFCRibbonGallery::OnDraw.md)|\(재정의 [CMFCRibbonButton::OnDraw](../Topic/CMFCRibbonButton::OnDraw.md).\)|  
|[CMFCRibbonGallery::OnEnable](../Topic/CMFCRibbonGallery::OnEnable.md)|\(재정의 `CMFCRibbonBaseElement::OnEnable`.\)|  
|[CMFCRibbonGallery::OnRTLChanged](../Topic/CMFCRibbonGallery::OnRTLChanged.md)|\(재정의 [CMFCRibbonBaseElement::OnRTLChanged](../Topic/CMFCRibbonBaseElement::OnRTLChanged.md).\)|  
|[CMFCRibbonGallery::RedrawIcons](../Topic/CMFCRibbonGallery::RedrawIcons.md)|갤러리를 다시 그립니다.|  
|[CMFCRibbonGallery::RemoveItemToolTips](../Topic/CMFCRibbonGallery::RemoveItemToolTips.md)|도구 설명을 갤러리의 모든 항목을 제거합니다.|  
|[CMFCRibbonGallery::SelectItem](../Topic/CMFCRibbonGallery::SelectItem.md)||  
|[CMFCRibbonGallery::SetACCData](../Topic/CMFCRibbonGallery::SetACCData.md)|\(재정의 [CMFCRibbonButton::SetACCData](../Topic/CMFCRibbonButton::SetACCData.md).\)|  
|[CMFCRibbonGallery::SetButtonMode](../Topic/CMFCRibbonGallery::SetButtonMode.md)|리본 갤러리 드롭다운 단추 또는 리본 메뉴에서 직접 팔레트를 표시할지 여부를 지정 합니다.|  
|[CMFCRibbonGallery::SetGroupName](../Topic/CMFCRibbonGallery::SetGroupName.md)|그룹 이름을 설정합니다.|  
|[CMFCRibbonGallery::SetIconsInRow](../Topic/CMFCRibbonGallery::SetIconsInRow.md)|갤러리에서 항목 당 행 수를 정의합니다.|  
|[CMFCRibbonGallery::SetItemToolTip](../Topic/CMFCRibbonGallery::SetItemToolTip.md)|갤러리에서 항목에 대 한 도구 설명 텍스트를 설정합니다.|  
|[CMFCRibbonGallery::SetPalette](../Topic/CMFCRibbonGallery::SetPalette.md)|팔레트 리본 갤러리에 첨부합니다.|  
|[CMFCRibbonGallery::SetPaletteID](../Topic/CMFCRibbonGallery::SetPaletteID.md)|전송 된 명령 ID를 정의 `WM_COMMAND` 갤러리 항목을 선택 하면 됩니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonGallery::OnDrawPaletteIcon](../Topic/CMFCRibbonGallery::OnDrawPaletteIcon.md)|갤러리 아이콘을 그릴 때 프레임 워크에 의해 호출 됩니다.|  
  
## 설명  
 갤러리는 사용자가 양식을 열 때 표시 된다는 갤러리 단추 일반 메뉴 단추 처럼 작동 합니다.  갤러리에서 항목을 선택 하면 프레임 워크는 전송 된 `WM_COMMAND` 단추 명령 ID와 함께 메시지.  메시지를 처리할 때 호출 해야 [CMFCRibbonGallery::GetLastSelectedItem](../Topic/CMFCRibbonGallery::GetLastSelectedItem.md) 갤러리에서 선택 된 항목을 확인 합니다.  
  
## 예제  
 다음 예제에서는 다양 한 메서드를 사용 하는 방법의 `CMFCRibbonGallery` 클래스를 구성 하는 `CMFCRibbonGallery` 개체입니다.  갤러리에서 항목 당 행 수를 지정, \[메뉴\] 패널의 크기 조정 가능, 세로 막대에는 팝업 메뉴의 왼쪽에 사용 및 리본 갤러리는 리본 표시줄에서 직접 팔레트 표시 방법을 예제를 보여 줍니다.  이 코드 조각에 속하지는  [그릴 클라이언트 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#6](../../mfc/reference/codesnippet/CPP/cmfcribbongallery-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md) [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md) [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
## 요구 사항  
 **헤더:** afxRibbonPaletteGallery.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonGalleryMenuButton Class](../../mfc/reference/cmfcribbongallerymenubutton-class.md)