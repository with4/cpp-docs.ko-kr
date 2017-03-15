---
title: "CDynamicChain 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CDynamicChain
- ATL.CDynamicChain
- CDynamicChain
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 4da97d0b3d72400d7e285fde187e6860759900af
ms.lasthandoff: 02/24/2017

---
# <a name="cdynamicchain-class"></a>CDynamicChain 클래스
이 클래스는 메시지 맵의 동적 연결을 지 원하는 메서드를 제공 합니다.  
  
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
 `CDynamicChain`Windows 메시지를 다른 개체의 메시지 맵에 런타임에 지시를 사용 하도록 설정 하는 메시지 맵 컬렉션을 관리 합니다.  
  
 메시지 맵의 동적 연결에 대 한 지원을 추가 하려면 다음을 수행 합니다.  
  
-   클래스를 파생 `CDynamicChain`합니다. 메시지 맵에 지정 된 [CHAIN_MSG_MAP_DYNAMIC](http://msdn.microsoft.com/library/7e5c72b7-cb31-4f3b-8a1b-6293804af220) 매크로를 다른 개체의 기본 메시지 맵에 체인입니다.  
  
-   연결 하려는 모든 클래스를 파생 시키는 [CMessageMap](../../atl/reference/cmessagemap-class.md)합니다. `CMessageMap`한 개체가 다른 개체에는 메시지 맵을 노출할 수 있습니다.  
  
-   호출 `CDynamicChain::SetChainEntry` 을 개체 및 메시지 맵에 사용할 체인을 식별 합니다.  
  
 예를 들어, 클래스에 다음과 같이 정의 됩니다.  
  
 [!code-cpp[NVC_ATL_Windowing #&88;](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]  
  
 클라이언트는 다음 호출 `CMyWindow::SetChainEntry`:  
  
 [!code-cpp[NVC_ATL_Windowing #&89;](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]  
  
 여기서 `chainedObj` 에서 파생 된 클래스의 인스턴스는 연결 된 개체 이며 `CMessageMap`합니다. 이제 경우 `myCtl` 로 처리 되지 않은 메시지를 수신 `OnPaint` 또는 `OnSetFocus`, 창 프로시저에서 메시지를 보냅니다 `chainedObj`의 기본 메시지 맵에 있습니다.  
  
 메시지 맵 연결에 대 한 자세한 내용은 참조 [메시지 맵](../../atl/message-maps-atl.md) 기사 "ATL 창 클래스입니다."  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="a-namecallchaina--cdynamicchaincallchain"></a><a name="callchain"></a>CDynamicChain::CallChain  
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
 [in] 연결 된 개체와 해당 메시지 지도와 관련 된 고유 식별자입니다.  
  
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
 **True 이면** 메시지를 완전히 처리 하 고, 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 호출 하 고 창 프로시저에 대 한 `CallChain`를 지정 해야는 [CHAIN_MSG_MAP_DYNAMIC](http://msdn.microsoft.com/library/7e5c72b7-cb31-4f3b-8a1b-6293804af220) 메시지 맵에서 매크로입니다. 예를 들어 참조는 [CDynamicChain](../../atl/reference/cdynamicchain-class.md) 개요.  
  
 `CallChain`이전 호출 해야 [SetChainEntry](#setchainentry) 연결 하는 `dwChainID` 개체 및 해당 메시지 맵을 사용 하 여 값입니다.  
  
##  <a name="a-namecdynamicchaina--cdynamicchaincdynamicchain"></a><a name="cdynamicchain"></a>CDynamicChain::CDynamicChain  
 생성자입니다.  
  
```
CDynamicChain();
```  
  
##  <a name="a-namedtora--cdynamicchaincdynamicchain"></a><a name="dtor"></a>CDynamicChain:: ~ CDynamicChain  
 소멸자입니다.  
  
```
~CDynamicChain();
```  
  
### <a name="remarks"></a>주의  
 할당 된 모든 리소스를 해제합니다.  
  
##  <a name="a-nameremovechainentrya--cdynamicchainremovechainentry"></a><a name="removechainentry"></a>CDynamicChain::RemoveChainEntry  
 컬렉션에서 지정 된 메시지 맵을 제거합니다.  
  
```
BOOL RemoveChainEntry(DWORD dwChainID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwChainID`  
 [in] 연결 된 개체와 해당 메시지 지도와 관련 된 고유 식별자입니다. 이 값에 대 한 호출을 통해 원래 정의 [SetChainEntry](#setchainentry)합니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 메시지 맵에 컬렉션에서 성공적으로 제거 됩니다. 그렇지 않으면 **FALSE**합니다.  
  
##  <a name="a-namesetchainentrya--cdynamicchainsetchainentry"></a><a name="setchainentry"></a>CDynamicChain::SetChainEntry  
 컬렉션에 지정 된 메시지 맵에 추가합니다.  
  
```
BOOL SetChainEntry(  
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwChainID`  
 [in] 연결 된 개체와 해당 메시지 지도와 관련 된 고유 식별자입니다.  
  
 `pObject`  
 [in] 메시지 맵을 선언 하는 연결 된 개체에 대 한 포인터입니다. 이 개체에서 파생 되어야 [CMessageMap](../../atl/reference/cmessagemap-class.md)합니다.  
  
 `dwMsgMapID`  
 [in] 연결 된 개체에서 메시지 맵의 식별자입니다. 기본값은 0으로 선언 된 기본 메시지 맵에 식별 하는 [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)합니다. 으로 선언 된 대체 메시지 맵을 지정 하려면 [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), 전달 `msgMapID`합니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 메시지 맵에 컬렉션에 성공적으로 추가 되는 경우. 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 하는 경우는 `dwChainID` 컬렉션에 이미 값, 해당 관련된 개체 및 메시지 맵에 바뀝니다 `pObject` 및 `dwMsgMapID`각각. 그렇지 않으면 새 항목이 추가 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWindowImpl 클래스](../../atl/reference/cwindowimpl-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

