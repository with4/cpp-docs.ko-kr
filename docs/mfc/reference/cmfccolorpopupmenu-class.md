---
title: "CMFCColorPopupMenu Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCColorPopupMenu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorPopupMenu class"
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CMFCColorPopupMenu Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자 문서 또는 응용 프로그램에서 색을 선택할 수 있는 팝업 메뉴를 나타냅니다.  
  
## 구문  
  
```  
class CMFCColorPopupMenu : public CMFCPopupMenu  
```  
  
## Members  
  
### Public 생성자  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCColorPopupMenu::CMFCColorPopupMenu](../Topic/CMFCColorPopupMenu::CMFCColorPopupMenu.md)|`CMFCColorPopupMenu` 개체를 생성합니다.|  
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|소멸자.|  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCColorPopupMenu::CreateTearOffBar](../Topic/CMFCColorPopupMenu::CreateTearOffBar.md)|도킹 가능한 분리 된 색상 막대를 만듭니다.  \(재정의 [CMFCPopupMenu::CreateTearOffBar](../Topic/CMFCPopupMenu::CreateTearOffBar.md).\)|  
|[CMFCColorPopupMenu::GetMenuBar](../Topic/CMFCColorPopupMenu::GetMenuBar.md)|반환 된  [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) 팝업 메뉴 안에 포함 됩니다.  \(재정의 [CMFCPopupMenu::GetMenuBar](../Topic/CMFCPopupMenu::GetMenuBar.md).\)|  
|`CMFCColorPopupMenu::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCColorPopupMenu::SetPropList](../Topic/CMFCColorPopupMenu::SetPropList.md)|포함 된 속성 표 컨트롤 개체를 설정 합니다. `CMFCColorBar` 개체입니다.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|Name|설명|  
|`m_bEnabledInCustomizeMode`|색상 막대를 표시할지 여부를 결정 하는 부울 값입니다.|  
|`m_wndColorBar`|`CMFCColorBar` 색상 선택을 제공 하는 개체입니다.|  
  
### 설명  
 이 클래스의 팝업 메뉴 기능을 상속의 `CMFCPopupMenu` 클래스와 관리는 `CMFCColorBar` 색상 선택을 제공 하는 개체.  도구 모음 프레임 워크 사용자 지정 모드에 있을 때와 `m_bEnabledInCustomizeMode` 구성원에 설정 된 `FALSE`, 색상 막대 개체는 표시 되지 않습니다.  사용자 지정 모드에 대 한 자세한 내용은 참조 하십시오.[CMFCToolBar::IsCustomizeMode](../Topic/CMFCToolBar::IsCustomizeMode.md)  
  
 `CMFCColorBar`에 대한 자세한 내용은 [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)를 참조하십시오.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 [CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)  
  
## 요구 사항  
 **헤더:** afxcolorpopupmenu.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)