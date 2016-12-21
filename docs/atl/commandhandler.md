---
title: "CommandHandler | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CommandHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CommandHandler function"
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CommandHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CommandHandler`세 번째 매개 변수로 식별 되는 함수는 `COMMAND_HANDLER` 메시지 맵의 매크로.  
  
## 구문  
  
```  
  
      LRESULT   
      CommandHandler  
      (  
   WORD wNotifyCode,  
   WORD wID,  
   HWND hWndCtl,  
   BOOL& bHandled   
);  
```  
  
#### 매개 변수  
 `wNotifyCode`  
 알림 코드입니다.  
  
 *wID*  
 메뉴 항목, 컨트롤 또는 액셀러레이터 키 식별자입니다.  
  
 *hWndCtl*  
 창 컨트롤에 대 한 핸들입니다.  
  
 `bHandled`  
 메시지 맵 세트 `bHandled` 에  **TRUE** 전에 `CommandHandler` 라고 합니다.  경우 `CommandHandler` 메시지를 완전히 처리 하지 않는 설정 해야 `bHandled` 에  **FALSE** 필요 합니다 라는 메시지가 더 이상 처리를 나타냅니다.  
  
## 반환 값  
 메시지 처리의 결과입니다.  성공한 경우 0입니다.  
  
## 설명  
 이 메시지 처리기에서 메시지 맵을 사용 하는 예제를 보려면  [COMMAND\_HANDLER](../Topic/COMMAND_HANDLER.md).  
  
## 참고 항목  
 [Implementing a Window](../atl/implementing-a-window.md)   
 [Message Maps](../atl/message-maps-atl.md)   
 [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)