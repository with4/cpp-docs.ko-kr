---
title: "CMFCToolBarsCustomizeDialog Class | Microsoft Docs"
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
  - "CMFCToolBarsCustomizeDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarsCustomizeDialog class"
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
caps.latest.revision: 28
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarsCustomizeDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

모덜리스 탭 대화 상자 \([CPropertySheet Class](../../mfc/reference/cpropertysheet-class.md)\) 사용자 도구 모음, 메뉴, 바로 가기 키, 도구, 사용자 정의 및 응용 프로그램에서 비주얼 스타일을 정의할 수 있습니다.  일반적으로 사용자가 선택 하 여이 대화 상자 액세스  **사용자 지정** 에서  **도구** 메뉴.  
  
 **사용자 지정** 대화 상자 여섯 개의 탭이 있습니다:  **명령**,  **도구 모음**,  **도구**,  **키보드**,  **메뉴**, 및  **옵션**.  
  
## 구문  
  
```  
class CMFCToolBarsCustomizeDialog : public CPropertySheet  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](../Topic/CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog.md)|`CMFCToolBarsCustomizeDialog` 개체를 생성합니다.|  
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddButton](../Topic/CMFCToolBarsCustomizeDialog::AddButton.md)|명령 목록에 도구 모음 단추를 삽입에  **명령** 페이지|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenu](../Topic/CMFCToolBarsCustomizeDialog::AddMenu.md)|메뉴 리소스 및 호출에서 로드 [CMFCToolBarsCustomizeDialog::AddMenuCommands](../Topic/CMFCToolBarsCustomizeDialog::AddMenuCommands.md) 해당 메뉴 명령 목록에 추가 하는  **명령** 페이지.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenuCommands](../Topic/CMFCToolBarsCustomizeDialog::AddMenuCommands.md)|메뉴 리소스 및 호출에서 로드 [CMFCToolBarsCustomizeDialog::AddMenuCommands](../Topic/CMFCToolBarsCustomizeDialog::AddMenuCommands.md) 해당 메뉴 명령 목록에 추가 하는  **명령** 페이지.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddToolBar](../Topic/CMFCToolBarsCustomizeDialog::AddToolBar.md)|도구 모음에서 리소스를 로드합니다.  각 메뉴 호출에서 명령 다음의 [CMFCToolBarsCustomizeDialog::AddButton](../Topic/CMFCToolBarsCustomizeDialog::AddButton.md) 명령 목록에서 단추를 삽입 하는 메서드는  **명령** 페이지에 지정한 범주 아래.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::Create](../Topic/CMFCToolBarsCustomizeDialog::Create.md)|표시는  **사용자 지정** 대화 상자.|  
|`CMFCToolBarsCustomizeDialog::EnableTools`|다음에 사용하도록 예약됩니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](../Topic/CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars.md)|활성화 또는 비활성화를 사용 하 여 새 도구 모음 만들기를  **사용자 지정** 대화 상자.|  
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](../Topic/CMFCToolBarsCustomizeDialog::FillAllCommandsList.md)|제공 된 채웁니다 `CListBox` 명령에서 개체의  **모든 명령** 을 범주.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](../Topic/CMFCToolBarsCustomizeDialog::FillCategoriesComboBox.md)|제공 된 채웁니다 `CComboBox` 개체의 각 명령 범주에서 이름으로는  **사용자 지정** 대화 상자.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](../Topic/CMFCToolBarsCustomizeDialog::FillCategoriesListBox.md)|제공 된 채웁니다 `CListBox` 개체의 각 명령 범주에서 이름으로는  **사용자 지정** 대화 상자.|  
|[CMFCToolBarsCustomizeDialog::GetCommandName](../Topic/CMFCToolBarsCustomizeDialog::GetCommandName.md)|지정 된 명령 ID와 관련 된 이름을 검색 합니다.|  
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](../Topic/CMFCToolBarsCustomizeDialog::GetCountInCategory.md)|지정 된 텍스트 레이블을 제공 된 목록에서 항목을 검색 합니다.|  
|[CMFCToolBarsCustomizeDialog::GetFlags](../Topic/CMFCToolBarsCustomizeDialog::GetFlags.md)|동작 대화 상자에 영향을 주는 플래그 집합을 검색 합니다.|  
|`CMFCToolBarsCustomizeDialog::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](../Topic/CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage.md)|사용자가 도구 모음 단추 또는 메뉴 항목 아이콘을 사용자 지정할 수 있도록 이미지 편집기를 시작 합니다.|  
|[CMFCToolBarsCustomizeDialog::OnInitDialog](../Topic/CMFCToolBarsCustomizeDialog::OnInitDialog.md)|속성 시트를 초기화를 확대 하도록 재정의 합니다.  \(재정의 [CPropertySheet::OnInitDialog](../Topic/CPropertySheet::OnInitDialog.md).\)|  
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](../Topic/CMFCToolBarsCustomizeDialog::PostNcDestroy.md)|프레임 워크에 의해 창이 소멸 된 후에 호출 됩니다.  \(재정의 `CPropertySheet::PostNcDestroy`.\)|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RemoveButton](../Topic/CMFCToolBarsCustomizeDialog::RemoveButton.md)|지정 된 명령 ID 사용 하 여 단추에 지정 된 범주 또는 모든 범주를 제거합니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RenameCategory](../Topic/CMFCToolBarsCustomizeDialog::RenameCategory.md)|범주 범주 목록 상자에서에서 변경의  **명령** 탭.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md)|명령 목록에서 단추에 대체는  **명령** 탭이 새 도구 모음 단추 개체.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::SetUserCategory](../Topic/CMFCToolBarsCustomizeDialog::SetUserCategory.md)|범주 추가 목록에 표시 되는 범주는  **명령** 탭.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::CheckToolsValidity](../Topic/CMFCToolBarsCustomizeDialog::CheckToolsValidity.md)|사용자 정의 도구 목록이 유효한 지 여부를 결정 하는 프레임 워크에서 호출 됩니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAfterChangeTool](../Topic/CMFCToolBarsCustomizeDialog::OnAfterChangeTool.md)|사용자 정의 도구 속성을 변경 하면 프레임 워크에서 호출 됩니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAssignKey](../Topic/CMFCToolBarsCustomizeDialog::OnAssignKey.md)|액션에 지정 된 바로 가기 키를 할당할 수 여부를 결정 합니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](../Topic/CMFCToolBarsCustomizeDialog::OnBeforeChangeTool.md)|사용자 정의 도구를 변경할 수 있는지 여부를 결정 합니다.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnInitToolsPage](../Topic/CMFCToolBarsCustomizeDialog::OnInitToolsPage.md)|사용자를 선택 하면 프레임 워크에서 호출을  **도구** 탭 요청 합니다.|  
  
## 설명  
 표시 하는  **사용자 지정** 대화 상자에서 만들기는 `CMFCToolBarsCustomizeDialog` 호출 및 개체의 [CMFCToolBarsCustomizeDialog::Create](../Topic/CMFCToolBarsCustomizeDialog::Create.md) 메서드.  
  
 동안에  **사용자 지정** 활성화 되어 대화 상자, 응용 프로그램 사용자가 사용자 지정 작업을 제한 하는 특수 모드에서 작동 합니다.  
  
## 예제  
 다음 예제에서는 다양 한 방법에 있는 `CMFCToolBarsCustomizeDialog` 클래스입니다.  도구 모음 단추 명령 목록 상자에서에 대체 하는 방법의 예제를 보여 줍니다 있는  **명령** 페이지에서 활성화를 사용 하 여 새 도구 모음 만들기는  **사용자 지정** 대화 상자를 표시 하 고는  **사용자 지정** 대화 상자.  이 코드 조각에 속해 있는  [IE 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/CPP/cmfctoolbarscustomizedialog-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCToolBarsCustomizeDialog](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)  
  
## 요구 사항  
 **헤더:** afxToolBarsCustomizeDialog.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPropertySheet Class](../../mfc/reference/cpropertysheet-class.md)