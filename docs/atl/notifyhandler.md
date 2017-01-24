---
title: "NotifyHandler | Microsoft Docs"
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
  - "NotifyHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NotifyHandler function"
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# NotifyHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

세 번째 매개 변수로 식별 되는 함수의 이름에 `NOTIFY_HANDLER` 메시지 맵의 매크로.  
  
## 구문  
  
```  
  
      LRESULT   
      NotifyHandler  
      (  
   int idCtrl,  
   LPNMHDR pnmh,  
   BOOL& bHandled   
);  
```  
  
#### 매개 변수  
 `idCtrl`  
 메시지를 보내는 컨트롤의 식별자입니다.  
  
 *pnmh*  
 주소는  [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) 알림 코드 및 추가 정보를 포함 하는 구조입니다.  일부 알림 메시지를 갖고 있는 더 큰 구조를이 매개 변수를 가리키는 있는  **NMHDR** 구조체의 첫 번째 구성원으로.  
  
 `bHandled`  
 메시지 맵 세트 `bHandled` 에  **TRUE** 전에  *NotifyHandler* 라고 합니다.  경우  *NotifyHandler* 메시지를 완전히 처리 하지 않는 설정 해야 `bHandled` 에  **FALSE** 필요 합니다 라는 메시지가 더 이상 처리를 나타냅니다.  
  
## 반환 값  
 메시지 처리의 결과입니다.  성공한 경우 0입니다.  
  
## 설명  
 이 메시지 처리기에서 메시지 맵을 사용 하는 예제를 보려면  [NOTIFY\_HANDLER](../Topic/NOTIFY_HANDLER.md).  
  
## 참고 항목  
 [Implementing a Window](../atl/implementing-a-window.md)   
 [Message Maps](../atl/message-maps-atl.md)   
 [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)