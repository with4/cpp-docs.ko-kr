---
title: "CMFCRibbonStatusBar Class | Microsoft Docs"
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
  - "CMFCRibbonStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonStatusBar class"
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
caps.latest.revision: 37
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonStatusBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonStatusBar` 리본 요소를 표시 하는 상태 표시줄 컨트롤 클래스를 구현 합니다.  
  
## 구문  
  
```  
class CMFCRibbonStatusBar : public CMFCRibbonBar  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonStatusBar::AddDynamicElement](../Topic/CMFCRibbonStatusBar::AddDynamicElement.md)|리본 상태 표시줄에는 동적 요소를 추가합니다.|  
|[CMFCRibbonStatusBar::AddElement](../Topic/CMFCRibbonStatusBar::AddElement.md)|리본 상태 표시줄에 새 리본 요소를 추가합니다.|  
|[CMFCRibbonStatusBar::AddExtendedElement](../Topic/CMFCRibbonStatusBar::AddExtendedElement.md)|리본 상태 표시줄의 확장된 영역에는 리본 요소를 추가합니다.|  
|[CMFCRibbonStatusBar::AddSeparator](../Topic/CMFCRibbonStatusBar::AddSeparator.md)|리본 상태 표시줄에는 구분 기호를 추가합니다.|  
|[CMFCRibbonStatusBar::Create](../Topic/CMFCRibbonStatusBar::Create.md)|리본 상태 표시줄을 만듭니다.|  
|[CMFCRibbonStatusBar::CreateEx](../Topic/CMFCRibbonStatusBar::CreateEx.md)|확장된 스타일을 가진 리본 상태 표시줄을 만듭니다.|  
|[CMFCRibbonStatusBar::FindByID](../Topic/CMFCRibbonStatusBar::FindByID.md)||  
|[CMFCRibbonStatusBar::FindElement](../Topic/CMFCRibbonStatusBar::FindElement.md)|지정 된 명령 ID가 있는 요소에는 포인터를 반환 합니다.|  
|[CMFCRibbonStatusBar::GetCount](../Topic/CMFCRibbonStatusBar::GetCount.md)|리본 상태 표시줄의 기본 영역에 있는 요소 개수를 반환 합니다.|  
|[CMFCRibbonStatusBar::GetElement](../Topic/CMFCRibbonStatusBar::GetElement.md)|지정 된 인덱스에 있는 요소에 대 한 포인터를 반환 합니다.|  
|[CMFCRibbonStatusBar::GetExCount](../Topic/CMFCRibbonStatusBar::GetExCount.md)|리본 상태 표시줄의 확장된 영역에 있는 요소 개수를 반환 합니다.|  
|[CMFCRibbonStatusBar::GetExElement](../Topic/CMFCRibbonStatusBar::GetExElement.md)|리본 상태 표시줄의 확장된 영역에서 지정 된 인덱스에 있는 요소에 대 한 포인터를 반환 합니다.|  
|[CMFCRibbonStatusBar::GetExtendedArea](../Topic/CMFCRibbonStatusBar::GetExtendedArea.md)||  
|[CMFCRibbonStatusBar::GetSpace](../Topic/CMFCRibbonStatusBar::GetSpace.md)||  
|[CMFCRibbonStatusBar::IsBottomFrame](../Topic/CMFCRibbonStatusBar::IsBottomFrame.md)||  
|[CMFCRibbonStatusBar::IsExtendedElement](../Topic/CMFCRibbonStatusBar::IsExtendedElement.md)||  
|[CMFCRibbonStatusBar::IsInformationMode](../Topic/CMFCRibbonStatusBar::IsInformationMode.md)|정보 모드 리본 상태 표시줄에 사용할 수 있는지 여부를 결정 합니다.|  
|[CMFCRibbonStatusBar::RecalcLayout](../Topic/CMFCRibbonStatusBar::RecalcLayout.md)|\(재정의 [CMFCRibbonBar::RecalcLayout](../Topic/CMFCRibbonBar::RecalcLayout.md).\)|  
|[CMFCRibbonStatusBar::RemoveAll](../Topic/CMFCRibbonStatusBar::RemoveAll.md)|리본 상태 표시줄에서 모든 요소를 제거합니다.|  
|[CMFCRibbonStatusBar::RemoveElement](../Topic/CMFCRibbonStatusBar::RemoveElement.md)|리본 상태 표시줄에 지정 된 명령 ID가 있는 요소를 제거 합니다.|  
|[CMFCRibbonStatusBar::SetInformation](../Topic/CMFCRibbonStatusBar::SetInformation.md)|리본 상태 표시줄의 정보 모드를 사용할 수 있거나.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonStatusBar::OnDrawInformation](../Topic/CMFCRibbonStatusBar::OnDrawInformation.md)|리본 상태 표시줄 정보 모드를 사용 하는 경우 표시 되는 정보 문자열을 표시 합니다.|  
  
## 설명  
 사용자가 리본 메뉴의 상태 표시줄에 기본 제공 되는 컨텍스트 메뉴를 사용 하 여 리본 요소에서 리본 상태 표시줄의 표시 여부를 변경할 수 있습니다.  추가 또는 요소를 동적으로 제거할 수 있습니다.  
  
 리본 상태 표시줄에 두 개의 영역이 있습니다: 기본 영역과 확장된 영역.  확장된 영역 리본 상태 표시줄의 오른쪽에 표시 되 고 주 영역 보다 다른 색으로 나타납니다.  
  
 일반적으로 주로 상태 표시줄의 상태 알림 표시 하 고 보기 컨트롤 확장된 영역을 표시 합니다.  확장된 영역 사용자 리본 상태 표시줄의 크기가 조정 될 때 가능한 길게 보입니다.  
  
## 예제  
 다음 예제에서는 다양 한 방법에 있는 `CMFCRibbonStatusBar` 클래스입니다.  리본 상태 표시줄에 대 한 일반 모드를 사용 하 고 추가 구분 기호, 리본 상태 표시줄에 새 리본 요소를 추가, 리본 상태 표시줄의 확장된 영역에는 리본 요소를 추가 하는 방법의 예제를 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#15](../../mfc/reference/codesnippet/CPP/cmfcribbonstatusbar-class_1.cpp)]  
[!code-cpp[NVC_MFC_RibbonApp#16](../../mfc/reference/codesnippet/CPP/cmfcribbonstatusbar-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)  
  
 [CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)  
  
## 요구 사항  
 **헤더:** afxribbonstatusbar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)