---
title: "Message Maps (ATL) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, 메시지 처리기"
  - "message maps, ATL"
ms.assetid: 9e100400-65c7-4a85-8857-4e6cb6dd7340
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Message Maps (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

메시지 맵은 처리기 함수는 특정 메시지, 명령 또는 알림 연결합니다.  ATL의 사용 하 여  [메시지 맵 매크로](../atl/reference/message-map-macros-atl.md), 창의 메시지 맵을 지정할 수 있습니다.  창 프로시저에서 `CWindowImpl`, `CDialogImpl`, 및 `CContainedWindowT` 에 자신의 메시지 맵 창 메시지를 직접.  
  
 [메시지 처리기 함수](../atl/message-handler-functions.md) 추가 인수 형식의 사용할 `BOOL&`.  이 인수는 메시지 처리, 설정 된 여부를 나타내는 `TRUE` 기본적으로.  처리기 함수는 다음 인수를 설정할 수 있습니다 `FALSE` 메시지를 처리 했음을 나타낼 수 있습니다.  이 경우 ATL 메시지 맵에 추가 처리기 함수를 찾으려면 계속 됩니다.  이 인수를 설정 여 `FALSE`, 먼저 어떤 작업을 수행 하는 메시지에 응답 하 고 다음 기본 처리 나 다른 처리기 함수는 메시지 처리를 완료할 수 있도록 수 있습니다.  
  
## 연결 된 메시지 맵  
 ATL에서는 메시지 맵과 체인 다른 클래스에 정의 된 메시지 맵 처리 메시지를 지시 하는 있습니다.  예를 들어, 일반적인 메시지 해당 클래스에 연결 된 모든 창에 대해 일관 된 동작을 제공 하는 별도 클래스에서 처리를 구현할 수 있습니다.  기본 클래스 또는 클래스의 데이터 멤버에 연결할 수 있습니다.  
  
 ATL에서는 동적 체인 개체의 메시지 맵에 연결할 런타임에 있습니다 지원 합니다.  동적 연결을 구현 하려면 클래스에서 파생 되어야  [CDynamicChain](../atl/reference/cdynamicchain-class.md).  다음 선언 된  [CHAIN\_MSG\_MAP\_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md) 메시지 맵의 매크로.  `CHAIN_MSG_MAP_DYNAMIC`개체와 메시지 맵이 체인화 하는 식별 하는 고유 번호를 필요 합니다.  이 호출을 통해 고유한 값을 정의 해야 `CDynamicChain::SetChainEntry`.  
  
 클래스에서 파생 되는 경우 메시지 맵을 선언 하는 클래스에 연결할 수 있습니다  [CMessageMap](../atl/reference/cmessagemap-class.md).  `CMessageMap`해당 메시지 맵을 다른 개체를 노출 하는 개체 수 있습니다.  이때 `CWindowImpl` 이미 파생 `CMessageMap`.  
  
## 대체 메시지 맵  
 마지막으로, 대체 메시지 맵을 선언, ATL을 지 원하는  [ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md) 매크로.  각 대체 메시지 맵을 전달 하는 고유 번호로 식별 됩니다 `ALT_MSG_MAP`.  대체 메시지를 사용 하 여, 하나의 지도에 여러 windows 메시지를 처리할 수 있습니다.  참고 기본적으로 `CWindowImpl` 대체 메시지 맵을 사용 하지 않습니다.  재정의이 지원을 추가 하는 `WindowProc` 에서 메서드를 `CWindowImpl`\-파생 된 클래스와 호출 `ProcessWindowMessage` 메시지 맵의 식별자.  
  
## 참고 항목  
 [Implementing a Window](../atl/implementing-a-window.md)