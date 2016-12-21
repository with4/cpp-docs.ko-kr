---
title: "Implementing CComObject, CComAggObject, and CComPolyObject | Microsoft Docs"
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
  - "CComPolyObject"
  - "CComAggObject"
  - "CComObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAggObject class"
  - "CComObject class, 구현"
  - "CComPolyObject class, 구현"
  - "CreateInstance 메서드"
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing CComObject, CComAggObject, and CComPolyObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스  [CComObject](../atl/reference/ccomobject-class.md),  [CComAggObject](../atl/reference/ccomaggobject-class.md), 및  [CComPolyObject](../atl/reference/ccompolyobject-class.md) 항상 상속 체인의 가장 많이 파생 된 클래스입니다.  책임 모든 메서드를 처리 하는 것이  **IUnknown**: `QueryInterface`, `AddRef`, 및  **릴리스**.  또한 `CComAggObject` 및 `CComPolyObject` \(집계 된 개체를 사용 하는 경우\) 특별 한 참조 횟수를 제공 하 고 `QueryInterface` 의미를 알 수 없는 내부 필요한.  
  
 여부 `CComObject`, `CComAggObject`, 또는 `CComPolyObject` 사용 다음 매크로 중 하나 \(또는 없음\)를 선언 하는지 여부에 따라 달라 집니다.  
  
|매크로|Effect|  
|---------|------------|  
|`DECLARE_NOT_AGGREGATABLE`|항상 사용 하 여 `CComObject`.|  
|`DECLARE_AGGREGATABLE`|사용 하 여 `CComAggObject` 개체를 집계 하는 경우 및 `CComObject` 되지 않은 경우.  `CComCoClass`이 매크로 포함 하므로 어떤 경우는  **DECLARE\_ \* \_AGGREGATABLE** 매크로 선언 된 클래스에이 야.|  
|`DECLARE_ONLY_AGGREGATABLE`|항상 사용 하 여 `CComAggObject`.  개체가 집계 되지 않은 경우 오류가 반환 됩니다.|  
|`DECLARE_POLY_AGGREGATABLE`|ATL의 인스턴스를 만들고  **CComPolyObject \<CYourClass\>** 때  **IClassFactory::CreateInstance** 라고 합니다.  만드는 동안 알 수 없는 외부의 값이 확인 됩니다.  이 경우  **NULL**,  **IUnknown** 집합체를 구현 합니다.  외부 알 수 없는 경우  **NULL**,  **IUnknown** 개체에 대 한 집계를 구현 합니다.|  
  
 사용 `CComAggObject` 및 `CComObject` 구현 하는 것이  **IUnknown** 생성 되는 개체의 종류에 가장 적합 합니다.  예를 들어, 집합체 참조 횟수를 알 수 없는 내부와 알 수 없는 외부에 대 한 포인터를 필요로 하는 동안 집합체 참조 횟수만 필요 합니다.  
  
 장점은 `CComPolyObject` 모두 필요 하지 않는 것입니다 `CComAggObject` 및 `CComObject` 집계 및 끌어냅니다 경우 처리 하는 모듈에서입니다.  단일 `CComPolyObject` 개체는 두 경우 모두 처리 합니다.  따라서 복사본 하나만 vtable 및 함수 중 하나의 복사본을 모듈에 존재 합니다.  Vtable이 큰 경우이 모듈 크기를 크게 줄일 수 있습니다.  그러나 vtable 작으면 사용 `CComPolyObject` 집계 또는 끌어냅니다 개체에 대 한 적합 하기 때문에 약간 더 큰 모듈 크기에 발생할 수 있습니다으로 `CComAggObject` 및 `CComObject`.  
  
## 참고 항목  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)   
 [Aggregation and Class Factory Macros](../atl/reference/aggregation-and-class-factory-macros.md)