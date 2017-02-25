---
title: "CMFCRibbonBaseElement Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonBaseElement"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonBaseElement class"
ms.assetid: 419ea91b-5062-44cc-b0a3-f87d29566f62
caps.latest.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 36
---
# CMFCRibbonBaseElement Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonBaseElement` 클래스는 기본 클래스에 추가할 수 있는 모든 요소는  [리본 표시줄](../../mfc/reference/cmfcribbonbar-class.md).  리본 요소의 예로 리본 단추, 확인란, 리본 및 리본 콤보 상자.  
  
## 구문  
  
```  
class CMFCRibbonBaseElement : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CMFCRibbonBaseElement`|`CMFCRibbonBaseElement` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonBaseElement::AddToKeyList](../Topic/CMFCRibbonBaseElement::AddToKeyList.md)|Keytip 리본 요소에 대 한 키 배열을 추가합니다.|  
|[CMFCRibbonBaseElement::AddToListBox](../Topic/CMFCRibbonBaseElement::AddToListBox.md)|리본 요소에 지정 된 리본 메뉴 명령 목록 상자에 추가합니다.|  
|[CMFCRibbonBaseElement::CanBeAddedToQuickAccessToolBar](../Topic/CMFCRibbonBaseElement::CanBeAddedToQuickAccessToolBar.md)|빠른 실행 도구 모음에는 리본 요소를 추가할 수 있는지를 나타냅니다.|  
|[CMFCRibbonBaseElement::CanBeCompacted](../Topic/CMFCRibbonBaseElement::CanBeCompacted.md)|리본 구성 요소의 크기가 압축 될 수 있는지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::CanBeStretched](../Topic/CMFCRibbonBaseElement::CanBeStretched.md)|리본 구성 요소의 높이 리본 행 높이를 세로로 늘릴 수 있습니다 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::CanBeStretchedHorizontally](../Topic/CMFCRibbonBaseElement::CanBeStretchedHorizontally.md)|리본 구성 요소의 너비를 변경할 수 있는지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::CleanUpSizes](../Topic/CMFCRibbonBaseElement::CleanUpSizes.md)|리본 요소에 대 한 차원 설정을 정리합니다.|  
|[CMFCRibbonBaseElement::ClosePopupMenu](../Topic/CMFCRibbonBaseElement::ClosePopupMenu.md)|리본 요소에 대 한 팝업 메뉴를 닫습니다.|  
|[CMFCRibbonBaseElement::CopyFrom](../Topic/CMFCRibbonBaseElement::CopyFrom.md)|지정 된 상태의 복사 `CMFCRibbonBaseElement` 현재 개체입니다.|  
|[CMFCRibbonBaseElement::DestroyCtrl](../Topic/CMFCRibbonBaseElement::DestroyCtrl.md)|리본 요소를 소멸 시킵니다.|  
|[CMFCRibbonBaseElement::DrawImage](../Topic/CMFCRibbonBaseElement::DrawImage.md)|리본 요소에 대 한 이미지를 그립니다.|  
|[CMFCRibbonBaseElement::Find](../Topic/CMFCRibbonBaseElement::Find.md)|현재 개체를 가리키면 리본 요소에 지정 된 포인터를 반환 합니다.|  
|[CMFCRibbonBaseElement::FindByData](../Topic/CMFCRibbonBaseElement::FindByData.md)|지정 된 데이터를 포함 하는 경우에 리본 요소에 대 한 포인터를 검색 합니다.|  
|[CMFCRibbonBaseElement::FindByID](../Topic/CMFCRibbonBaseElement::FindByID.md)|해당 요소에 지정 된 명령 ID가 식별 되는 경우 리본 요소에 대 한 포인터를 검색 합니다.|  
|[CMFCRibbonBaseElement::FindByOriginal](../Topic/CMFCRibbonBaseElement::FindByOriginal.md)|원래 리본 요소를 지정한 리본 요소와 일치 하는 리본 요소에 대 한 포인터를 검색 합니다.|  
|[CMFCRibbonBaseElement::GetCompactSize](../Topic/CMFCRibbonBaseElement::GetCompactSize.md)|컴팩트한 사이즈의 리본 요소를 반환합니다.|  
|[CMFCRibbonBaseElement::GetData](../Topic/CMFCRibbonBaseElement::GetData.md)|리본 요소와 연관 된 사용자 정의 데이터를 검색 합니다.|  
|[CMFCRibbonBaseElement::GetDescription](../Topic/CMFCRibbonBaseElement::GetDescription.md)|리본 요소에 대 한 설명을 반환합니다.|  
|[CMFCRibbonBaseElement::GetDroppedDown](../Topic/CMFCRibbonBaseElement::GetDroppedDown.md)|팝업 메뉴의 삭제 경우에 리본 요소에 대 한 포인터를 검색 합니다.|  
|[CMFCRibbonBaseElement::GetElements](../Topic/CMFCRibbonBaseElement::GetElements.md)|현재 리본 요소에 지정 된 배열에 추가합니다.|  
|[CMFCRibbonBaseElement::GetElementsByID](../Topic/CMFCRibbonBaseElement::GetElementsByID.md)|현재 리본 요소 지정 된 명령 id가 포함 된 경우 현재 리본 요소를 지정 된 배열에 추가|  
|[CMFCRibbonBaseElement::GetHighlighted](../Topic/CMFCRibbonBaseElement::GetHighlighted.md)|강조 표시 되는 경우 리본 요소에 대 한 포인터를 검색 합니다.|  
|[CMFCRibbonBaseElement::GetID](../Topic/CMFCRibbonBaseElement::GetID.md)|명령 ID는 리본 요소를 반환합니다.|  
|[CMFCRibbonBaseElement::GetImageSize](../Topic/CMFCRibbonBaseElement::GetImageSize.md)|이미지 크기의 리본 요소를 반환합니다.|  
|[CMFCRibbonBaseElement::GetIntermediateSize](../Topic/CMFCRibbonBaseElement::GetIntermediateSize.md)|리본 구성 요소의 크기를 중간 상태로 반환합니다.|  
|[CMFCRibbonBaseElement::GetKeys](../Topic/CMFCRibbonBaseElement::GetKeys.md)|리본 요소와 연관 된 keytip을 반환 합니다.|  
|[CMFCRibbonBaseElement::GetKeyTipRect](../Topic/CMFCRibbonBaseElement::GetKeyTipRect.md)|리본 요소에 keytip 경계 사각형을 검색합니다.|  
|[CMFCRibbonBaseElement::GetKeyTipSize](../Topic/CMFCRibbonBaseElement::GetKeyTipSize.md)|Keytip 텍스트의 크기를 검색합니다.|  
|[CMFCRibbonBaseElement::GetLocationInGroup](../Topic/CMFCRibbonBaseElement::GetLocationInGroup.md)|리본 그룹에는 리본 요소의 표시 위치를 나타냅니다.|  
|[CMFCRibbonBaseElement::GetMenuKeys](../Topic/CMFCRibbonBaseElement::GetMenuKeys.md)|단추와 연결 된 키를 반환 합니다.|  
|[CMFCRibbonBaseElement::GetNotifyID](../Topic/CMFCRibbonBaseElement::GetNotifyID.md)|리본 요소에 대 한 알림 명령 ID를 검색합니다.|  
|[CMFCRibbonBaseElement::GetOriginal](../Topic/CMFCRibbonBaseElement::GetOriginal.md)|원래 리본 요소를 검색합니다.|  
|[CMFCRibbonBaseElement::GetParentCategory](../Topic/CMFCRibbonBaseElement::GetParentCategory.md)|리본 메뉴는 리본 요소에 대 한 범주를 검색합니다.|  
|[CMFCRibbonBaseElement::GetParentPanel](../Topic/CMFCRibbonBaseElement::GetParentPanel.md)|리본 패널이 리본 요소를 포함 하는 검색 합니다.|  
|[CMFCRibbonBaseElement::GetParentRibbonBar](../Topic/CMFCRibbonBaseElement::GetParentRibbonBar.md)|리본 요소에 대 한 상위 리본 표시줄을 검색합니다.|  
|[CMFCRibbonBaseElement::GetParentWnd](../Topic/CMFCRibbonBaseElement::GetParentWnd.md)|리본 요소에 대 한 부모 창을 검색합니다.|  
|[CMFCRibbonBaseElement::GetPressed](../Topic/CMFCRibbonBaseElement::GetPressed.md)|현재 사용자가 누를 경우에 리본 요소에 대 한 포인터를 검색 합니다.|  
|[CMFCRibbonBaseElement::GetQuickAccessToolBarID](../Topic/CMFCRibbonBaseElement::GetQuickAccessToolBarID.md)|빠른 실행 도구 모음에 있으면 리본 요소의 명령 ID를 검색 합니다.|  
|[CMFCRibbonBaseElement::GetRect](../Topic/CMFCRibbonBaseElement::GetRect.md)|리본 구성 요소의 경계 사각형을 반환합니다.|  
|[CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md)|일반 크기의 리본 요소를 반환합니다.|  
|[CMFCRibbonBaseElement::GetSize](../Topic/CMFCRibbonBaseElement::GetSize.md)|리본 구성 요소의 현재 크기를 반환합니다.|  
|[CMFCRibbonBaseElement::GetText](../Topic/CMFCRibbonBaseElement::GetText.md)|리본 요소와 연결 된 텍스트를 반환 합니다.|  
|[CMFCRibbonBaseElement::GetToolTipText](../Topic/CMFCRibbonBaseElement::GetToolTipText.md)|리본 구성 요소의 도구 설명 텍스트를 반환합니다.|  
|[CMFCRibbonBaseElement::GetTopLevelRibbonBar](../Topic/CMFCRibbonBaseElement::GetTopLevelRibbonBar.md)|리본 요소에 대 한 최상위 수준 리본 표시줄을 검색합니다.|  
|[CMFCRibbonBaseElement::HasCompactMode](../Topic/CMFCRibbonBaseElement::HasCompactMode.md)|리본 요소 컴팩트 모드에 있는지 여부를 지정 합니다.|  
|[CMFCRibbonBaseElement::HasFocus](../Topic/CMFCRibbonBaseElement::HasFocus.md)|부모 요소에 키보드 포커스가 있는지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::HasIntermediateMode](../Topic/CMFCRibbonBaseElement::HasIntermediateMode.md)|리본 요소 중간 모드에 있는지 여부를 지정 합니다.|  
|[CMFCRibbonBaseElement::HasLargeMode](../Topic/CMFCRibbonBaseElement::HasLargeMode.md)|리본 요소 큰 모드에 있는지 여부를 지정 합니다.|  
|[CMFCRibbonBaseElement::HasMenu](../Topic/CMFCRibbonBaseElement::HasMenu.md)|리본 요소에 메뉴가 있는지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::HitTest](../Topic/CMFCRibbonBaseElement::HitTest.md)|지정 된 위치에 있는 경우에 리본 요소에 대 한 포인터를 검색 합니다.|  
|[CMFCRibbonBaseElement::IsAlignByColumn](../Topic/CMFCRibbonBaseElement::IsAlignByColumn.md)|리본 요소 다른 리본 요소를 세로로 정렬할지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::IsAlwaysLargeImage](../Topic/CMFCRibbonBaseElement::IsAlwaysLargeImage.md)|리본 요소 이미지 크기가 항상 큰 인지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::IsAutoRepeatMode](../Topic/CMFCRibbonBaseElement::IsAutoRepeatMode.md)|리본 요소 자동 반복 모드 인지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::IsChecked](../Topic/CMFCRibbonBaseElement::IsChecked.md)|리본 요소 선택 되어 있는지 여부를 지정 합니다.|  
|[CMFCRibbonBaseElement::IsCompactMode](../Topic/CMFCRibbonBaseElement::IsCompactMode.md)|리본 요소는 압축 모드에 있는지 여부를 지정 합니다.|  
|[CMFCRibbonBaseElement::IsDefaultMenuLook](../Topic/CMFCRibbonBaseElement::IsDefaultMenuLook.md)||  
|[CMFCRibbonBaseElement::IsDisabled](../Topic/CMFCRibbonBaseElement::IsDisabled.md)|리본 요소를 사용할 수 있는지 여부를 지정 합니다.|  
|[CMFCRibbonBaseElement::IsDroppedDown](../Topic/CMFCRibbonBaseElement::IsDroppedDown.md)|리본 요소 팝업 메뉴 표시 펼친 여부가 결정 됩니다.|  
|[CMFCRibbonBaseElement::IsFocused](../Topic/CMFCRibbonBaseElement::IsFocused.md)|리본 요소에 포커스가 있는지 여부를 지정 합니다.|  
|[CMFCRibbonBaseElement::IsGalleryIcon](../Topic/CMFCRibbonBaseElement::IsGalleryIcon.md)|리본 요소 리본 갤러리에 포함 되어 있는지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::IsHighlighted](../Topic/CMFCRibbonBaseElement::IsHighlighted.md)|리본 요소를 강조 표시 하는지 여부를 지정 합니다.|  
|[CMFCRibbonBaseElement::IsIntermediateMode](../Topic/CMFCRibbonBaseElement::IsIntermediateMode.md)|현재 이미지는 리본 요소에 대 한 중간 크기 인지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::IsLargeMode](../Topic/CMFCRibbonBaseElement::IsLargeMode.md)|큰 리본 요소에는 현재 이미지 크기의 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::IsMenuMode](../Topic/CMFCRibbonBaseElement::IsMenuMode.md)|리본 요소를 메뉴에 포함 되어 있는지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::IsPressed](../Topic/CMFCRibbonBaseElement::IsPressed.md)|사용자가 리본 요소 클릭 했는지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::IsQATMode](../Topic/CMFCRibbonBaseElement::IsQATMode.md)|리본 요소는 빠른 실행 도구 모음에 포함 되어 있는지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::IsSeparator](../Topic/CMFCRibbonBaseElement::IsSeparator.md)|리본 요소 구분 기호 표시 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::IsShowGroupBorder](../Topic/CMFCRibbonBaseElement::IsShowGroupBorder.md)|리본 요소가 공통 테두리 표시 그룹에 포함 되어 있는지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::IsShowTooltipOnBottom](../Topic/CMFCRibbonBaseElement::IsShowTooltipOnBottom.md)|리본 요소에 도구 설명을 표시할지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::IsTabStop](../Topic/CMFCRibbonBaseElement::IsTabStop.md)|키보드로 리본 요소를 선택할 수 있는지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::IsTextAlwaysOnRight](../Topic/CMFCRibbonBaseElement::IsTextAlwaysOnRight.md)|리본 요소에 대 한 텍스트의 오른쪽에 표시 되는지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::IsVisible](../Topic/CMFCRibbonBaseElement::IsVisible.md)|리본 요소를 현재 표시 되는지 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::IsWholeRowHeight](../Topic/CMFCRibbonBaseElement::IsWholeRowHeight.md)|리본 요소 표시 heigth 포함 리본 패널의 디스플레이 높이 동일 여부를 나타냅니다.|  
|[CMFCRibbonBaseElement::NotifyCommand](../Topic/CMFCRibbonBaseElement::NotifyCommand.md)|명령 알림을 리본 요소의 부모 창에 보냅니다.|  
|[CMFCRibbonBaseElement::NotifyHighlightListItem](../Topic/CMFCRibbonBaseElement::NotifyHighlightListItem.md)|사용자 목록에 있는 경우 리본 요소가 강조 표시 되 면 리본 막대의 부모 창을 알립니다.|  
|[CMFCRibbonBaseElement::OnAddToQAToolbar](../Topic/CMFCRibbonBaseElement::OnAddToQAToolbar.md)|리본 요소에 지정 된 빠른 실행 도구 모음에 추가합니다.|  
|[CMFCRibbonBaseElement::OnAfterChangeRect](../Topic/CMFCRibbonBaseElement::OnAfterChangeRect.md)|리본 요소에 대 한 도구 설명을 업데이트합니다.|  
|[CMFCRibbonBaseElement::OnAutoRepeat](../Topic/CMFCRibbonBaseElement::OnAutoRepeat.md)|지속적인된 사용자 입력에는 리본 요소를 업데이트합니다.|  
|[CMFCRibbonBaseElement::OnCalcTextSize](../Topic/CMFCRibbonBaseElement::OnCalcTextSize.md)|리본 요소에 대 한 텍스트의 크기를 계산합니다.|  
|[CMFCRibbonBaseElement::OnChangeMenuHighlight](../Topic/CMFCRibbonBaseElement::OnChangeMenuHighlight.md)|있는 메뉴에는 리본 요소에 대 한 강조를 변경 하면 프레임 워크에서 호출 됩니다.|  
|[CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md)|리본 요소를 그리려면 프레임 워크에서 호출 됩니다.|  
|[CMFCRibbonBaseElement::OnDrawKeyTip](../Topic/CMFCRibbonBaseElement::OnDrawKeyTip.md)|Keytip 리본 요소를 그리려면 프레임 워크에서 호출 합니다.|  
|[CMFCRibbonBaseElement::OnDrawMenuImage](../Topic/CMFCRibbonBaseElement::OnDrawMenuImage.md)|리본 요소에 대 한 메뉴 이미지를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCRibbonBaseElement::OnDrawOnList](../Topic/CMFCRibbonBaseElement::OnDrawOnList.md)|명령 목록 상자에서 리본 요소를 그리려면 프레임 워크에서 호출 합니다.|  
|[CMFCRibbonBaseElement::OnKey](../Topic/CMFCRibbonBaseElement::OnKey.md)|프레임 워크에서 사용자 keytip 리본 요소에 포커스가 있을 때 호출 됩니다.|  
|[CMFCRibbonBaseElement::OnMenuKey](../Topic/CMFCRibbonBaseElement::OnMenuKey.md)||  
|[CMFCRibbonBaseElement::OnRTLChanged](../Topic/CMFCRibbonBaseElement::OnRTLChanged.md)|레이아웃의 방향을 변경 하면 프레임 워크에서 호출 됩니다.|  
|[CMFCRibbonBaseElement::OnShow](../Topic/CMFCRibbonBaseElement::OnShow.md)|표시 하거나 숨기려면 리본 요소 프레임 워크에서 호출 됩니다.|  
|[CMFCRibbonBaseElement::OnShowPopupMenu](../Topic/CMFCRibbonBaseElement::OnShowPopupMenu.md)|리본 요소 팝업 메뉴에 표시 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCRibbonBaseElement::PostMenuCommand](../Topic/CMFCRibbonBaseElement::PostMenuCommand.md)||  
|[CMFCRibbonBaseElement::Redraw](../Topic/CMFCRibbonBaseElement::Redraw.md)|리본 요소에 대 한 표시를 업데이트합니다.|  
|[CMFCRibbonBaseElement::SetACCData](../Topic/CMFCRibbonBaseElement::SetACCData.md)|리본 요소에 대 한 내게 필요한 옵션 데이터를 설정합니다.|  
|[CMFCRibbonBaseElement::SetCompactMode](../Topic/CMFCRibbonBaseElement::SetCompactMode.md)|리본 요소에 대 한 표시 크기를 설정합니다.|  
|[CMFCRibbonBaseElement::SetData](../Topic/CMFCRibbonBaseElement::SetData.md)|데이터 항목에는 리본 요소와 연결합니다.|  
|[CMFCRibbonBaseElement::SetDefaultMenuLook](../Topic/CMFCRibbonBaseElement::SetDefaultMenuLook.md)||  
|[CMFCRibbonBaseElement::SetDescription](../Topic/CMFCRibbonBaseElement::SetDescription.md)|리본 요소에 대 한 설명을 설정합니다.|  
|[CMFCRibbonBaseElement::SetID](../Topic/CMFCRibbonBaseElement::SetID.md)|리본 요소의 명령 ID를 설정 합니다.|  
|[CMFCRibbonBaseElement::SetInitialMode](../Topic/CMFCRibbonBaseElement::SetInitialMode.md)|리본 요소에 대 한 초기 표시 크기를 설정합니다.|  
|[CMFCRibbonBaseElement::SetKeys](../Topic/CMFCRibbonBaseElement::SetKeys.md)|Keytip 리본 요소에 대 한 설정입니다.|  
|[CMFCRibbonBaseElement::SetOriginal](../Topic/CMFCRibbonBaseElement::SetOriginal.md)|원래 리본 요소는 리본 요소에 대 한 설정합니다.|  
|[CMFCRibbonBaseElement::SetParentCategory](../Topic/CMFCRibbonBaseElement::SetParentCategory.md)|리본 요소에 대 한 상위 범주를 설정 합니다.|  
|[CMFCRibbonBaseElement::SetParentMenu](../Topic/CMFCRibbonBaseElement::SetParentMenu.md)|부모 요소의 리본 메뉴 컨테이너를 설정합니다.|  
|[CMFCRibbonBaseElement::SetParentRibbonBar](../Topic/CMFCRibbonBaseElement::SetParentRibbonBar.md)|리본 요소에 대 한 상위 리본 표시줄을 설정합니다.|  
|[CMFCRibbonBaseElement::SetRect](../Topic/CMFCRibbonBaseElement::SetRect.md)|그 표시는 리본 요소에 대 한 사각형의 치수 fot을 설정 합니다.|  
|[CMFCRibbonBaseElement::SetText](../Topic/CMFCRibbonBaseElement::SetText.md)|리본 요소에 대 한 텍스트를 설정합니다.|  
|[CMFCRibbonBaseElement::SetTextAlwaysOnRight](../Topic/CMFCRibbonBaseElement::SetTextAlwaysOnRight.md)|리본 요소의 오른쪽에 표시할 텍스트를 설정 합니다.|  
|[CMFCRibbonBaseElement::SetToolTipText](../Topic/CMFCRibbonBaseElement::SetToolTipText.md)|리본 요소에 대 한 도구 설명 텍스트를 설정합니다.|  
|[CMFCRibbonBaseElement::SetVisible](../Topic/CMFCRibbonBaseElement::SetVisible.md)|리본 구성 요소의 표시 상태를 설정합니다.|  
|[CMFCRibbonBaseElement::StretchHorizontally](../Topic/CMFCRibbonBaseElement::StretchHorizontally.md)|리본 구성 요소의 너비를 늘립니다.|  
|[CMFCRibbonBaseElement::StretchToWholeRow](../Topic/CMFCRibbonBaseElement::StretchToWholeRow.md)|디스플레이 높이 리본 요소를 지정 된 행 높이를 변경합니다.|  
|[CMFCRibbonBaseElement::UpdateTooltipInfo](../Topic/CMFCRibbonBaseElement::UpdateTooltipInfo.md)|리본 요소에 대 한 명령 리소스를 사용 하 여 도구 설명 텍스트를 업데이트 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonBaseElement::OnProcessKey](../Topic/CMFCRibbonBaseElement::OnProcessKey.md)|바로 가기 키를 누를 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCRibbonBaseElement::OnSetFocus](../Topic/CMFCRibbonBaseElement::OnSetFocus.md)|리본 요소를 받거나 입력된 포커스를 잃을 때 프레임 워크에 의해 호출 됩니다.|  
  
