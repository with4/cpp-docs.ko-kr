---
title: "IUnknown 구현 클래스 (ATL) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.atl.Iunknown
dev_langs:
- C++
helpviewer_keywords:
- IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 53d5363f6b11904e31ea0e9c6f452b2c8fa7e000
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="iunknown-implementation-classes"></a>IUnknown 구현 클래스
다음 클래스에서는 구현 **IUnknown** 및 관련 메서드에서:  
  
-   [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) 참조 집계 및 집계 되지 않은 원시 개체에 대 한 계산을 관리 합니다. 스레딩 모델을 지정할 수 있습니다.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) 참조 집계 및 집계 되지 않은 원시 개체에 대 한 계산을 관리 합니다. 스레딩 모델 서버 기본값을 사용 합니다.  
  
-   [CComAggObject](../atl/reference/ccomaggobject-class.md) 구현 **IUnknown** 집계 개체에 대 한 합니다.  
  
-   [CComObject](../atl/reference/ccomobject-class.md) 구현 **IUnknown** 집계 되지 않은 원시 개체에 대 한 합니다.  
  
-   [CComPolyObject](../atl/reference/ccompolyobject-class.md) 구현 **IUnknown** 집계 및 집계 되지 않은 원시 개체에 대 한 합니다. 사용 하 여 `CComPolyObject` 두는 것을 방지 `CComAggObject` 및 `CComObject` 모듈에서입니다. 단일 `CComPolyObject` 집계 및 집계 되지 않은 원시 경우를 처리 하는 개체입니다.  
  
-   [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) 구현 **IUnknown** 모듈 잠금 수를 수정 하지 않고 집계 되지 않은 원시 개체입니다.  
  
-   [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) 구현 **IUnknown** 분리 인터페이스에 대 한 합니다.  
  
-   [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) 구현 **IUnknown** "캐시 된" 분리 인터페이스에 대 한 합니다.  
  
-   [CComContainedObject](../atl/reference/ccomcontainedobject-class.md) 구현 **IUnknown** 집계 또는 분리 인터페이스의 내부 개체에 대 한 합니다.  
  
-   [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) 관리 개체를 확인 하는 모듈에서 참조 횟수는 삭제 되지 않습니다.  
  
-   [CComObjectStack](../atl/reference/ccomobjectstack-class.md) 의 기본 구현을 사용 하 여 임시 COM 개체를 만듭니다 **IUnknown**합니다.  
  
## <a name="related-articles"></a>관련 문서  
 [ATL COM 개체 기본 사항](../atl/fundamentals-of-atl-com-objects.md)  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../atl/atl-class-overview.md)   
 [집계 및 클래스 팩터리 매크로](../atl/reference/aggregation-and-class-factory-macros.md)   
 [COM 맵 매크로](../atl/reference/com-map-macros.md)   
 [COM 맵 전역 함수](../atl/reference/com-map-global-functions.md)

