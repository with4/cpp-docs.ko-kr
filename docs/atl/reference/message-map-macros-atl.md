---
title: "메시지 맵 매크로 (ATL) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 8097982d6574af2ce1ba592dbead8abf6f6433df
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="message-map-macros-atl"></a>메시지 맵 매크로 (ATL)
이러한 매크로 메시지 맵 및 항목을 정의합니다.  
  
|||  
|-|-|  
|[ALT_MSG_MAP](#alt_msg_map)|대체 메시지 맵의 시작을 표시 합니다.|  
|[BEGIN_MSG_MAP](#begin_msg_map)|기본 메시지 맵의 시작을 표시 합니다.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|기본 클래스에는 대체 메시지 맵에 연결 합니다.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|클래스의 데이터 멤버에는 대체 메시지 맵에 연결 합니다.|  
|[CHAIN_MSG_MAP](#chain_msg_map)|기본 메시지에 대 한 체인의 기본 클래스에 매핑합니다.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|메시지에 대 한 체인 런타임 시 다른 클래스에 매핑합니다.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|기본 메시지를 체인 클래스의 데이터 멤버에 매핑합니다.|  
|[COMMAND_CODE_HANDLER](#command_code_handler)|지도 **WM_COMMAND** 알림 코드를 기반으로 하는 처리기 함수에는 메시지입니다.|  
|[COMMAND_HANDLER](#command_handler)|지도 **WM_COMMAND** 알림 코드 및 메뉴 항목, 컨트롤 또는 엑셀 러 레이 터의 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|지도 **WM_COMMAND** 메뉴 항목, 컨트롤 또는 엑셀 러 레이 터의 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|지도 **WM_COMMAND** 알림 코드와 컨트롤 식별자의 연속 된 범위에 따라 처리기 함수에는 메시지입니다.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|지도 **WM_COMMAND** 제어 식별자의 연속 된 범위에 따라 처리기 함수에는 메시지입니다.|  
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|빈 메시지 맵을 구현합니다.|  
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|그렇지 않으면 처리 되지 않는 리플 렉 트 된 메시지에 대 한 기본 처리기를 제공 합니다.|  
|[END_MSG_MAP](#end_msg_map)|메시지 맵의 끝을 표시 합니다.|  
|[FORWARD_NOTIFICATIONS](#forward_notifications)|부모 창에 알림 메시지를 전달합니다.|  
|[MESSAGE_HANDLER](#message_handler)|Windows 메시지를 처리기 함수에 매핑합니다.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|연속 된 Windows 메시지를 처리기 함수에 매핑합니다.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|지도 **WM_NOTIFY** 알림 코드를 기반으로 하는 처리기 함수에는 메시지입니다.|  
|[NOTIFY_HANDLER](#notify_handler)|지도 **WM_NOTIFY** 알림 코드와 컨트롤 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|지도 **WM_NOTIFY** 컨트롤 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|지도 **WM_NOTIFY** 알림 코드와 컨트롤 식별자의 연속 된 범위에 따라 처리기 함수에는 메시지입니다.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|지도 **WM_NOTIFY** 제어 식별자의 연속 된 범위에 따라 처리기 함수에는 메시지입니다.|  
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|알림 메시지를 다시 보낸 창에 반영 됩니다.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|매핑하는 리플 렉 트 된 **WM_COMMAND** 알림 코드를 기반으로 하는 처리기 함수에는 메시지입니다.|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|매핑하는 리플 렉 트 된 **WM_COMMAND** 알림 코드 및 메뉴 항목, 컨트롤 또는 엑셀 러 레이 터의 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|매핑하는 리플 렉 트 된 **WM_COMMAND** 메뉴 항목, 컨트롤 또는 엑셀 러 레이 터의 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|매핑하는 리플 렉 트 된 **WM_COMMAND** 알림 코드와 컨트롤 식별자의 연속 된 범위에 따라 처리기 함수에는 메시지입니다.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|매핑하는 리플 렉 트 된 **WM_COMMAND** 제어 식별자의 연속 된 범위에 따라 처리기 함수에는 메시지입니다.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|매핑하는 리플 렉 트 된 **WM_NOTIFY** 알림 코드를 기반으로 하는 처리기 함수에는 메시지입니다.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|매핑하는 리플 렉 트 된 **WM_NOTIFY** 알림 코드와 컨트롤 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|매핑하는 리플 렉 트 된 **WM_NOTIFY** 컨트롤 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|매핑하는 리플 렉 트 된 **WM_NOTIFY** 알림 코드와 컨트롤 식별자의 연속 된 범위에 따라 처리기 함수에는 메시지입니다.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|매핑하는 리플 렉 트 된 **WM_NOTIFY** 제어 식별자의 연속 된 범위에 따라 처리기 함수에는 메시지입니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  

##  <a name="alt_msg_map"></a>ALT_MSG_MAP  
 대체 메시지 맵의 시작을 표시 합니다.  
  
```
ALT_MSG_MAP(msgMapID)
```  
  
### <a name="parameters"></a>매개 변수  
 `msgMapID`  
 [in] 메시지 맵 식별자입니다.  
  
### <a name="remarks"></a>주의  
 ATL 각 메시지 맵을 번호로 식별합니다. 기본 메시지 맵에 있습니다 (사용 하 여 선언는 `BEGIN_MSG_MAP` 매크로) 0으로 식별 됩니다. 으로 식별 되는 대체 메시지 맵을 `msgMapID`합니다.  
  
 메시지 맵 창으로 보내는 메시지를 처리 하는 데 사용 됩니다. 예를 들어 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 포함 하는 개체에서 메시지 맵의 식별자를 지정할 수 있습니다. [CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc) 다음이 메시지 맵을 사용 하 여 적절 한 처리기 함수에 또는 다른 메시지 맵에 포함 된 창 메시지를 보내도록 합니다. 처리기 함수를 선언 하는 매크로 목록은 참조 하십시오. [BEGIN_MSG_MAP](#begin_msg_map)합니다.  
  
 항상 메시지 지도와 시작 `BEGIN_MSG_MAP`합니다. 그런 다음 후속 대체 메시지 맵을 선언할 수 있습니다.  
  
 [END_MSG_MAP](#end_msg_map) 매크로 메시지 맵의 끝을 표시 합니다. 항상 인스턴스 중 하나만 `BEGIN_MSG_MAP` 및 `END_MSG_MAP`합니다.  
  
 ATL에서 메시지 맵을 사용 하는 방법에 대 한 자세한 내용은 참조 [메시지 맵](../../atl/message-maps-atl.md)합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 기본 메시지 맵과 각각 하나의 처리기 함수를 포함 하는 하나의 대체 메시지 맵을 보여 줍니다.  
  
 [!code-cpp[NVC_ATL_Windowing #&98;](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 다음 예제에서는 두 개의 대체 메시지 맵을 보여 줍니다. 기본 메시지 맵은 비어 있습니다.  
  
 [!code-cpp[NVC_ATL_Windowing #&99;](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   

##  <a name="begin_msg_map"></a>BEGIN_MSG_MAP  
 기본 메시지 맵의 시작을 표시 합니다.  
  
```
BEGIN_MSG_MAP(theClass)
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 [in] 메시지 맵을 포함 하는 클래스의 이름입니다.  
  
### <a name="remarks"></a>주의  
 [CWindowImpl::WindowProc](cwindowimpl-class.md#windowproc) 기본 메시지 맵을 사용 하 여 창에 전송 된 메시지를 처리 합니다. 메시지 맵 메시지를 적절 한 처리기 함수에 또는 다른 메시지 구조에 지시합니다.  

  
 다음 매크로를 처리기 함수는 메시지를 매핑합니다. 이 함수에 정의 되어 있어야 `theClass`합니다.  
  
|매크로|설명|  
|-----------|-----------------|  
|[MESSAGE_HANDLER](#message_handler)|Windows 메시지를 처리기 함수에 매핑합니다.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|연속 된 Windows 메시지를 처리기 함수에 매핑합니다.|  
|[COMMAND_HANDLER](#command_handler)|지도 **WM_COMMAND** 알림 코드 및 메뉴 항목, 컨트롤 또는 엑셀 러 레이 터의 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|지도 **WM_COMMAND** 메뉴 항목, 컨트롤 또는 엑셀 러 레이 터의 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[COMMAND_CODE_HANDLER](#command_handler)|지도 **WM_COMMAND** 알림 코드를 기반으로 하는 처리기 함수에는 메시지입니다.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|인접 한 범위를 매핑합니다 **WM_COMMAND** 메뉴 항목, 컨트롤 또는 엑셀 러 레이 터의 식별자를 기반으로 메시지를 처리기 함수입니다.|  
|[NOTIFY_HANDLER](#notify_handler)|지도 **WM_NOTIFY** 알림 코드와 컨트롤 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|지도 **WM_NOTIFY** 컨트롤 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|지도 **WM_NOTIFY** 알림 코드를 기반으로 하는 처리기 함수에는 메시지입니다.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|인접 한 범위를 매핑합니다 **WM_NOTIFY** 컨트롤 식별자를 기반으로 메시지를 처리기 함수입니다.|  
  
 다음 매크로 직접 메시지를 다른 메시지 맵. 이 프로세스를 "연결" 라고  
  
|매크로|설명|  
|-----------|-----------------|  
|[CHAIN_MSG_MAP](#chain_msg_map)|기본 메시지에 대 한 체인의 기본 클래스에 매핑합니다.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|기본 메시지를 체인 클래스의 데이터 멤버에 매핑합니다.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|기본 클래스에는 대체 메시지 맵에 연결 합니다.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|클래스의 데이터 멤버에는 대체 메시지 맵에 연결 합니다.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|런타임 시 다른 클래스에 기본 메시지 맵에 체인입니다.|  
  
 다음 매크로 부모 창에서 "반영" 메시지를 직접. 예를 들어 컨트롤 일반적으로 알림 메시지를 해당 부모 창에 대 한 처리를 보내지만 부모 창 컨트롤에 다시 메시지를 반영할 수 있습니다.  
  
|매크로|설명|  
|-----------|-----------------|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|매핑하는 리플 렉 트 된 **WM_COMMAND** 알림 코드 및 메뉴 항목, 컨트롤 또는 엑셀 러 레이 터의 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|매핑하는 리플 렉 트 된 **WM_COMMAND** 메뉴 항목, 컨트롤 또는 엑셀 러 레이 터의 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|매핑하는 리플 렉 트 된 **WM_COMMAND** 알림 코드를 기반으로 하는 처리기 함수에는 메시지입니다.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|매핑하는 리플 렉 트 된 **WM_COMMAND** 제어 식별자의 연속 된 범위에 따라 처리기 함수에는 메시지입니다.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|매핑하는 리플 렉 트 된 **WM_COMMAND** 알림 코드와 컨트롤 식별자의 연속 된 범위에 따라 처리기 함수에는 메시지입니다.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|매핑하는 리플 렉 트 된 **WM_NOTIFY** 알림 코드와 컨트롤 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|매핑하는 리플 렉 트 된 **WM_NOTIFY** 컨트롤 식별자에 따라 처리기 함수에는 메시지입니다.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|매핑하는 리플 렉 트 된 **WM_NOTIFY** 알림 코드를 기반으로 하는 처리기 함수에는 메시지입니다.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|매핑하는 리플 렉 트 된 **WM_NOTIFY** 제어 식별자의 연속 된 범위에 따라 처리기 함수에는 메시지입니다.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|매핑하는 리플 렉 트 된 **WM_NOTIFY** 알림 코드와 컨트롤 식별자의 연속 된 범위에 따라 처리기 함수에는 메시지입니다.|  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&102;](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]  
  
 때는 `CMyExtWindow` 개체를 받습니다는 `WM_PAINT` 메시지가 전송, 메시지는 `CMyExtWindow::OnPaint` 실제 처리 합니다. 경우 `OnPaint` 전송의 기본 메시지 맵에 다음 추가 처리를 메시지는 메시지 필요 나타냅니다 `CMyBaseWindow`합니다.  
  
 기본 메시지 맵을 외에도 대체 메시지 맵을으로 정의할 수 있습니다 [ALT_MSG_MAP](#alt_msg_map)합니다. 항상 메시지 지도와 시작 `BEGIN_MSG_MAP`합니다. 그런 다음 후속 대체 메시지 맵을 선언할 수 있습니다. 다음 예제에서는 기본 메시지 맵과 각각 하나의 처리기 함수를 포함 하는 하나의 대체 메시지 맵을 보여 줍니다.  
  
 [!code-cpp[NVC_ATL_Windowing #&98;](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 다음 예제에서는 두 개의 대체 메시지 맵을 보여 줍니다. 기본 메시지 맵은 비어 있습니다.  
  
 [!code-cpp[NVC_ATL_Windowing #&99;](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
 [END_MSG_MAP](#end_msg_map) 매크로 메시지 맵의 끝을 표시 합니다. 항상 인스턴스 중 하나만 `BEGIN_MSG_MAP` 및 `END_MSG_MAP`합니다.  
  
 ATL에서 메시지 맵을 사용 하는 방법에 대 한 자세한 내용은 참조 [메시지 맵](../../atl/message-maps-atl.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="chain_msg_map_alt"></a>CHAIN_MSG_MAP_ALT  
 메시지 맵 항목을 정의합니다.  
  
```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```  
  
### <a name="parameters"></a>매개 변수  
 `theChainClass`  
 [in] 메시지 맵을 포함 하는 기본 클래스의 이름입니다.  
  
 `msgMapID`  
 [in] 메시지 맵 식별자입니다.  
  
### <a name="remarks"></a>주의  
 `CHAIN_MSG_MAP_ALT`기본 클래스에 대체 메시지 맵에 대 한 메시지를 보냅니다. 이 대체 메시지 맵을와 선언 합니다 [ALT_MSG_MAP(msgMapID)](#alt_msg_map)합니다. 기본 클래스의 기본 메시지 맵에 대 한 메시지를 보낼 (사용 하 여 선언 [BEGIN_MSG_MAP](#begin_msg_map))를 사용 하 여 `CHAIN_MSG_MAP`합니다. 예를 들어 참조 [CHAIN_MSG_MAP](#chain_msg_map)합니다.  
  
> [!NOTE]
>  항상 메시지 지도와 시작 `BEGIN_MSG_MAP`합니다. 포함 된 후속 대체 메시지 맵을 선언할 수 있습니다 `ALT_MSG_MAP`합니다. [END_MSG_MAP](#end_msg_map) 매크로 메시지 맵의 끝을 표시 합니다. 모든 메시지 맵에 인스턴스 중 하나만 있어야 합니다. `BEGIN_MSG_MAP` 및 `END_MSG_MAP`합니다.  
  
 ATL에서 메시지 맵을 사용 하는 방법에 대 한 자세한 내용은 참조 [메시지 맵](../../atl/message-maps-atl.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="chain_msg_map_alt_member"></a>CHAIN_MSG_MAP_ALT_MEMBER  
 메시지 맵 항목을 정의합니다.  
  
```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```  
  
### <a name="parameters"></a>매개 변수  
 `theChainMember`  
 [in] 메시지 맵이 포함 된 데이터 멤버의 이름입니다.  
  
 `msgMapID`  
 [in] 메시지 맵 식별자입니다.  
  
### <a name="remarks"></a>주의  
 `CHAIN_MSG_MAP_ALT_MEMBER`데이터 멤버에는 대체 메시지 맵에 메시지를 전달합니다. 이 대체 메시지 맵을와 선언 합니다 [ALT_MSG_MAP(msgMapID)](#alt_msg_map)합니다. 데이터 멤버의 기본 메시지 맵에 대 한 메시지를 보낼 (사용 하 여 선언 [BEGIN_MSG_MAP](#begin_msg_map))를 사용 하 여 `CHAIN_MSG_MAP_MEMBER`합니다. 예를 들어 참조 [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)합니다.  
  
> [!NOTE]
>  항상 메시지 지도와 시작 `BEGIN_MSG_MAP`합니다. 포함 된 후속 대체 메시지 맵을 선언할 수 있습니다 `ALT_MSG_MAP`합니다. [END_MSG_MAP](#end_msg_map) 매크로 메시지 맵의 끝을 표시 합니다. 모든 메시지 맵에 인스턴스 중 하나만 있어야 합니다. `BEGIN_MSG_MAP` 및 `END_MSG_MAP`합니다.  
  
 ATL에서 메시지 맵을 사용 하는 방법에 대 한 자세한 내용은 참조 [메시지 맵](../../atl/message-maps-atl.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="chain_msg_map"></a>CHAIN_MSG_MAP  
 메시지 맵 항목을 정의합니다.  
  
```
CHAIN_MSG_MAP(theChainClass)
```  
  
### <a name="parameters"></a>매개 변수  
 `theChainClass`  
 [in] 메시지 맵을 포함 하는 기본 클래스의 이름입니다.  
  
### <a name="remarks"></a>주의  
 `CHAIN_MSG_MAP`기본 클래스의 기본 메시지 맵에 대 한 메시지를 보냅니다 (사용 하 여 선언 [BEGIN_MSG_MAP](#begin_msg_map)). 기본 클래스의 대체 메시지 맵에 대 한 메시지를 보낼 (사용 하 여 선언 [ALT_MSG_MAP](#alt_msg_map))를 사용 하 여 [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)합니다.  
  
> [!NOTE]
>  항상 메시지 지도와 시작 `BEGIN_MSG_MAP`합니다. 포함 된 후속 대체 메시지 맵을 선언할 수 있습니다 `ALT_MSG_MAP`합니다. [END_MSG_MAP](#end_msg_map) 매크로 메시지 맵의 끝을 표시 합니다. 모든 메시지 맵에 인스턴스 중 하나만 있어야 합니다. `BEGIN_MSG_MAP` 및 `END_MSG_MAP`합니다.  
  
 ATL에서 메시지 맵을 사용 하는 방법에 대 한 자세한 내용은 참조 [메시지 맵](../../atl/message-maps-atl.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&107;](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]  
  
 이 예제에서는 다음을 설명 합니다.  
  
-   창 프로시저를 사용 하는 경우 `CMyClass`의 기본 메시지 맵 및 `OnPaint` 메시지는 메시지가 전송 되는 핸들 하지 않는 `CMyBaseClass`의 처리에 대 한 기본 메시지 맵.  
  
-   창 프로시저에서 첫 번째 대체 메시지 맵을 사용 하는 경우 `CMyClass`, 모든 메시지에 매핑됩니다. `CMyBaseClass`의 기본 메시지 맵에 있습니다.  
  
-   창 프로시저를 사용 하는 경우 `CMyClass`의 두 번째 대체 메시지 매핑 및 `OnChar` 메시지를 메시지에서 지정 된 대체 메시지 맵 보내지면 핸들 하지 않는 `CMyBaseClass`합니다. `CMyBaseClass`선언 된 메시지 맵이 있어야 합니다 `ALT_MSG_MAP(1)`합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="chain_msg_map_dynamic"></a>CHAIN_MSG_MAP_DYNAMIC  
 메시지 맵 항목을 정의합니다.  
  
```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```  
  
### <a name="parameters"></a>매개 변수  
 *dynaChainID*  
 [in] 개체의 메시지 맵에 대 한 고유 식별자입니다.  
  
### <a name="remarks"></a>주의  
 `CHAIN_MSG_MAP_DYNAMIC`메시지를 다른 개체의 기본 메시지 맵에 런타임에 지시합니다. 와 관련 된 개체 및 해당 메시지 맵을 *dynaChainID*를 통해 정의 하는 [CDynamicChain::SetChainEntry](cdynamicchain-class.md#setchainentry)합니다. 클래스를 파생 해야 `CDynamicChain` 사용 하기 위해 `CHAIN_MSG_MAP_DYNAMIC`합니다. 예를 들어 참조는 [CDynamicChain](../../atl/reference/cdynamicchain-class.md) 개요.  

  
> [!NOTE]
>  항상 메시지 지도와 시작 [BEGIN_MSG_MAP](#begin_msg_map)합니다. 포함 된 후속 대체 메시지 맵을 선언할 수 있습니다 `ALT_MSG_MAP`합니다. [END_MSG_MAP](#end_msg_map) 매크로 메시지 맵의 끝을 표시 합니다. 모든 메시지 맵에 인스턴스 중 하나만 있어야 합니다. `BEGIN_MSG_MAP` 및 `END_MSG_MAP`합니다.  
  
 ATL에서 메시지 맵을 사용 하는 방법에 대 한 자세한 내용은 참조 [메시지 맵](../../atl/message-maps-atl.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="chain_msg_map_member"></a>CHAIN_MSG_MAP_MEMBER  
 메시지 맵 항목을 정의합니다.  
  
```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```  
  
### <a name="parameters"></a>매개 변수  
 `theChainMember`  
 [in] 메시지 맵이 포함 된 데이터 멤버의 이름입니다.  
  
### <a name="remarks"></a>주의  
 `CHAIN_MSG_MAP_MEMBER`데이터 멤버의 기본 메시지 맵에 대 한 메시지를 보냅니다 (사용 하 여 선언 [BEGIN_MSG_MAP](#begin_msg_map)). 데이터 멤버의 대체 메시지 맵에 대 한 메시지를 보낼 (사용 하 여 선언 [ALT_MSG_MAP](#alt_msg_map))를 사용 하 여 [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)합니다.  
  
> [!NOTE]
>  항상 메시지 지도와 시작 `BEGIN_MSG_MAP`합니다. 포함 된 후속 대체 메시지 맵을 선언할 수 있습니다 `ALT_MSG_MAP`합니다. [END_MSG_MAP](#end_msg_map) 매크로 메시지 맵의 끝을 표시 합니다. 모든 메시지 맵에 인스턴스 중 하나만 있어야 합니다. `BEGIN_MSG_MAP` 및 `END_MSG_MAP`합니다.  
  
 ATL에서 메시지 맵을 사용 하는 방법에 대 한 자세한 내용은 참조 [메시지 맵](../../atl/message-maps-atl.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&108;](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]  
  
 이 예제에서는 다음을 설명 합니다.  
  
-   창 프로시저를 사용 하는 경우 `CMyClass`의 기본 메시지 맵 및 `OnPaint` 메시지는 메시지가 전송 되는 핸들 하지 않는 `m_obj`의 처리에 대 한 기본 메시지 맵.  
  
-   창 프로시저에서 첫 번째 대체 메시지 맵을 사용 하는 경우 `CMyClass`, 모든 메시지에 매핑됩니다. `m_obj`의 기본 메시지 맵에 있습니다.  
  
-   창 프로시저를 사용 하는 경우 `CMyClass`의 두 번째 대체 메시지 매핑 및 `OnChar` 메시지를 메시지의 지정 된 대체 메시지 맵을 전송 되는 핸들 하지 않는 `m_obj`합니다. 클래스 `CMyContainedClass` 선언 된 메시지 맵이 있어야 합니다 `ALT_MSG_MAP(1)`합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="command_code_handler"></a>COMMAND_CODE_HANDLER  
 유사한 [COMMAND_HANDLER](#command_handler), 매핑합니다 하지만 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 알림 코드에만 기반 하는 메시지입니다.  
  
```
COMMAND_CODE_HANDLER(code, func)
```  
  
### <a name="parameters"></a>매개 변수  
 `code`  
 [in] 알림 코드입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="command_handler"></a>COMMAND_HANDLER  
 메시지 맵 항목을 정의합니다.  
  
```
COMMAND_HANDLER(id, code, func)
```    
  
### <a name="parameters"></a>매개 변수  
 `id`  
 [in] 메뉴 항목, 컨트롤 또는 엑셀 러 레이 터의 식별자입니다.  
  
 `code`  
 [in] 알림 코드입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  
  
### <a name="remarks"></a>주의  
 `COMMAND_HANDLER`매핑하는 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 알림 코드와 컨트롤 식별자에 따라 지정 된 처리기 함수에는 메시지입니다. 예:  
  
 [!code-cpp[NVC_ATL_Windowing #&119;](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]  
  
 에 지정 된 모든 함수는 `COMMAND_HANDLER` 매크로 다음과 같이 정의 되어야 합니다.  
  
 `LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`  
  
 메시지 맵 집합 `bHandled` 를 **TRUE** 전에 `CommandHandler` 호출 됩니다. 경우 `CommandHandler` 메시지를 완전히 처리 하지 않는 설정 해야 `bHandled` 를 **FALSE** 를 나타내는 메시지에 추가 처리가 필요 합니다.  
  
> [!NOTE]
>  항상 메시지 지도와 시작 [BEGIN_MSG_MAP](#begin_msg_map)합니다. 포함 된 후속 대체 메시지 맵을 선언할 수 있습니다 [ALT_MSG_MAP](#alt_msg_map)합니다. [END_MSG_MAP](#end_msg_map) 매크로 메시지 맵의 끝을 표시 합니다. 모든 메시지 맵에 인스턴스 중 하나만 있어야 합니다. `BEGIN_MSG_MAP` 및 `END_MSG_MAP`합니다.  
  
 외에 `COMMAND_HANDLER`를 사용할 수 있습니다 [MESSAGE_HANDLER](#message_handler) 에 매핑하는 **WM_COMMAND** 식별자 또는 코드에 관계 없이 메시지입니다. 이 경우 `MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)` 모든을 구하고 **WM_COMMAND** 메시지를 `OnHandlerFunction`합니다.  
  
 ATL에서 메시지 맵을 사용 하는 방법에 대 한 자세한 내용은 참조 [메시지 맵](../../atl/message-maps-atl.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="command_id_handler"></a>COMMAND_ID_HANDLER  
 유사한 [COMMAND_HANDLER](#command_handler), 매핑합니다 하지만 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 메뉴 항목, 컨트롤 또는 엑셀 러 레이 터의 식별자에만 기반 하는 메시지입니다.  
  
```
COMMAND_ID_HANDLER(id, func)
```  
  
### <a name="parameters"></a>매개 변수  
 `id`  
 [in] 메뉴 항목, 컨트롤 또는 메시지를 보내는 엑셀 러 레이 터의 식별자입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="command_range_code_handler"></a>COMMAND_RANGE_CODE_HANDLER  
 유사한 [COMMAND_RANGE_HANDLER](#command_range_handler), 매핑합니다 하지만 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 단일 처리기 함수에 다양 한 컨트롤에서에서 특정 알림 코드를 사용 하 여 메시지입니다.  
  
```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```    
  
### <a name="parameters"></a>매개 변수  
 `idFirst`  
 [in] 컨트롤 식별자의 연속 된 범위 시작을 표시 합니다.  
  
 `idLast`  
 [in] 컨트롤 식별자의 연속 된 범위 끝을 표시 합니다.  
  
 `code`  
 [in] 알림 코드입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  
  
### <a name="remarks"></a>주의  
 이 범위는 메뉴 항목, 컨트롤 또는 메시지를 보내는 엑셀 러 레이 터의 식별자를 기반으로 합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="command_range_handler"></a>COMMAND_RANGE_HANDLER  
 유사한 [COMMAND_HANDLER](#command_handler), 매핑합니다 하지만 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 단일 처리기 함수에 다양 한 컨트롤의에서 메시지입니다.  
  
```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```    
  
### <a name="parameters"></a>매개 변수  
 `idFirst`  
 [in] 컨트롤 식별자의 연속 된 범위 시작을 표시 합니다.  
  
 `idLast`  
 [in] 컨트롤 식별자의 연속 된 범위 끝을 표시 합니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  
  
### <a name="remarks"></a>주의  
 이 범위는 메뉴 항목, 컨트롤 또는 메시지를 보내는 엑셀 러 레이 터의 식별자를 기반으로 합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="declare_empty_msg_map"></a>DECLARE_EMPTY_MSG_MAP  
 빈 메시지 맵을 선언합니다.  
  
```
DECLARE_EMPTY_MSG_MAP()
```  
  
### <a name="remarks"></a>주의  
 `DECLARE_EMPTY_MSG_MAP`매크로 호출 하는 편의 매크로 [BEGIN_MSG_MAP](#begin_msg_map) 및 [END_MSG_MAP](#end_msg_map) 빈 메시지 맵을 만듭니다.  
  
 [!code-cpp[NVC_ATL_Windowing #&122;](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]  
  
##  <a name="default_reflection_handler"></a>DEFAULT_REFLECTION_HANDLER  
 리플렉션된 메시지; 받을 자식 창 (컨트롤)에 대 한 기본 처리기를 제공 합니다. 처리기는 처리 되지 않은 메시지를 제대로 전달 됩니다 `DefWindowProc`합니다.  
  
```
DEFAULT_REFLECTION_HANDLER()
```  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="end_msg_map"></a>END_MSG_MAP  
 메시지 맵의 끝을 표시 합니다.  
  
```
END_MSG_MAP()
```  
  
### <a name="remarks"></a>주의  
 항상 사용 하는 [BEGIN_MSG_MAP](#begin_msg_map) 메시지 맵의 시작을 표시 하는 매크로입니다. 사용 하 여 [ALT_MSG_MAP](#alt_msg_map) 후속 대체 메시지 맵을 선언할 수 있습니다.  
  
 항상 인스턴스 중 하나만 `BEGIN_MSG_MAP` 및 `END_MSG_MAP`합니다.  
  
 ATL에서 메시지 맵을 사용 하는 방법에 대 한 자세한 내용은 참조 [메시지 맵](../../atl/message-maps-atl.md)합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 기본 메시지 맵과 각각 하나의 처리기 함수를 포함 하는 하나의 대체 메시지 맵을 보여 줍니다.  
  
 [!code-cpp[NVC_ATL_Windowing #&98;](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 다음 예제에서는 두 개의 대체 메시지 맵을 보여 줍니다. 기본 메시지 맵은 비어 있습니다.  
  
 [!code-cpp[NVC_ATL_Windowing #&99;](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="forward_notifications"></a>FORWARD_NOTIFICATIONS  
 부모 창에 알림 메시지를 전달합니다.  
  
```
FORWARD_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>주의  
 메시지 맵의 일부로이 매크로 지정 합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="message_handler"></a>MESSAGE_HANDLER  
 메시지 맵 항목을 정의합니다.  
  
```
MESSAGE_HANDLER( msg, func )
```  
  
### <a name="parameters"></a>매개 변수  
 `msg`  
 [in] Windows 메시지입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  
  
### <a name="remarks"></a>주의  
 `MESSAGE_HANDLER`지정 된 처리기 함수에는 Windows 메시지를 매핑합니다.  
  
 에 지정 된 모든 함수는 `MESSAGE_HANDLER` 매크로 다음과 같이 정의 되어야 합니다.  
  
 `LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`  
  
 메시지 맵 집합 `bHandled` 를 **TRUE** 전에 `MessageHandler` 호출 됩니다. 경우 `MessageHandler` 메시지를 완전히 처리 하지 않는 설정 해야 `bHandled` 를 **FALSE** 를 나타내는 메시지에 추가 처리가 필요 합니다.  
  
> [!NOTE]
>  항상 메시지 지도와 시작 [BEGIN_MSG_MAP](#begin_msg_map)합니다. 포함 된 후속 대체 메시지 맵을 선언할 수 있습니다 [ALT_MSG_MAP](#alt_msg_map)합니다. [END_MSG_MAP](#end_msg_map) 매크로 메시지 맵의 끝을 표시 합니다. 모든 메시지 맵에 인스턴스 중 하나만 있어야 합니다. `BEGIN_MSG_MAP` 및 `END_MSG_MAP`합니다.  
  
 외에 `MESSAGE_HANDLER`를 사용할 수 있습니다 [COMMAND_HANDLER](#command_handler) 및 [NOTIFY_HANDLER](#notify_handler) 매핑할 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 및 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) 각각 메시지입니다.  
  
 ATL에서 메시지 맵을 사용 하는 방법에 대 한 자세한 내용은 참조 [메시지 맵](../../atl/message-maps-atl.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&129;](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="message_range_handler"></a>MESSAGE_RANGE_HANDLER  
 유사한 [MESSAGE_HANDLER](#message_handler), 다양 한 Windows 메시지를 단일 처리기 함수에 매핑되므로 합니다.  
  
```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```  
  
### <a name="parameters"></a>매개 변수  
 *msgFirst*  
 [in] 메시지의 연속 된 범위 시작을 표시 합니다.  
  
 *msgLast*  
 [in] 메시지의 연속 된 범위 끝을 표시 합니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="notify_code_handler"></a>NOTIFY_CODE_HANDLER  
 유사한 [NOTIFY_HANDLER](#notify_handler), 매핑합니다 하지만 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) 알림 코드에만 기반 하는 메시지입니다.  
  
```
NOTIFY_CODE_HANDLER(cd, func)
```  
  
### <a name="parameters"></a>매개 변수  
 `cd`  
 [in] 알림 코드입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="notify_handler"></a>NOTIFY_HANDLER  
 메시지 맵 항목을 정의합니다.  
  
```
NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>매개 변수  
 `id`  
 [in] 메시지를 전송 하는 컨트롤의 식별자입니다.  
  
 `cd`  
 [in] 알림 코드입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  
  
### <a name="remarks"></a>주의  
 `NOTIFY_HANDLER`매핑하는 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) 알림 코드와 컨트롤 식별자에 따라 지정 된 처리기 함수에는 메시지입니다.  
  
 에 지정 된 모든 함수는 `NOTIFY_HANDLER` 매크로 다음과 같이 정의 되어야 합니다.  
  
 `LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`  
  
 메시지 맵 집합 `bHandled` 를 **TRUE** 전에 `NotifyHandler` 호출 됩니다. 경우 `NotifyHandler` 메시지를 완전히 처리 하지 않는 설정 해야 `bHandled` 를 **FALSE** 를 나타내는 메시지에 추가 처리가 필요 합니다.  
  
> [!NOTE]
>  항상 메시지 지도와 시작 [BEGIN_MSG_MAP](#begin_msg_map)합니다. 포함 된 후속 대체 메시지 맵을 선언할 수 있습니다 [ALT_MSG_MAP](#alt_msg_map)합니다. [END_MSG_MAP](#end_msg_map) 매크로 메시지 맵의 끝을 표시 합니다. 모든 메시지 맵에 인스턴스 중 하나만 있어야 합니다. `BEGIN_MSG_MAP` 및 `END_MSG_MAP`합니다.  
  
 외에 `NOTIFY_HANDLER`를 사용할 수 있습니다 [MESSAGE_HANDLER](#message_handler) 에 매핑하는 **WM_NOTIFY** 식별자 또는 코드에 관계 없이 메시지입니다. 이 경우 `MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)` 모든을 구하고 **WM_NOTIFY** 메시지를 `OnHandlerFunction`합니다.  
  
 ATL에서 메시지 맵을 사용 하는 방법에 대 한 자세한 내용은 참조 [메시지 맵](../../atl/message-maps-atl.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&130;](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="notify_id_handler"></a>NOTIFY_ID_HANDLER  
 비슷합니다 [NOTIFY_HANDLER](#notify_handler), 매핑합니다 하지만 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) 메시지 식별자를 기준만 제어 합니다.  
  
```
NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>매개 변수  
 `id`  
 [in] 메시지를 전송 하는 컨트롤의 식별자입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="notify_range_code_handler"></a>NOTIFY_RANGE_CODE_HANDLER  
 유사한 [NOTIFY_RANGE_HANDLER](#notify_range_handler), 매핑합니다 하지만 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) 단일 처리기 함수에 다양 한 컨트롤에서에서 특정 알림 코드를 사용 하 여 메시지입니다.  
  
```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```  
  
### <a name="parameters"></a>매개 변수  
 `idFirst`  
 [in] 컨트롤 식별자의 연속 된 범위 시작을 표시 합니다.  
  
 `idLast`  
 [in] 컨트롤 식별자의 연속 된 범위 끝을 표시 합니다.  
  
 `cd`  
 [in] 알림 코드입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  
  
### <a name="remarks"></a>주의  
 이 범위에서 메시지를 전송 하는 컨트롤의 식별자를 기반으로 합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="notify_range_handler"></a>NOTIFY_RANGE_HANDLER  
 유사한 [NOTIFY_HANDLER](#notify_handler), 매핑합니다 하지만 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) 단일 처리기 함수에 다양 한 컨트롤의에서 메시지입니다.  
  
```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>매개 변수  
 `idFirst`  
 [in] 컨트롤 식별자의 연속 된 범위 시작을 표시 합니다.  
  
 `idLast`  
 [in] 컨트롤 식별자의 연속 된 범위 끝을 표시 합니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  
  
### <a name="remarks"></a>주의  
 이 범위에서 메시지를 전송 하는 컨트롤의 식별자를 기반으로 합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="reflect_notifications"></a>REFLECT_NOTIFICATIONS  
 알림 메시지를 다시 보낸 자식 창 (컨트롤)를 반영 합니다.  
  
```
REFLECT_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>주의  
 부모 창의 메시지 맵에의 일부로이 매크로 지정 합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="reflected_command_code_handler"></a>REFLECTED_COMMAND_CODE_HANDLER  
 유사한 [COMMAND_CODE_HANDLER](#command_code_handler), 있지만 부모 창에서 반영 하는 명령에 매핑합니다.  
  
```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```  
  
### <a name="parameters"></a>매개 변수  
 `code`  
 [in] 알림 코드입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
   
##  <a name="reflected_command_handler"></a>REFLECTED_COMMAND_HANDLER  
 유사한 [COMMAND_HANDLER](#command_handler), 있지만 부모 창에서 반영 하는 명령에 매핑합니다.  
  
```
REFLECTED_COMMAND_HANDLER( id, code, func )
```  
  
### <a name="parameters"></a>매개 변수  
 `id`  
 [in] 메뉴 항목, 컨트롤 또는 엑셀 러 레이 터의 식별자입니다.  
  
 `code`  
 [in] 알림 코드입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  

##  <a name="reflected_command_id_handler"></a>REFLECTED_COMMAND_ID_HANDLER  
 유사한 [COMMAND_ID_HANDLER](#command_id_handler), 있지만 부모 창에서 반영 하는 명령에 매핑합니다.  
  
```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>매개 변수  
 `id`  
 [in] 메뉴 항목, 컨트롤 또는 엑셀 러 레이 터의 식별자입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  

##  <a name="reflected_command_range_code_handler"></a>REFLECTED_COMMAND_RANGE_CODE_HANDLER  
 유사한 [COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler), 있지만 부모 창에서 반영 하는 명령에 매핑합니다.  
  
```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```  
  
### <a name="parameters"></a>매개 변수  
 `idFirst`  
 [in] 컨트롤 식별자의 연속 된 범위 시작을 표시 합니다.  
  
 `idLast`  
 [in] 컨트롤 식별자의 연속 된 범위 끝을 표시 합니다.  
  
 `code`  
 [in] 알림 코드입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  

##  <a name="reflected_command_range_handler"></a>REFLECTED_COMMAND_RANGE_HANDLER  
 유사한 [COMMAND_RANGE_HANDLER](#command_range_handler), 있지만 부모 창에서 반영 하는 명령에 매핑합니다.  
  
```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>매개 변수  
 `idFirst`  
 [in] 컨트롤 식별자의 연속 된 범위 시작을 표시 합니다.  
  
 `idLast`  
 [in] 컨트롤 식별자의 연속 된 범위 끝을 표시 합니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  

##  <a name="reflected_notify_code_handler"></a>REFLECTED_NOTIFY_CODE_HANDLER  
 유사한 [NOTIFY_CODE_HANDLER](#notify_code_handler), 있지만 부모 창에서 반영 하는 알림을 매핑합니다.  
  
```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```  
  
### <a name="parameters"></a>매개 변수  
 `cd`  
 [in] 알림 코드입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  

##  <a name="reflected_notify_handler"></a>REFLECTED_NOTIFY_HANDLER  
 유사한 [NOTIFY_HANDLER](#notify_handler), 있지만 부모 창에서 반영 하는 알림을 매핑합니다.  
  
```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>매개 변수  
 `id`  
 [in] 메뉴 항목, 컨트롤 또는 엑셀 러 레이 터의 식별자입니다.  
  
 `cd`  
 [in] 알림 코드입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  

##  <a name="reflected_notify_id_handler"></a>REFLECTED_NOTIFY_ID_HANDLER  
 유사한 [NOTIFY_ID_HANDLER](#notify_id_handler), 있지만 부모 창에서 반영 하는 알림을 매핑합니다.  
  
```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>매개 변수  
 `id`  
 [in] 메뉴 항목, 컨트롤 또는 엑셀 러 레이 터의 식별자입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  

##  <a name="reflected_notify_range_code_handler"></a>REFLECTED_NOTIFY_RANGE_CODE_HANDLER  
 유사한 [NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler), 있지만 부모 창에서 반영 하는 알림을 매핑합니다.  
  
```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```    
  
### <a name="parameters"></a>매개 변수  
 `idFirst`  
 [in] 컨트롤 식별자의 연속 된 범위 시작을 표시 합니다.  
  
 `idLast`  
 [in] 컨트롤 식별자의 연속 된 범위 끝을 표시 합니다.  
  
 `cd`  
 [in] 알림 코드입니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h   
  
##  <a name="reflected_notify_range_handler"></a>REFLECTED_NOTIFY_RANGE_HANDLER  
 유사한 [NOTIFY_RANGE_HANDLER](#notify_range_handler), 있지만 부모 창에서 반영 하는 알림을 매핑합니다.  
  
```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>매개 변수  
 `idFirst`  
 [in] 컨트롤 식별자의 연속 된 범위 시작을 표시 합니다.  
  
 `idLast`  
 [in] 컨트롤 식별자의 연속 된 범위 끝을 표시 합니다.  
  
 `func`  
 [in] 메시지-처리기 함수의 이름입니다.  
  
## <a name="see-also"></a>참고 항목  
 [매크로](../../atl/reference/atl-macros.md)

