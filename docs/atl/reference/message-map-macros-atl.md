---
title: "Message Map Macros (ATL) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Message Map Macros (ATL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이러한 매크로 메시지 맵 및 항목을 정의합니다.  
  
|||  
|-|-|  
|[ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md)|대체 메시지 맵 시작 부분을 표시 합니다.|  
|[BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)|기본 메시지 맵 시작 부분을 표시합니다.|  
|[CHAIN\_MSG\_MAP\_ALT](../Topic/CHAIN_MSG_MAP_ALT.md)|기본 클래스에는 대체 메시지 맵 연결 합니다.|  
|[CHAIN\_MSG\_MAP\_ALT\_MEMBER](../Topic/CHAIN_MSG_MAP_ALT_MEMBER.md)|체인을 대체 메시지 클래스의 데이터 멤버에 매핑됩니다.|  
|[CHAIN\_MSG\_MAP](../Topic/CHAIN_MSG_MAP.md)|기본 메시지 맵 클래스에 연결 합니다.|  
|[CHAIN\_MSG\_MAP\_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md)|런타임에 다른 클래스에 메시지 맵에 체인.|  
|[CHAIN\_MSG\_MAP\_MEMBER](../Topic/CHAIN_MSG_MAP_MEMBER.md)|체인에는 기본 메시지 클래스의 데이터 멤버에 매핑됩니다.|  
|[COMMAND\_CODE\_HANDLER](../Topic/COMMAND_CODE_HANDLER.md)|지도  **WM\_COMMAND** 메시지 알림 코드에 따라 처리기 함수입니다.|  
|[COMMAND\_HANDLER](../Topic/COMMAND_HANDLER.md)|지도  **WM\_COMMAND** 메시지 처리기 함수를 알림 코드와의 메뉴 항목, 컨트롤 또는 액셀러레이터 키 식별자를 기반으로 합니다.|  
|[COMMAND\_ID\_HANDLER](../Topic/COMMAND_ID_HANDLER.md)|지도  **WM\_COMMAND** 메시지 처리기 함수를 메뉴 항목, 컨트롤 또는 액셀러레이터 키 식별자를 기반으로 합니다.|  
|[COMMAND\_RANGE\_CODE\_HANDLER](../Topic/COMMAND_RANGE_CODE_HANDLER.md)|지도  **WM\_COMMAND** 메시지 처리기 함수를 알림 코드 및 연속 범위 컨트롤 식별자를 기반으로 합니다.|  
|[COMMAND\_RANGE\_HANDLER](../Topic/COMMAND_RANGE_HANDLER.md)|지도  **WM\_COMMAND** 메시지 처리기 함수를 연속 된 범위의 컨트롤 식별자를 기반으로 합니다.|  
|[DECLARE\_EMPTY\_MSG\_MAP](../Topic/DECLARE_EMPTY_MSG_MAP.md)|빈 메시지 맵을 구현합니다.|  
|[DEFAULT\_REFLECTION\_HANDLER](../Topic/DEFAULT_REFLECTION_HANDLER.md)|그렇지 않으면 처리 되지 않습니다 리플렉션된 메시지에 대 한 기본 처리기를 제공 합니다.|  
|[END\_MSG\_MAP](../Topic/END_MSG_MAP.md)|메시지 맵의 끝을 표시 합니다.|  
|[FORWARD\_NOTIFICATIONS](../Topic/FORWARD_NOTIFICATIONS.md)|부모 창에 알림 메시지를 전달합니다.|  
|[MESSAGE\_HANDLER](../Topic/MESSAGE_HANDLER.md)|Windows 메시지를 처리기 함수에 매핑합니다.|  
|[MESSAGE\_RANGE\_HANDLER](../Topic/MESSAGE_RANGE_HANDLER.md)|인접 한 Windows 메시지를 처리기 함수에 매핑합니다.|  
|[NOTIFY\_CODE\_HANDLER](../Topic/NOTIFY_CODE_HANDLER.md)|지도  **WM\_NOTIFY** 메시지 알림 코드에 따라 처리기 함수입니다.|  
|[NOTIFY\_HANDLER](../Topic/NOTIFY_HANDLER.md)|지도  **WM\_NOTIFY** 메시지 처리기 함수를 알림 코드 및 컨트롤 식별자를 기준으로 합니다.|  
|[NOTIFY\_ID\_HANDLER](../Topic/NOTIFY_ID_HANDLER.md)|지도  **WM\_NOTIFY** 메시지 처리기 함수는 컨트롤 식별자를 기반으로 합니다.|  
|[NOTIFY\_RANGE\_CODE\_HANDLER](../Topic/NOTIFY_RANGE_CODE_HANDLER.md)|지도  **WM\_NOTIFY** 메시지 처리기 함수를 알림 코드 및 연속 범위 컨트롤 식별자를 기반으로 합니다.|  
|[NOTIFY\_RANGE\_HANDLER](../Topic/NOTIFY_RANGE_HANDLER.md)|지도  **WM\_NOTIFY** 메시지 처리기 함수를 연속 된 범위의 컨트롤 식별자를 기반으로 합니다.|  
|[REFLECT\_NOTIFICATIONS](../Topic/REFLECT_NOTIFICATIONS.md)|알림 메시지는 보낸 다시 창에 반영 됩니다.|  
|[REFLECTED\_COMMAND\_CODE\_HANDLER](../Topic/REFLECTED_COMMAND_CODE_HANDLER.md)|매핑되는 리플 렉 트  **WM\_COMMAND** 메시지 알림 코드에 따라 처리기 함수입니다.|  
|[REFLECTED\_COMMAND\_HANDLER](../Topic/REFLECTED_COMMAND_HANDLER.md)|매핑되는 리플 렉 트  **WM\_COMMAND** 메시지 처리기 함수를 알림 코드와의 메뉴 항목, 컨트롤 또는 액셀러레이터 키 식별자를 기반으로 합니다.|  
|[REFLECTED\_COMMAND\_ID\_HANDLER](../Topic/REFLECTED_COMMAND_ID_HANDLER.md)|매핑되는 리플 렉 트  **WM\_COMMAND** 메시지 처리기 함수를 메뉴 항목, 컨트롤 또는 액셀러레이터 키 식별자를 기반으로 합니다.|  
|[REFLECTED\_COMMAND\_RANGE\_CODE\_HANDLER](../Topic/REFLECTED_COMMAND_RANGE_CODE_HANDLER.md)|매핑되는 리플 렉 트  **WM\_COMMAND** 메시지 처리기 함수를 알림 코드 및 연속 범위 컨트롤 식별자를 기반으로 합니다.|  
|[REFLECTED\_COMMAND\_RANGE\_HANDLER](../Topic/REFLECTED_COMMAND_RANGE_HANDLER.md)|매핑되는 리플 렉 트  **WM\_COMMAND** 메시지 처리기 함수를 연속 된 범위의 컨트롤 식별자를 기반으로 합니다.|  
|[REFLECTED\_NOTIFY\_CODE\_HANDLER](../Topic/REFLECTED_NOTIFY_CODE_HANDLER.md)|매핑되는 리플 렉 트  **WM\_NOTIFY** 메시지 알림 코드에 따라 처리기 함수입니다.|  
|[REFLECTED\_NOTIFY\_HANDLER](../Topic/REFLECTED_NOTIFY_HANDLER.md)|매핑되는 리플 렉 트  **WM\_NOTIFY** 메시지 처리기 함수를 알림 코드 및 컨트롤 식별자를 기준으로 합니다.|  
|[REFLECTED\_NOTIFY\_ID\_HANDLER](../Topic/REFLECTED_NOTIFY_ID_HANDLER.md)|매핑되는 리플 렉 트  **WM\_NOTIFY** 메시지 처리기 함수는 컨트롤 식별자를 기반으로 합니다.|  
|[REFLECTED\_NOTIFY\_RANGE\_CODE\_HANDLER](../Topic/REFLECTED_NOTIFY_RANGE_CODE_HANDLER.md)|매핑되는 리플 렉 트  **WM\_NOTIFY** 메시지 처리기 함수를 알림 코드 및 연속 범위 컨트롤 식별자를 기반으로 합니다.|  
|[REFLECTED\_NOTIFY\_RANGE\_HANDLER](../Topic/REFLECTED_NOTIFY_RANGE_HANDLER.md)|매핑되는 리플 렉 트  **WM\_NOTIFY** 메시지 처리기 함수를 연속 된 범위의 컨트롤 식별자를 기반으로 합니다.|  
  
## 참고 항목  
 [Macros](../../atl/reference/atl-macros.md)