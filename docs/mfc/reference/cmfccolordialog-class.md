---
title: "CMFCColorDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCColorDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorDialog class"
  - "CMFCColorDialog::m_bIsMyPalette data member"
  - "CMFCColorDialog::m_bPickerMode data member"
  - "CMFCColorDialog::m_btnColorSelect data member"
  - "CMFCColorDialog::m_CurrentColor data member"
  - "CMFCColorDialog::m_hcurPicker data member"
  - "CMFCColorDialog::m_NewColor data member"
  - "CMFCColorDialog::m_pColourSheetOne data member"
  - "CMFCColorDialog::m_pColourSheetTwo data member"
  - "CMFCColorDialog::m_pPalette data member"
  - "CMFCColorDialog::m_pPropSheet data member"
  - "CMFCColorDialog::m_wndColors data member"
  - "CMFCColorDialog::m_wndStaticPlaceHolder data member"
  - "CMFCColorDialog::PreTranslateMessage method"
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCColorDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCColorDialog` 클래스는 색 선택 대화 상자를 나타냅니다.  
  
## 구문  
  
```  
class CMFCColorDialog : public CDialogEx  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCColorDialog::CMFCColorDialog](../Topic/CMFCColorDialog::CMFCColorDialog.md)|`CMFCColorDialog` 개체를 생성합니다.|  
|`CMFCColorDialog::~CMFCColorDialog`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCColorDialog::GetColor](../Topic/CMFCColorDialog::GetColor.md)|현재 선택한 색을 반환합니다.|  
|[CMFCColorDialog::GetPalette](../Topic/CMFCColorDialog::GetPalette.md)|색상표의 색을 반환합니다.|  
|`CMFCColorDialog::PreTranslateMessage`|창 메시지를 디스패치하기 전에 변환의  [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및  [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 기능입니다.  구문 및 자세한 정보를 참조 하십시오. [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).  \(재정의 `CDialogEx::PreTranslateMessage`.\)|  
|[CMFCColorDialog::RebuildPalette](../Topic/CMFCColorDialog::RebuildPalette.md)|색상표를 시스템 색상표에서 파생 됩니다.|  
|[CMFCColorDialog::SetCurrentColor](../Topic/CMFCColorDialog::SetCurrentColor.md)|현재 선택한 색을 설정합니다.|  
|[CMFCColorDialog::SetNewColor](../Topic/CMFCColorDialog::SetNewColor.md)|가장 해당 하는 RGB 값으로 지정 된 색을 설정합니다.|  
|[CMFCColorDialog::SetPageOne](../Topic/CMFCColorDialog::SetPageOne.md)|첫 번째 속성 페이지에 대 한 RGB 값을 선택합니다.|  
|[CMFCColorDialog::SetPageTwo](../Topic/CMFCColorDialog::SetPageTwo.md)|두 번째 속성 페이지에 대 한 RGB 값을 선택합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|`m_bIsMyPalette`|`TRUE`고유한 색상표 색 선택 대화 상자를 사용 하는 경우 또는 `FALSE` 지정 된 색상표 대화 상자를 사용 하는 경우는 `CMFCColorDialog` 생성자입니다.|  
|`m_bPickerMode`|`TRUE`색 선택 대화 상자에서 사용자를 선택 하는 동안. 그렇지 않으면 `FALSE`.|  
|`m_btnColorSelect`|사용자가 선택한 색 단추입니다.|  
|`m_CurrentColor`|현재 선택한 색입니다.|  
|`m_hcurPicker`|색을 선택 하는 데 사용 되는 커서입니다.|  
|`m_NewColor`|잠재 된 영구적으로 선택 하거나 수 원래 색으로 되돌릴 색상을 선택 합니다.|  
|`m_pColourSheetOne`|색 선택 속성 시트의 첫 번째 속성 페이지에 대 한 포인터입니다.|  
|`m_pColourSheetTwo`|색 선택 속성 시트의 두 번째 속성 페이지에 대 한 포인터입니다.|  
|`m_pPalette`|현재 논리 색상표입니다.|  
|`m_pPropSheet`|색 선택 대화 상자에 대 한 속성 시트에 대 한 포인터입니다.|  
|`m_wndColors`|색상 선택기 컨트롤 개체입니다.|  
|`m_wndStaticPlaceHolder`|정적 컨트롤 색 선택 속성 시트에 대 한 자리 표시자입니다.|  
  
## 설명  
 색 선택 대화 상자는 속성 시트를 두 표시 됩니다.  첫 번째 페이지에 시스템 팔레트에서 표준 색을 선택합니다. 두 번째 페이지에서 사용자 지정 색을 선택합니다.  
  
 생성할 수 있습니다는 `CMFCColorDialog` 하 고 호출 스택에 있는 개체 `DoModal`, 초기 색상을 매개 변수로 전달 된 `CMFCColorDialog` 생성자.  색 선택 대화 상자는 다음 몇 가지 만듭니다 [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md) 각 색상표 처리 하는 개체입니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## 예제  
 다음 예제에서는 다양 한 메서드를 사용 하 여 색 대화 상자를 구성 하는 방법의 `CMFCColorDialog` 클래스입니다.  예제 현재와의 대화 상자에서 새 색을 설정 하는 방법 및 색상 대화의 두 속성 페이지에 선택한 색의 빨강, 녹색 및 파랑 구성 요소를 설정 하는 방법을 보여 줍니다.  이 이때의 일부인의  [새 컨트롤 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/CPP/cmfccolordialog-class_1.cpp)]  
  
## 요구 사항  
 **헤더:** afxcolordialog.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md)