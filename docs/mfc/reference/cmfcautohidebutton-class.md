---
title: "CMFCAutoHideButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCAutoHideButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCAutoHideButton class"
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCAutoHideButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

숨기도록 구성된 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)를 표시하거나 숨기는 단추입니다.  
  
## 구문  
  
```  
class CMFCAutoHideButton : public CObject  
```  
  
## 멤버  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCAutoHideButton::BringToTop](../Topic/CMFCAutoHideButton::BringToTop.md)||  
|[CMFCAutoHideButton::Create](../Topic/CMFCAutoHideButton::Create.md)|자동 숨기기 단추를 만들고 초기화합니다.|  
|[CMFCAutoHideButton::GetAlignment](../Topic/CMFCAutoHideButton::GetAlignment.md)|자동 숨기기 단추의 맞춤을 검색합니다.|  
|[CMFCAutoHideButton::GetAutoHideWindow](../Topic/CMFCAutoHideButton::GetAutoHideWindow.md)|자동 숨기기 단추와 연결된 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 개체를 반환합니다.|  
|[CMFCAutoHideButton::GetParentToolBar](../Topic/CMFCAutoHideButton::GetParentToolBar.md)||  
|[CMFCAutoHideButton::GetRect](../Topic/CMFCAutoHideButton::GetRect.md)||  
|[CMFCAutoHideButton::GetSize](../Topic/CMFCAutoHideButton::GetSize.md)|자동 숨기기 단추의 크기를 결정합니다.|  
|[CMFCAutoHideButton::GetTextSize](../Topic/CMFCAutoHideButton::GetTextSize.md)|자동 숨기기 단추에 대한 텍스트 레이블의 크기를 반환합니다.|  
|[CMFCAutoHideButton::HighlightButton](../Topic/CMFCAutoHideButton::HighlightButton.md)|자동 숨기기 단추를 강조 표시합니다.|  
|[CMFCAutoHideButton::IsActive](../Topic/CMFCAutoHideButton::IsActive.md)|자동 숨기기 단추가 활성 상태인지를 나타냅니다.|  
|[CMFCAutoHideButton::IsHighlighted](../Topic/CMFCAutoHideButton::IsHighlighted.md)|자동 숨기기 단추의 강조 표시 상태를 반환합니다.|  
|[CMFCAutoHideButton::IsHorizontal](../Topic/CMFCAutoHideButton::IsHorizontal.md)|자동 숨기기 단추가 가로 또는 세로로 표시되는지를 결정합니다.|  
|[CMFCAutoHideButton::IsTop](../Topic/CMFCAutoHideButton::IsTop.md)||  
|[CMFCAutoHideButton::IsVisible](../Topic/CMFCAutoHideButton::IsVisible.md)|단추의 표시 여부를 나타냅니다.|  
|[CMFCAutoHideButton::Move](../Topic/CMFCAutoHideButton::Move.md)||  
|[CMFCAutoHideButton::OnDraw](../Topic/CMFCAutoHideButton::OnDraw.md)|자동 숨기기 단추를 그릴 때 프레임워크에서 이 메서드를 호출합니다.|  
|[CMFCAutoHideButton::OnDrawBorder](../Topic/CMFCAutoHideButton::OnDrawBorder.md)|자동 숨기기 단추의 테두리를 그릴 때 프레임워크에서 이 메서드를 호출합니다.|  
|[CMFCAutoHideButton::OnFillBackground](../Topic/CMFCAutoHideButton::OnFillBackground.md)|자동 숨기기 단추의 배경을 채울 때 프레임워크에서 이 메서드를 호출합니다.|  
|[CMFCAutoHideButton::ReplacePane](../Topic/CMFCAutoHideButton::ReplacePane.md)||  
|[CMFCAutoHideButton::ShowAttachedWindow](../Topic/CMFCAutoHideButton::ShowAttachedWindow.md)|연결된 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)를 표시하거나 숨깁니다.|  
|[CMFCAutoHideButton::ShowButton](../Topic/CMFCAutoHideButton::ShowButton.md)|자동 숨기기 단추를 표시하거나 숨깁니다.|  
|[CMFCAutoHideButton::UnSetAutoHideMode](../Topic/CMFCAutoHideButton::UnSetAutoHideMode.md)||  
  
## 설명  
 생성 시 `CMFCAutoHideButton` 개체가 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)에 연결됩니다.  사용자가 `CMFCAutoHideButton` 개체를 조작할 때 `CDockablePane` 개체가 숨겨지거나 표시됩니다.  
  
 기본적으로 프레임워크에서는 사용자가 자동 숨기기를 설정할 때 자동으로 `CMFCAutoHideButton`을 만듭니다.  프레임워크에서는 `CMFCAutoHideButton` 클래스 대신 사용자 지정 UI 클래스의 요소를 만들 수 있습니다.  프레임워크에서 사용해야 하는 사용자 지정 UI 클래스를 지정하려면 사용자 지정 UI 클래스와 같은 정적 멤버 변수 `CMFCAutoHideBar::m_pAutoHideButtonRTS`를 설정합니다.  기본적으로 이 변수는 `CMFCAutoHideButton`으로 설정됩니다.  
  
## 예제  
 다음 예제에서는 `CMFCAutoHideButton` 개체를 생성하고 `CMFCAutoHideButton` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다.  예제에서는 `Create` 메서드를 사용하여 `CMFCAutoHideButton` 개체를 초기화하고, 연결된 `CDockablePane` 클래스를 표시하고, 자동 숨기기 단추를 표시하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/CPP/cmfcautohidebutton-class_1.cpp)]  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md)  
  
## 요구 사항  
 **헤더:** afxautohidebutton.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCAutoHideBar Class](../../mfc/reference/cmfcautohidebar-class.md)   
 [CAutoHideDockSite Class](../../mfc/reference/cautohidedocksite-class.md)