---
title: "IPropertyNotifySinkCP 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
dev_langs: C++
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 91e2bcff0b168e9238351cff623f888221b583b2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP 클래스
이 클래스를 노출 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) 연결 가능 개체에 보내기 인터페이스로 인터페이스입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T, class CDV = CComDynamicUnkArray>  
class IPropertyNotifySinkCP 
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```    
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IPropertyNotifySinkCP`합니다.  
  
 `CDV`  
 연결 지점 및 해당 싱크 간의 연결을 관리 하는 클래스입니다. 기본값은 [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), 무제한 연결을 허용 하는 합니다. 사용할 수도 있습니다 [CComUnkArray](../../atl/reference/ccomunkarray-class.md), 고정된 된 수의 연결을 지정 하는 합니다.  
  
## <a name="remarks"></a>설명  
 `IPropertyNotifySinkCP`메서드를 상속 받고 해당 기본 클래스를 통해 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)합니다.  
  
 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) 인터페이스 싱크 개체 속성 변경에 대 한 알림을 받을 수 있습니다. 클래스 `IPropertyNotifySinkCP` 연결 가능 개체에 보내기 인터페이스로이 인터페이스를 노출 합니다. 클라이언트를 구현 해야 합니다는 `IPropertyNotifySink` 싱크의 메서드.  
  
 클래스를 파생 `IPropertyNotifySinkCP` 나타내는 연결점 만들려는 `IPropertyNotifySink` 인터페이스입니다.  
  
 Atl에서 연결 지점을 사용 하는 방법에 대 한 자세한 내용은 문서 참조 [연결점](../../atl/atl-connection-points.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
## <a name="see-also"></a>참고 항목  
 [IConnectionPointImpl 클래스](../../atl/reference/iconnectionpointimpl-class.md)   
 [IConnectionPointContainerImpl 클래스](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
