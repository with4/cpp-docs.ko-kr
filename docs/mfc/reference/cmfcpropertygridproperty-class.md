---
title: "CMFCPropertyGridProperty Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPropertyGridProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridProperty class"
ms.assetid: 36f3fabe-0efe-468b-8a0b-5a7956db38a2
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMFCPropertyGridProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

A `CMFCPropertyGridProperty` 개체 속성 목록 컨트롤에서 목록 항목을 나타냅니다.  
  
## 구문  
  
```  
class CMFCPropertyGridProperty : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCPropertyGridProperty::CMFCPropertyGridProperty](../Topic/CMFCPropertyGridProperty::CMFCPropertyGridProperty.md)|`CMFCPropertyGridProperty` 개체를 생성합니다.|  
|`CMFCPropertyGridProperty::~CMFCPropertyGridProperty`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCPropertyGridProperty::AddOption](../Topic/CMFCPropertyGridProperty::AddOption.md)|속성 목록 컨트롤에 새 목록 항목을 추가합니다.|  
|[CMFCPropertyGridProperty::AddSubItem](../Topic/CMFCPropertyGridProperty::AddSubItem.md)|자식 항목 속성에 추가합니다.|  
|[CMFCPropertyGridProperty::AdjustButtonRect](../Topic/CMFCPropertyGridProperty::AdjustButtonRect.md)|사각형이 포함 단추의 크기를 조정 하려면 속성을 알리려면 부모 속성 목록 컨트롤에서 호출 합니다.|  
|[CMFCPropertyGridProperty::AdjustInPlaceEditRect](../Topic/CMFCPropertyGridProperty::AdjustInPlaceEditRect.md)|텍스트 상자 및 선택적 스핀 단추 컨트롤의 속성 값을 설정 하는 데 사용 되는 경계를 검색 합니다.|  
|[CMFCPropertyGridProperty::AllowEdit](../Topic/CMFCPropertyGridProperty::AllowEdit.md)|편집 가능 또는 읽기 전용 속성을 만듭니다.|  
|[CMFCPropertyGridProperty::CreateInPlaceEdit](../Topic/CMFCPropertyGridProperty::CreateInPlaceEdit.md)|편집 가능한 컨트롤에 대 한 속성을 만들려면 프레임 워크에서 호출 합니다.|  
|[CMFCPropertyGridProperty::CreateSpinControl](../Topic/CMFCPropertyGridProperty::CreateSpinControl.md)|편집 가능한 스핀 단추 컨트롤을 만들려면 프레임 워크에서 호출 됩니다.|  
|[CMFCPropertyGridProperty::Enable](../Topic/CMFCPropertyGridProperty::Enable.md)|속성을 사용할 수 있거나.|  
|[CMFCPropertyGridProperty::EnableSpinControl](../Topic/CMFCPropertyGridProperty::EnableSpinControl.md)|속성 값을 수정 하는 데 사용 되는 스핀 단추 컨트롤을 사용할 수 있거나.|  
|[CMFCPropertyGridProperty::Expand](../Topic/CMFCPropertyGridProperty::Expand.md)|확장 또는 축소 하위 속성을 포함 하는 속성입니다.|  
|[CMFCPropertyGridProperty::FormatProperty](../Topic/CMFCPropertyGridProperty::FormatProperty.md)|속성 값의 텍스트 표현과 서식을 지정합니다.|  
|[CMFCPropertyGridProperty::GetData](../Topic/CMFCPropertyGridProperty::GetData.md)|검색은 `DWORD` 속성과 관련 된 값입니다.|  
|[CMFCPropertyGridProperty::GetDescription](../Topic/CMFCPropertyGridProperty::GetDescription.md)|속성 설명을 검색합니다.|  
|[CMFCPropertyGridProperty::GetExpandedSubItems](../Topic/CMFCPropertyGridProperty::GetExpandedSubItems.md)|확장 된 하위 항목을 검색합니다.|  
|[CMFCPropertyGridProperty::GetHierarchyLevel](../Topic/CMFCPropertyGridProperty::GetHierarchyLevel.md)|계층 구조 수준에서 속성의 인덱스를 검색합니다.|  
|[CMFCPropertyGridProperty::GetName](../Topic/CMFCPropertyGridProperty::GetName.md)|속성의 이름을 검색합니다.|  
|[CMFCPropertyGridProperty::GetNameTooltip](../Topic/CMFCPropertyGridProperty::GetNameTooltip.md)|도구 설명에 속성의 이름을 표시 하는 프레임 워크에서 호출 합니다.|  
|[CMFCPropertyGridProperty::GetOption](../Topic/CMFCPropertyGridProperty::GetOption.md)|인덱스에 의해 지정 된 옵션의 텍스트를 검색 합니다.|  
|[CMFCPropertyGridProperty::GetOptionCount](../Topic/CMFCPropertyGridProperty::GetOptionCount.md)|속성에 속하는 옵션을 검색 합니다.|  
|[CMFCPropertyGridProperty::GetOriginalValue](../Topic/CMFCPropertyGridProperty::GetOriginalValue.md)|현재 속성의 초기 값을 검색합니다.|  
|[CMFCPropertyGridProperty::GetParent](../Topic/CMFCPropertyGridProperty::GetParent.md)|Parent 속성에 대 한 포인터를 검색합니다.|  
|[CMFCPropertyGridProperty::GetRect](../Topic/CMFCPropertyGridProperty::GetRect.md)|속성의 경계 사각형을 검색합니다.|  
|[CMFCPropertyGridProperty::GetSubItem](../Topic/CMFCPropertyGridProperty::GetSubItem.md)|0부터 시작 인덱스로 식별 되는 하위 속성을 검색 합니다.|  
|[CMFCPropertyGridProperty::GetSubItemsCount](../Topic/CMFCPropertyGridProperty::GetSubItemsCount.md)|하위 항목을 검색합니다.|  
|`CMFCPropertyGridProperty::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCPropertyGridProperty::GetValue](../Topic/CMFCPropertyGridProperty::GetValue.md)|속성 값을 검색합니다.|  
|[CMFCPropertyGridProperty::GetValueTooltip](../Topic/CMFCPropertyGridProperty::GetValueTooltip.md)|다음 도구 설명에 표시 되는 속성 값의 텍스트 표현을 검색 하는 프레임 워크에서 호출 합니다.|  
|[CMFCPropertyGridProperty::HitTest](../Topic/CMFCPropertyGridProperty::HitTest.md)|해당 지점에 해당 속성이 목록 항목 속성 개체를 가리킵니다.|  
|[CMFCPropertyGridProperty::IsAllowEdit](../Topic/CMFCPropertyGridProperty::IsAllowEdit.md)|속성을 편집할 수 있는지 여부를 나타냅니다.|  
|[CMFCPropertyGridProperty::IsEnabled](../Topic/CMFCPropertyGridProperty::IsEnabled.md)|속성의 사용 여부를 나타냅니다.|  
|[CMFCPropertyGridProperty::IsExpanded](../Topic/CMFCPropertyGridProperty::IsExpanded.md)|속성의 확장 또는 축소 여부를 나타냅니다.|  
|[CMFCPropertyGridProperty::IsGroup](../Topic/CMFCPropertyGridProperty::IsGroup.md)|현재 속성 그룹을 나타내는지 여부를 나타냅니다.|  
|[CMFCPropertyGridProperty::IsInPlaceEditing](../Topic/CMFCPropertyGridProperty::IsInPlaceEditing.md)|현재 속성을 편집할 수 있는지 여부를 나타냅니다.|  
|[CMFCPropertyGridProperty::IsModified](../Topic/CMFCPropertyGridProperty::IsModified.md)|현재 속성이 수정 되었는지 여부를 나타냅니다.|  
|[CMFCPropertyGridProperty::IsParentExpanded](../Topic/CMFCPropertyGridProperty::IsParentExpanded.md)|현재 속성의 부모를 확장 하는지 여부를 나타냅니다.|  
|[CMFCPropertyGridProperty::IsSelected](../Topic/CMFCPropertyGridProperty::IsSelected.md)|현재 속성이 선택 되어 있는지 여부를 나타냅니다.|  
|[CMFCPropertyGridProperty::IsVisible](../Topic/CMFCPropertyGridProperty::IsVisible.md)|현재 속성이 표시 되는지 여부를 나타냅니다.|  
|[CMFCPropertyGridProperty::OnClickButton](../Topic/CMFCPropertyGridProperty::OnClickButton.md)|속성에 포함 된 단추를 클릭할 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCPropertyGridProperty::OnClickName](../Topic/CMFCPropertyGridProperty::OnClickName.md)|속성의 이름 필드를 클릭할 때 부모 속성 목록 컨트롤에서 호출 합니다.|  
|[CMFCPropertyGridProperty::OnClickValue](../Topic/CMFCPropertyGridProperty::OnClickValue.md)|속성의 값 필드를 클릭할 때 부모 속성 목록 컨트롤에서 호출 합니다.|  
|[CMFCPropertyGridProperty::OnCloseCombo](../Topic/CMFCPropertyGridProperty::OnCloseCombo.md)|속성에 포함 된 콤보 상자를 닫을 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCPropertyGridProperty::OnDblClk](../Topic/CMFCPropertyGridProperty::OnDblClk.md)|사용자 속성 두 번 클릭 하면 프레임 워크에서 호출 됩니다.|  
|[CMFCPropertyGridProperty::OnDrawButton](../Topic/CMFCPropertyGridProperty::OnDrawButton.md)|속성에 포함 된 단추를 그리려면 프레임 워크에서 호출 합니다.|  
|[CMFCPropertyGridProperty::OnDrawDescription](../Topic/CMFCPropertyGridProperty::OnDrawDescription.md)|속성 설명을 표시 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCPropertyGridProperty::OnDrawExpandBox](../Topic/CMFCPropertyGridProperty::OnDrawExpandBox.md)|확장 컨트롤 상자 하위 속성 포함 속성 근처 그리려면 프레임 워크에서 호출 합니다.|  
|[CMFCPropertyGridProperty::OnDrawName](../Topic/CMFCPropertyGridProperty::OnDrawName.md)|속성 이름을 표시 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCPropertyGridProperty::OnDrawValue](../Topic/CMFCPropertyGridProperty::OnDrawValue.md)|속성 값을 표시 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCPropertyGridProperty::OnEdit](../Topic/CMFCPropertyGridProperty::OnEdit.md)|사용자에 대 한 속성 값을 수정할 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCPropertyGridProperty::OnEndEdit](../Topic/CMFCPropertyGridProperty::OnEndEdit.md)|사용자가 완료 되 면 프레임 워크에서 호출 속성 값을 수정 합니다.|  
|[CMFCPropertyGridProperty::OnKillSelection](../Topic/CMFCPropertyGridProperty::OnKillSelection.md)||  
|[CMFCPropertyGridProperty::OnPosSizeChanged](../Topic/CMFCPropertyGridProperty::OnPosSizeChanged.md)||  
|[CMFCPropertyGridProperty::OnRClickName](../Topic/CMFCPropertyGridProperty::OnRClickName.md)|속성 이름 영역에서 마우스 오른쪽 단추를 클릭할 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCPropertyGridProperty::OnRClickValue](../Topic/CMFCPropertyGridProperty::OnRClickValue.md)|속성의 값 영역에서 마우스 오른쪽 단추를 클릭할 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCPropertyGridProperty::OnSelectCombo](../Topic/CMFCPropertyGridProperty::OnSelectCombo.md)|사용자는 편집 가능한 콤보 상자에서 항목을 선택 하면 프레임 워크에서 호출 됩니다.|  
|[CMFCPropertyGridProperty::OnSetCursor](../Topic/CMFCPropertyGridProperty::OnSetCursor.md)|속성 항목에 마우스 포인터를 이동할 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCPropertyGridProperty::OnSetSelection](../Topic/CMFCPropertyGridProperty::OnSetSelection.md)||  
|[CMFCPropertyGridProperty::OnUpdateValue](../Topic/CMFCPropertyGridProperty::OnUpdateValue.md)|편집 가능한 속성의 값을 변경 하면 프레임 워크에서 호출 됩니다.|  
|[CMFCPropertyGridProperty::PushChar](../Topic/CMFCPropertyGridProperty::PushChar.md)|속성 목록 컨트롤에서 속성을 선택 하 고 새 문자를 입력할 때 호출 됩니다.|  
|[CMFCPropertyGridProperty::Redraw](../Topic/CMFCPropertyGridProperty::Redraw.md)|속성을 다시 그립니다.|  
|[CMFCPropertyGridProperty::RemoveAllOptions](../Topic/CMFCPropertyGridProperty::RemoveAllOptions.md)|속성에서 모든 옵션 \(항목\)를 제거합니다.|  
|[CMFCPropertyGridProperty::RemoveSubItem](../Topic/CMFCPropertyGridProperty::RemoveSubItem.md)|지정 된 하위 항목을 제거합니다.|  
|[CMFCPropertyGridProperty::ResetOriginalValue](../Topic/CMFCPropertyGridProperty::ResetOriginalValue.md)|편집된 속성의 원래 값을 복원합니다.|  
|[CMFCPropertyGridProperty::SetData](../Topic/CMFCPropertyGridProperty::SetData.md)|연결 된 `DWORD` 속성 값입니다.|  
|[CMFCPropertyGridProperty::SetDescription](../Topic/CMFCPropertyGridProperty::SetDescription.md)|현재 속성에 설명 하는 텍스트를 지정 합니다.|  
|[CMFCPropertyGridProperty::SetName](../Topic/CMFCPropertyGridProperty::SetName.md)|속성 이름을 설정합니다.|  
|[CMFCPropertyGridProperty::SetOriginalValue](../Topic/CMFCPropertyGridProperty::SetOriginalValue.md)|편집 가능한 속성의 원래 값을 설정합니다.|  
|[CMFCPropertyGridProperty::SetValue](../Topic/CMFCPropertyGridProperty::SetValue.md)|속성 표에서 속성 값을 설정합니다.|  
|[CMFCPropertyGridProperty::Show](../Topic/CMFCPropertyGridProperty::Show.md)|표시 하거나 속성을 숨깁니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCPropertyGridProperty::CreateCombo](../Topic/CMFCPropertyGridProperty::CreateCombo.md)|콤보 상자 속성에 추가 하는 프레임 워크에서 호출 합니다.|  
|[CMFCPropertyGridProperty::HasButton](../Topic/CMFCPropertyGridProperty::HasButton.md)|속성 단추가 있는지 여부를 나타냅니다.|  
|[CMFCPropertyGridProperty::Init](../Topic/CMFCPropertyGridProperty::Init.md)|속성 개체를 초기화 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCPropertyGridProperty::IsSubItem](../Topic/CMFCPropertyGridProperty::IsSubItem.md)|지정 된 속성이 현재 속성의 하위 항목 인지 여부를 나타냅니다.|  
|[CMFCPropertyGridProperty::IsValueChanged](../Topic/CMFCPropertyGridProperty::IsValueChanged.md)|현재 속성 값이 변경 되었는지 여부를 나타냅니다.|  
|[CMFCPropertyGridProperty::OnCtlColor](../Topic/CMFCPropertyGridProperty::OnCtlColor.md)|배경색 속성의 채우기 브러시를 검색 해야 하는 경우 프레임 워크에서 호출 됩니다.|  
|[CMFCPropertyGridProperty::OnDestroyWindow](../Topic/CMFCPropertyGridProperty::OnDestroyWindow.md)|프레임 워크에서 속성이 소멸 또는 편집이 완료 될 때 호출 됩니다.|  
|[CMFCPropertyGridProperty::OnKillFocus](../Topic/CMFCPropertyGridProperty::OnKillFocus.md)|속성은 입력된 포커스를 잃었을 때 프레임 워크에 의해 호출 됩니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCPropertyGridProperty::m\_strFormatDouble](../Topic/CMFCPropertyGridProperty::m_strFormatDouble.md)|Double 형식의 값에 대 한 형식 문자열입니다.|  
|[CMFCPropertyGridProperty::m\_strFormatFloat](../Topic/CMFCPropertyGridProperty::m_strFormatFloat.md)|부동 소수점 형식의 값에 대 한 형식 문자열입니다.|  
|[CMFCPropertyGridProperty::m\_strFormatLong](../Topic/CMFCPropertyGridProperty::m_strFormatLong.md)|문자열 형식의 값에 대 한 긴 포맷 합니다.|  
|[CMFCPropertyGridProperty::m\_strFormatShort](../Topic/CMFCPropertyGridProperty::m_strFormatShort.md)|짧은 형식의 값에 대 한 형식 문자열입니다.|  
  
## 설명  
 사용 된 `CMFCPropertyGridProperty` 다음 목록 컨트롤에 속성을 추가 하는 속성을 나타내는 개체입니다.  자세한 내용은 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md)를 참조하십시오.  
  
 Property 개체는 데이터 형식 문자열, 날짜, 부울 또는 정수 값 등을 나타낼 수 있습니다.  자식 속성을 포함할 수 또는 단추 컨트롤 또는 콤보 상자와 같은 컨트롤을 포함할 수 있습니다.  
  
## 예제  
 다음 예제에서는 생성 한 `CMFCPropertyGridProperty` 개체.  예제 또한 다양 한 메서드를 사용 하는 방법을 보여 줍니다.를 `CMFCPropertyGridProperty` 클래스 옵션을 추가, 하위 항목을 추가, 속성을 사용 하 고 속성을 표시 합니다.  이 이때의 일부인의  [새 컨트롤 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#27](../../mfc/reference/codesnippet/CPP/cmfcpropertygridproperty-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
## 요구 사항  
 **헤더:** afxpropertygridctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md)