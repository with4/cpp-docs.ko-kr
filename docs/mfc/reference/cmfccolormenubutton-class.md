---
title: "CMFCColorMenuButton Class | Microsoft Docs"
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
  - "CMFCColorMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorMenuButton class"
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
caps.latest.revision: 29
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorMenuButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCColorMenuButton` 클래스는 색 선택 대화 상자를 시작 하는 도구 모음 단추 또는 메뉴 명령을 지원 합니다.  
  
## 구문  
  
```  
class CMFCColorMenuButton : public CMFCToolBarMenuButton  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCColorMenuButton::CMFCColorMenuButton](../Topic/CMFCColorMenuButton::CMFCColorMenuButton.md)|`CMFCColorMenuButton` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCColorMenuButton::EnableAutomaticButton](../Topic/CMFCColorMenuButton::EnableAutomaticButton.md)|수 있으며 일반 색 단추 위에 배치 되는 "자동" 단추를 사용할 수 없습니다.  \(표준 시스템 자동 단추인  **자동**.\)|  
|[CMFCColorMenuButton::EnableDocumentColors](../Topic/CMFCColorMenuButton::EnableDocumentColors.md)|시스템 색 대신 문서 특정 색상을 표시할 수 있습니다.|  
|[CMFCColorMenuButton::EnableOtherButton](../Topic/CMFCColorMenuButton::EnableOtherButton.md)|수 있으며 일반 색 단추 아래에 배치 되는 "기타" 단추를 사용할 수 없습니다.  \("기타" 단추는 표시 된 표준 시스템  **다른 색...**.\)|  
|[CMFCColorMenuButton::EnableTearOff](../Topic/CMFCColorMenuButton::EnableTearOff.md)|색상 창을 해제 떼어낼 수가 있습니다.|  
|[CMFCColorMenuButton::GetAutomaticColor](../Topic/CMFCColorMenuButton::GetAutomaticColor.md)|현재 자동 색을 검색합니다.|  
|[CMFCColorMenuButton::GetColor](../Topic/CMFCColorMenuButton::GetColor.md)|현재 단추의 색을 검색합니다.|  
|[CMFCColorMenuButton::GetColorByCmdID](../Topic/CMFCColorMenuButton::GetColorByCmdID.md)|지정 된 명령 ID에 해당 하는 색을 검색 합니다.|  
|[CMFCColorMenuButton::OnChangeParentWnd](../Topic/CMFCColorMenuButton::OnChangeParentWnd.md)|부모 창이 변경 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCColorMenuButton::OpenColorDialog](../Topic/CMFCColorMenuButton::OpenColorDialog.md)|색 선택 대화 상자가 열립니다.|  
|[CMFCColorMenuButton::SetColor](../Topic/CMFCColorMenuButton::SetColor.md)|현재 색 단추의 색을 설정합니다.|  
|[CMFCColorMenuButton::SetColorByCmdID](../Topic/CMFCColorMenuButton::SetColorByCmdID.md)|메뉴 단추는 지정 된 색상의 색을 설정합니다.|  
|[CMFCColorMenuButton::SetColorName](../Topic/CMFCColorMenuButton::SetColorName.md)|지정 된 색의 새 이름을 설정합니다.|  
|[CMFCColorMenuButton::SetColumnsNumber](../Topic/CMFCColorMenuButton::SetColumnsNumber.md)|표시 된 열 수를 설정 하는 `CMFCColorBar` 개체.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCColorMenuButton::CopyFrom](../Topic/CMFCColorMenuButton::CopyFrom.md)|현재 단추를 다른 도구 모음 단추를 복사합니다.|  
|[CMFCColorMenuButton::CreatePopupMenu](../Topic/CMFCColorMenuButton::CreatePopupMenu.md)|색 선택 대화 상자를 만듭니다.|  
|[CMFCColorMenuButton::IsEmptyMenuAllowed](../Topic/CMFCColorMenuButton::IsEmptyMenuAllowed.md)|빈 메뉴를 지원 하는지 여부를 나타냅니다.|  
|[CMFCColorMenuButton::OnDraw](../Topic/CMFCColorMenuButton::OnDraw.md)|단추에 이미지를 표시 하는 프레임 워크에서 호출 합니다.|  
|[CMFCColorMenuButton::OnDrawOnCustomizeList](../Topic/CMFCColorMenuButton::OnDrawOnCustomizeList.md)|호출 하기 전에 프레임 워크는 `CMFCColorMenuButton` 개체 도구 모음 사용자 지정 대화 상자의 목록에 표시 됩니다.|  
  
## 설명  
 원래 메뉴 명령이 나 도구 모음 단추를 교체할 수는 `CMFCColorMenuButton` 개체, 만들기는 `CMFCColorMenuButton` 개체는 적절 한 설정, [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md) 스타일 및 다음 호출의 `ReplaceButton` 메서드는 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md) 클래스.  도구 모음을 사용자 지정 하는 경우 호출 된 [CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md) 메서드.  
  
 색 선택 대화 상자를 처리 하는 동안 만들어진는 [CMFCColorMenuButton::CreatePopupMenu](../Topic/CMFCColorMenuButton::CreatePopupMenu.md) 이벤트 처리기입니다.  이벤트 처리기는 부모 프레임으로 알립니다는 `WM_COMMAND` 메시지.  `CMFCColorMenuButton` 개체가 원본 메뉴 명령이 나 도구 모음 단추에 할당 된 컨트롤 ID를 보냅니다.  
  
## 예제  
 만들고 색 단추 메뉴에서 다양 한 방법을 사용 하 여 구성 하는 방법 다음 예제는 `CMFCColorMenuButton` 클래스입니다.  예에서는 `CPalette` 개체 먼저 만들어지고 사용 되는 개체를 생성 하는 `CMFCColorMenuButton` 클래스.  `CMFCColorMenuButton` 개체의 자동 및 다른 단추를 사용 하 고 색 및 열 수를 설정 하 고 구성 합니다.  이 코드의 일부인의  [워드 패드 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/CPP/cmfccolormenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/CPP/cmfccolormenubutton-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
 [CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)  
  
## 요구 사항  
 **헤더:** afxcolormenubutton.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarsCustomizeDialog Class](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)   
 [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md)