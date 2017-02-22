---
title: "CMFCPropertyGridCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPropertyGridCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridCtrl class"
  - "CMFCPropertyGridCtrl::accHitTest method"
  - "CMFCPropertyGridCtrl::accLocation method"
  - "CMFCPropertyGridCtrl::get_accChild method"
  - "CMFCPropertyGridCtrl::get_accDefaultAction method"
  - "CMFCPropertyGridCtrl::get_accDescription method"
  - "CMFCPropertyGridCtrl::get_accName method"
  - "CMFCPropertyGridCtrl::get_accRole method"
  - "CMFCPropertyGridCtrl::get_accState method"
  - "CMFCPropertyGridCtrl::get_accValue method"
  - "CMFCPropertyGridCtrl::PreTranslateMessage method"
ms.assetid: 95877cae-2311-4a2a-9031-0c8c3cf0a5f9
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMFCPropertyGridCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 속성 사전순 또는 계층적 순서로 표시할 수 있는 편집 가능한 속성 표 컨트롤을 지원 합니다.  
  
## 구문  
  
```  
class CMFCPropertyGridCtrl : public CWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCPropertyGridCtrl::CMFCPropertyGridCtrl](../Topic/CMFCPropertyGridCtrl::CMFCPropertyGridCtrl.md)|`CMFCPropertyGridCtrl` 개체를 생성합니다.|  
|`CMFCPropertyGridCtrl::~CMFCPropertyGridCtrl`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|`CMFCPropertyGridCtrl::accHitTest`|자식 요소나 자식 개체를 화면에 특정 시점을 검색 하는 프레임 워크에서 호출 합니다.  \(재정의 [CWnd::accHitTest](../Topic/CWnd::accHitTest.md).\)|  
|`CMFCPropertyGridCtrl::accLocation`|지정한 개체의 현재 화면 위치를 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::accLocation](../Topic/CWnd::accLocation.md).\)|  
|[CMFCPropertyGridCtrl::accSelect](../Topic/CMFCPropertyGridCtrl::accSelect.md)|선택 영역을 수정 하거나 지정한 개체의 키보드 포커스를 이동 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::accSelect](../Topic/CWnd::accSelect.md).\)|  
|[CMFCPropertyGridCtrl::AddProperty](../Topic/CMFCPropertyGridCtrl::AddProperty.md)|속성 표 컨트롤에 새 속성을 추가 합니다.|  
|[CMFCPropertyGridCtrl::AlwaysShowUserToolTip](../Topic/CMFCPropertyGridCtrl::AlwaysShowUserToolTip.md)||  
|[CMFCPropertyGridCtrl::CloseColorPopup](../Topic/CMFCPropertyGridCtrl::CloseColorPopup.md)|색 선택 대화 상자를 닫습니다.|  
|[CMFCPropertyGridCtrl::Create](../Topic/CMFCPropertyGridCtrl::Create.md)|속성 표 컨트롤을 만들고 속성 표 컨트롤 개체를 연결 합니다.|  
|[CMFCPropertyGridCtrl::DeleteProperty](../Topic/CMFCPropertyGridCtrl::DeleteProperty.md)|속성 표 컨트롤에서 지정한 속성을 삭제합니다.|  
|[CMFCPropertyGridCtrl::DrawControlBarColors](../Topic/CMFCPropertyGridCtrl::DrawControlBarColors.md)||  
|[CMFCPropertyGridCtrl::EnableDescriptionArea](../Topic/CMFCPropertyGridCtrl::EnableDescriptionArea.md)|속성 목록 아래에 표시 되는 설명 영역을 사용할 수 있거나.|  
|[CMFCPropertyGridCtrl::EnableHeaderCtrl](../Topic/CMFCPropertyGridCtrl::EnableHeaderCtrl.md)|속성 표 컨트롤의 맨 위에 있는 머리글 컨트롤을 사용할 수 있거나.|  
|[CMFCPropertyGridCtrl::EnsureVisible](../Topic/CMFCPropertyGridCtrl::EnsureVisible.md)|속성 표 컨트롤 스크롤하여 지정 된 속성이 표시 될 때까지 속성 항목을 확장 합니다.|  
|[CMFCPropertyGridCtrl::ExpandAll](../Topic/CMFCPropertyGridCtrl::ExpandAll.md)|확장 또는 모든 속성 표 컨트롤 노드를 축소 합니다.|  
|[CMFCPropertyGridCtrl::FindItemByData](../Topic/CMFCPropertyGridCtrl::FindItemByData.md)|사용자 정의에 관련 된 속성을 검색 `DWORD` 값입니다.|  
|`CMFCPropertyGridCtrl::get_accChild`|주소를 검색 하는 프레임 워크에서 호출 된 `IDispatch` 지정 된 자식에 대 한 인터페이스.  \(재정의 [CWnd::get\_accChild](../Topic/CWnd::get_accChild.md).\)|  
|[CMFCPropertyGridCtrl::get\_accChildCount](../Topic/CMFCPropertyGridCtrl::get_accChildCount.md)|이 개체에 속한 자식의 수를 검색 하는 프레임 워크에서 호출 합니다.  \(재정의 [CWnd::get\_accChildCount](../Topic/CWnd::get_accChildCount.md).\)|  
|`CMFCPropertyGridCtrl::get_accDefaultAction`|개체의 기본 동작을 설명 하는 문자열을 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accDefaultAction](../Topic/CWnd::get_accDefaultAction.md).\)|  
|`CMFCPropertyGridCtrl::get_accDescription`|지정한 개체의 시각적 모양을 설명 하는 문자열을 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accDescription](../Topic/CWnd::get_accDescription.md).\)|  
|[CMFCPropertyGridCtrl::get\_accFocus](../Topic/CMFCPropertyGridCtrl::get_accFocus.md)|키보드 포커스를 갖는 개체를 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accFocus](../Topic/CWnd::get_accFocus.md).\)|  
|[CMFCPropertyGridCtrl::get\_accHelp](../Topic/CMFCPropertyGridCtrl::get_accHelp.md)|검색할 개체의 프레임 워크에서 호출 `Help` 속성의 문자열입니다.  \(재정의 [CWnd::get\_accHelp](../Topic/CWnd::get_accHelp.md).\)|  
|[CMFCPropertyGridCtrl::get\_accHelpTopic](../Topic/CMFCPropertyGridCtrl::get_accHelpTopic.md)|전체 경로를 검색 하는 프레임 워크에서 호출을 `WinHelp`지정 된 개체와 해당 파일 내에서 해당 항목의 식별자와 관련 된 파일.  \(재정의 [CWnd::get\_accHelpTopic](../Topic/CWnd::get_accHelpTopic.md).\)|  
|[CMFCPropertyGridCtrl::get\_accKeyboardShortcut](../Topic/CMFCPropertyGridCtrl::get_accKeyboardShortcut.md)|검색은 지정 된 개체의 바로 가기 키 또는 선택 키를 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accKeyboardShortcut](../Topic/CWnd::get_accKeyboardShortcut.md).\)|  
|`CMFCPropertyGridCtrl::get_accName`|지정한 개체의 이름을 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accName](../Topic/CWnd::get_accName.md).\)|  
|`CMFCPropertyGridCtrl::get_accRole`|지정 된 개체의 역할을 설명 하는 정보를 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accRole](../Topic/CWnd::get_accRole.md).\)|  
|[CMFCPropertyGridCtrl::get\_accSelection](../Topic/CMFCPropertyGridCtrl::get_accSelection.md)|이 개체의 선택된 된 자식 개체를 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accSelection](../Topic/CWnd::get_accSelection.md).\)|  
|`CMFCPropertyGridCtrl::get_accState`|지정한 개체의 현재 상태를 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accState](../Topic/CWnd::get_accState.md).\)|  
|`CMFCPropertyGridCtrl::get_accValue`|지정 된 개체의 값을 검색 하는 프레임 워크에서 호출 됩니다.  \(재정의 [CWnd::get\_accValue](../Topic/CWnd::get_accValue.md).\)|  
|[CMFCPropertyGridCtrl::GetBkColor](../Topic/CMFCPropertyGridCtrl::GetBkColor.md)|현재 속성 표 컨트롤의 배경 색을 검색합니다.|  
|[CMFCPropertyGridCtrl::GetBoldFont](../Topic/CMFCPropertyGridCtrl::GetBoldFont.md)|현재 속성 표에서 텍스트를 굵은 스타일으로 제어 Windows 글꼴을 검색 합니다.|  
|[CMFCPropertyGridCtrl::GetCurSel](../Topic/CMFCPropertyGridCtrl::GetCurSel.md)|현재 선택된 된 속성을 검색합니다.|  
|[CMFCPropertyGridCtrl::GetCustomColors](../Topic/CMFCPropertyGridCtrl::GetCustomColors.md)|속성 표 형태 컨트롤 요소에 대해 현재 정의 되어 있는 사용자 지정 색을 검색 합니다.|  
|[CMFCPropertyGridCtrl::GetDescriptionHeight](../Topic/CMFCPropertyGridCtrl::GetDescriptionHeight.md)|속성 표 컨트롤의 아래쪽에 있는 설명 영역의 높이 검색 합니다.|  
|[CMFCPropertyGridCtrl::GetDescriptionRows](../Topic/CMFCPropertyGridCtrl::GetDescriptionRows.md)|현재 속성 표 컨트롤의 설명 영역에서 행 개수를 검색합니다.|  
|[CMFCPropertyGridCtrl::GetHeaderCtrl](../Topic/CMFCPropertyGridCtrl::GetHeaderCtrl.md)|내부 검색  [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) 개체 프레임 워크 사용 현재 속성 표 컨트롤을 표시 합니다.|  
|[CMFCPropertyGridCtrl::GetHeaderHeight](../Topic/CMFCPropertyGridCtrl::GetHeaderHeight.md)|속성 표 컨트롤 머리글의 높이 검색합니다.|  
|[CMFCPropertyGridCtrl::GetLeftColumnWidth](../Topic/CMFCPropertyGridCtrl::GetLeftColumnWidth.md)|왼쪽된 열에는 각 속성의 이름을 포함 하는 현재 속성 표 컨트롤의 너비를 검색 합니다.|  
|[CMFCPropertyGridCtrl::GetListRect](../Topic/CMFCPropertyGridCtrl::GetListRect.md)|속성 표 컨트롤의 경계 사각형을 검색합니다.|  
|[CMFCPropertyGridCtrl::GetProperty](../Topic/CMFCPropertyGridCtrl::GetProperty.md)|속성 표 컨트롤 항목의 지정 된 인덱스에 해당 하는 property 개체에 대 한 포인터를 검색 합니다.|  
|[CMFCPropertyGridCtrl::GetPropertyColumnWidth](../Topic/CMFCPropertyGridCtrl::GetPropertyColumnWidth.md)|속성 값이 포함 된 열의 현재 너비를 검색 합니다.|  
|[CMFCPropertyGridCtrl::GetPropertyCount](../Topic/CMFCPropertyGridCtrl::GetPropertyCount.md)|속성 표 컨트롤에서 속성을 검색합니다.|  
|[CMFCPropertyGridCtrl::GetRowHeight](../Topic/CMFCPropertyGridCtrl::GetRowHeight.md)|속성 표 컨트롤에 있는 행의 높이 검색합니다.|  
|[CMFCPropertyGridCtrl::GetScrollBarCtrl](../Topic/CMFCPropertyGridCtrl::GetScrollBarCtrl.md)|속성 표 컨트롤에서 스크롤 막대 컨트롤에 대 한 포인터를 검색합니다.  \(재정의 [CWnd::GetScrollBarCtrl](../Topic/CWnd::GetScrollBarCtrl.md).\)|  
|[CMFCPropertyGridCtrl::GetTextColor](../Topic/CMFCPropertyGridCtrl::GetTextColor.md)|현재 속성 표 컨트롤에서 속성 항목의 텍스트 색을 검색합니다.|  
|`CMFCPropertyGridCtrl::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCPropertyGridCtrl::HitTest](../Topic/CMFCPropertyGridCtrl::HitTest.md)|지정 된 항목의 경우 속성 표 컨트롤 항목에 해당 하는 속성 개체에 대 한 포인터를 검색 합니다.  이 메서드 또한 지점을 포함 하는 속성 표 컨트롤에서 영역을 나타냅니다.|  
|[CMFCPropertyGridCtrl::InitHeader](../Topic/CMFCPropertyGridCtrl::InitHeader.md)|내부 초기화  [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) 개체 프레임 워크 사용 현재 속성 표 컨트롤을 표시 합니다.|  
|[CMFCPropertyGridCtrl::IsAlphabeticMode](../Topic/CMFCPropertyGridCtrl::IsAlphabeticMode.md)|속성 표 컨트롤에서 알파벳 모드 인지 여부를 나타냅니다.|  
|[CMFCPropertyGridCtrl::IsAlwaysShowUserToolTip](../Topic/CMFCPropertyGridCtrl::IsAlwaysShowUserToolTip.md)||  
|[CMFCPropertyGridCtrl::IsDescriptionArea](../Topic/CMFCPropertyGridCtrl::IsDescriptionArea.md)|설명 영역 속성 표 컨트롤의 표시 여부를 나타냅니다.|  
|[CMFCPropertyGridCtrl::IsGroupNameFullWidth](../Topic/CMFCPropertyGridCtrl::IsGroupNameFullWidth.md)|현재 속성 표 컨트롤의 너비에 각 속성 그룹 이름 표시 여부를 나타냅니다.|  
|[CMFCPropertyGridCtrl::IsHeaderCtrl](../Topic/CMFCPropertyGridCtrl::IsHeaderCtrl.md)|헤더 컨트롤을 표시할지 여부를 나타냅니다.|  
|[CMFCPropertyGridCtrl::IsMarkModifiedProperties](../Topic/CMFCPropertyGridCtrl::IsMarkModifiedProperties.md)|수정 된 속성 속성 표 컨트롤에 표시 되는 방식을 나타냅니다.|  
|[CMFCPropertyGridCtrl::IsShowDragContext](../Topic/CMFCPropertyGridCtrl::IsShowDragContext.md)|사용자가 열의 크기를 조정할 때 현재 속성 표 컨트롤의 이름 및 값 열 프레임 워크를 다시 그리는지 여부를 나타냅니다.|  
|[CMFCPropertyGridCtrl::IsVSDotNetLook](../Topic/CMFCPropertyGridCtrl::IsVSDotNetLook.md)|VS.net에서 사용 되는 스타일 속성 표 컨트롤의 모양 인지 여부를 나타냅니다.|  
|[CMFCPropertyGridCtrl::MarkModifiedProperties](../Topic/CMFCPropertyGridCtrl::MarkModifiedProperties.md)|수정 된 속성을 표시 하는 방법을 지정 합니다.|  
|`CMFCPropertyGridCtrl::PreTranslateMessage`|클래스에 의해 사용 되는  [CWinApp](../../mfc/reference/cwinapp-class.md) 창 메시지를 디스패치하기 전에 변환 하는  [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및  [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 기능.  \(재정의 [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMFCPropertyGridCtrl::RemoveAll](../Topic/CMFCPropertyGridCtrl::RemoveAll.md)|속성 표 컨트롤에서 속성의 모든 개체를 제거합니다.|  
|[CMFCPropertyGridCtrl::ResetOriginalValues](../Topic/CMFCPropertyGridCtrl::ResetOriginalValues.md)|모든 속성의 원래 값을 복원합니다.|  
|[CMFCPropertyGridCtrl::SetAlphabeticMode](../Topic/CMFCPropertyGridCtrl::SetAlphabeticMode.md)|설정 하거나 알파벳 모드를 다시 설정 합니다.|  
|[CMFCPropertyGridCtrl::SetBoolLabels](../Topic/CMFCPropertyGridCtrl::SetBoolLabels.md)|부울 레이블 텍스트를 지정합니다.|  
|[CMFCPropertyGridCtrl::SetCurSel](../Topic/CMFCPropertyGridCtrl::SetCurSel.md)|속성 표 컨트롤에서 속성을 선택 합니다.|  
|[CMFCPropertyGridCtrl::SetCustomColors](../Topic/CMFCPropertyGridCtrl::SetCustomColors.md)|다양 한 속성 표 컨트롤 요소에 대 한 사용자 지정 색을 지정합니다.|  
|[CMFCPropertyGridCtrl::SetDescriptionRows](../Topic/CMFCPropertyGridCtrl::SetDescriptionRows.md)|설명 섹션의 현재 속성 표 컨트롤에 표시할 행 수를 지정 합니다.|  
|[CMFCPropertyGridCtrl::SetGroupNameFullWidth](../Topic/CMFCPropertyGridCtrl::SetGroupNameFullWidth.md)|그룹 속성에 대해 범주 이름의 전체 너비 현재 속성 표 컨트롤에 표시할지 여부를 지정 합니다.|  
|[CMFCPropertyGridCtrl::SetListDelimiter](../Topic/CMFCPropertyGridCtrl::SetListDelimiter.md)|속성 값의 목록에서 구분 기호로 사용할 문자를 정의 합니다.|  
|[CMFCPropertyGridCtrl::SetShowDragContext](../Topic/CMFCPropertyGridCtrl::SetShowDragContext.md)|사용자가 열의 크기를 조정할 때 현재 속성 표 컨트롤의 이름 및 값 열 프레임 워크를 다시 그리는지 여부를 지정 합니다.|  
|[CMFCPropertyGridCtrl::SetVSDotNetLook](../Topic/CMFCPropertyGridCtrl::SetVSDotNetLook.md)|VS.net에 사용 되는 스타일 속성 표 컨트롤의 모양을 설정 합니다.|  
|[CMFCPropertyGridCtrl::UpdateColor](../Topic/CMFCPropertyGridCtrl::UpdateColor.md)|현재 선택한 색 속성 색 값을 설정합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCPropertyGridCtrl::AdjustLayout](../Topic/CMFCPropertyGridCtrl::AdjustLayout.md)|속성 및 속성 표 컨트롤을 다시 그립니다.|  
|[CMFCPropertyGridCtrl::CompareProps](../Topic/CMFCPropertyGridCtrl::CompareProps.md)|속성 표 컨트롤에서 속성을 정렬 하려면 호출 됩니다.|  
|[CMFCPropertyGridCtrl::EditItem](../Topic/CMFCPropertyGridCtrl::EditItem.md)|사용자 속성을 수정 하려면 시작할 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCPropertyGridCtrl::EndEditItem](../Topic/CMFCPropertyGridCtrl::EndEditItem.md)|사용자 속성 수정 중지 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCPropertyGridCtrl::Init](../Topic/CMFCPropertyGridCtrl::Init.md)|속성 표 컨트롤을 초기화 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCPropertyGridCtrl::OnChangeSelection](../Topic/CMFCPropertyGridCtrl::OnChangeSelection.md)|현재 선택 영역이 변경 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCPropertyGridCtrl::OnClickButton](../Topic/CMFCPropertyGridCtrl::OnClickButton.md)|속성 단추를 클릭 하면 프레임 워크에서 호출 됩니다.|  
|[CMFCPropertyGridCtrl::OnDrawBorder](../Topic/CMFCPropertyGridCtrl::OnDrawBorder.md)|속성 표 컨트롤 주위에 테두리를 그리려면 프레임 워크에서 호출 합니다.|  
|[CMFCPropertyGridCtrl::OnDrawDescription](../Topic/CMFCPropertyGridCtrl::OnDrawDescription.md)|설명 영역 그리고 설명 텍스트를 표시 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCPropertyGridCtrl::OnDrawList](../Topic/CMFCPropertyGridCtrl::OnDrawList.md)|속성 표 컨트롤의 속성 목록을 표시 하는 프레임 워크에서 호출 합니다.|  
|[CMFCPropertyGridCtrl::OnDrawProperty](../Topic/CMFCPropertyGridCtrl::OnDrawProperty.md)|속성을 표시 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCPropertyGridCtrl::OnPropertyChanged](../Topic/CMFCPropertyGridCtrl::OnPropertyChanged.md)|속성의 값이 변경 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCPropertyGridCtrl::OnSelectCombo](../Topic/CMFCPropertyGridCtrl::OnSelectCombo.md)|콤보 상자 컨트롤을 포함 하는 속성을 선택 하면 프레임 워크에서 호출 됩니다.|  
|[CMFCPropertyGridCtrl::ValidateItemData](../Topic/CMFCPropertyGridCtrl::ValidateItemData.md)|속성 데이터의 유효성 검사 프레임 워크에서 호출 됩니다.|  
  
