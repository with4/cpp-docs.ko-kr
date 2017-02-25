---
title: "사용자 정의 처리기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.handlers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_MESSAGE 매크로"
  - "ON_REGISTERED_MESSAGE 매크로"
  - "사용자 정의 처리기"
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 사용자 정의 처리기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The following map entries correspond to the function prototypes.  
  
|Map entry|함수 프로토타입|  
|---------------|--------------|  
|ON\_MESSAGE\( \<message\>, \<memberFxn\> \)|afx\_msg LRESULT memberFxn\( WPARAM, LPARAM \);|  
|ON\_REGISTERED\_MESSAGE\( \<nMessageVariable\>, \<memberFxn\> \)|afx\_msg LRESULT memberFxn\( WPARAM, LPARAM \);|  
|ON\_THREAD\_MESSAGE\( \<message\>, \<memberFxn\> \)|afx\_msg void memberFxn\( WPARAM, LPARAM \);|  
|ON\_REGISTERED\_THREAD\_MESSAGE\( \<nMessageVariable\>, \<memberFxn\> \)|afx\_msg void memberFxn\( WPARAM, LPARAM \);|  
  
## 참고 항목  
 [메시지 맵](../../mfc/reference/message-maps-mfc.md)   
 [WM\_ 메시지 처리기](../../mfc/reference/handlers-for-wm-messages.md)