---
title: "CMFCToolBarComboBoxButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBarComboBoxButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarComboBoxButton class"
ms.assetid: 32fa39f7-8e4e-4f0a-a31d-7b540d969a6c
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCToolBarComboBoxButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

콤보 상자 컨트롤과 도구 모음 단추 \([CComboBox Class](../../mfc/reference/ccombobox-class.md)\).  
  
## 구문  
  
```  
class CMFCToolBarComboBoxButton : public CMFCToolBarButton  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton](../Topic/CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton.md)|`CMFCToolBarComboBoxButton`를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarComboBoxButton::AddItem](../Topic/CMFCToolBarComboBoxButton::AddItem.md)|콤보 상자 목록의 끝에 항목을 추가합니다.|  
|[CMFCToolBarComboBoxButton::AddSortedItem](../Topic/CMFCToolBarComboBoxButton::AddSortedItem.md)|콤보 상자 목록에 항목을 추가합니다.  목록에서 항목의 순서를 지정한 `Compare`.|  
|[CMFCToolBarComboBoxButton::Compare](../Topic/CMFCToolBarComboBoxButton::Compare.md)|두 항목을 비교합니다.  라는 정렬할 항목 `AddSortedItems` 콤보 상자 목록에 추가 합니다.|  
|[CMFCToolBarComboBoxButton::CreateEdit](../Topic/CMFCToolBarComboBoxButton::CreateEdit.md)|새 편집 컨트롤을 콤보 상자 단추를 만듭니다.|  
|[CMFCToolBarComboBoxButton::DeleteItem](../Topic/CMFCToolBarComboBoxButton::DeleteItem.md)|콤보 상자 목록에서 항목을 삭제합니다.|  
|[CMFCToolBarComboBoxButton::FindItem](../Topic/CMFCToolBarComboBoxButton::FindItem.md)|지정 된 문자열에 들어 있는 항목의 인덱스를 반환 합니다.|  
|[CMFCToolBarComboBoxButton::GetByCmd](../Topic/CMFCToolBarComboBoxButton::GetByCmd.md)|콤보 상자 단추에 지정 된 명령 ID에 대 한 포인터를 반환|  
|[CMFCToolBarComboBoxButton::GetComboBox](../Topic/CMFCToolBarComboBoxButton::GetComboBox.md)|콤보 상자 단추에 포함 된 콤보 상자 컨트롤에 대 한 포인터를 반환 합니다.|  
|[CMFCToolBarComboBoxButton::GetCount](../Topic/CMFCToolBarComboBoxButton::GetCount.md)|항목에서 콤보 상자 목록을 반환합니다.|  
|[CMFCToolBarComboBoxButton::GetCountAll](../Topic/CMFCToolBarComboBoxButton::GetCountAll.md)|콤보 상자 단추에 지정 된 명령 ID가 발견  단추 목록 상자 콤보에서 항목 수를 반환합니다.|  
|[CMFCToolBarComboBoxButton::GetCurSel](../Topic/CMFCToolBarComboBoxButton::GetCurSel.md)|선택한 항목의 인덱스에 있는 콤보 상자 목록을 반환합니다.|  
|[CMFCToolBarComboBoxButton::GetCurSelAll](../Topic/CMFCToolBarComboBoxButton::GetCurSelAll.md)|콤보 상자 단추를 지정 된 명령 ID가 해당 단추 목록 상자 콤보에서 선택한 항목의 인덱스를 반환 하 고 찾습니다.|  
|[CMFCToolBarComboBoxButton::GetEditCtrl](../Topic/CMFCToolBarComboBoxButton::GetEditCtrl.md)|콤보 상자 단추에 포함 된 편집 컨트롤에 대 한 포인터를 반환 합니다.|  
|[CMFCToolBarComboBoxButton::GetItem](../Topic/CMFCToolBarComboBoxButton::GetItem.md)|목록 상자에서 콤보 상자에서 지정 된 인덱스와 연결 된 문자열을 반환 합니다.|  
|[CMFCToolBarComboBoxButton::GetItemAll](../Topic/CMFCToolBarComboBoxButton::GetItemAll.md)|콤보 상자 단추를 지정 된 명령 ID가 콤보 상자 목록의 해당 단추의 인덱스와 연관 된 문자열을 반환 하 고 찾습니다.|  
|[CMFCToolBarComboBoxButton::GetItemData](../Topic/CMFCToolBarComboBoxButton::GetItemData.md)|목록 상자에서 콤보 상자에서 지정 된 인덱스와 연관 된 32 비트 값을 반환 합니다.|  
|[CMFCToolBarComboBoxButton::GetItemDataAll](../Topic/CMFCToolBarComboBoxButton::GetItemDataAll.md)|콤보 상자 단추를 지정 된 명령 ID가 콤보 상자 목록의 해당 단추의 인덱스와 연관 된 32 비트 값을 반환 하 고 찾습니다.|  
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](../Topic/CMFCToolBarComboBoxButton::GetItemDataPtrAll.md)|콤보 상자 단추에 지정 된 명령 ID가 발견  검색 32 비트 값을 32 비트 값을 포인터로 반환 하 고 해당 단추를 콤보 상자 목록에서 인덱스 관련.|  
|[CMFCToolBarComboBoxButton::GetText](../Topic/CMFCToolBarComboBoxButton::GetText.md)|콤보 상자의 편집 컨트롤에서 텍스트를 반환합니다.|  
|[CMFCToolBarComboBoxButton::GetTextAll](../Topic/CMFCToolBarComboBoxButton::GetTextAll.md)|콤보 상자 단추를 지정 된 명령 ID가 단추 편집 컨트롤에서 텍스트를 반환 하 고 찾습니다.|  
|[CMFCToolBarComboBoxButton::IsCenterVert](../Topic/CMFCToolBarComboBoxButton::IsCenterVert.md)|응용 프로그램에서 콤보 상자 단추를 가운데 맞춤 또는 도구 모음의 위쪽에 맞춥니다 있는지 결정 합니다.|  
|[CMFCToolBarComboBoxButton::IsFlatMode](../Topic/CMFCToolBarComboBoxButton::IsFlatMode.md)|응용 프로그램에서 콤보 상자 단추를 평면 모양 있는지 여부를 결정 합니다.|  
|[CMFCToolBarComboBoxButton::RemoveAllItems](../Topic/CMFCToolBarComboBoxButton::RemoveAllItems.md)|모든 항목의 목록에서 상자 및 콤보 상자 컨트롤 편집 제거 합니다.|  
|[CMFCToolBarComboBoxButton::SelectItem](../Topic/CMFCToolBarComboBoxButton::SelectItem.md)|해당 인덱스, 32 비트 값 또는 문자열에 따라 콤보 상자에서 항목을 선택 하 고 선택 영역에 대 한 콤보 상자 컨트롤에 알립니다.|  
|[CMFCToolBarComboBoxButton::SelectItemAll](../Topic/CMFCToolBarComboBoxButton::SelectItemAll.md)|콤보 상자 단추에 지정 된 명령 ID가 발견  호출 `SelectItem` 해당 단추를 해당 문자열, 인덱스, 또는 32 비트 값에 따라 콤보 상자에서 항목을 선택 합니다.|  
|[CMFCToolBarComboBoxButton::SetCenterVert](../Topic/CMFCToolBarComboBoxButton::SetCenterVert.md)|응용 프로그램에서 콤보 상자 단추를 세로 가운데 맞춤 또는 도구 모음의 위쪽에 맞춥니다 있는지 여부를 지정 합니다.|  
|[CMFCToolBarComboBoxButton::SetDropDownHeight](../Topic/CMFCToolBarComboBoxButton::SetDropDownHeight.md)|드롭다운 목록 상자의 높이를 설정합니다.|  
|[CMFCToolBarComboBoxButton::SetFlatMode](../Topic/CMFCToolBarComboBoxButton::SetFlatMode.md)|응용 프로그램에서 콤보 상자 단추를 평면 모양 있는지 여부를 지정 합니다.|  
  
## 설명  
 도구 모음에 콤보 상자 단추를 추가 하려면 다음과이 같이 하십시오.  
  
 1.  부모 리소스 도구 모음 단추에 대 한 더미 리소스 ID를 예약 합니다.  
  
 2.  `CMFCToolBarComboBoxButton` 개체를 생성합니다.  
  
 3.  처리 된 메시지 처리기에서는 `AFX_WM_RESETTOOLBAR` 메시지, 새 콤보 상자 단추를 사용 하 여 더미 단추를 대체 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md).  
  
 자세한 내용은 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)를 참조하십시오.  콤보 상자 도구 모음 단추에 대 한 예제에서는 VisualStudioDemo 예제 프로젝트를 참조 하십시오.  
  
## 예제  
 다음 예제에서는 다양 한 방법에 있는 `CMFCToolBarComboBoxButton` 클래스입니다.  편집 및 콤보 상자를 사용 하 고, 세로 위치를 콤보 상자 단추에서 응용 프로그램 설정, 아래로 놓을 때 응용 프로그램에서 콤보 상자 단추의 평면 스타일 모양을 설정 하 고 콤보 상자 단추 편집 상자에 텍스트를 설정 합니다. 목록 상자의 높이 설정 하는 예제를 보여 줍니다.  이 코드 조각에 속해 있는  [Visual Studio 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#36](../../mfc/codesnippet/CPP/cmfctoolbarcomboboxbutton-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#37](../../mfc/codesnippet/CPP/cmfctoolbarcomboboxbutton-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
## 요구 사항  
 **헤더:** afxtoolbarcomboboxbutton.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)