## 설명  
 `CMFCPropertyGridCtrl` 클래스에서 파생 되는 편집 가능한 속성을 포함 한 속성 표 컨트롤 표시는  [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md) 클래스.  각 속성 형식을 나타내고 하위 항목이 포함 될 수 있습니다.  속성 표 컨트롤의 크기 조정 가능한 영역 아래쪽에서 선택한 속성의 설명을 표시할 수 있습니다 지원 합니다.  
  
 구성 속성 표 컨트롤을 사용 하는 `CMFCPropertyGridCtrl` 다음 호출 및 개체의 [CMFCPropertyGridCtrl::Create](../Topic/CMFCPropertyGridCtrl::Create.md) 메서드.  사용 된 [CMFCPropertyGridCtrl::AddProperty](../Topic/CMFCPropertyGridCtrl::AddProperty.md) 메서드 속성 목록에 추가 합니다.  
  
## 선택 속성  
 속성 항목 값을 나타내는 대신, 색상, 파일 또는 글꼴을 선택할 수 있도록 대화 상자를 시작할 수 있습니다.  
  
 다음 표에서 네 가지 선택 속성 형식을 보여 줍니다.  
  
|클래스|설명|  
|---------|--------|  
|[CMFCPropertyGridProperty Class](../../mfc/reference/cmfcpropertygridproperty-class.md)|값의 문자열, 부울, 날짜를 지정 하는 데 사용 되는 범용 속성입니다.|  
|[CMFCPropertyGridColorProperty Class](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)|색상 값을 선택 하는 데 사용 되는 속성입니다.|  
|[CMFCPropertyGridFileProperty Class](../../mfc/reference/cmfcpropertygridfileproperty-class.md)|파일을 선택 하는 데 사용 되는 속성입니다.|  
|[CMFCPropertyGridFontProperty Class](../../mfc/reference/cmfcpropertygridfontproperty-class.md)|글꼴을 선택 하는 데 사용 되는 속성입니다.|  
  
