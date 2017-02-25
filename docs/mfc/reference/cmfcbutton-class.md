---
title: "CMFCButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCButton class"
  - "CMFCButton constructor"
  - "CMFCButton::CreateObject method"
  - "CMFCButton::DrawItem method"
  - "CMFCButton::OnDrawParentBackground method"
  - "CMFCButton::PreTranslateMessage method"
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMFCButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCButton` 클래스 추가 기능에는  [CButton](../../mfc/reference/cbutton-class.md) 맞춤 단추 텍스트 단추 텍스트와 이미지를 결합, 커서를 선택 하 고 도구 설명을 지정 하는 같은 클래스.  
  
## 구문  
  
```  
class CMFCButton : public CButton  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CMFCButton::CMFCButton`|기본 생성자입니다.|  
|`CMFCButton::~CMFCButton`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCButton::CleanUp](../Topic/CMFCButton::CleanUp.md)|내부 변수를 다시 설정 하 고 이미지, 비트맵 및 아이콘과 같은 할당 된 리소스를 해제 합니다.|  
|`CMFCButton::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|`CMFCButton::DrawItem`|소유자가 그린 단추의 시각적 측면이 변경 될 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CButton::DrawItem](../Topic/CButton::DrawItem.md).\)|  
|[CMFCButton::EnableFullTextTooltip](../Topic/CMFCButton::EnableFullTextTooltip.md)|큰 도구 설명 창 또는 잘라낸 텍스트 작은 도구 설명 창에 도구 설명에 전체 텍스트를 표시할지 여부를 지정 합니다.|  
|[CMFCButton::EnableMenuFont](../Topic/CMFCButton::EnableMenuFont.md)|동일한 응용 프로그램 글꼴 메뉴 단추 텍스트 글꼴 인지 여부를 지정 합니다.|  
|[CMFCButton::EnableWindowsTheming](../Topic/CMFCButton::EnableWindowsTheming.md)|단추 테두리의 스타일을 현재 Windows 테마에 해당 하는지 여부를 지정 합니다.|  
|`CMFCButton::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCButton::GetToolTipCtrl](../Topic/CMFCButton::GetToolTipCtrl.md)|기본 도구 설명 컨트롤에 대 한 참조를 반환합니다.|  
|[CMFCButton::IsAutoCheck](../Topic/CMFCButton::IsAutoCheck.md)|확인란이 나 라디오 단추는 자동 단추 인지 여부를 나타냅니다.|  
|[CMFCButton::IsAutorepeatCommandMode](../Topic/CMFCButton::IsAutorepeatCommandMode.md)|단추는 자동 반복 모드로 설정 되어 있는지 여부를 나타냅니다.|  
|[CMFCButton::IsCheckBox](../Topic/CMFCButton::IsCheckBox.md)|단추 확인란 단추 인지 여부를 나타냅니다.|  
|[CMFCButton::IsChecked](../Topic/CMFCButton::IsChecked.md)|현재 단추가 선택 되어 있는지 여부를 나타냅니다.|  
|[CMFCButton::IsHighlighted](../Topic/CMFCButton::IsHighlighted.md)|단추 강조 표시 되는지 여부를 나타냅니다.|  
|[CMFCButton::IsPressed](../Topic/CMFCButton::IsPressed.md)|단추 강조 표시 하 고 있습니다 푸시되 지 여부를 나타냅니다.|  
|[CMFCButton::IsPushed](../Topic/CMFCButton::IsPushed.md)|단추가 푸시됩니다 여부를 나타냅니다.|  
|[CMFCButton::IsRadioButton](../Topic/CMFCButton::IsRadioButton.md)|단추는 라디오 단추 인지 여부를 나타냅니다.|  
|[CMFCButton::IsWindowsThemingEnabled](../Topic/CMFCButton::IsWindowsThemingEnabled.md)|단추 테두리의 스타일을 현재 Windows 테마에 해당 하는지 여부를 나타냅니다.|  
|`CMFCButton::OnDrawParentBackground`|단추의 부모 배경이 지정된 된 영역을 그립니다.  \(재정의 [AFX\_GLOBAL\_DATA::DrawParentBackground](../Topic/AFX_GLOBAL_DATA::DrawParentBackground.md).\)|  
|`CMFCButton::PreTranslateMessage`|창 메시지를 디스패치하기 전에 변환의  [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및  [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 기능입니다.  \(재정의 [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMFCButton::SetAutorepeatMode](../Topic/CMFCButton::SetAutorepeatMode.md)|단추는 자동 반복 모드를 설정합니다.|  
|[CMFCButton::SetCheckedImage](../Topic/CMFCButton::SetCheckedImage.md)|선택 된 단추에 대 한 이미지를 설정합니다.|  
|[CMFCButton::SetFaceColor](../Topic/CMFCButton::SetFaceColor.md)|단추 텍스트의 배경색을 설정합니다.|  
|[CMFCButton::SetImage](../Topic/CMFCButton::SetImage.md)|이미지 단추를 설정합니다.|  
|[CMFCButton::SetMouseCursor](../Topic/CMFCButton::SetMouseCursor.md)|커서 이미지를 설정합니다.|  
|[CMFCButton::SetMouseCursorHand](../Topic/CMFCButton::SetMouseCursorHand.md)|커서는 손 모양 이미지를 설정합니다.|  
|[CMFCButton::SetStdImage](../Topic/CMFCButton::SetStdImage.md)|사용 하는 `CMenuImages` 개체에서 단추 이미지를 설정 합니다.|  
|[CMFCButton::SetTextColor](../Topic/CMFCButton::SetTextColor.md)|선택 되지 않은 단추에 대 한 단추 텍스트의 색을 설정 합니다.|  
|[CMFCButton::SetTextHotColor](../Topic/CMFCButton::SetTextHotColor.md)|선택한 단추의 단추 텍스트의 색을 설정 합니다.|  
|[CMFCButton::SetTooltip](../Topic/CMFCButton::SetTooltip.md)|도구 설명 단추와 연결합니다.|  
|[CMFCButton::SizeToContent](../Topic/CMFCButton::SizeToContent.md)|단추 텍스트와 이미지를 포함 하는 단추 크기를 조정 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCButton::OnDraw](../Topic/CMFCButton::OnDraw.md)|단추를 그리려면 프레임 워크에서 호출 됩니다.|  
|[CMFCButton::OnDrawBorder](../Topic/CMFCButton::OnDrawBorder.md)|단추의 테두리를 그리려면 프레임 워크에서 호출 됩니다.|  
|[CMFCButton::OnDrawFocusRect](../Topic/CMFCButton::OnDrawFocusRect.md)|단추에 포커스 사각형을 그릴 것인지 프레임 워크에서 호출 합니다.|  
|[CMFCButton::OnDrawText](../Topic/CMFCButton::OnDrawText.md)|단추 텍스트를 그리려면 프레임 워크에서 호출 됩니다.|  
|[CMFCButton::OnFillBackground](../Topic/CMFCButton::OnFillBackground.md)|단추 텍스트의 배경을 그리려면 프레임 워크에서 호출 됩니다.|  
|[CMFCButton::SelectFont](../Topic/CMFCButton::SelectFont.md)|지정 된 디바이스 컨텍스트와 연결 된 글꼴을 검색 합니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCButton::m\_bDrawFocus](../Topic/CMFCButton::m_bDrawFocus.md)|단추 주위에 포커스 사각형을 그릴 것인지 여부를 나타냅니다.|  
|[CMFCButton::m\_bHighlightChecked](../Topic/CMFCButton::m_bHighlightChecked.md)|위로 커서를 이동 하면 BS\_CHECKBOX 스타일 단추를 강조 표시 하는지 여부를 나타냅니다.|  
|[CMFCButton::m\_bRightImage](../Topic/CMFCButton::m_bRightImage.md)|오른쪽에 이미지를 표시할지 여부를 나타냅니다.|  
|[CMFCButton::m\_bTransparent](../Topic/CMFCButton::m_bTransparent.md)|단추를 투명 하 게 인지 여부를 나타냅니다.|  
|[CMFCButton::m\_nAlignStyle](../Topic/CMFCButton::m_nAlignStyle.md)|단추 텍스트의 맞춤을 지정합니다.|  
|[CMFCButton::m\_nFlatStyle](../Topic/CMFCButton::m_nFlatStyle.md)|단추의 테두리, 플랫, semi\-flat, 3D 등의 스타일을 지정 합니다.|  
  
## 설명  
 다른 종류의 단추에서 파생 되는 `CMFCButton` 같은 클래스는  [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md) 하이퍼링크를 지 원하는 클래스와 `CMFCColorButton` 색 선택 대화 상자를 지 원하는 클래스입니다.  
  
 스타일의 한 `CMFCButton` 개체 수  *3D*,  *플랫*,  *semi\-flat* 또는  *테두리가*.  왼쪽, 위쪽 또는 가운데 단추에 단추 텍스트를 맞출 수 있습니다.  런타임 시 단추의 텍스트, 이미지 또는 텍스트와 이미지를 표시할지 여부를 제어할 수 있습니다.  커서를 단추 위로 이동 하면 특정 커서 이미지 표시 하도록 지정할 수도 있습니다.  
  
 또는 코드에서 직접 사용 하 여 단추 컨트롤을 만들는  **MFC 클래스 마법사** 도구 및 대화 상자 템플릿에.  단추 컨트롤을 직접 만드는 경우 추가 `CMFCButton` 변수를 응용 프로그램 및 다음 생성자를 호출 하 고 `Create` 메서드를의 `CMFCButton` 개체.  사용 하는 경우는  **MFC 클래스 마법사**, 추가 `CButton` 변수를 응용 프로그램을 다음에서 변수의 형식을 변경 하 고 `CButton` 에 `CMFCButton`.  
  
 대화 상자 응용 프로그램에서 알림 메시지를 처리 하기 위해 메시지 맵 엔트리 및 각 알림에 대 한 이벤트 처리기를 추가 합니다.  알림을 보낸는 `CMFCButton` 개체는 동일 보낸는 `CButton` 개체.  
  
## 예제  
 다음 예제에서는 다양 한 메서드를 사용 하 여 단추의 속성을 구성 하는 방법의 `CMFCButton` 클래스입니다.  일부인 예제는  [새 컨트롤 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/CPP/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/CPP/cmfcbutton-class_2.cpp)]  
[!code-cpp[NVC_MFC_NewControls#32](../../mfc/reference/codesnippet/CPP/cmfcbutton-class_3.cpp)]  
[!code-cpp[NVC_MFC_NewControls#33](../../mfc/reference/codesnippet/CPP/cmfcbutton-class_4.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
## 요구 사항  
 **헤더:** afxbutton.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCLinkCtrl Class](../../mfc/reference/cmfclinkctrl-class.md)   
 [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md)   
 [CMFCMenuButton 클래스](../../mfc/reference/cmfcmenubutton-class.md)