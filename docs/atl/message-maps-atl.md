---
title: "메시지 맵 (ATL) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message maps, ATL
- ATL, message handlers
ms.assetid: 9e100400-65c7-4a85-8857-4e6cb6dd7340
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 650dcd31e07ef1995f09b0521991d79726b22774
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="message-maps-atl"></a>메시지 맵 (ATL)
메시지 맵 특정 메시지, 명령 또는 알림 처리기 함수를 연결합니다. ATL의를 사용 하 여 [메시지 맵 매크로](../atl/reference/message-map-macros-atl.md), 창에 대 한 메시지 맵을 지정할 수 있습니다. 에 창 프로시저 `CWindowImpl`, `CDialogImpl`, 및 `CContainedWindowT` 창의 메시지를 메시지 맵에 있습니다.  
  
 [메시지 처리기 함수](../atl/message-handler-functions.md) 형식의 추가 인수를 사용할 `BOOL&`합니다. 이 인수는 메시지 처리 된 및로 설정 되어 있는지 여부를 나타냅니다 `TRUE` 기본적으로 합니다. 처리기 함수 다음 인수를 설정할 수 `FALSE` 메시지를 처리 하지 않았음을 나타냅니다. 이 경우 확인 메시지 맵에 처리기 함수에 대 한 ATL 계속 됩니다. 이 인수를 설정 하 여 `FALSE`, 먼저 메시지에 대 한 응답에서 특별 한 조치를 수행 하 고 다음 기본 처리 또는 다른 처리기 함수는 메시지의 처리를 완료할 수 있습니다.  
  
## <a name="chained-message-maps"></a>연결 된 메시지 맵  
 ATL 또한 있습니다 체인 메시지 맵을 다른 클래스에 정의 된 메시지 맵에 처리 메시지를 전송 하는 합니다. 예를 들어 일반 메시지 처리는 별도 클래스에 해당 클래스에 연결 된 모든 창에 대 한 균일 한 동작을 제공 하도록 구현할 수 있습니다. 기본 클래스 또는 클래스의 데이터 멤버를 연결할 수 있습니다.  
  
 ATL 지원 동적 체인는 연결할 수 있도록 다른 개체의 메시지 맵에 런타임 시 합니다. 클래스를 파생 해야 동적 체인을 구현 하려면 [CDynamicChain](../atl/reference/cdynamicchain-class.md)합니다. 그런 다음 선언에서 [CHAIN_MSG_MAP_DYNAMIC](reference/message-map-macros-atl.md#chain_msg_map_dynamic) 메시지 맵에서 매크로입니다. `CHAIN_MSG_MAP_DYNAMIC`개체와 연결 된 메시지 맵이 식별 하는 고유 번호가 필요 합니다. 호출을 통해이 고유한 값을 정의 해야 `CDynamicChain::SetChainEntry`합니다.  
  
 클래스에서 파생 된 메시지 맵을 선언 하는 모든 클래스에 연결할 수 있습니다 [CMessageMap](../atl/reference/cmessagemap-class.md)합니다. `CMessageMap`한 개체가 다른 개체에는 메시지 맵을 노출할 수 있습니다. `CWindowImpl` 에서 이미 파생 `CMessageMap`합니다.  
  
## <a name="alternate-message-maps"></a>대체 메시지 맵  
 마지막으로, ATL 지원 대체 메시지 맵을 사용 하 여 선언 된 [ALT_MSG_MAP](reference/message-map-macros-atl.md#alt_msg_map) 매크로입니다. 각 대체 메시지 맵에 전달 하는 고유 번호도 식별 되 `ALT_MSG_MAP`합니다. 대체 메시지를 사용 하 여 매핑합니다, 그리고 하나의 지도에 여러 창이 메시지를 처리할 수 있습니다. 기본적으로 유의 `CWindowImpl` 대체 메시지 맵을 사용 하지 않습니다. 재정의이 지원을 추가 하는 `WindowProc` 에서 메서드 프로그램 `CWindowImpl`-파생 된 클래스 및 호출 `ProcessWindowMessage` 메시지 맵 식별자를 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [창 구현](../atl/implementing-a-window.md)

