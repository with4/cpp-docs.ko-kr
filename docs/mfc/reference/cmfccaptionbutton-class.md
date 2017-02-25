---
title: "CMFCCaptionButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCCaptionButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCaptionButton class"
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CMFCCaptionButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCCaptionButton` 클래스는 도킹 창 또는 미니 프레임 창 캡션 표시줄에 표시 되는 단추를 구현 합니다.  일반적으로 프레임 워크는 캡션 단추를 자동으로 만듭니다.  
  
## 구문  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## Members  
  
### 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCCaptionButton::CMFCCaptionButton](../Topic/CMFCCaptionButton::CMFCCaptionButton.md)|CMFCCaptionButton 개체를 만듭니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCCaptionButton::GetHit](../Topic/CMFCCaptionButton::GetHit.md)|명령 단추를 통해 표시를 반환 합니다.|  
|[CMFCCaptionButton::GetIconID](../Topic/CMFCCaptionButton::GetIconID.md)|단추와 연결 된 이미지 ID를 반환 합니다.|  
|[CMFCCaptionButton::GetRect](../Topic/CMFCCaptionButton::GetRect.md)|단추에서 차지 하는 사각형을 반환 합니다.|  
|[CMFCCaptionButton::GetSize](../Topic/CMFCCaptionButton::GetSize.md)|너비 및 높이 단추 중 하나를 반환합니다.|  
|[CMFCCaptionButton::IsMiniFrameButton](../Topic/CMFCCaptionButton::IsMiniFrameButton.md)|제목 표시줄 높이 작은 크기로 설정 되어 있는지 여부를 나타냅니다.|  
|[CMFCCaptionButton::Move](../Topic/CMFCCaptionButton::Move.md)|그리기 단추 위치 및 창의 표시 상태를 설정합니다.|  
|[CMFCCaptionButton::OnDraw](../Topic/CMFCCaptionButton::OnDraw.md)|캡션 단추를 그립니다.|  
|[CMFCCaptionButton::SetMiniFrameButton](../Topic/CMFCCaptionButton::SetMiniFrameButton.md)|작은 제목 표시줄의 크기를 설정합니다.|  
  
## 설명  
 클래스에서 파생 될 수 있습니다 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md) 보호 된 메서드를 사용 하 고 `AddButton`, 캡션 단추 미니 프레임 창에 추가할 수 있습니다.  
  
 CPaneFrameWnd.h 두 종류의 캡션 단추의 명령 Id를 정의합니다.  
  
-   `AFX_CAPTION_BTN_PIN`도킹 창 자동 숨기기 모드를 지 원하는 경우 고정 단추를 표시 합니다.  
  
-   `AFX_CAPTION_BTN_CLOSE`어떤 표시는  **닫기** 단추 창 폐쇄 되거나 숨겨질 수 있는 경우.  
  
## 예제  
 다음 예제에서는 생성 하는 방법을 보여 줍니다.는 `CMFCCaptionButton` 개체 및 미니 제목 표시줄의 크기를 설정 합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/CPP/cmfccaptionbutton-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)  
  
## 요구 사항  
 **헤더:** afxcaptionbutton.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)