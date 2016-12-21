---
title: "IUnknown Implementation Classes | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.Iunknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUnknown implementation classes"
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IUnknown Implementation Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 구현 클래스  **IUnknown** 와 관련 된 메서드.  
  
-   [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) 관리 참조 횟수 집계와 끌어냅니다.  스레딩 모델을 지정할 수 있습니다.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) 관리 참조 횟수 집계와 끌어냅니다.  스레딩 모델의 서버 기본값을 사용 합니다.  
  
-   [CComAggObject](../atl/reference/ccomaggobject-class.md) 구현  **IUnknown** 의 집합체입니다.  
  
-   [CComObject](../atl/reference/ccomobject-class.md) 구현  **IUnknown** 의 집합체입니다.  
  
-   [CComPolyObject](../atl/reference/ccompolyobject-class.md) 구현  **IUnknown** 개체를 집계 하 고 끌어냅니다.  사용 하 여 `CComPolyObject` 모두 필요가 없습니다 `CComAggObject` 및 `CComObject` 모듈에서.  단일 `CComPolyObject` 개체 처리 경우 집계 및 끌어냅니다.  
  
-   [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) 구현  **IUnknown** 에 대 한 모듈의 잠금 횟수를 수정 하지 않고 집합체.  
  
-   [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) 구현  **IUnknown** 분리 된 인터페이스.  
  
-   [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) 구현  **IUnknown** 에 대 한 "캐시 된" 분리 된 인터페이스.  
  
-   [CComContainedObject](../atl/reference/ccomcontainedobject-class.md) 구현  **IUnknown** 집계 또는 분리 된 인터페이스의 내부 개체에 대 한.  
  
-   [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) 관리 개체가 되도록 모듈의 참조 횟수를 삭제할 수 없습니다.  
  
-   [CComObjectStack](../atl/reference/ccomobjectstack-class.md) 는 골격 구현을 사용 하 여 임시 COM 개체를 만들고  **IUnknown**.  
  
## 관련된 기사  
 [ATL COM 개체의 기본 사항](../atl/fundamentals-of-atl-com-objects.md)  
  
## 참고 항목  
 [Class Overview](../atl/atl-class-overview.md)   
 [Aggregation and Class Factory Macros](../atl/reference/aggregation-and-class-factory-macros.md)   
 [COM Map Macros](../atl/reference/com-map-macros.md)   
 [COM Map Global Functions](../atl/reference/com-map-global-functions.md)