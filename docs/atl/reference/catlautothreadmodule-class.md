---
title: "CAtlAutoThreadModule 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CAtlAutoThreadModule
- CAtlAutoThreadModule
- ATL::CAtlAutoThreadModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
caps.latest.revision: 19
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
ms.openlocfilehash: 09f4a7061ce1e4a09d0d27bd90dfcc16a37f4d5b
ms.lasthandoff: 02/24/2017

---
# <a name="catlautothreadmodule-class"></a>CAtlAutoThreadModule 클래스
이 클래스는 COM 서버를 스레드 풀링, 아파트 모델을 구현합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```  
  
## <a name="remarks"></a>주의  
 `CAtlAutoThreadModule`파생 되며 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) 스레드 풀링, 아파트 모델 COM 서버를 구현 합니다. `CAtlAutoThreadModule`사용 하 여 [CComApartment](../../atl/reference/ccomapartment-class.md) 모듈에서 각 스레드에 대 한 아파트를 관리할 수 있습니다.  
  
 사용 해야는 [DECLARE_CLASSFACTORY_AUTO_THREAD](http://msdn.microsoft.com/library/19d7105e-03e8-4412-9f5e-5384c8a5e18f) 지정 하 여 개체의 클래스 정의에 매크로 [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) 클래스 팩터리로 합니다. 파생 된 클래스의 단일 인스턴스를 추가 해야 `CAtlAutoThreadModuleT` 와 같은 `CAtlAutoThreadModule`합니다. 예:  
  
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
