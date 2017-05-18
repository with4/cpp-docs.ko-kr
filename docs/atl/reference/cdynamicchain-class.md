---
title: "CDynamicChain 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicChain
- ATLWIN/ATL::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CallChain
- ATLWIN/ATL::CDynamicChain::RemoveChainEntry
- ATLWIN/ATL::CDynamicChain::SetChainEntry
dev_langs:
- C++
helpviewer_keywords:
- message maps, chaining
- chaining message maps
- CDynamicChain class
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
caps.latest.revision: 21
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
ms.openlocfilehash: 54137760f2c1ee0f93fd8ad21238710f4b6a4a56
ms.contentlocale: ko-kr
ms.lasthandoff: 03/31/2017

---
# <a name="cdynamicchain-class"></a>CDynamicChain 클래스
이 클래스는 메시지 맵의 동적 체인을 지 원하는 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CDynamicChain
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDynamicChain::CDynamicChain](#cdynamicchain)|생성자입니다.|  
|[CDynamicChain:: ~ CDynamicChain](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDynamicChain::CallChain](#callchain)|다른 개체의 메시지 맵에 Windows 메시지를 보냅니다.|  
|[CDynamicChain::RemoveChainEntry](#removechainentry)|메시지 맵 항목을 컬렉션에서 제거합니다.|  
|[CDynamicChain::SetChainEntry](#setchainentry)|메시지 맵 항목을 컬렉션에 추가 하거나 기존 항목을 수정 합니다.|  
  
## <a name="remarks"></a>주의  
 `CDynamicChain`Windows 메시지를 다른 개체의 메시지 맵에 런타임 시 연결을 사용 하도록 설정 하는 메시지 맵의 컬렉션을 관리 합니다.  
  
 에 메시지 맵의 동적 체인에 대 한 지원을 추가 하려면 다음을 수행 합니다.  
  
-   클래스를 파생 `CDynamicChain`합니다. 메시지 맵에 지정는 [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) 매크로 다른 개체의 기본 메시지 맵에 체인으로 연결 합니다.  
  
-   연결 하려는 모든 클래스를 파생 [CMessageMap](../../atl/reference/cmessagemap-class.md)합니다. `CMessageMap`한 개체가 다른 개체에는 메시지 맵을 노출할 수 있습니다.  
  
-   호출 `CDynamicChain::SetChainEntry` 식별 하는 개체 및 메시지 맵에 체인을 해야 하는 하 합니다.  
  
 예를 들어, 클래스에 다음과 같이 정의 됩니다.  
  
 [!code-cpp[NVC_ATL_Windowing # 88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]  
  
 클라이언트는 다음 호출 `CMyWindow::SetChainEntry`:  
  
 [!code-cpp[NVC_ATL_Windowing # 89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]  
  
 여기서 `chainedObj` 는 연결 된 개체 이며에서 파생 된 클래스의 인스턴스가 `CMessageMap`합니다. 이제 경우 `myCtl` 하 여 처리 되지 않은 메시지를 받을 `OnPaint` 또는 `OnSetFocus`, 창 프로시저에 메시지를 보냅니다 `chainedObj`의 기본 메시지 맵.  
  
 메시지 맵 체인에 대 한 자세한 내용은 참조 [메시지 맵](../../atl/message-maps-atl.md) "ATL 창 클래스" 문서  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="callchain"></a>CDynamicChain::CallChain  
 다른 개체의 메시지 맵에 Windows 메시지를 보냅니다.  
  
```
BOOL CallChain(  
    DWORD dwChainID,
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwChainID`  
 [in] 자신의 메시지 맵을 체인으로 연결 된 개체와 연관 된 고유 식별자입니다.  
  
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
  
### <a name="return-value"></a>반환 값  
 **True 이면** 완벽 하 게 처리 되 고, 그렇지 않으면 메시지가 있으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 호출 하 고 창 프로시저에 대 한 `CallChain`를 지정 해야 합니다는 [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) 메시지 맵에서 매크로입니다. 예를 들어 참조는 [CDynamicChain](../../atl/reference/cdynamicchain-class.md) 개요입니다.  
  
 `CallChain`이전 호출을 [SetChainEntry](#setchainentry) 연결 하는 `dwChainID` 개체 및 자신의 메시지 맵을 포함 된 값입니다.  
  
##  <a name="cdynamicchain"></a>CDynamicChain::CDynamicChain  
 생성자입니다.  
  
```
CDynamicChain();
```  
  
##  <a name="dtor"></a>CDynamicChain:: ~ CDynamicChain  
 소멸자입니다.  
  
```
~CDynamicChain();
```  
  
### <a name="remarks"></a>설명  
 할당 된 모든 리소스를 해제합니다.  
  
##  <a name="removechainentry"></a>CDynamicChain::RemoveChainEntry  
 컬렉션에서 지정 된 메시지 맵을 제거합니다.  
  
```
BOOL RemoveChainEntry(DWORD dwChainID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwChainID`  
 [in] 자신의 메시지 맵을 체인으로 연결 된 개체와 연관 된 고유 식별자입니다. 원래 호출을 통해이 값을 정의 하면 [SetChainEntry](#setchainentry)합니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 메시지 맵에 컬렉션에서 성공적으로 제거 됩니다. 그렇지 않으면 **FALSE**합니다.  
  
##  <a name="setchainentry"></a>CDynamicChain::SetChainEntry  
 컬렉션에 지정 된 메시지 맵을 추가합니다.  
  
```
BOOL SetChainEntry(  
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwChainID`  
 [in] 자신의 메시지 맵을 체인으로 연결 된 개체와 연관 된 고유 식별자입니다.  
  
 `pObject`  
 [in] 메시지 맵을 선언 체인으로 연결 된 개체에 대 한 포인터입니다. 이 개체에서 파생 되어야 [CMessageMap](../../atl/reference/cmessagemap-class.md)합니다.  
  
 `dwMsgMapID`  
 [in] 연결 된 개체에서 메시지 맵의 식별자입니다. 기본값은 0으로, 기본 메시지 맵을 사용 하 여 선언 식별 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)합니다. 대체 메시지 맵을 지정을 사용 하 여 선언 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), 전달 `msgMapID`합니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 메시지 맵에 컬렉션에 추가 되는 경우. 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 경우는 `dwChainID` 값이 컬렉션에 이미, 정의와 연결 된 개체 및 메시지 맵에으로 바뀌는 `pObject` 및 `dwMsgMapID`각각. 그렇지 않으면 새 항목이 추가 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWindowImpl 클래스](../../atl/reference/cwindowimpl-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

