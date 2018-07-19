---
title: IUnknown 구현 클래스 (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.Iunknown
dev_langs:
- C++
helpviewer_keywords:
- IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b4cd2f2473249271285d6b8812dac1b924e5a172
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848537"
---
# <a name="iunknown-implementation-classes"></a>IUnknown 구현 클래스
다음 클래스 구현 `IUnknown` 및 관련 메서드에서:  
  
-   [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) 집계 및 집계 개체에 대 한 계산 참조를 관리 합니다. 스레딩 모델을 지정할 수 있습니다.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) 집계 및 집계 개체에 대 한 계산 참조를 관리 합니다. 스레딩 모델이 서버의 기본값을 사용 합니다.  
  
-   [CComAggObject](../atl/reference/ccomaggobject-class.md) 구현 `IUnknown` 집계 개체에 대 한 합니다.  
  
-   [CComObject](../atl/reference/ccomobject-class.md) 구현 `IUnknown` 집계 개체에 대 한 합니다.  
  
-   [CComPolyObject](../atl/reference/ccompolyobject-class.md) 구현 `IUnknown` 집계 및 집계 개체에 대 한 합니다. 사용 하 여 `CComPolyObject` 둘 다 하지 않아도 `CComAggObject` 고 `CComObject` 모듈에서입니다. 단일 `CComPolyObject` 집계 및 집계 하는 경우를 처리 하는 개체입니다.  
  
-   [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) 구현 `IUnknown` 모듈 잠금 횟수를 수정 하지 않고 집계 개체에 대 한 합니다.  
  
-   [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) 구현 `IUnknown` 분리 인터페이스입니다.  
  
-   [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) 구현 `IUnknown` "캐시" 분리 인터페이스에 대 한 합니다.  
  
-   [CComContainedObject](../atl/reference/ccomcontainedobject-class.md) 구현 `IUnknown` 집계 또는 분리 인터페이스의 내부 개체에 대 한 합니다.  
  
-   [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) 관리 개체를 확인 하려면 모듈에서 참조 횟수를 삭제할 수 없습니다.  
  
-   [CComObjectStack](../atl/reference/ccomobjectstack-class.md) 의 기본 구현을 사용 하 여 임시 COM 개체를 만들고 `IUnknown`합니다.  
  
## <a name="related-articles"></a>관련 문서  
 [ATL COM 개체 기본 사항](../atl/fundamentals-of-atl-com-objects.md)  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../atl/atl-class-overview.md)   
 [집계 및 클래스 팩터리 매크로](../atl/reference/aggregation-and-class-factory-macros.md)   
 [COM 맵 매크로](../atl/reference/com-map-macros.md)   
 [COM 맵 전역 함수](../atl/reference/com-map-global-functions.md)

