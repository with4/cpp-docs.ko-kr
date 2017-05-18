---
title: "CMessageMap 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMessageMap
- ATLWIN/ATL::CMessageMap
- ATLWIN/ATL::CMessageMap::ProcessWindowMessage
dev_langs:
- C++
helpviewer_keywords:
- CMessageMap class
- message maps, ATL
- ATL, message handlers
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
caps.latest.revision: 22
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 2726e73d35d01c942ac3d251579fe350be549800
ms.contentlocale: ko-kr
ms.lasthandoff: 03/31/2017

---
# <a name="cmessagemap-class"></a>CMessageMap 클래스
이 클래스를 사용 하면 다른 개체에 의해 액세스 되어야 하는 개체의 메시지 맵.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class ATL_NO_VTABLE CMessageMap
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMessageMap::ProcessWindowMessage](#processwindowmessage)|메시지 맵을 액세스는 `CMessageMap`-클래스를 파생 합니다.|  
  
## <a name="remarks"></a>설명  
 `CMessageMap`개체의 메시지를 허용 하는 추상 기본 클래스에 액세스 하 여 다른 개체에 의해 매핑되는입니다. 개체는 메시지 맵을 노출 하도록 하려면, 해당 클래스에서 파생 되어야 `CMessageMap`합니다.  
  
 ATL 사용 하 여 `CMessageMap` 지원이 포함 된 창과 동적 메시지 맵 체인입니다. 예를 들어 모든 클래스를 포함 하는 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 개체에서 파생 되어야 `CMessageMap`합니다. 다음 코드에서 가져온 것은 [SUBEDIT](../../visual-cpp-samples.md) 샘플. 통해 [CComControl](../../atl/reference/ccomcontrol-class.md), `CAtlEdit` 클래스에서 자동으로 파생 `CMessageMap`합니다.  
  
 [!code-cpp[NVC_ATL_Windowing # 90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]  
  
 때문에 포함된 된 창의 `m_EditCtrl`, 메시지 맵을 포함 하는 클래스에서 사용할 `CAtlEdit` 에서 파생 `CMessageMap`합니다.  
  
 메시지 맵에 대 한 자세한 내용은 참조 [메시지 맵](../../atl/message-maps-atl.md) "ATL 창 클래스" 문서  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="processwindowmessage"></a>CMessageMap::ProcessWindowMessage  
 로 식별 되는 메시지 맵을 액세스 `dwMsgMapID` 에 `CMessageMap`-클래스를 파생 합니다.  
  
```
virtual BOOL ProcessWindowMessage(  
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult,
    DWORD dwMsgMapID) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 [in] 메시지를 받는 창 핸들입니다.  
  
 `uMsg`  
 [in] 창에 전송 하는 메시지입니다.  
  
 `wParam`  
 [in] 추가 메시지 관련 정보입니다.  
  
 `lParam`  
 [in] 추가 메시지 관련 정보입니다.  
  
 `lResult`  
 [out] 메시지 처리의 결과입니다.  
  
 `dwMsgMapID`  
 [in] 메시지를 처리 하는 메시지 맵의 식별자입니다. 기본 메시지 맵을 사용 하 여 선언 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)를 0으로 식별 됩니다. 대체 메시지 맵을 사용 하 여 선언 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map),으로 식별 되 `msgMapID`합니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 메시지를 완전히 처리 된 고, 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 창 프로시저에 의해 호출 된 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 개체 또는 개체를 동적으로 연결 메시지 맵에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicChain 클래스](../../atl/reference/cdynamicchain-class.md)   
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)   
 [클래스 개요](../../atl/atl-class-overview.md)

