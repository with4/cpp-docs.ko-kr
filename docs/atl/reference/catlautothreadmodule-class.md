---
title: CAtlAutoThreadModule 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c89d142254909591ebd01bfa859be5488cbfaf6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="catlautothreadmodule-class"></a>CAtlAutoThreadModule 클래스
이 클래스는 COM 서버를 스레드 풀, 아파트 모델을 구현합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```  
  
## <a name="remarks"></a>설명  
 `CAtlAutoThreadModule` 파생 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) 스레드 풀링, 아파트 모델 COM 서버를 구현 합니다. `CAtlAutoThreadModule` 사용 하 여 [CComApartment](../../atl/reference/ccomapartment-class.md) 모듈에서 각 스레드에 대 한 아파트를 관리할 수 있습니다.  
  
 사용 해야 합니다는 [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) 지정 하 여 개체의 클래스 정의에서 매크로 [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) 클래스 팩터리로 합니다. 파생 된 클래스의 단일 인스턴스를 다음 추가 해야 `CAtlAutoThreadModuleT` 같은 `CAtlAutoThreadModule`합니다. 예를 들어:  
  
 `CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`  
  
> [!NOTE]
>  이 클래스는 사용 되지 않는 대신 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) 클래스입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IAtlAutoThreadModule`  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 `CAtlAutoThreadModule`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
## <a name="see-also"></a>참고 항목  
 [CAtlAutoThreadModuleT 클래스](../../atl/reference/catlautothreadmodulet-class.md)   
 [IAtlAutoThreadModule 클래스](../../atl/reference/iatlautothreadmodule-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [모듈 클래스](../../atl/atl-module-classes.md)
