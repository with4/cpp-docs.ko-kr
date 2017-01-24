---
title: "CMFCColorPickerCtrl Class | Microsoft Docs"
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
  - "CMFCColorPickerCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorPickerCtrl class"
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
caps.latest.revision: 33
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorPickerCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCColorPickerCtrl` 클래스 색상을 선택 하는 데 사용 되는 컨트롤에 대 한 기능을 제공 합니다.  
  
## 구문  
  
```  
class CMFCColorPickerCtrl : public CButton  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](../Topic/CMFCColorPickerCtrl::CMFCColorPickerCtrl.md)|`CMFCColorPickerCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCColorPickerCtrl::GetColor](../Topic/CMFCColorPickerCtrl::GetColor.md)|사용자가 선택한 색을 검색 합니다.|  
|[CMFCColorPickerCtrl::GetHLS](../Topic/CMFCColorPickerCtrl::GetHLS.md)|사용자가 선택한 색의 색조, 광도 및 채도 값을 검색 합니다.|  
|[CMFCColorPickerCtrl::GetHue](../Topic/CMFCColorPickerCtrl::GetHue.md)|사용자가 선택한 색의 색상 구성 요소를 검색 합니다.|  
|[CMFCColorPickerCtrl::GetLuminance](../Topic/CMFCColorPickerCtrl::GetLuminance.md)|사용자가 선택한 색의 광도 구성 요소를 검색 합니다.|  
|[CMFCColorPickerCtrl::GetSaturation](../Topic/CMFCColorPickerCtrl::GetSaturation.md)|사용자가 선택한 색의 채도 구성 요소를 검색 합니다.|  
|[CMFCColorPickerCtrl::SelectCellHexagon](../Topic/CMFCColorPickerCtrl::SelectCellHexagon.md)|지정 된 RGB 색 구성 요소 또는 지정 된 셀 육각형으로 정의 된 색을 현재 색을 설정 합니다.|  
|[CMFCColorPickerCtrl::SetColor](../Topic/CMFCColorPickerCtrl::SetColor.md)|현재 색상 지정 된 RGB 색상 값으로 설정합니다.|  
|[CMFCColorPickerCtrl::SetHLS](../Topic/CMFCColorPickerCtrl::SetHLS.md)|현재 색상 HLS 색을 지정한 값으로 설정합니다.|  
|[CMFCColorPickerCtrl::SetHue](../Topic/CMFCColorPickerCtrl::SetHue.md)|현재 선택된 된 색상의 색상 구성 요소를 변경합니다.|  
|[CMFCColorPickerCtrl::SetLuminance](../Topic/CMFCColorPickerCtrl::SetLuminance.md)|현재 선택된 된 색상의 광도 구성 요소를 변경합니다.|  
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](../Topic/CMFCColorPickerCtrl::SetLuminanceBarWidth.md)|색상 선택기 컨트롤에서 광도 막대의 너비를 설정합니다.|  
|[CMFCColorPickerCtrl::SetOriginalColor](../Topic/CMFCColorPickerCtrl::SetOriginalColor.md)|초기 선택된 된 색을 설정합니다.|  
|[CMFCColorPickerCtrl::SetPalette](../Topic/CMFCColorPickerCtrl::SetPalette.md)|현재 색상표를 설정합니다.|  
|[CMFCColorPickerCtrl::SetSaturation](../Topic/CMFCColorPickerCtrl::SetSaturation.md)|현재 선택한 색의 채도 구성 요소를 변경합니다.|  
|[CMFCColorPickerCtrl::SetType](../Topic/CMFCColorPickerCtrl::SetType.md)|색 선택 컨트롤을 표시 하는 형식을 설정 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCColorPickerCtrl::DrawCursor](../Topic/CMFCColorPickerCtrl::DrawCursor.md)|선택한 색을 가리키는 커서를 표시 하기 전에 프레임 워크에서 호출 됩니다.|  
  
## 설명  
 육각 색상표에서 색 선택 및 광도 표시줄에서 사용자 지정 색 선택 색 표시법 빨간색\/녹색\/파랑 또는 광도\/색조\/satuaration 표시법을 사용 하 여 지정 된 위치입니다.  
  
 다음 그림에서는 몇 가지 보여 줍니다 `CMFCColorPickerCtrl` 개체입니다.  
  
 ![CMFCColorPickerCtrl 대화 상자](../../mfc/reference/media/colorpicker.png "ColorPicker")  
  
 `CMFCColorPickerCtrl` 두 쌍의 스타일을 지원 합니다.  16 진수 및 HEX\_GREYSCALE 스타일 표준 색상 선택에 대 한 적절 한입니다.  선택 및 광도 스타일에 대 한 사용자 지정 색 선택 됩니다.  
  
 통합 하려면 다음 단계를 수행의 `CMFCColorPickerCtrl` 컨트롤을 대화 상자에.  
  
1.  사용 하는 경우는  **클래스 마법사**, 새 단추 컨트롤을 대화 상자 템플릿에 삽입 \(때문에 `CMFCColorPickerCtrl` 클래스에서 상속 되는 `CButton` 클래스\).  
  
2.  새 단추 컨트롤과 연결 된 대화 상자 클래스에 멤버 변수를 삽입 합니다.  다음 변수 형식에서 변경 `CButton` 에 `CMFCColorPickerCtrl`.  
  
3.  삽입 된 `WM_INITDIALOG` 대화 상자 클래스에 메시지 처리기입니다.  처리기에서 형식, 색상표, 및 초기 선택한 색의 설정의 `CMFCColorPickerCtrl` 제어 합니다.  
  
## 예제  
 구성 하는 방법 다음 예제는 `CMFCColorPickerCtrl` 의 다양 한 메서드를 사용 하 여 개체의 `CMFCColorPickerCtrl` 클래스.  선택 컨트롤의 종류를 설정 하는 방법 및 색상, 색조, 광도 및 채도 설정 하는 예제입니다.  일부인 예제는  [새 컨트롤 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/CPP/cmfccolorpickerctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/CPP/cmfccolorpickerctrl-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)  
  
## 요구 사항  
 **헤더:** afxcolorpickerctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md)