## 그림  
 다음 그림에서는 두 가지 방법으로 속성 표시 속성 표 컨트롤을 나타냅니다.  첫 그림 등록 정보를 계층 구조적으로 표시 하 고 두 번째 속성을 사전순으로 표시 합니다.  
  
 ![속성 목록 PropertySheet](../../mfc/reference/media/proplist.png "PropList")  
  
## 예제  
 다음 예제에서는 속성 표 컨트롤 개체에서 여러 메서드를 사용 하 여 구성 된 `CMFCPropertyGridCtrl` 클래스.  머리글 컨트롤을 사용 하 고, 설명 영역 활성화 하 고 속성 표 컨트롤의 모양을 설정 하는 예제입니다.  또한 예제 컨트롤은 컨트롤 정렬 알파벳 모드 해당 속성 이름을 포함 하는 모든 속성을 설정 하는 방법 및 속성 표 컨트롤의 다양 한 요소에 대 한 사용자 지정 색을 설정 하는 방법을 보여 줍니다.  이 이때의 일부인의  [새 컨트롤 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#14](../../mfc/reference/codesnippet/CPP/cmfcpropertygridctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#16](../../mfc/reference/codesnippet/CPP/cmfcpropertygridctrl-class_2.cpp)]  
[!code-cpp[NVC_MFC_NewControls#20](../../mfc/reference/codesnippet/CPP/cmfcpropertygridctrl-class_3.cpp)]  
[!code-cpp[NVC_MFC_NewControls#21](../../mfc/reference/codesnippet/CPP/cmfcpropertygridctrl-class_4.cpp)]  
[!code-cpp[NVC_MFC_NewControls#24](../../mfc/reference/codesnippet/CPP/cmfcpropertygridctrl-class_5.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)  
  
## 요구 사항  
 **헤더:** afxpropertygridctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)