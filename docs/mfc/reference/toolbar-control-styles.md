---
title: "ToolBar 컨트롤 스타일 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "도구 모음 컨트롤 스타일"
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# ToolBar 컨트롤 스타일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)는 단추의 동작 및 모양을 결정하는 스타일 플래그 집합을 가집니다.  사용자는 [CMFCToolBarButton::SetStyle](../Topic/CMFCToolBarButton::SetStyle.md)를 호출하는 것으로 이러한 플래그의 조합을 설정할 수 있습니다.  이 항목은 스타일 플래그 값과 의미를 열거합니다.  
  
## 속성 값  
 다음 값은 컨트롤이 나타내는 단추 형식을 결정합니다.  
  
 TBBS\_BUTTON  
 기본 누름단추\(기본값\)입니다.  
  
 TBBS\_CHECKBOX  
 확인란입니다.  
  
 TBBS\_CHECKGROUP  
 확인란 그룹의 시작입니다.  
  
 TBBS\_GROUP  
 단추 그룹의 시작입니다.  
  
 TBBS\_SEPARATOR  
 구분 기호입니다.  
  
 다음 값은 컨트롤의 현재 상태를 나타냅니다:  
  
 TBBS\_CHECKED  
 확인란이 선택되었습니다.  
  
 TBBS\_DISABLED  
 컨트롤이 사용하지 않도록 설정되어 있습니다.  
  
 TBBS\_INDETERMINATE  
 확인란이 미확정 상태입니다.  
  
 TBBS\_PRESSED  
 단추가 눌러진 상태로 표시됩니다.  
  
 다음 값은 도구 모음에 있는 단추의 레이아웃을 변경합니다.  
  
 TBBS\_BREAK  
 항목을 새로운 행에 배치하거나, 열을 분리하지 않고 새로운 열에 넣습니다.  
  
## 설명  
 현재 스타일은 [CMFCToolBarButton::m\_nStyle](../Topic/CMFCToolBarButton::m_nStyle.md)에 저장됩니다.  `SetStyles`를 호출할 때 몇몇 파생된 클래스는 추가 작업을 수행하기 때문에, 새 값을 `m_nStyle`으로 직접 설정하지 마십시오.  
  
 시각화 관리자는 각 상태에서 단추 모양을 결정합니다.  자세한 내용은 [시각화 관리자](../../mfc/visualization-manager.md)를 참조하십시오.  
  
## 요구 사항  
 **Header:** afxtoolbarbutton.h  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [시각화 관리자](../../mfc/visualization-manager.md)