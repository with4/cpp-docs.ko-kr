---
title: "구현 CComObject, CComAggObject, 및 CComPolyObject | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CComPolyObject
- CComAggObject
- CComObject
dev_langs: C++
helpviewer_keywords:
- CComPolyObject class, implementing
- CreateInstance method
- CComAggObject class
- CComObject class, implementing
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 54f237a629c4af9ea7ae30aeca21c03786abcd97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-ccomobject-ccomaggobject-and-ccompolyobject"></a>CComObject, CComAggObject, 및 CComPolyObject 구현
템플릿 클래스 [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), 및 [CComPolyObject](../atl/reference/ccompolyobject-class.md) 상속 체인의 가장 많이 파생 된 클래스는 항상 합니다. 책임의 메서드 중 일부를 처리 하는 **IUnknown**: `QueryInterface`, `AddRef`, 및 **릴리스**합니다. 또한 `CComAggObject` 및 `CComPolyObject` (집계 개체에 대해 사용) 하는 경우 특별 한 참조 횟수를 제공 하 고 `QueryInterface` 알 수 없는 내부에 필요한 의미 체계입니다.  
  
 여부를 `CComObject`, `CComAggObject`, 또는 `CComPolyObject` 사용 다음 매크로 중 하나 (또는 없음)를 선언 하는지 여부에 따라 달라 집니다.  
  
|매크로|효과|  
|-----------|------------|  
|`DECLARE_NOT_AGGREGATABLE`|항상 사용 하 여 `CComObject`합니다.|  
|`DECLARE_AGGREGATABLE`|사용 하 여 `CComAggObject` 개체가 집계 되는 경우 및 `CComObject` 없는 경우. `CComCoClass`이 매크로 포함 하므로 아닌 경우는 **DECLARE_\*_AGGREGATABLE** 매크로 클래스에 선언 된이 기본값으로 사용 됩니다.|  
|`DECLARE_ONLY_AGGREGATABLE`|항상 사용 하 여 `CComAggObject`합니다. 개체가 집계 되지 않은 경우 오류를 반환 합니다.|  
|`DECLARE_POLY_AGGREGATABLE`|인스턴스를 만들고 ATL **CComPolyObject\<CYourClass >** 때 **IClassFactory::CreateInstance** 호출 됩니다. 만드는 동안 알 수 없는 외부의 값이 확인 됩니다. 이 경우 **NULL**, **IUnknown** 집계 되지 않은 원시 개체에 대 한 구현 됩니다. 알 수 없는 외부 없으면 **NULL**, **IUnknown** 집계 개체에 대 한 구현 됩니다.|  
  
 사용 시의 이점은 `CComAggObject` 및 `CComObject` 는의 구현 **IUnknown** 생성 되는 개체의 종류에 대 한 최적화 됩니다. 예를 들어 집계 되지 않은 원시 개체 하기만 참조 횟수를 알 수 없는 내부에 대 한 참조 횟수와 알 수 없는 외부에 대 한 포인터를 필요로 하는 집합체 동안 있습니다.  
  
 사용 시의 이점은 `CComPolyObject` 두는 것을 방지 하는 `CComAggObject` 및 `CComObject` 모듈 집계 및 집계 되지 않은 원시 경우를 처리 합니다. 단일 `CComPolyObject` 두 경우 모두 처리 하는 개체입니다. 이 모듈에 존재 하 vtable의 복사본이 한 개만 및 함수 중 하나의 복사본을 의미 합니다. Vtable이 큰 경우 모듈 크기가 상당히 줄어들 수 있습니다이 있습니다. 그러나 vtable 작으면를 사용 하 여 `CComPolyObject` 조금 더 큰 모듈 크기는 집계 또는 집계 되지 않은 원시 개체에 대 한 최적화 되어 있지 않으므로 발생할 수 있습니다는 `CComAggObject` 및 `CComObject`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL COM 개체의 기본 사항](../atl/fundamentals-of-atl-com-objects.md)   
 [집계 및 클래스 팩터리 매크로](../atl/reference/aggregation-and-class-factory-macros.md)

