---
title: "CComPolyObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComPolyObject"
  - "ATL.CComPolyObject<contained>"
  - "ATL::CComPolyObject"
  - "ATL::CComPolyObject<contained>"
  - "ATL.CComPolyObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++], ATL"
  - "aggregation [C++], ATL 개체"
  - "CComPolyObject class"
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComPolyObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 구현  **IUnknown** 개체 집계 또는 끌어냅니다.  
  
## 구문  
  
```  
  
      template<  
   class contained   
>  
class CComPolyObject : public IUnknown, public CComObjectRootEx  
   < contained::_ThreadModel::ThreadModelNoCS >  
```  
  
#### 매개 변수  
 `contained`  
 파생 클래스에서  [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는  [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), 개체에서 지 원하는 다른 인터페이스 이름으로 원하는 대로.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComPolyObject::CComPolyObject](../Topic/CComPolyObject::CComPolyObject.md)|생성자입니다.|  
|[CComPolyObject::~CComPolyObject](../Topic/CComPolyObject::~CComPolyObject.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComPolyObject::AddRef](../Topic/CComPolyObject::AddRef.md)|개체의 참조 횟수를 증가 시킵니다.|  
|[CComPolyObject::CreateInstance](../Topic/CComPolyObject::CreateInstance.md)|\(정적\) 새로 만들 수 있습니다  **CComPolyObject \<** `contained`**\>** 개체의 오버 헤드 없이  [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComPolyObject::FinalConstruct](../Topic/CComPolyObject::FinalConstruct.md)|최종 초기화 수행 `m_contained`.|  
|[CComPolyObject::FinalRelease](../Topic/CComPolyObject::FinalRelease.md)|수행의 최종 파괴 `m_contained`.|  
|[CComPolyObject::QueryInterface](../Topic/CComPolyObject::QueryInterface.md)|요청 된 인터페이스에 대 한 포인터를 검색합니다.|  
|[CComPolyObject::Release](../Topic/CComPolyObject::Release.md)|개체의 참조 횟수를 감소 시킵니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CComPolyObject::m\_contained](../Topic/CComPolyObject::m_contained.md)|대리자  **IUnknown** 개체를 집계 하는 경우 또는 호출을 알 수 없는 외부의  **IUnknown** 개체가 집계 되지 않은 경우 개체의.|  
  
## 설명  
 `CComPolyObject`구현  [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 개체 집계 또는 끌어냅니다.  
  
 인스턴스의 경우 `CComPolyObject` 만들어진 값은 외부의 알 수 없는 체크 합니다.  이 경우  **NULL**,  **IUnknown** 집합체를 구현 합니다.  외부 알 수 없는 경우  **NULL**,  **IUnknown** 개체에 대 한 집계를 구현 합니다.  
  
 장점은 `CComPolyObject` 모두 필요 하지 않는 것입니다  [CComAggObject](../../atl/reference/ccomaggobject-class.md) 및  [CComObject](../../atl/reference/ccomobject-class.md) 집계 및 끌어냅니다 경우 처리 하는 모듈에서입니다.  단일 `CComPolyObject` 개체는 두 경우 모두 처리 합니다.  따라서 복사본 하나만 vtable 및 함수 중 하나의 복사본을 모듈에 존재 합니다.  Vtable이 큰 경우이 모듈 크기를 크게 줄일 수 있습니다.  그러나 vtable 작으면 사용 `CComPolyObject` 집계 또는 끌어냅니다 개체에 대 한 적합 하기 때문에 약간 더 큰 모듈 크기에 발생할 수 있습니다으로 `CComAggObject` 및 `CComObject`.  
  
 경우는 `DECLARE_POLY_AGGREGATABLE` 매크로 개체의 클래스 정의에 지정 된 `CComPolyObject` 개체를 만드는 데 사용 됩니다.  `DECLARE_POLY_AGGREGATABLE`자동으로 ATL 프로젝트 마법사를 사용 하 여 전체 컨트롤 또는 Internet Explorer 컨트롤을 만드는 경우 선언 됩니다.  
  
 집계 하는 경우는 `CComPolyObject` 개체가 자체  **IUnknown**개체의 외부에서 별도  **IUnknown**, 자체 참조 카운트를 유지 하 고.  `CComPolyObject`사용  [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) 를 알 수 없는 외부를 위임할 수 있습니다.  
  
 집계에 대 한 자세한 내용은  [ATL COM 개체의 기본 사항](../../atl/fundamentals-of-atl-com-objects.md).  
  
## 상속 계층 구조  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComPolyObject`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md)   
 [Class Overview](../../atl/atl-class-overview.md)