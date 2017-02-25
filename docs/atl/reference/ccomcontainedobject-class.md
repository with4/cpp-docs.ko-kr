---
title: "CComContainedObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComContainedObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++], ATL"
  - "aggregation [C++], ATL 개체"
  - "CComContainedObject class"
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComContainedObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 구현  [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 소유자 개체에 위임 하 여  **IUnknown**.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template<  
class Base   
>  
class CComContainedObject :  
public Base  
```  
  
#### 매개 변수  
 `Base`  
 파생 클래스에서  [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는  [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md).  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComContainedObject::CComContainedObject](../Topic/CComContainedObject::CComContainedObject.md)|생성자입니다.  소유자 개체의 멤버 포인터 초기화 `IUnknown`.|  
|[CComContainedObject::~CComContainedObject](../Topic/CComContainedObject::~CComContainedObject.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComContainedObject::AddRef](../Topic/CComContainedObject::AddRef.md)|소유자 개체의 참조 횟수를 증가 시킵니다.|  
|[CComContainedObject::GetControllingUnknown](../Topic/CComContainedObject::GetControllingUnknown.md)|소유자 개체 검색 `IUnknown`.|  
|[CComContainedObject::QueryInterface](../Topic/CComContainedObject::QueryInterface.md)|소유자 개체에서 요청한 인터페이스에 대 한 포인터를 검색 합니다.|  
|[CComContainedObject::Release](../Topic/CComContainedObject::Release.md)|소유자 개체의 참조 횟수를 감소 시킵니다.|  
  
## 설명  
 ATL을 사용 하 여 `CComContainedObject` 클래스에  [CComAggObject](../../atl/reference/ccomaggobject-class.md),  [CComPolyObject](../../atl/reference/ccompolyobject-class.md), 및  [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md).  `CComContainedObject`구현  [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 소유자 개체에 위임 하 여  **IUnknown**.  \(소유자는 집계 외부 개체 또는 분리 된 인터페이스는 만들어진 개체입니다.\) `CComContainedObject` calls `CComObjectRootEx`'s `OuterQueryInterface`, `OuterAddRef`, and `OuterRelease`, all inherited through `Base`.  
  
## 상속 계층 구조  
 `Base`  
  
 `CComContainedObject`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)