## 설명  
 `CMFCRibbonBaseElement` 클래스 초점, 강조 표시, 누를, 비활성화, 옵션을 선택 하거나 수 내려가면\) 상태 \(명령 ID, 텍스트 레이블, 도구 설명 텍스트 및 요소의 설명을 포함 하는 모든 리본 요소에 공통 된 속성을 정의 합니다.  
  
 이미지 크기의 리본 요소에 의해 정의 됩니다의 `RibbonImageType` 멤버는 다음 값 중 하나일 수 있습니다.  
  
-   `RibbonImageLarge`  
  
-   `RibbonImageSmall`  
  
 크기에 따라 리본 요소 중 하나는 작은 또는 큰 이미지를 표시합니다.  
  
## 예제  
 다음 예제에서는 다양 한 방법에 있는 `CMFCRibbonBaseElement` 클래스입니다.  예제를 가져오는 방법을 보여 줍니다.는 `CMFCRibbonBaseElement` 에서 개체는 `CMFCRibbonStatusBar` 클래스는 리본 요소에 대 한 설명을 설정, 텍스트 설정, keytip을 설정 하 고 리본 요소에 대 한 도구 설명 텍스트를 설정 합니다.  이 코드 조각에 속하지는  [그릴 클라이언트 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#8](../../mfc/reference/codesnippet/CPP/cmfcribbonbaseelement-class_1.cpp)]  
[!code-cpp[NVC_MFC_DrawClient#9](../../mfc/reference/codesnippet/CPP/cmfcribbonbaseelement-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
## 요구 사항  
 **헤더:** afxbaseribbonelement.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)