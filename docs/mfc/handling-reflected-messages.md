---
title: "리플렉션된 메시지 처리 | Microsoft Docs"
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
  - "메시지 처리, 리플렉트된 메시지"
  - "리플렉트된 메시지, 처리"
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 리플렉션된 메시지 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

메시지 리플렉션은 사용자가 컨트롤 자체 내에서 `WM_CTLCOLOR`, **WM\_COMMAND** 및 **WM\_NOTIFY**와 같은 메시지를 처리하게 합니다.  이것은 컨트롤을 좀 더 자립적이고 간이하게 만듭니다.  메커니즘은 ActiveX 컨트롤\(이전에 OLE 컨트롤이라고 명명된\)뿐만 아니라 Windows 공용 컨트롤을 사용하여 작동합니다.  
  
 메시지 리플렉션은 더 쉽게 파생된 클래스 `CWnd`를 재사용하게 합니다.  메시지 리플렉션은 [CWnd::OnChildNotify](../Topic/CWnd::OnChildNotify.md)을 경유하고 특별한 **ON\_XXX\_REFLECT** 메시지 엔트리를 사용하여 작동합니다. 예를 들면, **ON\_CTLCOLOR\_REFLECT** 및 **ON\_CONTROL\_REFLECT**입니다.  [Technical Note 62](../mfc/tn062-message-reflection-for-windows-controls.md)는 메시지 리플렉션을 보다 자세히 설명합니다.  
  
## 수행할 작업  
  
-   [메시지 리플렉션에 대해 더 알아보기](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [공용 컨트롤을 위한 메시지 리플렉션 구현](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [ActiveX 컨트롤을 위한 메시지 리플렉션 구현](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)  
  
## 참고 항목  
 [메시지 처리기 함수 선언](../mfc/declaring-message-handler-functions.md)