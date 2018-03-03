---
title: "CFirePropNotifyEvent 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
dev_langs:
- C++
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c9571ad4ba928c208c6c028f6e30cf7c27c196d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent 클래스
이 클래스는 컨트롤 속성 변경에 대 한 컨테이너의 싱크를 알리기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CFirePropNotifyEvent
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(정적) 컨테이너의 싱크를 컨트롤 속성이 변경 되었음을 알립니다.|  
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(정적) 컨트롤 속성을 변경 하려고 하는 컨테이너의 싱크를에 알립니다.|  
  
## <a name="remarks"></a>설명  
 `CFirePropNotifyEvent`에 컨트롤 속성이 변경 되거나 변경 되려고 하는 컨테이너의 싱크를 알려 주는 두 가지 방법이 있습니다.  
  
 컨트롤을 구현 하는 클래스에서 파생 된 경우 `IPropertyNotifySink`, `CFirePropNotifyEvent` 호출 하는 경우 메서드는 호출 `FireOnRequestEdit` 또는 `FireOnChanged`합니다. 컨트롤 클래스에서 파생 되지 않은 경우 `IPropertyNotifySink`, 이러한 함수에 대 한 호출은 반환 `S_OK`합니다.  
  
 컨트롤을 만드는 방법에 대 한 자세한 내용은 참조는 [ATL 자습서](../../atl/active-template-library-atl-tutorial.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="fireonchanged"></a>CFirePropNotifyEvent::FireOnChanged  
 모두 알려 연결 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) (개체의 모든 연결 지점)에 지정 된 개체 속성이 변경 하는 인터페이스입니다.  
  
```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnk*  
 [in] 에 대 한 포인터는 **IUnknown** 알림을 전송 하는 개체입니다.  
  
 *dispID*  
 [in] 변경 된 속성의 식별자입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 중 하나 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 이 기능은 컨트롤 연결점을 지원 하지 않는 경우에 호출할 수 있습니다.  
  
##  <a name="fireonrequestedit"></a>CFirePropNotifyEvent::FireOnRequestEdit  
 모두 알려 연결 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) (개체의 모든 연결 지점)에 지정 된 개체 속성 변경 되려고 하는 인터페이스입니다.  
  
```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnk*  
 [in] 에 대 한 포인터는 **IUnknown** 알림을 전송 하는 개체입니다.  
  
 *dispID*  
 [in] 변경할 속성의 식별자입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 중 하나 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 이 기능은 컨트롤 연결점을 지원 하지 않는 경우에 호출할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
