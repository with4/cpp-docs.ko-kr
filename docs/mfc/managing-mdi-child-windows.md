---
title: "MDI 자식 창 관리 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MDICLIENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "자식 창"
  - "자식 창, 및 MDICLIENT 창"
  - "프레임 창[C++], MDI 자식 창"
  - "MDI[C++], 자식 창"
  - "MDI[C++], 프레임 창"
  - "MDICLIENT 창"
  - "창[C++], MDI"
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MDI 자식 창 관리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MDI 주 프레임 창 \(응용프로그램마다 하나씩\)은 **MDICLIENT** 창이라고 불리는 특수한 자식 창이 포함되어 있습니다.  **MDICLIENT** 창은 주 프레임 창의 클라이언트 영역을 관리하고 자식 창들을 가지고 있습니다 :`CMDIChildWnd`으로 부터 파생된 문서 창.  문서 창들은 자체로 프레임 창들이기 때문에 \(MDI 자식 창들\), 자신의 자식이 있을 수도 있습니다.   이 모든 경우에 부모 창은 그것의 자식 창들을 관리해주고 몇가지 명령들을 전달합니다.  
  
 MDI 프레임 창에서 프레임 창은 **MDICLIENT** 창을 관리하고 컨트롤 막대와의 결합에서 그것을 재위치시킵니다.  **MDICLIENT** 창이 모든 MDI 자식 프레임 창을 관리 합니다.  다음 그림은 MDI 프레임 창, 그것의 **MDICLIENT** 창 그리고 자식 문서 프레임 창들의 관계를 보여줍니다.  
  
 ![MDI 프레임 창의 자식 창](../mfc/media/vc37gb1.png "vc37GB1")  
MDI 프레임 창 및 자식  
  
 MDI 프레임 창은 현재 MDI 자식 창의 결합에서 작동합니다.  MDI 프레임 창은 그 스스로 그것들을 처리하기 전에 MDI 자식에게 명령 메시지를 위임합니다.  
  
## 추가 정보  
  
-   [문서 프레임 창 만들기](../mfc/creating-document-frame-windows.md)  
  
-   [프레임 창 스타일](../mfc/frame-window-styles-cpp.md)  
  
## 참고 항목  
 [프레임 창 사용](../mfc/using-frame-windows.md)