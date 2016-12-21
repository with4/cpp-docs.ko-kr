---
title: "CMFCDropDownFrame Class | Microsoft Docs"
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
  - "CMFCDropDownFrame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDropDownFrame class"
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDropDownFrame Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

드롭다운 도구 모음과 드롭다운 도구 모음 단추 드롭다운 프레임 창 기능을 제공합니다.  
  
## 구문  
  
```  
class CMFCDropDownFrame : public CMiniFrameWnd  
```  
  
## Members  
  
### Public 생성자  
  
|||  
|-|-|  
|Name|설명|  
|`CMFCDropDownFrame::CMFCDropDownFrame`|기본 생성자입니다.|  
|`CMFCDropDownFrame::~CMFCDropDownFrame`|소멸자.|  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCDropDownFrame::Create](../Topic/CMFCDropDownFrame::Create.md)|`CMFCDropDownFrame` 개체를 만듭니다.|  
|`CMFCDropDownFrame::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|[CMFCDropDownFrame::GetParentMenuBar](../Topic/CMFCDropDownFrame::GetParentMenuBar.md)|상위 메뉴 모음 드롭다운 프레임을 검색합니다.|  
|[CMFCDropDownFrame::GetParentPopupMenu](../Topic/CMFCDropDownFrame::GetParentPopupMenu.md)|부모 팝업 메뉴의 아래쪽 프레임을 검색합니다.|  
|`CMFCDropDownFrame::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCDropDownFrame::RecalcLayout](../Topic/CMFCDropDownFrame::RecalcLayout.md)|아래쪽 프레임을 다시 설정합니다.|  
|[CMFCDropDownFrame::SetAutoDestroy](../Topic/CMFCDropDownFrame::SetAutoDestroy.md)|드롭다운 도구 모음 하위 창이 자동으로 소멸 됩니다 여부를 설정 합니다.|  
  
### 설명  
 이 클래스는 사용자 코드에서 직접 사용할 수 없습니다.  
  
 프레임 워크는이 클래스를 사용 하 여 프레임의 동작을 제공 하는 `CMFCDropDownToolbar` 및 `CMFCDropDownToolbarButton` 클래스입니다.  이러한 클래스에 대한 자세한 내용은 [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md) 및 [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)을 참조하십시오.  
  
## 예제  
 다음 예제에 대 한 포인터를 검색 하는 방법을 보여 줍니다.을 `CMFCDropDownFrame` 에서 개체는 `CFrameWnd` 클래스 및 자식 창을 자동으로 소멸 드롭다운 도구 모음 설정 하는 방법.  
  
 [!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/CPP/cmfcdropdownframe-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)  
  
## 요구 사항  
 **헤더:** afxdropdowntoolbar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)