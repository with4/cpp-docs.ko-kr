---
title: "CMFCRibbonMiniToolBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonMiniToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonMiniToolBar class"
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMFCRibbonMiniToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

상황별 팝업 도구 모음을 구현합니다.  
  
## 구문  
  
```  
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|기본 생성자입니다.|  
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|`CMFCRibbonMiniToolBar::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|`CMFCRibbonMiniToolBar::GetThisClass`|프레임워크에서 이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 가져오는 데 사용합니다.|  
|[CMFCRibbonMiniToolBar::IsContextMenuMode](../Topic/CMFCRibbonMiniToolBar::IsContextMenuMode.md)||  
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](../Topic/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar.md)|\(`CMFCPopupMenu::IsRibbonMiniToolBar`를 재정의합니다.\)|  
|[CMFCRibbonMiniToolBar::SetCommands](../Topic/CMFCRibbonMiniToolBar::SetCommands.md)|도구 모음에 표시되는 명령의 목록을 설정합니다.|  
|[CMFCRibbonMiniToolBar::Show](../Topic/CMFCRibbonMiniToolBar::Show.md)|지정된 화면 좌표에 미니 도구 모음을 표시합니다.|  
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](../Topic/CMFCRibbonMiniToolBar::ShowWithContextMenu.md)|상황에 맞는 메뉴와 함께 미니 도구 모음을 표시합니다.|  
  
## 설명  
 미니 도구 모음은 일반적으로 사용자가 문서에서 개체를 선택한 후에 표시됩니다.  예를 들어 사용자가 문서 작성 프로그램에서 텍스트 블록을 선택하고 나면 응용 프로그램은 텍스트 서식 지정 명령이 포함된 미니 도구 모음을 표시합니다.  
  
 마우스 포인터가 미니 도구 모음의 범위를 벗어나면 미니 도구 모음은 투명해집니다.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 `CMFCRibbonPanelMenu`  
  
 [CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)  
  
## 요구 사항  
 **헤더:** afxRibbonMiniToolBar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)