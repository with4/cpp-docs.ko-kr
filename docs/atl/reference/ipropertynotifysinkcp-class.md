---
title: "IPropertyNotifySinkCP 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: feff2467d6d72e9d0a9186dc269f48eb26cbfee2
ms.contentlocale: ko-kr
ms.lasthandoff: 03/17/2017

---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP 클래스
이 클래스는 노출 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) 연결 가능 개체에 보내기 인터페이스로 인터페이스입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
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
  
## <a name="remarks"></a>주의  
 `IPropertyNotifySinkCP`해당 기본 클래스를 통해 모든 메서드를 상속 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)합니다.  
  
 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) 인터페이스는 싱크 개체 속성 변경에 대 한 알림을 받을 수 있습니다. 클래스 `IPropertyNotifySinkCP` 연결 가능 개체에는 송신 인터페이스와이 인터페이스를 노출 합니다. 클라이언트를 구현 해야는 `IPropertyNotifySink` 싱크의 메서드.  
  
 클래스를 파생 `IPropertyNotifySinkCP` 나타내는 연결점을 만들려면는 `IPropertyNotifySink` 인터페이스입니다.  
  
 Atl에서 연결 지점 사용에 대 한 자세한 내용은 문서를 참조 하십시오. [연결점](../../atl/atl-connection-points.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
## <a name="see-also"></a>참고 항목  
 [IConnectionPointImpl 클래스](../../atl/reference/iconnectionpointimpl-class.md)   
 [IConnectionPointContainerImpl 클래스](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

