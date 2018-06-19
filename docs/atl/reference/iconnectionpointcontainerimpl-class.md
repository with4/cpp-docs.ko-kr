---
title: IConnectionPointContainerImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
dev_langs:
- C++
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af5e8b1bc1af0a515cc8fad0500c3f7d040b1eb9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361172"
---
# <a name="iconnectionpointcontainerimpl-class"></a>IConnectionPointContainerImpl 클래스
이 클래스의 컬렉션을 관리 하는 연결 지점 컨테이너를 구현 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>  
class ATL_NO_VTABLE IConnectionPointContainerImpl 
   : public IConnectionPointContainer
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IConnectionPointContainerImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|연결 가능 개체에서 지원 되는 연결점을 반복 하는 열거자를 만듭니다.|  
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|지정한 IID를 지 원하는 연결 지점에 대 한 인터페이스 포인터를 검색 합니다.|  
  
## <a name="remarks"></a>설명  
 `IConnectionPointContainerImpl` 컬렉션을 관리 하는 연결 지점 컨테이너를 구현 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 개체입니다. `IConnectionPointContainerImpl` 연결 가능 개체에 대 한 자세한 정보를 검색 하는 클라이언트가 호출할 수 있는 두 가지 방법을 제공 합니다.  
  
- `EnumConnectionPoints` 클라이언트가 어떤 나가는 개체가 지 원하는 인터페이스를 확인할 수 있습니다.  
  
- `FindConnectionPoint` 클라이언트가 개체가 특정 송신 인터페이스를 지원 하는지 여부를 확인할 수 있습니다.  
  
 Atl에서 연결 지점을 사용 하는 방법에 대 한 내용은 문서 참조 [연결점](../../atl/atl-connection-points.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IConnectionPointContainer`  
  
 `IConnectionPointContainerImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="enumconnectionpoints"></a>  IConnectionPointContainerImpl::EnumConnectionPoints  
 연결 가능 개체에서 지원 되는 연결점을 반복 하는 열거자를 만듭니다.  
  
```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```  
  
### <a name="remarks"></a>설명  
 참조 [IConnectionPointContainer::EnumConnectionPoints](http://msdn.microsoft.com/library/windows/desktop/ms682460) in the Windows SDK입니다.  
  
##  <a name="findconnectionpoint"></a>  IConnectionPointContainerImpl::FindConnectionPoint  
 지정한 IID를 지 원하는 연결 지점에 대 한 인터페이스 포인터를 검색 합니다.  
  
```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```  
  
### <a name="remarks"></a>설명  
 참조 [IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) in the Windows SDK입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)   
 [클래스 개요](../../atl/atl-class-overview.md)
