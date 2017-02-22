---
title: "CComAggObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComAggObject<contained>"
  - "ATL.CComAggObject"
  - "ATL.CComAggObject<contained>"
  - "CComAggObject"
  - "ATL::CComAggObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++], ATL"
  - "aggregation [C++], ATL 개체"
  - "CComAggObject class"
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CComAggObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에서 구현 된  [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 인터페이스는 집계 개체에 대 한.  정의에 따르면 집합체 외부 개체에 포함 되어 있습니다.  `CComAggObject` 클래스는 것은 [CComObject Class](../../atl/reference/ccomobject-class.md), 외부 클라이언트에 직접 액세스할 수 있는 인터페이스를 노출 된다는.  
  
## 구문  
  
```  
  
      template<  
   class contained  
>  
class CComAggObject :  
   public IUnknown, public CComObjectRootEx  
   < contained::_ThreadModel::ThreadModelNoCS >  
```  
  
#### 매개 변수  
 `contained`  
 파생 클래스에서  [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는  [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), 개체에서 지 원하는 다른 인터페이스 이름으로 원하는 대로.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComAggObject::CComAggObject](../Topic/CComAggObject::CComAggObject.md)|생성자입니다.|  
|[CComAggObject::~CComAggObject](../Topic/CComAggObject::~CComAggObject.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComAggObject::AddRef](../Topic/CComAggObject::AddRef.md)|집계 개체의 참조 횟수를 증가 시킵니다.|  
|[CComAggObject::CreateInstance](../Topic/CComAggObject::CreateInstance.md)|이 정적 함수를 새로 만들 수 있습니다  **CComAggObject \<** `contained`**\>** 개체의 오버 헤드 없이  [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComAggObject::FinalConstruct](../Topic/CComAggObject::FinalConstruct.md)|최종 초기화 수행 `m_contained`.|  
|[CComAggObject::FinalRelease](../Topic/CComAggObject::FinalRelease.md)|수행의 최종 파괴 `m_contained`.|  
|[CComAggObject::QueryInterface](../Topic/CComAggObject::QueryInterface.md)|요청 된 인터페이스에 대 한 포인터를 검색합니다.|  
|[CComAggObject::Release](../Topic/CComAggObject::Release.md)|집계 개체의 참조 카운트가 줄어듭니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CComAggObject::m\_contained](../Topic/CComAggObject::m_contained.md)|대리자 `IUnknown` 알 수 없는 외부 호출 합니다.|  
  
## 설명  
 `CComAggObject`구현  [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 의 집합체입니다.  `CComAggObject`자체의  **IUnknown** 인터페이스는 외부 개체에서의 별도  **IUnknown** 인터페이스, 및 해당 참조 횟수를 유지 합니다.  
  
 집계에 대 한 자세한 내용은  [ATL COM 개체의 기본 사항](../../atl/fundamentals-of-atl-com-objects.md).  
  
## 상속 계층 구조  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md)   
 [DECLARE\_ONLY\_AGGREGATABLE](../Topic/DECLARE_ONLY_AGGREGATABLE.md)   
 [DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)   
 [Class Overview](../../atl/atl-class-overview.md)